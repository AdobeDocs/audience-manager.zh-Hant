---
description: 使用「配置檔案合併規則」，您可以控制用於分割的資料集，並且可以跨多個設備準確地瞄準人。
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: 設定檔合併規則概述
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 3%

---

# [!UICONTROL Profile Merge Rules] 概述 {#profile-merge-rules-overview}

與 [!UICONTROL Profile Merge Rules] 您可以控制哪些資料集用於分割，並且可以跨多個設備準確地瞄準用戶。

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## 使用匿名和經過身份驗證的配置檔案進行資料收集和目標 {#data-collection-targeting}

通常，受眾細分和目標化依賴於從設備上的所有用戶收集的資料。 基於設備級資料的資料採集和目標定位存在一定的缺陷。 例如，您不能區分共用設備的多個用戶或跨多個設備準確地瞄準用戶。 以設備為中心的資料收集不再足以用於數字營銷活動或跨設備目標。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 從根本上改變 [!DNL Audience Manager] 收集資料和段用戶以進行目標。 它允許您使用兩種不同類型的配置檔案、一個設備配置檔案和 [認證配置檔案](../../reference/visitor-authentication-states.md)。

| 配置檔案類型 | 說明 |
|---|---|
| [!UICONTROL Device Profile] | A [!UICONTROL device profile] 與給定設備的ID綁定，例如 [!UICONTROL cookie] ID或移動設備ID。<br><br> 其功能包括:<ul><li>[!UICONTROL Rule-based traits] 當用戶未經身份驗證時實現。</li><li>[!UICONTROL Onboarded traits] 綁定到設備ID，如 [!UICONTROL cookie-based]，第三方資料。</li></ul> |
| [!UICONTROL Authenticated Profile] | 的 [!UICONTROL authenticated profile] 與登錄您的站點時傳入的用戶ID關聯。<br><br>其功能包括:<ul><li>[!UICONTROL Rule-based traits] 在用戶經過身份驗證時跨設備收集。</li><li>[!UICONTROL Onboarded traits] 連結到同一用戶ID的離線檔案中。</li></ul> |

這些不同的配置檔案控制可用於分割的資料。 例如， [認證配置檔案](../../reference/visitor-authentication-states.md)，可以精確 [!UICONTROL segments] 基於來自單個用戶的多個設備的資料。 這意味著您可以跨多個設備為客戶提供一致的品牌體驗。 [!DNL Audience Manager] 通過儲存用戶線上活動所使用的不同設備與其線上活動之間的映射，實現了這一點 [認證配置檔案](../../reference/visitor-authentication-states.md)。 這些映射稱為 [!UICONTROL Profile Link Device Graph]。

![](assets/authenticated2.png)

## 優勢 {#advantages}

與 [!UICONTROL Profile Merge Rules] 您可以：

* 目標用戶基於 [認證配置檔案](../../reference/visitor-authentication-states.md)、匿名配置檔案或兩者的組合。
* 針對跨設備的特定客戶。
* 基於確定性資料構建設備圖。
* 微調您的資料 [!UICONTROL segments] 根據不同的檔案。
* 更深入地瞭解您的受眾。
