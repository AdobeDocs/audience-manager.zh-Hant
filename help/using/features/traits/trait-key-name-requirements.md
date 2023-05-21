---
description: 本文描述鍵值對中鍵變數使用的命名約定。
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: 關鍵變數的名稱要求
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 9%

---

# 關鍵變數的名稱要求 {#name-requirements-for-key-variables}

本文描述鍵值對中鍵變數使用的命名約定。

## 鍵的命名要求

<!-- c_tb_key_name_requirements.xml -->

在 [!UICONTROL Expression Builder]，鍵值對中鍵變數的名稱可以包含任何數位，後跟1（或更多）個字母、破折號、下划線和附加數字。

* 有效密鑰名： `price123`。 `123price`。 `price-123`。 `c_price123`。

* 無效的密鑰名稱： `123`。 `price!123`。

## 預固定鍵變數 `c_`

的 `c_` 前置詞 *總是* 如果事件調用URL上發送資料的參數使用該語法，則此參數為必需欄位。
