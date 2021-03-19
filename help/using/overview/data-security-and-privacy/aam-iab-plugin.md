---
description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-title: 適用於 IAB TCF 的 Audience Manager 外掛程式
solution: Audience Manager
title: 適用於 IAB TCF 的 Audience Manager 外掛程式
feature: 資料管理與隱私
translation-type: tm+mt
source-git-commit: 65598677498ede26e4961cd4849c9b655dac38dc
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 40%

---


# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## 概述

您可能對使用者承擔的隱私權義務中的一個重要方面，是針對個人資料的使用方式（即「用途」）及其使用者（即「公司」），取得並傳遞使用者選擇。

Adobe 可讓您透過[選擇加入功能](https://docs.adobe.com/content/help/zh-Hant/id-service/using/implementation/opt-in-service/optin-overview.translate.html)和 [IAB 透明與同意架構 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。

本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。

>[!IMPORTANT]
>
>Audience Manager在[IAB TCF](https://iabeurope.eu/tcf-for-vendors/)中註冊，供應商ID為565。

適用於 IAB TCF 的 Audience Manager 外掛程式採用[選擇加入功能](https://docs.adobe.com/content/help/zh-Hant/id-service/using/implementation/opt-in-service/iab.html)，而這又是 [ Experience Platform Identity Service (ECID)](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html) 程式庫的一部分。

## 範圍和限制 {#scope-and-limitations}

身為使用 Audience Manager 的發佈商或廣告商，您可以依據 IAB TCF 向 Audience Manager 傳達使用者的選擇。

>[!IMPORTANT]
>
>IAB TCF規定僅適用於位於歐洲經濟區的訪客。

Audience Manager可協助您尊重使用者的隱私權選擇，並提供您簡單的方式，讓您與所有合作夥伴溝通這些選擇。

目前 Audience Manager 不支援：

* 行動裝置工作流程；
* 附加同意書至區段出口。

## 升級為 [!DNL IAB TCF v2.0] {#upgrading}

將[!DNL Audience Manager Plug-in for IAB TCF]實施從[!DNL IAB TCF] v1.1升級至[!DNL IAB TCF] v2.0，或首次啟用[!DNL IAB TCF] v2.0的客戶，應依照下述先決條件和實施的相同准則。

## 必要條件 {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager支援IAB TCF v2.0。
>
>IAB TCF v1.1支援將於2020年8月15日終止。
>
> 希望繼續使用IAB TCFAudience Manager插件進行許可管理的客戶應升級至[ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)的最新版本以獲得持續支援。
>
> 升級至最新的[ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)版本後，將不再支援IAB TCF v1.1同意字串，因此請務必在升級至最新的ECID版本之前更新您的CMP。

您必須符合以下先決條件，才能將IAB TCF的Audience Manager插件與Audience Manager一起使用：

1. 您必須使用 Adobe Experience Platform Identity Service (ECID) 5 或更新版本。[下載](https://github.com/Adobe-Marketing-Cloud/id-service/releases)最新版 ECID。
2. 您必須使用Audience Manager[!DNL Data Integration Library](DIL)9.0版或更新版本，可從[這裡](https://github.com/Adobe-Marketing-Cloud/dil/releases)下載。 閱讀 [Audience Manager 中的 DIL 文件](../../dil/dil-overview.md)。我們建議使用[Adobe啟動](https://docs.adobe.com/content/help/zh-Hant/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html)，以便最輕鬆地實作Audience Manager。
3. 或者，如果您使用[!DNL Server-Side Forwarding](SSF)將資料匯入Audience Manager，則必須升級至最新版的AppMeasurement。 使用 [Analytics 代碼管理器](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-tools/code-manager-admin.translate.html)下載 AppMeasurement。
4. 您必須使用與IAB TCF v2.0整合併已向IAB TCF註冊的「同意管理平台」(CMP)，不論是商業版或您自己的版本。 請參閱[在 IAB 框架內註冊的 CMP](https://iabeurope.eu/cmp-list/) 清單。

>[!WARNING]
>
>如果您使用不支援IAB TCF v.2.0的「同意管理平台」(CMP)，即使您的訪客在歐盟地區，Audience Manager仍會自動傳送ID同步的`gdpr=0`參數。 要確定您的GDPR驗證是否處於活動狀態，建議您向許可管理平台(CMP)確認它們支援IAB TCF v2.0。

## 建議及實作方式 {#recommendations}

若要在 Audience Manager 中啟用 IAB TCF 支援，請參閱[如何透過選擇加入設定 IAB](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html) 文件。

最簡單的方式是使用[Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html)在您的屬性上新增[!DNL ECID Opt-in]。 請參閱 [ECID 選擇加入擴充功能](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html)文件，瞭解如何設定 Launch 擴充功能。

## 使用 IAB 架構時的使用者選擇工作流程 {#user-choice-workflow}

造訪 Web 屬性時，您的使用者可以選擇提供其資料供發佈商及與發佈商合作的第三方廠商使用。

用戶以&#x200B;*conmence*&#x200B;和&#x200B;*合法利益*&#x200B;的形式為IAB目的提供選擇給在全球供應商清單中註冊的&#x200B;*第三方供應商*。

下圖呈現 CMP 對話方塊的範例，向首度造訪網站的訪客顯示。請記得，此對話方塊的外觀會因為客戶實作不同而有很大差異。

![CMP 對話框](assets/cmp-example.png)

有關IAB TCF v2.0中包括的各種目的和權限的詳細資訊，請參閱[IAB歐洲透明度與同意框架政策](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)。

用戶可以出於多種目的和供應商的考慮，授予其許可或合法利益（如果可用）。 例如，用戶可以授予其在設備上儲存資訊、開發和改進產品的許可，並授予其對CMP展示的所有第三方供應商的許可。

或者，在另一個例子中，它們可以出於所有目的給予其同意或合法利益，但僅授予《議定書》/《公約》締約方會議所展示的少數供應商的同意或合法利益。

當使用者選擇其隱私權選項後，使用者選擇會記錄在IAB TC字串中。 IAB TC字串儲存已核准用途與廠商的組合，以及其他中繼資料資訊（如需詳細資訊，請參閱[IAB頁面](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)）。

在IAB TCF中註冊的每家廠商都會評估IAB TC字串，並根據使用者的隱私權選擇做出決策。 請記住，使用者的隱私權選擇在所有註冊IAB TCF的廠商中都有效。

## Audience Manager{#aam-standard-purposes}所需用途

Audience Manager會根據[IAB歐洲透明度與同意框架政策](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions)中定義的下列目的，評估儲存在IAB TC字串中的使用者選擇。

* **目的1**:在裝置上儲存及／或存取資訊；
* **目的十**:開發和改進產品；
* **特別目的1**:確保安全性、防止詐欺和除錯。

>[!IMPORTANT]
>
>Audience Manager需要通過「目的1」和「目的10」的同意，加上廠商的同意，才能部署Cookie並啟始或遵循ID同步。
>
>根據[IAB規章](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)，特殊用途1（確保安全性、防止欺詐和除錯）一律同意，且使用者無法反對。

## Audience Manager 的行為取決於使用者是否授與同意 {#aam-behavior-consent}

Audience Manager的運作方式視IAB TC字串是否包含使用者同意（儲存和／或存取裝置上的資訊，以及開發和改善產品）而定。

我們也會檢查您在Audience Manager中所使用的所有目的地的使用者同意，只要這些目的地已向IAB TCF註冊。

| 若您的使用者&#x200B;*提供同意*，則 Audience Manager： | 若您的使用者&#x200B;*拒絕*&#x200B;同意，則 Audience Manager： |
|---|---|
| <ul><li>會執行您請求的所有 Audience Manager 使用案例。</li><li>以ID同步傳達對第三方的同意（在ID同步呼叫中以`gdpr_consent`傳遞`gdpr = 1`和同意字串）。</li><li>會評估並遵照從廣告伺服器像素傳遞的同意。</li><li>會執行合作夥伴起始的 ID 同步。</li></ul> | <ul><li>不會在您的例項中儲存任何新使用者資料。這包括合作夥伴 ID、訊號、特徵或像素資料。</li><li>不會起始第三方 ID 同步。</li><li>不會執行合作夥伴起始的 ID 同步。</li><li>將使用者排除在進一步的資料收集之外。</li></ul> |

## 發佈商使用案例 {#publisher-use-case}

透過實作IAB TCF的Audience Manager外掛程式，您不需要透過Adobe或其他第三方廠商的不同機制，在您的Web屬性上維護許可管理的自訂代碼。 下方影像和步驟說明使用案例。從影像左側開始：

1. 使用者造訪您的其中一個 Web 屬性。只要您使用的是最新版 ECID 和 DIL 程式庫 (請參閱[必要條件](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites))，就會觸發選擇加入流程。
2. Audience Manager 會檢查 IAB 流程是否適用 (`isIabContext=true`)。請參閱[建議及實作方式](aam-iab-plugin.md#recommendations)。
3. Audience Manager會檢查GDPR是否適用(`gdpr = 1`)，以及Web屬性上是否有已向IAB TCF註冊的CMP。 例如，這適用於從歐盟造訪的使用者。 請注意，您身為發行者，有責任設定GDPR旗標。
4. 如果適用GDPR,Audience Manager會檢查在`gdpr_consent`參數中傳遞的IAB TC字串，以取得必要的同意。 Audience Manager需要同意將資訊儲存和／或訪問設備（[IAB TCF目的1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)）、開發和改進產品（[IAB TCF目的10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)），以及Audience Manager供應商同意儲存、處理或激活資料。
5. 如果IAB TC字串存在且包含必要的同意，Audience Manager會將IAB TC字串傳遞至我們的[資料收集伺服器](../../reference/system-components/components-data-collection.md)(DCS)。
6. Audience Manager會在瀏覽器上設定[demdex Cookie](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-am.translate.html)來回應，並啟動並接受第三方ID同步。
7. 或者，如果在步驟4中傳遞的IAB TC字串不包含所有必要的權限，則Audience Manager不會收集、處理或啟動任何使用者資料，也不會執行或啟動ID同步。 此外，它還會從您所使用的目的地中剔除使用者。

>[!IMPORTANT]
>
>如果您與需要IAB TCF參數的Audience Manager目標合作夥伴合作，但您的網站上沒有支援IAB TCF的CMP，則Audience Manager會以ID同步方式傳送`gdpr=0`。 這表示GDPR不適用於這些使用者。
>
> 如果不需要，您應啟用Audience Manager中的IAB TCF功能，將適當的IAB TC字串傳送給目標合作夥伴。



![發佈商使用案例](assets/publisher-use-case.png)

## 廣告商使用案例 {#advertiser-use-case}

Audience Manager 會根據 IAB TCF 評估及遵照[像素呼叫](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)中傳遞的同意。

像素可由Audience Manager客戶在其合作夥伴頁面上放置，也可置於廣告伺服器中以納入廣告回應。 在第一種情況下，您的合作夥伴必須以程式設計方式擷取同意參數，並在引發之前將其新增至像素中。而第二種情況中，廣告伺服器會將供應端平台 (SSP) 或發佈商廣告伺服器傳來的同意參數附加至所有像素，這種情況較為常見，將於下文詳細說明。

Audience Manager 使用兩個參數在像素呼叫中傳遞使用者同意：

* `gdpr` 可為 0 (GDPR 不適用) 或1 (GDPR 適用)；
* `gdpr_consent` 是 URL 安全 base64 編碼 GDPR 同意字串 (請參閱[規格](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string))。曝光像素的範例呼叫，這兩個參數可能如下所示：

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

下方影像和步驟說明使用案例。從影像左側開始：

1. 系統會透過廣告伺服器向您的使用者顯示一次曝光內容。這會轉換為對我們的資料收集伺服器(DCS)的[像素呼叫](../../integration/media-data-integration/impression-data-pixels.md)。
2. Audience Manager 會檢查 GDPR 標幟是否適用。如果沒有，Audience Manager會將傳入`gdpr`和`gdpr_consent`變數的資料儲存在像素呼叫中。
3. 如果IAB TC字串存在且包含必要的權限，Audience Manager會將傳入`gdpr`和`gdpr_consent`變數的資料儲存在像素呼叫中。
4. 如果IAB TC字串遺失或缺乏必要的權限，Audience Manager會刪除像素呼叫中傳入`gdpr`和`gdpr_consent`變數的資料。

![廣告商使用案例](assets/advertiser-use-case.png)

## 支援 IAB TCF 的啟用合作夥伴 {#aam-activation-partners}

IAB TCF的Audience Manager外掛程式可讓您將IAB TC字串轉寄給啟動合作夥伴，同時尊重使用者的隱私權選擇。 如需哪些啟用合作夥伴支援 IAB TCF 的詳細資訊，請參閱[以裝置為基礎的目的地清單](/help/using/features/destinations/device-based-destinations-list.md)。

## 將同意附加至傳送至URL目的地的URL

與IAB TCF v2.0的Audience Manager整合支援向與IAB TCF v2.0整合的[URL目標](../../features/destinations/create-url-destination.md)發送的資訊附加同意。不過，此程式不會自動透過Audience Manager完成，以避免中斷特定URL格式。

想要附加同意書至傳送至[!DNL URL destinations]之資料的客戶必須手動將`${GDPR}`和`${GDPR_CONSENT_XXXX}`巨集新增至其URL格式，以目標合作夥伴ID取代`XXXX`。

範例: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

有關支援的目標宏的詳細資訊，請參見[目標宏定義](../../features/destinations/destination-macros.md)。

## 跨裝置同意管理

當您的網站訪客未提供適當的權限時，IAB TCF的Audience Manager外掛程式會自動開啟請求中顯示的ID。 如果請求包含[跨裝置ID(CRM ID)](../../reference/ids-in-aam.md),Audience Manager會將ID與連結至該[跨裝置ID(CRM ID)](../../reference/ids-in-aam.md)的最後一個裝置一起退出。

## 測試您的 IAB 實作 {#test-iab-implementation}

要測試您是否正確實作了IAB TCF的Audience Manager插件，請閱讀[驗證選擇服務的使用案例4](https://docs.adobe.com/content/help/zh-Hant/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.translate.html#section-64331998954d4892960dcecd744a6d88)。

## IAB 和 Audience Manager 中的選擇退出。優先順序。{#iab-and-optout}

使用者可以選擇另一個隱私權選項，即選擇退出所有資料收集。Adobe 會在[您的隱私權選擇](https://www.adobe.com/tw/privacy/opt-out.html)頁面中提供使用者執行此作業的選項。

Audience Manager 處理選擇退出請求的方式，於[文件中的另一篇文章](data-privacy-requests.md#opt-out-requests)中說明。

>[!IMPORTANT]
>
>在拒絕同意後選擇退出所有資料收集的使用者，無法選擇返回。

>[!NOTE]
>
>**優先順序** - 如果您的使用者使用全域選擇退出工具來選擇退出資料收集，如上述連結所述，此選擇優先於選擇加入和 IAB 驗證。

## 其他資源 {#additional-resources}

* [Adobe Experience Platform Identity Service 選擇加入](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB 歐洲 GDPR 資訊公開與同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB 歐洲 GDPR 資訊公開與同意框架技術規格](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF 外掛程式 - 影片示範](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)