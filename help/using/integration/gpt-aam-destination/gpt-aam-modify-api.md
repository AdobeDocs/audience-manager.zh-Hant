---
description: 新增if陳述式以檢查Audience Manager Cookie，然後呼叫Google Publisher Tag. setTargeting方法。
seo-description: 新增if陳述式以檢查Audience Manager Cookie，然後呼叫Google Publisher Tag. setTargeting方法。
seo-title: 修改GPT Settargeting API呼叫
solution: Audience Manager
title: 修改GPT Settargeting API呼叫
uuid: 0cd38f30-5d29-4511-a779-d32587 f1 dafb
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Modify the GPT `setTargeting` API Call {#modify-the-gpt-settargeting-api-call}

Add an if statement to check for Audience Manager cookies before calling the [!DNL Google Publisher Tag] `.setTargeting` method.

## Check for Audience Manager Cookies With an `IF` Statement

`.setTargeting` 此方法會從Audience Manager目的地Cookie和唯一使用者ID Cookie( `aam_uuid`)取得資料。However, if `.setTargeting` gets invoked before [!UICONTROL DIL] writes these cookies, or the cookies are empty, you may see errors when the page loads. To help avoid this, wrap the `.setTargeting` method in an `if` statement that checks for these cookies. If they're not set, this statement prevents `.setTargeting` from calling the `AamGpt` function.

### `IF` 陳述式程式碼範例

In this example, the Audience Manager destination cookie name is `Sample`. 當您在Audience Manager UI中建立目標Cookie時，就會設定此名稱。[!UICONTROL DIL] 設定 `aam_uuid` Cookie且無法變更名稱。

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>Depending on how you want to integrate with [!DNL DFP], you only need some of the lines in the code sample above:
>
>* 用戶端整合：僅限使用行1-3。
>* 伺服器端整合：不需要任何線條。
>* Ingest [!DNL DFP] log files for reporting in [!DNL Audience Manager]: use lines 4-6 only. This code inserts the value of the `aam_uuid` cookie into the logs so they can be ingested for reporting.


### `AamGpt` 函數與資料類型

Defines the key variables used in the `if` statement.

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 函數 </th> 
   <th colname="col2" class="entry"> 類型 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> AamGPT. getKey </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>傳回索引鍵值區段對中的索引鍵。For example, if your key-value pair consisted of <code> color=blue </code>, this returns <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGPT. getValues </code> </p> </td> 
   <td colname="col2"> <p>字串陣列 </p> </td> 
   <td colname="col3"> <p>Returns values in an array, e.g., <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGPT. getCookie </code> </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Returns the Audience Manager user ID, e.g., <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORE_贊_ this]
>
>* [建立GPT目的地](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Google Publisher標記的Audience Manager代碼](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

