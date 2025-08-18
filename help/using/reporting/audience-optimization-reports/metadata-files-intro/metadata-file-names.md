---
description: 根據這些規格為您的Audience Optimization中繼資料檔案命名。
seo-description: Name your Audience Optimization metadata file according to these specifications.
seo-title: Naming Conventions for Metadata Files
solution: Audience Manager
title: 中繼資料檔案的命名慣例
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 2%

---

# 中繼資料檔案的命名慣例{#naming-conventions-for-metadata-files}

根據這些規格為您的Audience Optimization中繼資料檔案命名。

## 語法和ID類別 {#syntax}

下列語法定義格式正確的中繼資料檔案名稱的結構。 請注意，*斜體*&#x200B;表示變數預留位置。 其他元素則是常數，不會變更。

**語法：** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*請勿*&#x200B;在中繼資料檔案（.txt或其他）中使用副檔名。

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* 中間元件&#x200B;**0**&#x200B;從技術上講是父系ID，這是舊版欄位。 值應一律設為&#x200B;**0**。
* 視維度而定，子項ID的值可能介於1到10之間。 請檢視下列項目: 

## 子ID維度 {#child-dimension}

在中繼資料檔案名稱中，子ID是可將檔案中的資料型別分類並將其置於階層中的識別碼。 您可以使用以下類別ID在檔案名稱中標籤子ID：

1. 促銷活動
1. Creative
1. 產品建議放置環境
1. Exchange
1. 網站
1. 廣告商（如果在[資料來源](../../../features/manage-datasources.md#details)中使用整合程式碼）
1. 插入順序(IO)
1. 垂直（亦即，特定產業或業務類別，例如「電腦」、「汽車」、「房地產」等）
1. 策略
1. 業務單位或品牌

## 範例 {#example}

若為Creative中繼資料檔案，檔案名稱可以是20190115_0_2。

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
