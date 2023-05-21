---
description: 當工作表返回錯誤或批量請求失敗時，該執行什麼操作。
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: 大量管理工具的疑難排解提示
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 4%

---

# 大量管理工具的疑難排解提示{#troubleshooting-tips-for-bulk-management-tools}

當工作表返回錯誤或批量請求失敗時，該執行什麼操作。



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[RBAC組權限](../../features/administration/administration-overview.md) 在 [!DNL Audience Manager] UI在 [!UICONTROL Bulk Management Tools]。

網路流量大、伺服器使用量大和資料集大等因素可能導致批量請求失敗或超時。 如果出現問題，工作表將停止寫入資料並顯示錯誤消息。 發生這種情況時，您應：

* 閱讀錯誤消息。
* 解決問題。
* 刪除所有已更新的行。
* 請重試批量請求。

## 驗證錯誤、長延遲或無響應行為 {#delays-behavior}

下表列出了在使用工作表進行批量請求時可能遇到的一些常見問題。 嘗試使用建議的解決方案解決這些問題。 如果建議的解決方案未解決問題，您應保存您的工作，重新啟動電腦，然後重試請求，而無需啟動或使用其他應用程式。

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 故障 </th> 
   <th colname="col2" class="entry"> 解決方案 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>驗證錯誤</b> </td> 
   <td colname="col2"> 
    <b>更新到最新版MicrosoftExcel</b>:當新版本的MicrosoftExcel發佈後，您使用的是較舊版本，您可能會在批量管理工作表中遇到驗證錯誤。 更新到最新版本的MicrosoftExcel以解決身份驗證錯誤。
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>長時間延遲</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>關閉相容模式</b>:檢查是否在MicrosoftExcel的相容模式下開啟了其他工作表。 相容模式可以增加運行時間。 關閉在此模式下可能開啟的所有電子錶格，然後重試批量請求。 </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>系統資源</b>:系統資源有限導致了長時間的延遲。 在發出批量請求之前，請嘗試關閉所有其他程式。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>無響應</b> </td> 
   <td colname="col2">如果按一下操作按鈕，則不會發生任何情況： 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">確保為選擇操作設定了正確的標題集。 </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">確保正在為複製的題頭使用正確的工作表。 </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">檢查要在批量操作中使用的資料的位置。 所有標題都從第A列第1行開始。 所有資料都以A列第2行（緊接在標題下）開始的相應標題中顯示。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 錯誤訊息

有時，在進行批量更改時可能會收到錯誤消息。 要解釋錯誤消息，請參見 [已定義響應代碼](/help/using/api/rest-api-main/aam-api-getting-started.md) 在API文檔中。
