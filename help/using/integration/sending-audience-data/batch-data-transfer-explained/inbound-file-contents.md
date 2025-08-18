---
description: 格式化傳入特徵資料檔案時，應遵循的必要欄位、語法和規則。
solution: Audience Manager
title: 傳入資料檔案內容 — 語法、無效字元、變數和範例
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
exl-id: 894f1923-6c78-41d2-b6a2-eebf56eaa29e
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 3%

---

# 傳入資料檔案內容：語法、無效字元、變數和範例 {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

格式化傳入特徵資料檔案時，應遵循的必要欄位、語法和規則。

## 檔案內容語法 {#file-content-syntax}

傳入資料檔案中的欄位必須以下列順序顯示。 在此範例中，已新增`<` `>`符號，以視覺化方式分隔每個元素。 您不需要將這些專案包含在資料檔案中。

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

如需其他接受的檔案內容格式，請參閱[自訂合作夥伴整合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

>[!NOTE]
>
>對於傳入資料檔案中傳送的每個使用者ID，我們最多可處理200行。 例如，如果您為使用者ID傳送300行，則會保留前200行，並捨棄其他100行。 在下列範例中，您符合要求，因為您為使用者ID 1和使用者ID 2各傳送3行。 我們並未對您包含在一行中的特徵或索引鍵值配對數量實施限制。
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## 已定義的檔案變數 {#file-variables-defined}

此表格列出並定義在正確格式化的傳入資料檔案中使用的變數。 *斜體*&#x200B;表示變數預留位置。

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
   <td colname="col2"> <p>使用者ID可以是： </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B"><span class="keyword"> Audience Manager </span>指派的不重複使用者識別碼( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>)。 </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">在您的CRM系統中指派的不重複使用者識別碼(<a href="../../../reference/ids-in-aam.md"> DPUUID，在Audience Manager </a>中)。 </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">行動作業系統公開之原始且未修改形式的行動Android或iOS裝置ID。 </li> 
     </ul> </p> <p>若為行動ID： </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA格式： ID必須為大寫並且非雜湊。 例如， <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android格式： ID必須為小寫並且非雜湊。 例如， <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>使用單一標籤分隔符號將使用者ID和特徵ID分開。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager </span>特徵識別碼。 我們要求您在傳入資料檔案中僅包含<i>已上線的特徵</i>。 我們不會在傳入資料傳輸中處理任何其他特徵型別。 </p> <p> <p>注意：特徵ID可使用GET方法找到，此方法會傳回所有特徵的詳細資訊。 如需詳細資訊，請參閱<a href="../../../api/rest-api-main/api-traits.md">特徵API方法</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 正在格式化[!UICONTROL Trait IDs] {#formatting-trait-ids}

下表說明在傳入資料檔案中識別[!UICONTROL trait]名稱或ID的前置詞。 如需範例，請參閱[範例檔案](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples)。

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
   <td colname="col2"> <p><code> d_sid </code>首碼會告訴系統，識別碼是<span class="keyword"> Audience Manager </span>特徵ID。 這是顯示在使用者介面中的ID。 您也可以使用API <code> GET </code>方法傳回特徵識別碼。 請參閱<a href="../../../api/rest-api-main/api-traits.md">特徵API方法</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>前置詞為<code> d_unsid </code>的資料會從該特徵中移除使用者。 在<code> d_unsid </code>檔案中忽略<code> overwrite </code>首碼。 </p> <p><code> d_unsid= </code>首碼會告訴系統，識別碼是<span class="keyword"> Audience Manager </span>特徵ID。 這是顯示在使用者介面中的ID。 您也可以使用API <code> GET </code>方法傳回特徵識別碼。 請參閱<a href="../../../api/rest-api-main/api-traits.md">特徵API方法</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules">特徵規則</a>可讓您設定特徵資格條件。 如果您將特徵規則的格式設為<code> ic == trait ID </code>，則可以使用簡單的逗號格式清單來傳送特徵。 </p> <p>例如，假設您建立了這3個特徵規則： </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>這些特徵與<code> ic </code>索引鍵相關聯。 這可讓您在資料檔案中建立更簡單的特徵清單。 而且，您不需要包含<code> ic </code>首碼。 因此，資料檔案的內容可能如下所示： </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>索引鍵值配對 </p> </td> 
   <td colname="col2"> <p>特徵資料可使用英數字串格式化為索引鍵/值組。 有數種方式可格式化機碼值組，如下所示： </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> ，<code> "gender"=m </code> ， <code> model = "pickup truck" </code> ， <code> product = tablet </code>都是格式正確的索引鍵值配對範例。 </p> </td> 
  </tr>
 </tbody>
</table>

## [!UICONTROL Trait IDs]、[!UICONTROL User IDs]和索引鍵值配對中的字元無效 {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs]僅包含數字字元。 我們要求您在傳入資料檔案中僅包含&#x200B;*個[!UICONTROL onboarded traits]*。 我們不會在傳入資料傳輸中處理任何其他[!UICONTROL trait]型別。

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
   <td colname="col2"> <p><i>請勿</i>在DPUUID中使用編碼冒號(<code> %3A </code>)或未編碼冒號( ： )符號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動iOS (IDFA)或Android裝置ID </p> </td> 
   <td colname="col2"> <p>行動裝置ID的格式必須嚴格，如下所示： </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA格式： ID必須為大寫並且非雜湊。 例如， <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android格式： ID必須為小寫並且非雜湊。 例如， <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 索引鍵值配對

機碼值組中的值名稱格式不正確也會造成問題。 在索引鍵/值配對中建立或命名值時，請遵循下列規則：

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字元 </th> 
   <th colname="col2" class="entry"> 需求 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>引號字元(") </p> </td> 
   <td colname="col2"> <p>您可以在索引鍵和索引鍵 — 值組的值部分中使用引號字元，如下所示： </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>虛線字元(-) </p> </td> 
   <td colname="col2"> <p>我們忽略鍵開頭的破折號。 例如，<code> -product = camera </code>會解譯為<code> product = camera </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>不要</i>使用<code> TAB </code>，而非索引鍵值配對中的空白值。 僅使用<code> TAB </code>來分隔傳入資料檔案中的變數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>請勿在索引鍵或值中使用新的行或定位字元( <code> \n, \t </code>)。 </p> </td> 
  </tr>
 </tbody>
</table>

## 資料檔案範例 {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 資料檔案格式 </th> 
   <th colname="col2" class="entry"> 說明與範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>與<code> d_sid </code>或<code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>此資料檔案顯示符合特徵24、26、27資格的使用者，且已從特徵28和29中移除。 </p> <p> 
     <code>
       59767559181262060060278870901087098252&nbsp;&nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>注意：  <p>您也可以使用下列語法，將特徵從使用者設定檔中移除，而不使用d_unsid： </p> <p> 
      <code>
        59767559181262060060278870901087098252&nbsp;28:0,&nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&nbsp;28:-1,&nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>與<code> ic== </code> </p> </td> 
   <td colname="col2"> <p>這些特徵已新增至首碼為<code> ic </code>的特徵規則。 因此，您可以將它們新增至以逗號分隔的資料檔案中，如下所示。 UUID和特徵ID以標籤分隔。 檔案中不需要<code> ic </code>首碼。 </p> <p><b>數值ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&nbsp;&nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>字串ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&nbsp;&nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用索引鍵值配對 </p> </td> 
   <td colname="col2"> 此檔案資料使用機碼值組將資料傳遞至<span class="keyword"> Audience Manager </span>。 <p> 
     <code>
       59767559181262060060278870901087098252&nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

如果需要其他範例，請[下載](assets/ftp_dpm_1234_1445374061.overwrite)範例資料檔案。 下載檔案的副檔名為`.overwrite`。 您可以使用簡單的文字編輯器將其開啟。

## 範例矩陣 {#examples-matrix}

下圖顯示格式化傳入檔案的正確方式範例，取決於[ID型別](../../../reference/ids-in-aam.md)以及要將[!UICONTROL traits]新增至設定檔的方法。

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID型別/作業 </th> 
   <th colname="col2" class="entry"> 使用d_sid將特徵新增至使用者設定檔 </th> 
   <th colname="col3" class="entry"> 使用d_unsid從使用者設定檔中移除特徵 </th> 
   <th colname="col4" class="entry"> 傳入索引鍵值配對，將特徵新增至使用者設定檔 </th> 
   <th colname="col5" class="entry"> 使用ic首碼將特徵新增至使用者設定檔 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>AUDIENCE MANAGER UUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1">範例1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2">範例2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3">範例3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4">範例4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>適用於Android裝置的Google Advertising ID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5">範例5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6">範例6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7">範例7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8">範例8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>適用於iOS裝置的Apple IDFA </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9">範例9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10">範例10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11">範例11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12">範例12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>您自己的CRM ID (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13">範例13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14">範例14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15">範例15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16">範例16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 範例 1 {#example-1}

使用[!UICONTROL trait IDs]傳送[!UICONTROL trait] [!DNL Audience Manager]的[!DNL UUIDs]資格資訊。

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### 範例 2 {#example-2}

使用[!UICONTROL trait IDs]傳送[!UICONTROL trait] [!DNL Audience Manager]的[!DNL UUIDs]取消資格資訊。

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

傳送機碼值組以新增[!UICONTROL trait] [!DNL Audience Manager]的[!DNL UUIDs]資格資訊。

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

或 

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### 範例4 {#example-4}

使用`ic`首碼來傳送[!UICONTROL trait] [!DNL Audience Manager]的[!DNL UUIDs]資格資訊。

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

或 

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### 範例5 {#example-5}

使用[!UICONTROL trait IDs]傳送[!UICONTROL trait]裝置的[!DNL Android]資格資訊。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 範例6 {#example-6}

使用[!UICONTROL trait IDs]傳送[!UICONTROL trait]裝置的[!DNL Android]取消資格資訊。

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

### 範例7 {#example-7}

傳送機碼值組以新增[!UICONTROL trait]裝置的[!DNL Android]資格資訊。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

或 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### 範例8 {#example-8}

使用`ic`首碼來傳送[!UICONTROL trait]裝置的[!DNL Android]資格資訊。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

或 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### 範例9 {#example-9}

使用[!UICONTROL trait IDs]傳送[!UICONTROL trait]裝置的[!DNL iOS]資格資訊。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 範例10 {#example-10}

使用[!UICONTROL trait IDs]傳送[!UICONTROL trait]裝置的[!DNL iOS]取消資格資訊。

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

### 範例11 {#example-11}

傳送機碼值組以新增[!UICONTROL trait]裝置的[!DNL iOS]資格資訊。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

或 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### 範例12 {#example-12}

使用`ic`首碼來傳送[!UICONTROL trait]裝置的[!DNL iOS]資格資訊。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

或 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### 範例13 {#example-13}

使用[!UICONTROL trait IDs]傳送[!UICONTROL trait]的[!DNL DPUUIDs]資格資訊。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 範例14 {#example-14}

使用[!UICONTROL trait IDs]傳送[!UICONTROL trait]的[!DNL DPUUIDs]取消資格資訊。

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

### 範例15 {#example-15}

傳送機碼值組以新增[!UICONTROL trait]的[!DNL DPUUIDs]資格資訊。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

或 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### 範例16 {#example-16}

使用`ic`首碼來傳送[!UICONTROL trait]的[!DNL DPUUIDs]資格資訊。

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
