---
description: DCS會監控收到並列入黑名單的ID，這些ID會在短時間內以異常高的速率傳送。
keywords: id；監控；黑名單；cs
seo-description: DCS會監控收到並列入黑名單的ID，這些ID會在短時間內以異常高的速率傳送。
seo-title: ID監控與黑名單
solution: Audience Manager
title: ID監控與黑名單
uuid: 498e0316-cf-1b-43e9-88ba-338ee0 daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID監控與黑名單

The [!UICONTROL DCS] monitors the IDs it receives and blacklists those that are being sent at an unusually high rate over a short period of time.

## 概述

To protect the Audience Manager infrastructure against malicious activity, the [!UICONTROL DCS] uses an advanced algorithm to monitor the IDs it receives. These can be [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), or [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). See [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) for detailed explanations of the IDs supported by Audience Manager.

The [!UICONTROL DCS] monitors the frequency at which it receives these IDs to detect potential malicious activity. [!UICONTROL DCS] 當在短時間內偵測到任何給定ID [!UICONTROL DCS] 的要求時，該ID會列入黑名單。

## 錯誤代碼

You can identify blacklisted IDs by the error codes received from the [!UICONTROL DCS]. 您可能收到的錯誤碼為：

* 303：封鎖客戶ID；
* 306：已封鎖宣告的裝置ID；
* 307：已封鎖ID的描述檔作業。

See [DCS Error Codes, Messages, and Examples](dcs-error-codes.md) for details on the error codes that you may receive.

## 取消列入黑名單

黑名單ID不應用於日後的請求中，因為它們會導致資料報告不正確。The [!UICONTROL DCS] does not support un-blacklisting of IDs.

## 對ID同步的影響

[!UICONTROL DCS] 呼叫可以包含一個或多個ID類型。如果該ID已列入黑名單，則完全忽略包含單一ID的呼叫，且此情況下不會同步任何ID同步。

When a multiple ID call also includes a blacklisted ID, the [!UICONTROL DCS] disregards the blacklisted ID and only uses the remaining, non-blacklisted IDs for synchronization.

## ID黑名單的原因和修正

列入黑名單的ID最常見的原因，是客戶基礎結構與Audience Manager之間的整合不正確。當您識別列入黑名單的ID時，請務必完整檢查您的Audience Manager整合。See **Implementation and Integration Guides** for detailed explanations of how you should configure Audience Manager to work with other Experience Cloud solutions or external systems.

Another frequent cause of blacklisted IDs are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!UICONTROL DCS] multiple times. 如果您將索引機器人識別為ID黑名單的原因，則應限制機器人存取您的網站。

如果您難以識別整合問題，請不要費心聯絡客戶支援。Prior to opening a support request, make sure to keep the `.har` `HTTP` archive of your browser ready. 此封存可協助支援團隊識別發生ID黑名單的原因。