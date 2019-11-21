---
description: 本檔案說明同意管理在Audience manager中的運作方式。
seo-description: 本檔案說明同意管理在Audience manager中的運作方式。
seo-title: 許可管理
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: 許可管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: fbe4e8c912093c495f27ca887a44ac31d394811a

---


# 許可管理

## 概述 {#overview}

在某些行銷活動需要同意的情況下，消費者同意必須有效（例如，沒有預先核取的方塊或預設）、未打包及提供服務不得以「資料主體」給予同意為條件。 有時甚至需要重新整理某些同意，才能繼續使用後續的資料。

Audience manager為您提供必要的工具，讓您獲得用戶的同意，以便您能夠跨通道向用戶提供個人化體驗。

>[!IMPORTANT]
>
> 本檔案內容不是法律咨詢，不是代替法律咨詢。
>
> 身為資料處理者，Adobe無法就取得同意提供法律建議。 我們建議您與同意管理解決方案供應商(例如 [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 或 [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/))合作，以取得最佳建議，並在設定選擇加入實施時諮詢您公司的法律部門，以取得有關同意和做法的建議。

## Experience cloud選擇加入服務

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) service lets you set up protocols for the visitor to determine if you can set a cookie on the user's device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

Experience cloud選 [](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) 擇加入服務也可讓您設定通訊協定，以整合您的同意管理平台(CMP)和現有系統，做為大型設計的一部分。

## 管理選擇加入／取得同意

Audience manager客戶可將廣告或個人化等不同使用案例的使用者同意儲存為Audience Manager中的特徵。 然後，建立具有這些特徵的區段時，將只包含針對每個使用案例提供個別同意的使用者。 請注意，使用此方法不會停止資料收集，但只會在您傳送要啟動的區段時影響資料的使用。 當使用者撤回其同意時，您可以使用傳入的Audience Manager批次程式或Audience manager選擇退出程式，從使用者個人檔案中移除這些特徵 [](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) ，如下所述。

## 管理退出／撤回同意

您可透過「您的隱私權選擇」頁面，管理Adobe Experience cloud的 [退出選項](https://www.adobe.com/privacy/opt-out.html#customeruse) 。 單鍵功能可讓您的使用者控制Adobe Experience cloud廣告解決方案（包括Audience Manager）收集的資料，並選擇退出。 具體而言，請參 [閱「隱私權選擇](https://www.adobe.com/privacy/opt-out.html#customeruse) 」頁面的「企業客戶」一節。 若為不支援協力廠商Cookie的瀏覽器，請參閱「宣告 [的ID定位」](../../features/declared-ids.md#declared-id-targeting)。 若為行動裝置，請擷取相關的Audience manager識別碼，並呼叫Audience Manager退出API，如「宣告的ID退出」 [範例所述](../../features/declared-ids.md#opt-out-examples)。 之後，您就可以使用Mobile SDK的退出API停止這些使用者的所有資料收集——請參閱 [Android裝置](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html)[和iOS裝置](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)。 您可在資料隱私權要求檔案中找到其 [他退出的詳細資訊](../../overview/data-security-and-privacy/data-privacy-requests.md)。

## 管理第二方資料提供者的同意

第二方資料提供者通常也是資料掌控者，並擁有從資料主體取得任何必要同意的程式，以便與其第二方資料合作夥伴共用資料。 您身為Audience Manager客戶，有責任判斷第二方資料提供者是否已取得您使用案例的必要同意。 有關取得同意的詳細資訊，請參閱上文。

## 管理第三方資料提供者的同意

第三方資料提供者也是資料掌控者，擁有取得同意及管理存取／刪除／更正要求的程式。 Adobe主動要求資料提供者在 [](https://www.adobe-audience-finder.com/) Adobe Audience Finder中更新其公司個人檔案資訊，並提供使用者資料收集的其他資訊。 資訊將來自資料提供者，並定期更新。 但是，由每位Audience manager客戶決定第三方資料提供者已取得該客戶使用案例的必要同意。 Adobe不就第三方資料供應商針對特定使用案例所取得或報告之同意之範圍或效力提出任何陳述。
