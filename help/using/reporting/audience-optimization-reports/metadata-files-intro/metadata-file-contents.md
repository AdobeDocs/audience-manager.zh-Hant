---
description: 根據這些規格，格式化您的「對象最佳化」中繼資料檔案的內容。
seo-description: 根據這些規格，格式化您的「對象最佳化」中繼資料檔案的內容。
seo-title: 中繼資料檔案的內容格式
solution: Audience Manager
title: 中繼資料檔案的內容格式
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 5%

---


# 中繼資料檔案的內容格式{#content-format-for-metadata-files}

根據這些規格，格式化您的「對象最佳化」中繼資料檔案的內容。

## 語法 {#syntax}

下列語法定義中繼資料檔案中格式正確的內容結構。 Note, *italics* indicates a variable placeholder.

**語法：**  *內容ID* |名 *稱* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

第三欄 **-1** ，技術上是父ID，是舊版欄位。 值應始終設定為 **-1**。

>[!NOTE]
>
>請注意，每個維度需要一個中繼資料檔案，因此儲存貯體中需要多個中繼資料檔案。 維度會列在「中繼資料檔案 [的命名慣例」文章中](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)。

**使用^a（control-A或ASCII 001）分隔檔案項目**

使 `^a` 用（control-A或ASCII 001）來分隔中繼資料檔案中的內容。 由於這些字元是非列印字元，上述語法範例只會顯示垂直號&quot;|&quot;以供顯示。

如有需要，您可下載範例檔 [案- 20181105_0_1](assets/20181105_0_1.zip)。 將它解壓縮並在您選擇的編輯器中編輯，並根據實際的中繼資料內容進行調整，因為它已包含必要的分隔字元。

>[!IMPORTANT]
>
>請勿將標題列新增至中繼資料檔案。

## 範例 {#examples}

讓我們來看看如何在中繼資料檔案中建構內容。 此結構的一部分取決於尺寸。 維度會列在「中繼資料檔案 [的命名慣例」文章中](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)。

**Campaign** 

在此範例中，檔案標題為20180921_0_1，檔案中的三欄為： 促銷活動ID、名稱和父ID。

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**創意**

在此範例中，檔案標題為20180827_0_2，檔案中的三欄為： Creative ID、Name和Parent ID。

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**網站**

在此範例中，檔案標題為20180921_0_5，檔案中的三欄為： 網站ID、名稱和父ID。

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
