---
title: 從Audience Manager標籤擴充功能移轉至網路SDK標籤擴充功能
description: 瞭解將Audience Manager的資料收集程式庫從Audience Manager標籤擴充功能更新為Web SDK標籤擴充功能的步驟
exl-id: 7f0486db-4511-4311-90df-290580fdcd78
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---

# 將Audience Manager的資料收集程式庫從Audience Manager標籤擴充功能更新為網頁SDK標籤擴充功能

## 目標對象

此頁面適用於使用[Audience Manager標籤擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/audience-manager/overview)將網頁集合資料匯入Audience Manager的Audience Manager客戶。 若客戶使用AppMeasurement JavaScript資料庫，請參閱如何將Audience Manager [的資料收集資料庫從AppMeasurement JavaScript資料庫更新至Web SDK JavaScript資料庫](appmeasurement-to-web-sdk.md)的指南。

## 此實作路徑的優缺點

使用此移轉方法的優缺點。 請仔細權衡每個選項，決定哪種方式最適合您的組織。

| 優勢 | 缺點 |
| --- | --- |
| <ul><li>**您的網站上沒有程式碼變更**：因為您的實作已安裝標籤，所以可以在標籤介面中進行所有移轉更新。</li><li>**使用您現有的實作**：此方法不需要全新實作。 雖然這確實需要新的規則動作，但您可以以最小的變更重複使用現有的資料元素和規則條件。</li><li>**不需要結構描述**：對於移轉至Web SDK的這個階段，您不需要XDM結構描述。 相反地，您可以填入`data`物件，這會直接將資料傳送到Adobe Audience Manager。 一旦移轉至Web SDK完成，您就可以為貴組織建立結構描述，並使用資料流對應來填入適用的XDM欄位。 如果移轉流程的這個階段需要結構描述，貴組織將被強制使用Adobe Audience Manager XDM結構描述。 使用此結構描述會使您的組織未來更難以使用您自己的結構描述。</li></ul> | <ul><li>**實作技術債**：由於此方法使用您現有實作的修改形式，因此可能更難追蹤實作邏輯並在需要時執行變更。 自訂程式碼可能特別難以偵錯。</li><li>**需要對應才能將資料傳送至Platform**：當您的組織準備好使用Real-Time CDP時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作要求`data`物件中的每個欄位必須是資料流對應工具中的專案，以將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li></ul> |

Adobe建議您在有使用Adobe Audience Manager標籤擴充功能的現有實作時遵循此實作路徑。

## 移轉至Web SDK所需的步驟

下列步驟包含需努力達成的具體目標。 選取每個步驟，以取得如何完成的詳細說明。

+++**1. 建立和設定資料流**

請依照下列指示，在Adobe Experience Platform Data Collection中建立資料流。 當您傳送資料至此資料流時，它會轉送資料至Audience Manager。 未來，相同的資料流會將資料轉送至Real-Time CDP。

1. 導覽至[experience.adobe.com](https://experience.adobe.com)並使用您的認證登入。
1. 使用右上方的首頁或產品選擇器來導覽至&#x200B;**[!UICONTROL Data Collection]**。
1. 在左側導覽中，選取&#x200B;**[!UICONTROL Datastreams]**。
1. 選取&#x200B;**[!UICONTROL New Datastream]**。
1. 輸入所要的名稱，然後選取&#x200B;**[!UICONTROL Save]**。
1. 建立資料流後，請選取&#x200B;**[!UICONTROL Add Service]**。
1. 在服務下拉式功能表中，選取&#x200B;**[!UICONTROL Adobe Audience Manager]**。
1. 請確定未核取&#x200B;**[!UICONTROL Enable XDM Flattened Fields]**&#x200B;選項。

   ![新增Audience Manager服務](assets/add-service.png) {style="border:1px solid lightslategray"}

您的資料流現在已準備好接收資料並傳遞給Audience Manager。

+++

+++**2.將Web SDK擴充功能新增至標籤屬性**

本節將準備您的標籤，以利後續步驟中進行的大量移轉作業。

1. 選取Adobe Experience Platform介面左上角的漢堡圖示，然後選取&#x200B;**[!UICONTROL Tags]**。
1. 選取所需的標籤屬性。
1. 在標籤屬性的左側導覽中，選取&#x200B;**[!UICONTROL Extensions]**。
1. 選取頂端附近的&#x200B;**[!UICONTROL Catalog]**，檢視所有可用副檔名的清單。
1. 搜尋並選取&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;副檔名，然後在右側選取&#x200B;**[!UICONTROL Install]**。

   ![目錄](assets/catalog.png) {style="border:1px solid lightslategray"}

1. 擴充功能組態設定隨即顯示。 找到&#x200B;**[!UICONTROL Datastreams]**&#x200B;區段，然後選取您使用的沙箱以及您在上一步中建立的資料流。

   ![資料流選擇](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. 選取&#x200B;**[!UICONTROL Save]**。

您的標籤屬性現在已安裝Web SDK。

+++

+++**3.建立資料物件資料元素**

資料物件資料元素提供直覺式架構，可設定Web SDK用來傳送至資料流的裝載。 您在下列步驟中更新的大部分規則都會與此資料元素互動。

1. 在標籤介面的左側導覽中，選取&#x200B;**[!UICONTROL Data Elements]**。
1. 選取&#x200B;**[!UICONTROL Add Data Element]**
1. 為資料元素執行下列設定：
   * **[!UICONTROL Name]**：您想要的任何專案，例如「資料層」或「資料物件」
   * **[!UICONTROL Extension]**： [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**： [!UICONTROL Variable]
   * 核取方塊可以維持原狀。
1. 在右側，選取下列設定：
   * 屬性選項按鈕： **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**： [!UICONTROL Adobe Audience Manager]
1. 選取&#x200B;**[!UICONTROL Save]**。

   ![建立資料元素](assets/create-data-element.png) {style="border:1px solid lightslategray"}

您的標籤屬性現在擁有更新每個規則所需的一切。

+++

+++**4.更新規則以使用Web SDK擴充功能，而非Audience Manager擴充功能**

此步驟包含移轉至Web SDK所需的大部分工作，且需要瞭解您實作的運作方式。 以下提供如何編輯典型標籤規則的範例。 更新實施中的所有標籤規則，以Web SDK擴充功能取代Audience Manager擴充功能的所有參考。

1. 在標籤介面的左側導覽中，選取&#x200B;**[!UICONTROL Rules]**。
1. 選取要編輯的規則。
1. 選取動作&#x200B;**[!UICONTROL Audience Manager - Set Variables]**
1. 請注意在此規則內設定的所有Audience Manager變數。 納入在下拉式功能表中設定的變數，以及在自訂程式碼中設定的變數。
1. 將[!UICONTROL Action Configuration]變更為下列設定：
   * **[!UICONTROL Extension]**： [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**：更新變數
1. 確定已在右側&#x200B;**[!UICONTROL Data element]**&#x200B;欄位的下拉式清單中選取您在步驟3建立的資料物件。
1. 將Audience Manager機碼值組設為其各自在Audience Manager擴充功能中設定的相同值。
1. 使用Web SDK擴充功能復寫所有規則邏輯後，請選取&#x200B;**[!UICONTROL Keep Changes]**。
1. 對使用Audience Manager標籤擴充功能設定值的每個動作設定重複這些步驟。

上述步驟僅適用於設定值的規則。 下列步驟會取代所有使用[!UICONTROL Action Configuration] [!UICONTROL Send Event]的動作。

1. 選取傳送網頁SDK事件的規則。
1. 選取動作型別&#x200B;**[!UICONTROL Send Event]**。
1. 將[!UICONTROL Action Configuration]變更為下列設定：
   * **[!UICONTROL Extension]**： [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**： [!UICONTROL Send event]
1. 在右側，將動作設定變更為下列專案：
   * **[!UICONTROL Type]**：使用&#x200B;**[!UICONTROL Web Webpagedetails Page Views]**。
   * **[!UICONTROL Data]**：選取您在步驟3建立的資料物件。
1. 選取&#x200B;**[!UICONTROL Keep Changes]**。
1. 對使用Audience Manager傳送事件的每個動作設定重複這些步驟。

+++

+++**5.發佈更新的規則**

發佈更新規則的工作流程，與標籤設定的任何其他變更相同。

1. 在標籤介面的左側導覽中，選取&#x200B;**[!UICONTROL Publishing Flow]**。
1. 選取&#x200B;**[!UICONTROL Add Library]**。
1. 為此標籤認可命名，例如「升級至Web SDK」。
1. 選取&#x200B;**[!UICONTROL Add All Changed Resources]**。
1. 選取&#x200B;**[!UICONTROL Save]**。
1. 發佈工作流程會顯示橘色點，表示正在建置。 圓點變成綠色後，您的變更即可在開發環境中使用。
1. 在開發環境中測試您的變更，以確保所有規則皆正確引發，且資料物件會填入預期值。
1. 準備就緒後，請提交程式庫進行核准、建置到測試環境，最後核准並發佈到生產環境。

   ![發佈流程](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6.停用Audience Manager擴充功能**

將標籤實作完全移轉至Web SDK後，您就可以停用Audience Manager擴充功能。

1. 在標籤介面的左側導覽中，選取&#x200B;**[!UICONTROL Extensions]**。
1. 找到並選取[!UICONTROL Audience Manager]副檔名。 在右側選取&#x200B;**[!UICONTROL Disable]**。
1. 依照上述相同的發佈工作流程，發佈移除[!UICONTROL Audience Manager]延伸模組。
1. 擴充功能在生產環境中停用後，您就可以完全解除安裝。 選取副檔名，選取右側的三個點功能表，然後選取&#x200B;**[!UICONTROL Uninstall]**。
1. 按照上面的相同發佈工作流程，將這些變更發佈到生產環境。

+++

此時，您的Audience Manager實作已完全移轉至Web SDK，並準備好在未來移轉至Real-Time CDP。
