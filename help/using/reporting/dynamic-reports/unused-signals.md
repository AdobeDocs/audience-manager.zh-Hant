---
description: 此報表會傳回庫存上所有未使用資訊的頻率計數，並傳送至Audience Manager。
seo-description: 此報表會傳回庫存上所有未使用資訊的頻率計數，並傳送至Audience Manager。
seo-title: 未使用的訊號報表
solution: Audience Manager
title: 未使用的訊號報表
uuid: 04334a5c-3e21-44db-b971-0b4457685 e9 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Unused Signals Report{#unused-signals-report}

此報表會傳回庫存上所有未使用資訊的頻率計數，並傳送至Audience Manager。

<!-- 

c_unused_signals.xml

 -->

## 未使用的訊號報表

A signal is information from your website passed in to [!DNL Audience Manager] in the form of [key-value pairs](../../reference/key-value-pairs-explained.md) (e.g., `color=blue, price>100, gender=female`, etc.).

未使用的訊號包含您收集但尚未對應至特徵的資料。[!UICONTROL Unused Signals] 報表會依據日期、索引鍵、值和頻率計數，顯示表格中的資料。Any unmapped signal passed in to [!DNL Audience Manager] at least 100 times in a day qualifies for the [!UICONTROL Unused Signals] report.

檢閱此報告有助於識別可對應至新特性或現有特徵的孤立訊號。

>[!NOTE]
>
>在搜尋欄位中指定索引鍵或值名稱，以限制結果至特定記錄。

## 使用個案

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 範例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>確保特徵一致性或新增相關值至單一索引鍵</b> </p> </td> 
   <td colname="col2"> <p>檢閱報表以考慮特定訊號的不同值變化。 </p> <p>For example, say you have a trait for the state "North Carolina" defined in a key-value pair as <code> c_state = North Carolina</code>. The report can help you find name variants and add those to the trait (e.g., <code> c_state = North Carolina, NC, N.C., NCarolina</code>). 或者，您可以使用報表識別名稱變數，並取代所有網站上具有統一值的變數。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>建立新特性</b> </p> </td> 
   <td colname="col2"> <p>檢閱報表，查看傳入特定索引鍵的新值。您可能想要根據這些新值建立新的索引鍵值配對。 </p> <p> <p>注意：針對經常變更的值檢查報表BI每周(例如，顯示、促銷活動、名人等)。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>尋找未對應的值</b> </p> </td> 
   <td colname="col2"> <p>檢閱第一個報表的報表。<span class="wintitle"> 「未使用的訊號」</span> 報表中的數字代表空值。這不一定壞事。這只是表示特定索引鍵沒有相關聯的值對應。當您看到重要變數的多個值時，請洽詢您的網站團隊以確定所有頁面都已正確標記。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最佳實務

Run and check the [!UICONTROL Unused Signals] report:

* 建立特徵或更新特徵規則後。這有助於確保正確設定特徵和規則。結果中的第1表示新特徵無法正確設定。
* 每周或每月。排程審核有助於確保特徵映射保持最新。

>[!NOTE]
>
>在報表中搜尋未使用的值時，請考慮下列特殊性。下列兩個範例之間的運算式有差異：

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Both examples show a trait which contains two key-value pairs v and a. The first expression translates into: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. The second expression contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23.
* Considering the two different expressions above, let&#39;s say you search in the [!UICONTROL Unused Signals Report] for the values that get passed on key a with any value different than 23, you&#39;ll only obtain results in the first case because values for key were not sent AT ALL. 在第二種情況下，會傳送與23不同的值，因此不會未使用索引鍵。

## 大量特徵建立

Contact your Partner Solutions representative if you need to bulk create a lot of traits based on data obtained from the [!UICONTROL Unused Signals] report.
