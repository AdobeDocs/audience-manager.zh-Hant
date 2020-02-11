---
description: 本文說明如何在Audience manager和Adobe Experience platform之間共用觀眾。
seo-description: 本文說明如何在Audience manager和Adobe Experience platform之間共用觀眾。
seo-title: Audience manager與Adobe Experience platform之間的觀眾分享
solution: Audience Manager
title: Audience manager與Adobe Experience platform之間的觀眾分享
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: a7311c35c70bbfd0aac015524f6e65b0e59415f5

---


# Audience manager與Adobe Experience platform之間的觀眾分享 {#aam-aep-audience-sharing}

>[!NOTE]
>
> 本頁所述的功能適用於Audience manager和Adobe Experience platform的客戶。
>
> 請連絡您的Adobe銷售代表以解除鎖定此功能的存取權。

## 概述 {#overview}

Audience manager和Adobe Experience platform之間的觀眾分享功能可讓您將Audience manager特徵和區段共用至Adobe Experience Platform，反之亦然。

您可以使用Experience platform中的Audience manager特徵和細分，將Audience manager資料新增至客戶個人檔案，並從Experience platform細分服務 [中獲益](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)。

在Audience Manager中，您可以將Experience platform區段用於資料管理平台使用案例，例如：
* 將第 [三方資料新增](/help/using/overview/data-types-collected.md#third-party-data) 至您的區段；
* [算法模型](/help/using/features/algorithmic-models/understanding-models.md);
* 將區段啟用至Experience platform目標目錄尚未支援的 [目標](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)。

此外，您的Experience platform區段會透過核心服務共用給其他Experience cloud解決 [方案](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)。

<br> 

請參閱下表以取得觀眾分享使用案例的概觀：

| **使用個案** | **Adobe Experience Platform** | **Audience Manager** | **核心服務** |
---------|----------|---------|---------
| **觀眾分享** | <ul><li>運用Audience manager資料豐富客戶個人檔案</li><li>在Experience platform區隔中使用Audience manager資料</li></ul> | <ul><li>新增第三方資料至區段</li><li>演算法模型</li><li>啟動至其他目的地</li></ul> | 在其他Experience cloud解決方案（例如Adobe Target或Analytics）中使用Experience platform細分。 |

<br> 

## Adobe Experience platform中的Audience manager細分和特徵 {#aam-segments-traits-in-aep}

您的Audience manager特徵和區段會在Experience platform中顯示為 **Audiences** ，在區段工作流程中。 如需Audience manager細分和Experience platform特徵的詳細資訊，請參閱：

* [區段服務概觀](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)
* [體驗平台區段產生器使用指南](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)

<br> 

## Audience manager中的Adobe Experience platform細分 {#aep-segments-in-aam}

您在Experience platform中建立的區段會以特徵和區段的形式出現在您的Audience Manager介面中，具有下列構成規則：
* 特徵：特徵規則是「體驗平台」區段的ID。
* 區段：區段由上述特徵組成。

### 特徵 {#aep-segments-as-aam-traits}

Audience manager會在您的特徵儲存區中自動建立名 **為「Experience Platform Traits** 」的特徵資料夾。

![Experience platform儀表板的特性](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

您可以在區段中使用自動建立的特徵與其他特徵一起使用。 例如，您可以將從Experience platform區段建立的特徵與透過 [Audience Marketplace取得的第三方特徵混](/help/using/features/audience-marketplace/audience-marketplace.md)合使用。

如需從「體驗平台」區段自動建立之特徵的範例，請參閱以下螢幕擷取：

![Experience platform的特性](/help/using/integration/integration-aep/assets/aep-trait.png)


| 項目編號 | 名稱 | 說明 |
---------|----------|---------
| 1 | 特徵類型 | 從Experience platform區段建立的特徵會在Audience manager中建立為已登入特徵。 |
| 2 | 資料來源 | 自動建立。 所有自動從Experience platform區段建立的特徵和區段都儲存在資料來源 **Adobe Experience platform觀眾共用中**。 |
| 3 | 整合代碼 | 整合程式碼對應於Experience platform中的區段ID。 |
| 4 | 特徵表達式 | 特徵表達式為 `segID = segment ID in Experience Platform`。 |
| 5 | 具有此特徵的區段 | 使用此特徵作為構圖的自動建立區段。 |

<br> 

### 區段 {#aep-segments-as-aam-segments}

Audience manager會在您的區段儲存空間中自動建立 **名為「Experience Platform Segments** 」的區段資料夾。

![控制面板的螢幕擷取](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

如需從Experience platform區段自動建立的區段範例，請參閱下列螢幕擷取：

![區段的螢幕擷取](/help/using/integration/integration-aep/assets/aep-segment.png)

| 項目編號 | 名稱 | 說明 |
---------|----------|---------
| 1 | 整合代碼 | 整合程式碼對應於Experience platform中的區段ID。 |
| 2 | 資料來源 | 自動建立。 所有自動從Experience platform區段建立的特徵和區段都儲存在資料來源 **Adobe Experience platform觀眾共用中**。 |
| 3 | 描述檔合併規則 | **外部合併原則** ：指出自動建立的區段會遵循Experience platform中設定的合併原則。 |
| 4 | 區段規則 | 區段由「特徵」區段中描述的 [特徵組成](#aep-segments-as-aam-traits)。 |
