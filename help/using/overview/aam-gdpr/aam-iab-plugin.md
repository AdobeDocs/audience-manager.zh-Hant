---
description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-title: 適用 IAB TCF 的 Audience Manager 增效模組
solution: Audience Manager
title: 適用 IAB TCF 的 Audience Manager 增效模組
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# 適用 IAB TCF 的 Audience Manager 增效模組 {#aam-iab-plugin}

## 概述

您對使用者的隱私義務中，其中一個重要面向是針對如何利用使用者個人資料 (即「目的」)，以及該等資料會由誰使用 (即「公司」)，向使用者傳達其擁有的選項，並取得使用者的選擇。

Adobe 可讓您透過[選擇加入功能](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)和 [IAB 透明與同意架構 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。

本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。Audience Manager在IAB TCF中註冊，供應商ID565。

AAB TCF適用的Audience Manager外掛程式採用 [選擇加入功能](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)，這就是Adobe [Experience Cloud ID Service(ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) 程式庫的一部分。

## 範圍與限制 {#scope-and-limitations}

身為使用Audience Manager的Publisher或Advertiser，您可以根據IAB TCF將使用者選擇傳達給Audience Manager。這為您提供簡單且一致的方式，將使用者選擇與您使用的所有合作夥伴通訊，Audience Manager可協助您尊重使用者的隱私權選擇。

本文所述的IAB TCF支援代表AAB架構支援IAB架構的第一階段。目前Audience Manager不支援：

* 行動裝置工作流程；
* 跨裝置許可管理；
* 同意傳送至 [URL目的地](/help/using/features/destinations/create-url-destination.md)的URL；
* 附加同意區段。

## 必備條件 {#prerequisites}

您必須符合下列必要條件，才能搭配AAB TCF與Audience Manager搭配使用：

1. 您必須使用Experience Cloud ID Service(ECID)4.1版或更新版本。[下載](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 我們最新的ECID版本。
2. 
   1. 您必須在 [這裡](https://github.com/Adobe-Marketing-Cloud/dil/releases)使用Audience Manager Data Integration Library(DIL)9.0版或更新版本。閱讀Audience [Manager文件](/help/using/dil/dil-overview.md)中的DIL。
   2. 或者，如果您使用伺服器端轉送(SSF)將資料匯入Audience Manager，則必須升級至最新版本的AppMeasurement。使用 [Analytics代碼管理器下載AppMeasurement](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)。
3. 您必須使用支援IAB並透過IAB TCF註冊的同意管理平台(CMP)。請參閱IAB架構中註冊 [的CMS清單](https://advertisingconsent.eu/cmp-list/)。

## Recommendations及其實施方式 {#recommendations}

若要啓用AAB TCF支援，請參閱我們的 [說明文件，說明如何使用選擇加入設定IAB](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)。

使用 [Adobe Launch](https://docs.adobelaunch.com/) 對您的屬性進行ECID選擇時，這最簡單。Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## 使用IAB架構時的使用者選擇工作流程 {#user-choice-workflow}

瀏覽Web屬性時，您的使用者可以針對發行者和publisher搭配使用的第三方供應商提供他們的選擇。使用者以 *標準目的* 和權限向全球廠商清單註冊的 *第三方供應商* 提供他們的選擇。下圖代表CMP對話的範例，顯示給網站的首次訪客。請記住，根據客戶實施，此對話的外觀可能不同。

![CMP對話](/help/using/overview/aam-gdpr/assets/cmp.png)

IAB架構的標準用途包括：

* 資訊儲存與存取
* 個人化
* 廣告選擇、傳送和報告
* 內容選擇、傳送和報告
* 測量

請參閱 [IAB架構規格頁面](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) ，以瞭解五個標準用途的說明。

使用者得同意以標準用途組合及供應商。例如，使用者可同意其儲存、個人化及測量的同意，並同意由「CMP」顯示之所有第三方供應商。或者，在另一個範例中，他們可以給予所有五個標準用途的同意，但僅授予「CMP」所顯示之供應商的同意。

當使用者選擇其隱私權選項後，使用者選擇會記錄在IAB TCF許可字串中。IAB TCF許可字串儲存已核准用途和廠商以及其他中繼資料資訊的組合(請參閱 [IAB頁面](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) 以瞭解詳細資訊)。所有註冊於IAB TCF的供應商都會評估IAB TCF許可字串，並根據使用者的隱私權選擇做出決策。請記住，使用者的隱私權選擇適用於所有已核准的廠商。

## Audience Manager需要的標準用途 {#aam-standard-purposes}

Audience Manager會評估儲存在IAB TFC許可字串中的使用者選擇：

* 資訊儲存與存取(全域廠商清單 [中的目的ID1](https://vendorlist.consensu.org/vendorlist.json))
* 個人化(目的ID2)
* 測量(目的ID5)
* Audience Manager廠商同意儲存、處理或啓用publisher資料。

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager行為取決於使用者是否授予同意 {#aam-behavior-consent}

Audience Manager的運作方式視AAB TCF許可字串是否偵測到使用者是否已針對這三個用途提供同意(儲存、個人化、測量)而異。

| 當您的使用者 *同意時*，Audience Manager： | 當您的使用者 *拒絕* 同意時，Audience Manager： |
|---|---|
| <ul><li>執行所有您要求的Audience Manager使用案例。</li><li>以ID同步方式傳達給第三方，(透過將gdpr=和同意字串傳遞至ID同步呼叫上的gdpr_ consept)。</li><li>評估並表揚從廣告伺服器像素傳遞的同意。</li><li>合作夥伴啓始的ID同步。</li></ul> | <ul><li>不會儲存您例項中的任何新使用者資料。其中包括合作夥伴ID、訊號、特徵或像素資料。</li><li>不會起始第三方ID同步。</li><li>不符合合作夥伴啓始的ID同步。</li></ul> |



## 發行者使用個案 {#publisher-use-case}

實施IAB TCF後，您不需要透過與Adobe或其他第三方廠商不同的機制，為您的Web屬性上的同意管理維護自訂代碼。影像中說明使用案例，以及下方步驟。從影像左側開始：

1. 使用者瀏覽您的其中一個Web屬性。只要您使用最新版本的ECID和DIL程式庫(請參閱 [「必要條件](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)」)，就會觸發加入流程。
2. Audience Manager會檢查IAB流程是否套用(`isIabContext=true`)。請參閱 [Recommendations及其實施](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations)方式。
3. Audience Manager會檢查GDPR是否適用(`gdpr = 1`)以及是否有CMP(在您的Web屬性上註冊)。例如，這適用於從歐盟地區造訪的使用者。請注意，您應負責設定GDPR標幟。
4. 如果套用GDPR，Audience Manager會檢查在參數 `gdpr_consent`中傳遞的IAB TCF許可字串，以取得必要權限。Audience Manager需要儲存、個人化、測量以及Audience Manager廠商同意的權限，才能儲存、處理或啓動資料。
5. 如果IAB TCF許可字串存在且包含必要權限，Audience Manager會將IAB TCF同意字串傳遞至我們 [的資料收集伺服器](/help/using/reference/system-components/components-data-collection.md) (DCS)。
6. Audience Manager會在瀏覽器上設定 [Demdex Cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) 回應。Audience Manager也會起始並鳴謝第三方ID同步。
7. 或者，如果步驟中傳遞的IAB TCF許可字串不包含所有必要權限，Audience Manager不會收集、處理或啓動資料，也不會接受或啓動ID同步。

![發行者使用個案](assets/publisher-use-case.png)

## 廣告商使用案例 {#advertiser-use-case}

根據IAB TCF，Audience Manager會評估 [並接受像素呼叫](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)傳入的同意。

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

## 支援IAB TCF的啓動合作夥伴 {#aam-activation-partners}

AAB TCF適用的Audience Manager外掛程式可讓您將IAB TCF同意字串轉送給啓動合作夥伴，同時拒絕使用者的隱私權選擇。有關哪些啓動合作夥伴支援IAB TCF的資訊(截至2019年月日)，請參閱 **[我們的合作夥伴Excel工作表](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**。

## 測試您的IAB實作 {#test-iab-implementation}

若要測試您已正確實作IAB TCF的Audience Manager外掛程式，請參閱 [「在加入和IAB實作驗證方法中使用案例4](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)」。

## AAB和Option-out在Audience Manager中。優先順序。 {#iab-and-optout}

使用者使用的另一個隱私權選項是選擇退出所有資料收集。Adobe提供使用者在 [「您的隱私權選擇](https://www.adobe.com/privacy/opt-out.html#customeruse) 」頁面中這麼做的方法。

Audience Manager會在我們文件中的 [個別文章中處理選擇退出管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)。

>[!NOTE]
>
>**優先順序** -如果您的使用者使用全域選擇退出工具退出資料收集，則這會優先於選擇加入和IAB驗證。

## 其他資源 {#additional-resources}

* [Experience Cloud ID Service Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR透明度與同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR透明度與許可框架技術規格](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF增效模組-視訊展示](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)