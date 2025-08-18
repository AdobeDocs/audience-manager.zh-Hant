---
description: 透過設定檔連結裝置圖表，提供區段重新定位和個人化區段資格的建議和使用案例。
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
ht-degree: 4%

---

# 設定檔連結裝置圖表使用案例 {#profile-link-device-graph-use-cases}

使用[!UICONTROL Profile Link Device Graph]進行區段重新定位和個人化區段資格的建議和使用案例。

## 建議 {#recommendations}

考慮將[!UICONTROL Profile Link]裝置圖表用於具有下列條件的行銷活動：

* 對其數位屬性進行高階驗證。 如果只有少量的已驗證使用者，請使用[外部裝置圖表選項](merge-rule-definitions.md#device-options)。
* 需要精確鎖定已知對象。 [!UICONTROL Profile Link Device Graph]是使用第一方已驗證的資料建置。
* 跨已驗證和未驗證狀態即時鎖定已知對象。

![](assets/merge-rule-triangle2.png)

## 跨裝置目標定位 {#cross-device-personalization}

假設John擁有三部他經常用來搜尋假日套裝交易的裝置：他的筆記型電腦([!DNL Device 1])、智慧型手機([!DNL Device 2])和平板電腦([!DNL Device 3])。 不過，John會使用裝置搜尋套件交易的不同專案：

* 他用筆記型電腦搜尋航班；
* 他用智慧手機搜尋旅館；
* 他使用平板電腦搜尋導覽。

即使John並未在上述三個裝置上進行驗證，透過&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**&#x200B;規則，假設有最後三部裝置上驗證身分的人，假設有假日John封裝提供者可將這些裝置與John已驗證的設定檔建立關聯。

![上次裝置圖表](assets/last-device-graph.png)

由於Audience Manager會針對區段限定參與設定檔合併的每個裝置設定檔，因此這三個裝置設定檔都會分段。 [!UICONTROL Profile Link Device Graph]可讓Audience Manager檢視所有三個裝置的行為，並將每個裝置限定於沒有單一裝置設定檔本身符合的區段。

此[!UICONTROL Profile Merge Rule]可讓行銷人員根據使用者活動（而非個別裝置活動），將一致的體驗傳送至單一人員擁有的所有裝置。

![跨裝置個人化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部裝置圖表使用案例](external-graph-use-cases.md)
>* [設定檔合併規則的一般使用案例](merge-rule-targeting-options.md)
>* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)
