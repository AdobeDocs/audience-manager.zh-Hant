---
description: 更新代碼以使用d_cid或d_cid_ic代替d_dpid和d_dpuuid。 DPID和DPUUID變數將繼續工作，但您應認為它們已棄用。 這包括沒有d_前置詞的DPID和DPUUID變型。
seo-description: Update your code to use d_cid or d_cid_ic instead of d_dpid and d_dpuuid. The DPID and DPUUID variables will continue to work, but you should consider them deprecated. This includes DPID and DPUUID variants without the d_ prefix.
seo-title: CID Replaces DPID and DPUUID
solution: Audience Manager
title: CID 取代 DPID 及 DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: Reference
exl-id: 18e6b1db-fe51-4560-9458-8d65474d2506
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 4%

---

# CID 取代 DPID 及 DPUUID{#cid-replaces-dpid-and-dpuuid}

更新要使用的代碼 `d_cid` 或 `d_cid_ic` 而不是 `d_dpid` 和 `d_dpuuid`。 DPID和DPUUID變數將繼續工作，但您應認為它們已棄用。 這包括DPID和DPUUID變型，但 `d_ prefix`。

## DPID和DPUUID:回顧 {#dpid-dpuuid-review}

DPID和DPUUID是包含資料提供器ID和用戶ID的鍵值對。 這些鍵值對將提供程式ID連結到用戶ID。 它們在事件調用、入站同步事件和ID調用期間發送資料。 沒有他們， [!DNL Audience Manager]，以及其他服務或功能，則無法匹配和同步ID。 這些變數有時使用或不使用 `d_` 前置詞如下所示。 注意，在代碼中， *斜體* 指示變數佔位符。

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 語法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>資料提供程式ID(DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資料提供程式唯一用戶ID(DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

這些鍵值對仍然有效，但已棄用。 您應更新代碼以改用CID或CID_IC。

## CID和CID_IC:關於 {#cid-cidic-about}

CID和CID_IC鍵值對替換DPID和DPUUID。 它們提供與DPID和DPUUID相同的功能，但效率更高，因為它們將資料提供程式ID（或整合代碼）和用戶ID包含在單個鍵值對中。 在每個鍵值對中：

* =符號將鍵與其相關值分開。
* 非打印ASCII字元%01分隔值。

`d_cid` 和 `d_cid_ic` 使用下面所示的語法。 注意，在代碼中， *斜體* 指示變數佔位符。

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
   <td colname="col1"> <p>客戶標識整合代碼(CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> 安 <span class="term"> 整合代碼</span> 是可以使用的替代ID，而不是資料源ID，分配者 <span class="keyword"> Audience Manager</span>。 請參閱 <a href="../features/manage-datasources.md#create-data-source"> 建立資料源</a> 的子菜單。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另請參見 [聲明ID的URL變數和語法](../features/declared-ids.md#variables-and-syntax)。

>[!NOTE]
>
>您可以將整合代碼用於您自己的資料源和全局 [共用資料源](../features/datasources-list-and-settings.md#settings-menu-options)，您可以訪問。 例如，在處理移動標識符資料源時可以使用整合代碼。 使用以下整合代碼，完全如下所述：

* **DSID_20914** 表示運行Android作業系統的設備。
* **DSID_20915** 表示運行iOS作業系統的設備。

**範例**

下表按事件類型提供了示例。

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件類型 </th> 
   <th colname="col2" class="entry"> 範例 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Event </p> </td> 
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
   <td colname="col1"> <p>生成Audience ManagerUUID(ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">新增: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">已過時: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

每個呼叫也可包括多個 `d_cid` 和 `d_cid_ic` 鍵值對如下所示：

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## 開發團隊的重要考慮事項 {#dev-considerations}

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
   <td colname="col2"> <p>您的開發團隊 <i>必須</i> 將URL編碼應用於CID鍵值對中的以下變數： </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>注：您必須對用戶ID和整合代碼進行URL編碼 <i>先</i> 將它們串聯到字串中。 這是因為不能在URL編碼中捕獲分隔兩個變數的ASCII字元%01。 </p> </p> <p>URL編碼可確保將包含保留或不安全字元（如，但不限於， +或=）的用戶ID和整合代碼正確傳輸到我們的伺服器。 </p> <p>使用 <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII編碼表</a> 的下界。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用全局共用資料源的整合代碼 </p> </td> 
   <td colname="col2"> <p>您可以將整合代碼用於您自己的資料源和全局 <a href="../features/datasources-list-and-settings.md#settings-menu-options"> 共用資料源</a>，您可以訪問。 例如，在處理移動標識符資料源時可以使用整合代碼。 使用以下整合代碼，完全如下所述： </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b> 表示運行Android作業系統的設備。 </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> 表示運行iOS作業系統的設備。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
