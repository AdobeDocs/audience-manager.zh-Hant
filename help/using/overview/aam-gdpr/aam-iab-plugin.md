---
description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-title: 適用 IAB TCF 的 Audience Manager 增效模組
solution: Audience Manager
title: 適用 IAB TCF 的 Audience Manager 增效模組
translation-type: tm+mt
source-git-commit: 0e32fcaee617e7f18ce4223ffacc39708fb32786

---


# 適用 IAB TCF 的 Audience Manager 增效模組 {#aam-iab-plugin}

## 概述

您對使用者的隱私義務中，其中一個重要面向是針對如何利用使用者個人資料 (即「目的」)，以及該等資料會由誰使用 (即「公司」)，向使用者傳達其擁有的選項，並取得使用者的選擇。

Adobe 可讓您透過[選擇加入功能](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)和 [IAB 透明與同意架構 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。

本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。Audience Manager在IAB TCF中註冊，供應商ID565。

The Audience Manager Plug-in for IAB TCF utilizes the [Opt-in functionality](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html), which is, in turn, part of the Adobe [Experience Cloud ID Service (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) library.

## Scope and Limitations {#scope-and-limitations}

身為使用Audience Manager的Publisher或Advertiser，您可以根據IAB TCF將使用者選擇傳達給Audience Manager。這為您提供簡單且一致的方式，將使用者選擇與您使用的所有合作夥伴通訊，Audience Manager可協助您尊重使用者的隱私權選擇。

本文所述的IAB TCF支援代表AAB架構支援IAB架構的第一階段。目前Audience Manager不支援：

* 行動裝置工作流程；
* 跨裝置許可管理；
* Appending consent to URLs sent to [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination);
* 附加同意區段。

## 必備條件 {#prerequisites}

您必須符合下列必要條件，才能搭配AAB TCF與Audience Manager搭配使用：

1. 您必須使用Experience Cloud ID Service(ECID)4.1版或更新版本。[下載](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 我們最新的ECID版本。
2. 
   1. You must be using Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from [here](https://github.com/Adobe-Marketing-Cloud/dil/releases). Read about [DIL in the Audience Manager documentation](/help/using/dil/dil-overview.md).
   2. 或者，如果您使用伺服器端轉送(SSF)將資料匯入Audience Manager，則必須升級至最新版本的AppMeasurement。Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
3. 您必須使用支援IAB並透過IAB TCF註冊的同意管理平台(CMP)。See the list of [CMPs registered within the IAB framework](https://advertisingconsent.eu/cmp-list/).

## Recommendations and how to implement {#recommendations}

To enable the IAB TCF support in Audience Manager, read our documentation on [how to set up IAB with Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

This is easiest done by using [Adobe Launch](https://docs.adobelaunch.com/) to instrument ECID Opt-in on your properties. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## User choice workflow when using the IAB framework {#user-choice-workflow}

瀏覽Web屬性時，您的使用者可以針對發行者和publisher搭配使用的第三方供應商提供他們的選擇。Users provide their choices in the form of *standard purposes* and permissions to *third-party vendors* registered in the global vendor list. 下圖代表CMP對話的範例，顯示給網站的首次訪客。請記住，根據客戶實施，此對話的外觀可能不同。

![CMP對話](/help/using/overview/aam-gdpr/assets/cmp.png)

IAB架構的標準用途包括：

* 資訊儲存與存取
* 個人化
* 廣告選擇、傳送和報告
* 內容選擇、傳送和報告
* 測量

Refer to the [IAB framework specification page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) for a description of the five standard purposes.

使用者得同意以標準用途組合及供應商。例如，使用者可同意其儲存、個人化及測量的同意，並同意由「CMP」顯示之所有第三方供應商。或者，在另一個範例中，他們可以給予所有五個標準用途的同意，但僅授予「CMP」所顯示之供應商的同意。

當使用者選擇其隱私權選項後，使用者選擇會記錄在IAB TCF許可字串中。The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the [IAB page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) for more information). 所有註冊於IAB TCF的供應商都會評估IAB TCF許可字串，並根據使用者的隱私權選擇做出決策。請記住，使用者的隱私權選擇適用於所有已核准的廠商。

## Standard purposes needed by Audience Manager {#aam-standard-purposes}

Audience Manager會評估儲存在IAB TFC許可字串中的使用者選擇：

* Information storage and access (purpose ID 1 in the [global vendor list](https://vendorlist.consensu.org/vendorlist.json))
* 個人化(目的ID2)
* 測量(目的ID5)
* Audience Manager廠商同意儲存、處理或啓用publisher資料。

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager behavior depends on whether the user grants consent {#aam-behavior-consent}

Audience Manager的運作方式視AAB TCF許可字串是否偵測到使用者是否已針對這三個用途提供同意(儲存、個人化、測量)而異。

| When your user *provides consent*, Audience Manager: | When your user *declines* consent, Audience Manager: |
|---|---|
| <ul><li>執行所有您要求的Audience Manager使用案例。</li><li>以ID同步方式傳達給第三方，(透過將gdpr=和同意字串傳遞至ID同步呼叫上的gdpr_ consept)。</li><li>評估並表揚從廣告伺服器像素傳遞的同意。</li><li>合作夥伴啓始的ID同步。</li></ul> | <ul><li>不會儲存您例項中的任何新使用者資料。其中包括合作夥伴ID、訊號、特徵或像素資料。</li><li>不會起始第三方ID同步。</li><li>不符合合作夥伴啓始的ID同步。</li></ul> |



## Publisher Use Case {#publisher-use-case}

實施IAB TCF後，您不需要透過與Adobe或其他第三方廠商不同的機制，為您的Web屬性上的同意管理維護自訂代碼。影像中說明使用案例，以及下方步驟。從影像左側開始：

1. 使用者瀏覽您的其中一個Web屬性。As long as you are using the latest versions of the ECID and DIL libraries (see [Prerequisites](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), the opt-in flow is triggered.
2. Audience Manager checks whether the IAB flow applies (`isIabContext=true`). See [Recommendations and how to implement](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager checks whether GDPR applies (`gdpr = 1`) and whether there is a CMP, registered with IAB, on your web property. 例如，這適用於從歐盟地區造訪的使用者。請注意，您應負責設定GDPR標幟。
4. If GDPR applies, Audience Manager checks the IAB TCF consent string, passed in the parameter `gdpr_consent`, for the needed permissions. Audience Manager需要儲存、個人化、測量以及Audience Manager廠商同意的權限，才能儲存、處理或啓動資料。
5. If the IAB TCF consent string is present and it contains the required permissions, Audience Manager passes the IAB TCF consent string on to our [data collection servers](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager responds by setting a [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) on the browser. Audience Manager也會起始並鳴謝第三方ID同步。
7. 或者，如果步驟中傳遞的IAB TCF許可字串不包含所有必要權限，Audience Manager不會收集、處理或啓動資料，也不會接受或啓動ID同步。

![發行者使用個案](assets/publisher-use-case.png)

## Advertiser Use Case {#advertiser-use-case}

Audience Manager evaluates and honors consent passed in [pixel calls](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), in accordance with the IAB TCF.

像素通常由Audience Manager客戶在其合作夥伴頁面上放置，或放在廣告伺服器中以便加入廣告回應中。在第一個案例中，您的合作夥伴必須以程式設計方式擷取同意參數並將其新增至像素，然後才觸發。在第二個案例中較常見的情況下，詳細說明如下：廣告伺服器會附加從供應端平台(SSP)接收的同意參數，或將sher廣告伺服器附加至所有像素。

Audience Manager使用兩個參數來傳遞像素呼叫的使用者同意：

* `gdpr` 可能為(GDPR不適用)或1(GDPR適用)；
* `gdpr_consent` 是URL安全的base64編碼GDPR許可字串(請參閱 [規格](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications))。曝光像素的範例呼叫，其中兩參數看起來如下所示：

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

影像中說明使用案例，以及下方步驟。從影像左側開始：

1. 透過廣告伺服器讓您的使用者印象深刻。如此就可對資料收集伺服器(DCS)進行像素呼叫。
1. Audience Manager會檢查是否套用GDPR旗標。如果沒有，Audience Manager會儲存像素呼叫中巨集變數傳入的資料。
1. 如果許可字串存在且包含必要權限，Audience Manager會儲存像素呼叫中巨集變數中傳入的資料。
1. 如果同意字串遺失或缺少必要權限，Audience Manager會捨棄像素呼叫中巨集變數傳入的資料。

![廣告商使用案例](assets/advertiser-use-case.png)

## Activation partners that support IAB TCF {#aam-activation-partners}

AAB TCF適用的Audience Manager外掛程式可讓您將IAB TCF同意字串轉送給啓動合作夥伴，同時拒絕使用者的隱私權選擇。For information on which activation partners support IAB TCF (accurate as of July 7th, 2019), refer to our **[Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**.

## Test your IAB implementation {#test-iab-implementation}

To test that you have correctly implemented the Audience Manager Plug-in for IAB TCF, read [Use Case 4 in Validation Methods for Opt-in and IAB implementation](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## AAB和Option-out在Audience Manager中。Order of precedence. {#iab-and-optout}

使用者使用的另一個隱私權選項是選擇退出所有資料收集。Adobe provides users with the means to do so within the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page.

Audience Manager addresses opt-out management in a [separate article in our documentation](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**優先順序** -如果您的使用者使用全域選擇退出工具退出資料收集，則這會優先於選擇加入和IAB驗證。

## 其他資源 {#additional-resources}

* [Experience Cloud ID Service Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR透明度與同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR透明度與許可框架技術規格](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF增效模組-視訊展示](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)