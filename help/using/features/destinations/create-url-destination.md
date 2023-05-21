---
description: URL目標會從頁面向目標進行像素調用。 按照以下說明使用目標生成器建立URL目標。
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: 設定 URL 目的地
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 3%

---

# 配置 [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] 將像素調用從頁面發到 [!DNL destination]。 按照以下說明建立 [!DNL URL] [!DNL destination] 與 [!UICONTROL Destination Builder]。

<!-- create-url-destination.xml -->

建立新 [!DNL URL] [!DNL destination]，轉到 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 並完成以下部分。

## 基本資訊 {#basic-info}

此部分包含啟動 [!DNL URL destination] 建立過程。 要完成本節：

1. 按一下 **[!UICONTROL Basic Information]** 來揭示控制項。
2. 命名 [!DNL destination]。 避免縮寫和特殊字元。
3. *（可選）* 描述 [!DNL destination]。 簡潔描述是定義或提供有關 [!DNL destination]。
4. 在 **[!UICONTROL Category]** 清單 **[!UICONTROL Custom]**。
5. 在 **[!UICONTROL Environment]** 清單中，選擇要觸發 [!DNL URL destination]。
6. 在 **[!UICONTROL Type]** 清單，按一下 **[!UICONTROL URL]**。
7. *（可選）* 選擇 **[!UICONTROL Auto-fill Destination Mapping]**。 選項包括:
   * **[!UICONTROL Segment ID]**:自動將段ID添加併發送到 [!DNL destination]。
   * **[!UICONTROL Integration Code Value]**:自動將段整合代碼添加併發送到目標映射。 整合代碼是客戶建立和使用的唯一標識符。 最多限255個字元。
8. 按一下 **[!UICONTROL Next]** 轉到 [!UICONTROL Configuration] 設定，按一下 **[!UICONTROL Data Export Labels]** 將導出控制項應用於 [!DNL destination]。

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

本節包含適用的選項 [資料導出控制項](../../features/data-export-controls.md) 到 [!DNL URL] 目標。 如果不使用資料導出控制項，請跳過此步驟。 要完成本節：

1. 按一下 **[!UICONTROL Data Export Labels]** 來揭示控制項。
2. 選擇與應用到目標的資料導出控制項相對應的標籤(請參閱 [將導出標籤添加到目標](/help/using/features/destinations/add-data-export-labels.md) )。
3. 按一下 **[!UICONTROL Save]**.

## 設定 {#configure-base-data}

本節包含用於設定基的選項 [!DNL URL] 和資料分隔符 [!DNL URL] 的下界。 此部分是可選的。 要完成本節：

1. 按一下 **[!UICONTROL Configuration]** 來揭示控制項。
1. *（可選）* 選擇 **[!UICONTROL Serialize]** 的子菜單。
這允許您將段發送到 [!DNL destination] 而不是對每個段分別調用。 序列化有助於提高資料傳輸效率。 選中此複選框將顯示URL和分隔符欄位。 有關詳細資訊，請參見 [標準和序列鍵值對](../../features/destinations/key-value-pairs.md)。
1. 如果選擇 **[!UICONTROL Serialize]**，則還必須配置下面描述的URL和分隔符欄位。

| 欄位 | 說明 |
|--- |--- |
| [!UICONTROL Base URL] | 標準的基部 `HTTP` [!DNL URL] 不會改變的。 另外，你需要把 `%ALIAS%`  [佔位符宏](../../features/destinations/destination-macros.md#destination-macros-defined) 的子菜單。 範例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 安全裝置的基部 `HTTPS` [!DNL URL] 不會改變的。 另外，你需要把 `%ALIAS%`   [佔位符宏](../../features/destinations/destination-macros.md#destination-macros-defined) 的子菜單。 範例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 分隔段變數的符號 [!DNL URL] 的下界。 這通常是逗號或分號。 從目標合作夥伴獲取此資訊。 |

## [!UICONTROL Segment Mappings] {#segment-mappings}

此部分允許您搜索和將段添加到 [!UICONTROL destination]。 要完成本節：

1. 按一下 **[!UICONTROL Segment Mappings]** 來揭示控制項。
1. 在 **[!UICONTROL Search and Add Segments]** 框中，開始鍵入段的名稱，或按一下 **[!UICONTROL Browse All Segments]** 瀏覽可用段的清單。
1. 按一下 **[!UICONTROL Add Selected Segments]** 找到要使用的段。 添加段將開啟 [!UICONTROL Edit Mapping] 的子菜單。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**:提供段使用的鍵值對。
   * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**:為 [!DNL destination]。 如果結束日期為空， [!DNL destination] 永不過期。
1. 按一下 **[!UICONTROL Done]**.
