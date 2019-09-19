---
description: 特徵存留時間(TTL)間隔如何影響區段成員資格。
seo-description: 特徵存留時間(TTL)間隔如何影響區段成員資格。
seo-title: 群體與特徵的即時說明
solution: Audience Manager
title: 區段的存留時間說明
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# 區段和特徵上線時間說明 {#segment-time-to-live-explained}

特徵( [!UICONTROL time-to-live] )間隔[!DNL TTL]如何影響區段成員資格。

<!-- segment-ttl-explained.xml -->

## 上線時間

[!DNL TTL] 定義網站訪客在最後一個特徵資格事件後在區段中停留的時間。 [!DNL TTL] 是設定在特徵上，而非區段上。 如果訪客在間隔結束前未看到合格特徵，則會從區段中 [!DNL TTL] 流失。 新特徵 [!DNL TTL] 的預設值為120天。 設為0天時，特徵不會過期。 [在特徵建立介面的部分中](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) ，建立或編輯特徵時 [!UICONTROL Advanced Options] ，設定TTL值。

## [!DNL TTL] 和從區段中刪除

如果使用者在時間間隔內未看到任何特徵，就會從區段中 [!DNL TTL] 掉出。 例如，如果您有1個特徵區段的30天 [!DNL TTL]，如果使用者在30天內再未看見該特徵，就會從該區段中移除。

![](assets/ttl_1.png)

## [!DNL TTL] 和區段續約

若 [!DNL TTL] 使用者在時段內看到該區段的特徵，則會重設，而且使用者仍留在區 [!DNL TTL] 段中。 此外，由於大部分區段包含具有其自有句號的多 [!DNL TTL] 個特徵，因此只要使用者持續看到與區段相關的任何特徵，就可以保留在區段中(並重設 [!DNL TTL] 間隔)。 例如，假設您有由特徵A（30天）和特徵B（15天） [!DNL TTL]組成的區段1 [!DNL TTL]。 假設使用者只看到每個特徵一次，下圖說明續約 [!DNL TTL] 程式和區段內總持續時間。

![](assets/ttl_2.png)

## [!DNL Audience Manager] TTL與第三方TTL設定無關

請記住， [!DNL TTL] 您的像素 [!DNL Audience Manager] 上的設定會獨立於協力廠商( [!DNL TTL][!DNL DSP]如、廣告網路等)使用的其他像素上的設定運作。

>[!MORE_LIKE_THIS]
>
>* [設定特徵過期間隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

