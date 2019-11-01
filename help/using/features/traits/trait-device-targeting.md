---
description: 說明您可用來在Audience manager帳戶的所有屬性中，透過裝置相關變數鎖定使用者的常見平台層級索引鍵值配對。
seo-description: 說明您可用來在Audience manager帳戶的所有屬性中，透過裝置相關變數鎖定使用者的常見平台層級索引鍵值配對。
seo-title: 使用平台層級的金鑰進行裝置定位
solution: Audience Manager
title: 使用平台層級的金鑰進行裝置定位
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

說明您可用來在Audience manager帳戶的所有屬性中，透過裝置相關變數鎖定使用者的常見平台層級索引鍵值配對。

## 平台層級變數的用途 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

平台層級變數可讓您從特定網站傳入資料，並讓其適用於帳戶中所有屬性的定 [!DNL Audience Manager] 位。 這些變數由鍵值 [配對組成](../../reference/key-value-pairs-explained.md) ，鍵前置詞 `d_` 如下所示。

## 由用戶代理定義的平台級密鑰 {#keys-user-agent}

從 [!UICONTROL Data Collection Servers] 請求中的使用者代理標 [題擷取這些索引鍵](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)`HTTP` 的值。 這些值表示來自資料庫的設備級 [!UICONTROL Device Atlas] 資訊。 下表中的信號可用，從用戶代理示例中提取。 [根據測量值，下載最常用的鍵](assets/device_keys.csv)，清單 [!UICONTROL Device Atlas] 中。

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
>即使一個或多個信號無法從用戶代理報頭中檢索，其它信號仍將傳遞給 [!UICONTROL Data Collection Servers]。

>[!MORELIKETHIS]
>
>* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)

