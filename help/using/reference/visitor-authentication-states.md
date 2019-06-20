---
description: Audience Manager中的訪客驗證狀態會判斷新特徵資訊是否寫入訪客已驗證的描述檔或裝置描述檔(從中收集資料)。Audience Manager會以相同方式處理事件呼叫中的訪客ID驗證狀態未知和LOGED_ OUT。
keywords: dpm.demdex.net
seo-description: Audience Manager中的訪客驗證狀態會判斷新特徵資訊是否寫入訪客已驗證的描述檔或裝置描述檔(從中收集資料)。Audience Manager會以相同方式處理事件呼叫中的訪客ID驗證狀態未知和LOGED_ OUT。
seo-title: Audience Manager中的訪客驗證狀態
solution: Audience Manager
title: Audience Manager中的訪客驗證狀態
uuid: d748c0c3-583-3fb9-ab3 e-793f5 f252 e47
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Visitor Authentication States in Audience Manager{#visitor-authentication-states-in-audience-manager}

Audience Manager中的訪客驗證狀態會判斷新特徵資訊是否寫入訪客已驗證的描述檔或裝置描述檔(從中收集資料)。Audience Manager會以相同方式處理事件呼叫中的訪客ID驗證狀態未知和LOGED_ OUT。

Beginning with [!DNL Experience Cloud] ID service v1.5+, the `setCustomerID` method includes the optional `AuthState` object. `AuthState` 根據 [訪客驗證狀態來識別訪客](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)。[!DNL Audience Manager] 以不同的方式處理所實現的特性，視呼叫中傳遞的驗證狀態和您用於分段的 [設定檔合併規則](../features/profile-merge-rules/merge-rules-dashboard.md) 而定。

## Authentication Status: UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>要求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>從已驗證的個人檔案讀取</b> 資訊 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>將</b> 新特性寫入已驗證的描述檔 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>是的，如果已驗證的選項合併規則=「上次驗證的設定檔」。 </p> </td> 
   <td colname="col3" morerows="1"> <p>否，特徵資料會新增至裝置描述檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>否，如果已驗證的選項合併規則=「目前已驗證的個人檔案」或「無驗證的個人檔案」。 </p> </td> 
  </tr> 
 </tbody> 
</table>

範例呼叫(會反白顯示對應至驗證狀態的請求值)：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentication Status: AUTHENTICATED {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>要求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>從已驗證的個人檔案讀取</b> 資訊 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>將</b> 新特性寫入已驗證的描述檔 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>是的，如果已驗證的選項合併規則=「目前已驗證的個人檔案」或「上次驗證的個人檔案」。 </p> </td> 
   <td colname="col3" morerows="1"> <p>是的，特徵資料會新增至已驗證的描述檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>否，如果已驗證的選項合併規則=「無驗證的個人檔案」。 </p> </td> 
  </tr> 
 </tbody> 
</table>

範例呼叫(會反白顯示對應至驗證狀態的請求值)：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentication Status: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>要求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>從已驗證的個人檔案讀取</b> 資訊 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>將</b> 新特性寫入已驗證的描述檔 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code>2</code> </p> </td> 
   <td colname="col2"> 是，如果已驗證的選項合併規則=「上次驗證的設定檔」 </td> 
   <td colname="col3" morerows="1"> <p>不行，特徵資料會寫入裝置描述檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> 否，如果已驗證的選項合併規則=「目前已驗證的個人檔案」或「無驗證個人檔案」 </td> 
  </tr> 
 </tbody> 
</table>

範例呼叫(會反白顯示對應至驗證狀態的請求值)：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 在這三個案例中，會對 [CID和UUID](../reference/ids-in-aam.md) 執行ID同步。

>[!MORE_贊_ this]
>
>* [客戶 ID 和驗證狀態](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)

