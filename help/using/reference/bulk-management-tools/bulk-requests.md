---
description: 大量請求會傳回可在「更新」、「建立」、「預估」和「刪除」工作表中與不同標題搭配使用的資料。
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: 大量請求
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 大量請求{#bulk-requests}

大量請求會傳回可在「更新」、「建立」、「預估」和「刪除」工作表中與不同標題搭配使用的資料。

>[!IMPORTANT]
>
>大量管理工具並非正式支援的Adobe產品。 客戶服務提供的疑難排解與支援將依個別情況處理。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>在[ UI中指派的](../../features/administration/administration-overview.md)RBAC群組許可權[!DNL Audience Manager]已在[!UICONTROL Bulk Management Tools]中接受。

[!UICONTROL Request]工作表沒有自己的欄標題集，您不需要將ID複製到任何欄。 而是會根據您在工具列中按一下之動作按鈕傳回資料。 此外，選用的報表功能會傳回畫素引發的頻率計數，以及數個固定時間間隔的不重複使用者計數。

若要進行大量請求，請開啟[!UICONTROL Bulk Management Tools]工作表並：

1. 按一下「**[!UICONTROL Request]**」標籤。
2. 在工作表頂端的工具列中，按一下與您要使用之資料對應的請求按鈕。 您可以要求：

   * 演演算法模型
   * 資料來源
   * 衍生訊號
   * 目的地對應
   * 演演算法、規則型和已上線的特徵
   * 區段
   * 特徵和區段資料夾ID

   [!DNL Audience Manager] API會將大量資料寫入回[!UICONTROL Request]工作表。

>[!NOTE]
>
>在您的結果中，`createTime`和`updateTime`欄會以指數表示法傳回資料。 基礎日期/時間戳記會以UNIX UTC時間記錄。 目前，工作表無法傳回可讀格式的日期/時間戳記。

如果大量更新傳回錯誤或失敗，請參閱[大量管理工具的疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
