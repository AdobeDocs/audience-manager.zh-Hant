---
description: 使用「儀表板」檢視依特徵類型和區段劃分之合作夥伴獨特訪客計數的資訊。
seo-description: 使用「儀表板」檢視依特徵類型和區段劃分之合作夥伴獨特訪客計數的資訊。
seo-title: 報表控制面板
solution: Audience Manager
title: 報表控制面板
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Reports Dashboard {#reports-dashboard}

在指定的時間範圍內，使用「儀表板」檢視依特徵類型和區段劃分的獨特訪客計數資訊。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) to extend user-group permissions to the [!UICONTROL Dashboard].使用者只能在控制面板上看到具有檢視權限的資訊。[!UICONTROL RBAC] 功能可讓您控制可供內部團隊檢視的報告資料。

例如，管理不同廣告商帳戶的代理商可以設定使用者群組權限，讓管理廣告商A帳戶的團隊無法看見廣告商B的報表資料。此控制面板可用來疑難排解資料傳送問題。

例如，如果您注意到下降或尖峰，在獨特使用者的類型劃分(基於規則型與在職)的詳盡分析中，您有更好的起點來追蹤潛在的資料傳送問題。If you notice a dip in total unique users and in on-boarded unique users, you can go to the [!UICONTROL On-boarding Status] report to see if there was an issue with an inbound file.

**若要存取控制面板：**

1. In the top navigation menu, click **[!UICONTROL Dashboard]**.
2. *選擇性* ：從下拉式清單(天、14天(預設值)、30天或60天)，從上次報告日期中選取所要的時間範圍。

   Depending on the period selected, the delta change in the [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] and [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] panels displays the change in unique visitors in the audience over the period ending today vs. the prior period of the same length. 例如，如果您選取天，則delta會比較前七天內的獨特訪客，並對七天前結束的獨特訪客進行比較。

   >[!NOTE]
   >
   >You can investigate a delta change that seems out of the ordinary by running a [!UICONTROL Trend] report. For example, if you see an unusually large delta change during the last seven days, you could run a [!UICONTROL Trend] report for the last 14 days (2 x 7) to better understand the numbers.

   根據登入使用者的權限，會顯示下列面板：

   * [合作夥伴獨特訪客](../reporting/reports-dashboard.md#partner-uniques)
   * [最大特徵/變更特徵](../reporting/reports-dashboard.md#largest-traits)
   * [最大區段/變更的區段](../reporting/reports-dashboard.md#most-changed-segments)

3. *Optional* click **[!UICONTROL Normalize]** above any graphic to show all the data of the dame scale.您也可以將滑鼠指標暫留在任何資料點上，以查看更多資訊。

## Partner Uniques {#partner-uniques}

Permission Required to View: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

此面板會顯示指定時間範圍內的獨特訪客數量。個別、顏色編碼線條代表使用演算法、規則型和已登錄特徵擷取的獨特訪客總數和獨特訪客數量。

>[!NOTE]
>
>獨特訪客的總數代表透過規則型或已登錄特性擷取的訪客。不過，獨特訪客的總數不等於使用規則型和已登錄特性擷取的獨特訪客總和。同一個獨特使用者可在這兩種特徵類型中呈現。

## Largest Traits/Most Changed Traits {#largest-traits}

Permission Required to View: [!UICONTROL View Traits].

![](assets/largest_traits.png)

此面板顯示不同特性擷取的獨特訪客數量。

Use the **[!UICONTROL Show]** drop-down list to display information about different types of traits: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded], or [!UICONTROL Rule-Based].

此面板包含下列標籤：

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 定位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最大特徵</span> </p> </td> 
   <td colname="col2"> <p>顯示依數字排序的獨特訪客數目(最高到最低)，並列出指定時間範圍內獨特訪客的增量變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最常變更的特徵</span> </p> </td> 
   <td colname="col2"> <p>顯示由delta變更排序的獨特訪客數目相關資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Largest Segments/Most Changed Segments {#most-changed-segments}

Permission Required to View: [!UICONTROL View Segments].

![](assets/largest_segments.png)

此面板會顯示不同區段所擷取的獨特訪客數。

此面板包含下列標籤：

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 定位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最大區段</span> </p> </td> 
   <td colname="col2"> <p>顯示指定時間範圍內獨特訪客人數和獨特訪客的增量變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 已變更的區段</span> </p> </td> 
   <td colname="col2"> <p>顯示由delta變更排序的獨特訪客數目相關資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

