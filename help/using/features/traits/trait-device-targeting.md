---
description: 說明常用的平台層級索引鍵值配對，您可用來鎖定具有Audience Manager帳戶中所有屬性之裝置相關變數的使用者。
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: 使用平台層級的索引鍵進行裝置定位
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 5%

---

# 使用平台層級的索引鍵進行裝置定位 {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google已更新 [!DNL Google Chrome] 全部 [!DNL Chromium]以將透過 `User-Agent` 頁首。
>自2023年3月起，Audience Manager善用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). 若要繼續使用透過 `User-Agent` 標題，您必須使用 [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 啟用 [高熵用戶代理客戶端提示](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>不支援這些更新 [DIL](../../../using/dil/dil-overview.md)，因此請Audience Manager使用 [!DNL DIL] 將無法透過 `User-Agent` 頁首。

說明常用的平台層級索引鍵值配對，您可用來鎖定具有Audience Manager帳戶中所有屬性之裝置相關變數的使用者。

## 平台層級變數的用途 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

平台層級變數可讓您擷取從特定網站傳入的資料，並可用於定位您 [!DNL Audience Manager] 帳戶。 這些變數由 [索引鍵值配對](../../reference/key-value-pairs-explained.md) 鍵首碼為 `d_` 如下所示。

## 由使用者代理定義的平台層級索引鍵 {#keys-user-agent}

此 [!UICONTROL Data Collection Servers] 從 [使用者代理標題](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` 要求。 值代表 [!UICONTROL Device Atlas] 資料庫。 下表中的訊號可供使用，從使用者代理範例中擷取。 [下載最常見鍵的清單](assets/device_keys.csv)，根據 [!UICONTROL Device Atlas] 測量。

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>即使一個或多個信號無法從用戶代理頭檢索，其他信號仍將傳遞至 [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)

