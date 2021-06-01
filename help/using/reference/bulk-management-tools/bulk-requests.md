---
description: 大量請求會傳回資料，供您在「更新」、「建立」、「預估」和「刪除」工作表中搭配不同標題使用。
seo-description: 大量請求會傳回資料，供您在「更新」、「建立」、「預估」和「刪除」工作表中搭配不同標題使用。
seo-title: 大量請求
solution: Audience Manager
title: 大量請求
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 3%

---

# 大量請求{#bulk-requests}

大量請求會傳回資料，供您在「更新」、「建立」、「預估」和「刪除」工作表中搭配不同標題使用。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[UI中](../../features/administration/administration-overview.md) 指派的RBAC [!DNL Audience Manager] 群組權限會遵循 [!UICONTROL Bulk Management Tools]。

[!UICONTROL Request]工作表沒有自己的一組列標題，您不需要將ID複製到任何列。 而是會根據您在工具列中按一下的動作按鈕，傳回資料。 此外，選用的報表功能會傳回像素觸發的頻率計數，以及數個固定時間間隔的不重複使用者計數。

若要提出大量請求，請開啟[!UICONTROL Bulk Management Tools]工作表，然後：

1. 按一下&#x200B;**[!UICONTROL Request]**&#x200B;標籤。
2. 在工作表頂端的工具列中，按一下與您要處理之資料相對應的請求按鈕。 您可以要求：

   * 演算法模型
   * 資料來源
   * 衍生訊號
   * 目標對應
   * 演算法、規則型和已上線特徵
   * 區段
   * 特徵和區段資料夾ID

   [!DNL Audience Manager] API會將大量資料寫回[!UICONTROL Request]工作表。

>[!NOTE]
>
>在結果中，`createTime`和`updateTime`欄會以指數記號傳回資料。 基礎日期/時間戳記以UNIX UTC時間記錄。 目前，工作表無法以可讀格式傳回日期/時間戳記。

如果您的批量更新返回錯誤或失敗，請參閱[批量管理工具的故障排除](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
