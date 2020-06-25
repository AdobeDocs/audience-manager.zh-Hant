---
description: 本文件說明在 Audience Manager 中控管客戶資料的方式。
seo-description: 本文件說明在 Audience Manager 中控管客戶資料的方式。
seo-title: 資料控管
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: 資料控管
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 96%

---


# 資料控管

## 概述 {#overview}

Audience Manager 中的資料控管指的是 Audience Manager 中客戶資料的生命週期，其中包括[收集和模糊化 IP 位址](data-governance.md#collecting-ip-addresses)、[資料保留](data-governance.md#data-retention)以及[跨境資料傳輸](data-governance.md#data-transfers)。

## 收集 IP 位址和 IP 位址模糊化 {#collecting-ip-addresses}

前往客戶網站的訪客 [!DNL IP] 位址會傳送至 Adobe [!DNL Data Processing Center] ([!DNL DPC])，且可能在此儲存該 [!DNL IP] 位址。視訪客的網路設定而定，此 [!DNL IP] 位址不一定代表訪客電腦的 [!DNL IP] 位址。例如，該 [!DNL IP] 位址可能是網路位址轉譯 (NAT) 防火牆、[!DNL HTTP] Proxy 或網際網路閘道的外部 [!DNL IP] 位址。

**IP 模糊化方法：** Adobe Audience Manager 遵循「設計隱私權」原則，允許客戶透過 UI 啟用 [!DNL IP] 模糊化功能 (針對全球各地理區域或特定國家/地區皆可)。若啟用此設定，將 [!DNL IP] 位址擷取到 Audience Manager 中時，系統會立即捨棄該 [!DNL IP] 位址的最後八位元 (最後一部分)。Audience Manager 會在處理前 (包括任何選擇性地理查閱或記錄 [!DNL IP] 位址之前) 捨棄 [!DNL IP] 位址的這個部分。例如：

* 之前：`255.255.255.255`
* 之後：`255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](../../features/administration/ip-obfuscation.md) to learn how to enable [!DNL IP] address obfuscation in the Audience Manager user interface.

請觀看以下影片，瞭解 [!DNL IP] 位址模糊化在 Audience Manager 中的運作方式。

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**地理細分：**&#x200B;如果您啟用 [!DNL IP] 位址模糊化功能，[!DNL IP] 位址的其餘幾個八位元仍可用於 Audience Manager 中的地理細分和報表。如果您未啟用 [!DNL IP] 位址模糊化功能，Audience Manager 會使用完整的 [!DNL IP] 位址。在任何情況下，您都可以使用「地理細分」功能，依地理區域識別 [!DNL IP] 位置，但在使用 [!DNL IP] 模糊化的情況下精確度會略為降低。[!DNL IP] 位址模糊化可能會顯著影響城市層級資訊的取得。地區和國家層級資訊則只會受到輕微影響。地理細分資料的詳細程度只到城市層級或郵遞區號層級，不到個人層級。進一步瞭解[地理目標定位](../../features/traits/trait-geotarget-keys.md)，以及如何使用地理變數設定特徵。

## Audience Manager 中的資料保留 {#data-retention}

對您的資料套用適當、安全且及時的資料保留政策，是遵守資料隱私權法規的重要一環。Audience Manager 客戶可定義所需的 TTL (存留時間)，以設定特徵和區段的自訂保留期。如需保留期的詳細資訊，請參閱[資料保留常見問題集](../../faq/faq-privacy.md)。

## 跨境資料傳輸 {#data-transfers}

當 Audience Manager 跨國境傳輸客戶的個人資料，Audience Manager 會確實遵守適用法律。請造訪 [Adobe 隱私權中心](https://www.adobe.com/tw/privacy/eudatatransfers.html)瞭解詳細資訊。