---
description: 由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。
seo-description: 由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。
solution: Audience Manager
title: IP 位址模糊化
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# IP 位址模糊化 {#ip-obfuscation}

使用此功能可模糊化Audience manager中收集的IP位址。

## 概觀與方法 {#overview-and-methodology}

由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。

### IP模糊化方法

Adobe Audience manager遵循「依設計而設計隱私權」的原則，允許客戶從UI啟用IP模糊化，不論是全球各地區或特定國家／地區。 當您啟用此設定時，當IP位址被收錄到Audience manager時，會立即捨棄IP位址的最後八位元（最後一部分）。 Audience manager會在處理之前（包括在任何選擇性的地理查閱或記錄IP位址之前）放棄此部分IP位址。 例如:

* 混淆前： `255.255.255.255`
* 混淆後： `255.255.255.0`

另請參閱「資料隱私權」區段中的收集IP位址和IP位 [址模糊化](/help/using/overview/data-security-and-privacy/data-privacy.md)。

## IP位址模糊化需求 {#ip-obfuscation-requirements}

IP位址模糊化僅適用於Audience manager管理員帳戶。 請參 [閱建立用戶](/help/using/features/administration/administration-overview.md#create-users) ，瞭解如何為用戶分配管理員權限。

>[!NOTE]
>
> 由於Audience manager處理的資料量龐大，從您更新設定開始，IP模糊化變更最多需要4小時。

## 設定IP位址模糊化 {#configure-ip-obfuscation}

請依照下列步驟設定IP位址模糊化。

1. 使用管理員帳戶登入Audience Manager，然後前往「管理&gt; **隱私權」**。
2. 選擇要使用的IP模糊化類型。
   1. **** 模糊化所有IP位址：選取此選項，讓Audience manager模糊化所有訪客IP位址的最後八位元，不論其來源為何地區。
   2. **** 模糊化特定國家／地區的IP位址：選取此選項，讓Audience manager模糊化特定國家／地區的訪客IP位址的最後八位元。 使用「國 **家／地區清單** 」或對應的「搜尋」欄位，尋找國家／地區以啟用IP模糊化，然後按一下+圖示，將它們新增至「 **選取模糊化」清單****** 。 將所有必要的國家／地區新增至「選取進行模糊 **化」清單後** ，按一下「 **儲存」**。

![](assets/ip-obfuscation.png)

## 停用IP位址模糊化 {#disable-ip-obfuscation}

若要全域停用IP位址模糊化，請前往「管 **理&gt;隱私**」，選 **取「不模糊化IP位址**」，然後按一下「 **儲存**」。

若要停用特定國家／地區的IP位址模糊化，請在「選取模糊化」清單中 **尋找國家／地區** ，然後按一下其對應 **的X** 圖示。 Click **Save** when you're done.

## 相關概念 {#related-concepts}

* [資料隱私權](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP位址模糊化視訊展示
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=chi_hant)

