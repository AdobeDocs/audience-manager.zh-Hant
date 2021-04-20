---
description: Recommendations，以及使用設定檔連結裝置圖表來重新定位區段及個人化區段資格的使用案例。
seo-description: Recommendations，以及使用設定檔連結裝置圖表來重新定位區段及個人化區段資格的使用案例。
seo-title: 設定檔連結裝置圖表使用案例
solution: Audience Manager
title: 設定檔連結裝置圖表使用案例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 9%

---

# 設定檔連結裝置圖表使用案例 {#profile-link-device-graph-use-cases}

Recommendations，並透過[!UICONTROL Profile Link Device Graph]使用案例來重新定位區段及個人化區段資格。

## 建議 {#recommendations}

請考慮以下促銷活動的[!UICONTROL Profile Link]裝置圖表：

* 在其數位屬性上擁有高等級的驗證。 如果您有少量已驗證的使用者，請使用[外部裝置圖形選項](merge-rule-definitions.md#device-options)。
* 需要精確鎖定已知受眾。 [!UICONTROL Profile Link Device Graph]是使用第一方的已驗證資料建立。
* 即時鎖定已知受眾的已驗證和未驗證狀態。

![](assets/merge-rule-triangle2.png)

## 跨裝置定位{#cross-device-personalization}

比方說，約翰擁有三款他經常用來搜尋度假套餐的設備：他的筆記型電腦([!DNL Device 1])、他的智慧手機([!DNL Device 2])和他的平板電腦([!DNL Device 3])。 不過，John會使用他的裝置來搜尋套件交易的不同項目：

* 他用筆記型電腦搜索航班；
* 他用智慧手機搜索酒店；
* 他用平板電腦搜尋導遊。

即使John未在上述所有三種裝置上驗證，透過使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**&#x200B;規則，假設他是最後一個在所有三種裝置上驗證的人員，假日套件提供者也可以將這些裝置與John的已驗證設定檔建立關聯。

![最後設備圖](assets/last-device-graph.png)

由於Audience Manager符合參與區段描述檔合併的每個裝置描述檔的資格，因此會將所有三個裝置描述檔分段。 [!UICONTROL Profile Link Device Graph]可讓Audience Manager查看所有三台裝置的行為，並讓每台裝置符合任何單一裝置描述檔獨自適用的區段。

此[!UICONTROL Profile Merge Rule]可讓行銷人員根據使用者活動而非個別裝置活動，為個人擁有的所有裝置提供一致的體驗。

![跨裝置個人化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部裝置圖表使用案例](external-graph-use-cases.md)
>* [設定檔合併規則的一般使用案例](merge-rule-targeting-options.md)
>* [描述檔合併規則常見問答集](../../faq/faq-profile-merge.md)

