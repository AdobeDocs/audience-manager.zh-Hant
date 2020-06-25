---
description: 使用「儀表板」可檢視在指定時間範圍內依特徵類型和區段劃分之合作夥伴獨特訪客計數的相關資訊。
seo-description: 使用「儀表板」可檢視在指定時間範圍內依特徵類型和區段劃分之合作夥伴獨特訪客計數的相關資訊。
seo-title: 報表控制面板
solution: Audience Manager
title: 報表控制面板
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---


# 報表控制面板 {#reports-dashboard}

使用「控制面板」可檢視特定時段內，依特徵類型和區段劃分的獨特訪客計數的相關資訊。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])將使用者群組權限延伸至 [!UICONTROL Dashboard]。 使用者只能在控制面板上看到他們有權檢視的資訊。 [!UICONTROL RBAC] 功能可讓您控制內部團隊可檢視的報表資料。

例如，管理不同廣告商帳戶的代理商可以設定使用者群組權限，讓管理廣告商A帳戶的團隊看不到廣告商B的報告資料。 此控制面板可用來疑難排解資料傳送問題。

例如，若您發現獨特使用者總數中出現下降或尖峰，並劃分了獨特使用者類型（規則型與已登入型），您就有更好的起點來追蹤潛在的資料傳送問題。 如果您發現獨特使用者總數和已登入的獨特使用者數量有所下降，您可前往報表 [!UICONTROL On-boarding Status] ，查看傳入檔案是否有問題。

**若要存取控制面板：**

1. 在頂端導覽功能表中，按一下 **[!UICONTROL Dashboard]**。
2. *可選* ：從下拉式清單(7天、14天（預設值）、30天或60天)中，選取上次報告日期的所需時間範圍。

   視選取的時段而定，「 >」和「 [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits][!UICONTROL Largest Segments][!UICONTROL Most Changed Segments] 」面板中的「增量」變更，會顯示觀眾中獨特訪客在今天結束的時段與相同長度的前一時段之間的變更。 例如，如果您選取「7天」,Delta會比較結束於今天的前7天內的獨特訪客與結束於七天前7天內的獨特訪客。

   >[!NOTE]
   >
   >您可以執行報表來調查Delta變更，這似乎不常 [!UICONTROL Trend] 見。 例如，如果您在過去七天中看到異常大的Delta變更，則可執行過去14天(2 x 7)的 [!UICONTROL Trend] 報表，以更好地瞭解數字。

   根據登入使用者的權限，會顯示下列面板：

   * [合作夥伴獨特客戶](../reporting/reports-dashboard.md#partner-uniques)
   * [最大特徵／最大變更特徵](../reporting/reports-dashboard.md#largest-traits)
   * [最大區段／變更最多的區段](../reporting/reports-dashboard.md#most-changed-segments)

3. *可選* ：按一 **[!UICONTROL Normalize]** 下任何圖形上方，以顯示相同比例的所有資料。 您也可以將滑鼠移至任何資料點，以檢視更多資訊。

## 合作夥伴獨特客戶 {#partner-uniques}

檢視所需權限： [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

此面板會顯示指定時段內的獨特訪客數。 個別的色彩編碼行代表使用演算法、規則型和已登入特徵所擷取的獨特訪客總數和數目。

>[!NOTE]
>
>獨特訪客的總數代表透過規則型或已登入特徵所擷取的訪客。 不過，獨特訪客的總數不等於使用規則型和已登入特徵所擷取的獨特訪客總數。 這兩個特徵類型中的任一種可能代表相同的唯一使用者。

## 最大特徵／最大變更特徵 {#largest-traits}

檢視所需權限： [!UICONTROL View Traits].

![](assets/largest_traits.png)

此面板會顯示各種特徵所擷取的獨特訪客數量。

使用下 **[!UICONTROL Show]** 拉式清單來顯示不同類型特徵的相關資訊： [!UICONTROL All Traits]、 [!UICONTROL Algorithmic]、 [!UICONTROL Onboarded]或 [!UICONTROL Rule-Based]。

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
   <td colname="col2"> <p>顯示依數字排序（最高到最低）的獨特訪客數量的相關資訊，並列出指定時段內獨特訪客的增量變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最常變更的特徵</span> </p> </td> 
   <td colname="col2"> <p>顯示依增量變更排序的獨特訪客數量的相關資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最大區段／變更最多的區段 {#most-changed-segments}

檢視所需權限： [!UICONTROL View Segments].

![](assets/largest_segments.png)

此面板會即時顯示不同區段所擷取的獨特訪客數量。

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
   <td colname="col2"> <p>顯示指定時段內獨特訪客的數量和獨特訪客的增量變化的相關資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 變更最多的區段</span> </p> </td> 
   <td colname="col2"> <p>顯示依增量變更排序的獨特訪客數量的相關資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

