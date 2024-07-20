---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---
# 指示

**注意：此頁面（或任何readme.md頁面）不會發佈至面對客戶的檔案**

## 目錄

+ 位於使用手冊根目錄的`TOC.md`提供此解決方案使用手冊中包含的主題組織。
+ 每個使用手冊都有自己的唯一`TOC.md`，您可以視需要排序所有頁面/主題。
+ 所有使用手冊的第一頁都是`overview.md`。

## 使用者指南

+ 使用手冊的簡介稱為`overview.md`
+ 使用手冊中的每個主題都有自己的不同目錄。
   + 如果指南中有名為&#x200B;*實作*&#x200B;的主題，則對應的目錄為`/implementation`
+ 所有影像資產都儲存在使用手冊根目錄的`/assets`中。
   + `/assets`目錄中的所有影像都會翻譯。
   + `/no-localize`目錄中的任何影像都不會翻譯（令人驚訝！）。 這可用來確保在loc版本中特定資產不會不必要地重現。

## 使用手冊層級中繼資料

+ 說明使用手冊的中繼資料儲存在`TOC.md`中。 其中包括：
   + product — 產品/功能的名稱。
   + 雲端 — 此產品所屬的雲端。
   + 受眾 — 指南鎖定目標的受眾或原型。
   + 使用手冊 — 使用手冊的名稱。

## 頁面層級中繼資料

+ 說明檔案所需的中繼資料會儲存為每個個別頁面的一部分。 其中包括：
   + title — 頁面標題。
   + description — 頁面說明。
   + seo-title - seo替代標題。
   + seo-description - SEO用途的替代標題。
   + short-title - （選擇性欄位）。
   + 索引 — 是/否 — 頁面是否會根據Adobe的搜尋平台編制索引。
   + 翻譯 — 是/否 — 此頁面是否會翻譯。
   + 版本 — 主要用於AEM和Campaign，代表產品的版本。
   + private-feature-pack — 主要用於AEM。
   + beta — 此產品是否為beta版？
   + 重新導向 — 必要時可用於建立新頁面的參照。
   + doc-type：參考（預設） /疑難排解/開發人員/教學課程/ kb /白皮書。

## 更多資訊

如需更多發佈指示、風格指南、範例和其他資源，請造訪[合作檔案存放庫](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
