---
description: Audience Analytics 可讓您傳送 Audience Manager 區段至 Analytics。若要使用此功能，您可以在 Audience Manager 中建立 Analytics 目的地並將區段對應至該目的地。
seo-description: Audience Analytics 可讓您傳送 Audience Manager 區段至 Analytics。若要使用此功能，您可以在 Audience Manager 中建立 Analytics 目的地並將區段對應至該目的地。
seo-title: 設定Analytics目的地
solution: Audience Manager
title: 設定Analytics目的地
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# 設定Analytics目的地

## 要求 {#requirements}

請參閱 [觀眾分析](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/)。

## 您的預設Analytics目標和新Analytics目標

| Analytics目標類型 | 說明 |
|---|---|
| 預設值 | 此預設目的地的名稱為您可編輯的「Adobe Analytics」。對應的報表套裝ID會顯示在您的Audience Manager特徵和區段的檔案夾儲存中。<br>如果您的帳戶有下列項目，Audience Manager會自動建立一個目的地： <br> <ul><li>符合 [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) 文件中所述的需求。</li><li>Analytics中的 [報表套裝](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) 。</li><li>[將報表套裝對應至組織](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)。</li></ul> |
| 新增 | 若要建立新的Analytics目的地，請前往「對象資料&gt;目標&gt;建立新目的地」，並遵循以下每個章節的步驟。 |

## 步驟1：提供基本資訊

本節包含開始Analytics目的地建立程序的欄位和選項。若要完成本節：

1. 按一下 **「基本資訊** 」以公開控制項。
1. 命名目的地。避免縮寫和特殊字元。
1. *(選擇性)* 說明目的地。簡明扼要的說明是定義或提供目標的更多資訊。
1. *(可選)* 在 **「平台** 」清單中，將預設設定保留為 **「全部**」。目前，這些選項不會執行任何動作。它們的設計目的是為了支援稍後新增的功能。
1. 在 **「類別** 」清單中，選取 **Adobe Experience Cloud**。
1. 在 **「類型** 」清單中，選取 **Adobe Analytics**。
1. 按一下 **「儲存** 」，前往「設定」設定，或按一下 **「資料匯出標籤** 」以套用控制項至目的地。

>[!NOTE]
>
>對於Analytics目標，預設會選取 **「自動填寫目標剪裁** 」核取方塊和 **「區段ID** 」選項。您無法變更這些設定。

![基本資訊](assets/basicinformation.png)

## 步驟2：設定資料匯出控制

本節包含將 [「資料匯出控制」](/help/using/features/data-export-controls.md) 套用至Analytics目的地的選項。如果您不使用資料匯出控制，請跳過此步驟。若要完成本節：

1. 按一下 **「資料匯出控制** 」以公開控制項。
1. 選取對應至目的地之資料匯出控制的標籤(請參閱 [「新增資料匯出標籤至目的地](/help/using/features/destinations/add-data-export-labels.md) 」)。對於Analytics目的地，預設會選取PII核取方塊。
1. 按一下&#x200B;**「儲存」**。

![exportControls](assets/exportControls.png)

## 步驟3：地圖套裝報表

「設定」區段列出已啓用伺服器端轉送功能的Analytics報表套裝。如果您有多個Analytics目的地，指派給這些目的地的報表套裝將由Audience Manager互斥並實施。若要完成本節：

1. 按一下 **「設定** 」以公開控制項。
1. 選取要傳送區段的一個(或更多)報表套裝。
1. 按一下&#x200B;**「儲存」**。

![reportsuites](assets/reportSuites.png)

## 步驟4：區段映射

本節提供可讓您自動或手動對應區段的選項。

| 對應選項 | 說明 |
|---|---|
| 自動對應所有目前和未來的區段 | 根據預設，此功能會將訪客符合每個點擊的區段傳送至Analytics。<br>如果訪客在單一點擊上屬於超過150個Audience Manager區段，則只有150個最近符合資格的區段會傳送至Analytics，而剩餘的清單則會被截斷。會將額外標幟傳送至Analytics，表示區段清單被截斷。此動作會顯示為「對象名稱」維度中的「對象限制」，以及「對象ID」維度中的「1」。如需詳細資訊，請參閱 [常見問答](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) 集。<br>此外，此選項會影響 [「區段產生器](/help/using/features/segments/segment-builder.md)」中的目的地可用性。例如，如果區段自動映射至Analytics目的地，則無法在區段產生器的 [目的地對應](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) 區段中選取該目的地。Analytics目的地顯示灰色，並在目標瀏覽器的「類型」欄中顯示「Analytics」。 |
| 手動對應區段 | 此選項會顯示搜尋和瀏覽控制，可讓您選擇要傳送至Analytics的區段。<br>若要搜尋區段： <br> <ol><li>在搜尋欄位中鍵入區段名稱或ID。</li><li>Click <b>Add.</b></li><li>繼續搜尋並新增區段，或按一下 <b>「完成」</b>。</li></ol><br>瀏覽區段： <ol><li>按一下 <b>「瀏覽所有區段</b>」。這會顯示可用區段的清單。</li><li>從清單中選取您要使用之區段的核取方塊，然後按一下 <b>「新增選取的區段</b>」。</li><li>按一下 <b>「新增對應」視窗中的「儲存</b> 」。在測試版發行期間，您無法變更對應、開始或結束日期。</li><li>繼續瀏覽並新增區段，或按一下 <b>「完成」</b>。</li></ol> ![mapsegments](assets/mapSegments.png) |

## 後續步驟

建立並儲存目的地後，您可以在Analytics中處理該資料。不過，您可能需要幾小時的時間才可在選取的報表套裝中使用資料。See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).
