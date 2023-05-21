---
description: 此報表返回在庫存上收集併發送到Audience Manager的所有未使用資訊的頻率計數。
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: 未使用的訊號報表
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 8fd148df6c19a5d8331faf66c671f91686954a77
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 2%

---

# 未使用的訊號報表{#unused-signals-report}

此報表返回在庫存上收集併發送到Audience Manager的所有未使用資訊的頻率計數。 要訪問此報表，請導航到 **分析>受眾報告>其他報告>未使用的信號**。

>[!NOTE]
>
>如果您看到「您無權訪問受眾報告」消息，請與Audience Manager顧問或客戶服務部門聯繫，為您預配此報告。

![未使用信號報告的螢幕快照](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## 概述

信號是從您的網站傳遞到 [!DNL Audience Manager] 格式 [鍵值對](../../reference/key-value-pairs-explained.md) (例如， `color=blue, price>100, gender=female`等)。

未使用的信號由您收集但尚未映射到某個特性的資料組成。 的 [!UICONTROL Unused Signals] 報表按日期、鍵、值和頻率計數顯示表中的資料。 傳入到的任何未映射信號 [!DNL Audience Manager] 一天至少有100次符合 [!UICONTROL Unused Signals] 報告。 未使用的信號被儲存45天，然後丟棄。

查看此報告以幫助識別可映射到新特徵或現有特徵的孤立信號。

>[!NOTE]
>
>在搜索欄位中指定鍵或值名稱，以將結果限制為特定記錄。

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
   <td colname="col1"> <p><b>確保特性一致性或將相關值添加到單個鍵</b> </p> </td> 
   <td colname="col2"> <p>查看報告以考慮特定信號的不同值變化。 </p> <p>例如，假設在鍵值對中定義的州「北卡羅來納州」具有以下特徵： <code> c_state = North Carolina</code>。 該報告可幫助您查找名稱變體，並將其添加到特徵(例如， <code> c_state = North Carolina, NC, N.C., NCarolina</code>)。 或者，您可以通過報告發現名稱變體，並在所有站點上用統一值替換這些變體。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>建立新特徵</b> </p> </td> 
   <td colname="col2"> <p>查看報告以查看在特定鍵上傳遞的新值。 您可能希望基於這些新值建立新的鍵值對。 </p> <p> <p>注：查看報告，瞭解頻繁更改的值（例如，顯示、活動、名人等）。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>查找未映射的值</b> </p> </td> 
   <td colname="col2"> <p>查看數字1的報表。 1中的數字 <span class="wintitle"> 未使用的信號</span> 報表表示空值。 這未必是壞事。 它只是表示特定鍵沒有關聯的值映射。 當您看到某個重要變數的1個值時，請與您的站點團隊進行檢查，以確保正確標籤了所有頁面。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最佳實務

運行並檢查 [!UICONTROL Unused Signals] 報告：

* 在你建立特質或更新特質規則後。 這有助於確保正確設定您的特性和規則。 結果中的數字1表示可能未正確配置新特性。
* 每兩週或每月。 計畫的審閱有助於確保特性映射是最新的。

>[!NOTE]
>
>在報告中搜索未使用的值時，請考慮以下特殊性。 以下兩個示例在表達式上存在差異：

* T(v=1) [!UICONTROL AND NOT] (a=23)
* T(v=1) [!UICONTROL AND] (a)=23))
* 兩個示例都顯示包含兩個鍵值對v和a的特性。第一個表達式轉換為：特徵包含鍵v，值為1 [!UICONTROL AND NOT] 鍵a的值為23。 第二個表達式包含鍵v，其值為1 [!UICONTROL AND] 鍵值為a [!UICONTROL NOT EQUAL] 23.
* 考慮到上面兩個不同的表達式，假設您在 [!UICONTROL Unused Signals Report] 對於在鍵a上傳遞的值，其值與23的任何值都不同，您只會在第一種情況下獲得結果，因為鍵的值未發送AT ALL。 在第二種情況下，發送的值不同於23，因此鍵a不是未使用的。

## 批量特徵建立

如果您需要根據從以下站點獲得的資料批量建立許多特性，請聯繫您的合作夥伴解決方案代表 [!UICONTROL Unused Signals] 報告。
