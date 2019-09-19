---
description: Adobe在退出管理方面符合所有業界標準。 閱讀以取得Audience manager支援之退出類型的完整資訊。
seo-description: Adobe在退出管理方面符合所有業界標準。 閱讀以取得Audience manager支援之退出類型的完整資訊。
seo-title: 退出管理
solution: Audience Manager
title: 退出管理
uuid: 61b43e0e-bfe3-497e-ade2-6a942a98407e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# 退出管理{#opt-out-management}

Adobe在退出管理方面符合所有業界標準。 閱讀以取得Audience manager支援之退出類型的完整資訊。

## 全球退出 {#global-opt-out}

全域退出代表所有品牌的Audience manager和其他Adobe Experience cloud解決方案都可選擇退出。 下表列出全域退出使用的方法：

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 退出 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>「您 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 的隱私權選 </a> 擇」頁面提供單鍵功能，讓您的使用者能夠控制Adobe Experience cloud廣告解決方案（包括Audience Manager）收集和選擇退出資料。 具體而言，請參 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 閱「隱私權選 </a> 擇」頁面的商業客戶區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>直接API呼叫Audience Manager </p> </td> 
   <td colname="col2"> <p>您可以透過呼叫以下的DCS API並加入 <a href="../../reference/ids-in-aam.md"> Audience Manager使用者ID，選擇退出所有Audience manager品牌的資料收集 </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex=1234567890123456789012345689012345789012345678;dextp=12;DST=12英吋 </code> </p> <p>因此，我們會為已提 <code>交的Audience Manager使用者ID設定demdex=NOTARGET</code><code>和dextp=NOTARGET</code> Cookie。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動裝置 </p> </td> 
   <td colname="col2"> <p>請參閱下列的退出與隱私權設定： </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android裝置 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS 裝置 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的使用者也可以造訪我們業界標準合作夥伴的網站，選擇退出全球資料收集。

* [數位廣告聯盟(DAA)](https://optout.aboutads.info/?c=2#!/);
* [網路廣告計畫(NAI)](https://optout.networkadvertising.org/?c=1#!/)。

遵循上述的退出要求：

* Audience manager將停止後續的所有資料收集、區段或啟動。
* 120天後，歷史資料會從使用者描述檔中移除。

## 合作夥伴層級選擇退出 {#partner-opt-out}

合作夥伴層級的退出允許特定Audience manager合作夥伴選擇退出資料收集。 合作夥伴層級的退出可搭配 [Declared ID呼叫和Device](../../features/declared-ids.md) ID呼叫運作，如以下章節所述。

### 具有宣告之ID呼叫的合作夥伴層級選擇退出

使用宣告的ID呼叫，在合作夥伴層級選擇退出後：

* 連結至[CRM ID的最後一個裝置ID(](../../reference/ids-in-aam.md)Audience Manager唯一使用者ID [](../../reference/ids-in-aam.md) )已選擇退出資料收集。
* Audience manager將停止所有連結至CRM ID之最後一個裝置ID的資料收集、分段或啟動。
* 不會刪除歷史資料。

<br/>

**退出呼叫**

當Audience Manager收到合作夥伴層級的退出請求時，DCS傳回的JSON會包含錯誤碼171 [，加上訊息](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)[!UICONTROL "Encountered opt out tag"]，而非Audience manager使用者ID。

<!-- 

<p> 
 <ul id="ul_65EF2E1ED8F24457A35299E38AFE1DBE"> 
  <li id="li_832D0B507BC64782A5D3662FD5173A37">Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL. </li> 
  <li id="li_D6C41CB385C5401D98156E5A3D79AAEE">The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions). </li> 
 </ul> </p>

 -->

<!-- 

<p>See <a href="../../overview/data-security-and-privacy/data-privacy.md"> Data Privacy </a> for more information about opting-out of data collection. </p>

 -->



**範例**

您可以使用和金鑰值配對，提出宣告 `d_cid` 的ID `d_cid_ic` 退出要求。 舊有參數(例如 `d_dpid` 和) `d_dpuuid` 仍然有效，但被視為已過時。 請參閱 [CID 取代 DPID 及 DPUUID](../../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

**使用CID和CID_IC退出**

如需說明和語法，請參 [閱URL變數和Declared ID的語法](../../features/declared-ids.md#variables-and-syntax)。

| 選擇退出使用 | 程式碼範例 |
|--- |--- |
| 資料提供者ID和使用者ID。 | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| 整合程式碼和使用者ID。 | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| 多個d_cid和d_cid_ic鍵值對。 | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### 使用裝置ID呼叫的合作夥伴層級選擇退出

您可以透過對 [DCS API進行下列呼叫，選擇退出品牌之指定裝置ID上的資料收集](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| 選擇退出使用 | 程式碼範例 |
|--- |--- |
| Audience manager唯一使用者ID(`uuid`)。 | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Experience Cloud ID(`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

閱讀更多 `uuid`相關資 `mid` 訊， `imsOrgId` 以及Audience manager [中的ID索引](/help/using/reference/ids-in-aam.md)。

透過裝置ID呼叫，在合作夥伴層級選擇退出後：

* 裝置ID已選擇退出資料收集。
* Audience manager將停止針對合作夥伴的所有資料收集、區段或啟動，而後會針對裝置ID進行。
* 不會刪除歷史資料。
