---
description: 批量請求返回資料，您可以在「更新」、「建立」、「估計」和「刪除」工作表中與不同的題頭一起使用。
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: 大量請求
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 2%

---

# 大量請求{#bulk-requests}

批量請求返回資料，您可以在「更新」、「建立」、「估計」和「刪除」工作表中與不同的題頭一起使用。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC組權限](../../features/administration/administration-overview.md) 在 [!DNL Audience Manager] UI在 [!UICONTROL Bulk Management Tools]。

的 [!UICONTROL Request] 工作表沒有其自己的列標題集，您也不需要將ID複製到任何列。 相反，它會根據您在工具欄中按一下的操作按鈕返回資料。 而且，可選報告功能返回像素觸發的頻率計數和多個固定時間間隔的唯一用戶計數。

要進行批量請求，請開啟 [!UICONTROL Bulk Management Tools] 工作表和：

1. 按一下 **[!UICONTROL Request]** 頁籤。
2. 在工作表頂部的工具欄中，按一下與要處理的資料對應的請求按鈕。 您可以請求：

   * 算法模型
   * 資料源
   * 派生信號
   * 目標映射
   * 算法、基於規則和上載特徵
   * 區段
   * 特性和段資料夾ID

   的 [!DNL Audience Manager] API將批量資料寫回 [!UICONTROL Request] 工作表。

>[!NOTE]
>
>在你的結果中， `createTime` 和 `updateTime` 列以指數表示法返回資料。 基礎日期/時間戳以UNIX UTC時間記錄。 當前，工作表無法以可讀格式返回日期/時間戳。

如果批量更新返回錯誤或失敗，請參見 [批量管理工具故障排除](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
