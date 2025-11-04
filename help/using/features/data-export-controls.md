---
description: 當此動作違反資料隱私權或資料使用協定時，資料匯出控制無法將資料傳送到目的地。
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: 資料匯出控制
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# 資料匯出控制 {#data-export-controls}

當此動作違反資料隱私權或資料使用合約時，[!UICONTROL Data Export Controls]會阻止您傳送資料至目的地。

## 概述 {#overview}

[!UICONTROL Data Export Controls]可讓您分類[資料來源](../features/datasources-list-and-settings.md#data-sources-list-and-settings)和[目的地](../features/destinations/destinations.md)。 您套用的分類會決定資料何時可以或無法匯出至目的地。 此功能包含：

* **[!UICONTROL Data Export Controls]**：您可以在&#x200B;*資料來源*&#x200B;上設定資料匯出控制。 在資料來源上設定時，這些控制項會限制該資料來源及其特徵的使用方式。
* **[!UICONTROL Data Export Labels]**：您可以在&#x200B;*目的地*&#x200B;上設定資料匯出標籤。 在目的地上設定時，這些標籤會識別目的地如何使用資料。 請參閱[將資料匯出標籤新增至目的地](/help/using/features/destinations/add-data-export-labels.md)，瞭解如何將匯出標籤新增至目的地。

根據套用至資料來源和目的地的分類，匯出控制項會禁止您：

* 當特徵屬於具有資料匯出控制項的資料來源，而該資料匯出控制項與區段對應至的一或多個目的地上的資料匯出標籤不相容時，將特徵新增至區段。
例如，假設區段對應至匯出標籤為&#x200B;**[!DNL This destination may enable a combination with personally identifiable information (PII)]**&#x200B;的目的地。 如果特徵所屬的資料來源具有顯示&#x200B;**[!DNL Cannot be tied to personally identifiable information (PII)]**&#x200B;的資料匯出控制項，匯出控制項會阻止您將特徵新增至該區段。
* 將任何資料傳送至目的地，該目的地具有資料匯出標籤，且被任何下列位置的資料匯出控制項封鎖：
   * 所包含特徵的資料來源；
   * 用於所包含區段中的特徵資料來源；
   * 包含的區段所利用的設定檔合併規則；
   * 所包含區段的設定檔合併規則所使用的任何資料來源。

[!UICONTROL Data Export Controls]可自動供所有Audience Manager客戶使用。 不過，您需要管理員許可權，才能將匯出控制項新增至資料來源。 將匯出標籤新增至目的地需要系統管理員許可權&#x200B;*或*&#x200B;足夠的許可權才能建立或編輯目的地。

## 已定義的控制項和標籤 {#controls-labels}

[!UICONTROL Data Export Controls]提供下列控制項，協助您分類資料來源和目的地。

若要封鎖資料傳送，您必須使用匯出控制將資料來源分類，並將匯出標籤新增至目的地。 如果您只套用匯出控制項至資料來源或目的地，此功能不會限制資料傳送。 在資料來源&#x200B;*和*&#x200B;目的地上設定時，匯出控制項會限制您可以新增到區段的特徵，並防止將區段成員傳送到目的地。

此外，在資料傳送限制生效之前，必須至少有一個匯出標籤符合匯出控制。 例如，假設您將[!UICONTROL PII]匯出控制項新增至資料來源。 接著，將站上目標定位標籤新增至目的地。 在此情況下，匯出控制項將不會限制資料傳送，因為設定不符。 不過，如果您將[!UICONTROL PII]匯出標籤新增至目的地，匯出控制項將會封鎖匯出。

>[!IMPORTANT]
>
>您不能藉由將資料匯出控制項置於區段的資料來源上來封鎖區段的匯出，您必須在下列任一專案上設定控制項：
>
> * 用於區段之特徵的資料來源；
> * 該區段利用的設定檔合併規則；
> * 區段的設定檔合併規則使用的任何資料來源。

<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data Source的資料匯出控制 </th> 
   <th colname="col2" class="entry"> 目的地的資料匯出標籤 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">沒有限制</span></b> </td> 
   <td colname="col2"> 不適用 </td> 
   <td colname="col3"> 依預設，系統不會為新資料來源和目的地設定匯出限制。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">無法繫結至個人識別資訊</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol">此目的地可能會啟用與個人識別資訊(PII)的組合</span></b> </td> 
   <td colname="col3">選取後，您無法： 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">將特徵新增至對應至使用PII之目的地的區段。 </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">將使用特徵建立的區段從資料來源對應至使用PII的目的地。 </li> 
    </ul> <p>協力廠商資料提供者及使用包含廣告/媒體追蹤資訊的資料來源時，通常需要用到這項功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">無法用於網站上的廣告目標定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol">此目的地可用於站上廣告目標定位</span></b> </td> 
   <td colname="col3">選取後，您無法： 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">將特徵新增至對應至目的地的區段，這些區段會根據訪客的網頁瀏覽歷史記錄自訂廣告傳遞。 </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">使用特徵建立的區段，從資料來源對應至根據訪客的網頁瀏覽歷史記錄自訂廣告傳送的目的地。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">無法用於站外廣告目標定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol">此目的地可用於站外廣告目標定位</span></b> </td> 
   <td colname="col3">選取後，您無法： 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">將特徵新增至對應至目的地的區段，藉此重新鎖定其他網站上的使用者。 </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">將使用特徵建立的區段，從資料來源對應至將使用者重新鎖定在其他網站上的目的地。 </li> 
    </ul> <p>使用社群媒體平台的資料時通常需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">無法用於網站上的個人化</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol">此目的地可用於站上廣告個人化</span></b> </td> 
   <td colname="col3">選取後，您無法： 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">將特徵新增至對應至目的地的區段，這些區段會根據使用者興趣或網頁瀏覽歷史記錄來自訂內容。 </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">使用特徵建立的區段從資料來源對應至目的地，該目的地會根據使用者興趣或網頁瀏覽記錄來自訂內容。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 工作流程 {#workflow}

若要開始使用，請檢閱資料來源和目的地檔案。 這些文章提供如何新增匯出控制項和標籤至您的資料來源和目的地的指示。

* [建立資料來源](../features/manage-datasources.md#create-data-source)
* [將資料匯出標籤新增至目的地](../features/destinations/add-data-export-labels.md)
