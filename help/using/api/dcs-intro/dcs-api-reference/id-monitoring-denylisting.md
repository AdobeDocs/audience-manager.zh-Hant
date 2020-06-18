---
description: DCS會監控其收到的ID，並將短時間內以異常高速率傳送的ID新增至拒絕清單。
keywords: id;monitoring;dcs
seo-description: DCS會監控其收到的ID，並將短時間內以異常高速率傳送的ID新增至拒絕清單。
seo-title: ID監控和密碼清單
solution: Audience Manager
title: ID監控和密碼清單
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID監控和密碼清單

這 [!DNL DCS] 些ID會監視它收到的ID，並將短時間內以異常高速率發送的ID添加到拒絕清單。

## 概述

為保護Audience Manager基礎架構不受惡意活 [!DNL DCS] 動的影響，使用進階演算法來監控其接收的ID。 這些 [!UICONTROL Data Provider Unique User ID]可以是[!UICONTROL CRM ID]s(s)、 [!UICONTROL Audience Manager Unique User ID]s([!UICONTROL AAM UUID]s) [!UICONTROL Experience Cloud ID]或[!UICONTROL ECID]s(s)。 如需 [Audience Manager支援之ID的詳細說明，請參閱Audience Manager中的ID索引](../../../reference/ids-in-aam.md) 。

The [!DNL DCS] to monitor the frequency of it receives these IDs to detect peative惡意活動。 當在 [!DNL DCS] 短時間內偵測到任何指定ID的 [!DNL DCS] 請求數量異常龐大時，該ID會新增至拒絕清單。

## 錯誤代碼

您可以根據從中收到的錯誤代碼來識別添加到拒絕清單的ID [!DNL DCS]。 您可能收到的錯誤碼為：

* 303: 封鎖客戶ID;
* 306: 已阻止聲明的設備ID;
* 307: ID的描述檔作業已封鎖。

如需 [您可能收到的錯誤碼的詳細資訊，請參閱](dcs-error-codes.md) DCS錯誤碼、訊息和範例。

## 從拒絕清單中刪除ID

已新增至拒絕清單的ID不應用於任何未來的請求，因為這些ID會導致資料報告不正確。 不 [!DNL DCS] 支援從拒絕清單中刪除ID。

## 對ID同步的影響

[!DNL DCS] 呼叫可包含一或多種ID類型。 如果將包含單一ID的呼叫新增至拒絕清單，且此情況下不會進行ID同步，則會完全忽略該ID的呼叫。

當多個ID呼叫也包含已拒絕的ID時， [!DNL DCS] 會忽略拒絕的ID，並僅使用剩餘的允許ID進行同步。

## ID拒絕列出的原因和修正

將ID新增至拒絕清單的最常見原因是客戶基礎架構與Audience Manager之間的整合不正確。 當您識別已登入清單的ID時，請務必徹底審查Audience Manager整合。 請參 **閱實作與整合指南** ，以取得如何設定Audience Manager以搭配其他Experience Cloud解決方案或外部系統運作的詳細說明。

另一個將ID新增至拒絕清單的常見原因是索引bot（Web爬蟲程式），這通常會導致流量增加，導致相同的ID被多次 [!DNL DCS] 傳送。 如果您將索引機器人識別為新增ID至拒絕清單的原因，您應限制機器人對您網站的存取。

如果您很難識別整合問題，請立即聯絡客戶支援。 在開啟支援要求之前，請務必讓您的瀏 `.har` 覽器 `HTTP` 封存就緒。 此封存可協助支援團隊識別將ID新增至拒絕清單的原因。