---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# 說明

**注意： 本頁（或任何readme.md頁面）不會發佈至客戶對應檔案**

## 目錄

+ `TOC.md` 在使用手冊的根目錄中提供了此解決方案指南中包含的主題的組織。
+ 每個使用手冊都有其獨特 `TOC.md`性，您可視需要訂購所有頁面／主題。
+ 所有使用手冊的第一頁是 `overview.md`。

## 使用者指引

+ 使用者指南的簡介稱為 `overview.md`
+ 使用手冊中的每個主題都有其自己的不同目錄。
   + 如果指南中有一個主題稱為「實 *施*」，則對應的目錄為 `/implementation`
+ 所有影像資產都儲存在 `/assets` 使用指南的根目錄中。
   + 目錄中的所 `/assets` 有映像都將本地化。
   + 目錄中的任 `/no-localize` 何影像都不會本地化（太意外了！）。 這可用來確保在本機版本中不會不必要的重制特定資產。

## 使用手冊級別元資料

+ 描述使用手冊的元資料儲存在中 `TOC.md`。 其中包括：
   + product —— 產品／功能的名稱。
   + cloud —— 此產品所屬的雲端。
   + 對象——指導的目標對象或原型。
   + user-guide —— 使用手冊的名稱。

## 頁面層級中繼資料

+ 描述文檔所需的元資料作為每個單獨頁面的一部分儲存。 其中包括：
   + title —— 頁面的標題。
   + description - description of page.
   + seo-title - seo替代標題。
   + seo-description —— 用於SEO目的的替代標題。
   + short-title -（可選欄位）。
   + 索引——是／否——頁面將由Adobe的搜尋平台建立索引。
   + 翻譯——是／否——將本頁本地化。
   + 版本——主要用於AEM和促銷活動，以表示產品版本。
   + private-feature-pack —— 主要用於AEM。
   + beta版——此產品是否採用beta版？
   + 重新導向——可用來建立必要之新頁面的參考。
   + doc-type: 參考（預設）/疑難排解／開發人員／教學課程/ kb /白皮書。

## 更多資訊

如需更多發佈指示、樣式指南、範例和其他資源，請造訪協作文 [件回購](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
