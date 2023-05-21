---
description: 在調用Google發佈器標籤.setTargeting方法之前，添加if語句以檢查Audience ManagerCookie。
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: 修改 GPT setTargeting API 呼叫
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 7%

---

# 修改GPT `setTargeting` API調用 {#modify-the-gpt-settargeting-api-call}

在調用Audience ManagerCookie之前，添加if語句以檢查 [!DNL Google Publisher Tag] `.setTargeting` 的雙曲餘切值。

## 檢查Audience ManagerCookie `IF` 語句

的 `.setTargeting` 方法從Audience Manager目標cookie和唯一用戶ID cookie獲取資料( `aam_uuid`)。 但是，如果 `.setTargeting` 在 [!UICONTROL DIL] 寫入這些cookie或cookie為空，在載入頁面時可能會出現錯誤。 為避免此情況，請包裝 `.setTargeting` 方法 `if` 用於檢查這些cookie的語句。 如果未設定，則此語句將阻止 `.setTargeting` 從呼叫 `AamGpt` 的子菜單。

### `IF` 語句代碼示例

在此示例中，Audience Manager目標cookie名稱為 `Sample`。 在Audience Manager用戶介面中建立目標Cookie時，可設定此名稱。 [!UICONTROL DIL] 設定 `aam_uuid` cookie和名稱無法更改。

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
>取決於您希望與 [!DNL Google Ad Manager]，您只需要上面代碼示例中的一些行：
>
>* 客戶端整合：僅使用第1-3行。
>* 伺服器端整合：不需要這些線。
>* 英格斯特 [!DNL Google Ad Manager] 用於報告的日誌檔案 [!DNL Audience Manager]:僅使用第4-6行。 此代碼插入 `aam_uuid` 將餅乾放入日誌中，以便可以攝取報告。


### `AamGpt` 函式和資料類型

定義在 `if` 的雙曲餘切值。

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
   <td colname="col3"> <p>返回鍵值段對中的鍵。 例如，如果鍵值對由 <code> color=blue </code>，返回 <code> color </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>字串陣列 </p> </td> 
   <td colname="col3"> <p>返回陣列中的值，例如 <code> ["value1","value2"] </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>整型 </p> </td> 
   <td colname="col3"> <p>返回Audience Manager用戶ID，例如 <code> 12345 </code>。 </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [建立 GPT 目的地](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [適用於 Google 發佈商廣告代碼的 Audience Manager 代碼](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

