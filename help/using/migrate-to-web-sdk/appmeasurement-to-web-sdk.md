---
title: 將您的資料收集程式庫更新，以便從AppMeasurementJavaScript程式庫將其Audience Manager至Web SDK JavaScript程式庫。
description: 瞭解將資料收集程式庫從AppMeasurementJavaScript程式庫更新為Web SDK JavaScript程式庫以進行Audience Manager的步驟。
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: 3ba980e97763866d82bdf94109068f1f1f8f63d2
workflow-type: tm+mt
source-wordcount: '2398'
ht-degree: 0%

---


# 將您的資料收集程式庫更新，以便從AppMeasurementJavaScript程式庫Audience Manager至Web SDK JavaScript程式庫

## 目標對象 {#intended-audience}

此頁面適用於使用[!DNL AppMeasurement] JavaScript資料庫將Web資料傳送至Audience Manager的Audience Manager和Adobe Analytics客戶。

根據您目前的資料收集方法，請參閱下表的Web SDK移轉步驟指南。

| 您現有的資料收集方法 | Web SDK移轉指示 |
|---------|----------|
| [!DNL AppMeasurement] JavaScript資料庫 | 請依照本指南的指示操作。 |
| [!DNL Audience Manager] [標籤延伸模組](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | 依照[中的指示將您的資料收集程式庫從Audience Manager標籤擴充功能更新為Web SDK標籤擴充功能](dil-extension-to-web-sdk.md)。 |
| [!DNL AppMeasurement] JavaScript資料庫+ [!DNL Audience Manager] [DIL資料庫](../dil/dil-overview.md) | 依照[中的指示將您的資料收集程式庫從Audience Manager標籤擴充功能更新為Web SDK標籤擴充功能](dil-extension-to-web-sdk.md)。 |

## 移轉概述 {#overview}

從[!DNL AppMeasurement]移轉至[Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home)主要是Adobe Analytics移轉。 針對Audience Manager客戶，此移轉作業也包含Audience Manager。 兩者必須一起移轉。 如果您主要處理Audience Manager，請務必讓Analytics團隊參與此移轉。

如果您使用[!DNL AppMeasurement]進行Audience Manager資料收集，您目前使用[!DNL Server-side Forwarding (SSF)]方法將分析資料傳送至Audience Manager。 在此設定中，Analytics資料收集請求會轉送至Audience Manager，後者也會處理頁面的Audience Manager回應。

這是多年的標準方法，很可能是您目前的設定。 如果您的[!DNL AppMeasurement]程式庫包含`AudienceManagement`模組，而您的資料收集呼叫在要求(`/b/ss/examplereportsuite/10/`)中包含`/10/`路徑，則本指南適用於您。

## 伺服器端轉送(SSF)與Web SDK資料流程 {#data-flows}

了解轉向Web SDK時Analytics與Audience Manager之間的資料流程差異(和Edge Network)對以下指示至關重要。

透過伺服器端轉送，Analytics區域資料收集節點會收集資料，將其轉換為Audience Manager接受的訊號，傳送給Audience Manager，並將Audience Manager回應傳回至頁面。 [!DNL AppMeasurement]程式庫中的[!DNL AudienceManagement]模組接著會處理回應（例如，卸除Cookie、傳送URL目的地）。 此程式稱為伺服器端轉送，因為Analytics會使用Adobe伺服器將資料轉送至Audience Manager。

透過Web SDK，Edge Network會以個別動作將資料傳送至Analytics和Audience Manager。 Web SDK是將資料傳送至所有解決方案的單一資料庫，Edge Network會將與解決方案無關的資料點轉換為解決方案專用格式。

在這個新的資料流程中，所有資料都會傳送到Edge Network[資料串流](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview)，您可以[設定](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure)，視需要傳送資料到Adobe解決方案。 若為Audience Manager，在資料流上啟用Audience Manager服務會將[!DNL XDM]和Analytics資料轉換為Audience Manager接受的訊號。 Edge Network也會將Audience Manager回應傳回至頁面，其中Web SDK會處理回應，類似於[!DNL AppMeasurement]和[!DNL AudienceManagement]模組的處理方式。

## 標籤與非標籤移轉 {#tags-vs-non-tags}

無論您是使用具有[!DNL AppMeasurement]擴充功能的標籤、其他標籤管理系統中的[!DNL AppMeasurement]資料庫，或直接在頁面上放置[!DNL AppMeasurement]，將Audience Manager移轉至Web SDK的步驟都相同。 由於Audience Manager移轉取決於Analytics移轉，因此從[!DNL AppMeasurement]移轉至Web SDK的步驟會在Analytics移轉期間決定。

該資訊包含在[標籤](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)或[JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)型實作的Analytics檔案中。

## XDM和`data.__adobe.`節點 {#xdm-data-nodes}

[Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home)的主要功能之一是將資料傳送至[Real-time Customer Data Platform (RTCDP)](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home)。 為了達成此目的，同時仍會收集其他Experience Cloud解決方案的資料，而不需要完全的重新實作，解決方案的特定資料會在資料收集伺服器呼叫中加以區隔。 此呼叫使用名為[體驗資料模型(XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)的標準化JSON結構描述

解決方案無關的元素（例如關於瀏覽器和裝置的資訊）會以預先確定的XDM結構傳送給Edge Network。 Edge Network會將此資料轉換為解決方案專用格式。 不過，Target、Analytics和Audience Manager專屬的資料會儲存在XDM裝載內的專用`data.__adobe`節點中。

例如：

* Analytics變數`s.eVar1`在XDM承載中呈現為`data.__adobe.analytics.evar1`。
* 與客戶忠誠度狀態相關的Target引數會儲存為`data.__adobe.target.loyaltyStatus`。

`__adobe`節點中的資料會傳送至個別解決方案(例如Analytics和Audience Manager)，而不會傳送至Experience Platform，即使資料流中已啟用Experience Platform服務亦然。 這表示您可以保留目前的Analytics和Audience Manager設定，同時靈活地將任何必要的資料元素對應至XDM結構描述元素，以即時用於使用[資料收集的資料準備](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)進行Experience Platform的使用案例。

例如，在結帳期間用於報告購物車內容的Analytics `s.products`字串仍可以原始格式傳送到Analytics和Audience Manager。 同時，您可以使用此字串的元素，針對Experience Platform使用案例建立更直覺式的XDM購物車結構描述。

由於大多數Audience Manager實作依賴轉送至Audience Manager的Analytics資料，因此您的許多Audience Manager特徵運算式可能以Analytics變數（`c_evar#`、`c_prop#`和`c_events`）為基礎。 為避免在移轉期間使用XDM格式重建特徵運算式，預設會設定Edge Network將`data.__adobe.analytics`節點中找到的任何Analytics變數轉換為Audience Manager訊號。 此程式類似於伺服器端轉送工作流程。

Edge Network可以執行此轉換，因為來自頁面的單一資料收集呼叫會傳送到單一資料流，以饋送多個Adobe解決方案。 因此，大部分從[!DNL AppMeasurement]移轉至Analytics和Audience Manager的Web SDK時，都會主要使用`data.__adobe.analytics`節點。

Edge Network會將裝置和瀏覽器資料從XDM裝載和封包標題轉換為Audience Manager訊號。 這可讓您繼續在Audience Manager特徵運算式中使用`h_`和`d_`平台金鑰。

## `data.__adobe.audiencemanager`節點 {#data-note}

`data.__adobe.audiencemanager`節點用於不依賴Analytics的Audience Manager實作。 它儲存先前透過[Audience Manager資料庫](../dil/dil-overview.md)資料庫傳送的自訂DIL索引鍵/值組，如[標籤延伸移轉指南](dil-extension-to-web-sdk.md)中所述。

雖然本指南概述的移轉不需要`data.__adobe.audiencemanager`節點，但此處說明的新資料流程可讓資料傳送至Audience Manager，而不需在Analytics中記錄。

如果您需要傳送自訂索引鍵/值組至Audience Manager，而不將其納入Analytics，則可使用`data.__adobe.audiencemanager`節點。 此節點中的任何資料集都會附加至資料收集伺服器呼叫中Audience Manager轉換的Analytics資料。

## 此實作路徑的優缺點

使用此移轉方法的優缺點。 請仔細權衡每個選項，決定哪種方式最適合您的組織。

| 優勢 | 缺點 |
| --- | --- |
| <ul><li>**使用您現有的實作**：雖然此方法需要一些實作變更，但它不需要從頭開始的全新實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更。</li><li>**不需要結構描述**：對於移轉至Web SDK的這個階段，您不需要XDM結構描述。 相反地，您可以填入`data`物件，這會直接將資料傳送到Audience Manager。 一旦移轉至Web SDK完成，您就可以為貴組織建立結構描述，並使用資料流對應來填入適用的XDM欄位。 如果移轉流程的這個階段需要結構描述，貴組織將被強制使用Audience ManagerXDM結構描述。 使用此結構描述會使您的組織未來更難以使用您自己的結構描述。</li></ul> | <ul><li>**實作技術債**：由於此方法使用您現有實作的修改形式，因此可能更難追蹤實作邏輯，並在日後需要時執行變更。</li><li>**需要對應才能將資料傳送至Platform**：當您的組織準備好使用Real-Time CDP時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作要求`data`物件中的每個欄位必須是資料流對應工具中的專案，以將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li></ul> |

Adobe建議在下列情況下使用此實施路徑：

* 您已有使用Adobe AnalyticsAppMeasurementJavaScript資料庫的實作。 如果您有使用Audience Manager標籤擴充功能的實作，請改為遵循[從Audience Manager標籤擴充功能移轉至Web SDK標籤擴充功能](dil-extension-to-web-sdk.md)。
* 您打算在未來使用Real-Time CDP，但不想從頭開始使用Web SDK實作來取代您的Audience Manager實作。 在Web SDK上從頭開始取代實作需要花費最大心力，但同時也提供最可行的長期實作架構。 如果您的組織願意徹底實施Web SDK，請參閱[Web SDK檔案](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home)以取得詳細資訊。

## 移轉至Web SDK所需的步驟

請依照下列步驟，將您的資料收集整合移轉至Web SDK。

+++**1. 移轉您的Analytics實作**。

請與您的Analytics團隊合作，遵循[標籤](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)或[JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)型實作中的Analytics移轉步驟。 移轉Analytics實作後，請繼續下列步驟。

+++

+++**2.將Audience Manager服務新增至資料流**

將Audience Manager服務新增至您在步驟1建立的資料流。

1. 導覽至[experience.adobe.com](https://experience.adobe.com)並使用您的認證登入。
1. 使用右上方的首頁或產品選擇器來導覽至&#x200B;**[!UICONTROL Data Collection]**。
1. 在左側導覽中，選取&#x200B;**[!UICONTROL Datastreams]**。
1. 選取您在步驟1的Analytics移轉過程中建立的資料串流。
1. 選取&#x200B;**[!UICONTROL Add Service]**。
1. 在服務下拉式功能表中，選取&#x200B;**[!UICONTROL Audience Manager]**。
1. 檢查&#x200B;**[!UICONTROL Cookie Destinations Enabled]**&#x200B;和&#x200B;**[!UICONTROL URL Destinations Enabled]**&#x200B;選項。 這些選項可讓Edge Network將這些Audience Manager目的地型別傳回頁面。
1. 確定&#x200B;**[!UICONTROL Enable XDM Flattened Fields]**&#x200B;已停用。 此選項會停用Analytics變數自動轉換為Audience Manager訊號的功能。 此選項旨在為在Edge Network自動將Analytics資料轉換為Audience Manager訊號之前移轉至Web SDK的使用者維持回溯相容性。

   >[!NOTE]
   >
   >若要在啟用&#x200B;**[!UICONTROL Enabled XDM Flattened Fields]**&#x200B;選項的情況下移轉至Web SDK，必須更新XDM格式的Audience Manager中所需的任何資料，以及使用prop、eVar或事件的所有Audience Manager特徵，以尋找XDM格式的資料。 Adobe建議將此選項保持停用。


   ![新增Audience Manager服務](assets/add-service.png) {style="border:1px solid lightslategray"}

1. 選取&#x200B;**[!UICONTROL Save]**&#x200B;以儲存資料流組態。

您的資料流現在已準備好接收資料並傳遞給Audience Manager。 請記下資料串流ID，因為此ID在程式碼中設定Web SDK時是必要的。

+++

+++**3.啟用協力廠商ID同步並設定Audience Manager容器識別碼**

1. 導覽至[experience.adobe.com](https://experience.adobe.com)並使用您的認證登入。
1. 使用右上方的首頁或產品選擇器來導覽至&#x200B;**[!UICONTROL Data Collection]**。
1. 在左側導覽中，選取&#x200B;**[!UICONTROL Datastreams]**。
1. 選取您在步驟1的Analytics移轉過程中建立的資料串流。
1. 選取資料流設定頁面右上角的&#x200B;**[!UICONTROL Edit]**。
1. 展開&#x200B;**[!UICONTROL Advanced Options]**&#x200B;下拉式功能表，並啟用&#x200B;**[!UICONTROL Third Party ID Sync]**&#x200B;功能（如果尚未啟用）。 此選項會告訴Edge Network傳回Audience Manager與Experience Platform資料合作夥伴的合作夥伴ID同步。

   ![啟用協力廠商ID同步處理。](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. 在大多數情況下，您可以將&#x200B;**[!UICONTROL Third Party ID Sync Container ID]**&#x200B;欄位保留空白。 它將預設為`0`。 不過，如果您偏好確保使用正確的容器ID，請遵循下列步驟：
   * 以無痕模式或私密模式開啟瀏覽器視窗，並導覽至屬於移轉一部分的頁面。
   * 使用瀏覽器的開發人員工具來篩選`dpm.demdex.net/id`的網路呼叫。 此呼叫只會在首次造訪的第一個頁面上觸發，因此需要無痕瀏覽器或私人瀏覽器。
   * 檢視請求的裝載。 如果`d_nsid`引數不是零，請將其複製到&#x200B;**[!UICONTROL Third Party ID Sync Container ID]**&#x200B;欄位。

1. 選取&#x200B;**[!UICONTROL Save]**。

您的資料流現在已準備好將資料傳送至Audience Manager，並將Audience Manager回應傳遞至Web SDK。

+++

## 在Analytics報表套裝管理員UI中設定伺服器端轉送和Audience Analytics {#configure-ssf-analytics}

如果您熟悉Analytics [伺服器端轉送](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf)功能，可能會想知道：「*是否應在Analytics報表套裝管理員UI中停用伺服器端轉送設定，以防止將Analytics資料傳送至Audience Manager兩次？*」。

答案為否，您不應停用此設定。 原因如下：

啟用此設定並將[!DNL AudienceManagement]模組新增至頁面上的[!DNL AppMeasurement]資料庫時，所有傳送至該報表套裝的資料也會流入Audience Manager。

為了遵循GDPR隱私權法規，在某些情況下，可在Analytics中收集資料，但無法在Audience Manager中收集。 此外，某些情況下還涉及全域報表套裝和特定區域的使用案例，在這些案例中，部分資料收集呼叫不應傳送至Audience Manager。 為了解決此問題，Adobe推出伺服器端轉送「關閉按鈕」。

如[Analytics和GDPR法規遵循頁面著重於伺服器端轉送](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr)中所述，將`cm.ssf=1`內容變數新增至Analytics資料收集伺服器可防止資料收集呼叫轉送至Audience Manager。

不停用此設定有兩個原因。

1. 在資料流上啟用Audience Manager服務時，Edge Network會將`cm.ssf`變數附加至傳送給Analytics的所有資料收集要求。 這麼做也會防止Analytics資料傳送至Audience Manager。 在資料流上啟用Assurance服務後，所有用於驗證Analytics移轉的Audience Manager記錄都會顯示`cm.ssf=1`變數。
1. 此設定也會啟用[!DNL Audience Analytics]整合的資料流。 如[Audience Analytics概觀](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam)中所述，此整合需要伺服器端轉送，因為對Analytics資料收集伺服器的Audience Manager回應在處理前已新增到Analytics點選。 Edge Network中也會發生類似的程式。 啟用伺服器端轉送時，Edge Network會從Audience Manager回應將必要區段新增至傳送至Analytics的資料。

總而言之，此設定必須保持啟用，以便Audience Analytics可繼續與Web SDK實作搭配運作，而且沒有任何資料會在Audience Manager中重複計算。
