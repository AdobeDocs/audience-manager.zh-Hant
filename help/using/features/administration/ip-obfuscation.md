---
description: 由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: IP 位址模糊化
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 16%

---

# IP 位址模糊化 {#ip-obfuscation}

使用此功能對在Audience Manager中收集的IP地址進行模糊處理。

## 概述和方法 {#overview-and-methodology}

由於全球隱私權規範，貴公司可能會想要模糊化許多國家/地區中的 IP 位址。Audience Manager 可讓您根據全球或個別國家/地區模糊化訪客 IP 位址。

### IP混淆方法

按照「按設計保密」的原則，Adobe Audience Manager允許客戶從UI中進行IP混淆，無論是在全球所有地理區域還是針對特定國家/地區。 啟用此設定時，當IP地址被引入Audience Manager時，IP地址的最後一個二進位八位數（最後一部分）會立即被丟棄。 Audience Manager在處理之前丟棄IP地址的這一部分（包括在任何可選地理查找或記錄IP地址之前）。 例如：

* 混淆前： `255.255.255.255`
* 混淆後： `255.255.255.0`

另請參見中的收集IP地址和IP地址混淆 [「資料隱私」部分](/help/using/overview/data-security-and-privacy/data-privacy.md)。

## IP地址混淆要求 {#ip-obfuscation-requirements}

IP地址模糊處理僅可用於Audience Manager管理員帳戶。 請參閱 [建立用戶](/help/using/features/administration/administration-overview.md#create-users) 瞭解如何為用戶分配管理員權限。

>[!NOTE]
>
> 由於Audience Manager處理的資料量很大，從更新設定開始，IP混淆更改可能需要4小時才能生效。

## 配置IP地址模糊處理 {#configure-ip-obfuscation}

按照以下步驟配置IP地址混淆。

1. 使用管理員帳戶登錄到Audience Manager，然後轉到 **管理>隱私**。
2. 選擇要使用的IP混淆類型。
   1. **對所有IP地址進行模糊處理：** 選擇此選項可使Audience Manager模糊處理所有訪問者IP地址的最後一個二進位八位數，而不管它們來自哪個區域。
   2. **對特定國家/地區的IP地址進行模糊處理：** 選擇此選項可使Audience Manager模糊化特定國家/地區的訪問者IP地址的最後八位數。 使用 **國家清單** 或相應 **搜索** 欄位，查找要為其啟用IP混淆的國家，然後按一下+表徵圖將它們添加到 **已選擇進行模糊處理** 清單框。 將所有必需國家添加到 **已選擇進行模糊處理** 清單，按一下 **保存**。

![](assets/ip-obfuscation.png)

## 禁用IP地址模糊處理 {#disable-ip-obfuscation}

要全局禁用IP地址模糊處理，請轉到 **管理>隱私**&#x200B;選中 **不對IP地址進行模糊處理**，然後按一下 **保存**。

要禁用特定國家/地區的IP地址混淆，請查找 **已選擇進行模糊處理** 清單，然後按一下其對應 **X** 表徵圖 按一下 **保存** 等你完事了。

## 相關概念 {#related-concepts}

* [資料隱私權](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP地址混淆視頻演示
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
