---
description: DCS會監控收到的ID，並以異常高的頻率將短時間內傳出的ID新增至拒絕名單。
keywords: id；監視；dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: ID監控與封鎖清單
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# ID監控與封鎖清單

[!DNL DCS]會監控所接收的ID，並將短時間內以異常高的頻率傳送的ID新增至拒絕清單。

## 概述

為了保護Audience Manager基礎結構不受惡意活動的侵擾，[!DNL DCS]會使用進階演演算法來監視其接收的ID。 這些可以是[!UICONTROL Data Provider Unique User ID] ([!UICONTROL CRM ID])、[!UICONTROL Audience Manager Unique User ID] ([!UICONTROL AAM UUID])或[!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID])。 請參閱Audience Manager](../../../reference/ids-in-aam.md)中的[ID索引，以取得Audience Manager所支援ID的詳細解釋。

[!DNL DCS]會監視收到這些ID的頻率，以偵測潛在的惡意活動。 當[!DNL DCS]在短時間內偵測到任何指定ID有異常大的[!DNL DCS]個要求時，該ID會新增至拒絕清單。

## 錯誤代碼

您可以利用從[!DNL DCS]收到的錯誤碼來識別新增至拒絕清單的ID。 您可能會收到的錯誤碼為：

* 303：封鎖的客戶ID；
* 306：封鎖的宣告裝置識別碼；
* 307：已封鎖識別碼的設定檔操作。

請參閱[DCS錯誤碼、訊息和範例](dcs-error-codes.md)，以取得您可能收到的錯誤碼詳細資訊。

## 從拒絕清單移除ID

已新增至拒絕清單的ID不應用於任何未來的請求，因為這些ID會導致不正確的資料報告。 [!DNL DCS]不支援從拒絕清單移除ID。

## 對ID同步的影響

[!DNL DCS]個呼叫可以包含一或多個型別的ID。 如果將包含單一ID的呼叫新增至拒絕清單，則會完全忽略該ID，且在此情況下不會發生ID同步。

當多個ID呼叫也包含已加入封鎖清單的ID時，[!DNL DCS]會忽略被拒絕的ID，而只使用剩餘的允許的ID進行同步。

## ID封鎖清單的原因和修正

新增ID至拒絕清單的最常見原因是客戶基礎架構與Audience Manager之間的整合不正確。 識別已加入封鎖清單的ID時，請務必仔細檢閱您的Audience Manager整合。 請參閱&#x200B;**實作與整合指南**，以取得您應如何設定Audience Manager以搭配其他Experience Cloud解決方案或外部系統使用的詳細說明。

將ID新增至拒絕清單的另一個常見原因是索引機器人（Web編目程式），這通常會導致流量增加，導致將相同的ID多次傳送給[!DNL DCS]。 如果您將索引機器人識別為將ID新增至拒絕清單的原因，您應該限制機器人對您網站的存取。

如果您難以辨識整合問題，請隨時聯絡客戶支援。 開啟支援要求之前，請確定讓瀏覽器的`.har` `HTTP`封存準備就緒。 此封存可協助支援團隊識別將ID新增至拒絕清單的原因。
