---
description: 根據這些規格，設定Audience Optimization中繼資料檔案內容的格式。
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: 中繼資料檔案的內容格式
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Log Files
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# 中繼資料檔案的內容格式{#content-format-for-metadata-files}

根據這些規格，設定Audience Optimization中繼資料檔案內容的格式。

## 語法 {#syntax}

下列語法定義中繼資料檔案中格式正確的內容結構。 請注意，*斜體*&#x200B;表示變數預留位置。

**語法：** *內容識別碼* | *名稱* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

第三欄&#x200B;**-1**&#x200B;在技術上為父系ID，這是舊版欄位。 值應一律設為&#x200B;**-1**。

>[!NOTE]
>
>請注意，每個維度需要一個中繼資料檔案，因此貯體中應該會有多個中繼資料檔案。 維度列在文章[中繼資料檔案的命名慣例](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)中。

**以^a （control-A或ASCII 001）分隔檔案專案**

使用`^a` （control-A或ASCII 001）來分隔中繼資料檔案中的內容。 由於這些是非列印字元，上述語法範例顯示僅供顯示用的直立線符號「|」。

如有需要，您可以下載範例檔案 — [20181105_0_1](assets/20181105_0_1.zip)。 解壓縮並在您選擇的編輯器中編輯，並根據實際中繼資料內容進行調整，因為其中已包含必要的分隔字元。

>[!IMPORTANT]
>
>請勿將標題列新增至中繼資料檔案。

## 範例 {#examples}

讓我們來看看您如何在中繼資料檔案中建構內容。 此結構的一部分取決於維度。 維度列在文章[中繼資料檔案的命名慣例](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)中。

**Campaign** 

在此範例中，檔案標題為20180921_0_1，而檔案中的三欄為：促銷活動ID、名稱和上層ID。

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**創意**

在此範例中，檔案標題為20180827_0_2，而檔案中的三欄為：創作ID、名稱和上層ID。

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**網站**

在此範例中，檔案標題為20180921_0_5，檔案中的三欄為：網站ID、名稱和父項ID。

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
