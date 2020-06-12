---
description: 可操作的記錄檔可讓您從廣告伺服器記錄檔擷取媒體訊號，以在Audience Manager中建立特徵。 從廣告伺服器擷取印象、點按和轉換為特徵，毋需附加像素。
keywords: actionable logs, alf, ALF
seo-description: 可操作的記錄檔可讓您從廣告伺服器記錄檔擷取媒體訊號，以在Audience Manager中建立特徵。 從廣告伺服器擷取印象、點按和轉換為特徵，毋需附加像素。
seo-title: 可操作的記錄檔
solution: Audience Manager
title: 可操作的記錄檔
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: 8f5dadb44ada3822b7336827c8863a7277b687c3
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 3%

---


# 可操作的記錄檔 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 可讓您從廣告伺服器記錄檔擷取媒體資料，並使用資料在Audience Manager中建立特徵。 Capture impressions, clicks, and conversions from ad servers as traits without having to append [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)在本檔案中指出程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../reference/code-style-elements.md)。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 簡化您從廣告伺服器擷取印象、點按和轉換的方式。 使用這項資訊進行使用者區隔，而不需手動將促銷活動屬性傳送至像素媒體 [!DNL Audience Manager]。

## 快速入門 {#getting-started}

若要開始使 [!UICONTROL Actionable Log Files]用，您必須將記錄檔資料匯入 [!DNL Audience Manager]。 下列連結將協助您開始使用：

* 如需 [!UICONTROL Google DCM] 記錄檔，請 [參閱將DCM資料檔案匯入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) , *並聯絡您的*[!DNL Audience Manager] 顧問。
* 如需 [!UICONTROL Google DFP] 記錄檔，請 [參閱將DFP資料檔案匯入Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) , *並聯絡您的*[!DNL Audience Manager] 顧問。
* 如需其他廣告伺服器記錄檔，請參 [閱資料和中繼資料](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)*檔案* ，並連絡您 [!DNL Audience Manager] 的顧問。

如果您已將記錄檔資料匯入 [!DNL Audience Manager]，請要求您的 [!DNL Audience Manager] 顧問或 [客戶服務為您](https://helpx.adobe.com/tw/contact/enterprise-support.ec.html)[!UICONTROL Actionable Log Files] 啟用。

>[!IMPORTANT]
>
> 從2019年底開始， [!UICONTROL Actionable Log Files] 新廣告伺服器的可用性開始增加。 Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/tw/contact/enterprise-support.ec.html) to get started.

## 使用可操作的日誌檔案 {#working-with-actionable-log-files}

使用 [!UICONTROL Actionable Log Files]時，廣告伺服器記錄檔的資訊會以 [!DNL Audience Manager] 您擷取即時網站互動資料的相同方式擷取。 [!DNL Audience Manager] 連線至您的廣告伺服器記錄檔儲存區，分析記錄檔中的資訊，並將記錄檔資料作為可操作訊號傳送至我們的資 [料收集伺服器](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍需要設定規則型特徵，以擷取可操作的訊號。 瞭解如何在 [Audience Manager UI或使用我們的大量管理工具](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ，設定以規 [則為基礎的特徵](../../reference/bulk-management-tools/bulk-create.md)。 向下捲動至「可 [操作的訊號](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) 」區段，以取得您可在規則型特徵中使用之所有鍵的清單。

>[!IMPORTANT]
>
>我們建議實作 [!UICONTROL Actionable Log Files] 而非 *像素*[呼叫](../../integration/media-data-integration/impression-data-pixels.md)。 我們不鼓勵使用這兩種選項，因為這會導致特徵的頻率增加。

## 可操作的信號 {#actionable-signals}

信號是中 [最小的資料單元](../../reference/signal-trait-segment.md)[!DNL Audience Manager]。 [!UICONTROL Actionable Log Files] 可讓您從廣告伺服器記錄檔中擷取廣告商、業務單位、創意和促銷活動值，以及點按事件和轉換事件。

請記住，若要使用這項資訊來建立和劃分受眾，您必須自行設定規則型特徵。

### 來自Google DCM記錄檔的可操作訊號 {#dcm-logs-signals}

該表列出了來自日誌檔案的可操作 [!DNL DCM] 信號：

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
   <td colname="col3"> <p>僅適用於轉換事件。 </p> <p>代表DCM中轉換活動的數值ID。 此欄位會從DCM對應至活動ID。 </p> <p> <p>提示： 您可以從DCM擷取多個或特定的轉換活動。 使用DCM中每 <code> d_conversion = activity ID</code> 個轉換活動建立特徵。 </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>僅適用於轉換事件。 </p> <p>此欄位對應至DCM中的轉換ID。 指示用戶從DCM轉換前的活動。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> 進行點按後轉換。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 用於曝光後轉換。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> 不符合的轉換。 轉換無法與先前的活動相符。 </li> 
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
   <td colname="col3"><p>廣告商資料來源的整合代碼。 請注意，這與Audience Manager資料來源無關。</p> <p>此欄位會從DCM對應至廣告商群組ID。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>業務單位ID。 此欄位從DCM對應至廣告商ID。 </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>DCM提供的促銷活動ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>DCM提供的Creative ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 銷售額以美元計，為-6的冪。 乘以1.000.000，以查看美元金額。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指出事件類型。 Audience Manager會從DCM記錄檔名讀取事件類型，並將其轉換為可操作的訊號。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 以獲得曝光。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按鈕。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> 轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用於捕獲DCM資料的資料源的ID。 請參閱 <a href="../../features/manage-datasources.md#create-data-source"> 如何建立資料來源</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表格中描述的信號像實 [!DNL Audience Manager] 時呼叫一樣被捕 `HTTP` 獲。 以下範例呼叫包含來自的轉換事件相關資訊 [!DNL DCM]。 呼叫不一定必須包含 *範例呼叫* 中的所有訊號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

對於平均大小為200萬行 [!DNL DCM] 的記錄檔，任何根據可操作訊號建立的特徵，都會在我們處理記錄檔後約一小時內實現。

>[!NOTE] {imporication=&quot;high&quot;}
>
>記錄檔中提供的事 [!DNL DCM] 件時間戳記將接受並傳遞至 [!UICONTROL Data Collection Servers]。
>
>* 如果日誌檔案中的資料行沒有時間戳 [!DNL DCM] 記，我們將調用的時間 `HTTP` 用作事件時間戳記。
>* 如果日誌檔案中的資料 [!DNL DCM] 行包含格式錯誤的時間戳記，我們將忽略整個行。


<br> 

### 來自一般廣告伺服器記錄檔的可操作訊號 {#generic-logs-signals}

首先，您必須將廣告伺服器登入我們的Amazon S3儲存貯體。 若要完成此作業，請 [閱讀「對象最佳化報表的資料檔案」和「可操作的記錄檔](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) 」 *並連絡您的*[!DNL Audience Manager] 顧問。 該表列出了通用日誌檔案中可操作的信號：

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
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> 非屬性或未知 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> 曝光、點按或轉換事件的UTC日期和時間。 使用格 <code>yyyy-MM-dd HH:mm:ss</code> 式。 </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>廣告商資料來源的整合代碼。 請注意，此欄位與 <a href="../../features/datasources-list-and-settings.md">Audience Manager資料來源無關。</a></p></td> 
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
   <td colname="col3"> <p>記錄檔中的Creative ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 購買或其他轉換金額。 資料類型： 漂浮。 </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指出事件類型。 Audience Manager會從記錄檔名讀取事件類型，並將其轉換為可操作的訊號。 請參 <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">閱日誌檔案命名約定</a>。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 以獲得曝光。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按鈕。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> 轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>您用來擷取記錄資料的資料來源ID。 請參閱 <a href="../../features/manage-datasources.md#create-data-source"> 如何建立資料來源</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表格中描述的信號像實 [!DNL Audience Manager] 時呼叫一樣被捕 `HTTP` 獲。 呼叫不一定必須包含 *範例呼叫* 中的所有訊號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## 在Audience Manager UI中使用可操作的信號 {#actionable-signals-in-ui}

您可以在「信號搜尋」介面中檢視傳入的可 [操作信號](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) 。

前往「 **觀眾資料** (1)> **訊號** (2)>搜尋 **(3)」，並選取「****** 可操作的記錄檔(4)」篩選器。

![UI中可操作的信號](/help/using/integration/assets/alf-in-signals.png)

若要使用可操作的訊號來建立規則型特徵，請選取可操作的記錄檔 **(1)，選取您要當做特徵規則使用的可操作訊號(2)，然後按** Create Trait from Selected Signals **** (3)。

![從訊號建立特徵](/help/using/integration/assets/alf-create-trait.png)


## 使用個案 {#use-cases}

實作的一個好 [!UICONTROL Actionable Log Files] 處是，將時近和頻 [率控制套用至任](../../features/segments/recency-and-frequency.md) 何包含可操作訊號的規則式特徵 [](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 。 例如，這可讓您在媒體促銷活動中，以頻率限制使用者顯示特定創意素材的次數。 閱 [讀立即跨裝置抑制](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) ，瞭解如何執行此動作。 其他使用案例包括：

### 重新定位使用者

重新鎖定看過創意123但未點按或轉換的使用者，並顯示創意456。 執行動作:

1. 建立特徵以擷取看到創意的使用者。 假設你給特徵命名 [!DNL Creative Trait 123]。 使用特徵規則：

   `d_creative == 123 AND d_event == imp`

2. 建立特徵以擷取點按或轉換的使用者。 假設你給這個命名 [!DNL Click and Converter]。 使用特徵規則：

   `d_event == click OR d_event=conv`

3. 建立區段，以填入看到Creative 123但未點按或轉換的使用者。 命名 [!DNL Retarget Users] 並使用區段規則：

   `Creative Trait 123 AND NOT Click and Converter`

4. 使用Creative 456將區 [!DNL Retarget Users] 段對應至目標，並定位目標使用者。

### 在對象最佳化報表或對象實驗室中使用DCM Floodlight活動

[Floodlight標籤](https://support.google.com/dcm/partner/answer/4293719?hl=en) ，讓廣告商可追蹤使用者轉換。 您可 [!UICONTROL Actionable Log Files]以在「對象最佳化報 [!DNL DCM] 告」或「對象實驗 [」中追蹤轉](../../reporting/audience-optimization-reports/audience-optimization-reports.md) 換率 [](../../features/audience-lab/audience-lab.md):

1. 建立特徵，並使用下列特徵規則從廣告伺服器記錄檔擷取轉換：

   `d_event == conv AND d_conversion == 123`

   在Audience Manager中建立特徵時， [!UICONTROL UI]請選 [!UICONTROL Conversion] 取為 [!UICONTROL Event Type]。

2. 在您建立特徵後，轉換將開始在和中報告 [!UICONTROL Audience Optimization Reports] 對象 [!UICONTROL Audience Lab]。

>[!MORELIKETHIS]
>
>* [將DCM資料檔案匯入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [受眾最佳化報告](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

