---
description: 此報告會傳回在選取日期前30天內至少實現10,000次的特性清單，並在相同時間間隔內，在任一方向的標準差大於或等於1.7。 此報表可協助您評估來自特徵中獨特使用者的印象數隨時間的波動。
seo-description: 此報告會傳回在選取日期前30天內至少實現10,000次的特性清單，並在相同時間間隔內，在任一方向的標準差大於或等於1.7。 此報表可協助您評估來自特徵中獨特使用者的印象數隨時間的波動。
seo-title: 每日特徵變化報表
solution: Audience Manager
title: 每日特徵變化報表
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---


# 每日特徵變化報表 {#daily-trait-variation-report}

此報告會傳回在選取日期前30天內至少實現10,000次的特性清單，並在相同時間間隔內，在任一方向的標準差大於或等於1.7。 此報表可協助您評估來自特徵中獨特使用者的印象數隨時間的波動。

>[!NOTE]
>
>Audience Manager中的「每日特徵變化」報表符合RBAC原則。 您只能根據您所屬的[RBAC用戶組](/help/using/features/administration/administration-overview.md)，查看您有權訪問的資料源中的特徵。

標準差會測量與平均值（或平均／預期值）的偏差或偏差量。 標準差低表示資料點趨近於平均值。 高標準差表示資料點分佈在大範圍值上。

![](assets/daily_trait_variation.png)

使用[!UICONTROL Date]清單為報表選取一或多個日期。 在清單底部會顯示色彩編碼長條圖，以視覺化方式呈現所有選定日期之所有特徵的標準差範圍。 黑色垂直線表示平均值。

中間欄包含由[!UICONTROL Trait ID]和[!UICONTROL Trait Name]識別的特徵清單。 按一下任何特徵以存取快顯對話方塊，讓您從下列選項中選取：

* **僅保留：** 從報表中移除所有其他特徵，並僅顯示此特徵的資料。
* **排除：從** 報表中移除此特徵，並顯示所有其他特徵的資料。您可以排除多個特徵。
* **檢視資料：** 可讓您顯示該列的資料。您也可以將所有列下載為文字檔案。

[!UICONTROL Standard Deviation]欄會顯示色彩編碼長條圖，顯示所選間隔內每個特徵的標準差。 紅條表示標準差為負的特徵（資料點通常低於平均值）。 綠條表示具有正標準差的特徵（資料點往往高於平均值）。 將滑鼠指標暫留在任何列上，以顯示快顯對話方塊，其中包含更多資訊和選項，以保留或排除該特徵並檢視更多資訊。

圖示會顯示在報表底部，可讓您以各種格式匯出資料、回復您對報表所做的任何變更（例如排除特徵）、啟用或停用自動更新，以及重新整理報表的資料。 請參閱[報表圖示和說明的工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)。

## 使用個案 {#use-cases}

**範例#1**:在您有具有高季節性等級的特性時，此報表非常有用。例如，假設您的線上商店正在測試各種類型和價格的季節性促銷活動。 您有下列在[!DNL Audience Manager]中定義的特徵：

* `productPage == "December Promotion"`
* `price > "500"`

假設您在12月20日執行[!UICONTROL Daily Trait Variation]報表，並注意到過去30天內上述特徵有明顯的正面偏差。 這可能表示您的訪客正在尋找您季節性促銷中提及的產品。 若要利用此趨勢，您可以投入更多精力，針對對該特定產品類別感興趣的訪客定位創意素材。

**範例#2**:此報告可協助您識別與標籤問題或特徵錯誤設定相關的定位異常。假設您已根據線上商店的類別定義下列特徵：

* `productPage == "smartphones"`

由於您的商店重新配置，您會根據品牌名稱，將智慧型手機頁面分割為多個頁面。 不過，您忘記更新[!DNL Audience Manager]中定義的特徵。

一個月後，您會執行[!UICONTROL Daily Trait Variation]報表，並注意到`productPage == "smartphones"`特徵上有很大的負偏差，不過根據您的網站分析，您的訪客數量已增加。 根據這些資訊，您會發現您尚未更新新產品頁面的[!DNL Audience Manager]特徵，因此您知道您必須建立下列特徵：

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

完成此作業後，您會看到您的受眾符合新建立特徵的資格。
