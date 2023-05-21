---
description: DCS監視它接收的ID，並將在短時間內以異常高的速率發送的ID添加到拒絕清單。
keywords: id；監控；dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: ID監控和密碼清單
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# ID監控和密碼清單

的 [!DNL DCS] 監視其接收的ID，並將在短時間內以異常高的速率發送的ID添加到拒絕清單。

## 概述

為保護Audience Manager基礎架構免受惡意活動的影響， [!DNL DCS] 使用高級算法來監視接收的ID。 這些可以是 [!UICONTROL Data Provider Unique User ID]s([!UICONTROL CRM ID]s) [!UICONTROL Audience Manager Unique User ID]s([!UICONTROL AAM UUID]s，或 [!UICONTROL Experience Cloud ID]s([!UICONTROL ECID]s)。 請參閱 [Audience Manager中ID的索引](../../../reference/ids-in-aam.md) 有關Audience Manager支援的ID的詳細說明。

的 [!DNL DCS] 監視接收這些ID的頻率，以檢測潛在的惡意活動。 當 [!DNL DCS] 檢測到異常大量 [!DNL DCS] 請求任何給定的ID，該ID將添加到拒絕清單。

## 錯誤代碼

您可以通過從 [!DNL DCS]。 您可能收到的錯誤代碼是：

* 303:阻止的客戶ID;
* 306:已阻止聲明的設備ID;
* 307:ID的配置檔案操作被阻止。

請參閱 [DCS錯誤代碼、消息和示例](dcs-error-codes.md) 以獲取您可能收到的錯誤代碼的詳細資訊。

## 從拒絕清單中刪除ID

添加到拒絕清單的ID不應用於任何將來的請求，因為這些請求將導致錯誤的資料報告。 的 [!DNL DCS] 不支援從拒絕清單中刪除ID。

## 對ID同步的影響

[!DNL DCS] 呼叫可以包括一個或多個類型的ID。 如果將包含單個ID的調用添加到拒絕清單中，並且在此情況下不發生ID同步，則該調用將被完全忽略。

當多ID調用還包括密碼列出的ID時， [!DNL DCS] 不考慮拒絕的ID，只使用剩餘的允許的ID進行同步。

## ID拒絕清單的原因和修復

將ID添加到拒絕清單的最常見原因是客戶基礎架構和Audience Manager之間的整合不正確。 當您確定已拒絕列出的ID時，請確保徹底查看您的Audience Manager整合。 請參閱 **實施和整合指南** 有關如何配置Audience Manager以與其他Experience Cloud解決方案或外部系統配合使用的詳細說明。

將ID添加到拒絕清單的另一個常見原因是索引bot（Web爬網程式），這通常導致通信量增加，導致將相同的ID發送到 [!DNL DCS] 多次。 如果將索引bot標識為將ID添加到拒絕清單的原因，則應限制bot訪問您的網站。

如果您在確定整合問題方面遇到困難，請毫不猶豫地聯繫客戶支援。 在開啟支援請求之前，請確保 `.har` `HTTP` 瀏覽器存檔就緒。 此存檔可幫助支援團隊確定ID被添加到拒絕清單的原因。
