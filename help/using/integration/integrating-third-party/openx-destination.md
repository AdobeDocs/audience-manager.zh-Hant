---
description: 將OpenX設為目的地，並將Audience Manager區段資料傳送至該平台。
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX作為Audience Manager目的地
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# OpenX作為Audience Manager目的地{#openx-as-an-audience-manager-destination}

將[!DNL OpenX]設定為目的地，並將Audience Manager區段資料傳送至該平台。

>[!NOTE]
>
>僅供站內廣告伺服器目標定位。

## OpenX目的地需求 {#openx-requirements}

程式碼放置的標準、支援的鍵值格式、報表，以及傳送給[!DNL OpenX]的區段資料型別。

<!-- aam-openx-requirements.xml -->

在將[!DNL OpenX]設定為Audience Manager目的地之前，請先檢閱下列內容：

* **[!UICONTROL DIL]：** [!UICONTROL Data Integration Library]程式碼應部署在您的網站上。 [!UICONTROL DIL]可協助您免除撰寫特殊程式碼以進行資料收集、整合、讀取Cookie值以及復原頁面資料等作業。
* **`get_aamCookie`函式：**&#x200B;擷取Audience Manager使用者ID和Cookie資料的程式碼。 將[此程式碼](../../features/destinations/get-aam-cookie-code.md)放在頁面頂端或`<head>`程式碼區塊內。
* **傳送傳遞記錄至Audience Manager：**&#x200B;如果您想要區段傳遞報告（選用），請為Audience Manager提供包含曝光層級傳遞資料的每日記錄。 資料可以是原始格式，但每筆記錄都必須包含Audience Manager `UUID`。 Audience Manager可以透過[!DNL FTP]收取或接收這些訊息。

### 索引鍵值資料：格式需求

Audience Manager會以機碼值組的形式傳送資料。 根據下列規格建立索引鍵值配對：

* 前置索引鍵有`c.` （例如`c.color`或`c.price`）。
* 以逗號分隔附加至單一索引鍵的序列化值（例如， `c.color = red, green, blue`）。
* 以&amp;符號（例如`c.color=red & c.price = 100 & c.condition = new`）分隔多個索引鍵值組。
* 金鑰名稱不應包含特殊字元，例如輔音符號和標點符號或其他符號。

### 只有合格的區段才會傳送到OpenX

傳入[!DNL OpenX]的資料量取決於特定使用者符合的區段數。 例如，假設您設定100個Audience Manager區段。 如果網站訪客符合其中五個區段的資格，則只會將這五個區段傳送至[!DNL OpenX] （並非全部100個）。

## 建立OpenX目的地 {#openx-destination}

在Audience Manager中為[!DNL OpenX]建立Cookie目的地。

<!-- aam-openx-destination.xml -->

在Audience Manager中，*目的地*&#x200B;是您要與其共用資料的任何其他系統（廣告伺服器、[!DNL DSP]、廣告網路等）。 [!UICONTROL Destination Builder]提供可讓您建立和管理這些資料傳遞程式的工具。 Audience Manager目的地功能位於&#x200B;*對象資料>目的地*。 若要開始使用，請按一下&#x200B;**[!UICONTROL Add New Destination]**&#x200B;並遵循下列步驟。

### 步驟1：基本資訊

若要完成[!UICONTROL Basic Information]區段：

1. 為目的地命名。
1. 從&#x200B;**[!UICONTROL "Cookie"]**&#x200B;下拉式清單中選取[!UICONTROL Type]。
1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;並移至[!UICONTROL Configuration]與[!UICONTROL Segment Mappings]區段。

### 步驟2：設定資訊

若要完成[!UICONTROL Configuration]區段：

1. **Cookie名稱：**&#x200B;為您的Cookie提供簡短描述性名稱。
1. **Cookie網域：**&#x200B;留空可在使用者目前頁面的網域中設定Cookie。 如果您要指定網域，請在名稱前面加上句點，如`.mydomain.com`。
1. 在[!UICONTROL Data Format]區段中選擇索引鍵選項。
1. 如果您的金鑰使用具有序列化值的資料，請選取&#x200B;**[!UICONTROL Serialize]**&#x200B;控制項並指定序列分隔符號（分隔序列化值的字元）。
1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;並展開[!UICONTROL Segment Mappings]區段。

### 步驟3：區段對應

若要將區段新增至Cookie目的地：

1. **尋找區段：** [!UICONTROL Segment Mappings]區段提供兩種搜尋工具來協助尋找區段。 若要搜尋區段，請執行下列步驟：
   * 選項1：開始在搜尋欄位中輸入區段名稱。 欄位會根據文字自動更新。 找到要使用的區段後，請按一下&#x200B;**[!UICONTROL Add]**。
   * 選項2：按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;開啟視窗，讓您依名稱或儲存位置瀏覽區段。 完成時，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。
1. **新增對應：**&#x200B;在對應快顯視窗中，在對應欄位中輸入區段ID，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 按一下 **[!UICONTROL Done]**。

## OpenX設定 {#openx-code-setup}

修改[!DNL OpenX]設定以使用Audience Manager區段資料。

<!-- aam-openx-code.xml -->

若要設定[!DNL OpenX]：

* 在您的網站上安裝[!UICONTROL DIL]程式碼。
* 在Audience Manager中將[!DNL OpenX]建立為Cookie目的地。
* 將`get_aamCookie`函式放置在頁面頂端，最好放在`<head>`程式碼區塊中。 `get_aamCookie`程式碼可在[這裡](../../features/destinations/get-aam-cookie-code.md)取得。
* 修改您的廣告標籤以呼叫`get_aamCookie`函式，並加入您在設定[!DNL OpenX]目的地時提供的Cookie名稱。 例如，如果您為Cookie `test_cookie`命名，則廣告標籤應呼叫`get_aamCookie`並參考Cookie名稱。
* 您的廣告標籤看起來可能類似於以下範例。

  ```
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

記得加入`xid=` 。 它保留在廣告呼叫期間傳入的實際不重複使用者識別碼([!UICONTROL UUID])。

完整格式的廣告呼叫看起來可能類似這樣：

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
