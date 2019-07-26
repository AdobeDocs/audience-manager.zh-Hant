---
description: 在格式化傳入特徵資料檔案時應遵循的必填欄位、語法和規則。
seo-description: 在格式化傳入特徵資料檔案時應遵循的必填欄位、語法和規則。
seo-title: 傳入資料檔案內容語法、無效字元、變數和範例
solution: Audience Manager
title: 傳入資料檔案內容語法、無效字元、變數和範例
uuid: 88699b29-1502-4183-a9 a4-be70692 a02 bb
translation-type: tm+mt
source-git-commit: 5a822460f93bb7295edafff03104ae7626b69a51

---


# Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

在格式化傳入特徵資料檔案時應遵循的必填欄位、語法和規則。

## File Content Syntax {#file-content-syntax}

傳入資料檔案中的欄位必須以下列順序顯示。In this example, the `<` `>` symbols have been added to help separate each element visually. 您不需要將這些項目包含在資料檔案中。

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

For other accepted file content formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>我們的限制為200行，我們可以處理傳入資料檔案中傳送的每個使用者ID。例如，如果您針對使用者ID傳送300行，則會保留前200行，並捨棄100行。在下列範例中，您是好的，因為您要傳送使用者ID和使用者ID的3行。我們不會針對包含在行中的特性或索引鍵值配對，強制執行限制。
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## File Variables Defined {#file-variables-defined}

表格列出並定義格式正確的傳入資料檔案中使用的變數。*斜體*&#x200B;表示變數預留位置。

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>使用者 ID </i> </code> </p> </td> 
   <td colname="col2"> <p>使用者ID可以是： </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B"><span class="keyword"> Audience Manager </span> 指派的唯一使用者ID( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>)。 </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">A unique user ID assigned in your CRM system ( <a href="../../../reference/ids-in-aam.md"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">行動Android或iOS裝置ID的原始未修改表格，由行動作業系統公開。 </li> 
     </ul> </p> <p>對於行動ID： </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA格式：ID必須大寫且不會雜湊。For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android格式：ID必須是小寫且不會雜湊。For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>使用單一標籤分隔字元分隔使用者ID和特徵ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>特徵ID </i></code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager </span> 特徵ID。We ask that you include <i>only onboarded traits</i> in inbound data files. 我們不會處理傳入資料傳輸中任何其他特徵類型。 </p> <p> <p>注意：您可以使用GET方法，透過傳回所有特性的詳細資訊來尋找特徵ID。For more information, see <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatting Trait IDs {#formatting-trait-ids}

下表說明識別傳入資料檔案中特徵名稱或ID的首碼。See the [sample files](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) for examples.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 首碼 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ sid= </code> </p> </td> 
   <td colname="col2"> <p><code> d_ sid </code> 前置詞會告訴我們的系統ID是 <span class="keyword"> Audience Manager </span> 特徵ID。這與使用者介面中顯示的ID相同。You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_ unsid= </code> </p> </td> 
   <td colname="col2"> <p>Data prefixed with <code> d_unsid </code> removes users from that trait. The <code> d_unsid </code> prefix is ignored in an <code> overwrite </code> file. </p> <p><code> d_ unsid= </code> 前置詞會告訴系統ID是 <span class="keyword"> Audience Manager </span> 特徵ID。這與使用者介面中顯示的ID相同。You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> 特徵規則 </a> 可讓您設定特徵資格的標準。If you format a trait rule as <code> ic == trait ID </code>, you can send in traits in a simple comma formatted list. </p> <p>例如，假設您建立了這個特徵規則： </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic==「123」 </code> </li>
      <li> <code> ic==「456」 </code> </li>
      <li> <code> ic==「789」 </code> </li>
     </ul> </p> <p>These traits are associated with the <code> ic </code> key. 這可讓您在資料檔案中建立更簡單的特徵清單。And, you do not need to include the <code> ic </code> prefix. 因此，您的資料檔案內容可能如下所示： </p> <p>
     <code><i>使用者ID</i>&lt; TAB&gt;123,456,789 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>索引鍵值配對 </p> </td> 
   <td colname="col2"> <p>特徵資料可使用英數字串格式格式設定為索引鍵值配對。格式化索引鍵值對有幾種方式，如下所示： </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key= value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> 「key」= value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key=「value」 </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> 「key」=「value」 </code> </li> 
     </ul><code> 「age」=「32」 </code> 、 <code> 「性別」= m </code> 、 <code> model=「cick truck」 </code> ， <code> product= tablet </code> 是正確格式化索引鍵值配對的所有範例。 </p> </td> 
  </tr>
 </tbody>
</table>

## Invalid Characters in Trait IDs, User IDs and Key-Value Pairs {#invalid-chars}

### 特徵ID

特徵ID僅包含數字字元。We ask that you include *only onboarded traits* in inbound data files. 我們不會處理傳入資料傳輸中任何其他特徵類型。

### 使用者 ID

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
   <td colname="col2"> <p><i>請勿</i> 使用編碼的冒號( <code> %3A </code>)或未編碼的冒號(：)中的符號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動iOS(IDFA)或Android裝置ID </p> </td> 
   <td colname="col2"> <p>行動裝置ID必須嚴格格式化，如下所示： </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA格式：ID必須大寫且不會雜湊。For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android格式：ID必須是小寫且不會雜湊。For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 索引鍵值配對

關鍵值配對中不正確的格式化值名稱也會造成問題。建立或命名索引鍵值對中的值時，請遵循下列規則：

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字元 </th> 
   <th colname="col2" class="entry"> 需求 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>引述字元(」) </p> </td> 
   <td colname="col2"> <p>您可以在索引鍵中使用引號字元，並在索引鍵值配對的值中使用值，例如： </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_ city=「New York」，d_ city=「San Francisco」 </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> 「d_ city」=「New York」，「d_ city」=「San Francisco」 </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>破折號字元(-) </p> </td> 
   <td colname="col2"> <p>我們忽略按鍵開頭的虛線。For example, <code> -product = camera </code> is interpreted as <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>請勿</i> 在關鍵值配對中使用 <code> TAB </code> 而非空值。Only use <code> TAB </code> to separate variables in the inbound data file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \ n，\ t </code> </p> </td> 
   <td colname="col2"> <p>Do not use the new line or tab characters ( <code> \n, \t </code>) in keys or in values. </p> </td> 
  </tr>
 </tbody>
</table>

## Data File Examples {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 資料檔案格式 </th> 
   <th colname="col2" class="entry"> 說明與範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>With <code> d_sid </code> or <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>此資料檔案顯示符合特性24、26、27並已從特徵28和29移除的使用者。 </p> <p> 
     <code>5976755918620620670090870090082598252&amp; amp；nbsp；&amp; amp；nbsp；d_ sid=24，d_ sid=26，d_ sid=27，d_ unsid=28，d_ unsid=29 </code>
  </p> <p>注意:  <p>您也可以使用下列語法從使用者描述檔移除特性，而不使用d_ unsid： </p> <p> 
      <code>5976755918620620670090870090082598252&amp; amp；nbsp；28：00與amp；nbsp；29：0 </code>
  </p> <p> 
      <code>5976755918620620670090870090082598252&amp; amp；nbsp；28：1與amp；nbsp；29：-1 </code>
  </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>With <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>These traits have been added to a trait rule with the <code> ic </code> prefix. 因此，您可以將它們新增至以逗號分隔的資料檔案。標籤會分隔UUID和特徵ID。The <code> ic </code> prefix is not required in the file. </p> <p><b>數值ID</b> </p> <p> 
     <code>DBWLogic3DHFMCFHBHB2M4F9ZKJExnrRDD2PXVI1&amp; amp；nbsp；&amp; amp；nbsp；30608,50354,50338,50352,30626 </code>
  </p> <p><b>字串ID</b> </p> <p> 
     <code>DBWLogic3DHFMCFHBHB2M4F9ZKJExnrRDD2PXVI1&amp; amp；nbsp；&amp; amp；nbsp；ic=52，ic=55 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>有索引鍵值配對 </p> </td> 
   <td colname="col2"> This file data uses key-value pairs to pass in data to <span class="keyword"> Audience Manager </span>. <p> 
     <code>5976755918620620670090870090082598252&amp; amp；nbsp；「性別」=「女性」，「奢華_ operper」=「yes」 </code>
  </p> </td> 
  </tr> 
 </tbody> 
</table>

[如果](assets/ftp_dpm_1234_1445374061.overwrite) 需要其他範例，請下載範例資料檔案。The download file has a `.overwrite` file extension. 您可以使用簡單的文字編輯器來開啓。

## Examples Matrix {#examples-matrix}

The chart below shows examples of the correct way to format your Inbound files, depending on the [type of IDs](../../../reference/ids-in-aam.md) and the method by which you want to add traits to profiles.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID類型/操作 </th> 
   <th colname="col2" class="entry"> 使用d_ sid新增特性至使用者描述檔 </th> 
   <th colname="col3" class="entry"> 使用d_ unsid從使用者描述檔移除特徵 </th> 
   <th colname="col4" class="entry"> 傳入索引鍵值配對，以新增特性至使用者描述檔 </th> 
   <th colname="col5" class="entry"> 使用ic首碼新增特性至使用者描述檔 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> 範例 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> 範例 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> 範例3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> 範例4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Android裝置的Google Advertising ID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> 範例5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> 範例6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> 範例7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> 範例8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>iOS裝置適用的Apple IDFA </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> 範例9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> 範例10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> 範例11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> 範例12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>您自己的CRM ID(DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> 範例13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> 範例14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> 範例15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> 範例16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Example 1 {#example-1}

使用特徵ID來傳送Audience Manager UUID的特徵資格資訊。

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Example 2 {#example-2}

使用特徵ID傳送Audience Manager UUID的特徵免資格資訊。

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

### Example 3 {#example-3}

以索引鍵值配對傳送，為Audience Manager UUID新增特徵資格資訊。

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

或 

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

使用ic首碼來傳送Audience Manager UUID的特徵資格資訊。

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

或 

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

使用特徵ID來傳送適用於Android裝置的特徵資格資訊。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

使用特徵ID為Android裝置傳送特徵不合格資訊。

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

### Example 7 {#example-7}

以索引鍵值配對傳送，為Android裝置新增特徵資格資訊。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

或 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

使用ic首碼來傳送適用於Android裝置的特徵資格資訊。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

或 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

使用特徵ID來傳送iOS裝置適用的特徵資格資訊。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

使用特徵ID為iOS裝置傳送特徵不合格資訊。

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

### Example 11 {#example-11}

以索引鍵值配對傳送，為iOS裝置新增特徵資格資訊。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

或 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

使用ic首碼傳送iOS裝置適用的特徵資格資訊。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

或 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

使用特徵ID為DPUUID傳送特徵資格資訊。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

使用特徵ID傳送特徵不合格的dpuuID資訊。

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

### Example 15 {#example-15}

在索引鍵值配對中傳送，為DPUUID新增特徵資格資訊。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

或 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

使用ic首碼傳送適用於DPUUID的特徵資格資訊。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

或 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORE_贊_ this]
>
>* [特徵產生器](../../../features/traits/about-trait-builder.md)

