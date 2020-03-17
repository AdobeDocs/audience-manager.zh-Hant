---
description: 大量請求會傳回您可在「更新」、「建立」、「估計」和「刪除」工作表中，與不同標題搭配使用的資料。
seo-description: 大量請求會傳回您可在「更新」、「建立」、「估計」和「刪除」工作表中，與不同標題搭配使用的資料。
seo-title: 大量請求
solution: Audience Manager
title: 大量請求
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# 大量請求{#bulk-requests}

大量請求會傳回您可在「更新」、「建立」、「估計」和「刪除」工作表中，與不同標題搭配使用的資料。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[UI中指派的](../../features/administration/administration-overview.md) RBAC群組權 [!DNL Audience Manager] 限在中接受 [!UICONTROL Bulk Management Tools]。

工 [!UICONTROL Request] 作表沒有其自己的列標題集，您也不需要將ID複製到任何列。 它會根據您在工具列中按一下的動作按鈕傳回資料。 此外，選用的報表功能會傳回像素觸發的頻率計數，以及數個固定時間間隔的獨特使用者計數。

若要進行大量請求，請開啟工作 [!UICONTROL Bulk Management Tools] 表並：

1. 按一下標 **[!UICONTROL Request]** 簽。
2. 在工作表頂端的工具列中，按一下與您要處理的資料對應的請求按鈕。 您可以要求：

   * 演算法模型
   * 資料來源
   * 衍生信號
   * 目標映射
   * 演算法、規則型和已登入特徵
   * 區段
   * 特徵和區段資料夾ID
   API [!DNL Audience Manager] 會將大量資料寫回工作 [!UICONTROL Request] 表。

>[!NOTE]
>
>在結果中，和列 `createTime` 以指數 `updateTime` 表示法返回資料。 基礎日期／時間戳記以UNIX UTC時間記錄。 目前，工作表無法以可讀格式傳回日期／時間戳記。

如果您的大量更新傳回錯誤或失敗，請參 [閱批量管理工具疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
