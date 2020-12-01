---
description: 由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。
seo-description: 由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。
solution: Audience Manager
title: IP 位址模糊化
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 22%

---


# IP 位址模糊化 {#ip-obfuscation}

使用此功能可模糊化Audience Manager中收集的IP位址。

## 概述與方法{#overview-and-methodology}

由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。

### IP模糊化方法

Adobe Audience Manager遵循「依設計而設計隱私權」的原則，允許客戶從UI啟用IP模糊化，不論是全球各地區或特定國家／地區。 當您啟用此設定時，當IP位址被收錄到Audience Manager時，會立即捨棄IP位址的最後八位元（最後一部分）。 Audience Manager會在處理之前（包括在任何選擇性的地理查閱或記錄IP位址之前）放棄此部分IP位址。 例如：

* 混淆前：`255.255.255.255`
* 混淆後：`255.255.255.0`

另請參閱[資料隱私區段](/help/using/overview/data-security-and-privacy/data-privacy.md)中的收集IP位址和IP位址模糊化。

## IP位址模糊化要求{#ip-obfuscation-requirements}

IP位址模糊化僅適用於Audience Manager管理員帳戶。 請參閱[建立使用者](/help/using/features/administration/administration-overview.md#create-users)以瞭解如何指派使用者的管理員權限。

>[!NOTE]
>
> 由於Audience Manager處理的資料量龐大，從您更新設定開始，IP模糊化變更最多需要4小時。

## 設定IP位址模糊化{#configure-ip-obfuscation}

請依照下列步驟設定IP位址模糊化。

1. 使用管理員帳戶登入Audience Manager，並前往「管理>隱私權&#x200B;**」。**
2. 選擇要使用的IP模糊化類型。
   1. **模糊化所有IP位址：** 選取此選項，讓Audience Manager模糊化所有訪客IP位址的最後八位元，不論其來源地為何。
   2. **模糊化特定國家的IP位址：選** 取此選項，讓Audience Manager模糊化特定國家的訪客IP位址的最後八位元。使用&#x200B;**國家／地區清單**&#x200B;或對應的&#x200B;**搜尋**&#x200B;欄位，尋找要啟用IP模糊化的國家／地區，然後按一下+圖示，將它們新增至「已選取模糊化」清單。 ****&#x200B;將所有必要的國家／地區新增至「已選取模糊化」清單後，按一下「儲存」。********

![](assets/ip-obfuscation.png)

## 停用IP位址模糊化{#disable-ip-obfuscation}

若要全域停用IP位址模糊化，請前往&#x200B;**管理>隱私權**，選擇&#x200B;**不要模糊化IP位址**，然後按一下&#x200B;**儲存**。

若要停用特定國家／地區的IP位址模糊化，請在&#x200B;**「已選取模糊化」**&#x200B;清單中尋找國家／地區，然後按一下其對應的&#x200B;**X**&#x200B;圖示。 完成時，按一下「保存」。****

## 相關概念 {#related-concepts}

* [資料隱私權](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP位址模糊化視訊展示
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

