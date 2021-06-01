---
description: 輔導狀態報表會檢查成敗比率，以處理傳入資料來源檔案中的記錄。 此報表會以互動式長條圖顯示資料，並以表格形式提供摘要量度。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在「Analytics >入門狀態報表」中找到此報表。 建立入站資料來源時，也可使用此報表。
seo-description: 輔導狀態報表會檢查成敗比率，以處理傳入資料來源檔案中的記錄。 此報表會以互動式長條圖顯示資料，並以表格形式提供摘要量度。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在「Analytics >入門狀態報表」中找到此報表。 建立入站資料來源時，也可使用此報表。
seo-title: 上線狀態報表
solution: Audience Manager
title: 上線狀態報表
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: 傳入和傳出報表
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1502'
ht-degree: 7%

---

# 上線狀態報表{#onboarding-status-report-about}

輔導狀態報表會檢查成敗比率，以處理傳入資料來源檔案中的記錄。 此報表會以互動式長條圖顯示資料，並以表格形式提供摘要量度。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在「Analytics >入門狀態報表」中找到此報表。 建立入站資料來源時，也可使用此報表。

>[!NOTE]
>
>只有具有管理員權限的使用者才能在Audience Manager使用者介面中看到此報表。 您可以將非管理員使用者的電子郵件新增至報表，以通知他們已上傳的傳入檔案狀態。 請參閱[接收電子郵件通知](/help/using/reporting/onboarding-status-report.md#receive-email-notifications)。

## 上線狀態報表：關於{#onboarding-status-about}

[!UICONTROL Onboarding Status Report]會檢查成敗比率，以處理傳入資料來源檔案中的記錄。 此報表會以互動式長條圖顯示資料，並以表格形式提供摘要量度。 該功能還包括可依固定時間間隔抽樣檢查檔案的選項，且會依每個錯誤類型顯示最常見的錯誤。您可以在&#x200B;**[!UICONTROL Analytics > Onboarding Status Report]**&#x200B;中找到此報告。 建立入站資料來源時，也可使用此報表。

## 錯誤報告和錯誤抽樣{#error-reporting-sampling}

錯誤報告和錯誤取樣是[!UICONTROL Onboarding Status]報告的2個獨立功能。

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
   <td colname="col2"> <p>錯誤報表會顯示傳入資料來源中處理的記錄數的成功率和失敗率。 它會以互動式堆疊長條圖傳回資料，並在圖表下方的表格中以摘要量度的形式傳回資料。 </p> <p>錯誤報告是自動的。 它會持續對您所有傳入資料來源執行。 它會根據預設時間間隔範圍或您使用日曆介面工具集設定的自訂時間間隔，傳回資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>錯誤取樣</b> </p> </td>
   <td colname="col2"> <p>錯誤取樣會分析資料檔案的內容，並針對每個錯誤類型傳回10個最常見的錯誤。 傳入資料檔案中的錯誤會使個別記錄無法處理。 將此報表用作疑難排解工具，有助於減少檔案錯誤數量並改善處理率。 </p> <p>必須手動激活錯誤採樣。 從啟動之日起，它會持續14天，然後關閉它。 在14天的間隔過期後，您可以重新開啟錯誤取樣。 當<a href="../features/manage-datasources.md#create-data-source">建立入站資料源</a>時，或從現有入站資料源的<span class="wintitle">資料源設定</span>部分勾選<b><span class="uicontrol">錯誤取樣</span></b>複選框，激活錯誤取樣。 </p> <p>錯誤採樣是一個計算量很大的過程。 因此，它只會針對每個錯誤類別傳回前10個錯誤。 它的設計目的並非要傳回傳入資料來源中包含的所有錯誤。 這些錯誤是一組可能較大的類似錯誤的代表性範例。 檢閱整個檔案，了解此報告旗標的錯誤類型、重新格式化檔案，然後再次傳入。 </p> <p>請參閱<a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">傳入資料檔案內容：語法、變數和範例</a>，以取得如何為傳入資料來源正確設定資料檔案格式的詳細資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 錯誤報表長條圖{#error-report-bar-chart}

錯誤報表會以圖表形式呈現堆疊長條圖中記錄處理的成功與失敗率，如下列範例所示。 圖表為互動式。 按一下長條圖時，圖表下方的表格中會顯示當天的摘要量度。

![](assets/stacked-graph.png)

## 錯誤報表表{#error-report-tables}

錯誤報表會在長條圖下方顯示表格資料。 表格顯示成功和失敗率，以及總計和百分比。

**成功和失敗的記錄**

此預設檢視會顯示報表中記錄總數的頻率計數，並包含依錯誤類型劃分的錯誤。

![](assets/success-failure.png)

**總計和百分比**

按一下&#x200B;**[!UICONTROL Totals & Percentages]**&#x200B;查看已成功處理的檔案百分比。

![](assets/totals-percentages.png)

## 14天的採樣報告出錯{#error-reporting-14-days}

當錯誤取樣作用中時，報表會顯示每個錯誤類型的前10個錯誤。 按一下報表頂端的錯誤類型按鈕，查看每一組取樣的資料。

>[!NOTE]
>
>此報表不會反白標示此最新版本的記錄錯誤。 若要尋找並修正檔案錯誤，您應檢閱結果，並將結果與[傳入資料檔案內容](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)檔案中的規格進行比較。

![](assets/error-samples.png)

## 接收電子郵件通知{#receive-email-notifications}

您可以新增收件者的電子郵件地址，以通知他們上傳的傳入檔案的狀態。 請注意，您可以為不同的資料來源選取不同的收件者。

![](assets/mail-notifications.png)

## 建立輔導狀態報表{#create-onboard-status-report}

[!UICONTROL Sample Error Report]返回資料源中的數字記錄已成功處理，以及失敗的數量。 請依照下列步驟產生[!UICONTROL Sample Error Report]。

<!-- 

create-onboarding-status-report.xml

 -->


1. 前往&#x200B;**[!UICONTROL Analytics > Onboarding Status Report]**。 搜尋資料來源或從清單中選擇一個。

2. 選取日期範圍。 選項包括:

   * 一組固定的報告間隔。
   * 可讓您建立自訂日期範圍的日曆小工具。

3. 按一下 **[!UICONTROL OK]**.

## 上線狀態報表詞語和定義{#report-terms-conditions}

此報告中所用標籤和術語的參考指南。

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
   <td colname="col2"> <p>列出從您選擇的入站資料源接收並處理<span class="keyword">Audience Manager</span>的檔案。 </p> <p>如果檔案名的格式不正確，則檔案處理會失敗。 檔案名要求會因您將此資料傳送至<span class="keyword">Audience Manager</span>的方式而異。 傳送方法包括<span class="keyword"> Amazon S3</span>和FTP。 有關如何為檔案命名的說明，請參閱： </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 傳入資料檔案的 Amazon S3 名稱要求 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>格式錯誤</b> </p> </td> 
   <td colname="col2"> <p>列出因語法或格式要求不匹配而無法處理的記錄數。 請參閱<a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">傳入資料檔案內容：語法、變數和範例</a>，以取得如何設定資料格式的資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>無效的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正確的<span class="keyword">Audience Manager</span>使用者ID(UUID)數。 這通常表示ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">不符合預期的38位數格式。 </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">包含字母字元。 ID應僅為數字。 </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>設備ID無效</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正確的全局設備ID的數量。 請參閱<a href="../reference/ids-in-aam.md">Audience Manager</a>和<a href="../features/global-data-sources.md">全域資料來源</a>中的ID索引，以了解裝置ID的格式設定方式，以及您應根據裝置類型使用的全域資料來源。</p>
  <p>報表的錯誤取樣區段包含無效裝置ID的詳細資訊，例如：</p>
   <ul>
    <li>與無效設備ID對應的資料源ID;</li>
    <li>設備ID無效；</li>
    <li>根據資料來源的預期裝置ID類型。</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>沒有相符的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>這些是已上線的ID <span class="keyword">Audience Manager</span>無法與現有ID相符。 當<span class="keyword">Audience Manager</span>尚未執行ID同步時，已上線的ID可能具有此狀態，或者即使在同步後，它仍不能與ID匹配。 </p> <p>若是不相符的行動ID,<span class="keyword">Audience Manager</span>將： </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">繼續儲存並嘗試同步此ID。 </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">如果無法同步ID，請在報表中將其記錄為<span class="wintitle">儲存的記錄</span>。 </li> 
    </ul> <p>如果您已上線的檔案包含行動ID，則您可以比其他量度更輕鬆地處理這些數字。 它們不會影響後續檔案的成功率和匹配率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未實現特徵</b> </p> </td> 
   <td colname="col2"> <p>列出<span class="keyword">Audience Manager</span>無法與已上線特徵相符的特徵。 這可能是以下原因造成的： </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">傳入資料檔案中的特徵格式不正確。 有關如何格式化資料檔案的資訊，請參閱<a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">傳入資料檔案內容：語法、變數和範例</a>。 </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">尚未在<span class="keyword">Audience Manager</span>中定義的特徵。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>成功百分比</b> </p> </td> 
   <td colname="col2"> <p>檔案中已成功儲存的記錄百分比。 成功百分比=已處理的記錄數/檔案中的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>已接收記錄</b> </p> </td> 
   <td colname="col2"> <p>接收的記錄總數。 在大多數情況下，此數目應符合傳入資料檔案中的記錄總數（行）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>儲存的記錄</b> </p> </td> 
   <td colname="col2"> <p>已成功儲存的記錄數。 由於檔案格式錯誤，所收到的某些記錄可能不會由<span class="keyword">Audience Manager</span>儲存。 儲存的記錄數可以小於接收的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>已實現特徵總數</b> </p> </td> 
   <td colname="col2"> <p>儲存在<span class="keyword">Audience Manager</span>平台中之所有傳入檔案的所有使用者的特徵數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未使用的訊號總數</b> </p> </td> 
   <td colname="col2"> <p>報表中收到的未使用訊號總數。 此總計以成功儲存的記錄總數為基礎。 </p> <p>如需詳細資訊，請參閱<a href="../reporting/dynamic-reports/unused-signals.md">未使用的訊號報表</a> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>
