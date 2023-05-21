---
description: Recommendations和使用案例，通過配置式連結設備圖形進行分段重定位和個性化分段鑑定。
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: 設定檔連結裝置圖表使用案例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 8%

---

# 設定檔連結裝置圖表使用案例 {#profile-link-device-graph-use-cases}

Recommendations及使用案例進行細分目標和個性化細分資格 [!UICONTROL Profile Link Device Graph]。

## 建議 {#recommendations}

考慮 [!UICONTROL Profile Link] 市場活動的設備圖表：

* 通過其數字屬性進行高級身份驗證。 使用 [外部設備圖形選項](merge-rule-definitions.md#device-options) 如果您有少量經過身份驗證的用戶。
* 需要準確定位已知受眾。 的 [!UICONTROL Profile Link Device Graph] 是使用第一方、經過身份驗證的資料構建的。
* 即時針對其已驗證和未驗證狀態的已知受眾。

![](assets/merge-rule-triangle2.png)

## 跨設備目標 {#cross-device-personalization}

比如說，約翰擁有三款設備，他經常用這些設備來搜索度假套餐交易：他的筆記型電腦[!DNL Device 1])，他的智慧手機([!DNL Device 2])和他的平板電腦([!DNL Device 3])。 但是，John使用他的設備來搜索不同的包交易項目：

* 他用筆記型電腦搜索航班；
* 他用智慧手機搜索酒店；
* 他用平板電腦搜索導遊。

即使John未在上述三種設備上進行身份驗證， **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** 規則中，假日包提供程式可以將這些設備與John的已驗證配置檔案相關聯，假定他是最後一個在所有三台設備上進行身份驗證的人。

![最後設備圖](assets/last-device-graph.png)

由於Audience Manager限定了參與段配置檔案合併的每個設備配置檔案，因此將分段所有三個設備配置檔案。 的 [!UICONTROL Profile Link Device Graph] 允許Audience Manager查看所有三台設備的行為，並限定每台設備的資料段，而沒有單個設備配置檔案可以單獨使用。

此 [!UICONTROL Profile Merge Rule] 使營銷人員能夠根據用戶活動而不是單個設備活動向由一個人擁有的所有設備提供一致的體驗。

![跨設備個性化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部裝置圖表使用案例](external-graph-use-cases.md)
>* [設定檔合併規則的一般使用案例](merge-rule-targeting-options.md)
>* [配置檔案合併規則常見問題](../../faq/faq-profile-merge.md)

