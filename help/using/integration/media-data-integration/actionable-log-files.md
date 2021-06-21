---
description: 可操作的記錄檔可讓您從廣告伺服器記錄檔擷取媒體訊號，以在Audience Manager中建立特徵。 將來自廣告伺服器的曝光數、點按次數和轉換擷取為特徵，而不需附加像素。
keywords: 可操作日誌，alf, ALF
seo-description: 可操作的記錄檔可讓您從廣告伺服器記錄檔擷取媒體訊號，以在Audience Manager中建立特徵。 將來自廣告伺服器的曝光數、點按次數和轉換擷取為特徵，而不需附加像素。
seo-title: 可操作的記錄檔
solution: Audience Manager
title: 可操作的記錄檔
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: 記錄檔
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1611'
ht-degree: 3%

---

# 可操作的記錄檔 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 可讓您從廣告伺服器記錄檔擷取媒體資料，並使用資料建立Audience Manager中的特徵。擷取來自廣告伺服器的曝光數、點按次數和轉換數作為特徵，而無須附加[像素](../../integration/media-data-integration/impression-data-pixels.md)。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)在本檔案中指出程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../reference/code-style-elements.md)。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 簡化從廣告伺服器擷取曝光數、點按和轉換的方式。使用此資訊進行使用者細分，而無須手動像素媒體將促銷活動屬性傳送至[!DNL Audience Manager]。

## 快速入門 {#getting-started}

若要開始使用[!UICONTROL Actionable Log Files]，您需要將記錄檔資料匯入[!DNL Audience Manager]。 下列連結將協助您開始使用：

* 若需[!UICONTROL Google Campaign Manager]記錄檔，請參閱將Google Campaign Manager資料檔案匯入至Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *和*&#x200B;連絡您的[!DNL Audience Manager]顧問。[
* 若需[!UICONTROL Google Ad Manager]（原稱為Google DFP）記錄檔，請參閱「將Google Ad Manager資料檔案匯入至Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *及*」連絡您的[!DNL Audience Manager]顧問。[
* 如需其他廣告伺服器記錄檔，請參閱[資料和中繼資料檔案](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *和*&#x200B;聯絡您的[!DNL Audience Manager]顧問。

如果您已將日誌資料導入[!DNL Audience Manager]，請咨詢[!DNL Audience Manager]顧問或[客戶服務](https://helpx.adobe.com/tw/contact/enterprise-support.ec.html)為您啟用[!UICONTROL Actionable Log Files]。

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## 使用可操作的日誌檔案{#working-with-actionable-log-files}

若使用[!UICONTROL Actionable Log Files]，來自廣告伺服器記錄檔的資訊會以[!DNL Audience Manager]擷取，其方式與您從即時網站互動擷取資料的方式相同。 [!DNL Audience Manager] 連線至您的廣告伺服器記錄儲存、剖析記錄檔中的資訊，並將記錄檔資料當成可操作的訊號傳送至我們的 [資料收集伺服器](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍需設定規則型特徵來擷取可操作的訊號。 請參閱如何在[Audience Manager使用者介面](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)中，或使用我們的[大量管理工具](../../reference/bulk-management-tools/bulk-create.md)來設定規則型特徵。 向下捲動至[可操作訊號](../../integration/media-data-integration/actionable-log-files.md#actionable-signals)區段，以取得可在規則型特徵中使用之所有索引鍵的清單。

>[!IMPORTANT]
>
>建議您實作[!UICONTROL Actionable Log Files] *，而非* [像素呼叫](../../integration/media-data-integration/impression-data-pixels.md)。 我們不鼓勵使用這兩種選項，因為這會增加特徵的頻率計數。

## 可操作的訊號{#actionable-signals}

訊號是[!DNL Audience Manager]中[最小資料單位](../../reference/signal-trait-segment.md)。 [!UICONTROL Actionable Log Files] 可讓您從廣告伺服器記錄檔中，將廣告商、業務單位、創意和促銷活動值擷取到曝光事件、點擊事件和轉換事件中，做為訊號。

請記住，若要將此資訊用於建立和劃分受眾，您必須自行設定規則型特徵。

### 來自Google促銷活動管理員記錄檔的可操作訊號{#dcm-logs-signals}

下表列出[!DNL Google Campaign Manager]日誌檔案中可操作的信號：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 記錄檔中的標題名稱 </th> 
   <th colname="col2" class="entry"> 訊號 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
   <th colname="col4" class="entry"> 範例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>僅適用於轉換事件。 </p> <p>代表Google促銷活動管理員中轉換活動的數值ID。 此欄位對應至Google促銷活動管理員的活動ID。 </p> <p> <p>提示：您可以從Google促銷活動管理員擷取多個或特定的轉換活動。 從Google促銷活動管理員為每個轉換活動使用<code> d_conversion = activity ID</code>建立特徵。 </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>僅適用於轉換事件。 </p> <p>此欄位對應至Google促銷活動管理員中的轉換ID。 指出從Google促銷活動管理員使用者轉換前的活動。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> 用於點按後轉換。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 貼文印象轉換。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> 不符合的轉換。轉換無法與先前的活動相符。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">曝光、點按或轉換事件的UTC日期和時間。 自1970-01-01 00:00:00 UTC以來以微秒錶示。</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>廣告商資料來源的整合代碼。 請注意，這與Audience Manager資料來源無關。</p> <p>此欄位會對應至Google促銷活動管理員中的廣告商群組ID。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>業務單位ID。 此欄位會對應至Google促銷活動管理員中的廣告商ID。 </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Google促銷活動管理員提供的促銷活動ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Google促銷活動管理員提供的創作ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 銷售額以美元計，為–6。 用1.000.000乘以1美元。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指出事件類型。 Audience Manager會從Google促銷活動管理員記錄檔名稱中讀取事件類型，並將其轉換為可操作的訊號。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 以取得曝光數。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按一下。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> ，以轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>您用來擷取Google促銷活動管理員資料的資料來源ID。 請參閱<a href="../../features/manage-datasources.md#create-data-source">如何建立資料來源</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表格中描述的訊號會像即時`HTTP`呼叫一樣在[!DNL Audience Manager]中擷取。 以下範例呼叫包含[!DNL Google Campaign Manager]轉換事件的相關資訊。 呼叫不一定必須包含範例呼叫中的&#x200B;*all*&#x200B;訊號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

對於200萬行的[!DNL Google Campaign Manager]日誌檔案，從可操作信號建立的任何特徵都會在處理日誌後大約一小時內實現。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Google Campaign Manager]記錄檔中提供的事件時間戳記將接受並傳遞至[!UICONTROL Data Collection Servers]。
>
>* 如果[!DNL Google Campaign Manager]記錄檔中的資料列沒有時間戳記，我們會使用`HTTP`呼叫的時間作為事件時間戳記。
>* 如果[!DNL Google Campaign Manager]日誌檔案中的資料行包含格式錯誤的時間戳，則忽略整行。


<br> 

### 來自[!DNL Google Ad Manager]記錄{#ad-manager-logs-signals}的可操作訊號

下表列出[!DNL Google Ad Manager]日誌檔案中可操作的信號：


| 記錄檔中的標題名稱 | 訊號 | 說明 |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | 傳遞的廣告管理員條列項目的數值ID |
| `OrderId` | `d_orderid` | 包含已傳送條列項目和創意素材的廣告管理員訂單數值ID。 |
| `CreativeId` | `d_creative` | 傳遞的廣告管理員創意內容數值ID。 |
| `-` | `d_event` | 指出事件類型。 Audience Manager會從廣告管理員記錄檔名稱中讀取事件類型，並將其轉換為可操作的訊號。 接受的值為：<br> <ul><li>d_event = imp以表示曝光數。</li><li>d_event =點按次數。</li><li>d_event =轉換和活動的conv。</li></ul> |
| `-` | `d_src` | 您用來擷取廣告管理員資料的資料來源ID。 請參閱[如何建立資料來源](/help/using/features/manage-datasources.md)。 |

表格中描述的訊號會以Audience Manager擷取，如即時HTTP呼叫。 以下範例呼叫包含來自Google廣告管理員之轉換事件的資訊。 呼叫不一定必須將所有訊號包含在範例呼叫中。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>[!DNL Google Ad Manager]記錄檔中提供的事件時間戳記將接受並傳遞至[!UICONTROL Data Collection Servers]。
>
>* 如果[!DNL Google Ad Manager]記錄檔中的資料列沒有時間戳記，我們會使用`HTTP`呼叫的時間作為事件時間戳記。
>* 如果[!DNL Google Ad Manager]日誌檔案中的資料行包含格式錯誤的時間戳，則忽略整行。


<br> 

### 來自一般廣告伺服器記錄檔的可操作訊號{#generic-logs-signals}

首先，您必須將廣告伺服器記錄放入我們的Amazon S3儲存貯體。 若要完成此操作，請閱讀[資料檔案以取得Audience Optimization報表和可操作的記錄檔](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *和*&#x200B;聯絡您的[!DNL Audience Manager]顧問。 下表列出一般記錄檔中可操作的訊號：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 記錄檔中的標題名稱 </th> 
   <th colname="col2" class="entry"> 訊號 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
   <th colname="col4" class="entry"> 範例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>指出轉換是否相符。 選項包括: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> 曝光數 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> 按一下 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> 未歸因或未知 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> 曝光、點按或轉換事件的UTC日期和時間。 使用<code>yyyy-MM-dd HH:mm:ss</code>格式。 </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>廣告商資料來源的整合代碼。 請注意，此欄位與<a href="../../features/datasources-list-and-settings.md">Audience Manager資料源無關。</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>業務單位ID。  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>記錄檔中的促銷活動ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>記錄檔中的創作ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 購買或其他轉換金額。 資料類型：漂浮。 </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指出事件類型。 Audience Manager會從記錄檔名稱中讀取事件類型，並將其轉換為可操作的訊號。 請參閱<a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">日誌檔案命名約定</a>。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 以取得曝光數。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按一下。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> ，以轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用於捕獲日誌資料的資料源的ID。 請參閱<a href="../../features/manage-datasources.md#create-data-source">如何建立資料來源</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表格中描述的訊號會像即時`HTTP`呼叫一樣在[!DNL Audience Manager]中擷取。 呼叫不一定必須包含範例呼叫中的&#x200B;*all*&#x200B;訊號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## 在Audience Manager使用者介面{#actionable-signals-in-ui}中使用可操作的訊號

您可以在[訊號搜尋](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md)介面中檢視傳入的可操作訊號。

前往&#x200B;**受眾資料**(1)> **訊號**(2)> **搜尋**(3)，並選取&#x200B;**可操作的記錄檔**(4)篩選器。

![UI中可操作的訊號](/help/using/integration/assets/alf-in-signals.png)

若要使用可操作訊號建立規則型特徵，請選取&#x200B;**可操作記錄檔**(1)，選取您要用作特徵規則的可操作訊號(2)，然後按&#x200B;**從選取訊號建立特徵**(3)。

![從訊號建立特徵](/help/using/integration/assets/alf-create-trait.png)


## 使用個案 {#use-cases}

實作[!UICONTROL Actionable Log Files]的其中一項優點，是可將[造訪間隔和頻率](../../features/segments/recency-and-frequency.md)控制套用至包含可操作訊號之任何[規則型特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)的選項。 舉例來說，這可讓您以頻率上限在媒體行銷活動中，顯示使用者特定創意內容的次數。 請閱讀[即時跨裝置隱藏](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)以了解如何執行此操作。 其他使用案例包括：

### 重新定位使用者

重新定位看過創意123但未點按或轉換的使用者，並顯示創意456。 執行動作:

1. 建立特徵以擷取看到創意內容的使用者。 假設您將特徵命名為[!DNL Creative Trait 123]。 使用特徵規則：

   `d_creative == 123 AND d_event == imp`

2. 建立特徵以擷取點按或轉換的使用者。 假設您將此名稱命名為[!DNL Click and Converter]。 使用特徵規則：

   `d_event == click OR d_event=conv`

3. 建立區段以填入看到創意123但未點按或轉換的使用者。 將其命名為[!DNL Retarget Users]，然後使用區段規則：

   `Creative Trait 123 AND NOT Click and Converter`

4. 將區段[!DNL Retarget Users]對應至目標，並將目標使用者對應至創意內容456的目標。

### 在「Audience Optimization報表」或「Audience Lab」中使用Google Campaign Manager Floodlight活動

[可鎖定](https://support.google.com/dcm/partner/answer/4293719?hl=en) Floodlight的廣告商，以追蹤使用者轉換。透過[!UICONTROL Actionable Log Files]，您可以在[Audience Optimization報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)或[Audience Lab](../../features/audience-lab/audience-lab.md)中追蹤[!DNL Google Campaign Manager]轉換：

1. 建立特徵並使用下列特徵規則來從廣告伺服器記錄檔擷取轉換：

   `d_event == conv AND d_conversion == 123`

   在Audience Manager[!UICONTROL UI]中建立特徵時，請選取[!UICONTROL Conversion]作為[!UICONTROL Event Type]。

2. 建立特徵後，系統會開始在[!UICONTROL Audience Optimization Reports]和[!UICONTROL Audience Lab]中報告轉換。

>[!MORELIKETHIS]
>
>* [將Google促銷活動管理員資料檔案匯入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
* [受眾最佳化報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

