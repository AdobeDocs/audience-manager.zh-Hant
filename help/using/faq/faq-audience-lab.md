---
description: 關於Audience Lab功能的常見問題。
seo-description: 關於Audience Lab功能的常見問題。
seo-title: Audience Lab常見問題
solution: Audience Manager
title: Audience Lab常見問題
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6 d45 d566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab FAQ{#audience-lab-faq}

關於Audience Lab功能的常見問題。

<!-- 

audience-lab-faq.xml

 -->

<br> 

**測試群組中建立的測試區段是否有不同區段ID？How do I map the IDs to different destinations?**

是的，測試區段有不同的區段ID。For destinations with [!UICONTROL Auto-fill Destination Mapping] or segments sent to [!DNL Google], [!UICONTROL Audience Lab] will handle the mapping values just like the destinations normally would.

<br> 

**相同的轉換特徵是否可與多個測試群組相關聯？**

可以，這是允許的。假設使用與轉換X關聯的男性區段以及使用與轉換X關聯的陰性區段進行一項測試的單一測試案例。這兩項測試在測試兩個不同受眾後，並不重要。

<br> 

**假設測試群組對測試區段分割使用驗證的設定檔。The authenticated profile is linked to 4[Audience Manager UUIDs](../reference/ids-in-aam.md). When the visitor exhibits a conversion trait from one of the four UUIDs, does[!UICONTROL Audience Lab]count this as one or four conversions?**

In this case, [!UICONTROL Audience Lab] only counts one conversion.

<br> 

**如果前述案例的訪客從連結到其驗證的描述檔的四個UUID中顯示轉換特徵，然後又顯示兩個連結至已驗證之描述檔的UUID的轉換特徵，該怎麼辦？Does this case count as one or three conversions?**

In this case, [!UICONTROL Audience Lab] counts three conversions, one for each device that has exhibited the authentication trait.

<br> 

**使用者可以[!UICONTROL Segment: Read-Only]存取存取權，還是[!UICONTROL Audience Lab]測試區段建立存取權？**

See [Create Segment Test Group](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) for information on how to use [!UICONTROL Audience Lab] with [!UICONTROL RBAC] privileges.

**我可以[!UICONTROL Audience Lab]與[!UICONTROL Profile Link Device Graph]和外部裝置圖形搭配使用([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html)、Tapad裝置圖形、Liveramp裝置圖表)嗎？**

For now, [!UICONTROL Audience Lab] can only split out segment populations by the devices connected to a qualifying device, when using the [!UICONTROL Profile Link Device Graph]. We are working on adding support in [!UICONTROL Audience Lab] for the other device graphs and will let you know when we do so.
