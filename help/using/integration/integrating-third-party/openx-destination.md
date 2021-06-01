---
description: 將OpenX設定為目的地，並將Audience Manager區段資料傳送至該平台。
seo-description: 將OpenX設定為目的地，並將Audience Manager區段資料傳送至該平台。
seo-title: OpenX 作為 Audience Manager 目的地
solution: Audience Manager
title: OpenX 作為 Audience Manager 目的地
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: 協力廠商整合
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 3%

---

# OpenX 作為 Audience Manager 目的地{#openx-as-an-audience-manager-destination}

將[!DNL OpenX]設為目的地，並傳送Audience Manager區段資料至該平台。

>[!NOTE]
>
>僅適用於Onsite廣告伺服器鎖定。

## OpenX目標要求{#openx-requirements}

程式碼放置、支援的鍵值格式、報表，以及傳送至[!DNL OpenX]的區段資料類型的標準。

<!-- aam-openx-requirements.xml -->

在將[!DNL OpenX]設定為Audience Manager目的地之前，請先查看以下內容：

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] 程式碼應部署在您的網站上。[!UICONTROL DIL] 有助於避免編寫特殊程式碼以用於資料收集、整合、讀取cookie值及恢復頁面資料的需求。
* **`get_aamCookie`函式：** 擷取Audience Manager使用者ID和Cookie資料的程式碼。將[此代碼](../../features/destinations/get-aam-cookie-code.md)放置在頁面頂端或`<head>`程式碼塊內。
* **傳送傳送記錄檔至Audience Manager:** 如果您想要區段傳送報表（選用），請為Audience Manager提供包含曝光層級傳送資料的每日記錄檔。資料可以是原始格式，但每個記錄必須包含Audience Manager`UUID`。 Audience Manager可以透過[!DNL FTP]接收這些檔案。

### 機碼值資料：格式需求

Audience Manager會以機碼值組的形式傳送資料。 根據下列規格建立機碼值組：

* 以`c.`（例如`c.color`或`c.price`）為鍵前置詞。
* 使用逗號（例如`c.color = red, green, blue`）分隔附加至單一鍵的序列化值。
* 以&amp;符號分隔多個索引鍵值配對（例如`c.color=red & c.price = 100 & c.condition = new`）。
* 索引鍵名稱不應包含特殊字元，例如重音符號、標點符號或其他符號。

### 只有合格區段會傳送至OpenX

傳遞至[!DNL OpenX]的資料量取決於特定使用者符合的區段數。 例如，假設您設定100個Audience Manager區段。 如果網站訪客符合其中5個區段的資格，則只有這5個區段會傳送至[!DNL OpenX]（並非全部100個）。

## 建立OpenX目標{#openx-destination}

為[!DNL OpenX]建立Audience Manager中的Cookie目的地。

<!-- aam-openx-destination.xml -->

在Audience Manager中，*destination*&#x200B;是任何其他系統（廣告伺服器、[!DNL DSP]、廣告網路等） 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程式的工具。Audience Manager目的地功能位於&#x200B;*受眾資料>目的地*&#x200B;中。 若要開始使用，請按一下&#x200B;**[!UICONTROL Add New Destination]**&#x200B;並遵循下列步驟。

### 步驟1:基本資訊

要完成[!UICONTROL Basic Information]部分：

1. 為目的地命名。
1. 從[!UICONTROL Type]下拉清單中選擇&#x200B;**[!UICONTROL "Cookie"]**。
1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;並移至[!UICONTROL Configuration]和[!UICONTROL Segment Mappings]區段。

### 步驟2:配置資訊

要完成[!UICONTROL Configuration]部分：

1. **Cookie名稱：** 為您的Cookie提供簡短的描述性名稱。
1. **Cookie網域：** 留空可在使用者目前頁面的網域中設定Cookie。如果要指定域，請在名稱前加上類似`.mydomain.com`的句號。
1. 在[!UICONTROL Data Format]區段中選擇鍵選項。
1. 如果您的鍵使用具有序列化值的資料，請選擇&#x200B;**[!UICONTROL Serialize]**&#x200B;控制項並指定序列分隔符（分隔序列化值的字元）。
1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;並展開[!UICONTROL Segment Mappings]區段。

### 步驟3:區段對應

若要新增區段至Cookie目的地：

1. **尋找區段：** 區段提 [!UICONTROL Segment Mappings] 供兩種搜尋工具，以協助找出區段。若要尋找區段：
   * 選項1:開始在搜尋欄位中輸入區段名稱。 欄位會根據文字自動更新。 找到您要使用的區段後，按一下&#x200B;**[!UICONTROL Add]**。
   * 選項2:按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;以開啟一個視窗，讓您依名稱或儲存位置瀏覽區段。 完成後，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。
1. **新增對應：** 在對應快顯視窗中，在對應欄位中輸入區段ID，然後按一下 **[!UICONTROL Save]**。
1. 按一下 **[!UICONTROL Done]**.

## OpenX安裝程式{#openx-code-setup}

修改[!DNL OpenX]設定以使用Audience Manager區段資料。

<!-- aam-openx-code.xml -->

要設定[!DNL OpenX]，請執行以下操作：

* 在您的網站上安裝[!UICONTROL DIL]程式碼。
* 將[!DNL OpenX]建立為Audience Manager中的Cookie目的地。
* 將`get_aamCookie`函式放置在頁面頂端，理想地放在`<head>`程式碼鎖中。 `get_aamCookie`代碼可用於[此處](../../features/destinations/get-aam-cookie-code.md)。
* 修改您的廣告標籤以呼叫`get_aamCookie`函式，並納入您在設定[!DNL OpenX]目的地時提供的Cookie名稱。 例如，如果您將Cookie命名為`test_cookie`，則廣告標籤應呼叫`get_aamCookie`並參考Cookie名稱。
* 您的廣告標籤看起來可能類似於下列範例。

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

請記得包含`xid=` 。 它保有廣告呼叫期間傳入的實際唯一使用者ID([!UICONTROL UUID])。

完整格式的廣告呼叫看起來可能類似這樣：

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
