---
description: 取消分段描述取消限定和從段中刪除設備配置檔案的進程。 能否從段中刪除設備配置檔案取決於用於建立配置檔案合併規則的設備選項。
seo-description: Unsegmentation describes processes that disqualify and remove device profiles from segments. Your ability to remove a device profile from a segment depends on the device option used to create a Profile Merge Rule.
seo-title: Profile Merge Rules and Device Un-Segmentation Processes
solution: Audience Manager
title: 設定檔合併規則與裝置取消細分程序
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 5%

---

# 設定檔合併規則與裝置取消細分程序 {#profile-merge-rules-and-device-un-segmentation-processes}

取消分段描述取消限定和從段中刪除設備配置檔案的進程。 從段中刪除設備配置檔案的能力取決於用於建立 [!UICONTROL Profile Merge Rule]。

## 可用設備選項 {#device-options}

作為提醒， [!UICONTROL Device Options] 在 [!UICONTROL Profile Merge Rules Setup] 建立或編輯 [!UICONTROL Profile Merge Rule]。

## 當前設備配置檔案選項和設備未分割 {#current-device-profile-options}

**[!UICONTROL Device Profile]** 是的預設設備配置檔案選項 [!UICONTROL Profile Merge Rule]。 [!DNL Audience Manager] 可以在 [!UICONTROL Profile Merge Rule] 使用 **[!UICONTROL Device Profile]** 的雙曲餘切值。 在這些情況下，當：

* 設備配置檔案已停用120天。 每週資料清理過程會從段中刪除非活動的設備配置檔案。
* 設備不再符合段資格，因為設備配置檔案的更新或更改會取消段資格。 當段資格條件發生更改或您應用 [!DNL AND NOT] 段規則的運算子，或指定 [頻率](../segments/recency-and-frequency.md) 使用小於/等於設定的條件。 在中介紹了使用案例 [即時跨設備抑制](instant-cross-device-suppression.md) 文檔。

![僅設備](assets/device-only.png)

## 無設備選項和設備取消分割 {#no-device-option}

[!DNL Audience Manager] 可以在 [!UICONTROL Profile Merge Rule] 使用 **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** 的雙曲餘切值。 在這些情況下，當跨設備ID不再符合段的條件時，會發生取消分段，因為對跨設備配置檔案的更新或更改會取消分段的資格。 當段資格條件發生更改或您應用 [!UICONTROL AND NOT] 段規則的運算子，或指定 [頻率](../segments/recency-and-frequency.md) 使用小於/等於設定的條件。 在中介紹了使用案例 [即時跨設備抑制](instant-cross-device-suppression.md) 文檔。

![](assets/current-no-device.png)

## 設備圖形選項和設備未分割 {#device-graph-options-unsegmentation}

[!DNL Audience Manager] 可在您的 [!UICONTROL Profile Merge Rule] 使用設備圖形選項。 當設備圖形中設備的合併配置檔案不再符合段的條件時，將發生取消分段，因為更新或更改此合併配置檔案會使其不符合段的條件。 當段資格條件發生更改或您應用 [!UICONTROL AND NOT] 段規則的運算子，或指定 [頻率](../segments/recency-and-frequency.md) 使用小於/等於設定的條件。 在中介紹了使用案例 [即時跨設備抑制](instant-cross-device-suppression.md) 文檔。

>[!NOTE]
>
>**100個設備分段評估和取消資格限制**。
>Audience Manager使用使用設備圖形的配置式合併規則計算段時，會合併多達100台設備。 Audience Manager評估當前設備和通過 [認證配置檔案](../../reference/visitor-authentication-states.md) （跨設備ID）。 如果發出無段信號，則當前設備和附加設備將從目的地的段中刪除。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [設定檔合併規則與裝置圖表常見問題集](../../faq/faq-profile-merge.md)
>* [即時跨裝置隱藏功能](instant-cross-device-suppression.md)

