---
description: Recommendations和使用案例，透過設定檔連結裝置圖表重新定位區段及個人化區段資格。
seo-description: Recommendations和使用案例，透過設定檔連結裝置圖表重新定位區段及個人化區段資格。
seo-title: 設定檔連結裝置圖表使用案例
solution: Audience Manager
title: 設定檔連結裝置圖表使用案例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: 個人資料合併
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 9%

---

# 設定檔連結裝置圖表使用案例 {#profile-link-device-graph-use-cases}

Recommendations和使用案例，透過[!UICONTROL Profile Link Device Graph]重新定位區段及個人化區段資格。

## 建議 {#recommendations}

請考量[!UICONTROL Profile Link]裝置圖表，適用於下列促銷活動：

* 在其數位屬性上擁有高層級的驗證。 如果您有少量已驗證的使用者，請使用[外部裝置圖表選項](merge-rule-definitions.md#device-options)。
* 需要準確鎖定已知對象。 [!UICONTROL Profile Link Device Graph]是使用第一方的已驗證資料建置。
* 即時鎖定已知受眾的驗證和未驗證狀態。

![](assets/merge-rule-triangle2.png)

## 跨裝置鎖定目標{#cross-device-personalization}

假設約翰有三台設備，他經常用這些設備來搜索度假套餐：他的筆記型電腦([!DNL Device 1])、智慧手機([!DNL Device 2])和平板電腦([!DNL Device 3])。 不過，John會使用其裝置來搜尋套件交易的不同項目：

* 他用筆記型電腦搜索航班；
* 他用智慧手機搜索酒店；
* 他用平板電腦搜索導遊。

即使John未在上述所有三部裝置上通過驗證，假設John是最後一個在所有三部裝置上進行驗證的人，假期套件提供者也可使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**&#x200B;規則，將這些裝置與John的已驗證設定檔建立關聯。

![最後裝置圖表](assets/last-device-graph.png)

由於Audience Manager符合參與區段之設定檔合併的每個裝置設定檔的資格，因此所有三個裝置設定檔都會分段。 [!UICONTROL Profile Link Device Graph]可讓Audience Manager查看所有三部裝置的行為，並讓每部裝置符合沒有單一裝置設定檔獨自符合的區段資格。

此[!UICONTROL Profile Merge Rule]可讓行銷人員根據使用者活動而非個別裝置活動，為一人擁有的所有裝置提供一致的體驗。

![跨裝置個人化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部裝置圖表使用案例](external-graph-use-cases.md)
* [設定檔合併規則的一般使用案例](merge-rule-targeting-options.md)
* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)

