---
description: 說明常用的平台層級索引鍵值配對，您可用來鎖定具有Audience Manager帳戶中所有屬性之裝置相關變數的使用者。
seo-description: 說明常用的平台層級索引鍵值配對，您可用來鎖定具有Audience Manager帳戶中所有屬性之裝置相關變數的使用者。
seo-title: 使用平台層級的索引鍵進行裝置定位
solution: Audience Manager
title: 使用平台層級的索引鍵進行裝置定位
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: 特徵
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---

# 使用平台層級的索引鍵進行裝置定位 {#device-targeting-with-platform-level-keys}

說明常用的平台層級索引鍵值配對，您可用來鎖定具有Audience Manager帳戶中所有屬性之裝置相關變數的使用者。

## 平台層級變數{#platform-variables}的用途

<!-- c_tb_device_targeting.xml -->

平台層級變數可讓您取用從特定網站傳入的資料，並讓其可用於[!DNL Audience Manager]帳戶中所有屬性的定位。 這些變數由[key-value對](../../reference/key-value-pairs-explained.md)組成，鍵首碼為`d_`，如下所示。

## 由用戶代理{#keys-user-agent}定義的平台級密鑰

[!UICONTROL Data Collection Servers]會從`HTTP`請求中的[使用者代理標題](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)擷取這些索引鍵的值。 這些值表示[!UICONTROL Device Atlas]資料庫中的設備級資訊。 下表中的訊號可供使用，從使用者代理範例中擷取。 [根據測量值下載最常見的鍵](assets/device_keys.csv)，清單 [!UICONTROL Device Atlas] 如下。

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
>即使一個或多個信號無法從用戶代理頭中檢索，其他信號仍將傳遞到[!UICONTROL Data Collection Servers]。

>[!MORELIKETHIS]
>
>* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)

