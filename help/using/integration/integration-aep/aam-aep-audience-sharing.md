---
description: 本文說明Audience Manager與Adobe Experience Platform之間如何共用觀眾。
seo-description: 本文說明Audience Manager與Adobe Experience Platform之間如何共用觀眾。
seo-title: Audience Manager 與 Adobe Experience Platform 之間的受眾共用
solution: Audience Manager
title: Audience Manager 與 Adobe Experience Platform 之間的受眾共用
keywords: AEP觀眾分享， AEP區隔，平台區隔，區隔分享，觀眾分享，分享區隔
feature: 平台整合
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1506'
ht-degree: 2%

---

# Experience Platform區段與Audience Manager和其他Experience Cloud解決方案共用{#aam-aep-audience-sharing}

>[!NOTE]
>
> 請洽詢您的Adobe銷售代表，以解除鎖定此功能的存取權。

## 概述 {#overview}

Audience Manager與Adobe Experience Platform之間的受眾分享功能可讓您將Audience Manager特徵和區段分享至Adobe Experience Platform，反之亦然。 您需要[[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)才能啟用Audience Manager與Adobe Experience Platform之間的觀眾分享。

您可以在Experience Platform中使用Audience Manager特徵和區段，將Audience Manager資料新增至客戶個人檔案，並從Experience Platform[區段服務](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)獲益。

在Audience Manager中，您可以將Experience Platform段用於資料管理平台使用案例，例如：
* 將[協力廠商資料](/help/using/overview/data-types-collected.md#third-party-data)新增至您的區段；
* [算法模型](/help/using/features/algorithmic-models/understanding-models.md);
* 將區段啟用至Experience Platform[目標目錄](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)尚未支援的目標。

此外，您的Experience Platform區段會透過[核心服務](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)共用給其他Experience Cloud解決方案。

>[!IMPORTANT]
>
> * 您需要Audience Manager授權才能啟用上述資料管理平台使用案例。
> * 您&#x200B;*不需要* Audience Manager授權，即可透過核心服務整合與Adobe Advertising Cloud、Adobe Target、Marketo和其他Experience Cloud解決方案共用Experience Platform區段。


<br> 

請參閱下表以取得觀眾分享使用案例的概觀：

| **使用個案** | **Adobe Experience Platform** | **Audience Manager** | **核心服務** |
---------|----------|---------|---------
| **觀眾分享** | <ul><li>利用Audience Manager資料豐富客戶個人檔案</li><li>在Audience Manager分段中使用Experience Platform資料</li></ul> | <ul><li>新增第三方資料至區段</li><li>演算法模型</li><li>啟動至其他目的地</li></ul> | 在其他Experience Platform解決方案(例如Adobe Target、Advertising Cloud或Marketo)中使用Experience Cloud區段。 |

<br> 

## Audience Manager群體與Adobe Experience Platform特徵{#aam-segments-traits-in-aep}

您的Audience Manager特徵和區段在Experience Platform中會以&#x200B;**Audiences**&#x200B;的形式出現在區段工作流程中。 如需Audience Manager區段和Experience Platform特徵的詳細資訊，請參閱：

* [區段服務概觀](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Experience Platform區段產生器使用指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager連接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Adobe Experience PlatformAudience Manager{#aep-segments-in-aam}中的區段

您在Experience Platform中建立的區段會以訊號、特徵和區段的形式出現在Audience Manager介面中，並包含下列構成規則：

* 信號：對於每個Experience Platform段，應以`segID = segment ID`的形式看到信號。
* 特徵：特徵規則是Experience Platform區段的ID。
* 區段：區段由上述特徵組成。

### 信號{#aep-segments-as-aam-signals}

選擇&#x200B;**[!UICONTROL Audience Data > Signals > General Online Data]**&#x200B;並按`SegId`搜索以查找來自Experience Platform的信號。 您可使用此畫面進行除錯，以檢查Experience Platform與Audience Manager之間的整合是否已正確設定。

![在「信號」儀表板中查看Experience Platform信號中的Audience Manager](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 特徵 {#aep-segments-as-aam-traits}

Audience Manager會在您的特徵儲存區中自動建立名為&#x200B;**Experience Platform特徵**&#x200B;的特徵資料夾。

![來自Experience Platform儀表板的特徵](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

您可以在區段中使用自動建立的特徵與其他特徵一起使用。 例如，您可以混合從Experience Platform區段建立的特徵與透過[Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md)取得的第三方特徵。

如需從Experience Platform區段自動建立之特徵的範例，請參閱下列螢幕擷取：

![Experience Platform特徵](/help/using/integration/integration-aep/assets/aep-trait.png)


| 項目編號 | 名稱 | 說明 |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | 從Experience Platform區段建立的特徵會建立為Audience Manager的已登入特徵。 |
| 2 | [!UICONTROL Data Source] | 自動建立。 從Experience Platform區段自動建立的所有特徵和區段都會儲存在資料來源&#x200B;**[!UICONTROL Adobe Experience Platform Audience Sharing]**&#x200B;中。 |
| 3 | [!UICONTROL Integration Code] | 整合代碼與Experience Platform中的區段ID對應。 |
| 4 | [!UICONTROL Trait Expression] | 特徵運算式為`segID = segment ID in Experience Platform`。 |
| 5 | [!UICONTROL Segments with this Trait] | 使用此特徵作為構圖的自動建立區段。 |

<br> 

### 區段 {#aep-segments-as-aam-segments}

Audience Manager會自動在區段儲存區中建立名為&#x200B;**Experience Platform區段**&#x200B;的區段資料夾。

![控制面板的螢幕擷取](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

如需從Experience Platform區段自動建立的區段範例，請參閱下列螢幕擷取：

![區段的螢幕擷取](/help/using/integration/integration-aep/assets/aep-segment.png)

| 項目編號 | 名稱 | 說明 |
---------|----------|---------
| 3 | [!UICONTROL Integration Code] | 整合代碼與Experience Platform中的區段ID對應。 |
| 2 | [!UICONTROL Data Source] | 自動建立。 從Experience Platform區段自動建立的所有特徵和區段都會儲存在資料來源&#x200B;**[!DNL Adobe Experience Platform Audience Sharing]**&#x200B;中。 |
| 1 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** 指出自動建立的區段會遵循Experience Platform中設定的合併原則。 |
| 4 | [!UICONTROL Segment Rule] | 區段由[Traits區段](#aep-segments-as-aam-traits)中描述的特徵組成。 |

## Audience Manager{#aam-data-export-control-in-aep}Experience Platform中的「資料導出控制」支援

為了在Experience Platform中強制執行資料使用合規性，必須為所有適用資料集和欄位指定適當的[資料使用標籤](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html)。 此外，[資料使用原則](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html)必須啟用針對這些標籤的特定行銷動作，如[資料使用標籤與實施(DULE)架構](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)所述。

在Audience Manager與Experience Platform之間的觀眾分享程式中，任何套用至Audience Manager區段的「資料匯出控制」都會轉換為「Experience Platform資料管理」所識別的相同標籤和行銷動作，反之亦然。

>[!NOTE]
>
>有關「資料匯出控制」的更多一般資訊，請參閱[「資料匯出控制」檔案](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)。
>
>本檔案提供特定Audience Manager資料匯出控制如何對應至平台中資料使用標籤和行銷動作的參考。

### 資料匯出控制項至資料使用標籤

下表概述特定資料匯出控制項如何對應至已辨識的資料使用標籤：

| 資料匯出控制 | 資料使用標籤 |
| --- | --- |
| 無法與個人識別資訊搭配使用 | C3:資料無法結合或與直接識別資訊搭配使用 |
| 無法用於Offsite廣告定位 | C5:資料無法用於內容或廣告的喜好式跨網站定位 |
| 無法用於Onsite廣告定位 | C6:資料無法用於站上廣告定位 |
| 無法用於現場個人化 | C7:資料無法用於內容的現場定位 |

### 將資料匯出控制項匯出至行銷動作

下表概述特定資料匯出標籤如何對應至已識別的行銷動作：

| 資料匯出標籤 | 行銷動作 |
| --- | --- |
| 此目標可能會結合個人識別資訊(PII) | 與PII結合 |
| 此目標可用於離站廣告定位 | 跨網站定位 |
| 此目標可用於現場廣告定位 | 現場廣告 |
| 此目的地可用於臨場廣告個人化 | Onsite個人化 |

## 瞭解Audience Manager與Experience Platform之間的區段人口差異{#aep-aam-segment-population-differences}

區段人口數可能因Audience Manager和Experience Platform區段而異。 雖然類似或相同對象的區段數目應該相近，但人口差異可能是由下列因素造成。

### Experience Platform分段評估

Audience Manager每天更新介面中的報表數字一次。   此項更新的時間與Experience Platform中區段評估的時間很少一致。

### 配置檔案合併規則與合併策略之間的差異

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) 在Audience Manager和 [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) Experience Platform中，使用的識別圖不同。因此，預期群體間會有所差異。

### Experience Platform中的分段組成

Adobe Experience Platform與Audience Manager之間的整合為所有客戶共用了許多標準[標識名稱空間](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types):ECID、IDFA、GAID、雜湊電子郵件地址(EMAIL_LC_SHA256)、AdCloud ID。 如果您的Experience Platform區段使用其中任何一個作為合格描述檔的主要識別，描述檔會計入Audience Manager特徵和區段。

此外，Audience Manager可針對您在Experience Platform區段中使用的任何自訂身分名稱空間，在下列情況下註冊傳入的實現：
* 身分標示為主&#x200B;*和*
* 您已有對應的跨裝置資料來源已Audience Manager。

>[!NOTE]
>
> 在Experience Platform中，以身分識別原始電子郵件的受眾永遠不會出現在Audience Manager中。

例如，如果您有Experience Platform區段「我的所有客戶」，且符合資格的設定檔是CRM ID、ECID、IDFA、原始和雜湊電子郵件地址，則Audience Manager中的對應區段將僅包含CRM ID、ECID、IDFA和雜湊電子郵件地址的設定檔。 Audience Manager區段人口將小於Experience Platform區段人口。

![Experience Platform至Audience Manager分部分享——分部組成](/help/using/integration/integration-aep/assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [區段服務概觀](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform區段產生器使用指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager連接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

