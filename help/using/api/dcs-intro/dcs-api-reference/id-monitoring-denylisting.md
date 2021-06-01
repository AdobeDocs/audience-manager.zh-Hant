---
description: DCS會監控收到的ID，並將在短時間內以異常高的頻率傳送的ID新增至拒絕名單。
keywords: id；監控；dcs
seo-description: DCS會監控收到的ID，並將在短時間內以異常高的頻率傳送的ID新增至拒絕名單。
seo-title: ID監控與封鎖
solution: Audience Manager
title: ID監控與封鎖
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# ID監控與封鎖

[!DNL DCS]會監控收到的ID，並將在短時間內以異常高的頻率傳送的ID新增至拒絕名單。

## 概述

為保護Audience Manager基礎架構免受惡意活動的侵擾，[!DNL DCS]使用高級算法監視其接收的ID。 這些可以是[!UICONTROL Data Provider Unique User ID]s([!UICONTROL CRM ID]s)、[!UICONTROL Audience Manager Unique User ID]s([!UICONTROL AAM UUID]s)或[!UICONTROL Experience Cloud ID]s([!UICONTROL ECID]s)。 請參閱[Audience Manager中的ID索引](../../../reference/ids-in-aam.md) ，以取得Audience Manager支援之ID的詳細說明。

[!DNL DCS]會監控收到這些ID的頻率，以偵測潛在的惡意活動。 當[!DNL DCS]在短時間內檢測到任何指定ID的異常大量[!DNL DCS]請求時，該ID將被添加到拒絕清單中。

## 錯誤代碼

您可以通過從[!DNL DCS]接收的錯誤代碼識別添加到拒絕清單的ID。 您可能收到的錯誤代碼為：

* 303:封鎖的客戶ID;
* 306:已阻止的聲明設備ID;
* 307:已阻止ID的配置檔案操作。

如需您可能收到的錯誤碼詳細資訊，請參閱[DCS錯誤碼、訊息和範例](dcs-error-codes.md)。

## 從拒絕名單中刪除ID

已新增至拒絕名單的ID不應用於任何未來的請求，因為這些ID會導致資料報表不正確。 [!DNL DCS]不支援從拒絕名單中刪除ID。

## 對ID同步的影響

[!DNL DCS] 呼叫可包含一或多種ID類型。若將包含單一ID的呼叫新增至拒絕清單，且在此情況下不會進行ID同步，則系統會完全忽略該ID的呼叫。

當多個ID呼叫也包含已拒絕的ID時，[!DNL DCS]會忽略已拒絕的ID，並只使用其餘的允許ID進行同步。

## ID封鎖的原因及修正

將ID新增至拒絕名單的最常見原因是客戶基礎架構與Audience Manager之間的整合不正確。 識別已拒絕的ID時，請務必徹底檢閱您的Audience Manager整合。 請參閱&#x200B;**實作與整合指南** ，以取得如何設定Audience Manager以搭配其他Experience Cloud解決方案或外部系統使用的詳細說明。

將ID新增至拒絕名單的另一個常見原因是索引機器人（Web編目程式），這通常會導致流量增加，導致將相同ID多次傳送至[!DNL DCS]。 如果您將索引機器人識別為將ID新增至拒絕名單的原因，則應限制機器人對您網站的存取。

如果您很難識別整合問題，請立即聯絡客戶支援。 開啟支援請求前，請務必將瀏覽器的`.har` `HTTP`封存保留為已備妥。 此封存可協助支援團隊識別ID新增至拒絕名單的原因。
