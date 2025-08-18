---
description: 特徵存留時間(TTL)間隔對區段會籍有何影響。
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: 區段存留時間說明
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# 區段和特徵存留時間說明 {#segment-time-to-live-explained}

特徵[!UICONTROL time-to-live] ([!DNL TTL])間隔如何影響區段會籍。

<!-- segment-ttl-explained.xml -->

## 存留時間

[!DNL TTL]會定義網站訪客在最後一個特徵資格事件後會在區段中停留多久。 [!DNL TTL]是針對特徵設定而非區段。 如果訪客在[!DNL TTL]間隔結束前不符合特徵資格，就會從區段中流失。 新特徵的預設[!DNL TTL]為120天。 設為0天時，特徵永不過期。 [當您在特徵建立介面的](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)區段中建立或編輯特徵時，請設定TTL值[!UICONTROL Advanced Options]。

### 1天TTL說明

將[!DNL TTL]設定為1天時，TTL計時器在特徵實現後的第二天開始，不計算特徵實現日剩餘的時數。

Audience Manager會根據下列公式，計算1天[!DNL TTL]的特徵的[!DNL TTL]有效期：

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **範例1**：在1:00 [!DNL UTC]實現的特徵有1天[!DNL TTL]。 [!DNL TTL]將在24 + 24 - 1 = 47小時後到期。
* **範例2**：在23:00 [!DNL UTC]實現的特徵有1天[!DNL TTL]。 [!DNL TTL]將在24 + 24 - 23 = 25小時後到期。

## [!DNL TTL]並卸除區段

如果使用者在[!DNL TTL]間隔內不符合任何特徵的資格，便會退出區段。 例如，如果您有30天[!DNL TTL]的1個特徵區段，如果使用者在未來30天內再次不符合特徵資格，就會退出該區段。

![](assets/ttl-explained.png)

## [!DNL TTL]和區段續約

如果[!DNL TTL]在[!DNL TTL]期間內符合該區段特徵資格，則會重設，且使用者會留在區段中。 此外，由於大部分割槽段包含多個具有自己[!DNL TTL]間隔的特徵，使用者可以留在區段中，並重設[!DNL TTL]間隔，只要他們仍符合與該區段相關聯的任何特徵的資格。

例如，假設您的區段1由特徵A （30天[!DNL TTL]）和特徵B （15天[!DNL TTL]）組成。 假設訪客僅符合每個特徵一次，下圖會概述[!DNL TTL]續約流程和區段內總持續時間。

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL獨立於第三方TTL設定

請記住，在您的[!DNL TTL]畫素上設定的[!DNL Audience Manager]與第三方使用的其他畫素（[!DNL TTL]、廣告網路等）上設定的[!DNL DSP]獨立運作。

>[!MORELIKETHIS]
>
>* [設定特徵過期時間間隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)
