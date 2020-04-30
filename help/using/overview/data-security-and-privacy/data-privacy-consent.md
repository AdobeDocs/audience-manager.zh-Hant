---
description: 本檔案說明同意管理在Audience Manager中的運作方式。
seo-description: 本檔案說明同意管理在Audience Manager中的運作方式。
seo-title: 許可管理
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: 許可管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 許可管理

## 概述 {#overview}

在某些行銷活動需要同意的情況下，Audience Manager客戶必須決定範圍和特定同意，以及是否需要重新整理某些同意才能繼續使用未來的資料。

Audience Manager提供您多種工具，協助您從使用者處取得必要同意，以便透過各個通道為他們提供個人化體驗。

>[!IMPORTANT]
>
> 本檔案內容不是法律咨詢，不是代替法律咨詢。
>
> 身為資料處理者，Adobe無法就取得同意提供法律建議。 您也可以考慮與許可管理解決方案供應商(例如 [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 或 [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/))合作，並在設定您的選擇性實施時，請洽詢貴公司的法律部門，以取得有關許可和慣例的建議。

## Experience Cloud選擇加入服務

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) lets you set up protocols for the visitor to assist you in determining if you can set a cookie on the individual&#39;s device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

Experience Cloud選 [](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) 擇加入服務也可讓您設定通訊協定，以整合您的同意管理平台(CMP)和現有系統，做為大型設計的一部分。

## 管理選擇加入／取得同意

Audience Manager客戶能夠針對各種使用案例（例如廣告或個人化）將使用者同意儲存為Audience Manager中的特徵。 然後，您使用這些特徵建立的區段將僅包含針對每個使用案例提供個別同意的使用者。 請注意，使用此方法不會停止資料收集，但只會在您傳送要啟動的區段時影響資料的使用。 當使用者撤回其同意時，您可以使用傳入的Audience Manager批次程式或Audience Manager選擇退出程式，從使用者個人檔案中移除這些特徵 [](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) ，如下所述。

## 管理退出／撤回同意

您可透過「您的隱私權選項」頁面，管理Adobe Experience Cloud的 [退出選項](https://www.adobe.com/privacy/opt-out.html#customeruse) 。 單鍵功能可讓您的使用者控制Adobe Experience Cloud廣告解決方案（包括Audience Manager）的資料收集，並選擇退出。 具體而言，請參 [閱「隱私權選擇](https://www.adobe.com/privacy/opt-out.html#customeruse) 」頁面的「企業客戶」一節。 若為不支援協力廠商Cookie的瀏覽器，請參閱「宣告 [的ID定位」](../../features/declared-ids.md#declared-id-targeting)。 若為行動裝置，請擷取相關的Audience Manager識別碼，並呼叫Audience Manager退出API，如「宣告的ID退出」 [範例所述](../../features/declared-ids.md#opt-out-examples)。 之後，您就可以使用Mobile SDK的退出API停止這些使用者的所有資料收集——請參閱 [Android裝置](https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html)[和iOS裝置](https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html)。 您可在資料隱私權要求檔案中找到其 [他退出的詳細資訊](../../overview/data-security-and-privacy/data-privacy-requests.md)。

## 管理第二方合作夥伴的同意

第二方合作夥伴通常也是資料掌控者，並擁有從資料主體取得任何必要同意的程式，以便與其第二方資料合作夥伴共用資料。 您身為Audience Manager客戶，有責任判斷第二方合作夥伴是否已取得您使用案例的必要同意。 有關取得同意的詳細資訊，請參閱上文。

## 管理Audience Marketplace第三方合作夥伴的同意

Audience Marketplace第三方合作夥伴也是資料掌控者，擁有取得同意及管理存取／刪除／更正要求的程式。 Adobe主動要求Audience Marketplace協力廠商合作夥伴在 [](https://www.adobe-audience-finder.com/) Adobe Audience Finder中更新其公司個人檔案資訊，並提供使用者資料收集的其他資訊。 資訊將來自Audience Marketplace第三方合作夥伴，並會定期更新。 不過，由每位Audience Manager客戶決定Audience Marketplace第三方合作夥伴已取得該客戶使用案例的必要同意。 Adobe不就特定使用案例所取得或報告之「Audience Marketplace第三方合作夥伴」之同意之範圍或效力作出陳述。
