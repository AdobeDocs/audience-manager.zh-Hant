---
description: 格式化入站特性資料檔案時應遵循的必填欄位、語法和規則。
solution: Audience Manager
title: 入站資料檔案內容 — 語法、無效字元、變數和示例
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
exl-id: 894f1923-6c78-41d2-b6a2-eebf56eaa29e
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 4%

---

# 傳入資料檔案內容：語法、無效字元、變數和範例 {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

格式化入站特性資料檔案時應遵循的必填欄位、語法和規則。

## 檔案內容語法 {#file-content-syntax}

入站資料檔案中的欄位必須按如下所示的順序顯示。 在此示例中， `<` `>` 已添加符號，以幫助直觀地分隔每個元素。 您不需要將這些內容包括在資料檔案中。

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

有關其他接受的檔案內容格式，請參見 [定制合作夥伴整合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

>[!NOTE]
>
>對於入站資料檔案中發送的每個用戶ID，我們最多可處理200行。 例如，如果為用戶ID發送300行，則前200行將保留，另外100行將被丟棄。 在下面的示例中，您是不錯的，因為您正在為用戶ID 1和用戶ID 2發送3行。 我們不會對您在一行中包括的特徵或鍵值對的數量實施限制。
>
>
```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## 定義的檔案變數 {#file-variables-defined}

該表列出並定義了正確格式化入站資料檔案中使用的變數。 *斜體*&#x200B;表示變數預留位置。

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>用戶ID可以是： </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">由分配的唯一用戶ID <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience ManagerUUID </a>)。 </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">在CRM系統中分配的唯一用戶ID( <a href="../../../reference/ids-in-aam.md"> DPUUID，在Audience Manager </a>)。 </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">移動作業系統所暴露的Android或iOS設備ID的原始未修改形式。 </li> 
     </ul> </p> <p>對於移動ID: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA格式：ID必須是大寫且不散列。 例如， <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android格式：ID必須小寫且不散列。 例如， <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>使用單個制表符分隔符分隔用戶ID和特性ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>的 <span class="keyword"> Audience Manager </span> 特徵ID 我們要求您包括 <i>只有已登陸的特徵</i> 入站資料檔案。 在入站資料傳輸中，我們不處理任何其他特性類型。 </p> <p> <p>注：可以使用返回所有特徵詳細資訊的GET方法來找到特徵ID。 有關詳細資訊，請參見 <a href="../../../api/rest-api-main/api-traits.md"> 特性API方法 </a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 格式 [!UICONTROL Trait IDs] {#formatting-trait-ids}

下表介紹了標識的前置詞 [!UICONTROL trait] 入站資料檔案中的名稱或ID。 查看 [示例檔案](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) 的上界。

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 前置詞 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p>的 <code> d_sid </code> 前置詞告訴我們系統ID是 <span class="keyword"> Audience Manager </span> 特徵ID 這與用戶介面中顯示的ID相同。 也可以使用API返回特性ID <code> GET </code> 的雙曲餘切值。 請參閱 <a href="../../../api/rest-api-main/api-traits.md"> 特性API方法 </a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>資料前置詞為 <code> d_unsid </code> 將用戶從該特性中刪除。 的 <code> d_unsid </code> 在 <code> overwrite </code> 的子菜單。 </p> <p>的 <code> d_unsid= </code> 前置詞告訴我們系統ID是 <span class="keyword"> Audience Manager </span> 特徵ID 這與用戶介面中顯示的ID相同。 也可以使用API返回特性ID <code> GET </code> 的雙曲餘切值。 請參閱 <a href="../../../api/rest-api-main/api-traits.md"> 特性API方法 </a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> 特質規則 </a> 讓你為特質鑑定設定標準。 如果將特徵規則格式為 <code> ic == trait ID </code>，可以在簡單逗號格式清單中發送trait。 </p> <p>例如，假設您建立以下3個特性規則： </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>這些特徵與 <code> ic </code> 按鈕 這允許您在資料檔案中建立一個更簡單的特性清單。 而且，你不需要把 <code> ic </code> 前置詞。 因此，資料檔案的內容可能如下所示： </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>鍵值對 </p> </td> 
   <td colname="col2"> <p>特性資料可以使用字母數字字串格式化為鍵值對。 有幾種格式化鍵值對的方法，如下所示： </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> 。 <code> "gender"=m </code> 。 <code> model = "pickup truck" </code> 。 <code> product = tablet </code> 都是正確格式鍵值對的示例。 </p> </td> 
  </tr>
 </tbody>
</table>

## 中的字元無效 [!UICONTROL Trait IDs]。 [!UICONTROL User IDs] 和鍵值對 {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] 只包含數字字元。 我們要求您包括 *僅[!UICONTROL onboarded traits]* 入站資料檔案。 我們不處理其他 [!UICONTROL trait] 入站資料傳輸中的類型。

### [!UICONTROL User IDs]

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID 類型 </th> 
   <th colname="col2" class="entry"> 需求 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>不要</i> 使用編碼的冒號( <code> %3A </code>)或未編碼的冒號(:)符號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移動iOS(IDFA)或Android設備ID </p> </td> 
   <td colname="col2"> <p>移動設備ID必須嚴格格式化，如下所示： </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA格式：ID必須是大寫且不散列。 例如， <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android格式：ID必須小寫且不散列。 例如， <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 鍵值對

鍵值對中格式不正確的值名稱也會導致問題。 在鍵值對中建立或命名值時，請遵循以下規則：

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字元 </th> 
   <th colname="col2" class="entry"> 需求 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>引號字元 (") </p> </td> 
   <td colname="col2"> <p>可以在鍵和鍵值對的值部分使用引號字元，如： </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>破折號字元(-) </p> </td> 
   <td colname="col2"> <p>我們忽略鍵頭的破折號。 比如說， <code> -product = camera </code> 解釋為 <code> product = camera </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>不要</i> 使用 <code> TAB </code> 而不是鍵值對中的空值。 僅使用 <code> TAB </code> 以在入站資料檔案中分離變數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>不使用新行或制表符字元( <code> \n, \t </code>)。 </p> </td> 
  </tr>
 </tbody>
</table>

## 資料檔案示例 {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 資料檔案格式 </th> 
   <th colname="col2" class="entry"> 說明和示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>與 <code> d_sid </code> 或 <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>此資料檔案顯示符合特徵24、26、27的用戶，已從特徵28和29中刪除。 </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>注意:  <p>您也可以使用以下語法從用戶配置檔案中刪除traits，而不是使用d_unsid: </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>包含 <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>這些特徵被加進了一個特徵規則 <code> ic </code> 前置詞。 因此，可以將它們添加到以逗號分隔的資料檔案中，如所示。 制表符分隔UUID和特性ID。 的 <code> ic </code> 檔案中不需要前置詞。 </p> <p><b>數字ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>字串ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帶鍵值對 </p> </td> 
   <td colname="col2"> 此檔案資料使用鍵值對將資料傳遞到 <span class="keyword"> Audience Manager </span>。 <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[下載](assets/ftp_dpm_1234_1445374061.overwrite) 示例資料檔案（如果需要其他示例）。 下載檔案具有 `.overwrite` 檔案副檔名。 可以使用簡單的文本編輯器開啟它。

## 示例矩陣 {#examples-matrix}

下圖顯示了正確格式化入站檔案的示例，具體取決於 [ID類型](../../../reference/ids-in-aam.md) 和您要添加的方法 [!UICONTROL traits] 到配置檔案。

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID類型/操作 </th> 
   <th colname="col2" class="entry"> 使用d_sid向用戶配置檔案添加特徵 </th> 
   <th colname="col3" class="entry"> 使用d_unsid從用戶配置檔案中刪除特徵 </th> 
   <th colname="col4" class="entry"> 發送鍵值對以向用戶配置檔案添加特徵 </th> 
   <th colname="col5" class="entry"> 使用ic前置詞向用戶配置檔案添加特徵 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience ManagerUUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> 範例 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> 範例 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> 示例3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> 示例4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>GoogleAndroid設備廣告ID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> 示例5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> 示例6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> 示例7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> 示例8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AppleIDFA用於iOS設備 </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> 示例9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> 示例10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> 示例11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> 示例12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>您自己的CRM ID(DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> 示例13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> 示例14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> 示例15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> 示例16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 範例 1 {#example-1}

使用 [!UICONTROL trait IDs] 發送 [!UICONTROL trait] 資格資訊 [!DNL Audience Manager] [!DNL UUIDs]。

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### 範例 2 {#example-2}

使用 [!UICONTROL trait IDs] 發送 [!UICONTROL trait] 取消資格資訊 [!DNL Audience Manager] [!DNL UUIDs]。

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

或 

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

或 

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### 範例 3 {#example-3}

發送鍵值對以添加 [!UICONTROL trait] 資格資訊 [!DNL Audience Manager] [!DNL UUIDs]。

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

或 

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### 示例4 {#example-4}

使用 `ic` 發送前置詞 [!UICONTROL trait] 資格資訊 [!DNL Audience Manager] [!DNL UUIDs]。

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

或 

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### 示例5 {#example-5}

使用 [!UICONTROL trait IDs] 發送 [!UICONTROL trait] 資格資訊 [!DNL Android] 設備。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 示例6 {#example-6}

使用 [!UICONTROL trait IDs] 發送 [!UICONTROL trait] 取消資格資訊 [!DNL Android] 設備。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

或 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

或 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### 示例7 {#example-7}

發送鍵值對以添加 [!UICONTROL trait] 資格資訊 [!DNL Android] 設備。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

或 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### 示例8 {#example-8}

使用 `ic` 發送前置詞 [!UICONTROL trait] 資格資訊 [!DNL Android] 設備。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

或 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### 示例9 {#example-9}

使用 [!UICONTROL trait IDs] 發送 [!UICONTROL trait] 資格資訊 [!DNL iOS] 設備。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 示例10 {#example-10}

使用 [!UICONTROL trait IDs] 發送 [!UICONTROL trait] 取消資格資訊 [!DNL iOS] 設備。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

或 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

或 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### 示例11 {#example-11}

發送鍵值對以添加 [!UICONTROL trait] 資格資訊 [!DNL iOS] 設備。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

或 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### 示例12 {#example-12}

使用 `ic` 發送前置詞 [!UICONTROL trait] 資格資訊 [!DNL iOS] 設備。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

或 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### 示例13 {#example-13}

使用 [!UICONTROL trait IDs] 發送 [!UICONTROL trait] 資格資訊 [!DNL DPUUIDs]。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 示例14 {#example-14}

使用 [!UICONTROL trait IDs] 發送 [!UICONTROL trait] 取消資格資訊 [!DNL DPUUIDs]。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

或 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

或 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### 示例15 {#example-15}

發送鍵值對以添加 [!UICONTROL trait] 資格資訊 [!DNL DPUUIDs]。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

或 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### 示例16 {#example-16}

使用 `ic` 發送前置詞 [!UICONTROL trait] 資格資訊 [!DNL DPUUIDs]。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

或 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [特徵產生器](../../../features/traits/about-trait-builder.md)

