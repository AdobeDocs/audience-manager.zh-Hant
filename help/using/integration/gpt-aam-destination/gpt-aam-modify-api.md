---
description: 在呼叫Google Publisher標籤。setTargeting方法前，新增if陳述式以檢查Audience Manager Cookie。
seo-description: 在呼叫Google Publisher標籤。setTargeting方法前，新增if陳述式以檢查Audience Manager Cookie。
seo-title: 修改 GPT setTargeting API 呼叫
solution: Audience Manager
title: 修改 GPT setTargeting API 呼叫
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 9%

---


# Modify the GPT `setTargeting` API Call {#modify-the-gpt-settargeting-api-call}

在呼叫方法前，新增if陳述式以檢查Audience Manager [!DNL Google Publisher Tag]`.setTargeting` Cookie。

## 使用陳述式檢查Audience Manager Cookies是 `IF` 否

方 `.setTargeting` 法會從Audience Manager目標Cookie和唯一使用者ID Cookie( `aam_uuid`)取得資料。 不過，如 `.setTargeting` 果在寫入這些Cookie [!UICONTROL DIL] 前被呼叫，或Cookie是空的，您可能會在頁面載入時看到錯誤。 若要避免此情況，請將方 `.setTargeting` 法包裝在 `if` 檢查這些Cookie的陳述式中。 如果未設定，則此語句會阻 `.setTargeting` 止調用函 `AamGpt` 數。

### `IF` 語句代碼示例

在此範例中，Audience Manager目標Cookie名稱為 `Sample`。 您在Audience Manager使用者介面中建立目標Cookie時，會設定此名稱。 [!UICONTROL DIL] 設定 `aam_uuid` Cookie，且名稱無法變更。

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
>視您要與整合的方式而 [!DNL Google Ad Manager]定，您只需要上述程式碼範例中的某些行：
>
>* 用戶端整合： 僅使用第1-3行。
>* 伺服器端整合： 這些線條都不需要。
>* 在以下 [!DNL Google Ad Manager] 位置收錄要報告的日誌檔案 [!DNL Audience Manager]: 僅使用第4-6行。 此程式碼會將Cookie的值 `aam_uuid` 插入記錄檔中，以便擷取這些Cookie以供報告。


### `AamGpt` 函式和資料類型

定義語句中使用的關鍵 `if` 變數。

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
   <td colname="col3"> <p>傳回鍵值區段對中的鍵。 例如，如果您的鍵值對由組成， <code> color=blue </code>則會傳回 <code> color </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>字串陣列 </p> </td> 
   <td colname="col3"> <p>傳回陣列中的值，例如 <code> ["value1","value2"] </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>傳回Audience Manager使用者ID，例如 <code> 12345 </code>。 </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [建立 GPT 目的地](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [適用於 Google 發佈商廣告代碼的 Audience Manager 代碼](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

