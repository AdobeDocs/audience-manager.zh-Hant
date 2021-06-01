---
description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-title: 適用於 IAB TCF 的 Audience Manager 外掛程式
solution: Audience Manager
title: 適用於 IAB TCF 的 Audience Manager 外掛程式
feature: 資料控管與隱私權
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 40%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## 概述

您對使用者可能承擔的隱私權義務中，有一個重要方面是針對如何使用其個人資料（即「目的」）以及由誰使用（即「公司」），取得並傳達使用者的選擇。

Adobe 可讓您透過[選擇加入功能](https://docs.adobe.com/content/help/zh-Hant/id-service/using/implementation/opt-in-service/optin-overview.translate.html)和 [IAB 透明與同意架構 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。

本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。

>[!IMPORTANT]
>
>Audience Manager在[IAB TCF](https://iabeurope.eu/tcf-for-vendors/)中註冊，廠商ID為565。

適用於 IAB TCF 的 Audience Manager 外掛程式採用[選擇加入功能](https://docs.adobe.com/content/help/zh-Hant/id-service/using/implementation/opt-in-service/iab.html)，而這又是 [ Experience Platform Identity Service (ECID)](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html) 程式庫的一部分。

## 範圍和限制 {#scope-and-limitations}

身為使用 Audience Manager 的發佈商或廣告商，您可以依據 IAB TCF 向 Audience Manager 傳達使用者的選擇。

>[!IMPORTANT]
>
>IAB TCF法規僅適用於位於歐洲經濟區的訪客。

Audience Manager可協助您尊重使用者的隱私權選擇，並提供您與所有合作夥伴溝通的簡單方式。

目前 Audience Manager 不支援：

* 行動裝置工作流程；
* 將同意附加至區段匯出。

## 升級為 [!DNL IAB TCF v2.0] {#upgrading}

客戶若要將其[!DNL Audience Manager Plug-in for IAB TCF]實作從[!DNL IAB TCF] v1.1升級為[!DNL IAB TCF] v2.0，或首次啟用[!DNL IAB TCF] v2.0，應按照下列說明遵循相同的先決條件和實作准則。

## 必要條件 {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager支援IAB TCF v2.0。
>
>IAB TCF v1.1支援將於2020年8月15日終止。
>
> 若客戶想繼續使用適用於IAB TCF的Audience Manager外掛程式來管理同意，請升級至[ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)的最新版本，以繼續提供支援。
>
> 升級至最新的[ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)版本後，將不再支援IAB TCF v1.1同意字串，因此請務必更新CMP，再升級至最新的ECID版本。

您必須符合下列必要條件，才能搭配Audience Manager使用適用於IAB TCF的Audience Manager外掛程式：

1. 您必須使用 Adobe Experience Platform Identity Service (ECID) 5 或更新版本。[下載](https://github.com/Adobe-Marketing-Cloud/id-service/releases)最新版 ECID。
2. 您必須使用Audience Manager[!DNL Data Integration Library](DIL)9.0版或更新版本，可從[此處](https://github.com/Adobe-Marketing-Cloud/dil/releases)下載。 閱讀 [Audience Manager 中的 DIL 文件](../../dil/dil-overview.md)。建議您使用[AdobeLaunch](https://docs.adobe.com/content/help/zh-Hant/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html)，以進行最簡單的Audience ManagerDIL實作。
3. 或者，如果您使用[!DNL Server-Side Forwarding](SSF)將資料匯入Audience Manager，則必須升級至最新版的AppMeasurement。 使用 [Analytics 代碼管理器](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-tools/code-manager-admin.translate.html)下載 AppMeasurement。
4. 您必須使用與IAB TCF v2.0整合且已向IAB TCF註冊的同意管理平台(CMP)，商業版或自有版皆可。 請參閱[在 IAB 框架內註冊的 CMP](https://iabeurope.eu/cmp-list/) 清單。

>[!WARNING]
>
>如果您使用不支援IAB TCF v.2.0的同意管理平台(CMP)，即使您的訪客身在歐盟，Audience Manager仍會以ID同步自動傳送`gdpr=0`參數。 若要判斷您的GDPR驗證是否有效，建議您向同意管理平台(CMP)確認其支援IAB TCF v2.0。

## 建議及實作方式 {#recommendations}

若要在 Audience Manager 中啟用 IAB TCF 支援，請參閱[如何透過選擇加入設定 IAB](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html) 文件。

最簡單的做法是使用[Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html)在您的屬性上新增[!DNL ECID Opt-in]。 請參閱 [ECID 選擇加入擴充功能](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html)文件，瞭解如何設定 Launch 擴充功能。

## 使用 IAB 架構時的使用者選擇工作流程 {#user-choice-workflow}

造訪 Web 屬性時，您的使用者可以選擇提供其資料供發佈商及與發佈商合作的第三方廠商使用。

使用者針對IAB目的，提供&#x200B;*同意*&#x200B;和&#x200B;*合法利益*&#x200B;形式的選擇給全域廠商清單中註冊的&#x200B;*第三方廠商*。

下圖呈現 CMP 對話方塊的範例，向首度造訪網站的訪客顯示。請記得，此對話方塊的外觀會因為客戶實作不同而有很大差異。

![CMP 對話框](assets/cmp-example.png)

[ IAB歐洲透明與同意架構政策](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)中涵蓋IAB TCF v2.0中各種用途和權限的詳細資訊。

使用者可出於目的與廠商的組合，授與其同意或合法利益（若有）。 例如，使用者可授予在裝置上儲存資訊的同意、開發和改善產品，以及授與CMP所顯示之所有協力廠商的同意。

或者，在另一個例子中，他們可針對所有用途授予其同意或合法利益，但只授予CMP所顯示的少數廠商同意或合法利益。

使用者選取其隱私權選擇後，使用者選擇便會記錄在IAB TC字串中。 IAB TC字串會儲存已核准用途與廠商的組合，以及其他中繼資料資訊（如需詳細資訊，請參閱[ IAB頁面](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)）。

在IAB TCF中註冊的每家廠商都會評估IAB TC字串，並根據使用者的隱私權選擇做出決策。 請記得，使用者的隱私權選擇在所有透過IAB TCF註冊的廠商中都有效。

## 按Audience Manager{#aam-standard-purposes}要求的用途

Audience Manager會針對[IAB歐洲透明與同意架構原則](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions)中定義的下列用途，評估儲存在IAB TC字串中的使用者選擇。

* **目的一**:在設備上儲存和/或訪問資訊；
* **目的** 10:開發和改進產品；
* **特殊目的1**:確保安全性、防止欺詐和調試。

>[!IMPORTANT]
>
>Audience Manager需要目的1和10的同意，加上廠商同意，才能部署Cookie，並初始化或執行ID同步。
>
>根據[IAB法規](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)，特殊用途1（確保安全性、防止欺詐和除錯）一律同意，且使用者無法反對。

## Audience Manager 的行為取決於使用者是否授與同意 {#aam-behavior-consent}

Audience Manager的運作方式會因IAB TC字串是否包含兩個用途（儲存和/或存取裝置上的資訊，以及開發和改良產品）的使用者同意而有所不同。

只要您在Audience Manager中使用的所有目的地已註冊IAB TCF，我們也會檢查這些目的地的使用者同意情形。

| 若您的使用者&#x200B;*提供同意*，則 Audience Manager： | 若您的使用者&#x200B;*拒絕*&#x200B;同意，則 Audience Manager： |
|---|---|
| <ul><li>會執行您請求的所有 Audience Manager 使用案例。</li><li>以ID同步傳達對第三方的同意（透過在ID同步呼叫上傳遞`gdpr = 1`和以`gdpr_consent`傳遞同意字串）。</li><li>會評估並遵照從廣告伺服器像素傳遞的同意。</li><li>會執行合作夥伴起始的 ID 同步。</li></ul> | <ul><li>不會在您的例項中儲存任何新使用者資料。這包括合作夥伴 ID、訊號、特徵或像素資料。</li><li>不會起始第三方 ID 同步。</li><li>不會執行合作夥伴起始的 ID 同步。</li><li>將使用者退出進一步的資料收集。</li></ul> |

## 發佈商使用案例 {#publisher-use-case}

借由實作適用於IAB TCF的Audience Manager外掛程式，您不需要透過Adobe或其他協力廠商的不同機制，維護您Web屬性上同意管理的自訂程式碼。 下方影像和步驟說明使用案例。從影像左側開始：

1. 使用者造訪您的其中一個 Web 屬性。只要您使用的是最新版 ECID 和 DIL 程式庫 (請參閱[必要條件](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites))，就會觸發選擇加入流程。
2. Audience Manager 會檢查 IAB 流程是否適用 (`isIabContext=true`)。請參閱[建議及實作方式](aam-iab-plugin.md#recommendations)。
3. Audience Manager會檢查GDPR是否適用(`gdpr = 1`)，以及您的Web屬性上是否有已向IAB TCF註冊的CMP。 例如，這適用於來自歐盟的造訪使用者。 請注意，您身為發佈商，有責任設定GDPR標幟。
4. 如果GDPR適用，Audience Manager會檢查傳入`gdpr_consent`參數的IAB TC字串，以取得必要的同意。 Audience Manager需要儲存和/或存取裝置上的資訊（[IAB TCF用途1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)）、開發和改良產品（[IAB TCF用途10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)）的同意，加上Audience Manager廠商對儲存、處理或啟用資料的同意。
5. 如果IAB TC字串存在且包含必要的同意，Audience Manager會將IAB TC字串傳遞至的[資料收集伺服器](../../reference/system-components/components-data-collection.md)(DCS)。
6. Audience Manager在瀏覽器上設定[demdex cookie](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-am.translate.html)來回應，並起始並執行第三方ID同步。
7. 或者，如果在步驟4傳遞的IAB TC字串不包含所有需要的權限，Audience Manager就不會收集、處理或啟用任何使用者資料，也不會執行或起始ID同步。 此外，它也會從您使用的目的地中選擇使用者。

>[!IMPORTANT]
>
>如果您與需要IAB TCF參數的Audience Manager目的地合作夥伴合作，但您的網站上沒有支援IAB TCF的CMP，則Audience Manager會以ID同步方式傳送`gdpr=0`。 這表示GDPR不適用於這些使用者。
>
> 如果不需要，您應在Audience Manager中啟用IAB TCF功能，將適當的IAB TC字串傳送至目的地合作夥伴。



![發佈商使用案例](assets/publisher-use-case.png)

## 廣告商使用案例 {#advertiser-use-case}

Audience Manager 會根據 IAB TCF 評估及遵照[像素呼叫](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)中傳遞的同意。

像素可由Audience Manager客戶在其合作夥伴頁面上放置，或置於廣告伺服器中以納入廣告回應。 在第一種情況下，您的合作夥伴必須以程式設計方式擷取同意參數，並在引發之前將其新增至像素中。而第二種情況中，廣告伺服器會將供應端平台 (SSP) 或發佈商廣告伺服器傳來的同意參數附加至所有像素，這種情況較為常見，將於下文詳細說明。

Audience Manager 使用兩個參數在像素呼叫中傳遞使用者同意：

* `gdpr` 可為 0 (GDPR 不適用) 或1 (GDPR 適用)；
* `gdpr_consent` 是 URL 安全 base64 編碼 GDPR 同意字串 (請參閱[規格](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string))。曝光像素的範例呼叫，這兩個參數可能如下所示：

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

下方影像和步驟說明使用案例。從影像左側開始：

1. 系統會透過廣告伺服器向您的使用者顯示一次曝光內容。這會轉譯為[像素呼叫](../../integration/media-data-integration/impression-data-pixels.md)至我們的資料收集伺服器(DCS)。
2. Audience Manager 會檢查 GDPR 標幟是否適用。若未包含，則Audience Manager會儲存像素呼叫中傳入`gdpr`和`gdpr_consent`變數的資料。
3. 如果IAB TC字串存在且包含必要的權限，Audience Manager會儲存像素呼叫中`gdpr`和`gdpr_consent`變數所傳遞的資料。
4. 如果IAB TC字串遺失或缺少必要的權限，Audience Manager會捨棄像素呼叫中`gdpr`和`gdpr_consent`變數所傳遞的資料。

![廣告商使用案例](assets/advertiser-use-case.png)

## 支援 IAB TCF 的啟用合作夥伴 {#aam-activation-partners}

適用於IAB TCF的Audience Manager外掛程式可讓您將IAB TC字串轉送給啟用合作夥伴，同時接受使用者的隱私權選擇。 如需哪些啟用合作夥伴支援 IAB TCF 的詳細資訊，請參閱[以裝置為基礎的目的地清單](/help/using/features/destinations/device-based-destinations-list.md)。

## 將同意附加至傳送至URL目的地的URL

與IAB TCF v2.0的Audience Manager整合支援對傳送至與IAB TCF v2.0整合之[URL目的地](../../features/destinations/create-url-destination.md)的資訊附加同意。不過，此程式不會透過Audience Manager自動完成，以避免中斷特定URL格式。

想要將同意附加至傳送至[!DNL URL destinations]的資料的客戶必須手動將`${GDPR}`和`${GDPR_CONSENT_XXXX}`巨集新增至其URL格式，並以目標合作夥伴ID取代`XXXX`。

範例: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

有關支援的目標宏的詳細資訊，請參閱[定義的目標宏](../../features/destinations/destination-macros.md)。

## 跨裝置同意管理

適用於IAB TCF的Audience Manager外掛程式會在您的網站訪客未提供適當權限時，自動選出請求上顯示的ID。 如果請求包含[跨裝置ID(CRM ID)](../../reference/ids-in-aam.md),Audience Manager會選出該ID，連結至該[跨裝置ID(CRM ID)](../../reference/ids-in-aam.md)的最後一個裝置。

## 測試您的 IAB 實作 {#test-iab-implementation}

若要測試您是否已正確實作適用於IAB TCF的Audience Manager外掛程式，請參閱驗證選擇加入服務](https://docs.adobe.com/content/help/zh-Hant/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.translate.html#section-64331998954d4892960dcecd744a6d88)中的[使用案例4。

## IAB 和 Audience Manager 中的選擇退出。優先順序。{#iab-and-optout}

使用者可以選擇另一個隱私權選項，即選擇退出所有資料收集。Adobe 會在[您的隱私權選擇](https://www.adobe.com/tw/privacy/opt-out.html)頁面中提供使用者執行此作業的選項。

Audience Manager 處理選擇退出請求的方式，於[文件中的另一篇文章](data-privacy-requests.md#opt-out-requests)中說明。

>[!IMPORTANT]
>
>拒絕同意後，選擇退出所有資料收集的使用者無法再選擇加入。

>[!NOTE]
>
>**優先順序** - 如果您的使用者使用全域選擇退出工具來選擇退出資料收集，如上述連結所述，此選擇優先於選擇加入和 IAB 驗證。

## 其他資源 {#additional-resources}

* [Adobe Experience Platform Identity Service 選擇加入](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB 歐洲 GDPR 資訊公開與同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB 歐洲 GDPR 資訊公開與同意框架技術規格](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF 外掛程式 - 影片示範](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
