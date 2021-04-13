---
description: 大量請求會傳回您可在「更新」、「建立」、「估計」和「刪除」工作表中，與不同標題搭配使用的資料。
seo-description: 大量請求會傳回您可在「更新」、「建立」、「估計」和「刪除」工作表中，與不同標題搭配使用的資料。
seo-title: 大量請求
solution: Audience Manager
title: 大量請求
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 3%

---

# 大量請求{#bulk-requests}

大量請求會傳回您可在「更新」、「建立」、「估計」和「刪除」工作表中，與不同標題搭配使用的資料。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[UI中指](../../features/administration/administration-overview.md) 派的RBAC群 [!DNL Audience Manager] 組權限在中接受 [!UICONTROL Bulk Management Tools]。

[!UICONTROL Request]工作表沒有其自己的列標題集，您不需要將ID複製到任何列。 它會根據您在工具列中按一下的動作按鈕傳回資料。 此外，選用的報表功能會傳回像素觸發的頻率計數，以及數個固定時間間隔的獨特使用者計數。

若要進行大量請求，請開啟[!UICONTROL Bulk Management Tools]工作表並：

1. 按一下&#x200B;**[!UICONTROL Request]**&#x200B;頁籤。
2. 在工作表頂端的工具列中，按一下與您要處理的資料對應的請求按鈕。 您可以要求：

   * 演算法模型
   * 資料來源
   * 衍生信號
   * 目標映射
   * 演算法、規則型和已登入特徵
   * 區段
   * 特徵和區段資料夾ID

   [!DNL Audience Manager] API會將大量資料寫回至[!UICONTROL Request]工作表。

>[!NOTE]
>
>在結果中，`createTime`和`updateTime`欄會以指數符號傳回資料。 基礎日期／時間戳記以UNIX UTC時間記錄。 目前，工作表無法以可讀格式傳回日期／時間戳記。

如果您的批量更新傳回錯誤或失敗，請參閱[批量管理工具疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
