---
description: 透過設定檔合併規則，您可以控制用於細分的資料集，並且可以跨多部裝置準確地鎖定人員。
seo-description: 透過設定檔合併規則，您可以控制用於細分的資料集，並且可以跨多部裝置準確地鎖定人員。
seo-title: 設定檔合併規則概述
solution: Audience Manager
title: 設定檔合併規則概述
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: 個人資料合併
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# [!UICONTROL Profile Merge Rules] 概述 {#profile-merge-rules-overview}

透過[!UICONTROL Profile Merge Rules]，您可以控制用於細分的資料集，並可以跨多部裝置準確地鎖定使用者。

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## 使用匿名和已驗證的設定檔{#data-collection-targeting}進行資料收集和定位

對象細分和鎖定目標通常會仰賴從裝置上所有使用者收集的資料。 根據裝置層級資料進行資料收集和定位有一些缺點。 例如，您無法區分共用裝置的多個使用者，或跨多個裝置準確鎖定使用者。 以裝置為中心的資料收集已不足以用於數位行銷活動或跨裝置鎖定目標。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 根本上會變更 [!DNL Audience Manager] 收集資料和區隔使用者以進行鎖定的方式。它可讓您使用2種不同類型的設定檔，一個裝置設定檔和一個[已驗證的設定檔](../../reference/visitor-authentication-states.md)。

| 設定檔類型 | 說明 |
|---|---|
| [!UICONTROL Device Profile] | [!UICONTROL device profile]系結至指定裝置的ID，例如[!UICONTROL cookie] ID或行動裝置ID。<br><br> 其功能包括:<ul><li>[!UICONTROL Rule-based traits] 當使用者未驗證時實現。</li><li>[!UICONTROL Onboarded traits] 系結至裝置ID，例如 [!UICONTROL cookie-based]協力廠商資料。</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile]系結至使用者登入您的網站時傳入的使用者ID。<br><br>其功能包括:<ul><li>[!UICONTROL Rule-based traits] 在使用者通過驗證時跨裝置收集。</li><li>[!UICONTROL Onboarded traits] 連結至相同使用者ID的離線檔案中。</li></ul> |

這些不同的設定檔會控制您可用於細分的資料。 例如，使用[已驗證的設定檔](../../reference/visitor-authentication-states.md)，您可以根據來自單一使用者多個裝置的資料，建立準確的[!UICONTROL segments]。 這表示您可以跨多部裝置為客戶提供一致的品牌體驗。 [!DNL Audience Manager] 為此，將人員用於線上活動的不同裝置對應至其已驗證的設 [定檔](../../reference/visitor-authentication-states.md)。這些映射稱為[!UICONTROL Profile Link Device Graph]。

![](assets/authenticated2.png)

## 優勢 {#advantages}

使用[!UICONTROL Profile Merge Rules]，您可以：

* 根據[已驗證的設定檔](../../reference/visitor-authentication-states.md)、匿名設定檔或兩者的組合來鎖定使用者。
* 鎖定裝置上的特定客戶。
* 根據確定性資料建立裝置圖表。
* 根據不同的設定檔，微調[!UICONTROL segments]中的資料。
* 取得對象的其他深入分析。
