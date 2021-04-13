---
description: 在呼叫Google Publisher標籤。setTargeting方法前，新增if陳述式以檢查Audience ManagerCookie。
seo-description: 在呼叫Google Publisher標籤。setTargeting方法前，新增if陳述式以檢查Audience ManagerCookie。
seo-title: 修改 GPT setTargeting API 呼叫
solution: Audience Manager
title: 修改 GPT setTargeting API 呼叫
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: 協力廠商整合
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 9%

---

# 修改GPT `setTargeting` API調用{#modify-the-gpt-settargeting-api-call}

在呼叫[!DNL Google Publisher Tag] `.setTargeting`方法之前，新增if陳述式以檢查Audience ManagerCookie。

## 檢查Audience ManagerCookie是否具有`IF`語句

`.setTargeting`方法會從Audience Manager目標Cookie和唯一使用者ID Cookie(`aam_uuid`)取得資料。 但是，如果`.setTargeting`在[!UICONTROL DIL]寫入這些Cookie之前被呼叫，或Cookie是空的，則頁面載入時可能會出現錯誤。 為避免此問題，請在檢查這些Cookie的`if`陳述式中包住`.setTargeting`方法。 如果未設定，則此語句會阻止`.setTargeting`調用`AamGpt`函式。

### `IF` 語句代碼示例

在此範例中，Audience Manager目標Cookie名稱為`Sample`。 您在Audience Manager使用者介面中建立目標Cookie時，會設定此名稱。 [!UICONTROL DIL] 設定 `aam_uuid` Cookie，且名稱無法變更。

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
>根據您要與[!DNL Google Ad Manager]整合的方式，您只需要上述程式碼範例中的某些行：
>
>* 用戶端整合：僅使用第1-3行。
>* 伺服器端整合：這些線條都不需要。
>* 在[!DNL Audience Manager]中收錄[!DNL Google Ad Manager]記錄檔以供報告：僅使用第4-6行。 此程式碼會將`aam_uuid` Cookie的值插入記錄檔，以便擷取這些Cookie以供報告。


### `AamGpt` 函式和資料類型

定義`if`語句中使用的關鍵變數。

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
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>傳回鍵值區段對中的鍵。 例如，如果您的鍵值對由<code> color=blue </code>組成，則會傳回<code> color </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>字串陣列 </p> </td> 
   <td colname="col3"> <p>傳回陣列中的值，例如<code> ["value1","value2"] </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>傳回Audience Manager使用者ID，例如<code> 12345 </code>。 </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [建立 GPT 目的地](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [適用於 Google 發佈商廣告代碼的 Audience Manager 代碼](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

