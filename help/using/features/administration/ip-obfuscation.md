---
description: 由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。
seo-description: 由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。
solution: Audience Manager
title: IP 位址模糊化
feature: 資料控管與隱私權
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 22%

---

# IP 位址模糊化 {#ip-obfuscation}

使用此功能將收集到的IP位址模糊化至Audience Manager。

## 概述和方法{#overview-and-methodology}

由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。

### IP模糊化方法

遵循「設計隱私權」原則，Adobe Audience Manager可讓客戶從UI啟用IP模糊化功能，無論是針對全球各地理區域或特定國家/地區皆可。 若啟用此設定，當將IP位址擷取至Audience Manager時，會立即捨棄IP位址的最後八位元（最後一部分）。 Audience Manager會在處理前（包括任何可選的地理查閱或IP位址記錄前）捨棄IP位址的這部分。 例如：

* 模糊化前：`255.255.255.255`
* 模糊化後：`255.255.255.0`

另請參閱[資料隱私權區段](/help/using/overview/data-security-and-privacy/data-privacy.md)中的收集IP位址和IP位址模糊化。

## IP位址模糊化需求{#ip-obfuscation-requirements}

IP位址模糊化僅適用於Audience Manager管理員帳戶。 請參閱[建立用戶](/help/using/features/administration/administration-overview.md#create-users)了解如何為用戶分配管理員權限。

>[!NOTE]
>
> 由於Audience Manager處理的資料量很大，IP模糊化變更最多可能需要4小時才會生效，從您更新設定的那一刻開始。

## 配置IP地址模糊化{#configure-ip-obfuscation}

請依照下列步驟來設定IP位址模糊化。

1. 使用管理員帳戶登入Audience Manager，然後前往&#x200B;**管理>隱私**。
2. 選擇您要使用的IP模糊化類型。
   1. **將所有IP位址模糊化：** 選取此選項，即可讓Audience Manager模糊化所有訪客IP位址的最後八位元，無論其來源地為何。
   2. **模糊化特定國家/地區的IP位址：** 選取此選項，讓Audience Manager模糊化特定國家/地區之訪客IP位址的最後八位元。使用&#x200B;**國家清單**&#x200B;或相應的&#x200B;**搜索**&#x200B;欄位查找要為其啟用IP模糊化的國家，然後按一下+表徵圖將其添加到&#x200B;**為模糊化選定**&#x200B;清單中。 將所有必要的國家/地區新增至「選取進行模糊化」**清單後，按一下「**&#x200B;儲存&#x200B;**」。**

![](assets/ip-obfuscation.png)

## 禁用IP地址模糊化{#disable-ip-obfuscation}

若要全域停用IP位址模糊化，請前往&#x200B;**管理>隱私權**，選取&#x200B;**不要模糊化IP位址**，然後按一下&#x200B;**儲存**。

若要停用特定國家/地區的IP位址模糊化，請尋找「選取進行模糊化」**清單中的國家/地區，然後按一下其對應的** X **圖示。**&#x200B;完成後，按一下「**儲存**」。

## 相關概念 {#related-concepts}

* [資料隱私權](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP位址模糊化影片示範
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
