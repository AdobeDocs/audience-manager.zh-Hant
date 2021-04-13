---
description: 取消區段會說明將裝置設定檔從區段中取消篩選和移除的程式。 從區段移除裝置描述檔的能力取決於用來建立描述檔合併規則的裝置選項。
seo-description: 取消區段會說明將裝置設定檔從區段中取消篩選和移除的程式。 從區段移除裝置描述檔的能力取決於用來建立描述檔合併規則的裝置選項。
seo-title: 設定檔合併規則與裝置取消細分程序
solution: Audience Manager
title: 設定檔合併規則與裝置取消細分程序
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: 描述檔合併
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# 設定檔合併規則與裝置取消細分程序 {#profile-merge-rules-and-device-un-segmentation-processes}

取消區段會說明將裝置設定檔從區段中取消篩選和移除的程式。 從區段移除裝置描述檔的能力取決於用來建立[!UICONTROL Profile Merge Rule]的裝置選項。

## 可用設備選項{#device-options}

當您建立或編輯[!UICONTROL Profile Merge Rule]時，[!UICONTROL Profile Merge Rules Setup]區段中會提供[!UICONTROL Device Options]。

## 當前設備配置檔案選項和設備取消分段{#current-device-profile-options}

**[!UICONTROL Device Profile]** 是的預設設備配置檔案選 [!UICONTROL Profile Merge Rule]項。[!DNL Audience Manager] 可在您使用選項時，從區段移除 [!UICONTROL Profile Merge Rule] 裝置設 **[!UICONTROL Device Profile]** 定檔。在這些情況下，當發生下列情況時，會發生取消分段：

* 裝置設定檔已停用120天。 每週資料清除程式會從您的區段中移除非作用中的裝置描述檔。
* 裝置不再符合區段的資格，因為裝置描述檔的更新或變更會使區段失去資格。 當區段限定條件變更，或您套用[!DNL AND NOT]運算子至區段規則，或指定使用小於／等於設定的[時近和頻率](../segments/recency-and-frequency.md)條件時，就會發生此情況。 [即時跨裝置抑制](instant-cross-device-suppression.md)說明檔案中說明使用案例。

![僅限裝置](assets/device-only.png)

## 無設備選項和設備取消分段{#no-device-option}

[!DNL Audience Manager] 可在您使用+選項時，從區段移除 [!UICONTROL Profile Merge Rule] 跨裝 **[!UICONTROL Current Authenticated Profiles]** 置ID **[!UICONTROL No Device Profile]** 。在這些情況下，當跨裝置ID不再符合區段資格時，會發生取消區段的情況，因為跨裝置描述檔的更新或變更會使區段不符資格。 當區段限定條件變更，或您套用[!UICONTROL AND NOT]運算子至區段規則，或指定使用小於／等於設定的[時近和頻率](../segments/recency-and-frequency.md)條件時，就會發生此情況。 [即時跨裝置抑制](instant-cross-device-suppression.md)說明檔案中說明使用案例。

![](assets/current-no-device.png)

## 裝置圖表選項與裝置取消區段{#device-graph-options-unsegmentation}

[!DNL Audience Manager] 可在您使用裝置圖形選項時，從區段移除 [!UICONTROL Profile Merge Rule] 多個裝置描述檔。當裝置圖表中裝置的合併描述檔不再符合區段資格時，會發生取消分段，因為此合併描述檔的更新或變更會使其不符合區段資格。 當區段限定條件變更，或您套用[!UICONTROL AND NOT]運算子至區段規則，或指定使用小於／等於設定的[時近和頻率](../segments/recency-and-frequency.md)條件時，就會發生此情況。 [即時跨裝置抑制](instant-cross-device-suppression.md)說明檔案中說明使用案例。

>[!NOTE]
>
>**100個裝置的區段評估和取消資格限制**。
>Audience Manager使用使用裝置圖形的描述檔合併規則來評估區段時，可合併多達100個裝置。 Audience Manager通過[驗證的配置檔案](../../reference/visitor-authentication-states.md)（跨設備ID）評估當前設備和最多99個與當前設備連結的設備。 如果發出未分段信號，則當前設備和其他設備將從目的地的分段中刪除。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [設定檔合併規則與裝置圖表常見問題集](../../faq/faq-profile-merge.md)
>* [即時跨裝置隱藏功能](instant-cross-device-suppression.md)

