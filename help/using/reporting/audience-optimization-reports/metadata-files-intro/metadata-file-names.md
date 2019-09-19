---
description: 根據這些規格命名您的「對象最佳化」中繼資料檔案。
seo-description: 根據這些規格命名您的「對象最佳化」中繼資料檔案。
seo-title: 中繼資料檔案的命名慣例
solution: Audience Manager
title: 中繼資料檔案的命名慣例
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 中繼資料檔案的命名慣例{#naming-conventions-for-metadata-files}

根據這些規格命名您的「對象最佳化」中繼資料檔案。

## 語法和ID類別 {#syntax}

下列語法定義格式良好的中繼資料檔案名稱的結構。 Note, *italics* indicates a variable placeholder. 其他元素是常數，不會變更。

**語法:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*請勿在中繼資料檔案* （.txt或其他檔案）中使用副檔名。

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* 中間的元 **件** 0在技術上是父ID，是舊版欄位。 值應始終設定為 **0**。
* 子ID的值可以介於1和10之間，具體取決於維度。 請檢視下列項目: 

## 子ID維度 {#child-dimension}

在中繼資料檔案名稱中，子ID是一種識別碼，可將檔案中的資料類型分類，並將其放入階層中。 您可以使用下列類別ID，在檔案名稱中標籤子ID:

1. 促銷活動
1. 創意
1. 位置
1. Exchange
1. 網站
1. 廣告商(若在資料來源中使用 [整合碼](../../../features/manage-datasources.md#details))
1. 插入順序(IO)
1. 垂直（即「電腦」、「汽車」、「房地產」等特定產業或商業類別）
1. 戰術
1. 業務單位或品牌

## 範例 {#example}

對於Creative中繼資料檔案，檔案名稱可能是20190115_0_2。

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
