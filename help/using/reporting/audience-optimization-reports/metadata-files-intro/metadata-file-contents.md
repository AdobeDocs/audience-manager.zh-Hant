---
description: 根據這些規格格式化觀眾最佳化中繼資料檔案的內容。
seo-description: 根據這些規格格式化觀眾最佳化中繼資料檔案的內容。
seo-title: 中繼資料檔案的內容格式
solution: Audience Manager
title: 中繼資料檔案的內容格式
uuid: 9ba44738-3e17-40c7-9e8c-5abd8661e16d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Content Format for Metadata Files{#content-format-for-metadata-files}

根據這些規格格式化觀眾最佳化中繼資料檔案的內容。

## 語法 {#syntax}

下列語法定義中繼資料檔案中格式良好內容的結構。Note, *italics* indicates a variable placeholder.

**語法：***內容ID* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

The third column **-1** is technically the Parent ID, which is a legacy field. The value should always be set as **-1**.

>[!NOTE]
>
>請注意，每個維度需要一個中繼資料檔案，所以儲存貯體中需要多個中繼資料檔案。The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**使用^ a(control-A或ASCII001)分隔檔案項目**

Use `^a` (control-A or ASCII 001) to separate content in your metadata files. 因為這些是非列印字元，上述語法範例顯示一個垂直號」|「僅供展示用途。

If needed, you may download the example file - [20181105_0_1](assets/20181105_0_1.zip). 解壓縮並編輯您選擇的編輯器並根據實際中繼資料內容進行調整，因為它已包含必要的分隔字元。

>[!IMPORTANT]
>
>請勿將標題列新增至中繼資料檔案。

## 範例 {#examples}

讓我們來看看如何在中繼資料檔案中建構內容。此結構的一部分取決於維度。The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign** 

在此範例中，檔案標題為20180921_0_1，而檔案中的三欄為：促銷活動ID、名稱和父ID。

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creative**

在此範例中，檔案標題為20180827_0_2，而檔案中的三欄為：Creative ID、名稱和父ID。

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**網站**

在此範例中，檔案標題為20180921_0_5，而檔案中的三欄為：網站ID、名稱和父ID。

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
