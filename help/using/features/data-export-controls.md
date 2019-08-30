---
description: 當此動作違反資料隱私權或資料使用合約時，「資料進出控制」可防止您將資料傳送至目的地。
seo-description: 當此動作違反資料隱私權或資料使用合約時，「資料進出控制」可防止您將資料傳送至目的地。
seo-title: 資料匯出控制
solution: Audience Manager
title: 資料匯出控制
uuid: de7f3608-c0 cb-4049-973a-8be5425 c600
translation-type: tm+mt
source-git-commit: 22657113512e136296be5c4bcb8e092e65f45c06

---


# 資料匯出控制 {#data-export-controls}

[!UICONTROL Data Export Controls] 防止您在此動作違反資料隱私或資料使用合約時傳送資料至目的地。

## 概述 {#overview}

[!UICONTROL Data Export Controls] 可讓您分類 [資料來源](../features/datasources-list-and-settings.md#data-sources-list-and-settings) 和 [目的地](../features/destinations/destinations.md)。您套用的分類會決定資料可以或無法匯出至目的地。此功能包含：

* **[!UICONTROL Data Export Controls]**：您可以設定 *資料來源*&#x200B;的資料匯出控制。在資料來源上設定時，這些控制項會限制資料來源及其特徵的使用方式。
* **[!UICONTROL Data Export Labels]**：您可以在 *目的地設定資料匯出標籤*。在目的地上設定時，這些標籤會識別目的地如何使用資料。請參閱 [「新增資料匯出標籤至目的地](/help/using/features/destinations/add-data-export-labels.md) 」，瞭解如何新增匯出標籤至目的地。

根據套用至資料來源和目的地的分類，匯出控制項會阻止您：

* 在特徵屬於資料來源時新增特徵至資料來源，其資料來源具有與將區段映射至一或多個目的地上的資料匯出標籤不相容的資料匯出控制。
例如，假設區段已對應至具有匯出標籤 **[!DNL This destination may enable a combination with personally identifiable information (PII)]**&#x200B;的目的地。匯出控制項可防止您將特徵新增至該區段，如果特徵所屬的資料來源具有表示資料的控制項 **[!DNL Cannot be tied to personally identifiable information (PII)]**。
* 傳送任何資料至目的地目的地時，會有資料匯出標籤，因為資料匯出控制會封鎖下列任何項目：
   * 隨附特徵的資料來源；
   * 用於包含區段之特徵的資料來源；
   * 由包含區段運用的描述檔合併規則；
   * 包含區段設定檔合併規則使用之任何資料來源。

[!UICONTROL Data Export Controls] 可自動供所有Audience Manager客戶使用。不過，您需要管理員權限來新增匯出控制項至資料來源。將匯出標籤新增至目的地需要管理員權限 *或* 足夠權限來建立或編輯目的地。

## 定義的控制項和標籤 {#controls-labels}

[!UICONTROL Data Export Controls] 提供下列控制項以協助您分類資料來源和目的地。

若要封鎖資料傳送，您必須將資料來源分類為匯出控制，並將匯出標籤新增至目的地。如果您僅將控制項套用至資料來源或目的地，此功能將不會限制資料傳送。在資料來源 *和* 目的地上設定時，匯出控制項將限制您新增至區段的特性，並防止將區段成員傳送至目的地。

此外，至少一個匯出標籤必須符合匯出控制項，資料傳送限制才會生效。例如，假設您將 [!UICONTROL PII] 匯出控制新增至資料來源。接著，您將站上定位標籤新增至目的地。在這種情況下，匯出控制項不會限制資料傳送，因為設定不符合。不過，如果您將 [!UICONTROL PII] 匯出標籤新增至目的地，匯出控制項將封鎖匯出。

>[!IMPORTANT]
>
>您無法在區段的資料來源上放置資料匯出控制來封鎖區段匯出，您必須對其中一個項目設定控制項：
> * 區段中使用之特徵的資料來源；
> * 區段運用的描述檔合併規則；
> * 區段設定檔合併規則使用之任何資料來源。


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
   <td colname="col3"> 根據預設，不會在新的資料來源和目的地上設定限制。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法系結至個人識別資訊</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目的地可結合個人識別資訊(PII)</span></b> </td> 
   <td colname="col3">選取時，您無法： 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">新增特徵至對應至使用PII之目的地的區段。 </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">將使用特徵從資料來源建立的區段對應至使用PII的目標。 </li> 
    </ul> <p>第三方資料供應商以及使用包含廣告/媒體追蹤資訊的資料來源時，通常需要這項功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於臨場感廣告鎖定</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目的地可用於臨場感廣告定位</span></b> </td> 
   <td colname="col3">選取時，您無法： 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">將特性新增至對應至根據訪客網頁瀏覽歷史記錄自訂廣告傳遞的目標群體。 </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">將使用特徵建立的區段對應至依據訪客網頁瀏覽歷史自訂廣告傳遞的目標。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於離線廣告鎖定</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目的地可用於離線廣告鎖定</span></b> </td> 
   <td colname="col3">一般使用這些限制時，您無法： 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">將特性新增至映射至目的地的群體，以便重新定位其他網站上的使用者。 </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">將使用特徵從資料來源建立的區段對應至目標，以便重新定位其他網站上的使用者。 </li> 
    </ul> <p>通常需要使用社交媒體平台的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於臨場感個人化</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目的地可用於臨場感廣告個人化</span></b> </td> 
   <td colname="col3">選取時，您無法： 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">將特性新增至對應至根據使用者興趣或網頁瀏覽記錄自訂內容的目標群體。 </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">將使用特徵建立的區段對應至依據使用者興趣或網頁瀏覽記錄自訂內容的目標。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 工作流程 {#workflow}

若要開始，請檢閱資料來源和目的地文件。這些文章提供如何新增匯出控制和標籤至您的資料來源和目的地的指示。

* [建立資料來源](../features/manage-datasources.md#create-data-source)
* [將資料匯出標籤新增至目的地](../features/destinations/add-data-export-labels.md)