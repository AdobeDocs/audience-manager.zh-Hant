---
description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-title: 適用 IAB TCF 的 Audience Manager 增效模組
solution: Audience Manager
title: 適用 IAB TCF 的 Audience Manager 增效模組
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# 適用 IAB TCF 的 Audience Manager 增效模組 {#aam-iab-plugin}

## 概述

您對使用者的隱私義務中，其中一個重要面向是針對如何利用使用者個人資料 (即「目的」)，以及該等資料會由誰使用 (即「公司」)，向使用者傳達其擁有的選項，並取得使用者的選擇。

Adobe 可讓您透過[選擇加入功能](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)和 [IAB 透明與同意架構 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。

本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。Audience Manager is registered in the IAB TCF with the vendor ID 565.

The Audience Manager Plug-in for IAB TCF utilizes the Opt-in functionality, which is, in turn, part of the Adobe Experience Cloud ID Service (ECID) library.[](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)[](https://marketing.adobe.com/resources/help/en_US/mcvid/)

## 範圍和限制 {#scope-and-limitations}

As a Publisher or Advertiser working with Audience Manager, you are able to convey user choices to Audience Manager as per IAB TCF. This provides you with an easy and consistent way of communicating user choices to all partners you work with and Audience Manager can help you respect your users' privacy choices.

本文所述的IAB TCF支援代表Audience manager計畫支援IAB架構的第一階段。 目前，Audience manager不支援：

* 行動裝置工作流程；
* 跨裝置許可管理；
* 將同意書附加至傳送至 [URL目的地的URL](/help/using/features/destinations/create-url-destination.md);
* 附加同意給區段。

## 必備條件 {#prerequisites}

您必須符合下列必要條件才能搭配Audience manager使用IAB TCF:

1. 您必須使用Experience Cloud ID服務(ECID)4.1版或更新版本。 [下載我們](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 最新的ECID版本。
2. 
   1. 您必須使用Audience Manager資料整合庫(DIL)9.0版或更新版本，可從此處 [下載](https://github.com/Adobe-Marketing-Cloud/dil/releases)。 閱讀Audience manager文 [件中的DIL相關資訊](/help/using/dil/dil-overview.md)。
   2. 或者，如果您使用伺服器端轉送(SSF)將資料匯入Audience Manager，則必須升級至最新版的AppMeasurement。 使用Analytics代碼管理 [器下載AppMeasurement](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)。
3. 您必須使用支援IAB且已向IAB TCF註冊的「同意管理平台」(CMP)，不論是商業版或您自己的版本。 請參見在IAB框架 [中註冊的CMP的清單](https://advertisingconsent.eu/cmp-list/)。

## 建議及實施方式 {#recommendations}

若要在Audience manager中啟用IAB TCF支援，請閱讀我們的檔案，了 [解如何使用選擇加入設定IAB](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)。

您最輕鬆的方式是使 [用Adobe Launch](https://docs.adobelaunch.com/) ，在您的屬性上測試ECID選擇加入。 Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## 使用IAB架構時的使用者選擇工作流程 {#user-choice-workflow}

在造訪Web屬性時，您的使用者可以提供其資料供發佈者及發佈者使用之第三方廠商使用的選擇。 使用者以標準用途和權限的形 *式提供* ，讓第 *三方廠商在全域廠商清單中註冊* 。 下圖代表CMP對話方塊的範例，顯示給網站的首次訪客。 請記住，根據客戶實作，此對話方塊看起來會大不相同。

![CMP對話框](/help/using/overview/aam-gdpr/assets/cmp.png)

IAB框架中的標準用途是：

* 資訊儲存和訪問
* 個人化
* 廣告選擇、傳送和報告
* 內容選擇、傳送和報告
* 測量

請參閱 [IAB架構規格頁](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) ，以瞭解五種標準用途的說明。

Users may grant their consent for a combination of standard purposes and vendors. For example, users could grant their consent for storage, personalization, and measurement and grant their consent to all third-party vendors displayed by the CMP. Or, in another example, they could grant their consent for all five standard purposes but only grant consent to a few of the vendors displayed by the CMP.

Once the user selects their privacy choices, the user choice(s) are recorded in the IAB TCF consent string. The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the IAB page for more information). [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format)Every vendor registered in the IAB TCF evaluates the IAB TCF consent string and makes decisions based on the users' privacy choices. Keep in mind that the users' privacy choices are valid across all approved vendors.

## Standard purposes needed by Audience Manager {#aam-standard-purposes}

Audience Manager evaluates the users' choices stored in the IAB TFC consent string for:

* Information storage and access (purpose ID 1 in the global vendor list)[](https://vendorlist.consensu.org/vendorlist.json)
* Personalization (purpose ID 2)
* Measurement (purpose ID 5)
* Audience Manager vendor consent to store, process, or activate on data for a publisher.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager behavior depends on whether the user grants consent {#aam-behavior-consent}

Audience Manager works differently depending on whether Audience Manager detects in the IAB TCF consent string that the user has provided consent for the three purposes (storage, personalization, measurement) or not.

| 當您的使用者 *提供同意*,Audience Manager會： | 當您的使用者拒 *絕* ,Audience Manager會： |
|---|---|
| <ul><li>執行您要求的所有Audience manager使用案例。</li><li>以ID同步傳達對第三方的同意（透過在ID同步呼叫中傳遞gdpr = 1和同意字串作為gdpr_concension）。</li><li>評估並接受從廣告伺服器像素傳遞的同意。</li><li>接受合作夥伴發起的ID同步。</li></ul> | <ul><li>不在實例中儲存任何新用戶資料。 這包括合作夥伴ID、訊號、特徵或像素資料。</li><li>不啟動第三方ID同步。</li><li>不遵守合作夥伴啟動的ID同步。</li></ul> |



## 發行者使用案例 {#publisher-use-case}

透過實作IAB TCF，您不需要透過Adobe或其他第三方廠商的不同機制，在您的Web屬性上維護自訂的許可管理代碼。 使用案例在影像和下列步驟中說明。 從影像左側開始：

1. 使用者瀏覽您的其中一個Web屬性。 只要您使用最新版的ECID和DIL程式庫(請參閱 [Presequires](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites))，就會觸發選擇加入流程。
2. Audience manager會檢查IAB流程是否套用(`isIabContext=true`)。 請參 [閱Recommendations及如何實作](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations)。
3. Audience manager會檢查GDPR是否適用(`gdpr = 1`)，以及您的Web屬性上是否有已向IAB註冊的CMP。 例如，這適用於從歐盟地區造訪的使用者。 請注意，您身為發行者，有責任設定GDPR旗標。
4. 如果適用GDPR,Audience manager會檢查在參數中傳遞的IAB TCF同意字串，以 `gdpr_consent`取得所需的權限。 Audience manager需要儲存、個人化、測量的權限，加上Audience manager廠商的同意權，才能儲存、處理或啟動資料。
5. 如果IAB TCF同意字串存在且包含必要的權限，Audience manager會將IAB TCF同意字串傳遞至我們的資 [料收集伺服器](/help/using/reference/system-components/components-data-collection.md) (DCS)。
6. Audience manager會在瀏覽器上設 [定Demdex Cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) ，做出回應。 Audience manager也會啟動並接受第三方ID同步。
7. 或者，如果在步驟5中傳遞的IAB TCF同意字串不包含所有必要的權限，Audience manager不會收集、處理或啟動資料，也不會執行或啟動ID同步。

![發行者使用案例](assets/publisher-use-case.png)

## 廣告商使用案例 {#advertiser-use-case}

Audience Manager evaluates and honors consent passed in pixel calls, in accordance with the IAB TCF.[](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)

像素通常由Audience manager客戶放在其合作夥伴頁面上，或置於廣告伺服器中以納入廣告回應。 In the first case, your partner must programmatically retrieve the consent parameter and add it to the pixel before firing. In the second case, which is more common and is described in detail below, ad servers append the consent parameters they receive from the Supply-Side Platform (SSP) or publisher ad servers to all pixels.

Audience Manager uses two parameters to pass user consent in pixel calls:

* `gdpr` 可以是0（GDPR不適用）或1（GDPR適用）;
* `gdpr_consent` is the URL-safe base64-encoded GDPR consent string (see specification). [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)A sample call for an impression pixel, with the two parameters could look like below:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

The use case is described in the image and in the steps below. Start from the left of the image:

1. Your user is served an impression via an ad server. 這會轉換為對資料收集伺服器(DCS)的像素呼叫。
1. Audience manager會檢查GDPR標幟是否適用。 如果沒有，Audience manager會將傳入巨集變數的資料儲存在像素呼叫中。
1. 如果同意字串存在且包含必要的權限，Audience manager會將傳入的資料儲存在像素呼叫的巨集變數中。
1. 如果同意字串遺失或缺少必要的權限，Audience manager會刪除像素呼叫中在巨集變數中傳遞的資料。

![廣告商使用案例](assets/advertiser-use-case.png)

## 支援IAB TCF的啟動合作夥伴 {#aam-activation-partners}

IAB TCF的Audience Manager外掛程式可讓您將IAB TCF同意字串轉寄給啟動合作夥伴，同時尊重使用者的隱私權選擇。 如需啟動合作夥伴支援IAB TCF（自2019年7月7日起準確無誤）的詳細資訊，請參閱我們的 **[Partner excel表單](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx)**。

## 測試您的IAB實作 {#test-iab-implementation}

若要測試您是否已正確實作IAB TCF的Audience manager外掛程式，請閱讀 [Use Case 4 in Validation Methods for Opt-in and IAB implementation](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)。

## IAB和Audience manager中的選擇退出。 優先順序。 {#iab-and-optout}

您的使用者可以選擇另一個隱私權選項，即選擇退出所有資料收集。 Adobe會在您的隱私權選擇頁面中提供使用者 [進行這項](https://www.adobe.com/privacy/opt-out.html#customeruse) 。

Audience manager可處理我們檔案中個別文 [章的退出管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)。

>[!NOTE]
>
>**優先順序** -如果您的使用者使用全域退出工具退出資料收集，如上述連結所述，優先順序優先於選擇加入和IAB驗證。

## 其他資源 {#additional-resources}

* [Experience Cloud ID服務選擇加入](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB歐洲GDPR透明度與同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB歐洲GDPR透明度和許可框架技術規格](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF plugin —— 視訊展示](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)