---
description: 新增if陳述式，在呼叫Google Publisher標籤.setTargeting方法之前檢查Audience ManagerCookie。
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: 修改GPT setTargeting API呼叫
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# 修改GPT `setTargeting` API呼叫 {#modify-the-gpt-settargeting-api-call}

在呼叫[!DNL Google Publisher Tag] `.setTargeting`方法之前，新增if陳述式以檢查Audience ManagerCookie。

## 使用`IF`陳述式檢查Audience ManagerCookie

`.setTargeting`方法從Audience Manager目的地Cookie和唯一使用者ID Cookie ( `aam_uuid`)取得資料。 不過，如果`.setTargeting`在[!UICONTROL DIL]寫入這些Cookie之前被叫用，或Cookie是空的，您可能會在頁面載入時看到錯誤。 為避免此問題，請將`.setTargeting`方法包裝在檢查這些Cookie的`if`陳述式中。 如果未設定，此陳述式會防止`.setTargeting`呼叫`AamGpt`函式。

### `IF`陳述式程式碼範例

在此範例中，Audience Manager目的地Cookie名稱為`Sample`。 當您在Audience Manager使用者介面中建立目的地Cookie時，請設定此名稱。 [!UICONTROL DIL]已設定`aam_uuid` Cookie，且無法變更名稱。

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
>根據您想要與[!DNL Google Ad Manager]整合的方式，您只需要上述程式碼範例中的部分行：
>
>* 使用者端整合：僅使用第1-3行。
>* 伺服器端整合：不需要任何行。
>* 擷取[!DNL Google Ad Manager]個記錄檔以在[!DNL Audience Manager]中報告：僅使用第4-6行。 此程式碼會將`aam_uuid` Cookie的值插入記錄檔中，以便擷取這些值以用於報表。

### `AamGpt`函式和資料型別

定義`if`陳述式中使用的索引鍵變數。

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
   <td colname="col3"> <p>傳回索引鍵/值區段配對中的索引鍵。 例如，如果您的機碼值組包含<code> color=blue </code>，這會傳回<code> color </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>字串陣列 </p> </td> 
   <td colname="col3"> <p>傳回陣列中的值，例如<code> ["value1","value2"] </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>傳回Audience Manager的使用者識別碼，例如<code> 12345 </code>。 </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [建立 GPT 目的地](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [適用於 Google 發佈商廣告代碼的 Audience Manager 代碼](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
