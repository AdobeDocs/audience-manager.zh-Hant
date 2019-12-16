---
description: 本檔案說明如何在Audience manager中管理客戶資料。
seo-description: 本檔案說明如何在Audience manager中管理客戶資料。
seo-title: 資料治理
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: 資料治理
translation-type: tm+mt
source-git-commit: 9004dc46c0ac431e9f193467a2147a2d9ac36cdc

---


# 資料治理

## 概述 {#overview}

Audience Manager中的資料治理是指Audience Manager中客戶資料的生命週期，其中包括收集和模糊化 [IP位址](data-governance.md#collecting-ip-addresses)、 [資料保留](data-governance.md#data-retention), [以及跨境資料傳輸](data-governance.md#data-transfers)。

## 收集IP位址和IP位址模糊化 {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** IP模糊化方法：Adobe Audience manager遵循「依設計隱私權」的原則，允許客戶在UI中啟用模糊化，不論是全球各地區或特定國家／地區 [!DNL IP] 。 當您啟用此設定時，當將位址收錄到Audience manager中時，會立即捨棄 [!DNL IP] 該位址的最後八位 [!DNL IP] 元（最後一部分）。 Audience manager會在處理前(包括任何選用的地理查閱或 [!DNL IP] 記錄位址之前)放棄此部分 [!DNL IP] 位址。 例如:

* 在可以記錄: `255.255.255.255`
* 之後: `255.255.255.0`

>[!NOTE]
>
>請參 [閱IP位址模糊化](../../features/administration/ip-obfuscation.md) ，以瞭解如何在Audience Manager UI [!DNL IP] 中啟用位址模糊化。

觀看以下影片，瞭解位址模糊 [!DNL IP] 化在Audience manager中的運作方式。

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=chi_hant)

**** 地域劃分：如果您啟 [!DNL IP] 用位址模糊化，位址的其餘八位元仍 [!DNL IP] 可用於Audience manager中的地域劃分和報告。 如果您未啟用位 [!DNL IP] 址模糊化，Audience manager會使用完整位 [!DNL IP] 址。 您可以使用「地理區段」功能，在任何情況下都可 [!DNL IP] 以依地理區域識別位置，但在使用模糊化時會略 [!DNL IP] 有降低精確度。 Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. 取得地區和國家一級的資訊只會受到輕微影響。 「地理區段」資料的粒度僅限城市層級或郵遞區號層級，而非個別層級。 進一步瞭解 [地理定位](../../features/traits/trait-geotarget-keys.md) ，以及如何使用地理變數設定特徵。

## Audience manager中的資料保留 {#data-retention}

對您的資料套用適當、安全且及時的資料保留政策是遵守資料隱私權法規的重要一環。 Audience Manager客戶可定義所需的TTL（存留時間），以設定特徵和區段的自訂保留期。 如需保 [留期的詳細資訊](../../faq/faq-privacy.md) ，請參閱資料保留常見問答集。

## 跨邊界資料傳輸 {#data-transfers}

當Audience manager跨國傳輸客戶的個人資料時，Audience manager會遵守適用法律。 請造訪 [Adobe隱私權中心](https://www.adobe.com/privacy/eudatatransfers.html) ，瞭解更多資訊。