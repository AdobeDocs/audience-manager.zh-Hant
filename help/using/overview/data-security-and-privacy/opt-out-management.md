---
description: Adobe符合所有適用於選擇退出管理的業界標準。請參閱以取得Audience Manager支援之退出類型的完整資訊。
seo-description: Adobe符合所有適用於選擇退出管理的業界標準。請參閱以取得Audience Manager支援之退出類型的完整資訊。
seo-title: 退出管理
solution: Audience Manager
title: 退出管理
uuid: 61b43e0e-bfe3-497e-ad2-6a942 a98407 e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Opt-out Management{#opt-out-management}

Adobe符合所有適用於選擇退出管理的業界標準。請參閱以取得Audience Manager支援之退出類型的完整資訊。

## Global Opt-Out {#global-opt-out}

全域選擇退出代表所有品牌的Audience Manager和其他Adobe Experience Cloud解決方案的選擇退出。下表列出全域選擇退出的方法：

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選擇退出 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page </a> provides 1-click features that let your end users control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section </a> of the Privacy Choices page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager的直接API呼叫 </p> </td> 
   <td colname="col2"> <p>You can opt-out from data collection by all Audience Manager brands by making a call to the DCS API below and include the <a href="../../reference/ids-in-aam.md"> Audience Manager User ID </a>: </p> <p> <code> curr -i「https://www.demdex.net/demoptout.jpg」—cookie」demdex=1234567780123456780120123456780121245678；dextp=12；DST=12」 </code> </p> <p>As a result, we will set <code>demdex=NOTARGET</code> and <code>dextp=NOTARGET</code> cookies for the submitted Audience Manager User ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動裝置 </p> </td> 
   <td colname="col2"> <p>請參閱選擇退出和隱私權設定： </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android裝置 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS 裝置 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的使用者也可以造訪我們業界標準合作夥伴的網站，選擇退出全球資料收集。

* [數位廣告聯盟(Digital Advertising Alliance，DAA](https://optout.aboutads.info/?c=2#!/))；
* [網路廣告促進會(NAI)](https://optout.networkadvertising.org/?c=1#!/)。

依照上述的選擇退出要求：

* Audience Manager將停止所有資料收集、細分或啓用。
* 歷史資料會在120天後從使用者描述檔移除。

## Partner Level Opt-Out {#partner-opt-out}

合作夥伴層級選擇退出允許特定Audience Manager合作夥伴選擇退出資料收集。The partner-level opt-out works with [Declared ID](../../features/declared-ids.md) calls and Device ID calls, as described in the sections below.

### 使用宣告ID呼叫的合作夥伴層級選擇退出

在合作夥伴層級選擇退出時，加上宣告的ID呼叫：

* The last device ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)) linked to the [CRM ID](../../reference/ids-in-aam.md) is opted out of data collection.
* Audience Manager會針對連結至CRM ID的最後一個裝置ID停止所有資料收集、分段或啓用。
* 不會刪除歷史資料。

<br/>

**退出呼叫**

When Audience Manager receives a partner-level opt-out request, the JSON returned by the DCS contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the Audience Manager user ID.

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

You can make a declared ID opt-out request with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. 請參閱 [CID 取代 DPID 及 DPUUID](../../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

**使用CID和CID_ IC選擇退出**

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#variables-and-syntax).

| 退出使用 | 程式碼範例 |
|--- |--- |
| 資料提供者ID和使用者ID。 | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| 整合代碼和使用者ID。 | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| 多d_ cid和d_ cid_ ic key-value配對。 | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### 合作夥伴層級選擇退出裝置ID呼叫

You can opt-out from data collection on a given device ID for a brand by making the following calls to the [DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| 退出使用 | 程式碼範例 |
|--- |--- |
| An Audience Manager Unique User ID (`uuid`). | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| An Experience Cloud ID (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Read more about `uuid`, `mid` and `imsOrgId` in the [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

遵循裝置ID呼叫的合作夥伴層級選擇退出：

* 裝置ID已選擇退出資料收集。
* Audience Manager將停止針對裝置ID的合作夥伴所有資料收集、分段或啓動。
* 不會刪除歷史資料。
