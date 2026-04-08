---
description: 大量請求會傳回可在「更新」、「建立」、「預估」和「刪除」工作表中與不同標題搭配使用的資料。
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: 大量請求
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
TQID: https://experienceleague.adobe.com/9VACsTAdf5nqwXAeQCqA7ME7M1sTOwt-eW-fyVdE-Ag
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 253
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
