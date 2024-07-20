---
description: 此報表會傳回在選取日期前30天內已實現至少10,000次且在相同時間間隔內任一方向的標準差大於或等於1.7的特徵清單。 報表可協助您評估某個特徵中來自不重複使用者的曝光次數在一段時間內的波動情況。
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: 每日特徵變化報表
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# 每日特徵變化報表 {#daily-trait-variation-report}

此報表會傳回在選取日期前30天內已實現至少10,000次且在相同時間間隔內任一方向的標準差大於或等於1.7的特徵清單。 報表可協助您評估某個特徵中來自不重複使用者的曝光次數在一段時間內的波動情況。

>[!NOTE]
>
>Audience Manager中的每日特徵變化報表會遵循RBAC原則。 您只能根據您所屬的[RBAC使用者群組](/help/using/features/administration/administration-overview.md)，從您有權存取的資料來源檢視特徵。

標準偏差會測量平均值（或平均/預期值）的偏差或分散程度。 較低的標準差表示資料點趨向於非常接近平均值。 高標準差表示資料點分散在很大的值範圍內。

![](assets/daily_trait_variation.png)

使用[!UICONTROL Date]清單為您的報告選取一或多個日期。 以色彩標示的長條圖會顯示在清單底部，以視覺化方式代表所有選定日期中所有特徵的標準差範圍。 黑色的垂直線表示平均值。

中間欄包含特徵清單，由[!UICONTROL Trait ID]和[!UICONTROL Trait Name]識別。 按一下任何特徵可存取快顯對話方塊，讓您從下列選項中選取：

* **僅保留：**&#x200B;從報表中移除所有其他特徵，並僅顯示此特徵的資料。
* **排除：**&#x200B;從報表中移除此特徵，並顯示所有其他特徵的資料。 您可以排除多個特徵。
* **檢視資料：**&#x200B;可讓您顯示該列的資料。 您也可以將所有列下載為文字檔。

[!UICONTROL Standard Deviation]欄會顯示以色彩標示的長條圖，其中顯示所選間隔內每個特徵的標準差。 紅色長條表示具有負標準差的特徵（資料點傾向於低於平均值）。 綠色長條圖表示具有正標準差的特徵（資料點傾向於高於平均值）。 將滑鼠移至任一長條圖上，即可顯示快顯對話方塊，其中含有更多資訊和選項，可保留或排除該特徵，並檢視更多資訊。

圖示會顯示在報表底部，可讓您匯出各種格式的資料、回覆您可能對報表所做的任何變更（例如排除特徵）、啟用或停用自動更新，以及重新整理報表資料。 請參閱[報表圖示和工具說明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)。

## 使用個案 {#use-cases}

**範例#1**：此報告在您具有季節性等級高的特徵時非常有用。 例如，假設您的線上商店正在測試各種型別和價格的季節性促銷活動。 您在[!DNL Audience Manager]中定義了下列特徵：

* `productPage == "December Promotion"`
* `price > "500"`

假設您在12月20日執行[!UICONTROL Daily Trait Variation]報表，並且您注意到過去30天內上述特徵有確實的正數偏差。 這可能表示您的訪客正在尋找季節性促銷活動中提到的產品。 若要利用此趨勢，您可以投入更多精力針對特定產品類別的創意內容，鎖定對創意內容感興趣的訪客。

**範例#2**：此報表可協助您識別與標籤問題或特徵設定錯誤相關的目標定位異常。 假設您已根據線上商店的類別定義下列特徵：

* `productPage == "smartphones"`

由於商店重新設定，您將智慧型手機頁面根據品牌名稱分割為多個頁面。 不過，您忘記更新[!DNL Audience Manager]中定義的特徵了。

一個月後，您執行[!UICONTROL Daily Trait Variation]報告並注意到`productPage == "smartphones"`特徵上有很大的負數偏差，儘管您的訪客人數已增加（根據您的網站分析）。 根據此資訊，您意識到您尚未針對新產品頁面更新[!DNL Audience Manager]中的特徵，因此您知道您需要建立以下特徵：

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

完成此操作後，您就會看到對象符合新建立特徵的資格。
