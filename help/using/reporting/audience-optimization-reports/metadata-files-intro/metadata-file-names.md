---
description: 根據這些規格為您的「對象最佳化」中繼資料檔案命名。
seo-description: 根據這些規格為您的「對象最佳化」中繼資料檔案命名。
seo-title: 中繼資料檔案的命名慣例
solution: Audience Manager
title: 中繼資料檔案的命名慣例
uuid: cab55b2a-2e54-45f6-aea-3735b911 f821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Naming Conventions for Metadata Files{#naming-conventions-for-metadata-files}

根據這些規格為您的「對象最佳化」中繼資料檔案命名。

## Syntax and ID Categories {#syntax}

下列語法定義格式良好中繼資料檔案名稱的結構。Note, *italics* indicates a variable placeholder. 其他元素是常數且不會變更。

**語法:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*請勿* 在中繼資料檔案(.txt或其他)中使用副檔名。

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* The middle component **0** is technically the Parent ID, which is a legacy field. The value should always be set as **0**.
* 子ID可以有到10之間的值，視維度而定。請檢視下列項目: 

## Child ID dimensions {#child-dimension}

在中繼資料檔案名稱中，子ID是識別檔案中資料類型並將其放入階層的識別碼。您可以將檔案名稱中的子ID標記為下列類別ID：

1. 促銷活動
1. Creative
1. 位置
1. Exchange
1. 網站
1. Advertiser (if using integration codes in a [data source](../../../features/manage-datasources.md#details))
1. 插入順序(IO)
1. 垂直(即特定產業或業務類別，例如「電腦」、「汽車車輛」、「不動產」等)
1. Tactic
1. 業務單位或品牌

## 範例 {#example}

對於Creative metadata檔案，檔案名稱可以是20190115_0_2。

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
