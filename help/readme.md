---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# 指示

**注：本頁（或任何readme.md頁）不會發佈給面向客戶的文檔**

## 目錄

+ `TOC.md` 在使用手冊的根部，提供本解決方案指南中包含的主題的組織。
+ 每個使用手冊都有其獨特之處 `TOC.md`中，您可以根據需要對所有頁面/主題進行排序。
+ 所有使用手冊的第一頁 `overview.md`。

## 使用手冊

+ 使用手冊簡介稱為 `overview.md`
+ 使用手冊中的每個主題都有其自己的不同目錄。
   + 如果指南中有一個主題名為 *實施*，對應的目錄為 `/implementation`
+ 所有映像資產都儲存在 `/assets` 的下一頁。
   + 中的所有影像 `/assets` 目錄將本地化。
   + 中的任何影像 `/no-localize` 目錄將不會本地化（有意外！）。 這可用於確保在本地版本中不會不必要地複製特定資產。

## 使用手冊級元資料

+ 描述使用手冊的元資料儲存在 `TOC.md`。 其中包括：
   + product — 產品/功能的名稱。
   + 雲 — 此產品所屬的雲。
   + 受眾 — 指導針對的受眾或原型。
   + 使用手冊 — 使用手冊的名稱。

## 頁級元資料

+ 描述文檔所需的元資料作為每個單獨頁面的一部分儲存。 其中包括：
   + title — 頁面標題。
   + description — 頁面說明。
   + seo-title -seo替代標題。
   + seo-description — 用於SEO的備選標題。
   + short-title — （可選欄位）。
   + 索引 — 是/否 — 將按Adobe的搜索平台對頁面進行索引。
   + 翻譯 — 是/否 — 將本頁本地化。
   + 版本 — 主要用AEM於和市場活動，表示產品版本。
   + 專用功能包 — 主要用AEM於
   + beta — 此產品是否為beta?
   + redirect — 可用於根據需要建立新頁面的ref。
   + doc類型：參考（預設）/故障排除/開發人員/教程/ kb/白皮書。

## 更多資訊

有關發佈說明、樣式指南、示例和其他資源的詳細資訊，請訪問 [協作文檔回購](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
