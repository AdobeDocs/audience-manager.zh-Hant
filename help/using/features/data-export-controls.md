---
description: 當動作違反資料隱私權或資料使用合約時，資料匯出控制無法將資料傳送至目的地。
seo-description: 當動作違反資料隱私權或資料使用合約時，資料匯出控制無法將資料傳送至目的地。
seo-title: 資料匯出控制
solution: Audience Manager
title: 資料匯出控制
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: 資料匯出控制
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 2%

---

# 資料匯出控制 {#data-export-controls}

[!UICONTROL Data Export Controls] 當此動作違反資料隱私權或資料使用合約時，防止您將資料傳送至目的地。

## 概述 {#overview}

[!UICONTROL Data Export Controls] 可讓您分類 [資料](../features/datasources-list-and-settings.md#data-sources-list-and-settings) 來源 [和目的地](../features/destinations/destinations.md)。您套用的分類會決定資料何時可匯出或無法匯出至目的地。 此功能包含：

* **[!UICONTROL Data Export Controls]**:您可以對資料來源設定「資料 *匯出控制*」。在資料來源上設定時，這些控制項會限制該資料來源及其特徵的使用方式。
* **[!UICONTROL Data Export Labels]**:您可以在目的地上設定資料匯 *出標籤*。在目的地上設定時，這些標籤會識別目的地使用資料的方式。 請參閱[將資料匯出標籤新增至目標](/help/using/features/destinations/add-data-export-labels.md) ，了解如何將匯出標籤新增至目標。

根據套用至資料來源和目的地的分類，匯出控制會阻止您：

* 當特徵屬於某個資料來源時新增特徵至區段，該資料來源具有與區段所對應之一或多個目的地的資料匯出標籤不相容的資料匯出控制項。
例如，假設區段對應至匯出標籤為**[!DNL This destination may enable a combination with personally identifiable information (PII)]**&#x200B;的目的地。 如果特徵所屬的資料來源有顯示&#x200B;**[!DNL Cannot be tied to personally identifiable information (PII)]**&#x200B;的資料匯出控制項，則匯出控制項會阻止您將特徵新增至該區段。
* 將任何資料發送到目標目的地具有資料導出標籤，該標籤被以下任意一個目的地的資料導出控制項阻止：
   * 包含特徵的資料來源；
   * 包含區段中所用特徵的資料來源；
   * 包含的區段採用的設定檔合併規則；
   * 包含區段的設定檔合併規則所使用的任何資料來源。

[!UICONTROL Data Export Controls] 自動供所有Audience Manager客戶使用。不過，您需要管理員權限，才能將匯出控制項新增至資料來源。 將導出標籤添加到目標需要管理員權限&#x200B;*或*&#x200B;來建立或編輯目標。

## 定義{#controls-labels}的控制項和標籤

[!UICONTROL Data Export Controls] 提供下列控制項，協助您分類資料來源和目的地。

若要封鎖資料傳送，您必須使用匯出控制項來分類資料來源，並新增匯出標籤至目的地。 如果您僅將匯出控制套用至資料來源或目的地，此功能將不會限制資料傳送。 在資料來源&#x200B;*和*&#x200B;目的地上設定時，匯出控制將限制您可新增至區段的特徵，並防止將區段成員傳送至目的地。

此外，在資料傳送限制生效之前，至少必須有一個匯出標籤符合匯出控制。 例如，假設您將[!UICONTROL PII]匯出控制項新增至資料來源。 接下來，您將站上定位標籤新增至目的地。 在此情況下，匯出控制不會限制資料傳送，因為設定不相符。 不過，如果將[!UICONTROL PII]匯出標籤新增至目的地，則匯出控制項會封鎖匯出。

>[!IMPORTANT]
>
>您無法借由將資料匯出控制項放在區段的資料來源來封鎖區段的匯出，您必須在以下任一項上設定控制項：
> * 區段中使用特徵的資料來源；
> * 區段採用的設定檔合併規則；
> * 區段的設定檔合併規則所使用的任何資料來源。


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 資料來源的資料匯出控制 </th> 
   <th colname="col2" class="entry"> 目的地的資料匯出標籤 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無限制</span></b> </td> 
   <td colname="col2"> 不適用 </td> 
   <td colname="col3"> 依預設，新資料來源和目的地不會設定匯出限制。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法與個人識別資訊</span></b> (PII)系結 </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目的地可能會啟用與個人識別資訊(PII)的結合</span></b> </td> 
   <td colname="col3">選取後，您無法： 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">將特徵新增至對應至使用PII之目的地的區段。 </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">將以資料來源的特徵建立的區段對應至使用PII的目的地。 </li> 
    </ul> <p>第三方資料提供者和使用包含廣告/媒體追蹤資訊的資料來源時，通常需要這個選項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於站上廣告定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目的地可用於站上廣告鎖定目標</span></b> </td> 
   <td colname="col3">選取後，您無法： 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">將特徵新增至對應至目的地的區段，這些目的地會根據訪客的網頁瀏覽記錄來自訂廣告傳送。 </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">將以資料來源的特徵建立的區段對應至根據訪客的網頁瀏覽記錄來自訂廣告傳送的目的地。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於離站廣告定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目的地可用於離站廣告鎖定</span></b> </td> 
   <td colname="col3">這些限制通常與「選取時」搭配使用，您不能： 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">將特徵新增至對應至重新鎖定其他網站上使用者之目的地的區段。 </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">將以資料來源的特徵建立的區段對應至將其他網站上的使用者重新鎖定為目標的目的地。 </li> 
    </ul> <p>使用來自社交媒體平台的資料時，通常需要用到。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於站上個人化</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目的地可用於站上廣告個人化</span></b> </td> 
   <td colname="col3">選取後，您無法： 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">將特徵新增至對應至目的地的區段，這些目的地會根據使用者興趣或網頁瀏覽記錄來自訂內容。 </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">將以資料來源的特徵建立的區段對應至根據使用者興趣或網頁瀏覽歷史記錄自訂內容的目的地。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 工作流程 {#workflow}

若要開始使用，請檢閱資料來源和目的地檔案。 這些文章提供如何將匯出控制項和標籤新增至資料來源和目的地的指示。

* [建立資料來源](../features/manage-datasources.md#create-data-source)
* [將資料匯出標籤新增至目的地](../features/destinations/add-data-export-labels.md)
