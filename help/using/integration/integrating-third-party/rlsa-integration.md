---
description: 此過程需要AdWords重新營銷清單、像素代碼和Audience ManagerURL目標。 它也稱為搜索廣告(RLSA)整合的再營銷清單。 僅適用於付費搜索。
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

# 將段發送到Google廣告再營銷清單 {#send-segments-to-a-google-adwords-remarketing-list}

此過程需要 [!DNL Google Ads] 重新營銷清單、像素代碼和Audience Manager [!DNL URL] [!DNL destination]。 它也稱為搜索廣告的再營銷清單([!DNL RLSA])整合。 僅適用於付費搜索。

>[!IMPORTANT]
>請注意，這不是兩個系統的產品化整合。

設定 [!DNL Google Ads] 將清單重新市場營銷為 [!DNL Audience Manager] [!DNL URL destination]:

1. 在 [!DNL Google Ads] 帳戶， [建立網站重新營銷清單](https://support.google.com/tagmanager/answer/6106960?hl=en) 寫下你的轉換ID。
1. 將以下URL用作基URL和安全URL的模板。 用轉換ID替換xxxxxxxx節。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience Manager, [建立 [!DNL URL destination]](../../features/destinations/create-url-destination.md) 或編輯現有 [!DNL destination]。 建立 [!DNL destination]:
   * 類型：URL
   * 序列化：已啟用
   * 分隔符：分號(&amp;semi;))

1. 在 [!UICONTROL Segment Mappings] 的 [!DNL URL] [!DNL destination]，將代碼從步驟2添加到 [!DNL URL] 和 [!DNL Secure URL] 的子菜單。 將代碼前置詞為 `http:` 和 `https:` 的 [!DNL URL] 和 [!DNL Secure URL] 的下界。

   >[!IMPORTANT]
   >
   >替換編碼和符號 `&` 帶非編碼和符號 `&`

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
   >如果使用多個段，請為要映射到的每個段獲取新像素 [!DNL Google Ads] [!DNL destination]。 這確保資料被應用到相應的重新營銷清單。

1. 將新段映射到此 [!DNL destination] 在Audience Manager中，將映射定義為 `aam=segmentID` 替換 `segmentID` 段的ID。
1. 在中定義時段 [!DNL Google Ads]，建立與步驟6中定義的映射相匹配的規則。

完成的映射可能與以下內容類似：

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [建立 [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [關於AdWords重新營銷清單](https://support.google.com/adwords/answer/2472738)
>* [AdWords再營銷的工作原理](https://support.google.com/adwords/answer/2454000)

