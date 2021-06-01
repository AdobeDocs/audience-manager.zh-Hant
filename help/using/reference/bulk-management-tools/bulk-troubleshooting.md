---
description: 工作表傳回錯誤或大量請求失敗時該做什麼。
seo-description: 工作表傳回錯誤或大量請求失敗時該做什麼。
seo-title: 大量管理工具的疑難排解提示
solution: Audience Manager
title: 大量管理工具的疑難排解提示
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 5%

---

# 大量管理工具的疑難排解提示{#troubleshooting-tips-for-bulk-management-tools}

工作表傳回錯誤或大量請求失敗時該做什麼。



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[UI中](../../features/administration/administration-overview.md) 指派的RBAC [!DNL Audience Manager] 群組權限會遵循 [!UICONTROL Bulk Management Tools]。

大量網路流量、伺服器使用量和大型資料集等因素都可能導致大量請求失敗或逾時。 如果有問題，工作表會停止寫入資料並顯示錯誤訊息。 發生此情況時，您應：

* 閱讀錯誤訊息。
* 解決問題。
* 刪除所有已更新的行。
* 再試一次批量請求。

## 驗證錯誤、長延遲或無響應行為{#delays-behavior}

下表列出在工作表中提出大量請求時可能遇到的一些常見問題。 嘗試使用建議的解決方案來修正這些問題。 如果建議的解決方案無法解決問題，則應保存您的工作，重新啟動電腦，然後重試請求，而不啟動或使用其他應用程式。

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
    <b>更新至最新版Microsoft Excel</b>:當發行新版Microsoft Excel且您使用舊版時，「大量管理」工作表中可能會發生驗證錯誤。更新至最新版的Microsoft Excel以解決驗證錯誤。
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>長時間延遲</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>關閉相容性模式</b>:檢查您是否在Microsoft Excel的相容性模式中開啟了其他工作表。相容性模式可增加執行階段。 關閉在此模式下可能開啟的任何電子錶格，然後重試批量請求。 </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>系統資源</b>:有限的系統資源導致了長時間的延遲。在發出批量請求之前，請嘗試關閉所有其他程式。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>無回應</b> </td> 
   <td colname="col2">如果您按一下動作按鈕，卻未發生任何情況： 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">請務必為選取動作提供正確的標題集。 </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">請務必為複製的標題使用正確的工作表。 </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">檢查要在批量操作中使用的資料的位置。 所有標題都從A欄開始，第1列。 所有資料都會進入A欄第2列（緊接在標題下方）開始的對應標題。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 錯誤訊息

有時，進行大量變更時可能會收到錯誤訊息。 若要解譯錯誤訊息，請參閱API檔案中的[已定義的回應代碼](/help/using/api/rest-api-main/aam-api-getting-started.md)。
