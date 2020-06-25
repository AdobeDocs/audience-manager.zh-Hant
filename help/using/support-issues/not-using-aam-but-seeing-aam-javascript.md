---
description: 我們未使用 Audience Manager，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。原因為何？
seo-description: 我們未使用，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。原因為何？
seo-title: 我們未使用 Audience Manager，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。原因為何？
solution: Audience Manager
title: 我們未使用 Audience Manager，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。原因為何？
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 100%

---


# 我們不是 Audience Manager 客戶，但在我們的網站上看到 Audience Manager Javascript 呼叫

## 問題

我們未使用 Adobe Audience Manager，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。

為什麼會這樣？

## 回答

您可能是正在屬性上執行 [Experience Cloud Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)。如果您確實如此，出現此 Audience Manager 參考指的不一定是該屬性執行 Audience Manager。相反地，這表示 Audience Manager 正在協助這項服務。

發出 Audience Manager 伺服器呼叫通常是為了同步[客戶 ID](https://docs.adobe.com/content/help/zh-Hant/id-service/using/id-service-api/methods/setcustomerids.translate.html)。
