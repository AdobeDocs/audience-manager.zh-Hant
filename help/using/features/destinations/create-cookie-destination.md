---
description: Cookie目標在用戶的瀏覽器中返回資料並將資料寫入Cookie。 Cookie包含可由其他平台讀取的資料，這些平台有權訪問該頁面。 按照以下說明建立Cookie目標 [!UICONTROL Destination Builder]。
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: 設定 Cookie 目的地
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 3%

---

# 設定 Cookie 目的地 {#create-cookie-destination}

Cookie目標在用戶的瀏覽器中返回資料並將資料寫入Cookie。 Cookie包含可由其他平台讀取的資料，這些平台有權訪問該頁面。 按照以下說明建立Cookie目標 [!UICONTROL Destination Builder]。

<!-- create-cookie-destination.xml -->

要建立新Cookie目標，請轉到 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 並完成以下部分。

## 基本資訊 {#basic-information}

此部分包含啟動Cookie目標建立過程的欄位和選項。 要完成本節：

1. 按一下 **[!UICONTROL Basic Information]** 來揭示控制項。
2. 命名目標。 避免縮寫和特殊字元。
3. *（可選）* 描述目標。 簡潔的描述是定義或提供有關目標的詳細資訊的有效方法。
4. 在 **[!UICONTROL Category]** 清單 **[!UICONTROL Custom]**。
5. 在 **[!UICONTROL Environment]** 清單，選擇 **[!UICONTROL Browser]**。 無法為本地移動環境(如Android或iOS應用)配置Cookie目標。
6. 在 **[!UICONTROL Type]** 清單，按一下 **[!UICONTROL Cookie]**。
7. *（可選）* 選擇 **[!UICONTROL Auto-fill Destination Mapping]**。 選項包括:
   * **[!UICONTROL Segment ID]**:自動將段ID添加併發送到目標。
   * **[!UICONTROL Integration Code Value]**:自動將段整合代碼添加併發送到目標映射。 整合代碼是客戶建立和使用的唯一標識符。 最多限255個字元。
8. 按一下 **[!UICONTROL Next]** 轉到 [!UICONTROL Configuration] 設定，按一下 **[!UICONTROL Data Export Labels]** 將導出控制項應用到目標。

## 資料導出標籤 {#data-export-labels-cookies}

本節包含適用的選項 [資料導出控制項](../../features/data-export-controls.md) 到Cookie目標。 如果不使用資料導出控制項，請跳過此步驟。 要完成本節：

1. 按一下 **[!UICONTROL Data Export Labels]** 來揭示控制項。
2. 選擇與應用到目標的資料導出控制相對應的標籤(請參閱 [將導出標籤添加到目標](/help/using/features/destinations/add-data-export-labels.md) )。
3. 按一下 **[!UICONTROL Save]**.

## 設定 {#configuration}

此部分包含用於為目標設定Cookie的欄位和選項。

>[!NOTE]
>
>[!DNL Audience Manager] 對寫入到目標cookie的資料進行編碼。 例如，空格編碼為 `%20` 分號編碼為 `%3B`。

要完成本節：

1. 按一下 **[!UICONTROL Configuration]** 以暴露控制項
1. 命名Cookie。 避免縮寫和特殊字元。
1. 選擇資料格式選項。 這些選項允許您為將段資料發送到目標的鍵值對選擇分隔符和分隔符。 格式選項包括：
   * **單鍵：** 用於在鍵值對中設定鍵。 在中選取段後，將設定值 [!UICONTROL Segment Mappings] 的下界。
   * **多鍵：** 用於設定鍵值對的鍵和值。 在下面的「段映射」部分中選擇段後，將建立鍵值對。
請參閱 [標準和序列鍵值對](../../features/destinations/key-value-pairs.md) 的子菜單。
1. 按一下 **[!UICONTROL Save]**.

所有其他設定都是可選的。 有關 **[!UICONTROL Cookie Domain]** 和 **[!UICONTROL Publish data to]** 設定，請參閱 [Cookie目標的可選設定](/help/using/features/destinations/cookie-destination-options.md)。

## 段映射 {#segments-mapping}

此部分允許您搜索段並將其添加到目標。 要完成本節：

1. 按一下 **[!UICONTROL Segment Mappings]** 來揭示控制項。
1. 在 **[!UICONTROL Search and Add Segments]** 框中，開始鍵入段的名稱，或按一下 **[!UICONTROL Browse All Segments]** 瀏覽可用段的清單。
1. 按一下 **[!UICONTROL Add Selected Segments]** 找到要使用的段。 添加段將開啟 [!UICONTROL Edit Mapping] 的子菜單。
1. 在 [!UICONTROL Edit Mapping] 對話框：
   * **[!UICONTROL Mapping]** 用於為上面「配置」部分中指定的鍵設定值。
   * **[!UICONTROL Publish from]** 用於設定目標的開始和結束日期。 如果結束日期為空，則目標將永不過期。
1. 按一下 **[!UICONTROL Save]**.
1. 按一下 **[!UICONTROL Done]**.
