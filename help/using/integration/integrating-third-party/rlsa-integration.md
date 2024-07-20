---
description: 此程式需要AdWords再行銷清單、畫素代碼和Audience ManagerURL目的地。 這也稱為搜尋廣告(RLSA)整合的再行銷清單。 僅適用於付費搜尋。
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: 將區段傳送至Google AdWords再行銷清單
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# 將區段傳送至Google Ads再行銷清單 {#send-segments-to-a-google-adwords-remarketing-list}

此程式需要[!DNL Google Ads]再行銷清單、畫素代碼和Audience Manager[!DNL URL] [!DNL destination]。 也稱為搜尋廣告([!DNL RLSA])整合的再行銷清單。 僅適用於付費搜尋。

>[!IMPORTANT]
>請注意，這並非兩個系統的產品化整合。

若要將[!DNL Google Ads]再行銷清單設定為[!DNL Audience Manager] [!DNL URL destination]：

1. 在您的[!DNL Google Ads]帳戶中，[建立網站再行銷清單](https://support.google.com/tagmanager/answer/6106960?hl=en)，並寫下您的轉換ID。
1. 使用下列URL作為基礎URL和安全URL的範本。 將xxxxxxxxxx區段取代為您的轉換ID。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience Manager中，[建立 [!DNL URL destination]](../../features/destinations/create-url-destination.md)或編輯現有的[!DNL destination]。 建立[!DNL destination]時，請使用下列設定：
   * 型別： URL
   * 序列化：已啟用
   * 分隔符號：分號（ &amp;amp；分號； ）

1. 在[!DNL URL] [!DNL destination]的[!UICONTROL Segment Mappings]區段中，將步驟2中的程式碼新增至[!DNL URL]和[!DNL Secure URL]欄位。 在[!DNL URL]和[!DNL Secure URL]欄位中分別以`http:`和`https:`作為程式碼的前置詞。

   >[!IMPORTANT]
   >
   >以未編碼的&amp;符號`&`取代已編碼的&amp;符號`&`

   不安全的[!DNL URL]程式碼：

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   安全[!DNL URL]程式碼：

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 按一下 **[!UICONTROL Save]**。

   >[!NOTE]
   >
   >如果您使用多個區段，請為每個要對應至[!DNL Google Ads] [!DNL destination]的區段取得新畫素。 這可確保資料套用至適當的再行銷清單。

1. 在Audience Manager中將新區段對應到此[!DNL destination]時，請將對應定義為`aam=segmentID`並將`segmentID`取代為您的區段識別碼。
1. 在[!DNL Google Ads]中定義貯體時，請建立符合步驟6中定義的對應的規則。

完成的對應看起來可能類似這樣：

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [建立 [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [關於AdWords再行銷清單](https://support.google.com/adwords/answer/2472738)
>* [AdWords再行銷的運作方式](https://support.google.com/adwords/answer/2454000)
