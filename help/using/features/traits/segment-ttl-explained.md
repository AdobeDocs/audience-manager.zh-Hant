---
description: 特徵存留時間(TTL)間隔對區段成員資格的影響。
seo-description: 特徵存留時間(TTL)間隔對區段成員資格的影響。
seo-title: 區段和特徵存留時間說明
solution: Audience Manager
title: 區段存留時間說明
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: 特徵
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 3%

---

# 區段和特徵存留時間說明 {#segment-time-to-live-explained}

特徵[!UICONTROL time-to-live]([!DNL TTL])間隔如何影響區段成員資格。

<!-- segment-ttl-explained.xml -->

## 存留時間

[!DNL TTL] 定義網站訪客在最後一個特徵資格事件後停留在區段中的時間。[!DNL TTL] 是針對特徵設定而非區段。如果訪客在[!DNL TTL]間隔結束前不符合特徵資格，則訪客會從區段中流失。 新特徵的預設[!DNL TTL]為120天。 設為0天時，特徵永不會過期。 [在特徵建](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 立介面的區段中建立或編輯特 [!UICONTROL Advanced Options] 徵時，設定TTL值。

### 1天TTL說明

將[!DNL TTL]設為1天時，TTL計時器會在特徵實現後隔天開始計時，不會計算特徵實現當天剩餘的小時數。

Audience Manager根據下列公式計算1天[!DNL TTL]特徵的[!DNL TTL]有效期：

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **範例1**:1:00即1天 [!DNL UTC]實現的特 [!DNL TTL]徵。[!DNL TTL] 將在24 + 24 - 1 = 47小時後過期。
* **範例2**:特徵在23:00實 [!DNL UTC]現，為期1 [!DNL TTL]天。[!DNL TTL] 將在24 + 24 - 23 = 25小時後過期。

## [!DNL TTL] 和退出區段

若使用者在[!DNL TTL]間隔內不符合任何特徵的資格，該使用者便會掉出區段。 例如，如果您有一個1 — 特徵區段，其長度為30天[!DNL TTL]，如果使用者在未來30天內不再符合特徵資格，則使用者會退出該區段。

![](assets/ttl-explained.png)

## [!DNL TTL] 和區段續約

[!DNL TTL]若使用者在[!DNL TTL]期間內符合該區段的特徵資格，則會重設，且使用者會保留在區段中。 此外，由於大部分區段包含具有其專屬[!DNL TTL]間隔的多個特徵，因此只要使用者持續符合與區段相關聯之任何特徵的資格，就可以保留在區段中，並重設[!DNL TTL]間隔。

例如，假設您的區段1由特徵A（30天[!DNL TTL]）和特徵B（15天[!DNL TTL]）組成。 假設訪客僅符合每個特徵的資格一次，下圖概述[!DNL TTL]續約程式和區段內總時間。

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL與協力廠商TTL設定無關

請記住，在您的[!DNL Audience Manager]像素上設定的[!DNL TTL]獨立於第三方使用的其他像素（[!DNL DSP]s、廣告網路等）上設定的[!DNL TTL]操作。

>[!MORELIKETHIS]
>
>* [設定特徵過期時間間隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

