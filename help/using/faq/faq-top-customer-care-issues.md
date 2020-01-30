---
description: 此頁面包含向Audience Manager客戶服務回報的主要問題。
seo-description: 此頁面包含向Audience Manager客戶服務回報的主要問題。
seo-title: 客戶服務——最常報告的問題
solution: Audience Manager
title: 客戶服務——最常報告的問題
translation-type: tm+mt
source-git-commit: f9d57da86b7e8962353b01b693a2359cade7b024

---


# 客戶服務——最常報告的問題{#most-frequent-issues}

本頁包含2019年向Audience Manager客戶服務報告的主要問題。

## 我們的唯讀使用者為何能夠建立、編輯或刪除特徵和區段？

**問題**

我們的唯讀使用者為何能夠建立、編輯或刪除特徵和區段？

**回答**

除了在管理區段中建立群組和權限之外，您還需要聯絡客戶服務(amsupport@adobe.com)，以便代表為您的帳戶啟用角色存取控制(RBAC)。

<br> 

## 為什麼我的Onhoted特徵種群在10月15日左右降至0? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

在2019年10月14日前後，我注意到裝置ID圖表的已登入特徵族群已降至0，而之前則高得多。

![裝置ID拖放影像](/help/using/support-issues/assets/device_id_populationdrop.png)

**回答**

在10月15日，Audience manager的「設定檔合併規則」功能的更新已變更為，不再針對裝置ID，針對上傳至跨裝置資料來源的CRM ID進行已登入資料的更新。  以前Audience manager會根據跨裝置ID（或CRM ID）來實現，並將這些實現複製至相關的Audience Manager UUID（裝置ID）。  該變化更準確地反映特徵資料的性質和正在實現的特徵。

若要檢視特徵實現，請從「特徵」檢視右上角的下拉式清單中選取「跨裝置ID」選項。

![依跨裝置ID檢視實現](/help/using/support-issues/assets/deviceid-crossdevice.png)

<br> 

## 為何我的特徵或區段不會顯示在「重疊報表」頁面中？

說明為何特徵和區段無法顯示在「重疊報表」頁面中。

**問題**

當使用者嘗試執行重疊報表時，為什麼不在重疊報表頁面中看到某些特徵和區段？

**回答**

必須符合最低獨特訪客需求，才能在重疊報表中列出特徵或區段。


* 針對特徵：28000年14天
* 針對區段：70000位14天期間的即時使用者

如需詳細資訊，請參閱「選取的Audience manager報 [表」中的「資料取樣和錯誤率」頁面](/help/using/reporting/report-sampling.md)。