---
description: 有關Audience Lab功能的常見問題。
seo-description: 有關Audience Lab功能的常見問題。
seo-title: Audience Lab常見問答集
solution: Audience Manager
title: Audience Lab常見問答集
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Audience Lab常見問答集{#audience-lab-faq}

有關Audience Lab功能的常見問題。

<!-- 

audience-lab-faq.xml

 -->

<br> 

**在測試群組中建立的測試區段是否有不同的區段ID? 如何將ID對應至不同的目的地？**

是的，測試區段有不同的區段ID。 對於已傳送 [!UICONTROL Auto-fill Destination Mapping] 至或區段的目 [!DNL Google]的地， [!UICONTROL Audience Lab] 將會處理對應值，就像一般的目的地一樣。

<br> 

**相同的轉換特徵是否與多個測試群組相關聯？**

是的，允許。 假設一個測試使用與轉換X相關聯的公分段，另一個測試使用與轉換X相關聯的母分段。 這兩個測試都會推動轉化，因為它們會測試兩個不同的受眾。

<br> 

**假設測試群組使用已驗證的設定檔來分割測試區段。 已驗證的設定檔會連結至4[個Audience Manager UUID](../reference/ids-in-aam.md)。 當訪客顯示來自四個UUID之一的轉換特徵時，這[!UICONTROL Audience Lab]會算作一或四個轉換嗎？**

在此情況下，只 [!UICONTROL Audience Lab] 計算一次轉換。

<br> 

**如果上述案例的訪客先顯示連結至其已驗證描述檔的4個UUID之一的轉換特徵，接著又顯示連結至已驗證描述檔的2個UUID的轉換特徵，該怎麼辦？ 此案例是否計為一或三次轉換？**

在此例中，計 [!UICONTROL Audience Lab] 算3個轉換，每個具有驗證特性的裝置各計算一個。

<br> 

**使用者是否可[!UICONTROL Segment: Read-Only]以存取，但也可以測[!UICONTROL Audience Lab]試區段建立存取權？**

如需 [如何使用權限的詳細資訊](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) ，請參閱建立 [!UICONTROL Audience Lab] 區段測試 [!UICONTROL RBAC] 群組。

**我是否可[!UICONTROL Audience Lab]以搭配使用[!UICONTROL Profile Link Device Graph]外部和外部裝置圖形([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html)、Tapad Device Graph、Liveramp Device Graph)?**

目前，使 [!UICONTROL Audience Lab] 用時，只能依連接至合格裝置的裝置來劃分區段人口族群 [!UICONTROL Profile Link Device Graph]。 我們正致力於在其他裝置圖 [!UICONTROL Audience Lab] 形中增加支援，並會在我們提供支援時通知您。
