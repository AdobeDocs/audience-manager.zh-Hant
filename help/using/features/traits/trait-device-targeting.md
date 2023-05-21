---
description: 介紹可用於目標用戶的通用平台級密鑰值對，這些對象具有與設備相關的變數，可跨Audience Manager帳戶中的所有屬性。
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
>Google已更新 [!DNL Google Chrome] 全部 [!DNL Chromium]基於瀏覽器，以最小化通過 `User-Agent` 標題。
>從2023年3月開始，Audience Manager通過利用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)。 繼續使用通過 `User-Agent` 標題，必須使用 [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 啟用 [高熵用戶代理客戶端提示](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en)。
>不支援這些更新 [DIL](../../../using/dil/dil-overview.md)，因此Audience Manager使用 [!DNL DIL] 將無法通過 `User-Agent` 標題。

介紹可用於目標用戶的通用平台級密鑰值對，這些對象具有與設備相關的變數，可跨Audience Manager帳戶中的所有屬性。

## 平台級變數的用途 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

平台級變數允許您從特定站點傳入資料，並使其可用於在所有屬性中定位 [!DNL Audience Manager] 帳戶。 這些變數由 [鍵值對](../../reference/key-value-pairs-explained.md) 鍵前置詞為 `d_` 如下所示。

## 由用戶代理定義的平台級密鑰 {#keys-user-agent}

的 [!UICONTROL Data Collection Servers] 從 [用戶代理頭](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) 在 `HTTP` 請求。 值表示來自 [!UICONTROL Device Atlas] 資料庫。 下表中的信號可用，如從用戶代理示例中提取的那樣。 [下載最常用鍵的清單](assets/device_keys.csv)，根據 [!UICONTROL Device Atlas] 量。

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
>即使無法從用戶代理報頭中檢索到一個或多個信號，其它信號仍將傳遞給 [!UICONTROL Data Collection Servers]。

>[!MORELIKETHIS]
>
>* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)

