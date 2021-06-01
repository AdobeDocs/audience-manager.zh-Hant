---
description: 此報表會傳回在您的詳細目錄中收集並傳送至Audience Manager的所有未使用資訊的頻率計數。
seo-description: 此報表會傳回在您的詳細目錄中收集並傳送至Audience Manager的所有未使用資訊的頻率計數。
seo-title: 未使用的訊號報表
solution: Audience Manager
title: 未使用的訊號報表
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: 重疊報表
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 2%

---

# 未使用的訊號報表{#unused-signals-report}

此報表會傳回在您的詳細目錄中收集並傳送至Audience Manager的所有未使用資訊的頻率計數。 若要存取此報表，請導覽至「**Analytics >對象報表>其他報表>未使用的訊號**」。

>[!NOTE]
>
>如果您看見「您無權存取對象報表」訊息，請連絡您的Audience Manager顧問或客戶服務，為您布建報表。

![未使用訊號報表的螢幕擷圖](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## 概述

訊號是從您的網站傳入[!DNL Audience Manager]的資訊，其形式為[索引鍵值配對](../../reference/key-value-pairs-explained.md)（例如`color=blue, price>100, gender=female`等）。

未使用的訊號包含您收集但尚未對應至特徵的資料。 [!UICONTROL Unused Signals]報表依日期、索引鍵、值和頻率計數顯示表格中的資料。 在符合[!UICONTROL Unused Signals]報表資格的一天中，任何未映射的訊號至少傳入[!DNL Audience Manager]100次。

檢閱此報表，協助識別可對應至新特徵或現有特徵的孤立訊號。

>[!NOTE]
>
>在搜尋欄位中指定索引鍵或值名稱，以將結果限制在特定記錄中。

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
   <td colname="col2"> <p>檢閱報表，了解特定訊號的不同值變化。 </p> <p>例如，假設您有州「North Carolina」的特徵，在機碼值組中定義為<code> c_state = North Carolina</code>。 報表可協助您尋找名稱變體，並將其新增至特徵（例如<code> c_state = North Carolina, NC, N.C., NCarolina</code>）。 或者，您也可以從報表中找出名稱變體，並以所有網站上的統一值取代這些變體。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>建立新特徵</b> </p> </td> 
   <td colname="col2"> <p>檢閱報表，查看在特定索引鍵上傳入哪些新值。 您可能想要根據這些新值建立新索引鍵值配對。 </p> <p> <p>注意： 檢查報表每兩週一次，以了解哪些值經常變更（例如，節目、行銷活動、名人等）。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>查找未映射的值</b> </p> </td> 
   <td colname="col2"> <p>查看數字1的報告。 <span class="wintitle">未使用的訊號</span>報表中的數字1代表空值。 這不一定是壞事。 這只是表示特定索引鍵沒有相關聯的值對應。 當您看到重要變數的許多1個值時，請洽詢您的網站團隊，確定所有頁面都已正確加上標籤。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最佳實務

執行並檢查[!UICONTROL Unused Signals]報表：

* 建立特徵或更新特徵規則後。 這有助於確保正確設定您的特徵和規則。 結果中的數字1表示新特徵可能未正確設定。
* 每兩週或每月。 排程的審核有助於確保特徵對應為最新狀態。

>[!NOTE]
>
>在報告中搜索未使用的值時，請考慮以下特殊性。 下列兩個範例在運算式上有差異：

* T(v=1 [!UICONTROL AND NOT](a=23))
* T(v=1 [!UICONTROL AND](a!=23))
* 這兩個範例都顯示一個特徵，其中包含兩個索引鍵值配對v和a。第一個運算式轉換為：特徵包含鍵v，值為1 [!UICONTROL AND NOT]，鍵a為23。 第二個表達式包含鍵v，其值為1 [!UICONTROL AND]，鍵a的值為[!UICONTROL NOT EQUAL] 23。
* 考慮到上述兩個不同的運算式，假設您在[!UICONTROL Unused Signals Report]中搜尋傳入索引鍵a的值（任何值皆不同於23），您只會在第一個案例中取得結果，因為索引鍵的值未「全部」傳送。 在第二種情況下，會傳送不同於23的值，因此鍵值a不會未使用。

## 大量特徵建立

如果您需要根據從[!UICONTROL Unused Signals]報表取得的資料大量建立許多特徵，請連絡您的合作夥伴解決方案代表。
