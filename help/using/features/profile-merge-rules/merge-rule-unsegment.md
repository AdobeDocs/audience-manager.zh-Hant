---
description: 取消細分會說明會取消區段中裝置設定檔的資格和移除程式。 您是否可從區段中移除裝置設定檔，取決於用來建立設定檔合併規則的裝置選項。
seo-description: 取消細分會說明會取消區段中裝置設定檔的資格和移除程式。 您是否可從區段中移除裝置設定檔，取決於用來建立設定檔合併規則的裝置選項。
seo-title: 設定檔合併規則與裝置取消細分程序
solution: Audience Manager
title: 設定檔合併規則與裝置取消細分程序
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: 個人資料合併
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# 設定檔合併規則與裝置取消細分程序 {#profile-merge-rules-and-device-un-segmentation-processes}

取消細分會說明會取消區段中裝置設定檔的資格和移除程式。 您從區段中移除裝置設定檔的能力，取決於用來建立[!UICONTROL Profile Merge Rule]的裝置選項。

## 可用設備選項{#device-options}

提醒您，當您建立或編輯[!UICONTROL Profile Merge Rule]時，[!UICONTROL Profile Merge Rules Setup]區段中會提供[!UICONTROL Device Options]。

## 當前設備配置檔案選項和設備取消細分{#current-device-profile-options}

**[!UICONTROL Device Profile]** 是的預設裝置設定檔選 [!UICONTROL Profile Merge Rule]項。[!DNL Audience Manager] 當您使用選項時，可從區段中移除 [!UICONTROL Profile Merge Rule] 裝置設 **[!UICONTROL Device Profile]** 定檔。在下列情況下，會發生取消細分：

* 裝置設定檔已停用120天。 每週資料清理程式會從您的區段中移除非作用中的裝置設定檔。
* 裝置不再符合區段的資格，因為裝置設定檔的更新或變更會取消區段的資格。 當區段資格標準變更，或您將[!DNL AND NOT]運算子套用至區段規則，或指定使用小於或等於設定的[時近和頻率](../segments/recency-and-frequency.md)條件時，就會發生此情況。 [即時跨裝置隱藏](instant-cross-device-suppression.md)檔案中有說明的使用案例。

![僅限裝置](assets/device-only.png)

## 無設備選項和設備取消細分{#no-device-option}

[!DNL Audience Manager] 當您使用+選項時，可以從區段中 [!UICONTROL Profile Merge Rule] 移除跨 **[!UICONTROL Current Authenticated Profiles]** 裝置 **[!UICONTROL No Device Profile]** ID。在這些情況下，當跨裝置ID不再符合區段的資格時，就會取消細分，因為跨裝置設定檔的更新或變更會取消其資格。 當區段資格標準變更，或您將[!UICONTROL AND NOT]運算子套用至區段規則，或指定使用小於或等於設定的[時近和頻率](../segments/recency-and-frequency.md)條件時，就會發生此情況。 [即時跨裝置隱藏](instant-cross-device-suppression.md)檔案中有說明的使用案例。

![](assets/current-no-device.png)

## 裝置圖表選項和裝置取消細分{#device-graph-options-unsegmentation}

[!DNL Audience Manager] 當您使用裝置圖表選項時，可以從區段 [!UICONTROL Profile Merge Rule] 移除多個裝置設定檔。取消細分會發生在裝置圖表中裝置的合併設定檔不再符合區段資格時，因為此合併設定檔的更新或變更會使該設定檔從區段中取消資格。 當區段資格標準變更，或您將[!UICONTROL AND NOT]運算子套用至區段規則，或指定使用小於或等於設定的[時近和頻率](../segments/recency-and-frequency.md)條件時，就會發生此情況。 [即時跨裝置隱藏](instant-cross-device-suppression.md)檔案中有說明的使用案例。

>[!NOTE]
>
>**區段評估和取消資格的100個裝置限制**。
>使用裝置圖表的設定檔合併規則評估區段時，Audience Manager可合併最多100部裝置。 Audience Manager會透過[已驗證的設定檔](../../reference/visitor-authentication-states.md)（跨裝置ID）評估目前裝置和最多99部連結至目前裝置的裝置。 如果發出取消細分訊號，則目的地的區段會移除目前裝置和其他裝置。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [設定檔合併規則與裝置圖表常見問題集](../../faq/faq-profile-merge.md)
* [即時跨裝置隱藏功能](instant-cross-device-suppression.md)

