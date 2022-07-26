---
description: 當此操作違反資料隱私或資料使用協定時，資料導出控制會阻止您將資料發送到目標。
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: 資料匯出控制
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: c7a6de018a0ddd782eecec0844c4f5c824431119
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 1%

---

# 資料匯出控制 {#data-export-controls}

[!UICONTROL Data Export Controls] 阻止您在此操作違反資料隱私或資料使用協定時將資料發送到目標。

## 概述 {#overview}

[!UICONTROL Data Export Controls] 讓你把 [資料源](../features/datasources-list-and-settings.md#data-sources-list-and-settings) 和 [目的地](../features/destinations/destinations.md)。 您應用的分類確定何時可以或無法將資料導出到目標。 此功能包括：

* **[!UICONTROL Data Export Controls]**:可以設定資料導出控制項 *資料源*。 在資料源上設定時，這些控制項將限制資料源及其特性的使用方式。
* **[!UICONTROL Data Export Labels]**:可以在上設定資料導出標籤 *目的地*。 在目標上設定時，這些標籤會標識目標如何使用資料。 請參閱 [將資料導出標籤添加到目標](/help/using/features/destinations/add-data-export-labels.md) 瞭解如何將導出標籤添加到目標。

根據應用於資料源和目標的分類，導出控制將阻止您：

* 當特徵屬於資料源時，向段添加特徵，該資料源具有與段映射到的一個或多個目標上的資料導出標籤不相容的資料導出控制。
例如，假定一個段映射到具有導出標籤的目標 **[!DNL This destination may enable a combination with personally identifiable information (PII)]**。 如果屬性所屬的資料源具有資料導出控制項，則導出控制項會阻止您向該段添加屬性 **[!DNL Cannot be tied to personally identifiable information (PII)]**。
* 將任何資料發送到具有資料導出標籤的目標，該標籤被資料導出控制項阻止：
   * 包含特徵的資料源；
   * 包含段中使用的特徵的資料源；
   * 包含的段利用的配置檔案合併規則；
   * 包含段的配置檔案合併規則使用的任何資料源。

[!UICONTROL Data Export Controls] 可自動供所有Audience Manager客戶使用。 但是，您需要管理員權限才能將導出控制項添加到資料源。 將導出標籤添加到目標需要管理員權限 *或* 足夠的權限建立或編輯目標。

## 定義的控制項和標籤 {#controls-labels}

[!UICONTROL Data Export Controls] 提供以下控制項以幫助您對資料源和目標進行分類。

要阻止資料傳送，必須使用導出控制項對資料源進行分類，並將導出標籤添加到目標。 如果僅將導出控制應用於資料源或目標，則此功能將不限制資料傳遞。 在兩個資料源上設定時 *和* 目標，導出控制項將限制您可以添加到段中的特徵，並防止將段成員發送到目標。

此外，在資料傳送限制生效之前，至少有一個導出標籤必須與導出控制項匹配。 例如，假設您 [!UICONTROL PII] 將控制項導出到資料源。 接下來，將現場目標標籤添加到目標。 在這種情況下，導出控制項將不限制資料傳遞，因為設定不匹配。 但是，如果 [!UICONTROL PII] 將標籤導出到目標，導出控制項將阻止導出。

>[!IMPORTANT]
>
>不能通過將資料導出控制項置於段的資料源上來阻止段的導出，必須對以下任一項設定控制項：
> * 資料源中使用的特徵；
> * 段利用的配置檔案合併規則；
> * 段的配置檔案合併規則使用的任何資料源。


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 資料源的資料導出控制項 </th> 
   <th colname="col2" class="entry"> 目標的資料導出標籤 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無限制</span></b> </td> 
   <td colname="col2"> 不適用 </td> 
   <td colname="col3"> 預設情況下，不會對新資料源和目標設定導出限制。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 不能與個人身份資訊關聯</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目標可以啟用與個人身份資訊(PII)的組合</span></b> </td> 
   <td colname="col3">選中後，不能： 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">向映射到使用PII的目標的段添加特徵。 </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">從資料源到使用PII的目標，使用特徵構建映射段。 </li> 
    </ul> <p>這通常是第三方資料提供商在使用包含廣告/媒體跟蹤資訊的資料源時需要的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於現場廣告目標</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目標可用於現場廣告定位</span></b> </td> 
   <td colname="col3">選中後，不能： 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">將特徵添加到映射到目標的段，這些目標根據訪問者的Web瀏覽歷史記錄定制廣告交付。 </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">根據訪問者的Web瀏覽歷史從資料源到定制廣告遞送的目的地的特性構建地圖段。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 不能用於非現場廣告目標</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目標可用於非現場廣告目標</span></b> </td> 
   <td colname="col3">這些限制通常與「選中時，不能： 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">向映射到目標的段添加特徵，以重新確定其他站點上的用戶的目標。 </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">將具有特性的資料段從資料源構建到目標，以重新確定其他站點上的用戶。 </li> 
    </ul> <p>使用社交媒體平台中的資料時通常需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 無法用於現場個性化</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目標可用於現場和個性化</span></b> </td> 
   <td colname="col3">選中後，不能： 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">向映射到目標的段添加特徵，這些目標根據用戶興趣或Web瀏覽歷史記錄定制內容。 </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">從資料源到根據用戶興趣或Web瀏覽歷史定制內容的目標，以特徵構建資料段。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 工作流程 {#workflow}

要開始，請查看資料源和目標文檔。 這些文章提供了有關如何將導出控制項和標籤添加到資料源和目標的說明。

* [建立資料來源](../features/manage-datasources.md#create-data-source)
* [將資料導出標籤添加到目標](../features/destinations/add-data-export-labels.md)
