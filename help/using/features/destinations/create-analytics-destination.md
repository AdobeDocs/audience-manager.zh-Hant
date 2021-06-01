---
description: Audience Analytics 可讓您傳送 Audience Manager 區段至 Analytics。若要使用此功能，您可以在 Audience Manager 中建立 Analytics 目的地並將區段對應至該目的地。
seo-description: Audience Analytics 可讓您傳送 Audience Manager 區段至 Analytics。若要使用此功能，您可以在 Audience Manager 中建立 Analytics 目的地並將區段對應至該目的地。
seo-title: 設定 Analytics 目的地
solution: Audience Manager
title: 設定 Analytics 目的地
feature: Adobe Analytics 整合功能
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 9%

---

# 設定 Analytics 目的地

## 要求 {#requirements}

若要設定Analytics目的地，您的Audience Manager使用者必須擁有管理員權限。 請參閱《管理指南》中的[建立用戶](/help/using/features/administration/administration-overview.md#create-users)。 請注意，擁有`CREATE_DESTINATIONS` [萬用字元權限](/help/using/features/administration/administration-overview.md#wild-card-permissions)並不足以建立Analytics目的地。
如需進一步需求，請參閱[Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html)中的必要條件。

## 您的預設Analytics目的地和新的Analytics目的地

| Analytics目的地類型 | 說明 |
|---|---|
| 預設值 | 此預設目的地的名稱為「Adobe Analytics」，您可加以編輯。 已對應的報表套裝ID會顯示在資料夾儲存中，供您Audience Manager特徵和區段使用。 <br>  如果您的帳戶有：Audience Manager會自動建立一個目的地：  <br>  <ul><li>符合[Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html)檔案中所述的要求。</li><li>Analytics中的[報表套裝](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)。</li><li>[將報表套裝對應至組織](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)。</li></ul> |
| 新增 | 若要建立新的Analytics目的地，請前往「對象資料>目的地>建立新目的地」，並遵循以下各節所述的步驟。 |

## 步驟1:提供基本資訊

本節包含啟動Analytics目標建立程式的欄位和選項。 要完成此部分：

1. 按一下&#x200B;**基本資訊**&#x200B;以公開控制項。
2. 為目的地命名。 避免縮寫和特殊字元。
3. *（選用）* 說明目的地。簡潔的說明是定義或提供目的地詳細資訊的有效方式。
4. *（選用）* 在「平 **** 台」清單中，將預設值設 **為「全部」**。目前，這些選項什麼也做不到。 這些功能旨在支援日後可新增的功能。
5. 在&#x200B;**類別**&#x200B;清單中，選擇&#x200B;**Adobe Experience Cloud**。
6. 在&#x200B;**Type**&#x200B;清單中，選擇&#x200B;**Adobe Analytics**。
7. 按一下&#x200B;**Save**&#x200B;以轉至「配置」設定，或按一下&#x200B;**Data Export Labels**&#x200B;以將導出控制項應用到目標。

>[!NOTE]
>
>對於Analytics目的地，預設會選取&#x200B;**自動填入目的地對應**&#x200B;核取方塊和&#x200B;**區段ID**&#x200B;選項。 您無法變更這些設定。

![基本資訊](assets/basicinformation.png)

## 步驟2:設定資料匯出控制

本節包含將[資料匯出控制項](/help/using/features/data-export-controls.md)套用至Analytics目的地的選項。 如果您不使用資料匯出控制，請略過此步驟。 要完成此部分：

1. 按一下&#x200B;**資料匯出控制項**&#x200B;以公開控制項。
1. 選取與套用至目的地的資料匯出控制相對應的標籤（請參閱[將資料匯出標籤新增至目的地](/help/using/features/destinations/add-data-export-labels.md)）。 針對Analytics目的地，預設會選取PII核取方塊。
1. 按一下&#x200B;**「儲存」**。

![exportcontrols](assets/exportControls.png)

## 步驟3:對應報表套裝

「設定」區段會列出已啟用伺服器端轉送的Analytics報表套裝。 如果您有多個Analytics目的地，則指派給這些目的地的報表套裝將會互斥，並由Audience Manager強制執行。 要完成此部分：

1. 按一下&#x200B;**Configuration**&#x200B;以公開控制項。
1. 選取您要傳送區段的目標一（或多個）報表套裝。
1. 按一下&#x200B;**「儲存」**。

![報表套裝](assets/reportSuites.png)

## 步驟4:區段對應

本節提供可讓您自動或手動對應區段的選項。

| 對應選項 | 說明 |
|---|---|
| 自動對應所有目前和未來的區段 | 依預設，此功能會將訪客符合資格的所有區段，以每次點擊為基礎傳送至Analytics。 <br>  如果訪客在單一點擊上屬於超過150個Audience Manager區段，則只會將最近150個合格區段傳送至Analytics，而其餘的清單則會遭截斷。系統會傳送額外標幟給Analytics，表示區段清單已截斷。 此動作在「對象名稱」維度中顯示為「已達對象上限」，在「對象ID」維度中顯示為「1」。 如需詳細資訊，請參閱[常見問題集](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html)。 <br>  此外，此選項也會影響區段產生器中的目 [的地可用性](/help/using/features/segments/segment-builder.md)。例如，如果區段自動對應至Analytics目的地，該目的地無法在區段產生器的[目的地對應](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations)區段中供選取。 Analytics目的地會顯示為灰色，並在目的地瀏覽器的「類型」欄中顯示「Analytics」。 |
| 手動對應區段 | 此選項會顯示搜尋和瀏覽控制項，可讓您選擇要傳送至Analytics的區段。 <br>  若要搜尋區段：  <br>  <ol><li>在搜尋欄位中輸入區段名稱或ID。</li><li>按一下「<b>添加」。</b></li><li>繼續搜尋和新增區段，或按一下<b>Done</b>。</li></ol><br>  若要瀏覽區段： <ol><li>按一下「<b>瀏覽所有區段</b>」。 這會顯示可用區段的清單。</li><li>從清單中，選取您要使用之區段的核取方塊，然後按一下「新增選取的區段<b>」。</b></li><li>在「添加映射」窗口中，按一下「<b>保存</b>」。 在測試版發行期間，您無法變更對應、開始或結束日期。</li><li>繼續瀏覽並新增區段，或按一下<b>Done</b>。</li></ol> ![mapsegments](assets/mapSegments.png) |

## 後續步驟

建立並儲存目的地後，您就可以在Analytics中處理該資料。 不過，您可能需要數小時的時間，才能在您選取的報表套裝中取得資料。 請參閱[在Analytics中使用對象資料](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html)。
