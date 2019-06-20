---
description: 此程序需要AdWords二次行銷清單、像素代碼和Audience Manager URL目的地。它也稱為搜尋廣告(RLSA)整合的二次行銷清單。僅適用於付費搜尋。
seo-description: 此程序需要AdWords二次行銷清單、像素代碼和Audience Manager URL目的地。它也稱為搜尋廣告(RLSA)整合的二次行銷清單。僅適用於付費搜尋。
seo-title: 將區段傳送至Google AdWords再行銷清單
solution: Audience Manager
title: 將區段傳送至Google AdWords再行銷清單
uuid: 5ad821c6-48b4-42c0-b912-1563331e93 a2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

This procedure requires a [!DNL Google Ads] remarketing list, pixel code, and an Audience Manager [!DNL URL] destination. It is also known as a remarketing list for search ads ([!DNL RLSA]) integration. 僅適用於付費搜尋。

>[!IMPORTANT]
>請注意，這並不是兩個系統的分類整合。

To set up a [!DNL Google Ads] remarketing list as an [!DNL Audience Manager] URL destination:

1. [!DNL Google Ads] 在您的帳戶中 [，建立網站重新行銷清單](https://support.google.com/adwords/answer/2454064?hl=en) 並記下您的轉換ID。
1. 使用下列URL作為基本URL和安全URL的範本。以您的轉換ID取代xxxx xxxx區段。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [Create a URL destination](../../features/destinations/manage-destinations.md#configure-url-destination) or edit an existing destination. 建立目的地時使用下列設定：
   * 類型：URL
   * 序列化：已啓用
   * 分隔字元：分號(；)

1. In the [!UICONTROL Segment Mappings] section of your [!DNL URL] destination, add the code from step 2 to the [!DNL URL] and [!DNL Secure URL] fields. Prefix the code with `http:` and `https:` in the [!DNL URL] and [!DNL Secure URL] fields, respectively.

   >[!IMPORTANT]
   >
   >Replace encoded ampersands `&` with un-encoded ampersands `&`

   Unsecure [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Click **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果您使用多個區段，請針對您要對應至Google廣告目的地的每個區段取得新像素。如此可確保資料套用至適當的再行銷清單。

1. When mapping a new segment to this destination in Audience Manager, define the mapping as `aam=segmentID` and replace `segmentID` with the ID of your segment.
1. When defining a bucket in [!DNL Google Ads], create a rule that matches the mapping defined at step 6.

完成的對應看起來類似於：

![](../assets/rlsa_mapping.png)

>[!MORE_贊_ this]
>
>* [目的地](../../features/destinations/destinations.md)
>* [建立URL目的地](../../features/destinations/manage-destinations.md#configure-url-destination)
>* [關於AdWords重新行銷清單](https://support.google.com/adwords/answer/2472738)
>* [AdWords重新行銷如何運作](https://support.google.com/adwords/answer/2454000)

