---
description: 此程式需要AdWords再行銷清單、像素代碼和Audience ManagerURL目標。 它也稱為搜尋廣告(RLSA)整合的再行銷清單。 僅適用於付費搜尋。
seo-description: 此程式需要AdWords再行銷清單、像素代碼和Audience ManagerURL目標。 它也稱為搜尋廣告(RLSA)整合的再行銷清單。 僅適用於付費搜尋。
seo-title: 將區段傳送至 Google AdWords 再行銷清單
solution: Audience Manager
title: 將區段傳送至 Google AdWords 再行銷清單
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: 協力廠商整合
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 5%

---

# 傳送區段至Google廣告再行銷清單{#send-segments-to-a-google-adwords-remarketing-list}

此程式需要[!DNL Google Ads]重新行銷清單、像素代碼和Audience Manager[!DNL URL] [!DNL destination]。 它也稱為搜尋廣告([!DNL RLSA])整合的再行銷清單。 僅適用於付費搜尋。

>[!IMPORTANT]
>請注意，這並非兩個系統的分類整合。

要將[!DNL Google Ads]再行銷清單設定為[!DNL Audience Manager] [!DNL URL destination]，請執行以下操作：

1. 在您的[!DNL Google Ads]帳戶中，[建立網站重新行銷清單](https://support.google.com/adwords/answer/2454064?hl=en)並記下轉換ID。
1. 使用下列URL做為基本URL和安全URL的範本。 將xxxxxxxx區段取代為轉換ID。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience Manager中，[建立 [!DNL URL destination]](../../features/destinations/create-url-destination.md)或編輯現有[!DNL destination]。 建立[!DNL destination]時，請使用以下設定：
   * 類型：URL
   * 序列化：已啟用
   * 分隔字元：分號(;)

1. 在[!DNL URL] [!DNL destination]的[!UICONTROL Segment Mappings]區段中，將步驟2的程式碼新增至[!DNL URL]和[!DNL Secure URL]欄位。 在[!DNL URL]和[!DNL Secure URL]欄位中，分別將程式碼加上`http:`和`https:`。

   >[!IMPORTANT]
   >
   >將編碼&amp;符號`&`取代為未編碼&amp;符號`&`

   不安全[!DNL URL]代碼：

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   安全[!DNL URL]代碼：

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 按一下 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果您使用多個區段，請為每個要對應至[!DNL Google Ads] [!DNL destination]的區段取得新像素。 這可確保資料套用至適當的再行銷清單。

1. 將新區段對應至Audience Manager中的此[!DNL destination]時，請將對應定義為`aam=segmentID`，並以區段的ID取代`segmentID`。
1. 在[!DNL Google Ads]中定義貯體時，請建立符合步驟6所定義之對應的規則。

完成的對應看起來可能類似：

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [建立 [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [關於AdWords再行銷清單](https://support.google.com/adwords/answer/2472738)
>* [AdWords再行銷的運作方式](https://support.google.com/adwords/answer/2454000)

