---
description: 大量更新可讓您在單一作業中編輯多個區段、特徵、模型、資料來源以及區段或特徵資料夾元素。 請依照下列指示進行大量更新。
keywords: baaam
seo-description: 大量更新可讓您在單一作業中編輯多個區段、特徵、模型、資料來源以及區段或特徵資料夾元素。 請依照下列指示進行大量更新。
seo-title: 大量更新
solution: Audience Manager
title: 大量更新
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# 大量更新{#bulk-updates}

大量更新可讓您在單一作業中編輯多個區段、特徵、模型、資料來源以及區段或特徵資料夾元素。 請依照下列指示進行大量更新。

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[UI中指派的](../../features/administration/administration-overview.md) RBAC群組權 [!DNL Audience Manager] 限在中接受 [!UICONTROL Bulk Management Tools]。

若要進行大量更新，請開啟工作 [!UICONTROL Bulk Management Tools] 表並：

1. 按一下 **[!UICONTROL Headers]** 標籤，並複製您要編輯之項目的更新標題。
2. 按一下標 **[!UICONTROL Update]** 簽。
3. 將更新標題貼入更新工作表的第一列。 請注意下列事項：

   * 更新資料夾時，需要所有標題。
   * 更新區段或特徵時，您只需要區段ID(SID)和需要變更的標題元素。 刪除未使用的標題。

4. 根據標題標籤，貼上或輸入要變更為對應欄的資料。
5. 在工作表工具列中，按一下符合您正在更新之項目的更新按鈕。
此動作會開啟對 [!UICONTROL Account Information] 話方塊。

6. 提供必要 [的登入資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ，然後按一 **[!UICONTROL Submit]**&#x200B;下。

   工作表會建立 [!UICONTROL Results] 欄。 欄會 [!UICONTROL Results] 傳回成功作業的JSON回應。 如需范 [例，請參閱](../../api/rest-api-main/rest-api-main.md) REST API。 在輸入資料之前，您的大量更新工作表看起來應類似下列：

![](assets/update.png)

如果您的大量更新傳回錯誤或失敗，請參 [閱批量管理工具疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
