---
description: 「登錄狀態報表」會檢查傳入資料來源檔案中處理記錄的成功率和失敗率。此報表會顯示互動式長條圖中的資料，並提供表格形式的摘要度量。該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在「Analytics>上線狀態報表」中找到此報表。當您建立傳入的資料來源時，也可以使用此報表。
seo-description: 「登錄狀態報表」會檢查傳入資料來源檔案中處理記錄的成功率和失敗率。此報表會顯示互動式長條圖中的資料，並提供表格形式的摘要度量。該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在「Analytics>上線狀態報表」中找到此報表。當您建立傳入的資料來源時，也可以使用此報表。
seo-title: 入門狀態報表關於
solution: Audience Manager
title: 入門狀態報表關於
uuid: 6ca8a90a-436b-4fce-adf1-48f3 b96 b3 ed
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Onboarding Status Report{#onboarding-status-report-about}

「登錄狀態報表」會檢查傳入資料來源檔案中處理記錄的成功率和失敗率。此報表會顯示互動式長條圖中的資料，並提供表格形式的摘要度量。該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在「Analytics&gt;上線狀態報表」中找到此報表。當您建立傳入的資料來源時，也可以使用此報表。

>[!NOTE]
>
>只有具有管理員權限的使用者才能在Audience Manager使用者介面中看到此報表。您可以將電子郵件新增至報表，讓非管理員使用者收到上傳的傳入檔案狀態通知。See [Receive E-mail Notifications](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Onboarding Status Report: About {#onboarding-status-about}

[!UICONTROL Onboarding Status Report] 在傳入資料來源檔案中處理記錄的成功和失敗率。此報表會顯示互動式長條圖中的資料，並提供表格形式的摘要度量。該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。You can find this report in **[!UICONTROL Analytics > Onboarding Status Report]**. 當您建立傳入的資料來源時，也可以使用此報表。

## Error Reporting and Error Sampling {#error-reporting-sampling}

Error reporting and error sampling are 2 separate features of the [!UICONTROL Onboarding Status] report.

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
   <td colname="col2"> <p>錯誤報告會顯示傳入資料來源中處理之記錄數的成功和失敗率。它會在互動式堆疊列圖表中傳回資料，並以圖表下方表格中的摘要度量傳回資料。 </p> <p>錯誤報告是自動的。它會持續針對所有傳入的資料來源執行。它會根據預設時間間隔或您使用日曆Widget設定的自訂時間間隔傳回資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>錯誤取樣</b> </p> </td>
   <td colname="col2"> <p>錯誤取樣會解析資料檔案的內容，並傳回每個錯誤類型的10個最常見錯誤。傳入資料檔案中的錯誤會防止您處理個別的記錄。使用此報告做為疑難排解工具，以協助減少檔案錯誤次數並提高處理率。 </p> <p>您必須手動啓動錯誤取樣。它會從啓動當日執行14天，然後自行關閉。您可以在14天間隔到期後重新啓動錯誤取樣。<a href="../features/manage-datasources.md#create-data-source"> 當您建立傳入資料來源</a> ，或從現有傳入資料來源的「 <b><span class="uicontrol"></span></b><span class="wintitle"> 資料來源設定</span> 」區段核取「錯誤取樣」核取方塊時，會啓動錯誤取樣。 </p> <p>錯誤取樣是一項繁重的處理程序。因此，它只會傳回每個錯誤類別的前10個錯誤。它不會傳回傳入資料來源中包含的每個錯誤。這些錯誤是潛在較大群組發生類似錯誤的代表樣本。檢視您的整個檔案以瞭解此報告標幟的錯誤類型、重新格式化檔案，然後再次傳送。 </p> <p>See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for more information about how to properly format an data file for an inbound data source. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Error Report Bar Chart {#error-report-bar-chart}

此錯誤報告會繪制堆疊列圖表中記錄處理的成功和失敗率，如以下範例所示。圖表是互動式的。按一下列會顯示該日期下圖表中的摘要量度。

![](assets/stacked-graph.png)

## Error Report Tables {#error-report-tables}

錯誤報告會在長條圖下方顯示表格資料。表格顯示成功和失敗率以及總計和百分比。

**成功和失敗記錄**

此預設檢視會顯示報表中記錄總計的頻率計數，並包含錯誤類型的錯誤劃分。

![](assets/success-failure.png)

**總計與百分比**

Click **[!UICONTROL Totals & Percentages]** to see what % of your files were processed successfully.

![](assets/totals-percentages.png)

## Error Sampling Report for 14 Days {#error-reporting-14-days}

發生錯誤取樣時，報表會顯示每個錯誤類型的前10大錯誤。按一下報表頂端的錯誤類型按鈕，以查看每組取樣資料。

>[!NOTE]
>
>報表不會反白標示此目前版本的記錄錯誤。To find and fix file errors, you should review the results and compare those to the specifications in the [Inbound Data File Contents](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) documentation.

![](assets/error-samples.png)

## Receive E-mail Notifications {#receive-email-notifications}

您可以新增要收到已上載傳入檔案狀態通知的收件者電子郵件地址。請注意，您可以針對不同的資料來源選取不同的收件者。

![](assets/mail-notifications.png)

## Create an Onboarding Status Report {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] returns the number records in a data source were processed successfully and how many failed. Follow these steps to generate a [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. **[!UICONTROL Analytics > Onboarding Status Report]** 前往。搜尋資料來源或從清單中選擇一個資料來源。

2. 選取日期範圍。選項包括:

   * 固定報表間隔集。
   * 可讓您建立自訂日期範圍的日曆Widget。

3. Click **[!UICONTROL OK]**.

## Onboarding Status Report Terms and Definitions {#report-terms-conditions}

此報表中使用之標籤和詞語的參考指南。

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
   <td colname="col2"> <p>Lists files that <span class="keyword"> Audience Manager</span> received and processed from you selected inbound data source. </p> <p>如果檔案名稱格式錯誤，檔案處理將會失敗。File name requirements vary depending on how you send this data to <span class="keyword"> Audience Manager</span>. Delivery methods include <span class="keyword"> Amazon S3</span> and FTP. 如需如何命名檔案的指示，請參閱： </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 傳入資料檔案的 Amazon S3 名稱要求 </a> </li> 
      <li id="li_9590241AEC0C482D91C64DB760B32B0D"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md"> 傳入資料檔案的 FTP 名稱要求 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>格式錯誤</b> </p> </td> 
   <td colname="col2"> <p>列出處理失敗的記錄數，因為它們不符合語法或格式需求。See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for information on how to format your data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>無效的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>Lists the number of improperly formatted <span class="keyword"> Audience Manager</span> user IDs (UUID). 通常會指出ID： </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">不符合預期的38位數格式。 </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">包含字母字元。ID只能是數字。 </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>無效的裝置ID</b> </p> </td> 
   <td colname="col2"> <p>列出格式錯誤的全域裝置ID數。See <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a> and <a href="../features/global-data-sources.md">Global Data Sources</a>  for details on how device IDs should be formatted and what global data sources you should use, based on the device type.</p>
  <p>報表的錯誤取樣區段包含有關無效裝置ID的詳細資訊，例如：</p>
   <ul>
    <li>與無效裝置ID相對應的資料來源ID；</li>
    <li>無效的裝置ID；</li>
    <li>根據資料來源的預期裝置ID類型。</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>無相符AAM ID</b> </p> </td> 
   <td colname="col2"> <p>These are onboarded IDs <span class="keyword"> Audience Manager</span> cannot match to an existing ID. <span class="keyword"> 當Audience Manager</span> 尚未執行ID同步或即使同步後仍然無法比對ID時，已登錄ID也可以具有此狀態。 </p> <p>In the case of unmatched mobile IDs, <span class="keyword"> Audience Manager</span> will: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">繼續儲存並嘗試同步此ID。 </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Record it as a <span class="wintitle"> Stored Record</span> in the report if the ID cannot be synched. </li> 
    </ul> <p>如果您的已登錄檔案包含行動ID，則您可以比其他度量稍微稍微地處理這些數字。它們不會影響後續檔案的成功和匹配率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未實現特徵</b> </p> </td> 
   <td colname="col2"> <p>Lists traits that <span class="keyword"> Audience Manager</span> cannot match to an onboarded trait. 這可能是因為： </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">傳入資料檔案中的格式不正確。For on how to format your data file, see <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Traits that have not yet been defined in <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>成功百分比</b> </p> </td> 
   <td colname="col2"> <p>成功儲存檔案中記錄的百分比。百分比成功=已處理的記錄/檔案中的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>收到的記錄</b> </p> </td> 
   <td colname="col2"> <p>收到的記錄總數。在大多數情況下，此數字應符合傳入資料檔案中的記錄總數(線條)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>儲存的記錄</b> </p> </td> 
   <td colname="col2"> <p>成功儲存的記錄數。Because of file format errors, some of the records received may not be stored by <span class="keyword"> Audience Manager</span>. 儲存的記錄數可能少於收到的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>總實現特性</b> </p> </td> 
   <td colname="col2"> <p>The number of traits for all users across all inbound files that get stored in the <span class="keyword"> Audience Manager</span> platform. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未使用的總訊號</b> </p> </td> 
   <td colname="col2"> <p>報表中未使用的未使用訊號總數。此總計是根據成功儲存的記錄總數而定。 </p> <p>See <a href="../reporting/dynamic-reports/unused-signals.md"> Unused Signals Report</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>
