---
description: 「可動作記錄檔」可讓您擷取Google DCM記錄檔中的媒體資料，並使用資料在Audience Manager中建立特徵。從廣告伺服器擷取曝光數、點按數及轉換數做為特徵，而不必使用像素呼叫。
keywords: 可操作的記錄檔
seo-description: 「可動作記錄檔」可讓您擷取Google DCM記錄檔中的媒體資料，並使用資料在Audience Manager中建立特徵。從廣告伺服器擷取曝光數、點按數及轉換數做為特徵，而不必使用像素呼叫。
seo-title: 可操作的記錄檔
solution: Audience Manager
title: 可操作的記錄檔
uuid: 4c47615f-ed47-41ba-8694-1d7 de4 f55 d62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# 可操作的記錄檔 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 可讓您擷取 [!DNL Google DCM] 記錄檔中的媒體資料，並使用資料在Audience Manager中建立特徵。從廣告伺服器擷取曝光數、點按數及轉換數做為特徵，而不必使用像素呼叫。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)在本文件中指出程式碼元素和選項。如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../reference/code-style-elements.md)。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 簡化從廣告伺服器擷取印象、點按和轉換的方式。使用此資訊進行使用者分段，而不需手動使用像素媒體來傳送促銷活動屬性 [!DNL Audience Manager]。

## 快速入門 {#getting-started}

若要開始使用 [!UICONTROL Actionable Log Files]，以及使用 [我們的「對象最佳化報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)」，您必須將DCM記錄檔匯入 [!DNL Audience Manager]至。請參閱 [將DCM資料檔案匯入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)*，* 並聯絡您的 [!DNL Audience Manager] 顧問。

如果您已將 [!UICONTROL DCM] 記錄資料匯入 [!DNL Audience Manager]，請要求 [!DNL Audience Manager] 顧問或 [客戶服務](https://helpx.adobe.com/contact/enterprise-support.ec.html) 啓用 [!UICONTROL Actionable Log Files] 。

>[!NOTE] {importance=「high」}
>
>[!UICONTROL Actionable Log Files] 僅適用於 [!DNL Google DCM] 記錄檔。

## 使用可操作的記錄檔 {#working-with-actionable-log-files}

此外 [!UICONTROL Actionable Log Files][!DNL DCM] ，記錄檔的資訊也 [!DNL Audience Manager] 會擷取來自即時網站互動資料的資料。[!DNL Audience Manager] 連線至您的 [!DNL Google Cloud] 儲存空間、剖析 [!DNL DCM] 記錄檔中的資訊，並將記錄檔資料傳送至我們 [的資料收集伺服器](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍需要設定規則型特徵來擷取可操作的訊號。瞭解如何在 [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 或使用 [我們的大量管理工具設定規則型特徵](../../reference/bulk-management-tools/bulk-create.md)。向下捲動至「 [可ActionSignal」](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) 區段，查看可用於規則型特徵的所有索引鍵清單。

對於超過1000000行的平均 [!DNL DCM] 記錄檔，在處理記錄檔後大約一小時內，就會實現任何由可操作訊號建立的特性。

>[!IMPORTANT] {importance=「high」}
>
>建議您實施 [!UICONTROL Actionable Log Files]*，而非*[像素呼叫](../../integration/media-data-integration/impression-data-pixels.md)。我們發現這兩個選項的用途，因為這導致特徵的頻率計數增加。

## 可操作的訊號 {#actionable-signals}

訊號是最 [小的資料單位](../../reference/signal-trait-segment.md)[!DNL Audience Manager]。[!UICONTROL Actionable Log Files] 可讓您擷取曝光事件中的廣告商、業務單位、創意和促銷活動值，並按一下事件和轉換事件做為 [!DNL DCM] 記錄的訊號。

請記住，若要將此資訊用於觀眾建立和分段，您必須自行設定規則特徵。表格列出 [!DNL DCM] 來自記錄檔的可操作訊號：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 訊號 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 範例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ event</code> </p> </td> 
   <td colname="col2"> <p>指出來自DCM的事件類型。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_ event= imp</code> for impressions。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_ event= click</code> for click。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_ event= config</code> 進行轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp，click，conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversion</code> </p> </td> 
   <td colname="col2"> <p>僅適用於轉換事件。 </p> <p>代表DCM中轉換活動的數值ID。此欄位會對應至來自DCM的活動ID。 </p> <p> <p>秘訣：您可以從DCM擷取多個或特定的轉換活動。使用 <code> dCM中每個轉換活動的d_ conversion=活動ID</code> 來建立特徵。 </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversionType</code> </p> </td> 
   <td colname="col2"> <p>僅適用於轉換事件。 </p> <p>此欄位會對應至DCM中的轉換ID。指出使用者從DCM轉換之前的活動。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 點</code> 按後轉換。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> ，用於曝光後轉換。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> ，產生不相符的轉換。轉換無法符合先前的活動。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsc</code> </p> </td> 
   <td colname="col2"> <p>廣告主 ID.</p> <p>廣告商資料來源的整合代碼。請注意，這與Audience Manager資料來源無關。</p> <p>此欄位會對應至來自DCM的廣告商群組ID。 </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col2"> <p>業務單位ID。此欄位會對應至來自DCM的廣告商ID。 </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col2"> <p>DCM提供的促銷活動ID。 </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col2"> <p>DCM提供的Creative ID。 </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col2"> <p>用來擷取DCM資料之資料來源的ID。請參閱 <a href="../../features/manage-datasources.md#create-data-source"> 如何建立資料來源</a>。 </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表格中描述的訊號 [!DNL Audience Manager] 會像 `HTTP` 即時呼叫一樣擷取。以下範例呼叫包含有關轉換事件的資訊 [!DNL DCM]。呼叫不一定必須包含 *範例呼叫中的所有* 訊號。

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance=「high」}
>
>[!DNL DCM] 記錄中提供的事件時間戳記將會履行並傳遞 [!UICONTROL Data Collection Servers]至。
>
>* [!DNL DCM] 如果記錄檔中的資料行無法使用時間戳記，我們將 `HTTP` 呼叫時間當做事件時間戳記。
>* [!DNL DCM] 如果記錄檔中的資料行包含格式錯誤的時間戳記，我們會忽略整個列。


## 使用個案 {#use-cases}

實施 [!UICONTROL Actionable Log Files] 的好處之一，就是將 [最近一次的頻率和頻率](../../features/segments/recency-and-frequency.md) 控制套用至任何 [包含可動作訊號的規則型特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 。例如，您可讓您在媒體促銷活動中，將使用者顯示特定創意的次數提升到最大。其他使用案例包括：

### 重新定向使用者

重新定向看見創意123但未按一下或轉換並顯示創意456的使用者。執行動作:

1. 建立特徵來擷取看過創意素材的使用者。假設您為特徵命名 [!DNL Creative Trait 123]。使用特徵規則：

   `d_creative == 123 AND d_event == imp`

1. 建立特徵來擷取按一下或轉換的使用者。讓我們假設您為 [!DNL Click and Converter]此命名。使用特徵規則：

   `d_event == click OR d_event=conv`

1. 建立區段以填入看見創意123但未按一下或轉換的使用者。命名並 [!DNL Retarget Users] 使用區段規則：

   `Creative Trait 123 AND NOT Click and Converter`

1. 使用創意456將區段 [!DNL Retarget Users] 對應至目的地並定位目標使用者。

### 在對象最佳化報表或Audience Lab中使用DCM Floodlight活動

[Floodlight標籤](https://support.google.com/dcm/partner/answer/4293719?hl=en) 可讓廣告商追蹤使用者轉換。有 [!UICONTROL Actionable Log Files]了，您可以追蹤 [!DNL DCM][對象最佳化報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md) 或 [Audience Lab](../../features/audience-lab/audience-lab.md)中的轉換：

1. 建立特徵並使用下列特徵規則，擷取廣告伺服器記錄檔的轉換：

   `d_event == conv AND d_conversion == 123`

   在Audience Manager中建立特徵時 [!UICONTROL UI]，請選擇 [!UICONTROL Conversion][!UICONTROL Event Type]為。

2. 當您建立特徵後，就會開始報告和開始報告轉換 [!UICONTROL Audience Optimization Reports][!UICONTROL Audience Lab]。

>[!MORE_贊_ this]
>
>* [將DCM資料檔案匯入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [對象最佳化報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

