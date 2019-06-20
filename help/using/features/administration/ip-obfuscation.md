---
description: 由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。
seo-description: 由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。
solution: Audience Manager
title: IP 位址模糊化
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# IP 位址模糊化 {#ip-obfuscation}

使用此功能來模糊在Audience Manager中收集的IP位址。

## Overview and Methodology {#overview-and-methodology}

由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。

### IP模糊化方法

依照「隱私權依據設計」的原則，Adobe Audience Manager允許客戶從UI啓用IP模糊化，不論是全域地理區域或特定國家。啓用此設定時，當IP位址吸收到Audience Manager時，即會立即捨棄IP位址的最後八位元(最後一部分)。Audience Manager會在處理前廢止此IP位址的此部分(包括任何選用地理查閱或IP位址記錄)。例如:

* Before obfuscation: `255.255.255.255`
* After obfuscation: `255.255.255.0`

See also, Collecting IP addresses and IP Address Obfuscation in our [Data Privacy section](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP Address Obfuscation Requirements {#ip-obfuscation-requirements}

IP位址模糊化僅適用於Audience Manager管理員帳戶。See [Create Users](/help/using/features/administration/administration-overview.md#create-users) to understand how to assign administrator privileges for a user.

>[!NOTE]
>
> 由於Audience Manager處理的資料量龐大，從您更新設定的那一刻起，IP模糊化變更可能需要小時才生效。

## Configure IP Address Obfuscation {#configure-ip-obfuscation}

依照下列步驟設定IP位址模糊化。

1. Log in to Audience Manager with an administrator account and go to **Administration &gt; Privacy**.
2. 選擇您要使用的IP模糊化類型。
   1. **模糊化所有IP位址：** 選取此選項，讓Audience Manager模糊化所有訪客IP位址的最後八位數字，不論其來源來源為何。
   2. **模糊化特定國家的IP位址：** 選取此選項，讓Audience Manager模糊化特定國家的訪客IP位址的最後八位數字。Use the **List of Countries** or the corresponding **Search** field to find the countries to enable IP obfuscation for, and click the + icon to add them to the **Selected for Obfuscation** list. Once you&#39;ve added all the required countries to the **Selected for Obfuscation** list, click **Save**.

![](assets/ip-obfuscation.png)

## Disable IP Address Obfuscation {#disable-ip-obfuscation}

To disable IP address obfuscation globally, go to **Administration &gt; Privacy**, select **Do not obfuscate IP addresses**, and click **Save**.

To disable IP address obfuscation for specific countries, find the countries in the **Selected for Obfuscation** list, then click their corresponding **X** icon. Click **Save** when you&#39;re done.

## 相關概念 {#related-concepts}

* [資料隱私權](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP位址模糊化視訊展示
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=chi_hant)

