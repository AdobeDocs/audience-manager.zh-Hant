---
description: 我們並未使用Audience Manager，但在Javascript除錯程式中看到Audience Manager Javascript呼叫——原因為何？
seo-description: 我們並未使用，但在Javascript除錯程式中看到Audience Manager Javascript呼叫——原因何在？
seo-title: 我們並未使用Audience Manager，但在Javascript除錯程式中看到Audience Manager Javascript呼叫——原因為何？
solution: Audience Manager
title: 我們並未使用Audience Manager，但在Javascript除錯程式中看到Audience Manager Javascript呼叫——原因為何？
translation-type: tm+mt
source-git-commit: 7206b43562eded19bfb30f8aea3bcad946a3f834

---


# 我們不是Audience Manager客戶，但在我們的網站上看到Audience Manager Javascript呼叫

## 連結

我們並未使用Adobe Audience Manager，但是在Javascript除錯程式中看到Audience Manager Javascript呼叫。  為什麼會發生這種情況？

## 回答

您可能正在屬性上執行訪客ID服務。 如果您是，取得此AAM參考不一定是指執行Audience Manager的屬性，但這表示Audience Manager實際上是這項服務的助力。

請注意，AAM呼叫通常是用來同步設定客戶ID。
