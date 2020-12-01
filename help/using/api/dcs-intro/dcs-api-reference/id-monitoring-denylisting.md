---
description: DCS會監控其收到的ID，並將短時間內以異常高速率傳送的ID新增至拒絕清單。
keywords: id;monitoring;dcs
seo-description: DCS會監控其收到的ID，並將短時間內以異常高速率傳送的ID新增至拒絕清單。
seo-title: ID監控和密碼清單
solution: Audience Manager
title: ID監控和密碼清單
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID監控和密碼清單

[!DNL DCS]會監視它收到的ID，並將短時間內以異常高速率發送的ID添加到拒絕清單。

## 概述

為保護Audience Manager基礎架構不受惡意活動的影響，[!DNL DCS]會使用進階演算法來監控其接收的ID。 這些參數可以是[!UICONTROL Data Provider Unique User ID]s([!UICONTROL CRM ID]s)、[!UICONTROL Audience Manager Unique User ID]s([!UICONTROL AAM UUID]s)或[!UICONTROL Experience Cloud ID]s([!UICONTROL ECID]s)。 如需Audience Manager支援之ID的詳細說明，請參閱Audience Manager中的[ ID索引](../../../reference/ids-in-aam.md)。

[!DNL DCS]會監控收到這些ID的頻率，以偵測潛在的惡意活動。 當[!DNL DCS]在短時間內偵測到任何指定ID的異常大量[!DNL DCS]請求時，該ID會新增至拒絕清單。

## 錯誤代碼

您可以通過從[!DNL DCS]收到的錯誤代碼來標識添加到拒絕清單的ID。 您可能收到的錯誤碼為：

* 303:封鎖客戶ID;
* 306:已阻止聲明的設備ID;
* 307:ID的描述檔作業已封鎖。

如需您可能收到的錯誤碼的詳細資訊，請參閱[DCS錯誤碼、訊息和範例](dcs-error-codes.md)。

## 從拒絕清單中刪除ID

已新增至拒絕清單的ID不應用於任何未來的請求，因為這些ID會導致資料報告不正確。 [!DNL DCS]不支援從拒絕清單中刪除ID。

## 對ID同步的影響

[!DNL DCS] 呼叫可包含一或多種ID類型。如果將包含單一ID的呼叫新增至拒絕清單，且此情況下不會進行ID同步，則會完全忽略該ID的呼叫。

當多個ID呼叫也包含已拒絕的ID時，[!DNL DCS]會忽略已拒絕的ID，並僅使用剩餘的允許ID進行同步。

## ID拒絕列出的原因和修正

將ID新增至拒絕清單的最常見原因是客戶基礎架構與Audience Manager之間的整合不正確。 當您識別已登入清單的ID時，請務必徹底審查Audience Manager整合。 請參閱&#x200B;**實作與整合指南**，以取得如何設定Audience Manager以搭配其他Experience Cloud解決方案或外部系統運作的詳細說明。

將ID新增至拒絕清單的另一個常見原因是索引bot（Web爬蟲程式），這通常會導致流量增加，導致相同的ID被多次傳送至[!DNL DCS]。 如果您將索引機器人識別為新增ID至拒絕清單的原因，您應限制機器人對您網站的存取。

如果您很難識別整合問題，請立即聯絡客戶支援。 在開啟支援要求之前，請務必讓瀏覽器的`.har` `HTTP`封存備妥。 此封存可協助支援團隊識別將ID新增至拒絕清單的原因。