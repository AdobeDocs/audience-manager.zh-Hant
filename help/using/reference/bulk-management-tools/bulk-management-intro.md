---
description: 使用批量管理工具，您可以通過單個操作一次建立和管理多個對象。 可以使用批量管理工具處理資料源、派生信號、目標、資料夾、段和特徵。
keywords: baaam;BAAAM；下載baam
seo-description: The Bulk Management Tools let you create and manage multiple objects at once with single operation. You can use Bulk Management Tools to work with data sources, derived signals, destinations, folders, segments, and traits.
seo-title: Getting Started With Bulk Management
solution: Audience Manager
title: 大量管理快速入門
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 911eab2d661907c6f1e2ffc08603d994bd346395
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 3%

---

# 大量管理快速入門{#getting-started-with-bulk-management}

的 [!DNL Bulk Management Tools] 允許您使用單個操作一次建立和管理多個對象。 您可以使用 [!DNL Bulk Management Tools] 與 [!UICONTROL data sources]。 [!UICONTROL derived signals]。 [!UICONTROL destinations]。 [!UICONTROL folders]。 [!UICONTROL models]。 [!UICONTROL segments], [!UICONTROL traits]。

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[RBAC組權限](../../features/administration/administration-overview.md) 在 [!DNL Audience Manager] 用戶介面在 [!UICONTROL Bulk Management Tools]。

## 概述 {#overview}

此功能使用 [!DNL Microsoft Excel] 帶有宏的電子錶格，可對其進行安全、經過驗證的調用 [!DNL Audience Manager] API。 API提供了允許您批量進行更改的方法和服務。 您不必知道如何編碼或使用我們的API來使用它。 工作表包含執行特定批量更改功能的列標題和標籤。 要進行批量更改，您只需將預定義的標題添加到特定工作表，提供要批量更改的資訊，然後按一下操作按鈕。 工作表和API將為您完成其餘工作。

## 下載 {#download}

下載最新工作表 **[這裡](assets/BAAAM_V2_20210609.xlsm)** （上次更新於2021年6月）。

## 必要條件 {#prereqs}

使用 [!DNL Bulk Management Tools]，您需要：

* 您 [!DNL Experience Cloud] 登錄。 作為客戶，您應該已經擁有這些憑據。
* 的 [!DNL Bulk Management Tools] 工作表。 [下載工作表](assets/BAAAM_V2_20200502.xlsm) 獲取最新版本。
* [!DNL Microsoft Excel] 運行 [!DNL macOS] 或64位 [!DNL Microsoft Windows]。 建議您使用 [!DNL Microsoft Excel]。
* 開啟工作表時，必須 **啟用宏** 為 [!DNL Bulk Management Tools] 工作。

## 身份驗證要求和選項 {#auth-reqs}

批量更改需要身份驗證。 執行任何操作之前，必須登錄。 由於工作表進行API調用，因此您需要將其配置為在用戶帳戶中進行身份驗證。

**API驗證要求**

第二版 [!DNL Bulk Management Tools]於2019年10月發佈，簡化了驗證過程。 此版本中的驗證步驟概述如下：

1. 開啟電子錶格並導航到 **[!UICONTROL Config]** 的子菜單。
2. 按照工作表中概述的步驟操作。
   ![](assets/baaam-authentication.png)
3. 完成這些步驟後，您有權進行批量更改。

進行批量更改時，您仍須確認您有權進行更改，但API驗證是自動的。

**域驗證選項**

域身份驗證允許您選擇test批量請求或直接將其應用於生產帳戶。 對測試版環境進行批量更改不會影響您的生產客戶。 生產更改將立即生效。 批量管理工作表允許您在以下環境中工作：

* Beta
* 生產

## 操作和操作 {#actions-ops}

的 [!UICONTROL Bulk Management Tools] 工作表由驗證按鈕、操作頁籤、操作按鈕和 **[!UICONTROL Headers]** 頁籤。 的 **[!UICONTROL Headers]** 頁籤包含操作頁籤使用的預格式列標題。 操作頁籤包含執行所選批量操作的宏。 要執行批量操作，請將一組標題複製到相應的操作頁籤中，輸入標題資料，然後按一下操作按鈕。

之後 [驗證](#auth-reqs)，按一下操作按鈕開始。

![](assets/baaam-worksheet.png)

下表列出了可執行的操作和可使用 [!UICONTROL Bulk Management Tools] 工作表。

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 動作 </th> 
   <th colname="col2" class="entry"> 對象 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>批量活動顯示在工作表底部的標籤中，包括： </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">請求 </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">更新 </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">建立 </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">估計 </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">刪除 </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>可以批量更改的對象位於 <b><span class="uicontrol"> 標題</span></b> 頁籤，包括： </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 資料源</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 派生信號</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 目的地</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> 模型</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 特徵資料夾</a> 和段資料夾 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> 區段</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 特徵</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**批量操作示例**

例如，讓我們看一下如何同時建立多個特徵。 要在批量操作中建立多個特徵，您需要：

1. 按一下 **[!UICONTROL Headers]** 頁籤並複製 [!UICONTROL Create a Trait] 的雙曲餘切值。
2. 按一下 **[!UICONTROL Create]** 頁籤，然後貼上從第1行第A列開始的標籤。
3. 提供與每個列標題相關的資訊，然後按一下 **[!UICONTROL Create Traits]**。 此操作將提示您確認身份驗證。 在確認身份驗證後，將運行批量作業。 檢查工作表左下角的職務狀態通知。


>[!NOTE]
>
>處理大量請求時，工作表可能無響應，並且似乎處於非活動狀態。 在這些情況下，別管它。 完成批量請求後，工作表將響應。 如果工作表長時間沒有響應，請參閱 [疑難解答部分](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
