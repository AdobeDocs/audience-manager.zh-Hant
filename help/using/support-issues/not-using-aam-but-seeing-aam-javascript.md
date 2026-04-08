---
description: 我們未使用 Audience Manager，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。原因為何？
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: 我們未使用 Audience Manager，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。原因為何？
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 136
ht-degree: 98%

---

# 我們不是 Audience Manager 客戶，但在我們的網站上看到 Audience Manager Javascript 呼叫

## 問題

我們未使用 Adobe Audience Manager，但卻在 Javascript 除錯工具中看到 Audience Manager Javascript 呼叫。

為什麼會這樣？

## 回答

您可能是正在屬性上執行 [Experience Cloud 身分識別服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。如果您確實如此，出現此 Audience Manager 參考指的不一定是該屬性執行 Audience Manager。相反地，這表示 Audience Manager 正在協助這項服務。

發出 Audience Manager 伺服器呼叫通常是為了同步[客戶 ID](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html)。
