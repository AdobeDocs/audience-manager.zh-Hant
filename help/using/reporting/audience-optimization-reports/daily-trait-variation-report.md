---
description: 此報表會傳回在選定日期前30天至少達到10,000次的特性清單，並在相同時間間隔內以任一方向的標準差大於或等於1.7。此報表可協助您評估特徵中獨特使用者的印象數目隨時間變化的情形。
seo-description: 此報表會傳回在選定日期前30天至少達到10,000次的特性清單，並在相同時間間隔內以任一方向的標準差大於或等於1.7。此報表可協助您評估特徵中獨特使用者的印象數目隨時間變化的情形。
seo-title: 每日特徵變化報表
solution: Audience Manager
title: 每日特徵變化報表
uuid: 4e82bb17-d447-4ec1-a4 fc-e15 b0 f1 b47 f0
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Daily Trait Variation Report {#daily-trait-variation-report}

此報表會傳回在選定日期前30天至少達到10,000次的特性清單，並在相同時間間隔內以任一方向的標準差大於或等於1.7。此報表可協助您評估特徵中獨特使用者的印象數目隨時間變化的情形。

>[!NOTE]
>
>Audience Manager中的「每日特徵變化」報表遵守CSC原則。You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

標準差會測量平均值或平均值偏離平均值(或平均值/預期值)的量。低標準差表示資料點傾向接近平均值。高標準差表示資料點分散在較大範圍內。

![](assets/daily_trait_variation.png)

Use the [!UICONTROL Date] list to select one or more dates for your report. 顏色編碼長條圖會顯示在清單底部，提供所有選取日期之所有特性之標準差範圍的視覺化表示法。黑色垂直線表示平均值。

The middle column contains a list of traits, identified by [!UICONTROL Trait ID] and [!UICONTROL Trait Name]. 按一下任何特徵，存取彈出式對話方塊，讓您從下列選項中選取：

* **僅限：** 移除報表中的所有其他特徵，並僅顯示此特徵的資料。
* **排除：** 從報表中移除此特徵，並顯示所有其他特性的資料。您可以排除多個特性。
* **檢視資料：** 可讓您顯示該列的資料。您也可以將所有列下載為文字檔。

[!UICONTROL Standard Deviation] 欄會顯示顏色編碼橫條圖，以顯示每個特徵在所選間隔上的標準差。紅色列表示負標準差(資料點傾向低於平均值)。綠條表示正面標準差的特徵(資料點傾向高於平均值)。將滑鼠移到任何列上，以顯示彈出式對話方塊，其中包含更多資訊和選項，以保留或排除該特徵並檢視更多資訊。

報表底部會顯示圖示，可讓您匯出各種格式的資料、回復您對報表所做的變更(例如排除特性)、啓用或停用自動更新，以及重新整理報表的資料。See [Report Icons and Tools Explained](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## 使用個案 {#use-cases}

**範例#1**：在您擁有高季節性等級特徵的情況下，此報告非常有用。例如，假設您的線上商店正在測試各種類型和價格的季節性促銷活動。You have the following traits defined in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Say you run the [!UICONTROL Daily Trait Variation] report on the 20th of December and you notice a solid positive deviation on the above mentioned traits in the past 30 days. 這可以建議您的訪客尋找您季節性促銷活動中提及的產品。為了利用這個趨勢，您可以對對客戶感興趣的訪客，投入更多心力鎖定特定產品類別的目標群體。

**範例#2**：此報表可協助您識別與標記問題或特徵錯誤設定相關的定位異常。假設您已根據線上商店的類別定義下列特徵：

* `productPage == "smartphones"`

由於您的商店重新設定，您根據品牌名稱將智慧型手機頁面分割為多頁。However, you forget to update the traits defined in [!DNL Audience Manager].

One month later, you run the [!UICONTROL Daily Trait Variation] report and notice a large negative deviation on the `productPage == "smartphones"` trait, although your visitor number has increased, according to your site analytics. Based on this information, you realize that you haven't updated the traits in [!DNL Audience Manager] for your new product pages, so you know that you need to create the following traits:

* productPage==「Samsung」
* productPage==「apple」
* productPage==「weahouse」

在完成這項作業後，您將看到符合新建立特徵的受眾。
