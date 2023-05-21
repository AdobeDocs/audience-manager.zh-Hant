---
description: 根據這些規範命名Audience Optimization元資料檔案。
seo-description: Name your Audience Optimization metadata file according to these specifications.
seo-title: Naming Conventions for Metadata Files
solution: Audience Manager
title: 中繼資料檔案的命名慣例
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 8%

---

# 中繼資料檔案的命名慣例{#naming-conventions-for-metadata-files}

根據這些規範命名Audience Optimization元資料檔案。

## 語法和ID類別 {#syntax}

以下語法定義格式良好的元資料檔案名的結構。 注意， *斜體* 指示變數佔位符。 其它元素是常數，不更改。

**語法:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*不要* 在元資料檔案（.txt或其他檔案）中使用檔案副檔名。

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* 中間元件 **0** 嚴格來說是「父ID」，它是舊欄位。 值應始終設定為 **0**。
* 子ID的值可以介於1和10之間，具體取決於尺寸。 請檢視下列項目: 

## 子ID維 {#child-dimension}

在元資料檔案名中，子ID是標識符，它將檔案中的資料類型分類並將其放入層次結構中。 可以使用以下類別ID在檔案名中標籤子ID:

1. 促銷活動
1. 創意
1. 位置
1. Exchange
1. 站點
1. 廣告商(如果在 [資料源](../../../features/manage-datasources.md#details))
1. 插入順序(IO)
1. 垂直（即「電腦」、「汽車」、「房地產」等特定行業或業務類別）
1. 戰術
1. 業務單位或品牌

## 範例 {#example}

對於Creative元資料檔案，檔案名可能為20190115_0_2。

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
