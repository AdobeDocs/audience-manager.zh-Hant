---
description: 我們未使用 Audience Manager，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。原因為何？
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: 我們未使用 Audience Manager，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。原因為何？
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 90%

---

# 我們不是 Audience Manager 客戶，但在我們的網站上看到 Audience Manager Javascript 呼叫

## 問題

我們未使用 Adobe Audience Manager，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。

為什麼會這樣？

## 回答

您可能是正在屬性上執行 [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)。如果您確實如此，出現此 Audience Manager 參考指的不一定是該屬性執行 Audience Manager。相反地，這表示 Audience Manager 正在協助這項服務。

發出 Audience Manager 伺服器呼叫通常是為了同步[客戶 ID](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html)。
