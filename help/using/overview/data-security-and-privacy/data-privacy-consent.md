---
description: 本文件說明在 Audience Manager 中管理同意的運作方式。
seo-description: 本文件說明在 Audience Manager 中管理同意的運作方式。
seo-title: 同意管理
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: 同意管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 34af220db2cf23ccde225eb1e05af7ce0e1513b7
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 100%

---


# 同意管理

## 概述 {#overview}

在某些行銷活動需要同意的情況下，Audience Manager 客戶必須決定範圍，以及決定是否需要重新整理特定同意才能繼續使用未來的資料。

Audience Manager 提供多種工具，可協助您向使用者處取得必要同意，以便透過各個管道為他們提供個人化體驗。

>[!IMPORTANT]
>
> 本文件的內容不是法律建議，且用意並非要取代法律建議。
>
> Adobe 身為資料處理者，無法針對取得同意的作業提供法律建議。您也可以考慮與同意管理解決方案提供者 (例如 [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 或 [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/)) 合作，並在設定您的選擇加入實作時，諮詢貴公司的法律部門，取得有關同意和實務作法的建議。

## Experience Cloud 選擇加入服務

[Experience Cloud 選擇加入服務](https://docs.adobe.com/content/help/zh-Hant/id-service/using/implementation/opt-in-service/optin-overview.translate.html)可讓您為訪客設定通訊協定，協助您判斷當訪客造訪您的網站時，是否可在其個別裝置或瀏覽器上設定 Cookie。

這是 [!DNL Experience Cloud ID (ECID) Service] 的擴充功能，其用途是讓您控制 Experience Cloud 解決方案是否能在使用者同意前，為使用者在網頁上放置 Cookie，以及可使用哪個解決方案來執行

[Experience Cloud 選擇加入服務](https://docs.adobe.com/content/help/zh-Hant/id-service/using/implementation/opt-in-service/optin-overview.translate.html)也可讓您設定通訊協定，以整合您的同意管理平台 (CMP) 和現有的系統，成為更大型設計的一部分。

## 管理選擇加入/取得同意

Audience Manager 客戶能針對各種使用案例 (例如廣告或個人化) 將使用者同意儲存為 Audience Manager 中的特徵。之後您使用這些特徵建立的區段，只會包含針對每個使用案例分別提供同意的使用者。請注意，使用此方法不會停止資料收集，但只會在您傳送要啟用的區段時影響資料的使用方式。使用者撤回其同意時，您可以使用 Audience Manager 的[傳入批次程序](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)或 Audience Manager 選擇退出程序，從使用者設定檔中移除這些特徵，如下所述。

## 管理選擇退出/撤回同意

您可透過[您的隱私權選擇](https://www.adobe.com/tw/privacy/opt-out.html)頁面管理 Adobe Experience Cloud 的選擇退出選項。一鍵式功能可讓您的一般使用者控制和選擇退出 Adobe Experience Cloud 廣告解決方案 (包括 Audience Manager) 的資料收集。具體說明請參閱「隱私權選擇」頁面上的[企業客戶區段](https://www.adobe.com/tw/privacy/opt-out.html)。針對不支援第三方 Cookie 的瀏覽器，請參閱[宣告 ID 目標定位](../../features/declared-ids.md#declared-id-targeting)。針對行動裝置，請擷取相關 的Audience Manager 識別碼，並呼叫 Audience Manager 選擇退出 API，如[宣告 ID 選擇退出範例](../../features/declared-ids.md#opt-out-examples)所述。之後您就可以使用 Mobile SDK 的選擇退出 API 停止這些使用者的所有資料收集；請參閱 [Android 裝置](https://docs.adobe.com/content/help/zh-Hant/mobile-services/android/gdpr-privacy-android/privacy.html)和 [iOS 裝置](https://docs.adobe.com/content/help/zh-Hant/mobile-services/ios/privacy-gdpr-ios/privacy.html)。[資料隱私權請求文件](../../overview/data-security-and-privacy/data-privacy-requests.md)中提供其他有關選擇退出的詳細資訊。

## 管理第二方合作夥伴的同意

第二方合作夥伴通常也是資料控制者，且擁有向資料主體取得任何必要同意 (同意與其第二方資料合作夥伴共用資料) 的程序。您身為 Audience Manager 客戶，有責任判斷第二方合作夥伴是否已針對您的使用案例取得必要同意。有關取得同意的詳細資訊，請參閱上文。

## 管理 Audience Marketplace 第三方合作夥伴的同意

Audience Marketplace 第三方合作夥伴也是資料控制者，擁有取得同意及管理存取/刪除/更正請求的程序。Adobe 主動要求 Audience Marketplace 第三方商合作夥伴在 [ Adobe Audience Finder](https://www.adobe-audience-finder.com/) 中更新其公司設定檔資訊，並提供與使用者資料收集相關的其他資訊。資訊將來自 Audience Marketplace 第三方合作夥伴，且會定期更新。不過 Audience Marketplace 第三方合作夥伴是否已針對該客戶的使用案例取得必要的同意，由各個 Audience Manager 客戶自行判斷。Adobe 不就 Audience Marketplace 第三方合作夥伴針對特定使用案例取得或報告同意之範圍或效力做任何聲明。
