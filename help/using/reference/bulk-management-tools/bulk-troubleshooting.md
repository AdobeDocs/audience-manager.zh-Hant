---
description: 當工作表傳回錯誤或大量請求失敗時，該怎麼辦。
seo-description: 當工作表傳回錯誤或大量請求失敗時，該怎麼辦。
seo-title: 大量管理工具的疑難排解提示
solution: Audience Manager
title: 大量管理工具的疑難排解提示
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 5%

---


# 大量管理工具的疑難排解提示{#troubleshooting-tips-for-bulk-management-tools}

當工作表傳回錯誤或大量請求失敗時，該怎麼辦。



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[UI中指派的](../../features/administration/administration-overview.md) RBAC群組權 [!DNL Audience Manager] 限在中接受 [!UICONTROL Bulk Management Tools]。

大量網路流量、伺服器使用量和大型資料集等因素可能導致大量要求失敗或逾時。 如果有問題，工作表會停止寫入資料並顯示錯誤訊息。 發生這種情況時，您應：

* 閱讀錯誤訊息。
* 解決問題。
* 刪除已更新的所有行。
* 再次嘗試大量請求。

## 驗證錯誤、長時間延遲或無響應行為 {#delays-behavior}

下表列出您在使用工作表進行大量請求時可能遇到的一些常見問題。 嘗試使用建議的解決方案來修正這些問題。 如果建議的解決方案無法解決問題，您應儲存您的工作、重新啟動電腦，然後再次嘗試要求，而不需啟動或使用其他應用程式。

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
    <b>更新至最新版Microsoft Excel</b>: 當新版Microsoft Excel發行且您使用舊版時，「批量管理」工作表中可能會發生驗證錯誤。 更新至最新版Microsoft Excel以解決驗證錯誤。
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>長時間延遲</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>關閉相容模式</b>: 檢查您是否在Microsoft Excel的相容性模式中開啟其他工作表。 相容性模式可增加執行時期。 關閉您在此模式中開啟的任何試算表，然後再試一次大量請求。 </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>系統資源</b>: 系統資源有限導致長時間延遲。 請先嘗試關閉所有其他程式，再進行大量請求。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>無回應</b> </td> 
   <td colname="col2">如果您按一下動作按鈕，則不會發生任何事件： 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">請確定您有正確的標題集以用於選取動作。 </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">請確定您正在為複製的標題使用正確的工作表。 </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">檢查要在批量操作中使用的資料位置。 所有標題都以欄A第1列開始。 所有資料都會進入對應的標題，從欄A，列2開始（緊接在標題下方）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 錯誤訊息

有時，您會在進行大量變更時收到錯誤訊息。 若要解譯錯誤訊息，請參 [閱API檔案中的](/help/using/api/rest-api-main/aam-api-getting-started.md) 「回應代碼定義」。

