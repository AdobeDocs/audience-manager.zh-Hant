---
description: 2019 年 10 月 14 日前後，我注意到裝置 ID 圖表的已上線特徵母體已降至 0，而之前高很多。
seo-description: Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher.
seo-title: Why did my Onboarded trait populations drop to 0 around October 15th?
solution: Audience Manager
title: 為什麼我的已上線特徵母體在 10 月 15 日左右降至 0？
feature: Support
exl-id: e93cee15-7d05-4f81-8f14-a3e03f214542
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 100%

---

# 為什麼我的已上線特徵母體在 10 月 15 日左右降至 0？ {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## 問題

2019 年 10 月 14 日前後，我注意到裝置 ID 圖表的已上線特徵母體已降至 0，而之前高很多。為什麼會發生這個情況？

![裝置 ID 影像放置](assets/device_id_populationdrop.png)

## 回答

10 月 15 日，Audience Manager 的「設定檔合併規則」功能更新已做出變更，上傳至跨裝置資料來源的 CRM ID 作為輸入資料的已上線資料，已不再針對裝置 ID 實現。之前 Audience Manager 會針對跨裝置 ID (或 CRM ID) 來實現，也會將這些實現項目複製到相關聯的 Audience Manager UUID (裝置 ID)。這項變更的目的是更準確反映特徵資料和正在實現的設定檔之性質。

若要檢視特徵實現項目，請在「Trait」檢視右上角的下拉式清單中選取「Cross-Device ID」選項。

![依跨裝置 ID 檢視實現項目](assets/deviceid-crossdevice.png)
