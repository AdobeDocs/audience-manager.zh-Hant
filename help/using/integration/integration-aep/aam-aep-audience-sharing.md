---
description: 瞭解如何啟用資料共用，以及如何在Audience Manager和Adobe Experience Platform之間共用受眾
solution: Audience Manager
title: Experience Platform區段與Audience Manager和其他Experience Cloud解決方案共用
keywords: AEP受眾共用， AEP區段，平台區段，區段共用，受眾共用，共用區段， AAM AEP區段共用
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# Experience Platform區段與Audience Manager和其他Experience Cloud解決方案共用

## 概述 {#overview}

Audience Manager和Adobe Experience Platform之間的受眾共用功能可讓您將您的Audience Manager特徵和區段共用至Adobe Experience Platform，並將Experience Platform區段共用至Audience Manager。

您需要Experience Platform中的[[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=zh-Hant)和[Experience Cloud對象](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=zh-Hant)目的地，才能在Audience Manager和Adobe Experience Platform之間啟用對象共用。

您可以使用Experience Platform中的Audience Manager特徵和區段，將Audience Manager資料新增至您的客戶設定檔，並從Experience Platform [細分服務](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=zh-Hant)中獲益。

在Audience Manager中，您可以將Experience Platform區段用於「資料管理平台」的使用案例，例如：
* 將[第三方資料](/help/using/overview/data-types-collected.md#third-party-data)新增至您的區段；
* [演演算法模型](/help/using/features/algorithmic-models/understanding-models.md)；
* 對Experience Platform [目的地目錄](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html?lang=zh-Hant)中尚未支援的目的地啟用您的區段。

此外，您的Experience Platform區段已透過[核心服務](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=zh-Hant)與其他Experience Cloud解決方案共用。

>[!IMPORTANT]
>
> * 您需要Audience Manager授權才能啟用上述資料管理平台使用案例。
> * 您&#x200B;*不需要* Audience Manager授權，即可透過核心服務整合，與Adobe Advertising Cloud、Adobe Target、Marketo和其他Experience Cloud解決方案共用Experience Platform區段。

請參閱下表，以取得對象共用使用案例的概觀：

| **使用個案** | **Adobe Experience Platform** | **Audience Manager** | **核心服務** |
|---------|----------|---------|---------|
| **對象共用** | <ul><li>利用Audience Manager資料豐富客戶設定檔</li><li>在Experience Platform區段中使用Audience Manager資料</li></ul> | <ul><li>將第三方資料新增至區段</li><li>演演算法建模</li><li>啟用至其他目的地</li></ul> | 在其他Experience Cloud解決方案(例如Adobe Target、Advertising Cloud或Marketo)中使用Experience Platform區段。 |

{style="table-layout:auto"}

## Adobe Experience Platform中的Audience Manager區段和特徵 {#aam-segments-traits-in-aep}

以下各節說明如何啟用從Audience Manager到Experience Platform的資料共用，以及如何在Experience Platform中使用Audience Manager特徵和區段。

### 啟用從Audience Manager到Experience Platform的資料共用 {#enable-aam-to-aep-data}

若要將區段和特徵從Audience Manager傳送至Experience Platform，您必須在Audience Manager來源目錄中設定Experience Platform來源聯結器。 這是自助式工作流程，不需要Adobe客戶服務或工程團隊的參與。 若要設定Audience Manager來源聯結器，請閱讀：

* [Audience Manager來源](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=zh-Hant)
* [在UI中建立Adobe Audience Manager來源連線](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=zh-Hant)

>[!IMPORTANT]
>
>Adobe鼓勵客戶在不選取&#x200B;**[!UICONTROL Select all segments]**&#x200B;和&#x200B;**[!UICONTROL Select all traits]**&#x200B;選項的情況下設定連線，如下所示。 當您使用Audience Manager來源首次將Audience Manager區段傳送至Platform時，大量的Audience Manager區段母體的擷取會直接影響您的總設定檔計數。 這表示選取所有區段可能會導致設定檔計數超過您的授權使用權益。
>
>![此熒幕擷圖顯示工作流程中未勾選的「選取所有區段」和「選取所有特徵」選項，以便連線至Audience Manager來源聯結器。](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### 在Experience Platform中使用Audience Manager特徵和區段 {#use-aam-data-in-aep}

設定Audience Manager來源聯結器以從Audience Manager匯入特徵和區段後，您的Audience Manager資料在Experience Platform中會顯示為區段工作流程中的&#x200B;**受眾**。 如需Experience Platform中Audience Manager區段和特徵的詳細資訊，請閱讀：

* [分段服務總覽](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=zh-Hant#audiences)
* [Experience Platform區段產生器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=zh-Hant#audiences)

## Audience Manager中的Adobe Experience Platform區段 {#aep-segments-in-aam}

以下各節說明如何啟用從Experience Platform到Audience Manager的資料共用，以及如何在Audience Manager中使用Experience Platform區段。

### 啟用從Experience Platform到Audience Manager的資料共用 {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> 本節說明從Experience Platform到Audience Manager的舊版區段共用整合。 您現在可以設定這項整合，不需要Adobe客戶代表的支援。 如需詳細資訊，請閱讀[Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=zh-Hant)目的地檔案。

>[!NOTE]
>
> 請聯絡您的Adobe客戶成功經理或客戶服務，以解鎖此功能的存取權。

若要將區段從Experience Platform傳送至Audience Manager，您必須聯絡客戶服務或您的客戶成功經理。 客戶服務及客戶支援管理團隊必須提交票證(請參閱範本票證AAM-52354)以啟用從Platform到Audience Manager的連線。

請務必共用從Platform到Audience Manager之資料的計畫，以確保連線設定正確。 例如，如果您需要為傳送至Adobe Target的區段共用區域資料，則需要在票證中傳達此資訊。 從Experience Platform到Audience Manager的資料共用連線會在提交請求後的6個工作天內設定。

### 在Audience Manager中使用Experience Platform區段 {#use-aep-data-in-aam}

您在Experience Platform中建立的區段會在Audience Manager介面中顯示為訊號、特徵和區段，並包含下列構成規則：

* 訊號：每個Experience Platform區段應該會看到`segID = segment ID`格式的訊號。
* 特徵：特徵規則是Experience Platform區段的ID。
* 區段：區段由上述特徵組成。

### 訊號 {#aep-segments-as-aam-signals}

選取&#x200B;**[!UICONTROL Audience Data > Signals > General Online Data]**&#x200B;並依`SegId`搜尋，以尋找來自Experience Platform的訊號。 您可以使用此畫面進行偵錯，以檢查Experience Platform與Audience Manager之間的整合是否已正確設定。

![在訊號儀表板中檢視Audience Manager中的Experience Platform訊號](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 特徵 {#aep-segments-as-aam-traits}

Audience Manager會在您的特徵儲存空間中自動建立名為&#x200B;**Experience Platform特徵**&#x200B;的特徵資料夾。

來自Experience Platform儀表板的![特徵](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

您可以在區段中使用自動建立的特徵，連同其他特徵。 例如，您可以將從Experience Platform區段建立的特徵與透過[Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md)取得的第三方特徵混合在一起。

如需從Experience Platform區段自動建立的特徵範例，請參閱下方的熒幕擷圖：

來自Experience Platform的![特徵](/help/using/integration/integration-aep/assets/aep-trait.png)


| 專案編號 | 名稱 | 說明 |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | 從Experience Platform區段建立的特徵，會在Audience Manager中建立為已登入的特徵。 |
| 2 | [!UICONTROL Data Source] | 已自動建立。 所有從Experience Platform區段自動建立的特徵和區段都會儲存在資料來源&#x200B;**[!UICONTROL Adobe Experience Platform Audience Sharing]**&#x200B;中。 |
| 3 | [!UICONTROL Integration Code] | 整合程式碼會對應至Experience Platform中的區段ID。 |
| 4 | [!UICONTROL Trait Expression] | 特徵運算式是`segID = segment ID in Experience Platform`。 |
| 5 | [!UICONTROL Segments with this Trait] | 使用此特徵作為構成的自動建立區段。 |

{style="table-layout:auto"}

### 區段 {#aep-segments-as-aam-segments}

Audience Manager會在您的區段儲存空間中自動建立名為&#x200B;**Experience Platform區段**&#x200B;的區段資料夾。

![儀表板的熒幕擷圖](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

如需從Experience Platform區段自動建立的區段範例，請參閱下方的熒幕擷圖：

![區段](/help/using/integration/integration-aep/assets/aep-segment.png)的熒幕擷圖

| 專案編號 | 名稱 | 說明 |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | 整合程式碼會對應至Experience Platform中的區段ID。 |
| 2 | [!UICONTROL Data Source] | 已自動建立。 所有從Experience Platform區段自動建立的特徵和區段都會儲存在資料來源&#x200B;**[!DNL Adobe Experience Platform Audience Sharing]**&#x200B;中。 |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]**&#x200B;表示自動建立的區段會遵循Experience Platform中設定的合併原則。 |
| 4 | [!UICONTROL Segment Rule] | 此區段包含[特徵區段](#aep-segments-as-aam-traits)中說明的特徵。 |

{style="table-layout:auto"}

## Experience Platform中的Audience Manager資料匯出控制支援 {#aam-data-export-control-in-aep}

為了在Experience Platform中強制資料使用規範，所有適用的資料集和欄位都必須有適當的[資料使用標籤](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=zh-Hant)。 此外，必須啟用[資料使用原則](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=zh-Hant#)，以針對這些標籤執行特定的行銷動作，如[資料使用標籤與實作(DULE)架構](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=zh-Hant#dule-framework)所概述。

在Audience Manager和Experience Platform之間的受眾共用程式中，套用至Audience Manager區段的任何資料匯出控制都會轉譯為Experience Platform資料控管所識別的相等標籤和行銷動作，反之亦然。

>[!NOTE]
>
>如需資料匯出控制項的一般資訊，請參閱[資料匯出控制項檔案](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=zh-Hant)。
>
>本檔案提供特定Audience Manager資料匯出控制項如何對應至Platform中資料使用標籤和行銷動作的參考資料。

### 資料匯出控制到資料使用標籤

下表概述特定資料匯出控制項如何對應至已識別的資料使用標籤：

| 資料匯出控制 | 資料使用情況標籤 |
| --- | --- |
| 無法與個人識別資訊搭配使用 | C3：資料無法結合或搭配可直接識別的資訊使用 |
| 無法用於站外廣告目標定位 | C5：資料不可用於基於興趣、跨網站的內容或廣告目標定位 |
| 無法用於網站上的廣告目標定位 | C6：資料無法用於網站上的廣告目標定位 |
| 無法用於網站上的個人化 | C7：資料無法用於網站上的內容目標定位 |

{style="table-layout:auto"}

### 行銷動作的資料匯出控制

下表概述特定「資料匯出標籤」對應至已識別行銷動作的方式：

| 資料匯出標籤 | 行銷動作 |
| --- | --- |
| 此目的地可能會啟用與個人識別資訊(PII)的組合 | 與PII結合 |
| 此目的地可用於站外廣告目標定位 | 跨網站目標定位 |
| 此目的地可用於網站上的廣告目標定位 | 現場Advertising |
| 此目的地可用於網站上的廣告個人化 | 現場Personalization |

{style="table-layout:auto"}

## 瞭解Audience Manager和Experience Platform之間的區段母體差異 {#aep-aam-segment-population-differences}

區段母體數量可能因Audience Manager和Experience Platform區段而異。 雖然類似或相同對象的區段數字應該接近，但母體中的差異可能是下列因素所造成。

### Experience Platform中的區段評估

Audience Manager會每天更新一次介面中的報表編號。 此更新很少會與Experience Platform中區段評估的時間一致。

### 設定檔合併規則與合併原則之間的差異

Audience Manager中的[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md)與Experience Platform中的[[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html?lang=zh-Hant)運作方式不同，而且每個使用的身分圖表也不同。 因此，區段母體之間可能會出現一些差異。

>[!NOTE]
>
> 從Experience Platform共用區段至Audience Manager時，您的Platform組織[預設合併原則](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=zh-Hant#default-merge-policy)會優先於與Audience Manager共用的區段[所使用的](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=zh-Hant#merge-policies)合併原則。 例如，如果共用區段的合併原則允許[ID拼接](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=zh-Hant#configure)，但組織的預設合併原則不允許，這可能會導致Platform和Audience Manager之間的母體差異。

### Experience Platform中的區段構成

Adobe Experience Platform與Audience Manager之間的整合為所有客戶共用許多標準的[身分名稱空間](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=zh-Hant#identity-types)：ECID、IDFA、GAID、雜湊電子郵件地址(EMAIL_LC_SHA256)、AdCloud ID。 如果您的Experience Platform區段使用任何這些作為合格設定檔的主要身分，則設定檔會計入Audience Manager特徵和區段中。

>[!NOTE]
>
> Experience Platform中去除原始電子郵件身分的受眾永遠不會出現在Audience Manager中。

例如，如果您有Experience Platform區段「我的所有客戶」，且合格的設定檔為CRM ID、ECID、IDFA、原始和雜湊電子郵件地址，則Audience Manager中的對應區段將僅包含以ECID、IDFA和雜湊電子郵件地址作為輸入資料的設定檔。 Audience Manager中的區段母體將小於Experience Platform中的區段母體。

![Experience Platform到Audience Manager區段共用 — 區段組合](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [分段服務總覽](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=zh-Hant#audiences)
>* [Experience Platform區段產生器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=zh-Hant#audiences)
>* [Audience Manager聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=zh-Hant)
