---
description: 此程式需要AdWords再行銷清單、像素代碼和Audience Manager URL目標。 它也稱為搜尋廣告(RLSA)整合的再行銷清單。 僅適用於付費搜尋。
seo-description: 此程式需要AdWords再行銷清單、像素代碼和Audience Manager URL目標。 它也稱為搜尋廣告(RLSA)整合的再行銷清單。 僅適用於付費搜尋。
seo-title: 將區段傳送至Google adWords再行銷清單
solution: Audience Manager
title: 將區段傳送至Google adWords再行銷清單
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 傳送區段至Google廣告再行銷清單 {#send-segments-to-a-google-adwords-remarketing-list}

此程式需要重 [!DNL Google Ads] 新行銷清單、像素程式碼和Audience manager目 [!DNL URL] 標。 它也稱為搜尋廣告([!DNL RLSA])整合的再行銷清單。 僅適用於付費搜尋。

>[!IMPORTANT]
>請注意，這並非兩個系統的分類整合。

若要將再行銷 [!DNL Google Ads] 清單設為 [!DNL Audience Manager] URL目的地：

1. 在您的 [!DNL Google Ads] 帳戶中 [建立網站再行銷清單](https://support.google.com/adwords/answer/2454064?hl=en) ，並記下轉換ID。
1. 使用下列URL做為基本URL和安全URL的範本。 將xxxxxxxx區段取代為轉換ID。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience manager中，建 [立URL目標](../../features/destinations/create-url-destination.md) ，或編輯現有目標。 建立目標時，請使用下列設定：
   * 類型：URL
   * 序列化：已啟用
   * 分隔字元：分號(;)

1. 在您目 [!UICONTROL Segment Mappings] 標的區 [!DNL URL] 段中，將步驟2的程式碼新增至 [!DNL URL] 和欄 [!DNL Secure URL] 位。 請分別在和欄 `http:` 位中 `https:` ，將程 [!DNL URL] 式碼加上 [!DNL Secure URL] 和前置。

   >[!IMPORTANT]
   >
   >使用未編碼的 `&` &amp;符號取代編碼的&amp;符號 `&`

   不安全 [!DNL URL] 的代碼：

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   安全 [!DNL URL] 代碼：

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Click **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果您使用多個區段，請為每個要對應至Google Ads目的地的區段取得新像素。 這可確保資料套用至適當的再行銷清單。

1. 在Audience manager中將新區段對應至此目標時，請將對應定義為， `aam=segmentID` 並以 `segmentID` 區段的ID取代。
1. 在中定義貯體時， [!DNL Google Ads]請建立符合步驟6所定義之對應的規則。

完成的對應看起來可能類似：

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [目的地](../../features/destinations/destinations.md)
>* [建立URL目標](../../features/destinations/create-url-destination.md)
>* [關於AdWords再行銷清單](https://support.google.com/adwords/answer/2472738)
>* [AdWords再行銷的運作方式](https://support.google.com/adwords/answer/2454000)

