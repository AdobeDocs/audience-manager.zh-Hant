---
description: 取消細分會說明取消資格並從區段中移除裝置設定檔的程式。 您從區段移除裝置設定檔的功能取決於用來建立設定檔合併規則的裝置選項。
seo-description: Unsegmentation describes processes that disqualify and remove device profiles from segments. Your ability to remove a device profile from a segment depends on the device option used to create a Profile Merge Rule.
seo-title: Profile Merge Rules and Device Un-Segmentation Processes
solution: Audience Manager
title: 設定檔合併規則與裝置取消細分程式
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# 設定檔合併規則與裝置取消細分程式 {#profile-merge-rules-and-device-un-segmentation-processes}

取消細分會說明取消資格並從區段中移除裝置設定檔的程式。 您從區段移除裝置設定檔的能力取決於用來建立[!UICONTROL Profile Merge Rule]的裝置選項。

## 可用的裝置選項 {#device-options}

提醒您，當您建立或編輯[!UICONTROL Profile Merge Rule]時，[!UICONTROL Device Options]可在[!UICONTROL Profile Merge Rules Setup]區段中取得。

## 目前的裝置設定檔選項和裝置取消細分 {#current-device-profile-options}

**[!UICONTROL Device Profile]**&#x200B;是[!UICONTROL Profile Merge Rule]的預設裝置設定檔選項。 當您的[!UICONTROL Profile Merge Rule]使用&#x200B;**[!UICONTROL Device Profile]**&#x200B;選項時，[!DNL Audience Manager]可以從區段中移除裝置設定檔。 在這些條件下，取消細分會在下列情況發生：

* 裝置設定檔已停用120天。 每週資料清理程式會從您的區段中移除非使用中的裝置設定檔。
* 裝置不再符合區段的資格，因為裝置設定檔的更新或變更會取消其資格。 當區段資格條件變更，或您將[!DNL AND NOT]運運算元套用至區段規則，或指定使用小於/等於設定的[造訪間隔和頻率](../segments/recency-and-frequency.md)條件時，就會發生這種情況。 使用案例在[即時跨裝置隱藏](instant-cross-device-suppression.md)檔案中有所說明。

![僅限裝置](assets/device-only.png)

## 沒有裝置選項和裝置取消細分 {#no-device-option}

當您的[!UICONTROL Profile Merge Rule]使用&#x200B;**[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**&#x200B;選項時，[!DNL Audience Manager]可以從區段中移除跨裝置識別碼。 在這些情況下，當跨裝置ID不再符合區段資格時，就會發生取消分段，因為跨裝置設定檔的更新或變更會取消其資格。 當區段資格條件變更，或您將[!UICONTROL AND NOT]運運算元套用至區段規則，或指定使用小於/等於設定的[造訪間隔和頻率](../segments/recency-and-frequency.md)條件時，就會發生這種情況。 使用案例在[即時跨裝置隱藏](instant-cross-device-suppression.md)檔案中有所說明。

![](assets/current-no-device.png)

## 裝置圖表選項和裝置取消細分 {#device-graph-options-unsegmentation}

當您的[!UICONTROL Profile Merge Rule]使用裝置圖表選項時，[!DNL Audience Manager]可以從區段中移除多個裝置設定檔。 當裝置圖表的合併設定檔不再符合區段資格時，就會發生取消分段，因為更新或變更此合併設定檔會使該合併設定檔不再符合區段的資格。 當區段資格條件變更，或您將[!UICONTROL AND NOT]運運算元套用至區段規則，或指定使用小於/等於設定的[造訪間隔和頻率](../segments/recency-and-frequency.md)條件時，就會發生這種情況。 使用案例在[即時跨裝置隱藏](instant-cross-device-suppression.md)檔案中有所說明。

>[!NOTE]
>
>**100個區段評估與取消資格的裝置限制**。
>透過使用裝置圖表的設定檔合併規則來評估區段時，Audience Manager可合併最多100部裝置。 Audience Manager會透過[已驗證的設定檔](../../reference/visitor-authentication-states.md) （跨裝置識別碼），評估目前裝置和連結至目前裝置的最多99部裝置。 如果系統發出取消細分訊號，則目前的裝置和其他裝置將會從目的地的區段中移除。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [設定檔合併規則與裝置圖表常見問題集](../../faq/faq-profile-merge.md)
>* [即時跨裝置隱藏功能](instant-cross-device-suppression.md)
