---
description: 此程序需要AdWords二次行銷清單、像素代碼和Audience Manager URL目的地。它也稱為搜尋廣告(RLSA)整合的二次行銷清單。僅適用於付費搜尋。
seo-description: 此程序需要AdWords二次行銷清單、像素代碼和Audience Manager URL目的地。它也稱為搜尋廣告(RLSA)整合的二次行銷清單。僅適用於付費搜尋。
seo-title: 將區段傳送至Google AdWords再行銷清單
solution: Audience Manager
title: 將區段傳送至Google AdWords再行銷清單
uuid: 5ad821c6-48b4-42c0-b912-1563331e93 a2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# 將區段傳送至Google廣告再行銷清單 {#send-segments-to-a-google-adwords-remarketing-list}

此程序需要 [!DNL Google Ads] 重新行銷清單、像素代碼和Audience Manager [!DNL URL] 目的地。它也稱為搜尋廣告([!DNL RLSA])整合的再行銷清單。僅適用於付費搜尋。

>[!IMPORTANT]
>請注意，這並不是兩個系統的分類整合。

若要設定 [!DNL Google Ads] 再行銷清單作為 [!DNL Audience Manager] URL目的地：

1. [!DNL Google Ads] 在您的帳戶中 [，建立網站重新行銷清單](https://support.google.com/adwords/answer/2454064?hl=en) 並記下您的轉換ID。
1. 使用下列URL作為基本URL和安全URL的範本。以您的轉換ID取代xxxx xxxx區段。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience Manager中 [，建立URL目的地](../../features/destinations/create-url-destination.md) 或編輯現有目的地。建立目的地時使用下列設定：
   * 類型：URL
   * 序列化：已啓用
   * 分隔字元：分號(；)

1. 在目的地 [!UICONTROL Segment Mappings] 的區段 [!DNL URL] 中，將程式碼從步驟新增至 [!DNL URL] 和 [!DNL Secure URL] 欄位。分別在 `http:``https:`[!DNL URL][!DNL Secure URL] 和欄位中加上程式碼。

   >[!IMPORTANT]
   >
   >使用未編碼的&amp;符號取代編碼的符號 `&``&`

   不安全 [!DNL URL] 的程式碼：

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   安全 [!DNL URL] 程式碼：

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Click **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果您使用多個區段，請針對您要對應至Google廣告目的地的每個區段取得新像素。如此可確保資料套用至適當的再行銷清單。

1. 在Audience Manager中將新區段對應至此目的地時，請定義對應並 `aam=segmentID``segmentID` 以區段ID取代。
1. 定義儲存貯體時 [!DNL Google Ads]，請建立符合步驟所定義對應的規則。

完成的對應看起來類似於：

![](../assets/rlsa_mapping.png)

>[!MORE_贊_ this]
>
>* [目的地](../../features/destinations/destinations.md)
>* [建立URL目的地](../../features/destinations/create-url-destination.md)
>* [關於AdWords重新行銷清單](https://support.google.com/adwords/answer/2472738)
>* [AdWords重新行銷如何運作](https://support.google.com/adwords/answer/2454000)

