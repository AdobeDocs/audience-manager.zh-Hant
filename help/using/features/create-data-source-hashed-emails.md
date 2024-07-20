---
title: 設定雜湊電子郵件工作流程的資料來源
description: 瞭解如何建立資料來源，以儲存雜湊電子郵件工作流程的雜湊電子郵件。
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
source-git-commit: d55dbc4f9630e3d22dfb988f6725f33993229c48
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# 設定雜湊電子郵件工作流程的資料來源

雜湊電子郵件工作流程（例如以人物為基礎的目的地）會要求您建立資料來源以儲存雜湊電子郵件地址。

請依照下列步驟，建立和設定雜湊電子郵件的資料來源。

1. 登入您的Audience Manager帳戶並移至&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然後按一下&#x200B;**[!UICONTROL Add New]**。
1. 輸入您新資料來源的&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
1. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;下拉式功能表中，選取&#x200B;**[!UICONTROL Cross Device]**。
   ![顯示資料來源詳細資訊區段的Audience ManagerUI影像。](../features/assets/create-hashed-email-data-source.png)
1. 在&#x200B;**[!UICONTROL Data Source Settings]**&#x200B;區段中，同時選取&#x200B;**[!UICONTROL Inbound]**&#x200B;和&#x200B;**[!UICONTROL Outbound]**&#x200B;選項，並啟用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations]**&#x200B;選項。
1. 使用下拉式功能表為此資料來源選取&#x200B;**[!UICONTROL Emails(SHA256, lowercased)]**&#x200B;標籤。

   >[!IMPORTANT]
   >
   >此選項僅會將資料來源標示為包含使用該特定演演算法雜湊的資料。 Audience Manager在此步驟不會雜湊資料。 確定您計畫儲存在此資料來源中的電子郵件地址已使用[!DNL SHA256]演演算法雜湊。 否則，您將無法將其用於雜湊電子郵件工作流程。

   ![顯示資料來源設定區段的Audience ManagerUI影像。](../features/assets/data-source-settings.png)
