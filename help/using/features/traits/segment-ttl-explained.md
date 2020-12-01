---
description: 特徵存留時間(TTL)間隔如何影響區段成員資格。
seo-description: 特徵存留時間(TTL)間隔如何影響區段成員資格。
seo-title: 群體與特徵的即時說明
solution: Audience Manager
title: 區段的存留時間說明
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 3%

---


# 區段和特徵存留時間說明 {#segment-time-to-live-explained}

特徵[!UICONTROL time-to-live]([!DNL TTL])間隔如何影響區段成員資格。

<!-- segment-ttl-explained.xml -->

## 上線時間

[!DNL TTL] 定義網站訪客在最後一個特徵資格事件後在區段中停留的時間。[!DNL TTL] 是針對特徵設定而非區段。如果訪客在[!DNL TTL]間隔結束前不符合特徵，則會從區段中流失。 新特徵的預設[!DNL TTL]為120天。 設為0天時，特徵不會過期。 [在特徵創](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 建介面的部分建立或編輯特徵 [!UICONTROL Advanced Options] 時設定TTL值。

### 1天TTL說明

將[!DNL TTL]設為1天時，TTL計時器會在特徵實現後的第二天開始，而不會計算特徵實現日期剩餘的時間。

Audience Manager會根據下列公式，計算1天[!DNL TTL]特徵的[!DNL TTL]有效期：

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **範例1**:1:00時，1天 [!DNL UTC]即可發現特徵 [!DNL TTL]。[!DNL TTL] 將於24 + 24 - 1 = 47小時後到期。
* **範例2**:23:00,1天 [!DNL UTC]的特質 [!DNL TTL]。[!DNL TTL] 24 + 24 - 23 = 25小時後到期。

## [!DNL TTL] 和從區段中刪除

如果使用者在[!DNL TTL]間隔內未符合其任何特徵，則會從區段中掉出。 例如，如果您有1個特徵區段，且30天[!DNL TTL]，如果使用者在未來30天內不再符合該特徵的資格，就會從該區段中移除。

![](assets/ttl-explained.png)

## [!DNL TTL] 和區段續約

[!DNL TTL]會重設，如果使用者符合該區段在[!DNL TTL]期間內的特徵，則會保留在區段中。 此外，由於大部分區段包含具有其專屬[!DNL TTL]間隔的多個特徵，因此使用者可以保留在區段中，並重設[!DNL TTL]間隔，只要它們仍符合與區段相關的任何特徵的資格。

例如，假設您有由特徵A（30天[!DNL TTL]）和特徵B（15天[!DNL TTL]）組成的區段1。 假設訪客僅符合每個特徵一次的資格，下圖說明[!DNL TTL]續約程式和區段內持續時間總計。

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL與第三方TTL設定無關

請記住，在[!DNL Audience Manager]像素上設定的[!DNL TTL]與在協力廠商使用的其他像素（[!DNL DSP]s、廣告網路等）上設定的[!DNL TTL]獨立運作。

>[!MORELIKETHIS]
>
>* [設定特徵過期間隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

