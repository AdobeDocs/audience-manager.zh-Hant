---
description: 透過設定檔合併規則，您可以控制用於細分的資料集，並可以在多個裝置上準確地鎖定人員。
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: 設定檔合併規則概述
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# [!UICONTROL Profile Merge Rules]總覽 {#profile-merge-rules-overview}

透過[!UICONTROL Profile Merge Rules]，您可以控制要用於細分的資料集，並且可以跨多部裝置準確地鎖定使用者。

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## 使用匿名和已驗證的設定檔進行資料收集和定位 {#data-collection-targeting}

通常，對象細分和目標定位會依賴從裝置上的所有使用者收集的資料。 根據裝置層級資料的資料收集和鎖定目標有一些缺點。 例如，您無法區分共用一部裝置的多個使用者，也無法跨多部裝置準確地鎖定使用者。 以裝置為中心的資料收集已不足以應付數位行銷活動或跨裝置目標定位。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules]從根本上改變[!DNL Audience Manager]收集用於鎖定目標的資料和區段使用者的方式。 它可讓您使用2種不同的設定檔型別、裝置設定檔和[已驗證的設定檔](../../reference/visitor-authentication-states.md)。

| 設定檔型別 | 說明 |
|---|---|
| [!UICONTROL Device Profile] | [!UICONTROL device profile]繫結至指定裝置的識別碼，例如[!UICONTROL cookie] ID或行動裝置ID。<br><br>它包含：<ul><li>[!UICONTROL Rule-based traits]已在使用者未驗證時實現。</li><li>[!UICONTROL Onboarded traits]繫結至裝置ID，例如[!UICONTROL cookie-based]，協力廠商資料。</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile]繫結至有人登入您的網站時傳入的使用者ID。<br><br>它包含：<ul><li>當使用者通過驗證時，會跨裝置收集[!UICONTROL Rule-based traits]。</li><li>在連結至相同使用者ID的離線檔案中[!UICONTROL Onboarded traits]。</li></ul> |

這些不同的設定檔控制您可以用於細分的資料。 例如，使用[已驗證的設定檔](../../reference/visitor-authentication-states.md)，您可以根據單一使用者來自多個裝置的資料，建立正確的[!UICONTROL segments]。 這表示您可以跨多部裝置為客戶提供一致的品牌體驗。 [!DNL Audience Manager]透過將某人線上活動使用的不同裝置對應儲存到其[已驗證的設定檔](../../reference/visitor-authentication-states.md)來達成此目的。 這些對應稱為[!UICONTROL Profile Link Device Graph]。

![](assets/authenticated2.png)

## 優勢 {#advantages}

透過[!UICONTROL Profile Merge Rules]，您可以：

* 根據[已驗證的設定檔](../../reference/visitor-authentication-states.md)、匿名設定檔或兩者的組合來鎖定使用者。
* 跨裝置鎖定特定客戶。
* 根據確定性資料建立裝置圖表。
* 根據不同的設定檔微調您[!UICONTROL segments]中的資料。
* 為受眾獲取額外的insight。
