---
description: 當工作表傳回錯誤或大量請求失敗時應執行的動作。
seo-description: 當工作表傳回錯誤或大量請求失敗時應執行的動作。
seo-title: 批量管理工具的疑難排解提示
solution: Audience Manager
title: 批量管理工具的疑難排解提示
uuid: 550908a-e24 e-4f31-954b-7132c0 c8 dc3 e
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Troubleshooting Tips for Bulk Management Tools{#troubleshooting-tips-for-bulk-management-tools}

當工作表傳回錯誤或大量請求失敗時應執行的動作。



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具的提供目的僅限於方便使用。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI](../../features/administration/administration-overview.md) 中指派的RBAC群組權限 [!DNL Audience Manager] 會受到尊重 [!UICONTROL Bulk Management Tools]。

嚴重網路流量、伺服器使用量和大型資料集等因素可能會導致大量要求失敗或逾時。如果發生問題，工作表會停止寫入資料並顯示錯誤訊息。此時，您應：

* 請閱讀錯誤訊息。
* 修正問題。
* 刪除已更新的所有列。
* 再次嘗試大量請求。

## Long delays or unresponsive behavior {#delays-behavior}

下表列出在使用工作表進行大量請求時可能遇到的一些常見問題。嘗試使用建議的解決方案來修正這些問題。如果建議的解決方案無法解決問題，請儲存您的工作、重新啓動電腦，然後再次嘗試請求，而不需啓動或使用其他應用程式。

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 故障 </th> 
   <th colname="col2" class="entry"> 解決方案 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>耽擱已久</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>關閉相容性模式</b>：請檢查您是否已在Microsoft Excel的相容性模式中開啓其他工作表。相容性模式可增加執行階段。關閉任何可在此模式中開啓的試算表，然後再次嘗試大量請求。 </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>系統資源</b>：有限的系統資源造成長時間的延誤。請先關閉所有其他方案，再進行大量要求。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>無回應</b> </td> 
   <td colname="col2">如果您按下動作按鈕，就不會發生任何事： 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">確定您擁有選取動作的正確標題組。 </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">確定您使用正確的工作表做為複製的標題。 </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">檢查您要在大量作業中使用的資料位置。所有標題都會開始於A，第列。所有資料都會進入對應的標題，從A欄、列(緊接在標題下方)開始。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

