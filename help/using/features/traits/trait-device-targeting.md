---
description: 說明您可用來在Audience Manager帳戶的所有屬性中，透過裝置相關變數鎖定使用者的常見平台層級索引鍵值配對。
seo-description: 說明您可用來在Audience Manager帳戶的所有屬性中，透過裝置相關變數鎖定使用者的常見平台層級索引鍵值配對。
seo-title: 使用平台層級的索引鍵進行裝置定位
solution: Audience Manager
title: 使用平台層級的索引鍵進行裝置定位
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 9%

---


# 使用平台層級的索引鍵進行裝置定位 {#device-targeting-with-platform-level-keys}

說明您可用來在Audience Manager帳戶的所有屬性中，透過裝置相關變數鎖定使用者的常見平台層級索引鍵值配對。

## 平台層級變數{#platform-variables}的用途

<!-- c_tb_device_targeting.xml -->

平台層級變數可讓您從特定網站傳入資料，並讓它適用於[!DNL Audience Manager]帳戶中所有屬性的定位。 這些變數由[key-value對](../../reference/key-value-pairs-explained.md)組成，鍵前置詞為`d_`，如下所示。

## 由用戶代理定義的平台級密鑰{#keys-user-agent}

[!UICONTROL Data Collection Servers]會從`HTTP`請求中的[使用者代理標題](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)擷取這些索引鍵的值。 這些值代表來自[!UICONTROL Device Atlas]資料庫的設備級資訊。 下表中的信號可用，從用戶代理示例中提取。 [根據測量值，下載最常用的鍵](assets/device_keys.csv)，清 [!UICONTROL Device Atlas] 單。

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
>即使無法從用戶代理報頭檢索到一個或多個信號，其它信號仍將傳遞到[!UICONTROL Data Collection Servers]。

>[!MORELIKETHIS]
>
>* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)

