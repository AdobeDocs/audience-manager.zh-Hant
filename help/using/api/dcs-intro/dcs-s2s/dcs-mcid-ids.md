---
description: ID服務客戶應參閱本節，瞭解如何讀取訪問者Cookie以獲取進行DCS API調用所需的ID。
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: 透過 Adobe Experience Platform Identity Service 取得使用者 ID 和區域
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 6%

---

# 透過 Adobe Experience Platform Identity Service 取得使用者 ID 和區域 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID服務客戶應參閱本節，瞭解如何讀取訪問者Cookie以獲取所需ID的資訊 [!DNL DCS] API調用。

## 從ID服務Cookie獲取用戶ID {#get-user-ids-from-service-cookie}

的 [Adobe Experience Platform身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html) 將訪問者和區域ID分配給訪問您網站的用戶。 這些ID標識了中所有解決方案中的用戶 [!DNL Experience Cloud] 如果你想要 [!DNL DCS] 呼叫。

* 的 [!UICONTROL user ID] 需要標識資料並將其與特定訪問者關聯。
* 的 [!UICONTROL region ID] 是必需的，因為它與區域伺服器名稱相關聯，您需要將資料發送到 [!DNL DCS]。 的 [!DNL DCS] 將資訊儲存在地理上最接近站點訪問者的資料中心中。 請參閱 [DCS 地區 ID、位置與主機名稱](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

ID服務客戶可以從ID服務Cookie或通過調用函式提取此資訊。 下表說明了開始時需要完成的任務或步驟。

中的代碼 *斜體* 表示變數佔位符。

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任務 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. 檢查 <span class="keyword"> Experience Cloud</span> 狀態</b> </p> </td> 
   <td colname="col2"> <p>你需要 <span class="keyword"> Experience Cloud</span> 帳戶以使用ID服務。 如果你有 <span class="keyword"> Experience Cloud</span> 帳戶，太好了！ </p> <p> 如果你不是 <span class="keyword"> Experience Cloud</span>，然後註冊。 我們很想擁有你，總有更多空間。 有關如何設定帳戶的說明，請參閱 <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> 為核心服務啟用您的解決方案</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2.設定 <span class="keyword"> ID服務</span></b> </p> </td> 
   <td colname="col2"> <p>的 <span class="keyword"> ID服務</span> 由要用於資料收集的每頁上的JavaScript代碼組成。 請參閱ID服務 <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> 實施指南</a> 的子菜單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3.閱讀 <span class="keyword"> ID服務</span> 餅</b> </p> </td> 
   <td colname="col2"> <p>的 <span class="keyword"> ID服務</span> 將用戶和區域ID儲存在AMCVcookie中。 完整Cookie名稱為 <code>AMCV_<i>###</i>@AdobeOrg</code>。 的 <code><i>###</i></code> 元素是組織ID的佔位符。 請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a> 的雙曲餘切值。 </p> <p>分析這些鍵值對的AMCVcookie: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>:此鍵值對保存 <span class="keyword"> Experience Cloud</span> 用戶ID。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>:此鍵值對保存區域ID(有時稱為 <span class="term"> 位置提示</span>)，它與區域伺服器名關聯。 </li> 
     </ul> </p> <p>您可以撥打 <span class="wintitle"> DCS</span> 一旦您擁有了用戶和區域ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4.檢索 <span class="keyword"> Experience CloudID</span> 具有getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>（可選）</i> 此函式返回 <span class="keyword"> Experience Cloud</span> 訪客身份。 它專為定制解決方案和特定使用案例而設計。 請參閱 <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> 使用getMarketingCloudVisitorID</a> 下面和 <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> 相關ID服務文檔</a>。 </p> <p>如果從ID服務Cookie獲取用戶和位置ID，則無需使用此功能。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用 `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

獲取訪問者身份的另一種方法是 `getMarketingCloudVisitorID` 的子菜單。 調用此函式時，將查詢 [!DNL ID service] 並返回ID。 `getMarketingCloudVisitorID` 接受可選 `callback` 參數，如所示：

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 回叫使用和用途 {#callback-usage}

`callback` 為可選項。 此函式不工作，但僅當訪問者具有 [!DNL Experience Cloud] 瀏覽器中的cookie。 如果訪問者Cookie丟失，或訪問者沒有ID，則函式返回空 `()` 的雙曲餘切值。 即使在載入頁面並訪問者收到新ID後，也會發生這種情況。 為了避免這種情況， `callback` 強制此函式在載入頁面後檢查訪問者ID。 沒有 `callback`，即使稍後將訪問者瀏覽器寫入訪問者ID函式，訪問者ID函式也不會返回。

## 後續步驟 {#next-steps}

一旦您擁有了用戶和區域ID，就可以開始發送和接收 [!DNL DCS] 資料。 請參閱 [進行DCS API調用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。
