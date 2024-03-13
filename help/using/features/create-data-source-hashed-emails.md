---
title: 設定雜湊電子郵件工作流程的資料來源
description: 瞭解如何建立資料來源，以儲存雜湊電子郵件工作流程的雜湊電子郵件。
solution: Audience Manager
feature: Data Sources
source-git-commit: 903c2602f759e0d507e45f1db4cbc880a599c32e
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---


# 設定雜湊電子郵件工作流程的資料來源

雜湊電子郵件工作流程（例如以人物為基礎的目的地）會要求您建立資料來源以儲存雜湊電子郵件地址。

請依照下列步驟，建立和設定雜湊電子郵件的資料來源。

1. 登入您的Audience Manager帳戶並移至 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然後按一下 **[!UICONTROL Add New]**.
1. 輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 新資料來源的ID。
1. 在 **[!UICONTROL ID Type]** 下拉式功能表，選取 **[!UICONTROL Cross Device]**.
   ![顯示「資料來源詳細資料」區段的Audience ManagerUI影像。](../features/assets/create-hashed-email-data-source.png)
1. 在 **[!UICONTROL Data Source Settings]** 區段，選取兩者 **[!UICONTROL Inbound]** 和 **[!UICONTROL Outbound]** 選項，並啟用 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 選項。
1. 使用下拉式功能表選取 **[!UICONTROL Emails(SHA256, lowercased)]** 此資料來源的標籤。

   >[!IMPORTANT]
   >
   >此選項僅會將資料來源標示為包含使用該特定演演算法雜湊的資料。 Audience Manager在此步驟不會雜湊資料。 確定您計畫儲存在此資料來源中的電子郵件地址已使用 [!DNL SHA256] 演演算法。 否則，您將無法將其用於雜湊電子郵件工作流程。

   ![顯示資料來源設定區段的Audience ManagerUI影像。](../features/assets/data-source-settings.png)

