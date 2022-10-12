---
description: 了解如何啟用資料共用，以及如何在Audience Manager與Adobe Experience Platform之間共用受眾
solution: Audience Manager
title: Experience Platform區段共用與Audience Manager和其他Experience Cloud解決方案
keywords: AEP受眾共用， AEP區段，平台區段，區段共用，受眾共用，共用區段， AAM AEP區段共用
feature: Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '1901'
ht-degree: 1%

---

# Experience Platform區段共用與Audience Manager和其他Experience Cloud解決方案

## 概述 {#overview}

Audience Manager和Adobe Experience Platform之間的受眾共用功能可讓您將Audience Manager特徵和區段共用至Adobe Experience Platform，反之亦然。 您需要 [[!DNL Audience Manager Connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) 啟用Audience Manager與Adobe Experience Platform之間的受眾共用。

您可以在Experience Platform中使用Audience Manager特徵和區段，將Audience Manager資料新增至客戶設定檔，並從Experience Platform中受益 [細分服務](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en).

在「Audience Manager」中，您可以將「Experience Platform」區段用於「資料管理平台」使用案例，例如：
* 新增 [第三方資料](/help/using/overview/data-types-collected.md#third-party-data) 至您的區段；
* [演算法建模](/help/using/features/algorithmic-models/understanding-models.md);
* 對Experience Platform尚未支援的目的地啟用區段 [目的地目錄](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

此外，您的Experience Platform區段會透過 [核心服務](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * 您需要Audience Manager授權才能啟用上述資料管理平台使用案例。
> * 您 *不需要* 透過核心服務整合，與Adobe Advertising Cloud、Adobe Target、Marketo和其他Experience Cloud解決方案共用Experience Platform區段的Audience Manager授權。


請參閱下表，概略了解受眾共用使用案例：

| **使用個案** | **Adobe Experience Platform** | **Audience Manager** | **核心服務** |
|---------|----------|---------|---------|
| **受眾共用** | <ul><li>使用Audience Manager資料豐富客戶設定檔</li><li>在Audience Manager細分中使用Experience Platform資料</li></ul> | <ul><li>新增第三方資料至區段</li><li>演算法建模</li><li>啟動至其他目的地</li></ul> | 在Adobe Target、Advertising Cloud或Marketo等其他Experience Cloud解決方案中使用Experience Platform區段。 |

{style=&quot;table-layout:auto&quot;}

## Audience Manager區段和Adobe Experience Platform特徵 {#aam-segments-traits-in-aep}

以下各節說明如何啟用從Audience Manager到Experience Platform的資料共用，以及如何在Experience Platform中使用Audience Manager特徵和區段。

### 啟用從Audience Manager到Experience Platform的資料共用 {#enable-aam-to-aep-data}

若要將區段和特徵從Audience Manager傳送至Experience Platform，您必須在Experience Platform來源目錄中設定Audience Manager來源連接器。 這是自助服務工作流程，不需要Adobe客戶服務或工程團隊參與。 要設定Audience Manager源連接器，請閱讀：

* [Audience Manager來源](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [在UI中建立Adobe Audience Manager來源連線](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Adobe可鼓勵客戶在不選取 **[!UICONTROL Select all segments]** 和 **[!UICONTROL Select all traits]** 選項，如下所示。 首次使用Audience Manager來源將Audience Manager區段傳送至Platform時，擷取大量Audience Manager區段母體會直接影響您的設定檔總數。 這表示選取所有區段可能會導致設定檔計數超過您的授權使用權限。
>
>![螢幕擷圖顯示「選取所有區段」和「選取所有特徵」選項，此選項在工作流程中未勾選，而會連線至Audience Manager來源連接器。](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### 在Audience Manager中使用Experience Platform特徵和區段 {#use-aam-data-in-aep}

設定Audience Manager來源連接器以從Audience Manager匯入特徵和區段後，您的Audience Manager資料在Experience Platform中顯示為 **對象** 在區段工作流程中。 如需Audience Manager區段和Experience Platform特徵的詳細資訊，請參閱：

* [區段服務概觀](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Experience Platform區段產生器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Adobe Experience Platform區段Audience Manager {#aep-segments-in-aam}

以下各節說明如何啟用從Experience Platform到Audience Manager的資料共用，以及如何在Audience Manager中使用Experience Platform區段。

### 啟用從Experience Platform到Audience Manager的資料共用 {#enable-aep-to-aam-data}

>[!NOTE]
>
> 請連絡您的Adobe客戶成功經理或客戶服務，以解除鎖定此功能的存取權。

若要將區段從Experience Platform傳送至Audience Manager，您必須聯絡客戶服務或您的客戶成功經理。 客戶服務和客戶支援管理團隊必須提交票證(請參閱範本票證AAM-52354)，才能啟用從平台到Audience Manager的連線。

請務必共用從Platform傳至Audience Manager的資料計畫，以確保連線設定正確。 例如，如果您需要為傳送至Adobe Target的區段共用地區資料，則需要在票證中傳達這些資訊。 從Experience Platform到Audience Manager的資料共用連線會在提交請求後的6個工作天內設定。

### 在Audience Manager中使用Experience Platform區段 {#use-aep-data-in-aam}

您在「Experience Platform」中建立的區段，會以訊號、特徵和區段形式顯示在Audience Manager介面中，並具有下列組成規則：

* 訊號：對於每個Experience Platform區段，您應會在表單中看到訊號 `segID = segment ID`.
* 特徵：特徵規則是Experience Platform區段的ID。
* 區段：區段包含上述特徵。

### 訊號 {#aep-segments-as-aam-signals}

選擇 **[!UICONTROL Audience Data > Signals > General Online Data]** 搜索依據 `SegId` 尋找來自Experience Platform的訊號。 您可以使用此畫面進行除錯，以檢查Experience Platform和Audience Manager之間的整合是否已正確設定。

![請參閱訊號控制面板中Audience Manager中的Experience Platform訊號](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 特徵 {#aep-segments-as-aam-traits}

Audience Manager會自動建立名為 **Experience Platform特徵** 在特徵儲存區中。

![來自Experience Platform控制面板的特徵](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

您可以在區段中與其他特徵搭配使用自動建立的特徵。 例如，您可以混合從Experience Platform區段建立的特徵和透過 [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

如需從Experience Platform區段自動建立的特徵範例，請參閱下方的螢幕擷取畫面：

![來自Experience Platform的特徵](/help/using/integration/integration-aep/assets/aep-trait.png)


| 物料編號 | 名稱 | 說明 |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | 從Experience Platform區段建立的特徵會在Audience Manager中建立為已上線的特徵。 |
| 2 | [!UICONTROL Data Source] | 自動建立。 從Experience Platform區段自動建立的所有特徵和區段都會儲存在資料來源中 **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | 整合代碼對應至Experience Platform中的區段ID。 |
| 4 | [!UICONTROL Trait Expression] | 特徵運算式為 `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | 以此特徵作為組成的自動建立區段。 |

{style=&quot;table-layout:auto&quot;}

### 區段 {#aep-segments-as-aam-segments}

Audience Manager會自動建立區段資料夾，稱為 **Experience Platform區段** 在區段儲存中。

![控制面板的螢幕擷圖](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

如需從Experience Platform區段自動建立的區段範例，請參閱下方的螢幕擷圖：

![區段的螢幕擷圖](/help/using/integration/integration-aep/assets/aep-segment.png)

| 物料編號 | 名稱 | 說明 |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | 整合代碼對應至Experience Platform中的區段ID。 |
| 2 | [!UICONTROL Data Source] | 自動建立。 從Experience Platform區段自動建立的所有特徵和區段都會儲存在資料來源中 **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** 指示自動建立的段遵循在Experience Platform中設定的合併策略。 |
| 4 | [!UICONTROL Segment Rule] | 區段包含 [特徵區段](#aep-segments-as-aam-traits). |

{style=&quot;table-layout:auto&quot;}

## Audience Manager資料匯出控制支援Experience Platform {#aam-data-export-control-in-aep}

為了在Experience Platform中強制遵循資料使用量，必須為所有適用的資料集和欄位指定適當 [資料使用量標籤](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html). 此外， [資料使用原則](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html) 必須啟用，才能依照 [資料使用標籤與實作(DULE)架構](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework).

在Audience Manager與Experience Platform之間的受眾共用程式中，已套用至Audience Manager區段的任何資料匯出控制，都會轉譯為Experience Platform資料控管所認可的相等標籤和行銷動作，反之亦然。

>[!NOTE]
>
>如需資料匯出控制的更一般資訊，請參閱 [資料匯出控制檔案](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
>
>本檔案提供特定「Audience Manager資料匯出控制項」如何對應至Platform中資料使用標籤和行銷動作的參考。

### 資料匯出控制項至資料使用量標籤

下表概述特定資料匯出控制項如何對應至已識別的資料使用量標籤：

| 資料匯出控制 | 資料使用量標籤 |
| --- | --- |
| 無法與個人識別資訊搭配使用 | C3:資料無法結合或與可直接識別的資訊搭配使用 |
| 無法用於Offsite廣告鎖定 | C5:資料無法用於內容或廣告的興趣型跨網站目標定位 |
| 無法用於Onsite廣告鎖定 | C6:資料無法用於站上廣告鎖定目標 |
| 無法用於站上個人化 | C7:資料無法用於內容的站上定位 |

{style=&quot;table-layout:auto&quot;}

### 行銷動作的資料匯出控制

下表概述特定資料匯出標籤如何對應至已識別的行銷動作：

| 資料匯出標籤 | 行銷動作 |
| --- | --- |
| 此目的地可能會啟用與個人識別資訊(PII)的結合 | 與PII結合 |
| 此目的地可用於離站廣告鎖定 | 跨網站鎖定 |
| 此目的地可用於站上廣告鎖定 | 站上廣告 |
| 此目的地可用於站上廣告個人化 | 站上個人化 |

{style=&quot;table-layout:auto&quot;}

## 了解Audience Manager和Experience Platform之間的區段母體差異 {#aep-aam-segment-population-differences}

區段母體數目可能因您的Audience Manager和Experience Platform區段而異。 雖然類似或相同受眾的區段數應相近，但人口差異可能是因為下列因素所致。

### 區段評估Experience Platform

Audience Manager每天更新介面中的報表編號一次。 此項更新的時間很少與Experience Platform中區段評估的時間一致。

### 配置檔案合併規則與合併策略之間的差異

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) Audience Manager和 [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) 在Experience Platform中，工作方式不同，而每個使用的身分圖表也會有所不同。 因此，預期區段母體之間會有一些差異。

>[!NOTE]
>
> 從Experience Platform到Audience Manager共用區段時，您的Platform組織 [預設合併原則](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy) 優先於 [區段使用的合併原則](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies) 與Audience Manager共用。 例如，如果共用區段的合併原則允許 [ID匯整](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure)，但組織的預設合併政策未執行，這可能會導致Platform和Audience Manager之間的母體差異。

### Experience Platform中的區段組成

Adobe Experience Platform與Audience Manager的整合共用許多標準 [身分識別命名空間](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types) 對於所有客戶：ECID、IDFA、GAID、雜湊電子郵件地址(EMAIL_LC_SHA256)、AdCloud ID。 如果您的Experience Platform區段使用其中任何一個作為合格設定檔的主要身分，則設定檔會計入Audience Manager特徵和區段。

>[!NOTE]
>
> 身分Experience Platform中將原始電子郵件作為輸入資料的對象永遠不會出現在Audience Manager中。

例如，如果您有「我的所有Experience Platform」區段，且合格的設定檔會是CRM ID、ECID、IDFA、原始和雜湊電子郵件地址，則Audience Manager中的對應區段只會包含以ECID、IDFA和雜湊電子郵件地址作為輸入資料的設定檔。 Audience Manager中的區段母體會小於Experience Platform中的區段母體。

![Experience Platform對Audience Manager分段共用 — 分段組成](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [區段服務概觀](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform區段產生器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

