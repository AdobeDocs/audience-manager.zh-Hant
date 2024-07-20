---
description: 說明在您的Audience Manager帳戶中，透過與裝置相關的變數，以所有屬性來鎖定使用者的共同平台層級索引鍵值配對。
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: 使用平台層級索引鍵鎖定目標裝置
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---

# 使用平台層級索引鍵鎖定目標裝置 {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google已更新[!DNL Google Chrome]和所有[!DNL Chromium]型瀏覽器的功能，以將透過`User-Agent`標題收集的資訊減至最少。
>從2023年3月開始，Audience Manager運用[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)支援這些更新。 若要繼續使用透過`User-Agent`標題提供的特徵資訊，您必須使用[Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)並啟用[高平均資訊量使用者代理程式使用者端提示](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en)。
>[DIL](../../../using/dil/dil-overview.md)不支援這些更新，因此使用[!DNL DIL]的Audience Manager客戶將無法透過`User-Agent`標頭收集特徵資訊。

說明在您的Audience Manager帳戶中，透過與裝置相關的變數，以所有屬性來鎖定使用者的共同平台層級索引鍵值配對。

## 平台層級變數的用途 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

平台層級變數可讓您取得從特定網站傳入的資料，並使其可用於在[!DNL Audience Manager]帳戶中的所有屬性中進行目標定位。 這些變數由[索引鍵值配對](../../reference/key-value-pairs-explained.md)組成，其索引鍵前置詞為`d_`，如下所示。

## 使用者代理程式定義的平台層級金鑰 {#keys-user-agent}

[!UICONTROL Data Collection Servers]會從`HTTP`要求中的[使用者代理程式標頭](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)擷取這些金鑰的值。 值代表來自[!UICONTROL Device Atlas]資料庫的裝置層級資訊。 下表中的訊號可供使用，例如從使用者代理範例擷取的訊號。 [根據[!UICONTROL Device Atlas]測量結果，下載最常用的金鑰清單](assets/device_keys.csv)。

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
>即使無法從使用者代理程式標頭擷取一或多個訊號，其他訊號仍會傳遞至[!UICONTROL Data Collection Servers]。

>[!MORELIKETHIS]
>
>* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)
