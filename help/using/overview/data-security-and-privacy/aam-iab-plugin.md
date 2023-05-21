---
description: Adobe 可讓您透過選擇加入功能和 IAB 透明與同意架構 (TCF)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。
seo-description: Adobe provides you with the means to manage and communicate your users' privacy choices through the Opt-in functionality and through IAB Transparency and Consent Framework (TCF) support. This article describes the Audience Manager use cases that support the IAB TCF and how to implement IAB TCF support in Audience Manager.
seo-title: Audience Manager Plug-in for IAB TCF
solution: Audience Manager
title: 適用於 IAB TCF 的 Audience Manager 外掛程式
feature: Data Governance & Privacy
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '2367'
ht-degree: 34%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## 概述

在您對用戶可能承擔的隱私義務中，一個重要方面是獲取和傳遞用戶對如何使用其個人資料（即「目的」）和由誰（即「公司」）的選擇。

Adobe 可讓您透過[選擇加入功能](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)和 [IAB 透明與同意架構 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)，管理使用者的隱私權選擇，並與使用者針對該選擇溝通。

本文說明支援 IAB TCF 的 Audience Manager 使用案例，講解如何在 Audience Manager 中實作 IAB TCF 支援。

>[!IMPORTANT]
>
>Audience Manager在 [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) 供應商ID為565。

適用於 IAB TCF 的 Audience Manager 外掛程式採用[選擇加入功能](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html)，而這又是 [ Experience Platform Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html) 程式庫的一部分。

## 範圍和限制 {#scope-and-limitations}

身為使用 Audience Manager 的發佈商或廣告商，您可以依據 IAB TCF 向 Audience Manager 傳達使用者的選擇。

>[!IMPORTANT]
>
>IAB TCF條例僅適用於位於歐洲經濟區的遊客。

Audience Manager可幫助您尊重用戶的隱私選擇，還為您提供了一種簡單的方法，讓您能夠將這些選擇與與您合作的所有合作夥伴進行交流。

目前 Audience Manager 不支援：

* 行動裝置工作流程；
* 附上對分部出口的同意。

## 升級為 [!DNL IAB TCF v2.0] {#upgrading}

升級客戶 [!DNL Audience Manager Plug-in for IAB TCF] 實施 [!DNL IAB TCF] v1.1至 [!DNL IAB TCF] v2.0或啟用 [!DNL IAB TCF] v2.0首次應遵循與下文所述有關先決條件和實施的相同准則。

## 必要條件 {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager支援IAB TCF v2.0。
>
>IAB TCF v1.1支援將於2020年8月15日結束。
>
> 如果客戶希望繼續使用IAB TCF的Audience Manager插件進行許可管理，則應升級到 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 繼續支援。
>
> 升級到最新 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 版本，將不再支援IAB TCF v1.1同意字串，因此請確保在升級到最新ECID版本之前更新CMP。

您必須滿足以下先決條件才能將IAB TCF的Audience Manager插件與Audience Manager一起使用：

1. 您必須使用 Adobe Experience Platform Identity Service (ECID) 5 或更新版本。[下載](https://github.com/Adobe-Marketing-Cloud/id-service/releases)最新版 ECID。
2. 您必須使用Audience Manager [!DNL Data Integration Library] (DIL)9.0版或更高版本，可從 [這裡](https://github.com/Adobe-Marketing-Cloud/dil/releases)。 閱讀 [Audience Manager 中的 DIL 文件](../../dil/dil-overview.md)。建議使用 [Adobe Audience Manager標籤擴展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 最簡單的DILAudience Manager。
3. 或者，如果您 [!DNL Server-Side Forwarding] (SSF)要將資料導入Audience Manager，必須升級到最新版本的AppMeasurement。 使用 [Analytics 代碼管理器](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html)下載 AppMeasurement。
4. 您必須使用與IAB TCF v2.0整合併在IAB TCF中註冊的「同意管理平台」(CMP)，無論是商業版還是您自己的版本。 請參閱[在 IAB 框架內註冊的 CMP](https://iabeurope.eu/cmp-list/) 清單。

>[!WARNING]
>
>如果您使用的是不支援IAB TCF v.2.0的同意管理平台(CMP),Audience Manager將自動發送 `gdpr=0` ID同步中的參數，即使訪問者在歐盟。 要確定您的GDPR驗證是否處於活動狀態，我們建議您通過您的同意管理平台(CMP)確認他們支援IAB TCF v2.0。

## 建議及實作方式 {#recommendations}

若要在 Audience Manager 中啟用 IAB TCF 支援，請參閱[如何透過選擇加入設定 IAB](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html) 文件。

最簡單的方法是 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) 添加 [!DNL ECID Opt-in] 你的財產。 閱讀文檔 [ECID選擇加入擴展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) 瞭解如何設定標籤擴展。

## 使用 IAB 架構時的使用者選擇工作流程 {#user-choice-workflow}

造訪 Web 屬性時，您的使用者可以選擇提供其資料供發佈商及與發佈商合作的第三方廠商使用。

用戶以以下形式提供其選擇 *同意* 和 *合法利益* 以便IAB *第三方供應商* 在全局供應商清單中註冊。

下圖呈現 CMP 對話方塊的範例，向首度造訪網站的訪客顯示。請記得，此對話方塊的外觀會因為客戶實作不同而有很大差異。

![CMP 對話框](assets/cmp-example.png)

有關IAB TCF v2.0中包括的各種目的和權限的詳細資訊，請參閱 [IAB歐洲透明度和同意框架政策](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)。

用戶可以出於目的和供應商的組合而同意或合法利益（如果有）。 例如，用戶可以同意將資訊儲存在設備上、開發和改進產品，並可以同意CMP顯示的所有第三方供應商。

或者，在另一個例子中，它們可以出於所有目的給予其同意或合法利益，但只給予《議定書》/《公約》締約方會議所展示的少數供應商同意或合法利益。

一旦用戶選擇其隱私選擇，則用戶選擇被記錄在IAB TC字串中。 IAB TC字串儲存已批准用途和供應商的組合以及其他元資料資訊(請參見 [IAB頁](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) )的正平方根。

在IAB TCF中註冊的每個供應商都評估IAB TC字串並根據用戶的隱私選擇做出決策。 請記住，用戶的隱私選擇在所有註冊到IAB TCF的供應商中都有效。

## 按Audience Manager要求的目的 {#aam-standard-purposes}

Audience Manager為以下目的評估儲存在IAB TC字串中的用戶選擇，如 [IAB歐洲透明度和同意框架政策](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions)。

* **用途1**:在設備上儲存和/或訪問資訊；
* **用途10**:開發和改進產品；
* **特殊用途1**:確保安全性、防止欺詐和調試。

>[!IMPORTANT]
>
>Audience Manager需要獲得目的1和目的10的同意，加上供應商的同意，才能部署cookie並啟動或遵守ID同步。
>
>每 [IAB條例](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)、特殊目的1（確保安全性、防止欺詐和調試）始終是同意的，用戶不能對此提出異議。

## Audience Manager 的行為取決於使用者是否授與同意 {#aam-behavior-consent}

Audience Manager的工作方式不同，具體取決於IAB TC字串是否包括用戶同意用於兩個目的（儲存和/或訪問設備上的資訊，以及開發和改進產品）。

我們還檢查您在Audience Manager中工作的所有目的地的用戶同意，只要這些目的地已註冊到IAB TCF。

| 若您的使用者&#x200B;*提供同意*，則 Audience Manager： | 若您的使用者&#x200B;*拒絕*&#x200B;同意，則 Audience Manager： |
|---|---|
| <ul><li>會執行您請求的所有 Audience Manager 使用案例。</li><li>以ID同步向第三方傳達同意(通過 `gdpr = 1` 同意字串為 `gdpr_consent` 在ID同步調用上)。</li><li>會評估並遵照從廣告伺服器像素傳遞的同意。</li><li>會執行合作夥伴起始的 ID 同步。</li></ul> | <ul><li>不會在您的例項中儲存任何新使用者資料。這包括合作夥伴 ID、訊號、特徵或像素資料。</li><li>不會起始第三方 ID 同步。</li><li>不會執行合作夥伴起始的 ID 同步。</li><li>從進一步的資料收集中選出用戶。</li></ul> |

## 發佈商使用案例 {#publisher-use-case}

通過實施IAB TCF的Audience Manager插件，您無需通過與Adobe或其他第三方供應商的不同機制在您的Web屬性上維護同意管理的自定義代碼。 下方影像和步驟說明使用案例。從影像左側開始：

1. 使用者造訪您的其中一個 Web 屬性。只要您使用的是最新版 ECID 和 DIL 程式庫 (請參閱[必要條件](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites))，就會觸發選擇加入流程。
2. Audience Manager 會檢查 IAB 流程是否適用 (`isIabContext=true`)。請參閱[建議及實作方式](aam-iab-plugin.md#recommendations)。
3. Audience Manager檢查GDPR是否適用(`gdpr = 1`)以及您的web屬性上是否有註冊到IAB TCF的CMP。 例如，這將適用於從歐洲聯盟訪問的用戶。 請注意，作為發佈者，您有責任設定GDPR標誌。
4. 如果應用GDPR,Audience Manager將檢查傳入的IAB TC字串 `gdpr_consent` 參數。 Audience Manager需要同意在設備上儲存和/或訪問資訊([IAB TCF用途1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes))、開發及改進產品([IAB TCF用途10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes))，加上Audience Manager供應商同意儲存、處理或激活資料。
5. 如果IAB TC字串存在且包含所需的同意，則Audience Manager將IAB TC字串傳遞給我們 [資料收集伺服器](../../reference/system-components/components-data-collection.md) (DCS)。
6. Audience Manager通過設定 [德克斯餅乾](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) 在瀏覽器上啟動並執行第三方ID同步。
7. 或者，如果步驟4中傳遞的IAB TC字串不包含所有所需權限，則Audience Manager不會收集、處理或激活任何用戶資料，也不會執行或啟動ID同步。 此外，它還從您所使用的目標中選擇用戶。

>[!IMPORTANT]
>
>如果您正在與需要IAB TCF參數的Audience Manager目標合作夥伴合作，但您的網站上沒有支援IAB TCF的CMP，則Audience Manager會發送 `gdpr=0` 中。 這意味著GDPR不適用於這些用戶。
>
> 如果不需要，您應啟用Audience Manager中的IAB TCF功能，以將相應的IAB TC字串發送到目標合作夥伴。



![發佈商使用案例](assets/publisher-use-case.png)

## 廣告商使用案例 {#advertiser-use-case}

Audience Manager 會根據 IAB TCF 評估及遵照[像素呼叫](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)中傳遞的同意。

像素可由Audience Manager客戶在其合作夥伴頁面上放置，或者被放置在廣告伺服器中以包括在廣告響應中。 在第一種情況下，您的合作夥伴必須以程式設計方式擷取同意參數，並在引發之前將其新增至像素中。而第二種情況中，廣告伺服器會將供應端平台 (SSP) 或發佈商廣告伺服器傳來的同意參數附加至所有像素，這種情況較為常見，將於下文詳細說明。

Audience Manager 使用兩個參數在像素呼叫中傳遞使用者同意：

* `gdpr` 可為 0 (GDPR 不適用) 或1 (GDPR 適用)；
* `gdpr_consent` 是 URL 安全 base64 編碼 GDPR 同意字串 (請參閱[規格](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string))。曝光像素的範例呼叫，這兩個參數可能如下所示：

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

下方影像和步驟說明使用案例。從影像左側開始：

1. 系統會透過廣告伺服器向您的使用者顯示一次曝光內容。這就意味著 [像素調用](../../integration/media-data-integration/impression-data-pixels.md) 資料收集伺服器(DCS)。
2. Audience Manager 會檢查 GDPR 標幟是否適用。否則，Audience Manager將儲存在 `gdpr` 和 `gdpr_consent` 像素調用中的變數。
3. 如果IAB TC字串存在且包含所需權限，則Audience Manager儲存在 `gdpr` 和 `gdpr_consent` 像素調用中的變數。
4. 如果IAB TC字串缺失或缺少所需權限，Audience Manager將刪除在 `gdpr` 和 `gdpr_consent` 像素調用中的變數。

![廣告商使用案例](assets/advertiser-use-case.png)

## 支援 IAB TCF 的啟用合作夥伴 {#aam-activation-partners}

IAB TCF的Audience Manager插件使您能夠將IAB TC字串轉發給激活夥伴，同時尊重用戶的隱私選擇。 如需哪些啟用合作夥伴支援 IAB TCF 的詳細資訊，請參閱[以裝置為基礎的目的地清單](/help/using/features/destinations/device-based-destinations-list.md)。

## 將同意添加到發送到URL目標的URL

與IAB TCF v2.0的Audience Manager整合支援對發送到 [URL目標](../../features/destinations/create-url-destination.md) 與IAB TCF v2.0整合。但是，此過程不會通過Audience Manager自動完成，以避免中斷特定URL格式。

希望向發送到的資料追加同意的客戶 [!DNL URL destinations] 必須手動添加 `${GDPR}` 和 `${GDPR_CONSENT_XXXX}` 宏到其URL格式，替換 `XXXX` 目標合作夥伴ID。

範例: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

請參閱 [定義的目標宏](../../features/destinations/destination-macros.md) 的子菜單。

## 跨設備同意管理

IAB TCF的Audience Manager插件會在您的站點訪問者未提供適當權限時自動選擇請求中存在的ID。 如果請求包含 [跨設備ID(CRM ID)](../../reference/ids-in-aam.md),Audience Manager會開啟ID，以及連結到該ID的最後一個設備 [跨設備ID(CRM ID)](../../reference/ids-in-aam.md)。

## 測試您的 IAB 實作 {#test-iab-implementation}

要test已正確實現IAB TCF的Audience Manager插件，請閱讀 [驗證選擇加入服務時使用案例4](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88)。

## IAB 和 Audience Manager 中的選擇退出。優先順序。 {#iab-and-optout}

使用者可以選擇另一個隱私權選項，即選擇退出所有資料收集。Adobe 會在[您的隱私權選擇](https://www.adobe.com/tw/privacy/opt-out.html)頁面中提供使用者執行此作業的選項。

Audience Manager 處理選擇退出請求的方式，於[文件中的另一篇文章](data-privacy-requests.md#opt-out-requests)中說明。

>[!IMPORTANT]
>
>在拒絕同意後被選擇不參與所有資料收集的用戶不能被選擇重新加入。

>[!NOTE]
>
>**優先順序** - 如果您的使用者使用全域選擇退出工具來選擇退出資料收集，如上述連結所述，此選擇優先於選擇加入和 IAB 驗證。

## 其他資源 {#additional-resources}

* [Adobe Experience Platform Identity Service 選擇加入](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB 歐洲 GDPR 資訊公開與同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB 歐洲 GDPR 資訊公開與同意框架技術規格](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF 外掛程式 - 影片示範](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
