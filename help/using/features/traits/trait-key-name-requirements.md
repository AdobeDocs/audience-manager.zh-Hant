---
description: 本文說明關鍵值對中關鍵變數所使用的命名慣例。
seo-description: 本文說明關鍵值對中關鍵變數所使用的命名慣例。
seo-title: 關鍵變數的名稱需求
solution: Audience Manager
title: 關鍵變數的名稱需求
uuid: fa72e732-895d-4cf6-bea0-66b404 c2 b059
translation-type: tm+mt
source-git-commit: bdbc2525a13eb04898b0a844ba478cde07e83252

---


# Name Requirements for Key Variables {#name-requirements-for-key-variables}

本文說明關鍵值對中關鍵變數所使用的命名慣例。

## 索引鍵的命名需求

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], the name of a key variable in a key-value pair can consist of any number of digits followed by 1 (or more) letters, a dash, an underscore, and additional digits.

* Valid key names: `price123`, `123price`, `price-123`, `c_price123`.

* Invalid key names: `123`, `price!123`.

## Prefixing Key Variables with `c_`

The `c_` prefix is *always* required if the parameters that send in data on an event call URL use that syntax.