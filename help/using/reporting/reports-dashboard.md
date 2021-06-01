---
description: 使用控制面板來檢視關於您的合作夥伴獨特訪客計數的資訊，這些訪客計數會依特徵類型和特定時段的區段來劃分。
seo-description: 使用控制面板來檢視關於您的合作夥伴獨特訪客計數的資訊，這些訪客計數會依特徵類型和特定時段的區段來劃分。
seo-title: 報表控制面板
solution: Audience Manager
title: 報表控制面板
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: 報表參考
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# 報表控制面板 {#reports-dashboard}

使用控制面板檢視特定時間範圍內依特徵類型和區段劃分的獨特訪客計數的相關資訊。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] 使 [!UICONTROL Role Based Access Control] 用([!UICONTROL RBAC])將使用者群組權限擴充至 [!UICONTROL Dashboard]。使用者只能在控制面板上看到他們有權檢視的資訊。 [!UICONTROL RBAC] 功能可讓您控制內部團隊可檢視的報表資料。

例如，管理不同廣告商帳戶的代理可設定使用者群組權限，讓管理廣告商A帳戶的團隊看不到廣告商B的報表資料。 此控制面板可用來疑難排解資料傳送問題。

例如，若您發現不重複使用者總數中出現下降或尖峰，且劃分了不重複使用者類型（規則型與已上線），您便有更好的起點來追蹤潛在的資料傳送問題。 如果您發現不重複使用者總數和已上線的不重複使用者數目減少，您可以前往[!UICONTROL On-boarding Status]報表，查看傳入檔案是否有問題。

**若要存取控制面板：**

1. 在頂端導覽功能表中，按一下&#x200B;**[!UICONTROL Dashboard]**。
2. ** 可選從下拉式清單(7天、14天（預設值）、30天或60天)中，選取上次報表日期所需的時間範圍。

   根據選取的期間，[!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits]和[!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments]面板中的差異變更會顯示在對象中，不重複訪客在今天結束的期間與相同長度的先前期間中的變化。 例如，如果您選取7天，差值會將結束今天的前7天內的獨特訪客與結束於7天前的7天內的獨特訪客進行比較。

   >[!NOTE]
   >
   >您可以執行[!UICONTROL Trend]報表，以調查異常的差異變更。 例如，如果您在過去七天內看到異常大的差異變更，則可執行過去14天(2 x 7)的[!UICONTROL Trend]報表，以便更清楚了解數字。

   下列面板會依登入使用者的權限而顯示：

   * [合作夥伴不重複值](../reporting/reports-dashboard.md#partner-uniques)
   * [最大特徵/變更最多的特徵](../reporting/reports-dashboard.md#largest-traits)
   * [最大區段/變更最多的區段](../reporting/reports-dashboard.md#most-changed-segments)

3. ** 選用 **[!UICONTROL Normalize]** 按一下任何圖形的上方，以顯示相同比例的所有資料。您也可以將滑鼠移至任何資料點上方，以查看詳細資訊。

## 合作夥伴唯一值{#partner-uniques}

需要的查看權限：[!UICONTROL View All Traits]。

![](assets/partner_uniques.png)

此面板會顯示指定時間範圍內的不重複訪客數量。 個別的色彩編碼行代表獨特訪客的總數，以及使用演算法、規則型和已上線特徵擷取的不重複訪客的數量。

>[!NOTE]
>
>不重複訪客的總數代表透過規則型或已上線特徵擷取的訪客。 不過，不重複訪客的總數不等於使用規則型和已上線特徵所擷取的不重複訪客總數。 這兩個特徵類型中，可能會呈現相同的不重複使用者。

## 最大特徵/最大變更特徵{#largest-traits}

需要的查看權限：[!UICONTROL View Traits]。

![](assets/largest_traits.png)

此面板會顯示各種特徵所擷取的不重複訪客數量。

使用&#x200B;**[!UICONTROL Show]**&#x200B;下拉式清單來顯示不同特徵類型的相關資訊：[!UICONTROL All Traits]、[!UICONTROL Algorithmic]、[!UICONTROL Onboarded]或[!UICONTROL Rule-Based]。

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
   <td colname="col2"> <p>顯示依編號（最高至最低）排序的不重複訪客數量的相關資訊，並列出指定時間範圍內不重複訪客的差異變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 變更最多的特徵</span> </p> </td> 
   <td colname="col2"> <p>顯示依差異變更排序的不重複訪客數量的相關資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最大區段/變更最多的區段{#most-changed-segments}

需要的查看權限：[!UICONTROL View Segments]。

![](assets/largest_segments.png)

此面板會即時顯示各區段擷取的不重複訪客數量。

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
   <td colname="col2"> <p>顯示指定時間範圍內獨特訪客的數量和獨特訪客的差異變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 變更次數最多的區段</span> </p> </td> 
   <td colname="col2"> <p>顯示依差異變更排序的不重複訪客數量的相關資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>
