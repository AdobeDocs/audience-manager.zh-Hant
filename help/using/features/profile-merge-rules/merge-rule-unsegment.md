---
description: 「取消分段」說明從區段中取消資格和移除裝置設定檔的程序。您從區段移除裝置描述檔的能力，取決於用於建立描述檔合併規則的裝置選項。
seo-description: 「取消分段」說明從區段中取消資格和移除裝置設定檔的程序。您從區段移除裝置描述檔的能力，取決於用於建立描述檔合併規則的裝置選項。
seo-title: 描述檔合併規則與裝置取消分段程序
solution: Audience Manager
title: 描述檔合併規則與裝置取消分段程序
uuid: b61c6de3-5Fe4-4892-a05 a-96a4 cb35 af34
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rules and Device Un-Segmentation Processes {#profile-merge-rules-and-device-un-segmentation-processes}

「取消分段」說明從區段中取消資格和移除裝置設定檔的程序。Your ability to remove a device profile from a segment depends on the device option used to create a [!UICONTROL Profile Merge Rule].

## Available Device Options {#device-options}

As a reminder, the [!UICONTROL Device Options] are available in the [!UICONTROL Profile Merge Rules Setup] section when you create or edit a [!UICONTROL Profile Merge Rule].

![](assets/merge-rules-options.png)

## Current Device Profile Option and Device Unsegmentation {#current-device-profile-options}

**[!UICONTROL Current Device Profile]** 是預設裝置設定檔選項 [!UICONTROL Profile Merge Rule]。[!DNL Audience Manager] 可在 [!UICONTROL Profile Merge Rule] 您使用 **[!UICONTROL Current Device Profile]** 選項時從區段移除裝置描述檔。在下列情況下，在下列情況下會發生取消分段：

* 裝置設定檔閒置120天。每周資料清理程序會移除區段中的非活動裝置設定檔。
* 裝置不再符合區段的資格，因為裝置設定檔的更新或變更會使其不符合資格。This happens when segment qualification criteria change, or you apply an [!DNL AND NOT] operator to a segment rule, or specify [recency and frequency](../../features/segments/recency-and-frequency.md) conditions that use the less than/equal to settings. [「立即跨裝置抑制」](../../features/profile-merge-rules/instant-cross-device-suppression.md) 文件說明使用案例。

![](assets/single_device_use_case.png)

<!-- 

<p> <span class="keyword"> Audience Manager</span> can remove a device profile from a segment when your <span class="wintitle"> Profile Merge Rule</span> uses the <b><span class="uicontrol"> Current Device Profile</span></b> option. Under these conditions, unsegmentation happens when: </p> 
<p> 
 <ul id="ul_596501272A224228BD330DD56E01D973"> 
  <li id="li_E4FA1A5C722748CD82AE3A49FCBE86F6">The device profile has been inactive for 120-days. A weekly data cleanup process removes inactive device profiles from your segments. </li> 
  <li id="li_DB0CCD28425048D5B35309B8C2C384F9">The device no longer qualifies for a segment because updates or changes to the device profile disqualify it. This happens when segment qualification criteria change, or you apply an AND NOT operator to a segment rule, or specify <a href="../../features/segments/recency-and-frequency.md"> recency and frequency</a> conditions that use the less than/equal to settings. </li> 
 </ul> </p> 
<p style="text-align: center;"> <img src="assets/unsegment3.png" id="image_B55E5A5EB1964AA08C817211006294E1" /> </p>

 -->

## No Device Option and Device Unsegmentation {#no-device-option}

[!DNL Audience Manager] 可以在 [!UICONTROL Profile Merge Rule] 使用 **[!UICONTROL No Device Profile]** + **[!UICONTROL Current Authenticated]** 選項時從區段移除跨裝置ID。在這些情況下，跨裝置ID的跨裝置ID不符合區段資格，因為跨裝置設定檔的更新或變更會使其不符合資格。This happens when segment qualification criteria change, or you apply an [!UICONTROL AND NOT] operator to a segment rule, or specify [recency and frequency](../../features/segments/recency-and-frequency.md) conditions that use the less than/equal to settings. [「立即跨裝置抑制」](../../features/profile-merge-rules/instant-cross-device-suppression.md) 文件說明使用案例。

![](assets/no_device_use_case.png)

## Device Graph Options and Device Unsegmentation {#device-graph-options-unsegmentation}

[!DNL Audience Manager] 可以在 [!UICONTROL Profile Merge Rule] 使用裝置圖表選項時從區段移除多個裝置設定檔。當裝置圖表中裝置的合併描述檔不符合區段的更新或變更，因為此合併設定檔的更新或變更將不符合區段資格時，就會發生分段。This happens when segment qualification criteria change, or you apply an [!UICONTROL AND NOT] operator to a segment rule, or specify [recency and frequency](../../features/segments/recency-and-frequency.md) conditions that use the less than/equal to settings. [「立即跨裝置抑制」](../../features/profile-merge-rules/instant-cross-device-suppression.md) 文件說明使用案例。

>[!NOTE]
>
>**使用裝置圖表評估區段時，區段評估和取消資格**[!DNL Audience Manager] 的四裝置限制最多可合併 [!UICONTROL Profile Merge Rule] 四部裝置。[!DNL Audience Manager] 評估 *目前裝置和上次看到的三部裝置*。如果未發出區段訊號，則會從目的地中移除即時檢視的目前裝置和另外三個裝置。例如，在六裝置叢集中，最多可合併、評估和符合區段的部裝置。同樣地，最多可合併、評估和未分段個裝置。

![](assets/cross_device_workflow.png)

<!-- 

<p>Currently, <span class="keyword"> Audience Manager</span> <i>cannot </i> remove a device profile from a segment when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. This applies to rules created with these <span class="wintitle"> Device Options</span> settings: </p> 
<p> 
 <ul id="ul_0923834C984F464E9AB12FF5A8773214"> 
  <li id="li_731F67B7A07342988B13D7F91ECA5A9E">Profile Link Device Graph. </li> 
  <li id="li_D1EFC6F124124E64A0732DD060F788BE">The <span class="keyword"> Adobe</span> device graph. </li> 
  <li id="li_CFD4189D4488432D92732532D23B30C7">Other third-party device graph options available that are available to you. </li> 
 </ul> </p> 
<p> Unlike the previous case above, using the AND NOT operator or less than/equal to settings won't remove all of the devices from a segment profile. However, you can unsegment device profiles if you create simple segment rules and apply unsegment logic in the destination that receives your data. The following sections walks you through different unsegmentation use cases. </p>

 -->



<!-- 

<p>This workaround shows you how to unsegment with Boolean <span class="wintitle"> AND NOT</span> logic when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. This procedure uses separate, simple segments mapped to the same destination. In this case, you apply AND NOT logic on the destination rather than creating rules in Segment Builder. To set up unsegment rules for this use case: </p> 
<p> 
 <ol id="ol_677F0F9E6CB640079D9021DE66819916"> 
  <li id="li_95F898FDFB2D4F5395201FEA2E60A3AF">Create separate, single-trait segments as shown in the following example. <p style="text-align: center;"><img src="assets/unsegment1.png" id="image_9574D599F449482F8475D9AD2B725DE1" /> </p> </li> 
  <li id="li_3A9F6D8B3CBB4F65B9A06EEC3B265158">Map the segments to the same destination. In this case, we're sending these to <span class="keyword"> Media Optimizer</span>. </li> 
  <li id="li_092BB5887D0D4EE4B09F4B1C6703D454">Set AND NOT logic on the destination (<span class="keyword"> Media Optimizer</span>) rather than in <span class="keyword"> Audience Manager</span>. <p style="text-align: center;"><img src="assets/unsegment2.png" id="image_1E707693ABED41129F11F9FBA334DA58" /> </p> </li> 
 </ol> </p> 
<p> If you're not using <span class="keyword"> Media Optimizer</span>, apply AND NOT logic on whatever destination receives these segments. </p>

 -->



<!-- 

<p>This workaround shows you how to unsegment with the < = (less than/equal to) recency and frequency settings when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. To set up unsegment rules for this use case: </p> 
<p> 
 <ol id="ol_DCBEE004B9FE40A881E4EC17FAEA50C2"> 
  <li id="li_DB8C1B6D5C5546E68769902A4F367966">Create a segment that contains a single trait and apply a > = (greater than/equal to) recency and frequency rule to the trait. <p style="text-align: center;"><img src="assets/unsegment4.png" id="image_38069E00B8E8435AAD6E4420CC788D1E" /> </p> </li> 
  <li id="li_0DC50960D83B4B27A40F0BC76B944E0B">Map the segment to a destination. In this case, we're sending the segment to <span class="keyword"> Media Optimizer</span>. </li> 
  <li id="li_FC23194A9FE54296914393F8067A6672">Set NOT logic on the destination (<span class="keyword"> Media Optimizer</span>) rather than in <span class="keyword"> Audience Manager</span>. Use NOT logic to exclude all devices that qualify for this segment from your campaign. <p style="text-align: center;"><img src="assets/unsegment5.png" id="image_BE4408DCB12041A191F208CB1807B9E6" /> </p> </li> 
 </ol> </p> 
<p> If you're not using <span class="keyword"> Media Optimizer</span>, apply NOT logic on whatever destination receives these segments. </p>

 -->

>[!MORE_贊_ this]
>
>* [描述檔合併規則與裝置圖表常見問題](../../faq/faq-profile-merge.md)
>* [即時跨裝置隱藏功能](../../features/profile-merge-rules/instant-cross-device-suppression.md)
>* [設定檔合併規則與裝置圖表的重要考量](../../features/profile-merge-rules/considerations-pmr-device-graph.md)

