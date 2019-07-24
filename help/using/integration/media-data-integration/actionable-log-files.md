---
description: 「可動作記錄檔」可讓您擷取Google DCM記錄檔中的媒體資料，並使用資料在Audience Manager中建立特徵。從廣告伺服器擷取曝光數、點按數及轉換數做為特徵，而不必使用像素呼叫。
keywords: 可操作的記錄檔
seo-description: 「可動作記錄檔」可讓您擷取Google DCM記錄檔中的媒體資料，並使用資料在Audience Manager中建立特徵。從廣告伺服器擷取曝光數、點按數及轉換數做為特徵，而不必使用像素呼叫。
seo-title: 可操作的記錄檔
solution: Audience Manager
title: 可操作的記錄檔
uuid: 4c47615f-ed47-41ba-8694-1d7 de4 f55 d62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 可操作的記錄檔 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 可讓您擷取 [!DNL Google DCM] 記錄檔中的媒體資料，並使用資料在Audience Manager中建立特徵。從廣告伺服器擷取曝光數、點按數及轉換數做為特徵，而不必使用像素呼叫。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)在本文件中指出程式碼元素和選項。如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../reference/code-style-elements.md)。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 簡化從廣告伺服器擷取印象、點按和轉換的方式。Use this information for user segmentation without having to manually pixel media to send campaign attributes to [!DNL Audience Manager].

## 快速入門 {#getting-started}

To get started with [!UICONTROL Actionable Log Files], and to use our [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md), you need to import DCM log data into [!DNL Audience Manager]. See [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and* contact your [!DNL Audience Manager] consultant.

If you are already importing [!UICONTROL DCM] log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!NOTE] {importance=「high」}
>
>[!UICONTROL Actionable Log Files] 僅適用於 [!DNL Google DCM] 記錄檔。

## Working with Actionable Log Files {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from [!DNL DCM] logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager] 連線至您的 [!DNL Google Cloud] 儲存空間、剖析 [!DNL DCM] 記錄檔中的資訊，並將記錄檔資料傳送至我們 [的資料收集伺服器](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍需要設定規則型特徵來擷取可操作的訊號。See how to set up rule-based traits either in the [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or using our [Bulk Management Tools](../../reference/bulk-management-tools/bulk-create.md). Scroll down to the [Actionable Signals](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) section for a list of all the keys you can use in rule-based traits.

For an average-sized [!DNL DCM] log file of 2 million lines, any traits created from actionable signals are realized within approximately one hour after we process the logs.

>[!IMPORTANT] {importance=「high」}
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of*  [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). 我們發現這兩個選項的用途，因為這導致特徵的頻率計數增加。

## Actionable Signals {#actionable-signals}

Signals are the [smallest data units](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] 可讓您擷取曝光事件中的廣告商、業務單位、創意和促銷活動值，並按一下事件和轉換事件做為 [!DNL DCM] 記錄的訊號。

請記住，若要將此資訊用於觀眾建立和分段，您必須自行設定規則特徵。The table lists the actionable signals from [!DNL DCM] log files:

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
   <td colname="col2"> <p>僅適用於轉換事件。 </p> <p>代表DCM中轉換活動的數值ID。此欄位會對應至來自DCM的活動ID。 </p> <p> <p>秘訣：您可以從DCM擷取多個或特定的轉換活動。Create traits using <code> d_conversion = activity ID</code> for each conversion activity from DCM. </p> </p> </td> 
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
   <td colname="col2"> <p>廣告主 ID. 此欄位會對應至來自DCM的廣告商群組ID。 </p> </td> 
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
   <td colname="col2"> <p>用來擷取DCM資料之資料來源的ID。See <a href="../../features/manage-datasources.md#create-data-source"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. The example call below contains information on a conversion event from [!DNL DCM]. Calls do not necessarily have to include *all* the signals in the example call.

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

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. 例如，您可讓您在媒體促銷活動中，將使用者顯示特定創意的次數提升到最大。其他使用案例包括：

### 重新定向使用者

重新定向看見創意123但未按一下或轉換並顯示創意456的使用者。執行動作:

1. 建立特徵來擷取看過創意素材的使用者。Let's say you name the trait [!DNL Creative Trait 123]. 使用特徵規則：

   `d_creative == 123 AND d_event == imp`

1. 建立特徵來擷取按一下或轉換的使用者。Let's say you name this one [!DNL Click and Converter]. 使用特徵規則：

   `d_event == click OR d_event=conv`

1. 建立區段以填入看見創意123但未按一下或轉換的使用者。Name it [!DNL Retarget Users] and use the segment rule:

   `Creative Trait 123 AND NOT Click and Converter`

1. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### 在對象最佳化報表或Audience Lab中使用DCM Floodlight活動

[Floodlight標籤](https://support.google.com/dcm/partner/answer/4293719?hl=en) 可讓廣告商追蹤使用者轉換。With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md) or in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. 建立特徵並使用下列特徵規則，擷取廣告伺服器記錄檔的轉換：

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab].

>[!MORE_贊_ this]
>
>* [將DCM資料檔案匯入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [對象最佳化報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

