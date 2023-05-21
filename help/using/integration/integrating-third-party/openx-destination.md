---
description: 將OpenX設定為目標，並將Audience Manager段資料發送到該平台。
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX 作為 Audience Manager 目的地
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 2%

---

# OpenX 作為 Audience Manager 目的地{#openx-as-an-audience-manager-destination}

設定 [!DNL OpenX] 將Audience Manager段資料發送到該平台。

>[!NOTE]
>
>僅針對現場廣告伺服器。

## OpenX目標要求 {#openx-requirements}

代碼放置標準、支援的鍵值格式、報告和發送到的段資料類型 [!DNL OpenX]。

<!-- aam-openx-requirements.xml -->

在設定之前查看以下內容 [!DNL OpenX] 作為Audience Manager目標：

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] 應在您的站點上部署代碼。 [!UICONTROL DIL] 有助於消除為資料收集、整合、讀取cookie值和恢復頁資料編寫特殊代碼的需要。
* **`get_aamCookie`函式：** 捕獲Audience Manager用戶ID和Cookie資料的代碼。 位置 [此代碼](../../features/destinations/get-aam-cookie-code.md) 在頁面頂部或 `<head>` 去塊。
* **將傳遞日誌發送到Audience Manager:** 如果要生成段交貨報表（可選），請向Audience Manager提供包含印象級交貨資料的日誌。 資料可以是原始格式，但每條記錄必須包含Audience Manager `UUID`。 Audience Manager可以通過 [!DNL FTP]。

### 鍵值資料：格式要求

Audience Manager以鍵值對的形式發送資料。 根據以下規範建立鍵值對：

* 前言鍵 `c.` (例如， `c.color` 或 `c.price`)。
* 用逗號分隔附加到單個鍵的序列化值(例如， `c.color = red, green, blue`)。
* 將多個鍵值對與號分開(例如， `c.color=red & c.price = 100 & c.condition = new`)。
* 鍵名不應包含特殊字元，如強調符號和標點符號或其他符號。

### 只將限定段發送到OpenX

傳入的金額資料 [!DNL OpenX] 取決於特定用戶需要多少段。 例如，假設您設定了100個Audience Manager段。 如果站點訪問者有資格獲得其中五個，則僅將這五個段發送給 [!DNL OpenX] （不是全部100個）。

## 建立OpenX目標 {#openx-destination}

建立Cookie目標 [!DNL OpenX] Audience Manager。

<!-- aam-openx-destination.xml -->

在Audience Manager中，a *目標* 是其他系統（ad伺服器） [!DNL DSP]、ad網路等) 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 提供了用於建立和管理這些資料傳遞過程的工具。 Audience Manager目標功能位於 *受眾資料>目標*。 要開始，請按一下 **[!UICONTROL Add New Destination]** 按照以下步驟操作。

### 步驟1:基本資訊

完成 [!UICONTROL Basic Information] 部分：

1. 命名目標。
1. 選擇 **[!UICONTROL "Cookie"]** 從 [!UICONTROL Type] 的子菜單。
1. 按一下 **[!UICONTROL Next]** 繼續 [!UICONTROL Configuration] 和 [!UICONTROL Segment Mappings] 的下界。

### 步驟2:配置資訊

完成 [!UICONTROL Configuration] 部分：

1. **Cookie名稱：** 為Cookie提供簡短的描述性名稱。
1. **Cookie域：** 留空可在用戶當前頁面的域中設定Cookie。 如果要指定域，請在名稱前加上類似的句點， `.mydomain.com`。
1. 在 [!UICONTROL Data Format] 的子菜單。
1. 如果鍵使用具有序列化值的資料，請選擇 **[!UICONTROL Serialize]** 控制並指定序列分隔符（分隔序列化值的字元）。
1. 按一下 **[!UICONTROL Save]** 並擴展 [!UICONTROL Segment Mappings] 的子菜單。

### 第3步：段映射

要將段添加到Cookie目標：

1. **查找段：** 的 [!UICONTROL Segment Mappings] 部分提供了兩個搜索工具以幫助查找段。 要查找段，請執行以下操作：
   * 選項1:開始在搜索欄位中鍵入段名稱。 該欄位會根據文本自動更新。 按一下 **[!UICONTROL Add]** 找到要使用的段後。
   * 選項2:按一下 **[!UICONTROL Browse All Segments]** 開啟一個窗口，以便按名稱或儲存位置瀏覽段。 按一下 **[!UICONTROL Add Selected Segments]** 完成。
1. **添加映射：** 在映射彈出窗口中，在映射欄位中輸入段ID，然後按一下 **[!UICONTROL Save]**。
1. 按一下 **[!UICONTROL Done]**.

## OpenX安裝程式 {#openx-code-setup}

修改 [!DNL OpenX] 設定以處理Audience Manager段資料。

<!-- aam-openx-code.xml -->

設定 [!DNL OpenX]:

* 安裝 [!UICONTROL DIL] 你網站上的代碼。
* 建立 [!DNL OpenX] 作為Cookie的Audience Manager。
* 放置 `get_aamCookie` 功能，最好在 `<head>` 去塊。 的 `get_aamCookie` 代碼可用 [這裡](../../features/destinations/get-aam-cookie-code.md)。
* 修改廣告標籤以調用 `get_aamCookie` 函式，並包括在設定 [!DNL OpenX] 目標。 例如，如果您為Cookie命名 `test_cookie`，則ad標籤應調用 `get_aamCookie` 並引用cookie名稱。
* 您的廣告標籤可能與下面的示例類似。

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

記住要包括 `xid=` 。 它保存實際唯一用戶ID([!UICONTROL UUID])在廣告呼叫期間傳入。

完整形成的廣告呼叫可能與以下類似：

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
