---
description: 簡單像素(可用來限定特性的使用者)執行即時資料傳輸。Audience Manager介面可讓客戶以自助方式建立任意數量的像素。像素字串由簡單的ID或索引鍵值配對組成。
seo-description: 簡單像素(可用來限定特性的使用者)執行即時資料傳輸。Audience Manager介面可讓客戶以自助方式建立任意數量的像素。像素字串由簡單的ID或索引鍵值配對組成。
seo-title: 像素型資料傳輸
solution: Audience Manager
title: 像素型資料傳輸
uuid: 8773bfc06-6b8d-4a6a-a8 b7-e0437486 ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Pixel-based Data Transfers {#pixel-based-data-transfers}

簡單像素(可用來限定特性的使用者)執行即時資料傳輸。Audience Manager介面可讓客戶以自助方式建立任意數量的像素。像素字串由簡單的ID或索引鍵值配對組成。

<!-- c_rt_inbound_pixel_transfers.xml -->

若要啓用傳入的資料傳輸，廠商和用戶端將：

1. 確定您希望供應商或合作夥伴引發哪些特性。
1. 取得特徵的像素。In the traits list screen, hover over the **[!UICONTROL Actions]** column and click the **[!UICONTROL Get trait URL]** symbol for the desired trait.
1. Provide the [!DNL URL] to the vendor or partner.

## 範例

This basic event call sends trait ID 1234 to [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

You can serialize trait IDs in an event call to help reduce `HTTP` traffic from the page. 將其他特徵ID附加至URL字串，如下列範例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
