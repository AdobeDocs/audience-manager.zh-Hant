---
description: 此報表會傳回清單上收集並傳送至Audience Manager的所有未使用資訊的頻率計數。
seo-description: 此報表會傳回清單上收集並傳送至Audience Manager的所有未使用資訊的頻率計數。
seo-title: 未使用的訊號報表
solution: Audience Manager
title: 未使用的訊號報表
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 2%

---


# 未使用的訊號報表{#unused-signals-report}

此報表會傳回清單上收集並傳送至Audience Manager的所有未使用資訊的頻率計數。 若要存取此報表，請導覽至「 **分析>對象報表>其他報表>未使用的信號」**。

>[!NOTE]
>
>如果您看到訊息「您無權存取觀眾報表」，請連絡您的Audience Manager顧問或客戶服務為您布建報表。

![未使用訊號報表的螢幕擷取](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## 概述

信號是您網站以鍵值配對 [!DNL Audience Manager] 形式傳入 [的資訊](../../reference/key-value-pairs-explained.md) (例如 `color=blue, price>100, gender=female`等)。

未使用的信號由您收集但尚未映射至特徵的資料組成。 報 [!UICONTROL Unused Signals] 表會依日期、索引鍵、值和頻率計數顯示表格中的資料。 任何未映射的訊號在一 [!DNL Audience Manager] 天中傳入至少100次，都符合報表的 [!UICONTROL Unused Signals] 資格。

檢閱此報告，協助識別可對應至新特徵或現有特徵的孤立訊號。

>[!NOTE]
>
>在搜尋欄位中指定索引鍵或值名稱，以將結果限制在特定記錄。

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
   <td colname="col1"> <p><b>確保特徵一致性或將相關值新增至單一索引鍵</b> </p> </td> 
   <td colname="col2"> <p>請檢閱報表，以說明特定訊號的不同值變化。 </p> <p>例如，假設您有州「North Carolina」的特徵，該州在鍵值對中定義為 <code> c_state = North Carolina</code>。 報表可協助您尋找名稱變數，並將其新增至特徵(例如 <code> c_state = North Carolina, NC, N.C., NCarolina</code>)。 或者，您也可以利用報表找出名稱變數，並將所有網站的名稱變數取代為統一值。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>建立新特徵</b> </p> </td> 
   <td colname="col2"> <p>檢視報表，查看在特定索引鍵上傳入的新值。 您可能想要根據這些新值建立新的索引鍵值配對。 </p> <p> <p>注意：  每兩週檢查報表中是否有經常變更的值（例如，顯示、促銷活動、名人等）。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>查找未映射值</b> </p> </td> 
   <td colname="col2"> <p>檢視數字1的報表。 「未使用的信號」報 <span class="wintitle"> 表中的數字</span> 1代表空值。 這未必是壞事。 它只是表示特定索引鍵沒有關聯的值映射。 當您看到重要變數的許多1個值時，請洽詢您的網站團隊，以確定所有頁面都已正確標籤。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最佳實務

執行並檢查報 [!UICONTROL Unused Signals] 表：

* 建立特徵或更新特徵規則後。 這有助於確保您的特徵和規則已正確設定。 結果中的數字1表示新特徵可能未正確設定。
* 雙週或每月。 排程的審核有助於確保特徵映射是最新的。

>[!NOTE]
>
>在報告中搜索未使用的值時，請考慮以下特殊性。 以下兩個範例在運算式上有所不同：

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* 兩個範例都顯示包含兩個索引鍵值對v和a的特徵。 第一個表達式可轉換為： 特徵包含鍵v，值為1, [!UICONTROL AND NOT] 鍵a，值為23。 第二個表達式包含鍵v，其值為1, [!UICONTROL AND] 鍵a為23 [!UICONTROL NOT EQUAL] 。
* 考慮到上述兩個不同的運算式，假設您在中搜尋傳入索引鍵a的值（其值與23不同），您只會在第一種情況下取得結果，因為索引鍵的值未傳送AT ALL。 [!UICONTROL Unused Signals Report] 在第二種情況下，會傳送不同於23的值，因此鍵a不會未使用。

## 大量特徵建立

如果您需要根據從報表取得的資料大量建立許多特性，請連絡您的合作夥伴解決方案 [!UICONTROL Unused Signals] 代表。
