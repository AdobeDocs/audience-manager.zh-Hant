---
description: 本文說明索引鍵值配對中索引鍵變數使用的命名慣例。
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: 關鍵變數的名稱要求
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
TQID: https://experienceleague.adobe.com/OEw-vhgEQtUfiyA4FzKp7rnxeFOZh2nL3r1-YudPAhc
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 105
ht-degree: 0%

---

# 關鍵變數的名稱要求 {#name-requirements-for-key-variables}

本文說明索引鍵值配對中索引鍵變數使用的命名慣例。

## 索引鍵的命名需求

<!-- c_tb_key_name_requirements.xml -->

在[!UICONTROL Expression Builder]中，機碼值組中的機碼變數名稱可由任何數字後面接著1 （或更多）字母、破折號、底線和其他數字組成。

* 有效的金鑰名稱： `price123`、`123price`、`price-123`、`c_price123`。

* 無效的金鑰名稱： `123`， `price!123`。

## 在索引鍵變數前面加上`c_`

如果在事件呼叫URL上傳送資料的引數使用該語法，則`c_`首碼為&#x200B;*一律為*。
