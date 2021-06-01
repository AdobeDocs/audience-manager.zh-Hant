---
description: 選用的布林值設定，可決定 DIL 是否要將資料傳送至 Adobe Experience Cloud Device Co-op。
seo-description: 選用的布林值設定，可決定 DIL 是否要將資料傳送至 Adobe Experience Cloud Device Co-op。
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
feature: DIL實作
exl-id: 33dca495-6923-4966-9ec3-8b0fd2f17649
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 77%

---

# isCoopSafe{#iscoopsafe}

選用的布林值設定，可決定 DIL 是否要將資料傳送至 Adobe Experience Cloud Device Co-op。

## 要求 {#requirements}

若要使用`isCoopSafe`，您必須：

* 使用[!UICONTROL DIL] v6.11或更高版本。
* 參與 [Experience Cloud Device Co-op](https://docs.adobe.com/content/help/zh-Hant/device-co-op/using/home.translate.html)。潛在的 Co-op 成員也需審閱此文件，以確定 `isCoopSafe` 是否解決了關於如何使用資料建立裝置圖形的可能問題。

* 請與您的[!DNL Adobe]顧問合作，在您的Device co-op帳戶上設定允許清單或封鎖清單標幟。 沒有自助路徑可啟用這些標幟。

## 使用個案 {#use-cases}

`isCoopSafe` 有助於解決關於 Device co-op 現有或潛在成員資料收集的 2 個使用案例。這些關於網站訪客資料如何傳給 Device co-op 的使用案例有助於建立設備圖形。以下表格說明 `isCoopSafe` 如何搭配其他使用案例以封鎖或傳送資料給裝置圖形

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>已驗證的訪客</b> </p> </td> 
   <td colname="col2"> <p>將<code> isCoopSafe </code>新增至您的<span class="wintitle">DIL</span>程式碼，以控制Device Co-op如何使用已驗證且接受或未接受使用條款的訪客資料來建立裝置圖形。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>第三方網站上的 DIL</b> </p> </td> 
   <td colname="col2"> <p>將<code> isCoopSafe </code>新增至您的<span class="wintitle">DIL</span>程式碼，以用於下列第三方網站： </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">無法確保已驗證的訪客是否已經接受使用者條款。 </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">需要控制 Device Co-op 使用資料的方式，以建立裝置圖形。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 語法與程式碼範例 {#syntax-code-sample}

**語法:** `isCoopSafe: true | false`

布林值選項決定 Device Co-op 是否使用客戶資料。

* `isCoopSafe: true`: 行動 SDK 或是網站所蒐集的訪客資料&#x200B;*可以*&#x200B;用來協助建立裝置圖形。

* `isCoopSafe: false`: 行動 SDK 或是網站所蒐集的訪客資料&#x200B;*不可以*&#x200B;用來協助建立裝置圖形。

**程式碼範例**

當DIL具現化時，請設定此選項。

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## 事件呼叫 POST 參數 {#post-parameters}

根據您設定的標幟（`true`或`false`）,[!UICONTROL DIL]將`isCoopSafe`轉譯為這些POST參數，並在事件呼叫時將參數傳送至[!DNL Adobe]:

* `d_coop_safe=1`
* `d_coop_unsafe=1`

POST 參數告知 [!DNL Experience Cloud] Device Co-op 是否能在裝置圖像中包含使用者資料。以下表格定義了在事件呼叫中 `isCoopSafe` 布林值標幟與所傳遞的 POST 參數之間的關係。如果您沒有使用 `isCoopSafe`，這些都不會在事件呼叫中傳遞。

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定狀態 </th> 
   <th colname="col2" class="entry"> POST 參數 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>Device Co-op 可以使用訪客資料來協助建立裝置圖像。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>Device Co-op 不可以使用訪客資料來協助建立裝置圖像。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Post-Instantiation API  {#post-instantiation}

這些 API 允許您覆寫 `isCoopSafe` 狀態。這些都是必要措施，因為它們可以讓您在網站或未重新整理的單頁應用程式中變更訪客實例化之後/登錄之後的狀態。舉例來說，如果用戶向您的網站或應用程式進行身份驗證，並隨後接受使用者條款原則允許 Device Co-op 使用其資料，則您可能需要呼叫這些 API。

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopSafe(); </code> </p> </td> 
   <td colname="col2"> <p>在後續事件呼叫中設定POST參數<code> d_coop_safe=1 </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>在後續事件呼叫中設定POST參數<code> d_coop_unsafe=1 </code>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->
