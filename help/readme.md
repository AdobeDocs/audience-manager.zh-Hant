---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# 說明

**注意：此頁面（或任何readme.md頁面）不會發佈至面對客戶的檔案**

## 目錄

+ `TOC.md` 位於使用手冊的根目錄，提供使用手冊中所包含適用於此解決方案的主題組織。
+ 每個使用手冊都有各自的唯一`TOC.md`，您可以視需要排序所有頁面/主題。
+ 所有使用手冊的第一頁都是`overview.md`。

## 使用者指引

+ 使用手冊的簡介稱為`overview.md`
+ 使用手冊中的每個主題都有各自的不同目錄。
   + 如果指南中有一個名為&#x200B;*Implementation*&#x200B;的主題，則相應目錄為`/implementation`
+ 所有影像資產都儲存在使用手冊根目錄的`/assets`中。
   + `/assets`目錄中的所有影像都將本地化。
   + `/no-localize`目錄中的任何影像都不會翻譯（令人驚訝！）。 這可用來確保在loc版本中特定資產不會不必要地重現。

## 使用手冊層級中繼資料

+ 描述使用手冊的元資料儲存在`TOC.md`中。 其中包括：
   + 產品 — 產品/功能名稱。
   + 雲端 — 此產品所屬的雲端。
   + 對象 — 指南鎖定目標的對象或原型。
   + 使用手冊 — 使用手冊名稱。

## 頁面層級中繼資料

+ 說明檔案所需的中繼資料會儲存為每個個別頁面的一部分。 其中包括：
   + 標題 — 頁面標題。
   + 說明 — 頁面說明。
   + seo-title - seo替代標題。
   + seo-description - SEO用途的替代標題。
   + short-title — （可選欄位）。
   + 索引 — 是/否 — 頁面是否會根據Adobe的搜尋平台編列索引。
   + 翻譯 — 是/否 — 此頁面是否會翻譯。
   + 版本 — 主要用於AEM和Campaign，以表示產品的版本。
   + private-feature-pack — 主要用於AEM。
   + 測試版 — 此產品是否為測試版？
   + 重新導向 — 可視需要用來建立新頁面的參照。
   + doc-type:參考（預設）/疑難排解/開發人員/教學課程/ kb /白皮書。

## 更多資訊

如需更多發佈指示、樣式指南、範例和其他資源，請造訪[協作檔案存放庫](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
