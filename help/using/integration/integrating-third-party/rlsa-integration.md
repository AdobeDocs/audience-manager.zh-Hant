---
description: 此程式需要AdWords再行銷清單、像素代碼和Audience ManagerURL目的地。 這也稱為搜尋廣告(RLSA)整合的再行銷清單。 僅適用於付費搜尋。
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: 將區段傳送至 Google AdWords 再行銷清單
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 3%

---

# 將區段傳送至Google廣告再行銷清單 {#send-segments-to-a-google-adwords-remarketing-list}

此程式需要 [!DNL Google Ads] 再行銷清單、像素代碼和Audience Manager [!DNL URL] [!DNL destination]. 這也稱為搜尋廣告的再行銷清單([!DNL RLSA])整合。 僅適用於付費搜尋。

>[!IMPORTANT]
>請注意，這不是兩個系統的產品化整合。

若要設定 [!DNL Google Ads] 重新行銷清單作為 [!DNL Audience Manager] [!DNL URL destination]:

1. 在 [!DNL Google Ads] 帳戶， [建立網站再行銷清單](https://support.google.com/tagmanager/answer/6106960?hl=en) 並記下轉換ID。
1. 使用下列URL作為基礎URL和安全URL的範本。 將xxxxxxxx區段替換為您的轉換ID。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience Manager中， [建立 [!DNL URL destination]](../../features/destinations/create-url-destination.md) 或編輯現有 [!DNL destination]. 建立 [!DNL destination]:
   * 類型：URL
   * 序列化：已啟用
   * 分隔字元：分號(&amp;semi;)

1. 在 [!UICONTROL Segment Mappings] 區段 [!DNL URL] [!DNL destination]，將程式碼從步驟2新增至 [!DNL URL] 和 [!DNL Secure URL] 欄位。 為程式碼加上前置詞 `http:` 和 `https:` 在 [!DNL URL] 和 [!DNL Secure URL] 欄位。

   >[!IMPORTANT]
   >
   >取代編碼&amp;符號 `&` 具有未編碼&amp;符號 `&`

   不安全 [!DNL URL] 代碼：

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   安全 [!DNL URL] 代碼：

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 按一下 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >若您使用多個區段，請針對您要對應至 [!DNL Google Ads] [!DNL destination]. 這可確保將資料套用至適當的再行銷清單。

1. 將新區段對應至此 [!DNL destination] 在Audience Manager中，將對應定義為 `aam=segmentID` 替換 `segmentID` 和區段的ID。
1. 在中定義貯體時 [!DNL Google Ads]，建立符合步驟6中定義之對應的規則。

完成的對應看起來可能類似以下：

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [建立 [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [關於AdWords再行銷清單](https://support.google.com/adwords/answer/2472738)
>* [AdWords再行銷的運作方式](https://support.google.com/adwords/answer/2454000)

