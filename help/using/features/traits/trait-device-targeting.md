---
description: 說明通用平台層級金鑰-值配對，您可使用此配對來定位使用者管理員帳戶中所有屬性的裝置相關變數。
seo-description: 說明通用平台層級金鑰-值配對，您可使用此配對來定位使用者管理員帳戶中所有屬性的裝置相關變數。
seo-title: 使用平台層級密鑰進行裝置定位
solution: Audience Manager
title: 使用平台層級密鑰進行裝置定位
uuid: bc048cc5-3df1-49bc-ac78-0ea5 d7 edd9 cc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

說明通用平台層級金鑰-值配對，您可使用此配對來定位使用者管理員帳戶中所有屬性的裝置相關變數。

## Purpose of Platform-level Variables {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Platform-level Keys Defined by User Agent {#keys-user-agent}

[!UICONTROL Data Collection Servers] 從請求中 [的使用者代理標題](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) 擷取這些索引鍵 `HTTP` 的值。The values represent device-level information from the [!UICONTROL Device Atlas] database. 下表中的訊號可從使用者代理範例中取得。[根據測量，下載最常用的索引鍵](assets/device_keys.csv)[!UICONTROL Device Atlas] 清單。

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
>Even if one or more signals cannot be retrieved from the user agent header, the other signals will still be passed to the [!UICONTROL Data Collection Servers].

>[!MORE_贊_ this]
>
>* [關鍵變數的首碼需求](../../features/traits/trait-variable-prefixes.md)

