---
description: 入站狀態報告檢查入站資料源檔案中處理記錄的成功率和失敗率。 此報表以互動式條形圖顯示資料，並以表格形式提供摘要度量。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在分析>登機狀態報告中找到此報告。 建立入站資料源時，此報告也可用。
seo-description: The Onboarding Status Report checks success and failure rates for processing records in your inbound data source files. This report displays data in an interactive bar chart and provides summary metrics in tabular form. And, it includes an option that samples files for a fixed time interval and displays the most common errors for each error type. You can find this report in Analytics > Onboarding Status Report. This report is also available when you create an inbound data source.
seo-title: Onboarding Status Report
solution: Audience Manager
title: 上線狀態報表
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: Inbound and Outbound Reports
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1416'
ht-degree: 6%

---

# 上線狀態報表{#onboarding-status-report-about}

入站狀態報告檢查入站資料源檔案中處理記錄的成功率和失敗率。 此報表以互動式條形圖顯示資料，並以表格形式提供摘要度量。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在分析>登機狀態報告中找到此報告。 建立入站資料源時，此報告也可用。

>[!NOTE]
>
>只有具有管理員權限的用戶才能在Audience Manager用戶介面中查看此報告。 您可以將非管理員用戶的電子郵件添加到報告中，以通知他們已上傳入站檔案的狀態。 請參閱 [接收電子郵件通知](/help/using/reporting/onboarding-status-report.md#receive-email-notifications)。

## 入門狀態報告：關於 {#onboarding-status-about}

的 [!UICONTROL Onboarding Status Report] 檢查入站資料源檔案中處理記錄的成功率和失敗率。 此報表以互動式條形圖顯示資料，並以表格形式提供摘要度量。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在 **[!UICONTROL Analytics > Onboarding Status Report]**。 建立入站資料源時，此報告也可用。

## 錯誤報告和錯誤採樣 {#error-reporting-sampling}

錯誤報告和錯誤採樣是 [!UICONTROL Onboarding Status] 報告。

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 功能 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>錯誤報告</b> </p> </td>
   <td colname="col2"> <p>錯誤報告顯示入站資料源中處理的記錄數的成功率和失敗率。 它返回互動式堆疊條形圖中的資料，以及圖表下表中的摘要度量。 </p> <p>錯誤報告是自動的。 它針對所有入站資料源持續運行。 它根據預設時間間隔範圍或您使用日曆構件設定的自定義時間間隔返回資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>錯誤採樣</b> </p> </td>
   <td colname="col2"> <p>採樣錯誤分析資料檔案的內容並返回每種錯誤類型的10個最常見錯誤。 入站資料檔案中的錯誤會阻止處理單個記錄。 將此報告用作故障排除工具，以幫助減少檔案錯誤數並提高處理率。 </p> <p>必須手動激活錯誤採樣。 從激活之日起，它會運行14天，然後關閉它。 在14天間隔過期後，可以重新開啟錯誤採樣。 在您 <a href="../features/manage-datasources.md#create-data-source"> 建立入站資料源</a> 或通過檢查 <b><span class="uicontrol"> 錯誤採樣</span></b> 的子菜單。 <span class="wintitle"> 資料源設定</span> 現有入站資料源的部分。 </p> <p>誤差採樣是一個計算量很大的過程。 因此，它僅為每個錯誤類別返回前10個錯誤。 它不是設計為返回入站資料源中包含的每個錯誤。 這些錯誤是一組可能較大的類似錯誤的典型示例。 查看整個檔案，瞭解此報告標籤的錯誤類型，重新格式化檔案，然後再次發送。 </p> <p>請參閱 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 入站資料檔案內容：語法、變數和示例</a> 的子菜單。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 錯誤報表條形圖 {#error-report-bar-chart}

錯誤報告用圖形表示堆疊條形圖中記錄處理的成功率和失敗率，如下例所示。 圖是交互的。 按一下某個欄在圖形下面的表中顯示該日的摘要度量。

![](assets/stacked-graph.png)

## 錯誤報表 {#error-report-tables}

錯誤報告在條形圖下方顯示表格資料。 該表顯示了成功率和失敗率以及合計和百分比。

**成功記錄和失敗記錄**

此預設視圖顯示報告中總記錄的頻率計數，並包括按錯誤類型劃分的錯誤細目。

![](assets/success-failure.png)

**合計和百分比**

按一下 **[!UICONTROL Totals & Percentages]** 查看已成功處理的檔案百分比。

![](assets/totals-percentages.png)

## 14天的錯誤採樣報告 {#error-reporting-14-days}

如果錯誤採樣處於活動狀態，則報告將顯示每種錯誤類型的前10個錯誤。 按一下報表頂部的錯誤類型按鈕以查看每組採樣資料。

>[!NOTE]
>
>此報告不會突出顯示此當前版本中的記錄錯誤。 要查找和修復檔案錯誤，您應查看結果，並將結果與中的規範進行比較 [入站資料檔案內容](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 文檔。

![](assets/error-samples.png)

## 接收電子郵件通知 {#receive-email-notifications}

您可以添加收件人的電子郵件地址，以通知您上載的入站檔案的狀態。 請注意，您可以為不同的資料源選擇不同的收件人。

![](assets/mail-notifications.png)

## 建立入門狀態報告 {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] 返回資料源中的數字記錄已成功處理，失敗數目。 按照以下步驟生成 [!UICONTROL Sample Error Report]。

<!-- 

create-onboarding-status-report.xml

 -->


1. 轉到 **[!UICONTROL Analytics > Onboarding Status Report]**。 搜索資料源或從清單中選擇資料源。

2. 選擇日期範圍。 選項包括:

   * 一組固定的報告間隔。
   * 用於建立自定義日期範圍的日曆小部件。

3. 按一下 **[!UICONTROL OK]**.

## 入門狀態報表術語和定義 {#report-terms-conditions}

此報告中使用的標籤和術語的參考指南。

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 術語 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>資料同步檔案名</b> </p> </td> 
   <td colname="col2"> <p>列出 <span class="keyword"> Audience Manager</span> 從您選擇的入站資料源接收並處理。 </p> <p>如果檔案名格式不正確，檔案處理將失敗。 檔案名要求因您將資料發送到的方式而異 <span class="keyword"> Audience Manager</span>。 傳遞方法包括 <span class="keyword"> AmazonS3</span> 和FTP。 有關如何命名檔案的說明，請參閱： </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 傳入資料檔案的 Amazon S3 名稱要求 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>格式錯誤</b> </p> </td> 
   <td colname="col2"> <p>列出由於不符合語法或格式要求而處理失敗的記錄數。 請參閱 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 入站資料檔案內容：語法、變數和示例</a> 中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>無效AAMID</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正確的數目 <span class="keyword"> Audience Manager</span> 用戶ID(UUID)。 通常，這表示ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">與預期的38位格式不匹配。 </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">包含字母字元。 ID應僅為數字。 </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>設備ID無效</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正確的全局設備ID的數量。 請參閱 <a href="../reference/ids-in-aam.md">Audience Manager中ID的索引</a> 和 <a href="../features/global-data-sources.md">全局資料源</a>  有關設備ID應如何格式化以及您應使用哪些全局資料源的詳細資訊，請參閱設備類型。</p>
  <p>報告的錯誤採樣部分包含有關無效設備ID的詳細資訊，如：</p>
   <ul>
    <li>與無效設備ID對應的資料源ID;</li>
    <li>無效的設備ID;</li>
    <li>基於資料源的預期設備ID的類型。</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>無匹配AAMID</b> </p> </td> 
   <td colname="col2"> <p>這些是已登入的ID <span class="keyword"> Audience Manager</span> 無法與現有ID匹配。 登入的ID在 <span class="keyword"> Audience Manager</span> 尚未執行ID同步，或者即使同步後仍無法與ID匹配。 </p> <p>如果移動ID不匹配， <span class="keyword"> Audience Manager</span> 將： </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">繼續儲存並嘗試同步此ID。 </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">記錄為 <span class="wintitle"> 儲存記錄</span> 框中。 </li> 
    </ul> <p>如果您的掛接檔案包含移動ID，則您可以比其他度量輕一點地處理這些數字。 它們不會影響成功和後續檔案的匹配率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未實現任何特性</b> </p> </td> 
   <td colname="col2"> <p>列出 <span class="keyword"> Audience Manager</span> 不能與一種單身特質相匹配。 這可能是以下原因造成的： </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">入站資料檔案中的特徵格式不正確。 有關如何格式化資料檔案的資訊，請參見 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 入站資料檔案內容：語法、變數和示例</a>。 </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">尚未定義的特徵 <span class="keyword"> Audience Manager</span>。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>成功百分比</b> </p> </td> 
   <td colname="col2"> <p>檔案中成功儲存的記錄百分比。 成功百分比=已處理的記錄/檔案中的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>接收的記錄</b> </p> </td> 
   <td colname="col2"> <p>接收的記錄總數。 在大多數情況下，此數字應與入站資料檔案中的記錄（行）總數相匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>儲存的記錄</b> </p> </td> 
   <td colname="col2"> <p>成功儲存的記錄數。 由於檔案格式錯誤，某些接收的記錄可能由 <span class="keyword"> Audience Manager</span>。 儲存的記錄數可以小於接收的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>已實現特徵總數</b> </p> </td> 
   <td colname="col2"> <p>儲存在 <span class="keyword"> Audience Manager</span> 平台。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未使用信號總數</b> </p> </td> 
   <td colname="col2"> <p>報告中接收的未使用信號總數。 此總數基於成功儲存的記錄總數。 </p> <p>請參閱 <a href="../reporting/dynamic-reports/unused-signals.md"> 未使用的信號報告</a> 的子菜單。 </p> </td> 
  </tr> 
 </tbody> 
</table>
