---
description: 「資料匯出控制」可防止您在此動作違反資料隱私或資料使用合約時傳送資料至目的地。
seo-description: 「資料匯出控制」可防止您在此動作違反資料隱私或資料使用合約時傳送資料至目的地。
seo-title: 資料匯出控制
solution: Audience Manager
title: 資料匯出控制
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 1%

---


# 資料匯出控制 {#data-export-controls}

[!UICONTROL Data Export Controls] 防止您在此動作違反資料隱私或資料使用合約時傳送資料至目的地。

## 概述 {#overview}

[!UICONTROL Data Export Controls] 可讓您分類 [資料來源](../features/datasources-list-and-settings.md#data-sources-list-and-settings)[和目標](../features/destinations/destinations.md)。 您套用的分類會決定資料何時可匯出至目的地。 此功能包括：

* **[!UICONTROL Data Export Controls]**: 您可以在資料來源上設定「資料匯 *出控制」*。 當在資料來源上設定時，這些控制項會限制資料來源及其特性的使用方式。
* **[!UICONTROL Data Export Labels]**: 您可以在目標上設定「資料匯出 *標籤」*。 在目標上設定時，這些標籤會識別目標使用資料的方式。 請參 [閱新增資料匯出標籤至目標](/help/using/features/destinations/add-data-export-labels.md) ，瞭解如何新增匯出標籤至目標。

根據套用至資料來源和目的地的分類，匯出控制項會讓您無法：

* 當特徵屬於資料來源時，新增特徵至區段，其資料匯出控制項與區段所對應之一或多個目的地上的資料匯出標籤不相容。
例如，假設區段已對應至具有匯出標籤的目標 **[!DNL This destination may enable a combination with personally identifiable information (PII)]**。 如果特徵所屬的資料來源具有顯示的資料匯出控制項，則匯出控制項會阻止您新增特徵至該區段 **[!DNL Cannot be tied to personally identifiable information (PII)]**。
* 將任何資料發送到目標目標目標具有資料導出標籤，該標籤被以下任一目標的資料導出控制所阻止：
   * 內含特徵的資料來源；
   * 包含區段中使用之特徵的資料來源；
   * 包含的區段採用的描述檔合併規則；
   * 內含區段的描述檔合併規則所使用的任何資料來源。

[!UICONTROL Data Export Controls] 會自動提供給所有Audience Manager客戶。 不過，您需要管理員權限才能將匯出控制項新增至資料來源。 將導出標籤添加到目標需要管理員 *權限* ，或者需要足夠的權限才能建立或編輯目標。

## 已定義的控制項和標籤 {#controls-labels}

[!UICONTROL Data Export Controls] 提供下列控制項以協助您分類資料來源和目標。

若要封鎖資料傳送，您必須使用匯出控制項來分類資料來源，並新增匯出標籤至目標。 如果您僅將匯出控制套用至資料來源或目標，此功能將不會限制資料傳送。 在資料來源和目標上 *設定* ，匯出控制項將限制您可新增至區段的特性，並防止區段成員傳送至目標。

此外，在資料傳送限制生效之前，至少必須有一個匯出標籤符合匯出控制。 例如，假設您將匯出控 [!UICONTROL PII] 制項新增至資料來源。 接著，您將網站定位標籤新增至目標。 在這種情況下，匯出控制項不會限制資料傳送，因為設定不符。 不過，如果您將匯出標 [!UICONTROL PII] 簽新增至目標，匯出控制項將會封鎖匯出。

>[!IMPORTANT]
>
>您無法將資料匯出控制項置於區段的資料來源上，以封鎖區段的匯出，您必須在下列其中一項上設定控制項：
> * 區段中使用特徵的資料來源；
> * 區段採用的描述檔合併規則；
> * 區段的描述檔合併規則所使用的任何資料來源。


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 資料來源的資料匯出控制 </th> 
   <th colname="col2" class="entry"> 目標的資料導出標籤 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無限制</span></b> </td> 
   <td colname="col2"> 不適用 </td> 
   <td colname="col3"> 依預設，不會針對新資料來源和目標設定匯出限制。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法系結至個人識別資訊</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目標可能會結合個人識別資訊(PII)</span></b> </td> 
   <td colname="col3">選取此選項時，您無法： 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">新增特徵至映射至使用PII之目的地的區段。 </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">將以特徵從資料來源建立的區段對應至使用PII的目的地。 </li> 
    </ul> <p>當使用包含廣告／媒體追蹤資訊的資料來源時，第三方資料提供者通常會要求這麼做。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於站上廣告定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目標可用於現場廣告定位</span></b> </td> 
   <td colname="col3">選取此選項時，您無法： 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">新增特徵至對應至目標的區段，以根據訪客的網頁瀏覽記錄自訂廣告傳遞。 </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">將以資料來源的特徵建立的區段對應至根據訪客網頁瀏覽記錄自訂廣告傳遞的目標。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於離站廣告定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目標可用於離站廣告定位</span></b> </td> 
   <td colname="col3">這些限制通常與「選取時，您無法： 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">新增特徵至映射至目標的區段，以重新定位其他網站上的使用者。 </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">將以資料來源的特徵建立的區段對應至重新定位其他網站上使用者的目標。 </li> 
    </ul> <p>使用社交媒體平台的資料時，通常需要使用此功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於臨場感個人化</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目的地可用於臨場廣告個人化</span></b> </td> 
   <td colname="col3">選取此選項時，您無法： 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">新增特徵至對應至目標的區段，以根據使用者興趣或網頁瀏覽記錄自訂內容。 </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">將以資料來源的特徵建立的區段對應至根據使用者興趣或網頁瀏覽記錄自訂內容的目標。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 工作流程 {#workflow}

若要開始，請檢閱資料來源和目標檔案。 這些文章提供如何新增匯出控制項和標籤至資料來源和目的地的指示。

* [建立資料來源](../features/manage-datasources.md#create-data-source)
* [將資料匯出標籤新增至目標](../features/destinations/add-data-export-labels.md)