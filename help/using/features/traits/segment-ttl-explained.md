---
description: 特質生存時間(TTL)間隔如何影響段成員。
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: 已解釋段的生存時間
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 3%

---

# 區段和特徵存留時間說明 {#segment-time-to-live-explained}

特質 [!UICONTROL time-to-live] ([!DNL TTL])間隔影響段成員身份。

<!-- segment-ttl-explained.xml -->

## 生存時間

[!DNL TTL] 定義站點訪問者在最後一個特質鑑定事件後在段中停留的時間。 [!DNL TTL] 是針對特徵設定而非區段。如果遊客在遊戲結束前不具備某種特質，他們就會從遊戲中消失 [!DNL TTL] 間隔。 預設 [!DNL TTL] 新特徵需要120天。 如果設定為0天，則該特徵永遠不會過期。 [設定TTL值](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 建立或編輯特徵時 [!UICONTROL Advanced Options] 的子菜單。

### 1天TTL已解釋

設定 [!DNL TTL] TTL定時器在特性實現後第二天開始，至1天，不計算特性實現日剩餘的時間。

Audience Manager計算 [!DNL TTL] 1天的特徵到期 [!DNL TTL] 根據以下公式：

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **示例1**:1:00時發現的特徵 [!DNL UTC],1天 [!DNL TTL]。 [!DNL TTL] 24 + 24 - 1 = 47小時後到期。
* **示例2**:23:00時發現的性狀 [!DNL UTC],1天 [!DNL TTL]。 [!DNL TTL] 24 + 24 - 23 = 25小時後到期。

## [!DNL TTL] 並退出段

如果用戶不符合其任何特徵，則用戶會從段中脫離 [!DNL TTL] 間隔。 例如，如果有1個特性段，30天 [!DNL TTL]如果用戶在30天內再次不符合該特徵，用戶將退出該部分。

![](assets/ttl-explained.png)

## [!DNL TTL] 和段續訂

的 [!DNL TTL] 重置，並且用戶仍保留在段中（如果符合段在段中的特性） [!DNL TTL] 期間。 另外，因為大多數片段包含具有自身特徵的多個特徵 [!DNL TTL] 間隔，用戶可以保留在段中，並重置 [!DNL TTL] 間隔，只要它們繼續符合與段關聯的任何特徵。

例如，假設您有由特性A（30天）組成的段1 [!DNL TTL])和特徵B（15天） [!DNL TTL])。 假設訪問者只鑑定一次每個特徵，下圖將概述 [!DNL TTL] 續訂流程和段內總持續時間。

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL與第三方TTL設定無關

記住， [!DNL TTL] 設定 [!DNL Audience Manager] 像素獨立於操作 [!DNL TTL] 設定第三方使用的其他像素([!DNL DSP]s、ad網路等)。

>[!MORELIKETHIS]
>
>* [設定特性到期間隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

