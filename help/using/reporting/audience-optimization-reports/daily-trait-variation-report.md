---
description: 此報表返回在選定日期之前的30天內至少實現了10,000次的特性清單，並且在同一時間間隔內的任一方向上的標準偏差大於或等於1.7。 該報告可幫助您評估某個特性中的獨特用戶的印象數隨時間的變化如何。
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: 每日特徵變化報表
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 1%

---

# 每日特徵變化報表 {#daily-trait-variation-report}

此報表返回在選定日期之前的30天內至少實現了10,000次的特性清單，並且在同一時間間隔內的任一方向上的標準偏差大於或等於1.7。 該報告可幫助您評估某個特性中的獨特用戶的印象數隨時間的變化如何。

>[!NOTE]
>
>Audience Manager中的Daily Trait Variation報告遵循RBAC原則。 您只能從您有權訪問的資料源中根據 [RBAC用戶組](/help/using/features/administration/administration-overview.md) 屬於你。

標準差測量與平均值（或平均/預期值）的偏差或偏差量。 標準偏差較低，表明資料點趨近於均值。 高標準偏差表示資料點在大範圍值上分佈。

![](assets/daily_trait_variation.png)

使用 [!UICONTROL Date] 清單，選擇報表的一個或多個日期。 在清單底部顯示一個彩色編碼條形圖，該條形圖提供所有選定日期所有特徵的標準偏差範圍的可視表示。 黑色垂直線表示平均值。

中間列包含由 [!UICONTROL Trait ID] 和 [!UICONTROL Trait Name]。 按一下任何特性以訪問彈出對話框，該對話框允許您從以下選項中進行選擇：

* **僅保留：** 從報告中刪除所有其他特徵，並僅顯示該特徵的資料。
* **排除：** 從報告中刪除此特性並顯示所有其他特性的資料。 可以排除多個特徵。
* **查看資料：** 用於顯示該行的資料。 您還可以將所有行作為文本檔案下載。

的 [!UICONTROL Standard Deviation] 列顯示顏色編碼的條形圖，這些條形圖顯示選定間隔內每個特徵的標準差。 紅條表示標準偏差為負的特徵（資料點往往低於平均值）。 綠條表示標準偏差為正的特徵（資料點往往高於平均值）。 將滑鼠移到任何欄上，以顯示一個彈出對話框，其中包含更多資訊和選項，以保留或排除該特性並查看更多資訊。

表徵圖顯示在報表底部，您可以以各種格式導出資料、還原對報表可能進行的任何更改（如排除特徵）、啟用或禁用自動更新以及刷新報表資料。 請參閱 [報告表徵圖和說明的工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)。

## 使用個案 {#use-cases}

**示例#1**:此報告在具有高季節性特徵的情況下非常有用。 例如，假設您的線上商店正在測試各種類型和價格的季節性促銷。 您具有以下特徵，定義於 [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

說你負責 [!UICONTROL Daily Trait Variation] 12月20日的報告，您注意到過去30天上述性狀存在明顯的正偏差。 這可能表明您的訪客正在尋找您在季節性促銷中提及的產品。 為了利用這一趨勢，您可以投入更多精力，針對對其感興趣的訪客，針對特定產品類別的創意人士。

**示例#2**:此報告可以幫助您確定與標籤問題或特性錯誤配置相關的目標異常。 假設您根據線上商店的類別定義了以下特性：

* `productPage == "smartphones"`

由於您的商店重新配置，您正在根據品牌名稱將智慧手機頁面拆分為多個頁面。 但是，您忘記更新中定義的特徵 [!DNL Audience Manager]。

一個月後，你 [!UICONTROL Daily Trait Variation] 報告並注意到 `productPage == "smartphones"` 性狀，儘管根據網站分析，訪客數量有所增加。 根據這些資訊，您意識到您尚未更新 [!DNL Audience Manager] 為新產品頁建立，因此您知道需要建立以下特徵：

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

一旦你這樣做，你將看到你的觀眾符合新創造的特徵。
