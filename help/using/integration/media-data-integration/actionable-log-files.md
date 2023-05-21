---
description: 可操作的日誌檔案允許您從ad伺服器日誌檔案捕獲媒體信號，以在Audience Manager中建立特徵。 捕獲廣告伺服器中的印象、點擊和轉換，作為特徵，而無需添加像素。
keywords: 可操作日誌， alf, alf
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: 可操作的記錄檔
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 3%

---

# 可操作的記錄檔 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 允許您從ad伺服器日誌檔案中捕獲媒體資料，並使用這些資料在Audience Manager中建立特徵。 捕獲廣告伺服器中的印象、點擊和轉換為特徵，而無需追加 [像素](../../integration/media-data-integration/impression-data-pixels.md)。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)指明代碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../reference/code-style-elements.md)。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 簡化從廣告伺服器捕獲印象、點擊和轉換的方式。 使用此資訊進行用戶分段，而無需手動對媒體進行像素化以將市場活動屬性發送到 [!DNL Audience Manager]。

## 入門 {#getting-started}

開始 [!UICONTROL Actionable Log Files]，您需要將日誌資料導入 [!DNL Audience Manager]。 以下連結將幫助您入門：

* 對於 [!UICONTROL Google Campaign Manager] 日誌，請參閱 [將Google市場活動經理資料檔案導入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *和* 聯繫 [!DNL Audience Manager] 顧問。
* 對於 [!UICONTROL Google Ad Manager] (原GoogleDFP)日誌，請參閱 [將GoogleAd Manager資料檔案導入Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *和* 聯繫 [!DNL Audience Manager] 顧問。
* 有關其他廣告伺服器日誌，請參見 [資料和元資料檔案](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *和* 聯繫 [!DNL Audience Manager] 顧問。

如果已將日誌資料導入 [!DNL Audience Manager]請 [!DNL Audience Manager] 顧問或 [客戶服務](https://helpx.adobe.com/tw/contact/enterprise-support.ec.html) 啟用 [!UICONTROL Actionable Log Files] 為你。

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## 使用可操作的日誌檔案 {#working-with-actionable-log-files}

與 [!UICONTROL Actionable Log Files]，將捕獲來自ad伺服器日誌的資訊 [!DNL Audience Manager] 就像從即時網站交互中獲取資料一樣。 [!DNL Audience Manager] 連接到您的ad伺服器日誌儲存，解析日誌中的資訊，並將日誌資料作為可操作信號發送給我們 [資料收集伺服器](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍然需要設定基於規則的特性來捕獲可操作的信號。 瞭解如何在 [Audience Manager用戶介面](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 或使用 [批量管理工具](../../reference/bulk-management-tools/bulk-create.md)。 向下滾動到 [可操作的信號](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) 的子目錄。

>[!IMPORTANT]
>
>我們建議實施 [!UICONTROL Actionable Log Files] *而不是*  [像素調用](../../integration/media-data-integration/impression-data-pixels.md)。 我們不鼓勵使用這兩種選擇，因為這會導致性狀計數的頻率增加。

## 可操作的信號 {#actionable-signals}

信號是 [最小資料單位](../../reference/signal-trait-segment.md) 在 [!DNL Audience Manager]。 [!UICONTROL Actionable Log Files] 允許您從廣告伺服器日誌中捕獲廣告商、業務部門、創意和營銷活動在印象事件中的值，按一下事件和轉換事件作為信號。

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] 支援以下ad伺服器：
> <br>
>
> * [Google營銷經理](#dcm-logs-signals)
> * [Google廣告經理](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud，閃電俠，西茲梅克](#generic-logs-signals)


請記住，為了將這些資訊用於受眾的建立和細分，您需要自己設定基於規則的特性。

### 來自Google市場活動經理日誌的可操作信號 {#dcm-logs-signals}

該表列出了來自 [!DNL Google Campaign Manager] 日誌檔案：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日誌檔案中的頭名 </th> 
   <th colname="col2" class="entry"> 訊號 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
   <th colname="col4" class="entry"> 範例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>僅適用於轉換事件。 </p> <p>表示Google市場活動管理器中轉換活動的數字ID。 此欄位映射到Google市場活動經理的活動ID。 </p> <p> <p>提示：您可以從Google市場活動經理獲取多個或特定的轉換活動。 使用 <code> d_conversion = activity ID</code> 為來自Google市場活動經理的每個轉換活動。 </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>僅適用於轉換事件。 </p> <p>此欄位映射到Google市場活動經理中的轉換ID。 指示從Google市場活動經理轉換用戶之前的活動。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> 用於按一下後轉換。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 後印象轉換。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> 不匹配的轉換。 轉換無法與上一個活動匹配。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">UTC的印象、按一下或轉換事件的日期和時間。 自1970-01-01 00以來以微秒錶示:00:00 UTC。</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>廣告商資料源的整合代碼。 請注意，這與Audience Manager資料源無關。</p> <p>此欄位映射到來自Google市場活動經理的廣告商組ID。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>業務單位ID。 此欄位映射到來自Google市場活動經理的廣告商ID。 </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>由Google市場活動經理提供的市場活動ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>由Google市場活動經理提供的創意ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 以美元表示的銷售額，以–6的冪表示。 乘以1.000.000，看成美元金額。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指示事件類型。 Audience Manager從Google市場活動經理日誌檔案名中讀取事件類型，並將其轉換為可操作的信號。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 留個印象。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按鈕 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> 轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用於捕獲Google市場活動經理資料的資料源的ID。 請參閱 <a href="../../features/manage-datasources.md#create-data-source"> 如何建立資料源</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信號在 [!DNL Audience Manager] 像一個即時 `HTTP` 呼叫。 下面的示例調用包含來自的轉換事件的資訊 [!DNL Google Campaign Manager]。 呼叫不一定必須包括 *全部* 示例調用中的信號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

對於平均大小 [!DNL Google Campaign Manager] 日誌檔案包含200萬行，所有由可操作信號產生的特徵在我們處理日誌後大約一小時內被實現。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>中提供的事件時間戳 [!DNL Google Campaign Manager] 日誌將被保存並傳遞給 [!UICONTROL Data Collection Servers]。
>
>* 如果時間戳不適用於 [!DNL Google Campaign Manager] 日誌檔案，我們使用 `HTTP` 調用為事件時間戳。
>* 如果 [!DNL Google Campaign Manager] 日誌檔案包含格式錯誤的時間戳，我們將忽略整行。


<br> 

### 來自的可操作信號 [!DNL Google Ad Manager] 日誌 {#ad-manager-logs-signals}

該表列出了來自 [!DNL Google Ad Manager] 日誌檔案：


| 日誌檔案中的頭名 | 訊號 | 說明 |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | 已交付Ad Manager行項的數字ID |
| `OrderId` | `d_orderid` | 包含已交付行項和創意的Ad Manager訂單的數字ID。 |
| `CreativeId` | `d_creative` | 交付的Ad Manager創作檔案的數字ID。 |
| `-` | `d_event` | 指示事件類型。 Audience Manager從Ad Manager日誌檔案名中讀取事件類型，並將其轉換為可操作的信號。 接受的值為： <br> <ul><li>d_event = imp以獲取印象。</li><li>d_event =按一下以按一下。</li><li>d_event =轉換和活動的conv。</li></ul> |
| `-` | `d_src` | 用於捕獲Ad Manager資料的資料源的ID。 請參閱 [如何建立資料源](/help/using/features/manage-datasources.md)。 |

表中描述的信號以Audience Manager形式捕獲，如即時HTTP調用。 下面的示例調用包含有關來自Google廣告管理器的轉換事件的資訊。 調用不一定必須包括示例調用中的所有信號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>中提供的事件時間戳 [!DNL Google Ad Manager] 日誌將被保存並傳遞給 [!UICONTROL Data Collection Servers]。
>
>
>* 如果時間戳不適用於 [!DNL Google Ad Manager] 日誌檔案，我們使用 `HTTP` 調用為事件時間戳。
>* 如果 [!DNL Google Ad Manager] 日誌檔案包含格式錯誤的時間戳，我們將忽略整行。


<br> 

### 來自Adobe Advertising Cloud、Flashtalking和Sizmek的可操作信號，以及Sizmek廣告伺服器日誌 {#generic-logs-signals}

首先，您必須將您的廣告伺服器日誌存入我們的AmazonS3儲存桶。 要完成此任務，請閱讀 [用於Audience Optimization報告的資料檔案和可操作的日誌檔案](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *和* 聯繫 [!DNL Audience Manager] 顧問。 該表列出了廣告伺服器日誌檔案中可操作的信號：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日誌檔案中的頭名 </th> 
   <th colname="col2" class="entry"> 訊號 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
   <th colname="col4" class="entry"> 範例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>指示轉換是否匹配。 選項包括: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> 曝光 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> 按一下 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> 未屬性或未知 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> UTC的印象、按一下或轉換事件的日期和時間。 使用 <code>yyyy-MM-dd HH:mm:ss</code> 的子菜單。 </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>廣告商資料源的整合代碼。 請注意，此欄位與 <a href="../../features/datasources-list-and-settings.md">Audience Manager資料源。</a></p></td> 
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
   <td colname="col3"> <p>日誌檔案中的市場活動ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>日誌檔案中的Creative ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 採購或其他轉換金額。 資料類型：浮起來。 </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指示事件類型。 Audience Manager從日誌檔案名中讀取事件類型並將其轉換為可操作的信號。 請參閱 <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">日誌檔案命名約定</a>。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 留個印象。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按鈕 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> 轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用於捕獲日誌資料的資料源的ID。 請參閱 <a href="../../features/manage-datasources.md#create-data-source"> 如何建立資料源</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信號在 [!DNL Audience Manager] 像一個即時 `HTTP` 呼叫。 呼叫不一定必須包括 *全部* 示例調用中的信號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## 在Audience Manager用戶介面中處理可操作信號 {#actionable-signals-in-ui}

您可以在 [信號搜索](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) 。

轉到 **受眾資料** (1)> **信號** (2)> **搜索** (3)並選擇 **可操作的日誌檔案** (4)過濾器。

![UI中可操作的信號](/help/using/integration/assets/alf-in-signals.png)

要使用可操作信號建立基於規則的特徵，請選擇 **可操作的日誌檔案** (1)，選擇要用作特性規則的可操作信號(2)，然後按 **從所選信號建立特性** （三）。

![從信號中建立特徵](/help/using/integration/assets/alf-create-trait.png)


## 使用個案 {#use-cases}

實施的一個好處 [!UICONTROL Actionable Log Files] 是要應用的選項 [頻率](../../features/segments/recency-and-frequency.md) 控制項 [基於規則的特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 包含可操作信號。 例如，這允許您在媒體活動中對用戶顯示特定創意的次數進行頻率限制。 閱讀 [即時跨設備抑制](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) 來學習如何做。 其他使用案例包括：

### 重定目標用戶

重定目標用戶，這些用戶看到創意123，但沒有點擊或轉換，並向他們展示創意456。 執行動作:

1. 建立一個特徵，以捕捉看到創意的用戶。 假設你說出 [!DNL Creative Trait 123]。 使用特徵規則：

   `d_creative == 123 AND d_event == imp`

2. 建立特徵以捕獲按一下或轉換的用戶。 假設你給這個取名 [!DNL Click and Converter]。 使用特徵規則：

   `d_event == click OR d_event=conv`

3. 建立段以填充看到creative 123但未按一下或轉換的用戶。 命名它 [!DNL Retarget Users] 並使用段規則：

   `Creative Trait 123 AND NOT Click and Converter`

4. 映射段 [!DNL Retarget Users] 到目標和目標用戶，創意為456。

### 在「Audience Optimization報告」或「觀眾實驗室」中使用「Google市場活動經理」泛光燈活動

[泛光燈標籤](https://support.google.com/dcm/partner/answer/4293719?hl=en) 使廣告商能夠跟蹤用戶轉換。 與 [!UICONTROL Actionable Log Files]，您可以跟蹤 [!DNL Google Campaign Manager] 轉換 [Audience Optimization報告](../../reporting/audience-optimization-reports/audience-optimization-reports.md) 或 [觀眾實驗室](../../features/audience-lab/audience-lab.md):

1. 建立一個特性，並使用以下特性規則從ad伺服器日誌捕獲轉換：

   `d_event == conv AND d_conversion == 123`

   當在Audience Manager中建立特徵 [!UICONTROL UI]選中 [!UICONTROL Conversion] 的 [!UICONTROL Event Type]。

2. 一旦建立了該特性，將開始在 [!UICONTROL Audience Optimization Reports] 在 [!UICONTROL Audience Lab]。

>[!MORELIKETHIS]
>
>* [將Google市場活動經理資料檔案導入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [受眾最佳化報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

