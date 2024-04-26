---
title: 將您的資料收集程式庫更新，以便從AppMeasurementJavaScript程式庫Audience Manager至Web SDK JavaScript程式庫。
description: 瞭解將資料收集程式庫從AppMeasurementJavaScript程式庫更新為Web SDK JavaScript程式庫以進行Audience Manager的步驟。
source-git-commit: b0c35d79a07b481e332ddf8f4aedab5484416a51
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---


# 將您的資料收集程式庫更新，以便從AppMeasurementJavaScript程式庫Audience Manager至Web SDK JavaScript程式庫

## 目標對象 {#intended-audience}

本頁適用於使用AppMeasurement將網頁集合資料匯入Audience Manager的Audience Manager客戶。 對於使用的客戶 [Audience Manager標籤延伸模組](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview)，請參閱如何更新您的資料收集程式庫以進行Audience Manager的指南 [從Audience Manager標籤擴充功能到Web SDK標籤擴充功能](dil-extension-to-web-sdk.md).

## 此實作路徑的優缺點

使用此移轉方法的優缺點。 請仔細權衡每個選項，決定哪種方式最適合您的組織。

| 優勢 | 缺點 |
| --- | --- |
| <ul><li>**使用您現有的實施**：雖然此方法需要一些實作變更，但不需要從頭開始全新的實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更。</li><li>**不需要結構描述**：針對移轉至Web SDK的這個階段，您不需要XDM結構描述。 反之，您可以填入 `data` 物件，會將資料直接傳送至Audience Manager。 一旦移轉至Web SDK完成，您就可以為貴組織建立結構描述，並使用資料流對應來填入適用的XDM欄位。 如果移轉流程的這個階段需要結構描述，貴組織將被強制使用Audience ManagerXDM結構描述。 使用此結構描述會使您的組織未來更難以使用您自己的結構描述。</li></ul> | <ul><li>**實作技術債務**：由於此方法使用您現有實施的修改形式，日後追蹤實施邏輯及執行變更時，可能會較困難。</li><li>**需要對應才能將資料傳送至Platform**：當貴組織準備好使用Real-Time CDP時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作需要 `data` 物件是資料流對應工具中的專案，可將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li></ul> |

Adobe建議在下列情況下使用此實施路徑：

* 您已有使用Adobe AnalyticsAppMeasurementJavaScript程式庫的現有實作。 如果您有使用Audience Manager標籤擴充功能的實作，請依照 [從Audience Manager標籤擴充功能移轉至Web SDK標籤擴充功能](dil-extension-to-web-sdk.md) 而非。
* 您打算在未來使用Real-Time CDP，但不想從頭開始使用Web SDK實作來取代您的Audience Manager實作。 在Web SDK上從頭開始取代實作需要花費最大心力，但同時也提供最可行的長期實作架構。 如果您的組織願意徹底實施Web SDK，請參閱 [Web SDK檔案](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) 以取得更多詳細資料。

## 移轉至Web SDK所需的步驟

下列步驟包含需努力達成的具體目標。 按一下每個步驟，以取得如何完成的詳細指示。

+++**1. 建立及設定資料串流**

在Adobe Experience Platform Data Collection中建立資料流。 當您傳送資料至此資料流時，它會轉送資料至Audience Manager。 未來，相同的資料流會將資料轉送至Real-Time CDP。

1. 瀏覽至 [experience.adobe.com](https://experience.adobe.com) 並使用您的憑證登入。
1. 使用右上方的首頁或產品選擇器來導覽至 **[!UICONTROL Data Collection]**.
1. 在左側導覽中選取 **[!UICONTROL Datastreams]**.
1. 選取 **[!UICONTROL New Datastream]**.
1. 輸入所要的名稱，然後選取 **[!UICONTROL Save]**.
1. 建立資料流後，選取 **[!UICONTROL Add Service]**.
1. 在服務下拉式功能表中，選取 **[!UICONTROL Audience Manager]**.

   ![新增Audience Manager服務](assets/add-service.png) {style="border:1px solid lightslategray"}

您的資料流現在已準備好接收資料並傳遞給Audience Manager。 請記下資料串流ID，因為此ID在程式碼中設定Web SDK時是必要的。

+++

+++**2.安裝Web SDK JavaScript程式庫**

另請參閱 [使用JavaScript程式庫安裝Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) 以取得詳細資訊和要使用的程式碼區塊。 參考最新版本的 `alloy.js` 因此可以使用其方法呼叫。

+++

+++**3.設定Web SDK**

使用Web SDK將您的實作設定為指向步驟1中建立的資料流 [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) 命令。 此 `configure` 命令必須在每個頁面上設定，因此您可以將其與程式庫安裝程式碼一併納入。

使用 [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) 和 [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) Web SDK中的屬性 `configure` 命令：

* 設定 `edgeConfigId` 與上一步驟中擷取的資料串流ID比對。
* 設定 `orgId` 至您組織的IMS組織ID。

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

您可以選擇在中設定其他屬性 [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) 會根據貴組織的實作需求執行命令。

+++

+++**4.更新程式碼邏輯以使用JSON裝載**

變更您的Audience Manager實作，使其不依賴 `AppMeasurement.js` 或 `s` 物件。 請改為將變數設為格式正確的JavaScript物件，這會在傳送至Adobe時轉換為JSON物件。 擁有 [資料層](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) 在設定值時，您可在您的網站上獲得極大的協助，因為您可以繼續參考這些相同的值。

若要將資料傳送至Audience Manager，Web SDK裝載必須使用 `data.__adobe.audiencemanager` 在此物件中設定所有analytics變數。 此物件中的變數與其AppMeasurement變數的對應變數具有相同的名稱和格式。 例如，如果您設定 `products` 變數，請勿像使用XDM時一樣將其分割為個別物件。 請改為將其加入為字串，準確地說，如果您將 `s.products` 變數：

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

最終，此裝載包含所有所需值，以及 `s` 實作中的物件即會移除。 您可以使用JavaScript提供的任何資源來設定此裝載物件，包括點標籤法來設定個別值。

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5.更新方法呼叫以使用Web SDK**

更新您呼叫的所有執行個體 [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) 和 [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method)，將替換為 [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) 命令。 我們需考慮三種情況：

* **頁面檢視追蹤**：以Web SDK取代頁面檢視追蹤呼叫 `sendEvent` 命令：

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **自動連結追蹤**：此 [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) 設定屬性預設為啟用。 它會自動設定正確的連結追蹤變數，以將資料傳送至Audience Manager。 如果您想要停用自動連結追蹤，請將此屬性設為 `false` 在 [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) 命令。

* **手動連結追蹤**：Web SDK在pageview和非頁面檢視呼叫之間沒有個別的命令。 在裝載物件內提供該區別。

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6.驗證和發佈變更**

移除對AppMeasurement和 `s` 物件，將您的變更發佈至開發環境，以驗證新實施是否有效。 一旦您驗證一切都正常運作，您就可以將更新發佈到生產環境。

若已正確移轉， `AppMeasurement.js` 您的網站上不再需要，可以移除此指令碼的所有參考。

+++

此時，您的Audience Manager實作已完全移轉至Web SDK，並準備好在未來移轉至Real-Time CDP。
