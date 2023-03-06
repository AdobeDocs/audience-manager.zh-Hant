---
description: Audience Analytics 可讓您傳送 Audience Manager 區段至 Analytics。若要使用此功能，您可以在 Audience Manager 中建立 Analytics 目的地並將區段對應至該目的地。
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: 設定 Analytics 目的地
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: ef8cca16c8c9478f8558c26bf6f3ae95cd72e7ac
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 5%

---

# 設定 Analytics 目的地

## 要求 {#requirements}

若要設定Analytics目的地，您的Audience Manager使用者必須擁有管理員權限。 請參閱 [建立使用者](/help/using/features/administration/administration-overview.md#create-users) 中。 請注意，有 `CREATE_DESTINATIONS` [通配符權限](/help/using/features/administration/administration-overview.md#wild-card-permissions) 不足以建立Analytics目的地。
如需進一步需求，請參閱 [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html).

## 您的預設Analytics目的地和新的Analytics目的地

| Analytics目的地類型 | 說明 |
|---|---|
| 預設值 | 此預設目的地的名稱為「Adobe Analytics」，您可加以編輯。 已對應的報表套裝ID會顯示在資料夾儲存中，供您Audience Manager特徵和區段使用。 <br>  如果您的帳戶有：Audience Manager會自動建立一個目的地： <br>  <ul><li>符合 [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html) 檔案。</li><li>A [報表套裝](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) 中。</li></ul> |
| 新增 | 若要建立新的Analytics目的地，請前往「對象資料>目的地>建立新目的地」，並遵循以下各節所述的步驟。 |

## Adobe Analytics的Audience Manager區段資格 {#segment-qualifications}

傳送區段資訊至Analytics目的地時，Audience Manager只會傳送訪客符合資格的區段。 如果訪客停止符合區段的資格，此資訊為 _not_ 轉送至Adobe Analytics。

例如，請考量下列區段規則：

* 區段A:特徵1和特徵2
* 區段B:特徵1和非特徵2

在Analytics報表中，即使設定檔已停止符合區段B的資格，該設定檔仍可能顯示為符合這兩個區段的資格。

## 步驟1:提供基本資訊

本節包含啟動Analytics目標建立程式的欄位和選項。 要完成此部分：

1. 按一下 **基本資訊** 來公開控制項。
2. 為目的地命名。 避免縮寫和特殊字元。
3. *（可選）* 說明目的地。 簡潔的說明是定義或提供目的地詳細資訊的有效方式。
4. *（可選）* 在 **平台** 清單，將預設設定保留為 **全部**. 目前，這些選項什麼也做不到。 這些功能旨在支援日後可新增的功能。
5. 在 **類別** 清單，選擇 **Adobe Experience Cloud**.
6. 在 **類型** 清單，選擇 **Adobe Analytics**.
7. 按一下 **儲存** 前往「組態設定」，或按一下 **資料匯出標籤** 將導出控制項應用於目標。

>[!NOTE]
>
>若為Analytics目的地， **自動填充目標映射** 核取方塊和 **區段ID** 選項。 您無法變更這些設定。

![基本資訊](assets/basicinformation.png)

## 步驟2:設定資料匯出控制

本節包含適用的選項 [資料匯出控制](/help/using/features/data-export-controls.md) 至Analytics目的地。 如果您不使用資料匯出控制，請略過此步驟。 要完成此部分：

1. 按一下 **資料匯出控制** 來公開控制項。
1. 選取與套用至目的地的資料匯出控制相對應的標籤(請參閱 [將資料匯出標籤新增至目的地](/help/using/features/destinations/add-data-export-labels.md) )。 針對Analytics目的地，預設會選取PII核取方塊。
1. 按一下&#x200B;**「儲存」**。

![exportcontrols](assets/exportControls.png)

## 步驟3:對應報表套裝

「設定」區段會列出已啟用伺服器端轉送的Analytics報表套裝。 如果您有多個Analytics目的地，則指派給這些目的地的報表套裝將會互斥，並由Audience Manager強制執行。 要完成此部分：

1. 按一下 **設定** 來公開控制項。
1. 選取您要傳送區段的目標一（或多個）報表套裝。
1. 按一下&#x200B;**「儲存」**。

![報表套裝](assets/reportSuites.png)

## 步驟4:區段對應

本節提供可讓您自動或手動對應區段的選項。

| 對應選項 | 說明 |
|---|---|
| 自動對應所有目前和未來的區段 | 依預設，此功能會將訪客符合資格的所有區段，以每次點擊為基礎傳送至Analytics。 <br>  如果訪客在單一點擊上屬於超過150個Audience Manager區段，則只會將最近150個合格區段傳送至Analytics，而其餘的清單則會遭截斷。 系統會傳送額外標幟給Analytics，表示區段清單已截斷。 此動作在「對象名稱」維度中顯示為「已達對象上限」，在「對象ID」維度中顯示為「1」。 請參閱 [常見問題集](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) 以取得詳細資訊。 <br>  此外，此選項會影響 [區段產生器](/help/using/features/segments/segment-builder.md). 例如，如果區段自動對應至Analytics目的地，該目的地將無法在 [目的地對應](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) 區段。 Analytics目的地會顯示為灰色，並在目的地瀏覽器的「類型」欄中顯示「Analytics」。 |
| 手動對應區段 | 此選項會顯示搜尋和瀏覽控制項，可讓您選擇要傳送至Analytics的區段。 <br>  若要搜尋區段： <br>  <ol><li>在搜尋欄位中輸入區段名稱或ID。</li><li>按一下 <b>新增。</b></li><li>繼續搜尋和新增區段，或按一下 <b>完成</b>.</li></ol><br>  若要瀏覽區段： <ol><li>按一下 <b>瀏覽所有區段</b>. 這會顯示可用區段的清單。</li><li>從清單中選取您要使用之區段的核取方塊，然後按一下 <b>新增選取的區段</b>.</li><li>按一下 <b>儲存</b> （在「添加映射」窗口中）。 在測試版發行期間，您無法變更對應、開始或結束日期。</li><li>繼續瀏覽和新增區段或按一下 <b>完成</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## 後續步驟

建立並儲存目的地後，您就可以在Analytics中處理該資料。 不過，您可能需要數小時的時間，才能在您選取的報表套裝中取得資料。 請參閱 [在Analytics中使用受眾資料](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
