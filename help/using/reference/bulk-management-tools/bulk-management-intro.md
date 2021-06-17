---
description: 批量管理工具允許您通過單個操作一次建立和管理多個對象。 您可以使用大量管理工具來處理資料來源、衍生訊號、目的地、資料夾、區段和特徵。
keywords: baaam; BAAAM；下載baaam
seo-description: 批量管理工具允許您通過單個操作一次建立和管理多個對象。 您可以使用大量管理工具來處理資料來源、衍生訊號、目的地、資料夾、區段和特徵。
seo-title: 大量管理快速入門
solution: Audience Manager
title: 大量管理快速入門
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 911eab2d661907c6f1e2ffc08603d994bd346395
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 4%

---

# 大量管理快速入門{#getting-started-with-bulk-management}

[!DNL Bulk Management Tools]可讓您透過單一操作一次建立和管理多個物件。 您可以使用[!DNL Bulk Management Tools]來搭配[!UICONTROL data sources]、[!UICONTROL derived signals]、[!UICONTROL destinations]、[!UICONTROL folders]、[!UICONTROL models]、[!UICONTROL segments]和[!UICONTROL traits]使用。

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[使用者](../../features/administration/administration-overview.md) 介面中指派 [!DNL Audience Manager] 的RBAC群組權限會遵循 [!UICONTROL Bulk Management Tools]。

## 概述 {#overview}

此功能使用[!DNL Microsoft Excel]試算表及巨集，向[!DNL Audience Manager] API發出經過驗證的安全呼叫。 API提供的方法和服務可讓您大量進行變更。 您不必知道如何編寫程式碼或使用我們的API來使用。 工作表包含執行特定大量變更功能的欄標題和標籤。 若要進行大量變更，您只需將預先定義的標題新增至特定工作表、提供您要大量變更的資訊，然後按一下動作按鈕。 工作表和API為您完成其餘的工作。

## 下載 {#download}

下載最新工作表&#x200B;**[此處](assets/BAAAM_V2_20210609.xlsm)**（上次於2021年6月更新）。

## 必要條件 {#prereqs}

若要使用[!DNL Bulk Management Tools]，您需要下列項目：

* 您的[!DNL Experience Cloud]登入。 身為客戶，您應已具備這些認證。
* [!DNL Bulk Management Tools]工作表。 [下載](assets/BAAAM_V2_20200502.xlsm) worksheetto取得最新版本。
* [!DNL Microsoft Excel] 在64 [!DNL macOS] 位元或上執行 [!DNL Microsoft Windows]。建議您使用最新版本的[!DNL Microsoft Excel]。
* 開啟工作表時，必須&#x200B;**啟用宏**,[!DNL Bulk Management Tools]才能運作。

## 身份驗證要求和選項{#auth-reqs}

大量變更需要驗證。 執行任何動作之前，您必須先登入。 由於工作表會進行API呼叫，因此您需要將其設定為驗證至您的使用者帳戶。

**API驗證需求**

2019年10月發行的[!DNL Bulk Management Tools]第二版簡化了驗證程式。 此版本中的驗證步驟概述如下：

1. 開啟試算表並導覽至&#x200B;**[!UICONTROL Config]**&#x200B;工作表。
2. 按照工作表中概述的步驟操作。
   ![](assets/baaam-authentication.png)
3. 完成這些步驟後，您即獲授權進行大量變更。

進行大量變更時，您仍須確認您已獲得進行變更的授權，但API驗證會自動執行。

**域驗證選項**

網域驗證可讓您選擇測試大量請求，或直接將它們套用至您的生產帳戶。 對測試版環境進行大量變更不會影響您的生產帳戶。 生產變更會立即生效。 大量管理工作表可讓您在下列環境中工作：

* Beta
* 生產

## 操作和操作{#actions-ops}

[!UICONTROL Bulk Management Tools]工作表由驗證按鈕、操作頁簽、操作按鈕和&#x200B;**[!UICONTROL Headers]**&#x200B;頁簽組成。 **[!UICONTROL Headers]**&#x200B;頁簽包含操作頁簽使用的預格式化列標題。 操作頁簽包含執行所選批量操作的宏。 若要執行大量作業，請將一組標題複製到適當的動作標籤中、輸入標題資料，然後按一下動作按鈕。

在[驗證](#auth-reqs)後，按一下動作按鈕以開始使用。

![](assets/baaam-worksheet.png)

下表列出了可以執行的操作，以及可以在[!UICONTROL Bulk Management Tools]工作表中處理的項。

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 動作 </th> 
   <th colname="col2" class="entry"> 物件 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>大量動作會顯示在工作表底部的標籤中，並包含： </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">請求 </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">更新 </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">建立 </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">估計 </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">刪除 </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>您可以大量變更的物件位於<b><span class="uicontrol">標題</span></b>標籤下，並包含： </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 資料來源</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 衍生訊號</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 目的地</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> 模型</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 特徵資</a> 料夾和區段資料夾 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> 區段</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 特徵</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**批量操作示例**

例如，讓我們來看看如何一次建立多個特徵。 若要以大量作業建立多個特徵，請執行下列作業：

1. 按一下&#x200B;**[!UICONTROL Headers]**&#x200B;標籤，並複製[!UICONTROL Create a Trait]選項下的所有標籤。
2. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;標籤，然後貼上從第1行A列開始的標籤。
3. 提供與每個列標題相關的資訊，然後按一下&#x200B;**[!UICONTROL Create Traits]**。 此操作將提示您確認身份驗證。 確認驗證後，就會執行大量工作。 檢查工作表的左下角，以獲取作業狀態通知。


>[!NOTE]
>
>處理大型請求時，工作表可能會停止回應，且顯示為非作用中。 在這些情況下，別管它。 大量請求完成時，工作表會變得回應。 如果工作表長時間沒有回應，請參閱[疑難排解區段](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
