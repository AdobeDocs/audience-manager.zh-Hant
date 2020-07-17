---
description: 入門狀態報告會檢查傳入資料來源檔案中處理記錄的成功和失敗率。 此報告以互動式長條圖顯示資料，並以表格形式提供摘要度量。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在「Analytics >登入狀態報表」中找到此報表。 當您建立傳入資料來源時，也可使用此報表。
seo-description: 入門狀態報告會檢查傳入資料來源檔案中處理記錄的成功和失敗率。 此報告以互動式長條圖顯示資料，並以表格形式提供摘要度量。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在「Analytics >登入狀態報表」中找到此報表。 當您建立傳入資料來源時，也可使用此報表。
seo-title: 上線狀態報表
solution: Audience Manager
title: 上線狀態報表
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: inbound and outbound reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1498'
ht-degree: 7%

---


# 上線狀態報表{#onboarding-status-report-about}

入門狀態報告會檢查傳入資料來源檔案中處理記錄的成功和失敗率。 此報告以互動式長條圖顯示資料，並以表格形式提供摘要度量。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在「Analytics >登入狀態報表」中找到此報表。 當您建立傳入資料來源時，也可使用此報表。

>[!NOTE]
>
>只有具有管理員權限的使用者才能在Audience Manager使用者介面中看到此報表。 您可以讓非管理員使用者透過將電子郵件新增至報表，得知已上傳傳入檔案的狀態。 請參 [閱接收電子郵件通知](/help/using/reporting/onboarding-status-report.md#receive-email-notifications)。

## 入門狀態報告： 關於 {#onboarding-status-about}

The [!UICONTROL Onboarding Status Report] checks success and failure rates for processing records in your inbound data source files. 此報告以互動式長條圖顯示資料，並以表格形式提供摘要度量。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在中找到此報表 **[!UICONTROL Analytics > Onboarding Status Report]**。 當您建立傳入資料來源時，也可使用此報表。

## 錯誤報告和錯誤抽樣 {#error-reporting-sampling}

錯誤報告和錯誤取樣是報告的2個獨立 [!UICONTROL Onboarding Status] 功能。

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
   <td colname="col2"> <p>錯誤報告顯示入站資料源中處理的記錄數的成功率和失敗率。 它會以互動式堆疊長條圖傳回資料，並在圖表下方的表格中傳回摘要度量。 </p> <p>自動報告錯誤。 它會持續為所有傳入的資料來源執行。 它會根據預設時間間隔範圍或您使用日曆介面工具集設定的自訂時間間隔，傳回資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>誤差取樣</b> </p> </td>
   <td colname="col2"> <p>錯誤取樣會剖析資料檔案的內容，並針對每個錯誤類型傳回10個最常見的錯誤。 傳入資料檔案中的錯誤會導致無法處理個別記錄。 使用此報告做為疑難排解工具，可協助減少檔案錯誤數量並改善處理率。 </p> <p>您必須手動激活錯誤採樣。 從啟動當日開始，它會持續14天，然後關閉自己。 您可以在14天間隔過期後重新開啟錯誤取樣。 在建立入站資料源時 <a href="../features/manage-datasources.md#create-data-source"></a><b><span class="uicontrol"></span></b><span class="wintitle"></span> ，或通過選中現有入站資料源的「資料源設定」部分中的「錯誤採樣」複選框來激活錯誤採樣。 </p> <p>誤差採樣是計算量大的過程。 因此，它只會針對每個錯誤類別傳回前10個錯誤。 它並非設計為傳回傳入資料來源中包含的所有錯誤。 這些錯誤是一組可能較大的類似錯誤的代表性示例。 檢閱整個檔案，瞭解此報告標幟的錯誤類型、重新格式化檔案，然後再次傳送。 </p> <p>請參閱 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 傳入資料檔案內容： 語法、變數和範例</a> ，以取得如何正確設定傳入資料來源之資料檔案格式的詳細資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 錯誤報表長條圖 {#error-report-bar-chart}

錯誤報告會以圖形表示堆疊長條圖中記錄處理的成功與失敗率，如下列範例所示。 圖表是互動式的。 按一下橫條，圖表下方的表格中會顯示當天的摘要量度。

![](assets/stacked-graph.png)

## 錯誤報表 {#error-report-tables}

錯誤報告會在長條圖下方顯示表格式資料。 表格顯示成功與失敗率，以及總數和百分比。

**成功和失敗的記錄**

此預設檢視會顯示報表中記錄總數的頻率計數，並依錯誤類型包含錯誤的劃分。

![](assets/success-failure.png)

**總計與百分比**

按一 **[!UICONTROL Totals & Percentages]** 下，查看哪些%的檔案已成功處理。

![](assets/totals-percentages.png)

## 14天錯誤取樣報告 {#error-reporting-14-days}

當錯誤取樣作用中時，報表會顯示每個錯誤類型的前10個錯誤。 按一下報表頂端的錯誤類型按鈕，以檢視每組取樣資料。

>[!NOTE]
>
>報告不會反白顯示此目前版本的記錄錯誤。 要查找和修正檔案錯誤，您應查看結果，並將結果與傳入資料檔案內容文檔中 [的規範進行比較](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 。

![](assets/error-samples.png)

## 接收電子郵件通知 {#receive-email-notifications}

您可以新增收件者的電子郵件地址，以便收到上傳傳入檔案狀態的通知。 請注意，您可以為不同的資料來源選擇不同的收件者。

![](assets/mail-notifications.png)

## 建立入職狀態報表 {#create-onboard-status-report}

返 [!UICONTROL Sample Error Report] 回資料源中成功處理的數量記錄和失敗數。 請依照下列步驟產生 [!UICONTROL Sample Error Report]。

<!-- 

create-onboarding-status-report.xml

 -->


1. 前往 **[!UICONTROL Analytics > Onboarding Status Report]**。 搜尋資料來源，或從清單中選擇一個。

2. 選擇日期範圍。 選項包括:

   * 一組固定報告間隔。
   * 可讓您建立自訂日期範圍的日曆Widget。

3. 按一下 **[!UICONTROL OK]**.

## 入門狀態報表術語和定義 {#report-terms-conditions}

此報告中使用之標籤和詞語的參考指南。

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 術語 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>資料同步檔案名稱</b> </p> </td> 
   <td colname="col2"> <p>列出 <span class="keyword"></span> Audience Manager從您選取的傳入資料來源接收並處理的檔案。 </p> <p>如果檔案名的格式不正確，檔案處理將失敗。 檔案名稱需求會依您將此資料傳送至 <span class="keyword"> Audience Manager的方式而異</span>。 傳送方法 <span class="keyword"> 包括Amazon S3</span> 和FTP。 如需如何命名檔案的指示，請參閱： </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 傳入資料檔案的 Amazon S3 名稱要求 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>格式錯誤</b> </p> </td> 
   <td colname="col2"> <p>列出因語法或格式要求不符而無法處理的記錄數。 請參閱 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 傳入資料檔案內容： 語法、變數和範例</a> ，以取得如何格式化資料的資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>無效的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正確的 <span class="keyword"> Audience Manager使用者ID</span> (UUID)數目。 通常，這表示ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">不符合預期的38位數格式。 </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">包含字母字元。 ID只能是數字。 </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>設備ID無效</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正確的全域裝置ID的數目。 請參 <a href="../reference/ids-in-aam.md">閱Audience Manager和</a><a href="../features/global-data-sources.md"></a> Global Data Sources中的ID索引，以取得裝置ID應如何格式化以及您應根據裝置類型使用哪些全域資料來源的詳細資訊。</p>
  <p>報表的錯誤取樣區段包含無效裝置ID的詳細資訊，例如：</p>
   <ul>
    <li>與無效設備ID對應的資料源ID;</li>
    <li>無效的設備ID;</li>
    <li>根據資料來源，預期的裝置ID類型。</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>無相符的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>這些是已登入的ID <span class="keyword"> Audience Manager</span> ，無法與現有ID相符。 已登入的ID在 <span class="keyword"> Audience Manager</span> 尚未執行ID同步，或者即使在同步後仍無法符合ID時，可能會有此狀態。 </p> <p>在無法匹配的行動ID的情況下， <span class="keyword"> Audience Manager</span> 將： </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">繼續儲存並嘗試同步此ID。 </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">如果ID無法同 <span class="wintitle"> 步</span> ，請將它記錄為報表中的儲存記錄。 </li> 
    </ul> <p>如果您已登入的檔案包含行動ID，則可比其他量度輕一點處理這些數字。 它們不會影響後續檔案的成功和比對率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未實現特徵</b> </p> </td> 
   <td colname="col2"> <p>列出 <span class="keyword"></span> Audience Manager不能與已登入特徵相符的特徵。 這可能是以下原因造成的： </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">傳入資料檔案中的特徵格式不正確。 有關如何格式化資料檔案的資訊，請參閱傳入 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 資料檔案內容： 語法、變數和範例</a>。 </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">尚未在 <span class="keyword"> Audience Manager中定義的特徵</span>。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>成功百分比</b> </p> </td> 
   <td colname="col2"> <p>您檔案中成功儲存的記錄百分比。 成功百分比=已處理的記錄／檔案中的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>收到的記錄</b> </p> </td> 
   <td colname="col2"> <p>收到的記錄總數。 在大多數情況下，此數字應符合傳入資料檔案中記錄（行）的總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>儲存記錄</b> </p> </td> 
   <td colname="col2"> <p>成功儲存的記錄數。 由於檔案格式錯誤，Audience Manager可能無法儲存收到的某些記 <span class="keyword"> 錄</span>。 儲存的記錄數可以小於接收的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>實現的特徵總數</b> </p> </td> 
   <td colname="col2"> <p>儲存在 <span class="keyword"> Audience Manager平台之所有傳入檔案中之所有使用者的特徵數</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未使用信號總數</b> </p> </td> 
   <td colname="col2"> <p>報告中接收的未使用信號總數。 此總計基於成功儲存的記錄總數。 </p> <p>如需詳 <a href="../reporting/dynamic-reports/unused-signals.md"> 細資訊，請參閱未使用的訊號報表</a> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>
