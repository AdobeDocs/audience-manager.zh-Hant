---
description: 更新您的程式碼以使用d_ cid或d_ cid_ ic而非d_ dpid和d_ dpuuid。DPID和DPUUID變數仍會繼續運作，但您應認為已過時。這包括DPID和DPUUID變體，不含d_ prefix。
seo-description: 更新您的程式碼以使用d_ cid或d_ cid_ ic而非d_ dpid和d_ dpuuid。DPID和DPUUID變數仍會繼續運作，但您應認為已過時。這包括DPID和DPUUID變體，不含d_ prefix。
seo-title: CID取代DPID和DPUUID
solution: Audience Manager
title: CID取代DPID和DPUUID
uuid: 3641eac5-b19 e-45d5-bc1 c-35a23 b4 bab8 c
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# CID Replaces DPID and DPUUID{#cid-replaces-dpid-and-dpuuid}

Update your code to use `d_cid` or `d_cid_ic` instead of `d_dpid` and `d_dpuuid`. DPID和DPUUID變數仍會繼續運作，但您應認為已過時。This includes DPID and DPUUID variants without the `d_ prefix`.

## DPID and DPUUID: A Review {#dpid-dpuuid-review}

DPID和DPUUID是索引鍵值配對，其中包含資料供應商ID和使用者ID。這些金鑰值對會將提供者ID連結至使用者ID。它們會傳送事件呼叫期間的資料、傳入的同步事件，以及ID呼叫。Without them, [!DNL Audience Manager], and other services or features, would not have a way to match and synchronize IDs. These variables are sometimes expressed with or without the `d_` prefix as shown below. Note, in the code, *italics* indicates a variable placeholder.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 語法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>資料供應商ID(DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_ dpid=<i>資料供應商ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>資料供應商ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資料提供者唯一使用者ID(DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_ dpuuid=<i>資料提供者唯一使用者ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>資料提供者唯一使用者ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

這些索引鍵值對仍可運作，但已過時。您應更新程式碼以使用CID或CID_ IC。

## CID and CID_IC: About {#cid-cidic-about}

CID和CID_ IC金鑰-值對取代DPID和DPUUID。它們提供與DPID和DPUUID相同的功能，但較有效率，因為它們包含資料供應商ID(或整合程式碼)和單一索引鍵值配對中的使用者ID。在每個索引鍵值配對中：

* =符號會將索引鍵與其相關值分開。
* 非列印ASCII字元%1會分隔值。

`d_cid` 並 `d_cid_ic` 使用下列語法。Note, in the code, *italics* indicates a variable placeholder.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 語法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>客戶ID(CID) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid=<i>資料供應商ID</i>%01<i>使用者ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客戶ID整合代碼(CID_ IC) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid_ ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> <span class="term"> 整合代碼</span> 是可供使用的替代ID，而非 <span class="keyword"> Audience Manager指派的資料來源ID</span>。See <a href="../features/manage-datasources.md#create-data-source"> Create a Data Source</a> if you need to configure an integration code. </p> </td> 
  </tr> 
 </tbody> 
</table>

See also, [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>You can use integration codes for your own data sources and for global [shared data sources](../features/datasources-list-and-settings.md#settings-menu-options), which you have access to. 例如，您可以使用整合代碼來處理行動識別碼資料來源。請使用下列整合代碼，如下所示：

* **GID_20914** for GGAID，代表執行Android作業系統的裝置。
* **DSID_20915** for IDFA，代表執行iOS作業系統的裝置。

**範例**

下表依事件類型提供範例。

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件類型 </th> 
   <th colname="col2" class="entry"> 範例 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>事件 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">New: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Deprecated: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳入同步(IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">New: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Deprecated: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>產生Audience Manager UUID(ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">New: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Deprecated: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Each call can also include multiple `d_cid` and `d_cid_ic` key value pairs like this:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Important Considerations for Development Teams {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>項目 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>URL編碼 </p> </td> 
   <td colname="col2"> <p>Your development teams <i>must</i> apply URL encoding to the following variables in the CID key-value pair: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> 使用者ID</code><code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> 整合程式碼</code> </li> 
     </ul> </p> <p> <p>Note: You must URL encode the user ID and integration code <i>before</i> concatenating them into a string. 這是因為要分隔兩個變數的ASCII字元%1，不能在URL編碼中擷取。 </p> </p> <p>URL編碼可確保您的使用者ID和包含保留或不安全字元(例如，但不限於)的使用者ID和整合代碼會正確傳輸至我們的伺服器。 </p> <p>Use the <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII encoding table</a> for reference. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用全域共用資料來源的整合代碼 </p> </td> 
   <td colname="col2"> <p>You can use integration codes for your own data sources and for global <a href="../features/datasources-list-and-settings.md#settings-menu-options"> shared data sources</a>, which you have access to. 例如，您可以使用整合代碼來處理行動識別碼資料來源。請使用下列整合代碼，如下所示： </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>GID_20914</b> for GGAID，代表執行Android作業系統的裝置。 </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> for IDFA，代表執行iOS作業系統的裝置。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

