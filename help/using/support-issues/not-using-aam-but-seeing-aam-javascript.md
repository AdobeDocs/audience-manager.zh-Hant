---
description: 我們並未使用Audience Manager，但在Javascript除錯程式中看到Audience Manager Javascript呼叫——原因為何？
seo-description: 我們並未使用，但在Javascript除錯程式中看到Audience Manager Javascript呼叫——原因何在？
seo-title: 我們並未使用Audience Manager，但在Javascript除錯程式中看到Audience Manager Javascript呼叫——原因為何？
solution: Audience Manager
title: 我們並未使用Audience Manager，但在Javascript除錯程式中看到Audience Manager Javascript呼叫——原因為何？
translation-type: tm+mt
source-git-commit: 1f5c1a91f0b5df5291d3143d297e25128b5bb716

---


# 我們不是Audience Manager客戶，但在我們的網站上看到Audience Manager Javascript呼叫

## 連結

我們並未使用Adobe Audience Manager，但是在Javascript除錯程式中看到Audience Manager Javascript呼叫。

為什麼會這樣？

## 回答

您可能是在您的屬 [性上執行Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) 。 如果您是，取得此Audience Manager參考並不一定指執行Audience Manager的屬性。 相反地，這表示Audience Manager是這項服務的助力。

Audience Manager伺服器呼叫通常是為了同步 [客戶ID](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)。
