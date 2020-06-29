---
description: 使用描述檔連結裝置圖表，針對區段重新定位和個人化區段資格的建議和使用案例。
seo-description: 使用描述檔連結裝置圖表，針對區段重新定位和個人化區段資格的建議和使用案例。
seo-title: 設定檔連結裝置圖表使用案例
solution: Audience Manager
title: 設定檔連結裝置圖表使用案例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 9%

---


# 設定檔連結裝置圖表使用案例 {#profile-link-device-graph-use-cases}

針對區段重新定位和個人化區段資格的建議和使用案例 [!UICONTROL Profile Link Device Graph]。

## 建議 {#recommendations}

請考慮適 [!UICONTROL Profile Link] 用於下列促銷活動的裝置圖表：

* 在其數位屬性上擁有高等級的驗證。 如果您 [有少量已驗證的使用者](merge-rule-definitions.md#device-options) ，請使用外部裝置圖形選項。
* 需要精確鎖定已知受眾。 使 [!UICONTROL Profile Link Device Graph] 用第一方驗證資料建立。
* 即時鎖定已知受眾的已驗證和未驗證狀態。

![](assets/merge-rule-triangle2.png)

## 跨裝置定位 {#cross-device-personalization}

比方說，約翰擁有三款他經常用來搜尋度假套餐的設備： 他的筆記本[!DNL Device 1]電腦、智慧手機[!DNL Device 2]()和平板電腦([!DNL Device 3])。 不過，John會使用他的裝置來搜尋套件交易的不同項目：

* 他用筆記型電腦搜索航班；
* 他用智慧手機搜索酒店；
* 他用平板電腦搜尋導遊。

即使John未在上述所有三種裝置上驗證，透過使用 **[!UICONTROL Last Authenticated Profiles]****[!UICONTROL Profile Link Device Graph]** +規則，假期套件提供者也可將這些裝置與John的驗證設定檔建立關聯，假設他是最後一個在所有三種裝置上驗證的人。

![最後設備圖](assets/last-device-graph.png)

由於Audience Manager可讓參與區段描述檔合併的每個裝置描述檔都符合資格，因此這三個裝置描述檔都會被分段。 Audience Manager可 [!UICONTROL Profile Link Device Graph] 讓Audience Manager檢視這三種裝置的行為，並讓每個裝置都符合單一裝置設定檔獨享的區段資格。

這可 [!UICONTROL Profile Merge Rule] 讓行銷人員根據使用者活動而非個別裝置活動，為個人擁有的所有裝置提供一致的體驗。

![跨裝置個人化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部裝置圖表使用案例](external-graph-use-cases.md)
>* [設定檔合併規則的一般使用案例](merge-rule-targeting-options.md)
>* [描述檔合併規則常見問答集](../../faq/faq-profile-merge.md)

