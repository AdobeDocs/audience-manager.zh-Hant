---
description: 本文說明索引鍵值配對中索引鍵變數所使用的命名慣例。
seo-description: 本文說明索引鍵值配對中索引鍵變數所使用的命名慣例。
seo-title: 關鍵變數的名稱要求
solution: Audience Manager
title: 關鍵變數的名稱要求
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 12%

---


# 關鍵變數的名稱要求 {#name-requirements-for-key-variables}

本文說明索引鍵值配對中索引鍵變數所使用的命名慣例。

## 鍵的命名要求

<!-- c_tb_key_name_requirements.xml -->

在 [!UICONTROL Expression Builder]中，鍵值對中的鍵變數名稱可以由任意數字組成，後跟1（或多個）字母、破折號、下划線和附加數字。

* 有效密鑰名： `price123`, `123price`, `price-123`, `c_price123`。

* 無效的密鑰名稱： `123`, `price!123`ý?

## 前置關鍵變數 `c_`

如果 `c_` 在事件 ** 呼叫URL上傳送資料的參數使用該語法，則前置詞一律為必要。