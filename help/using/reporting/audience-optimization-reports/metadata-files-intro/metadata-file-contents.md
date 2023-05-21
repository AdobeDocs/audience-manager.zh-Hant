---
description: 根據這些規範設定Audience Optimization元資料檔案的內容格式。
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: 中繼資料檔案的內容格式
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Log Files
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# 中繼資料檔案的內容格式{#content-format-for-metadata-files}

根據這些規範設定Audience Optimization元資料檔案的內容格式。

## 語法 {#syntax}

以下語法定義元資料檔案中格式良好的內容的結構。 注意， *斜體* 指示變數佔位符。

**語法：**  *內容ID* | *名稱* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

第三欄 **-1** 嚴格來說是「父ID」，它是舊欄位。 值應始終設定為 **-1**。

>[!NOTE]
>
>請注意，每個維需要一個元資料檔案，因此儲存桶中需要多個元資料檔案。 維列在文章中 [元資料檔案的命名約定](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)。

**使用^a分隔檔案條目（control-A或ASCII 001）**

使用 `^a` （control-A或ASCII 001）來分隔元資料檔案中的內容。 由於這些字元是非打印字元，因此上面的語法示例只顯示管道「|」，僅供顯示。

如果需要，您可以下載示例檔案 —  [20181105_0_1](assets/20181105_0_1.zip)。 解壓縮它，並在所選編輯器中編輯，並根據實際元資料內容進行調整，因為它已包含所需的分隔符。

>[!IMPORTANT]
>
>不要將標題行添加到元資料檔案。

## 範例 {#examples}

讓我們看一下如何在元資料檔案中構建內容。 此結構的一部分取決於尺寸。 維列在文章中 [元資料檔案的命名約定](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)。

**Campaign** 

在本示例中，檔案標題為20180921_0_1 ，檔案中的三列為：市場活動ID、名稱和父ID。

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**創意**

在本示例中，檔案標題為20180827_0_2 ，檔案中的三列為：建立ID、名稱和父ID。

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**站點**

在本示例中，檔案標題為20180921_0_5 ，檔案中的三列為：站點ID、名稱和父ID。

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
