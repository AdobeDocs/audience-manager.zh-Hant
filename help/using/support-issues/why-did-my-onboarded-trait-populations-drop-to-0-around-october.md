---
description: 在2019年10月14日前後，我注意到裝置ID圖表的已登入特徵族群已降至0，而之前則高得多。
seo-description: 在2019年10月14日前後，我注意到裝置ID圖表的已登入特徵族群已降至0，而之前則高得多。
seo-title: 為什麼我的Onhoted特徵種群在10月15日左右降至0?
solution: Audience Manager
title: 為什麼我的Onhoted特徵種群在10月15日左右降至0?
translation-type: tm+mt
source-git-commit: 0487a15c5fcd0e653bedf0e7fd8326f5cc363660

---


# 為什麼我的Onhoted特徵種群在10月15日左右降至0? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## 連結

在2019年10月14日前後，我注意到裝置ID圖表的已登入特徵族群已降至0，而之前則高得多。 為什麼會發生這種事？

![裝置ID拖放影像](assets/device_id_populationdrop.png)

## 回答

在10月15日，Audience Manager的「設定檔合併規則」功能的更新已變更為，不再針對裝置ID，針對上傳至跨裝置資料來源的CRM ID進行已登入資料的更新。  以前Audience Manager會根據跨裝置ID（或CRM ID）來實現，並將這些實現複製至相關的Audience Manager UUID（裝置ID）。  該變化更準確地反映特徵資料的性質和正在實現的特徵。

若要檢視特徵實現，請從「特徵」檢視右上角的下拉式清單中選取「跨裝置ID」選項。

![依跨裝置ID檢視實現](assets/deviceid-crossdevice.png)