---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# 說明

**注意：本頁（或任何readme.md頁面）不會發佈至客戶對應檔案**

## 目錄

+ `TOC.md` 在使用手冊的根目錄中提供了此解決方案指南中包含的主題的組織。
+ 每個使用手冊都有其專屬的`TOC.md`，您可視需要在其中排序所有頁面／主題。
+ 所有使用手冊的第一頁是`overview.md`。

## 使用者指引

+ 使用手冊的簡介稱為`overview.md`
+ 使用手冊中的每個主題都有其自己的不同目錄。
   + 如果指南中有名為&#x200B;*Implementation*&#x200B;的主題，則對應的目錄為`/implementation`
+ 所有影像資產都儲存在使用手冊根目錄的`/assets`中。
   + `/assets`目錄中的所有映像都將本地化。
   + `/no-localize`目錄中的任何影像都不會本地化（太意外了！）。 這可用來確保在本機版本中不會不必要的重制特定資產。

## 使用手冊級別元資料

+ 描述使用手冊的元資料儲存在`TOC.md`中。 其中包括：
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
   + doc-type:參考（預設）/疑難排解／開發人員／教學課程/ kb /白皮書。

## 更多資訊

如需更多發佈指示、樣式指南、範例和其他資源，請造訪[協作檔案回購](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
