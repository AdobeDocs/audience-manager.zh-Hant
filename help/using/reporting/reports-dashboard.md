---
description: 使用儀表板可查看有關合作夥伴在指定時間範圍內按特性類型和段細分的唯一訪問者計數的資訊。
seo-description: Use the Dashboard to view information about your partners' unique visitor counts broken down by trait types and segments for a specified time frame.
seo-title: Reports Dashboard
solution: Audience Manager
title: 報表控制面板
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# 報表控制面板 {#reports-dashboard}

使用「儀表板」可查看有關指定時間範圍內按特性類型和段細分的唯一訪問者計數的資訊。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])將用戶組權限擴展到 [!UICONTROL Dashboard]。 用戶只能查看儀表板上他們有權查看的資訊。 [!UICONTROL RBAC] 功能允許您控制內部團隊可以查看的報告資料。

例如，管理不同廣告商帳戶的代理可以配置用戶組權限，以便管理廣告商A帳戶的團隊無法查看廣告商B的報告資料。 此儀表板可用於排除資料傳遞問題。

例如，如果您注意到具有唯一用戶類型（基於規則與已裝載）的分類的唯一用戶總數中出現「下降」或「高峰」，則您有一個更好的起點來跟蹤潛在的資料傳遞問題。 如果您注意到唯一用戶總數和已登入的唯一用戶數量有所下降，則可以轉到 [!UICONTROL On-boarding Status] 報告以查看入站檔案是否有問題。

**要訪問儀表板：**

1. 在頂部導航菜單中，按一下 **[!UICONTROL Dashboard]**。
2. *可選* 從下拉清單(7天、14天（預設值）、30天或60天)中選擇上次報告日期的所需時間範圍。

   根據所選期間， [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] 和 [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] 面板顯示在截至今天的時段與相同長度的前一時段的受眾中唯一訪問者的變化。 例如，如果選擇7天，則增量將比較截止到今天的前七天內的唯一訪問者與截止到七天前的七天內的唯一訪問者。

   >[!NOTE]
   >
   >通過運行 [!UICONTROL Trend] 報告。 例如，如果您在過去七天內看到異常大的增量更改，則可以運行 [!UICONTROL Trend] 報告過去14天(2 x 7)以更好地瞭解數字。

   根據登錄用戶的權限，將顯示以下面板：

   * [合作夥伴Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [最大特徵/最改變的特徵](../reporting/reports-dashboard.md#largest-traits)
   * [最大段/更改最多的段](../reporting/reports-dashboard.md#most-changed-segments)

3. *可選* 按一下 **[!UICONTROL Normalize]** 顯示所有相同比例的資料。 您還可以將滑鼠指針置於任何資料點上以查看詳細資訊。

## 合作夥伴Uniques {#partner-uniques}

查看所需權限： [!UICONTROL View All Traits]。

![](assets/partner_uniques.png)

此面板顯示指定時間範圍內的唯一訪問者數。 顏色編碼的單個線條表示使用算法、基於規則和附件特徵捕獲的唯一訪問者總數和數量。

>[!NOTE]
>
>唯一訪問者總數表示通過基於規則或已登入的特徵捕獲的訪問者。 但是，唯一訪問者總數不等於使用基於規則和已登入的特徵捕獲的唯一訪問者總數。 這兩種特性類型中的任意一種都可能代表同一唯一用戶。

## 最大特徵/最改變的特徵 {#largest-traits}

查看所需權限： [!UICONTROL View Traits]。

![](assets/largest_traits.png)

此面板顯示由各種特徵捕獲的唯一訪問者的數量。

使用 **[!UICONTROL Show]** 下拉清單，顯示有關不同類型特徵的資訊： [!UICONTROL All Traits]。 [!UICONTROL Algorithmic]。 [!UICONTROL Onboarded]或 [!UICONTROL Rule-Based]。

此面板包含以下頁籤：

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
   <td colname="col2"> <p>顯示有關按編號（從最高到最低）排序的唯一訪問者數的資訊，還列出指定時間範圍內唯一訪問者的增量更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最改變的特性</span> </p> </td> 
   <td colname="col2"> <p>顯示有關按增量更改排序的唯一訪問者數的資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最大段/更改最多的段 {#most-changed-segments}

查看所需權限： [!UICONTROL View Segments]。

![](assets/largest_segments.png)

此面板即時顯示各段捕獲的唯一訪問者數。

此面板包含以下頁籤：

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 定位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最大段</span> </p> </td> 
   <td colname="col2"> <p>顯示有關指定時間範圍內唯一訪問者的數量和唯一訪問者的增量更改的資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 更改最多的段</span> </p> </td> 
   <td colname="col2"> <p>顯示有關按增量更改排序的唯一訪問者數的資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>
