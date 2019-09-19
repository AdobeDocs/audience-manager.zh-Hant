---
description: DCS會監控其收到的ID，並列出在短時間內以異常高的速率傳送的ID。
keywords: id；監控；黑名單；dcs
seo-description: DCS會監控其收到的ID，並列出在短時間內以異常高的速率傳送的ID。
seo-title: ID監控與黑名單
solution: Audience Manager
title: ID監控與黑名單
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID監控與黑名單

監 [!UICONTROL DCS] 視其收到的ID，並列出在短時間內以異常高的速率傳送的ID。

## 概述

為保護Audience manager基礎架構不受惡意活 [!UICONTROL DCS] 動的影響，使用進階演算法來監控其接收的ID。 這些 [!UICONTROL Data Provider Unique User ID]可以是[!UICONTROL CRM ID]s(s)、 [!UICONTROL Audience Manager Unique User ID]s([!UICONTROL AAM UUID]s) [!UICONTROL Experience Cloud ID]或[!UICONTROL ECID]s(s)。 如需 [Audience Manager支援之ID的詳細說明，請參閱Audience Manager中的ID索引](../../../reference/ids-in-aam.md) 。

The [!UICONTROL DCS] the moniters of frequency it receives these IDs to detect peative惡意活動。 當在 [!UICONTROL DCS] 短時間內偵測到任何指定 [!UICONTROL DCS] ID的異常大量請求時，該ID便會列入黑名單。

## 錯誤代碼

您可以透過從收到的錯誤碼識別黑名單ID [!UICONTROL DCS]。 您可能收到的錯誤碼為：

* 303:封鎖客戶ID;
* 306:已阻止聲明的設備ID;
* 307:ID的描述檔作業已封鎖。

如需 [您可能收到的錯誤碼的詳細資訊，請參閱](dcs-error-codes.md) DCS錯誤碼、訊息和範例。

## 取消黑名單

黑名單ID不應用於任何未來的請求，因為它們會導致錯誤的資料報告。 不 [!UICONTROL DCS] 支援ID的非黑名單。

## 對ID同步的影響

[!UICONTROL DCS] 呼叫可包含一或多種ID類型。 如果將單一ID列入黑名單，且此情況下不會進行ID同步，則完全不會考慮包含單一ID的呼叫。

當多個ID呼叫也包含黑名單ID時， [!UICONTROL DCS] 會忽略黑名單ID，並僅使用其餘的未黑名單ID進行同步。

## ID黑名單的原因和修正

ID被列入黑名單的最常見原因是客戶基礎架構與Audience manager之間的整合不正確。 當您識別黑名單ID時，請務必徹底審查Audience manager整合。 請參 **閱實作與整合指南** ，以取得如何設定Audience manager以搭配其他Experience cloud解決方案或外部系統運作的詳細說明。

黑名單ID的另一個常見原因是索引bot（Web爬蟲程式），這通常會導致流量增加，導致相同ID被多次傳 [!UICONTROL DCS] 送至。 如果您將索引機器人識別為ID黑名單的原因，您應限制機器人對您網站的存取。

如果您很難識別整合問題，請立即聯絡客戶支援。 在開啟支援要求之前，請務必讓您的瀏 `.har` 覽器 `HTTP` 封存就緒。 此封存可協助支援團隊識別ID黑名單的發生原因。