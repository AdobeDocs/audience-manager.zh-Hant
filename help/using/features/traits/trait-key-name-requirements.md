---
description: 本文說明機碼值組中機碼變數使用的命名慣例。
seo-description: 本文說明機碼值組中機碼變數使用的命名慣例。
seo-title: 關鍵變數的名稱要求
solution: Audience Manager
title: 關鍵變數的名稱要求
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: 特徵
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 12%

---

# 關鍵變數的名稱要求 {#name-requirements-for-key-variables}

本文說明機碼值組中機碼變數使用的命名慣例。

## 索引鍵的命名需求

<!-- c_tb_key_name_requirements.xml -->

在[!UICONTROL Expression Builder]中，鍵值對中的鍵變數名稱可以包含任意數字，後跟1（或更多）個字母、破折號、底線和附加數字。

* 有效的密鑰名：`price123`、`123price`、`price-123`、`c_price123`。

* 密鑰名稱無效：`123`, `price!123`。

## 使用`c_`前置詞鍵變數

如果在事件呼叫URL上傳送資料的參數使用該語法，則`c_`前置詞為&#x200B;*always*。
