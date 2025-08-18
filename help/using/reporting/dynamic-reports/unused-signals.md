---
description: 此報表會傳回在詳細目錄中收集並傳送至Audience Manager的所有未使用資訊的頻率計數。
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: 未使用的訊號報表
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 9c980b8fd5c3cb6ba7b3031726da726ee5caeec6
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---

# 未使用的訊號報表{#unused-signals-report}

此報表會傳回在詳細目錄中收集並傳送至Audience Manager的所有未使用資訊的頻率計數。 若要存取此報表，請瀏覽至&#x200B;**Analytics >對象報表>其他報表>未使用的訊號**。

>[!NOTE]
>
>如果您看到訊息「您沒有對象報表的存取權」，請聯絡您的Audience Manager顧問或客戶服務，為您布建報表。

![未使用訊號報表的熒幕擷圖](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## 概述

訊號是來自您網站的資訊，以[!DNL Audience Manager]索引鍵值配對[ （例如](../../reference/key-value-pairs-explained.md)等）的形式傳入`color=blue, price>100, gender=female`。

未使用的訊號包含您收集但尚未對應至特徵的資料。 [!UICONTROL Unused Signals]報表會依日期、索引鍵、值和頻率計數，在表格中顯示資料。 任何傳入至[!DNL Audience Manager]的未對應訊號（一天內至少100次）都符合[!UICONTROL Unused Signals]報表的資格。

未使用的訊號會儲存45天然後捨棄。 未使用的訊號報表會顯示過去10天的資料。

請檢閱此報表，協助識別可對應至新特徵或現有特徵的孤立訊號。

>[!NOTE]
>
>在搜尋欄位中指定索引鍵或值名稱，將結果限製為特定記錄。

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
   <td colname="col1"> <p><b>確定特徵一致或新增相關值至單一索引鍵</b> </p> </td> 
   <td colname="col2"> <p>檢閱報告，說明特定訊號的不同值變化。 </p> <p>例如，假設您在機碼值組中將「北卡羅來納」州的特徵定義為<code> c_state = North Carolina</code>。 報表可協助您尋找名稱變體，並將這些變體新增至特徵（例如，<code> c_state = North Carolina, NC, N.C., NCarolina</code>）。 或者，您也可以使用報告找出名稱變體，並將這些變體取代為所有網站的統一值。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>建立新特徵</b> </p> </td> 
   <td colname="col2"> <p>檢閱報告，瞭解在特定索引鍵上傳入了哪些新值。 您可能想要根據這些新值建立新的機碼值組。 </p> <p> <p>注意：請每兩週檢查一次報表中是否有頻繁變更的值（例如節目、行銷活動、名人等）。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>尋找未對應的值</b> </p> </td> 
   <td colname="col2"> <p>檢閱數字1的報告。 <span class="wintitle">未使用的訊號</span>報表中的數字1代表null值。 這並不一定是壞事。 這僅表示特定索引鍵沒有關聯的值對應。 當您看到重要變數的許多1個值時，請洽詢您的網站團隊，以確保您的所有頁面都已正確標籤。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最佳實務

執行並檢查[!UICONTROL Unused Signals]報告：

* 建立特徵或更新特徵規則之後。 這有助於確保您的特徵和規則已正確設定。 結果中的數字1表示新特徵可能未正確設定。
* 每兩週或每月。 已排程的檢閱有助於確保特徵對應是最新的。

>[!NOTE]
>
>在報表中搜尋未使用的值時，請考慮以下特性。 以下兩個範例的運算式不同：

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a！=23))
* 這兩個範例都顯示一個特徵，其中包含兩個機碼值組v和a。第一個運算式會轉譯為：特徵包含值為1 [!UICONTROL AND NOT]的索引鍵v和值為23的索引鍵a。 第二個運算式包含值為1 [!UICONTROL AND]的索引鍵v和值為[!UICONTROL NOT EQUAL] 23的索引鍵a。
* 考慮到上述兩種不同的運算式，假設您在[!UICONTROL Unused Signals Report]中搜尋傳遞至索引鍵a的值，其任何值都不是23，則您只能在第一個案例中取得結果，因為索引鍵的值完全未傳送。 在第二個案例中，傳送的值與23不同，因此機碼a不會未使用。

## 大量特徵建立

如果您需要根據從[!UICONTROL Unused Signals]報表取得的資料大量建立許多特徵，請聯絡您的合作夥伴解決方案代表。
