---
description: 特徵時間對即時(TTL)間隔會影響區段成員資格。
seo-description: 特徵時間對即時(TTL)間隔會影響區段成員資格。
seo-title: 區段與特徵的即時說明
solution: Audience Manager
title: 區段的即時說明
uuid: 5b2c6911-50b9-4b68-9dd4-212128d112eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Segment and Trait Time-to-Live Explained {#segment-time-to-live-explained}

How trait [!UICONTROL time-to-live] ([!DNL TTL]) interval affects segment membership.

<!-- segment-ttl-explained.xml -->

## 即時上線

[!DNL TTL] 定義網站訪客在最後一個特徵資格事件之後停留的時間長度。[!DNL TTL] 設定於特徵而非區段上。Visitors fall out of a segment if they do not see a qualifying trait before the end of the [!DNL TTL] interval. The default [!DNL TTL] for new traits is 120 days. 設為天時，特徵永遠不會過期。[在特徵建立](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 介面 [!UICONTROL Advanced Options] 的區段中建立或編輯特徵時，設定TTL值。

## [!DNL TTL] 並捨棄區段

A user falls out of a segment if they do not see any of its traits within the [!DNL TTL] interval. For example, if you have a 1-trait segment with a 30 days [!DNL TTL], the user will drop out of that segment if they do not see the trait again within the 30 days.

![](assets/ttl_1.png)

## [!DNL TTL] 和區段續約

[!DNL TTL] 重設後，如果使用者在時段 [!DNL TTL] 內看到該區段特徵，則會將其保留在區段中。Also, because most segments contain multiple traits with their own [!DNL TTL] periods, a user can remain in a segment (and reset the [!DNL TTL] interval) as long as they keep seeing any traits associated with a segment. For example, say you have Segment 1 composed of Trait A (30 day [!DNL TTL]) and Trait B (15 day [!DNL TTL]). Assuming the user sees each trait only once, the illustration below outlines the [!DNL TTL] renewal process and total in-segment duration.

![](assets/ttl_2.png)

## [!DNL Audience Manager] THTML獨立於第三方TTL設定

Remember, the [!DNL TTL] set on your [!DNL Audience Manager] pixel operates independently from the [!DNL TTL] set on other pixels used by third parties ([!DNL DSP]s, ad networks, etc.).

>[!MORE_贊_ this]
>
>* [設定特徵過期間隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

