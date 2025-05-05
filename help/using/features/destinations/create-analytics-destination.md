---
description: Audience Analytics 可讓您傳送 Audience Manager 區段至 Analytics。若要使用此功能，您可以在 Audience Manager 中建立 Analytics 目的地並將區段對應至該目的地。
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: 設定Analytics目的地
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: ef8cca16c8c9478f8558c26bf6f3ae95cd72e7ac
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 4%

---

# 設定Analytics目的地

## 要求 {#requirements}

若要設定Analytics目的地，您的Audience Manager使用者必須擁有管理員許可權。 請參閱管理指南中的[建立使用者](/help/using/features/administration/administration-overview.md#create-users)。 請注意，擁有`CREATE_DESTINATIONS` [萬用字元許可權](/help/using/features/administration/administration-overview.md#wild-card-permissions)並不足以建立Analytics目的地。
如需進一步需求，請參閱[Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html)中的先決條件。

## 您的預設分析目的地和新的分析目的地

| Analytics目的地型別 | 說明 |
|---|---|
| 預設值 | 此預設目的地的名稱為「Adobe Analytics」，您可以編輯此名稱。 對應的報表套裝ID會顯示在您Audience Manager特徵和區段的資料夾儲存空間中。 <br>  如果您的帳戶具有： <br>，則Audience Manager會自動建立一個目的地  <ul><li>符合[Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html)檔案中描述的需求。</li><li>Analytics中的[報告套裝](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html)。</li></ul> |
| 新增 | 若要建立新的Analytics目的地，請前往「對象資料>目的地>建立新目的地」 ，並遵循以下各節所述的步驟操作。 |

## Adobe Analytics中的Audience Manager區段資格 {#segment-qualifications}

將區段資訊傳送至Analytics目的地時，Audience Manager只會傳送訪客符合資格的區段。 如果訪客不再符合區段的資格，此資訊&#x200B;_不會_&#x200B;轉送至Adobe Analytics。

例如，請考量下列區段規則：

* 區段A：特徵1和特徵2
* 區段B：特徵1而非特徵2

在Analytics報表中，即使設定檔已停止符合區段B的資格，仍會顯示為符合兩個區段的資格。

## 步驟1：提供基本資訊

此區段包含啟動Analytics目的地建立程式的欄位和選項。 若要完成本節：

1. 按一下&#x200B;**基本資訊**&#x200B;以公開控制項。
2. 為目的地命名。 避免使用縮寫和特殊字元。
3. *（選擇性）*&#x200B;說明目的地。 簡潔的說明是定義或提供更多目的地相關資訊的有效方式。
4. *（選擇性）*&#x200B;在&#x200B;**Platform**&#x200B;清單中，保留預設為&#x200B;**全部**。 目前，這些選項沒有任何作用。 其設計可支援日後可能新增的功能。
5. 在&#x200B;**類別**&#x200B;清單中，選取&#x200B;**Adobe Experience Cloud**。
6. 在&#x200B;**型別**&#x200B;清單中，選取&#x200B;**Adobe Analytics**。
7. 按一下[儲存]&#x200B;**移至[組態]設定，或按一下[資料匯出標籤]**&#x200B;將匯出控制項套用至目的地。**&#x200B;**

>[!NOTE]
>
>對於Analytics目的地，預設會選取&#x200B;**自動填入目的地對應**&#x200B;核取方塊和&#x200B;**區段識別碼**&#x200B;選項。 您無法變更這些設定。

![基本資訊](assets/basicinformation.png)

## 步驟2：設定資料匯出控制項

此區段包含將[資料匯出控制項](/help/using/features/data-export-controls.md)套用至Analytics目的地的選項。 如果您不使用資料匯出控制項，請略過此步驟。 若要完成本節：

1. 按一下&#x200B;**資料匯出控制項**&#x200B;以公開控制項。
1. 選取與套用至目的地的資料匯出控制對應的標籤（請參閱[將資料匯出標籤新增至目的地](/help/using/features/destinations/add-data-export-labels.md) ）。 對於Analytics目的地，預設會選取PII核取方塊。
1. 按一下&#x200B;**「儲存」**。

![exportcontrols](assets/exportControls.png)

## 步驟3：對應報表套裝

設定區段會列出已啟用伺服器端轉送的Analytics報表套裝。 如果您有多個Analytics目的地，則指派給這些目的地的報表套裝會互斥，並由Audience Manager強制執行。 若要完成本節：

1. 按一下&#x200B;**組態**&#x200B;以公開控制項。
1. 選取您要傳送區段的一或多個報表套裝。
1. 按一下&#x200B;**「儲存」**。

![報告套裝](assets/reportSuites.png)

## 步驟4：區段對應

本節提供可讓您自動或手動對應區段的選項。

| 對應選項 | 說明 |
|---|---|
| 自動對應所有目前和未來的區段 | 依預設選取，此功能會根據每次點選將訪客符合資格的所有區段傳送至Analytics。 <br>  如果訪客在一次點選中屬於超過150個Audience Manager區段，系統只會將最近符合資格的150個區段傳送至Analytics，其餘清單則會截斷。 系統會傳送額外標幟給Analytics，表示區段清單已截斷。 此動作在「對象名稱」維度中顯示為「已達對象上限」，在「對象ID」維度中顯示為「1」。 如需詳細資訊，請參閱[常見問題集](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html)。 <br>  此外，此選項也會影響[區段產生器](/help/using/features/segments/segment-builder.md)中的目的地可用性。 例如，如果區段自動對應至Analytics目的地，該目的地將無法在「區段產生器」的[目的地對應](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations)區段中選取。 Analytics目的地會呈現灰色，並在目的地瀏覽器的「型別」欄中顯示「Analytics」。 |
| 手動對應區段 | 此選項會顯示搜尋和瀏覽控制項，可讓您選擇要將哪些區段傳送至Analytics。 <br>  若要搜尋區段： <br>  <ol><li>在搜尋欄位中輸入區段名稱或ID。</li><li>按一下<b>新增。</b></li><li>繼續搜尋並新增區段，或按一下[完成]。<b></b></li></ol><br>  若要瀏覽區段： <ol><li>按一下<b>瀏覽所有區段</b>。 這會公開可用區段的清單。</li><li>從清單中選取您要使用之區段的核取方塊，然後按一下<b>新增選取的區段</b>。</li><li>在[新增對應]視窗中按一下[儲存]。<b></b> 在Beta版發行期間，您無法變更對應、開始或結束日期。</li><li>繼續瀏覽並新增區段，或按一下<b>完成</b>。</li></ol> ![對應區段](assets/mapSegments.png) |

## 後續步驟

建立並儲存目的地後，您可以在Analytics中處理該資料。 不過，可能需要數小時的時間，資料才會顯示在您選取的報表套裝中。 檢視[在Analytics中使用對象資料](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html)。
