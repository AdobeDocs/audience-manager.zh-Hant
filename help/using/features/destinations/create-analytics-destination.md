---
description: Audience Analytics 可讓您傳送 Audience Manager 區段至 Analytics。若要使用此功能，您可以在 Audience Manager 中建立 Analytics 目的地並將區段對應至該目的地。
seo-description: Audience Analytics 可讓您傳送 Audience Manager 區段至 Analytics。若要使用此功能，您可以在 Audience Manager 中建立 Analytics 目的地並將區段對應至該目的地。
seo-title: 設定Analytics目的地
solution: Audience Manager
title: 設定Analytics目的地
translation-type: tm+mt
source-git-commit: 3179b9007e102f7031cc4cc9e0da64f77cfa3eeb

---


# 設定Analytics目的地

## 要求 {#requirements}

See [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## 您的預設Analytics目標和新Analytics目標

| Analytics目標類型 | 說明 |
|---|---|
| 預設值 | 此預設目的地的名稱為您可編輯的「Adobe Analytics」。對應的報表套裝ID會顯示在您的Audience Manager特徵和區段的檔案夾儲存中。<br>如果您的帳戶有下列項目，Audience Manager會自動建立一個目的地： <br> <ul><li>Met the requirements described in the [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) documentation.</li><li>A [report suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[將報表套裝對應至組織](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)。</li></ul> |
| 新增 | 若要建立新的Analytics目的地，請前往「對象資料&gt;目標&gt;建立新目的地」，並遵循以下每個章節的步驟。 |

## 步驟1：提供基本資訊

本節包含開始Analytics目的地建立程序的欄位和選項。若要完成本節：

1. Click **Basic Information** to expose the controls.
2. 命名目的地。避免縮寫和特殊字元。
3. *(選擇性)* 說明目的地。簡明扼要的說明是定義或提供目標的更多資訊。
4. *(可選)* 在 **「平台** 」清單中，將預設設定保留為 **「全部**」。目前，這些選項不會執行任何動作。它們的設計目的是為了支援稍後新增的功能。
5. In the **Category** list, select **Adobe Experience Cloud**.
6. In the **Type** list, select **Adobe Analytics**.
7. Click **Save** to go to the Configuration settings or click **Data Export Labels** to apply export controls to the destination.

>[!NOTE]
>
>For an Analytics destination, the **Auto-fill Destination Mappping** check box and **Segment ID** option are selected by default. 您無法變更這些設定。

![基本資訊](assets/basicinformation.png)

## 步驟2：設定資料匯出控制

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. 如果您不使用資料匯出控制，請跳過此步驟。若要完成本節：

1. Click **Data Export Controls** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) ). 對於Analytics目的地，預設會選取PII核取方塊。
3. 按一下&#x200B;**「儲存」**。

![exportControls](assets/exportControls.png)

## 步驟3：地圖套裝報表

「設定」區段列出已啓用伺服器端轉送功能的Analytics報表套裝。如果您有多個Analytics目的地，指派給這些目的地的報表套裝將由Audience Manager互斥並實施。若要完成本節：

1. Click **Configuration** to expose the controls.
2. 選取要傳送區段的一個(或更多)報表套裝。
3. 按一下&#x200B;**「儲存」**。

![reportsuites](assets/reportSuites.png)

## 步驟4：區段映射

本節提供可讓您自動或手動對應區段的選項。

| 對應選項 | 說明 |
|---|---|
| 自動對應所有目前和未來的區段 | 根據預設，此功能會將訪客符合每個點擊的區段傳送至Analytics。<br>如果訪客在單一點擊上屬於超過150個Audience Manager區段，則只有150個最近符合資格的區段會傳送至Analytics，而剩餘的清單則會被截斷。會將額外標幟傳送至Analytics，表示區段清單被截斷。此動作會顯示為「對象名稱」維度中的「對象限制」，以及「對象ID」維度中的「1」。See the [FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) for details. <br>此外，此選項會影響 [「區段產生器](/help/using/features/segments/segment-builder.md)」中的目的地可用性。For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the [destination mappings](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) section of Segment Builder. Analytics目的地顯示灰色，並在目標瀏覽器的「類型」欄中顯示「Analytics」。 |
| 手動對應區段 | 此選項會顯示搜尋和瀏覽控制，可讓您選擇要傳送至Analytics的區段。<br>若要搜尋區段： <br> <ol><li>在搜尋欄位中鍵入區段名稱或ID。</li><li>Click <b>Add.</b></li><li>Continue to search and add segments or click <b>Done</b>.</li></ol><br>瀏覽區段： <ol><li>Click <b>Browse all segments</b>. 這會顯示可用區段的清單。</li><li>From the list, select the check box of the segment you want to use and click <b>Add selected segments</b>.</li><li>Click <b>Save</b> in the Add Mappings window. 在測試版發行期間，您無法變更對應、開始或結束日期。</li><li>Continue to browse and add segments or click <b>Done</b>.</li></ol> |

![mapsegments](assets/mapSegments.png)

## 後續步驟

建立並儲存目的地後，您可以在Analytics中處理該資料。不過，您可能需要幾小時的時間才可在選取的報表套裝中使用資料。See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).



