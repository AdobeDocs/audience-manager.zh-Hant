---
description: 此報表會傳回特徵清單，這些特徵在選取日期前30天內實現至少10,000次，且在相同時間間隔內，每個方向的標準差大於或等於1.7。 報表可協助您評估特徵中不重複使用者的曝光次數隨時間而波動的情形。
seo-description: 此報表會傳回特徵清單，這些特徵在選取日期前30天內實現至少10,000次，且在相同時間間隔內，每個方向的標準差大於或等於1.7。 報表可協助您評估特徵中不重複使用者的曝光次數隨時間而波動的情形。
seo-title: 每日特徵變化報表
solution: Audience Manager
title: 每日特徵變化報表
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: 受眾最佳化報表
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 2%

---

# 每日特徵變化報表 {#daily-trait-variation-report}

此報表會傳回特徵清單，這些特徵在選取日期前30天內實現至少10,000次，且在相同時間間隔內，每個方向的標準差大於或等於1.7。 報表可協助您評估特徵中不重複使用者的曝光次數隨時間而波動的情形。

>[!NOTE]
>
>Audience Manager中的「每日特徵變化」報表遵循RBAC原則。 您只能根據您所屬的[RBAC使用者群組](/help/using/features/administration/administration-overview.md)，查看您有權存取的資料來源特徵。

標準差會測量偏離平均值（或平均/預期值）的變異或分散量。 標準差低表示資料點往往非常接近平均值。 標準偏差高表示資料點散布在大範圍值中。

![](assets/daily_trait_variation.png)

使用[!UICONTROL Date]清單為報表選取一或多個日期。 清單底部會顯示彩色編碼長條圖，以視覺化方式呈現所有選定日期中所有特徵的標準差範圍。 黑色垂直線表示平均值。

中間欄包含由[!UICONTROL Trait ID]和[!UICONTROL Trait Name]識別的特徵清單。 按一下任何特徵以存取快顯對話方塊，讓您從下列選項中選取：

* **僅保留：** 從報表中移除所有其他特徵，並僅顯示此特徵的資料。
* **排除：** 從報表中移除此特徵，並顯示所有其他特徵的資料。您可以排除多個特徵。
* **檢視資料：** 可讓您顯示該列的資料。您也可以以文字檔案的形式下載所有列。

[!UICONTROL Standard Deviation]欄顯示彩色編碼長條圖，顯示所選間隔內每個特徵的標準差。 紅色長條表示具有負標準差的特徵（資料點通常低於平均值）。 綠色長條表示特徵有正標準差（資料點傾向高於平均值）。 將滑鼠移至任何長條以顯示彈出式對話方塊，其中包含保留或排除該特徵的詳細資訊和選項，以及檢視詳細資訊。

圖示會顯示在報表底部，可讓您以各種格式匯出資料、還原對報表所可能進行的任何變更（例如排除特徵）、啟用或停用自動更新，以及重新整理報表的資料。 請參閱[報表圖示和說明的工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)。

## 使用個案 {#use-cases}

**範例1**:若您有具有高季節性水準特徵，此報表將相當實用。例如，假設您的線上商店正在測試各種類型和價格的季節性促銷活動。 您在[!DNL Audience Manager]中定義下列特徵：

* `productPage == "December Promotion"`
* `price > "500"`

假設您在12月20日執行[!UICONTROL Daily Trait Variation]報表，並注意到過去30天內上述特徵有明顯的正偏差。 這可能表示您的訪客正在尋找您在季節性促銷中提及的產品。 若要利用此趨勢，您可投入更多精力，將特定產品類別的創意內容鎖定在對其感興趣的訪客上。

**範例2**:此報表可協助您識別與標籤問題或特徵錯誤設定相關的定位異常。假設您已根據線上商店的類別定義下列特徵：

* `productPage == "smartphones"`

由於您的商店重新配置，您會根據品牌名稱將智慧手機頁面分割為多個頁面。 不過，您應忘記更新[!DNL Audience Manager]中定義的特徵。

一個月後，您執行[!UICONTROL Daily Trait Variation]報表，並注意到`productPage == "smartphones"`特徵出現大的負偏差，但根據您的網站分析，您的訪客數量已增加。 根據這些資訊，您發現尚未針對新產品頁面更新[!DNL Audience Manager]中的特徵，因此您知道需要建立下列特徵：

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

執行此動作後，您會看到對象符合新建立特徵的資格。
