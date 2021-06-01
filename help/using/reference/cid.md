---
description: 更新您的程式碼以使用d_cid或d_cid_ic，而非d_dpid和d_dpuuid。 DPID和DPUUID變數仍可繼續運作，但您應將其視為已過時。 這包括不含d_首碼的DPID和DPUUID變體。
seo-description: 更新您的程式碼以使用d_cid或d_cid_ic，而非d_dpid和d_dpuuid。 DPID和DPUUID變數仍可繼續運作，但您應將其視為已過時。 這包括不含d_首碼的DPID和DPUUID變體。
seo-title: CID 取代 DPID 及 DPUUID
solution: Audience Manager
title: CID 取代 DPID 及 DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: 參考
exl-id: 18e6b1db-fe51-4560-9458-8d65474d2506
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 4%

---

# CID 取代 DPID 及 DPUUID{#cid-replaces-dpid-and-dpuuid}

更新您的程式碼以使用`d_cid`或`d_cid_ic`，而非`d_dpid`和`d_dpuuid`。 DPID和DPUUID變數仍可繼續運作，但您應將其視為已過時。 這包括不含`d_ prefix`的DPID和DPUUID變體。

## DPID和DPUUID:評論{#dpid-dpuuid-review}

DPID和DPUUID是機碼值組，包含資料提供者ID和使用者ID。 這些機碼值配對會將提供者ID連結至使用者ID。 它們會在事件呼叫、傳入同步事件和ID呼叫期間傳入資料。 若沒有這些ID,[!DNL Audience Manager]和其他服務或功能將無法比對及同步ID。 這些變數有時會以或不以`d_`前置詞來表示，如下所示。 注意，在程式碼中，*斜體*&#x200B;表示變數預留位置。

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 語法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>資料提供者ID(DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資料提供者唯一使用者ID(DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

這些機碼值組仍可運作，但已遭取代。 您應更新程式碼，改為使用CID或CID_IC。

## CID和CID_IC:關於{#cid-cidic-about}

CID和CID_IC索引鍵值配對取代DPID和DPUUID。 它們提供的函式與DPID和DPUUID相同，但效率更高，因為它們包含資料提供者ID（或整合代碼）和使用者ID在單一機碼值組中。 在每個機碼值組中：

* =符號將鍵與其相關值分開。
* 非打印ASCII字元%01將值分隔。

`d_cid` 並 `d_cid_ic` 使用下列語法。注意，在程式碼中，*斜體*&#x200B;表示變數預留位置。

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
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客戶ID整合代碼(CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> <span class="term">整合代碼</span>是可以使用的替代ID，而非由<span class="keyword">Audience Manager</span>指派的資料來源ID。 如果您需要設定整合代碼，請參閱<a href="../features/manage-datasources.md#create-data-source">建立資料來源</a> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另請參閱[URL變數和宣告ID的語法](../features/declared-ids.md#variables-and-syntax)。

>[!NOTE]
>
>您可以為自己的資料來源和您有權存取的全域[共用資料來源](../features/datasources-list-and-settings.md#settings-menu-options)使用整合代碼。 例如，使用行動識別碼資料來源時，您可以使用整合代碼。 請使用下列整合程式碼，如下所指定：

* **GAID的DSID_20914** ，代表執行Android作業系統的裝置。
* **IDFA的DSID_20915** ，代表執行iOS作業系統的裝置。

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
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">新增: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">已過時: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>入站同步(IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">新增: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">已過時: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>產生Audience ManagerUUID(ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">新增: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">已過時: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

每個呼叫也可以包含多個`d_cid`和`d_cid_ic`索引鍵值組，如下所示：

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## 開發團隊的重要考量{#dev-considerations}

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
   <td colname="col2"> <p>您的開發團隊<i>必須</i>將URL編碼套用至CID索引鍵值配對中的下列變數： </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>注意：您必須在</i>將使用者ID和整合程式碼串連至字串之前，將使用者ID和整合程式碼編碼為URL。 <i>這是因為分隔兩個變數的ASCII字元%01在URL編碼中不能被捕獲。 </i></p> </p> <p>URL編碼可確保將包含保留或不安全字元（例如，但不限於，+或=）的使用者ID和整合代碼正確傳輸至我們的伺服器。 </p> <p>使用<a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII編碼表</a>作為參考。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用全域共用資料來源的整合程式碼 </p> </td> 
   <td colname="col2"> <p>您可以為自己的資料來源和您有權存取的全域<a href="../features/datasources-list-and-settings.md#settings-menu-options">共用資料來源</a>使用整合代碼。 例如，使用行動識別碼資料來源時，您可以使用整合代碼。 請使用下列整合程式碼，如下所指定： </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>GAID的DSID_20914</b> ，代表執行Android作業系統的裝置。 </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>IDFA的DSID_20915</b> ，代表執行iOS作業系統的裝置。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
