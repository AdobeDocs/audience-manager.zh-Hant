---
description: 由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: IP 位址模糊化
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 14%

---

# IP 位址模糊化 {#ip-obfuscation}

此功能可模糊化在Audience Manager中收集的IP位址。

## 概述和方法 {#overview-and-methodology}

由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。

### IP模糊化方法

遵循「設計隱私權」原則，Adobe Audience Manager可讓客戶透過UI啟用IP模糊化功能（針對全球各地理區域或特定國家/地區皆可）。 啟用此設定時，將IP位址擷取到Audience Manager中時，會立即捨棄該IP位址的最後八位元（最後一部分）。 Audience Manager會在處理前（包括任何選擇性地理查閱或記錄IP位址之前）捨棄此IP位址部分。 例如：

* 模糊化之前： `255.255.255.255`
* 模糊化之後： `255.255.255.0`

另請參閱我們的「收集IP位址和IP位址模糊化」 [資料隱私權區段](/help/using/overview/data-security-and-privacy/data-privacy.md).

### IP模糊化優先順序 {#precedence}

[資料流層級IP模糊化](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#create) 優先於Audience Manager中設定的任何IP模糊化選項，並套用至所有IP位址。 Audience Manager執行的任何地理位置查詢都會受到資料流層級的影響 [!UICONTROL IP obfuscation] 選項。 在Audience Manager中，根據完全模糊化的IP進行地理位置查詢，將會產生未知區域，且不會實現任何根據結果地理位置資料的區段。

## IP位址模糊化需求 {#ip-obfuscation-requirements}

IP位址模糊化僅適用於Audience Manager管理員帳戶。 另請參閱 [建立使用者](/help/using/features/administration/administration-overview.md#create-users) 以瞭解如何為使用者指派管理員許可權。

>[!NOTE]
>
> 由於Audience Manager處理了大量的資料，IP模糊化變更最多可能需要4小時的時間，才會從您更新設定時起生效。

## 設定IP位址模糊化 {#configure-ip-obfuscation}

請依照下列步驟設定IP位址模糊化。

1. 以系統管理員帳戶登入Audience Manager並移至 **管理>隱私權**.
2. 選擇您要使用的IP模糊化型別。
   1. **模糊化所有IP位址：** 選取此選項，可讓Audience Manager將所有訪客IP位址的最後八位元模糊化，無論其來源地區為何。
   2. **模糊化特定國家的IP位址：** 選取此選項，可讓Audience Manager模糊化特定國家/地區之訪客IP位址的最後八位元。 使用 **國家/地區清單** 或對應的 **搜尋** 欄位以尋找可啟用IP模糊化的國家/地區，然後按一下+圖示以將其新增至 **已選取進行模糊化** 清單。 一旦您將所有必要國家/地區新增至 **已選取進行模糊化** 清單，按一下 **儲存**.

![](assets/ip-obfuscation.png)

## 停用IP位址模糊化功能 {#disable-ip-obfuscation}

若要全域停用IP位址模糊化功能，請前往 **管理>隱私權**，選取 **不要模糊化IP位址**，然後按一下 **儲存**.

若要針對特定國家/地區停用IP位址模糊化功能，請在 **已選取進行模糊化** 清單，然後按一下它們對應的 **X** 圖示。 按一下 **儲存** 完成時。

## 相關概念 {#related-concepts}

* [資料隱私權](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP位址模糊化影片示範
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
