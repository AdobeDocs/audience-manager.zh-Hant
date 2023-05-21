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

要配置分析目標，您的Audience Manager用戶必須具有管理權限。 請參閱 [建立用戶](/help/using/features/administration/administration-overview.md#create-users) 的上界。 請注意， `CREATE_DESTINATIONS` [通配符權限](/help/using/features/administration/administration-overview.md#wild-card-permissions) 不足以建立分析目標。
有關進一步要求，請參閱中的「必備元件」 [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html)。

## 預設分析目標和新分析目標

| 分析目標類型 | 說明 |
|---|---|
| 預設值 | 此預設目標的名稱為「Adobe Analytics」，您可以編輯該名稱。 映射的報告套件ID將顯示在資料夾儲存中，用於Audience Manager特徵和段。 <br>  Audience Manager如果帳戶具有以下條件，則自動建立一個目標： <br>  <ul><li>滿足中描述的要求 [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html) 文檔。</li><li>A [報告套件](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) 分析。</li></ul> |
| 新增 | 要建立新的分析目標，請轉至「受眾資料」>「目標」>「建立新目標」，並按照下面介紹的每個部分的步驟進行操作。 |

## Audience ManagerAdobe Analytics分部資格 {#segment-qualifications}

在將段資訊發送到分析目標時，Audience Manager只發送訪問者有資格獲取的段。 如果訪問者停止符合段的條件，則此資訊 _不_ 轉給Adobe Analytics。

例如，請考慮以下段規則：

* 段A:性狀1和性狀2
* B類：性狀1和非性狀2

在分析報告中，配置檔案可能顯示為兩個段的合格配置檔案，即使它停止了對段B的合格配置。

## 步驟1:提供基本資訊

此部分包含啟動分析目標建立過程的欄位和選項。 要完成本節：

1. 按一下 **基本資訊** 來揭示控制項。
2. 命名目標。 避免縮寫和特殊字元。
3. *（可選）* 描述目標。 簡潔的描述是定義或提供有關目標的詳細資訊的有效方法。
4. *（可選）* 在 **平台** 清單，將預設設定為 **全部**。 目前，這些選項沒有任何作用。 它們旨在支援以後可能添加的功能。
5. 在 **類別** 清單，選擇 **Adobe Experience Cloud**。
6. 在 **類型** 清單，選擇 **Adobe Analytics**。
7. 按一下 **保存** 轉到「配置」設定或按一下 **資料導出標籤** 將導出控制項應用到目標。

>[!NOTE]
>
>對於分析目標， **自動填充目標映射** 複選框 **段ID** 選項。 不能更改這些設定。

![基礎資訊](assets/basicinformation.png)

## 步驟2:配置資料導出控制項

本節包含適用的選項 [資料導出控制項](/help/using/features/data-export-controls.md) 到分析目標。 如果不使用資料導出控制項，請跳過此步驟。 要完成本節：

1. 按一下 **資料導出控制項** 來揭示控制項。
1. 選擇與應用到目標的資料導出控制項相對應的標籤(請參閱 [將資料導出標籤添加到目標](/help/using/features/destinations/add-data-export-labels.md) )。 對於分析目標，預設情況下會選中PII複選框。
1. 按一下&#x200B;**「儲存」**。

![導出控制項](assets/exportControls.png)

## 第3步：映射報表套件

「配置」部分列出了已啟用伺服器端轉發的分析報告套件。 如果您有多個分析目標，則分配給這些目標的報告套件將相互排斥並通過Audience Manager強制執行。 要完成本節：

1. 按一下 **配置** 來揭示控制項。
1. 選擇要將段發送到的一個（或多個）報表套件。
1. 按一下&#x200B;**「儲存」**。

![報告套房](assets/reportSuites.png)

## 第4步：段映射

本節提供了一些選項，可以自動或手動映射段。

| 映射選項 | 說明 |
|---|---|
| 自動映射所有當前和將來的段 | 預設情況下，此功能將按點擊次數將訪問者有資格訪問的所有段發送到分析。 <br>  如果訪問者在一次點擊中屬於150多個Audience Manager段，則只有150個最近合格的段被發送到分析，而其餘的清單被截斷。 將向分析發送一個附加標誌，表示段清單被截斷。 此操作在「受眾名稱」維中顯示為「已達到受眾限制」，在「受眾ID」維中顯示為「1」。 查看 [常見問題](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) 的雙曲餘切值。 <br>  此外，此選項還會影響 [段生成器](/help/using/features/segments/segment-builder.md)。 例如，如果段自動映射到分析目標，則該目標在 [目標映射](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) 的子菜單。 分析目標顯示為灰色，並在目標瀏覽器的「類型」列中顯示「分析」。 |
| 手動映射段 | 此選項顯示搜索和瀏覽控制項，允許您選擇要發送到分析的段。 <br>  要搜索段： <br>  <ol><li>在搜索欄位中鍵入段名稱或ID。</li><li>按一下 <b>添加。</b></li><li>繼續搜索和添加段，或按一下 <b>完成</b>。</li></ol><br>  瀏覽段： <ol><li>按一下 <b>瀏覽所有段</b>。 這將顯示可用段的清單。</li><li>從清單中，選中要使用的段的複選框，然後按一下 <b>添加選定段</b>。</li><li>按一下 <b>保存</b> 中。 在測試版發行期間，不能更改映射、開始或結束日期。</li><li>繼續瀏覽和添加段，或按一下 <b>完成</b>。</li></ol> ![映射段](assets/mapSegments.png) |

## 後續步驟

建立和保存目標後，可以在分析中使用該資料。 但是，在所選報告套件中提供資料可能需要幾個小時。 請參閱 [在分析中使用受眾資料](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html)。
