---
description: 關於 Audience Lab 功能的常見問題。
seo-description: Frequently asked questions about the Audience Lab feature.
seo-title: Audience Lab FAQ
solution: Audience Manager
title: Audience Lab 常見問題集
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
exl-id: 25bdabb5-2ba8-45d2-81ca-05c0590d7d96
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 94%

---

# Audience Lab 常見問題集{#audience-lab-faq}

關於 Audience Lab 功能的常見問題。

<br> 

**在測試群組中建立的測試區段是否有不同的區段 ID？如何將這些 ID 對應至不同的目的地？**

是的，測試區段有不同的區段 ID。對於具有 [!UICONTROL Auto-fill Destination Mapping] 的目的地或已傳送至 [!DNL Google] 的區段，[!UICONTROL Audience Lab] 處理對應值的方式就像一般的目的地一樣。

<br> 

**相同的轉換特徵可以與多個測試群組相關聯嗎？**

可以，這是允許的情況。假設在某個案例中，一個測試使用與轉換 X 相關聯的男性細分群體，而另一個測試使用與轉換 X 相關聯的女性細分群體。這兩個測試都會促進轉換，因為它們測試的是兩個不同的客群。

<br> 

**假設測試群組使用已驗證的設定檔來分割測試區段。已驗證的設定檔連結至 4 個 [Audience Manager UUID](../reference/ids-in-aam.md)。如果訪客展現來自四個 UUID 其中之一的轉換特徵，[!UICONTROL Audience Lab] 會將此轉換計為一次轉換還是四次轉換？**

在此情況下，[!UICONTROL Audience Lab] 只會計為一次轉換。

<br> 

**如果上述案例的訪客先展現來自四個 UUID (連結至其已驗證的設定檔) 之一的轉換特徵，接著又展現另外兩個 UUID (連結至其已驗證的設定檔) 的轉換特徵，又會怎麼計算？此案例會計為一次還是三次轉換？**

在此案例中，[!UICONTROL Audience Lab] 會計為 3 次轉換，每個展現驗證特徵的裝置各算一次。

<br> 

**使用者是否可擁有 [!UICONTROL Segment: Read-Only] 存取權，同時也擁有 [!UICONTROL Audience Lab] 測試區段的建立存取權？**

如需如何透過 [!UICONTROL RBAC] 權限使用 [!UICONTROL Audience Lab] 的詳細資訊，請參閱[建立區段測試群組](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)。

**我可以將[!UICONTROL Audience Lab]與[!UICONTROL Profile Link Device Graph]和外部裝置圖形（ Tapad裝置圖形、Liveramp裝置圖形）結合使用嗎？**

目前，使用 [!UICONTROL Profile Link Device Graph] 時，[!UICONTROL Audience Lab] 只能依連接至合格裝置的裝置來分割區段母體。我們正致力在 [!UICONTROL Audience Lab] 中增加對其他裝置圖表的支援，將會在提供支援時通知您。
