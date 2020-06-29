---
description: 格式化傳入特徵資料檔案時，您應遵循的必填欄位、語法和規則。
seo-description: 格式化傳入特徵資料檔案時，您應遵循的必填欄位、語法和規則。
seo-title: 傳入資料檔案內容語法、無效字元、變數和範例
solution: Audience Manager
title: 傳入資料檔案內容語法、無效字元、變數和範例
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 4%

---


# 傳入資料檔案內容：語法、無效字元、變數和範例 {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

格式化傳入特徵資料檔案時，您應遵循的必填欄位、語法和規則。

## 檔案內容語法 {#file-content-syntax}

傳入資料檔案中的欄位必須依下列順序顯示。 在此範例中，已新增 `<` 符號， `>` 以協助以視覺化方式分隔每個元素。 您不需要將這些項目納入資料檔案中。

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

如需其他接受的檔案內容格式，請參閱自 [訂合作夥伴整合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

>[!NOTE]
>
>對於傳入資料檔案中傳送的每個使用者ID，我們可處理的行數上限為200行。 例如，如果您傳送300行作為使用者ID，則會保留前200行，並捨棄其他100行。 在以下範例中，您很好，因為您會針對使用者ID 1和使用者ID 2分別傳送3行。 我們不會對您在行中包含的特徵或索引鍵值配對數目實施限制。
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

該表列出並定義了格式正確的傳入資料檔案中使用的變數。 *斜體*&#x200B;表示變數預留位置。

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
      <li id="li_23829FE2F6464E33859B3E388FCD106B">由Audience Manager指派的唯一 <span class="keyword"> 使用者ID </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>)。 </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">在您的CRM系統中指派的唯一使用者ID( <a href="../../../reference/ids-in-aam.md"> Audience Manager中的DPUUID </a>)。 </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">行動作業系統公開的行動Android或iOS裝置ID，其原始未修改的格式。 </li> 
     </ul> </p> <p>針對行動ID: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA格式： ID必須大寫，而非雜湊。 例如， <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android格式： ID必須小寫，而非雜湊。 例如， <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>使用單一標籤分隔字元分隔使用者ID和特徵ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Audience Manager <span class="keyword"> 特 </span> 徵ID。 我們要求您在傳入的資 <i>料檔案中僅包含已登入的特徵</i> 。 我們不會處理傳入資料傳輸中的任何其他特徵類型。 </p> <p> <p>注意：  可使用GET方法來尋找「特徵ID」，該方法會傳回所有特徵的詳細資訊。 如需詳細資訊，請參 <a href="../../../api/rest-api-main/api-traits.md"> 閱特徵API方法 </a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 格式 [!UICONTROL Trait IDs] {#formatting-trait-ids}

下表說明了用於標識傳入資料 [!UICONTROL trait] 檔案中的名稱或ID的前置詞。 如需範例， [請參閱範例檔](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) 。

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 首碼 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p>首 <code> d_sid </code> 碼會告訴我們的系統ID是 <span class="keyword"> Audience Manager特 </span> 徵ID。 這是使用者介面中顯示的相同ID。 您也可以使用API方法傳回特徵 <code> GET </code> ID。 See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>前置詞為的資 <code> d_unsid </code> 料會從該特徵中移除使用者。 檔案 <code> d_unsid </code> 中將忽略前置詞 <code> overwrite </code> 。 </p> <p>首 <code> d_unsid= </code> 碼會告訴我們的系統ID是 <span class="keyword"> Audience Manager特 </span> 徵ID。 這是使用者介面中顯示的相同ID。 您也可以使用API方法傳回特徵 <code> GET </code> ID。 See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> 特徵規則 </a> 可讓您設定特徵資格的准則。 如果您將特徵規則格式化為 <code> ic == trait ID </code>，則可以以簡單的逗號格式清單傳送特徵。 </p> <p>例如，假設您建立這3個特徵規則： </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>這些特徵與密鑰相 <code> ic </code> 關聯。 這可讓您在資料檔案中建立更簡單的特徵清單。 而且，您不需要加入首 <code> ic </code> 碼。 因此，您的資料檔案內容可能如下所示： </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>鍵值對 </p> </td> 
   <td colname="col2"> <p>特徵資料可使用英數字串格式化為鍵值配對。 有幾種格式化鍵值對的方法，如下所示： </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> 、 、 <code> "gender"=m </code> 、 <code> model = "pickup truck" </code> 、 <code> product = tablet </code> 都是格式正確的鍵值對的示例。 </p> </td> 
  </tr>
 </tbody>
</table>

## 無效的字 [!UICONTROL Trait IDs]元和 [!UICONTROL User IDs] 鍵值配對 {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] 只包含數字字元。 我們要求您僅將內 *嵌[!UICONTROL onboarded traits]*資料檔案納入傳入。 我們不會處理傳入[!UICONTROL trait]資料傳輸中的任何其他類型。

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
   <td colname="col2"> <p><i>請勿使用</i> 「編碼」冒號( <code> %3A </code>)或「未編碼」冒號(: )符號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動iOS(IDFA)或Android裝置ID </p> </td> 
   <td colname="col2"> <p>行動裝置ID必須嚴格格式化，如下所示： </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA格式： ID必須大寫，而非雜湊。 例如， <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android格式： ID必須小寫，而非雜湊。 例如， <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 鍵值對

鍵值對中的值名稱格式不正確也會導致問題。 建立或命名鍵值對中的值時，請遵循以下規則：

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
   <td colname="col2"> <p>您可以在鍵和鍵值對的值部分使用引號字元，例如： </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>破折號字元(-) </p> </td> 
   <td colname="col2"> <p>我們忽略鍵開頭的破折號。 例如， <code> -product = camera </code> 被解釋為 <code> product = camera </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>請勿在鍵</i> -值 <code> TAB </code> 配對中使用空值，而不使用空值。 僅用於 <code> TAB </code> 分隔傳入資料檔案中的變數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>請勿在鍵或值中使用新的行或 <code> \n, \t </code>制表符字元()。 </p> </td> 
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
   <td colname="col1"> <p>使用 <code> d_sid </code> 或 <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>此資料檔案顯示符合特徵24、26、27的使用者，且已從特徵28和29移除。 </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>注意:  <p>您也可以使用下列語法，從使用者描述檔移除特徵，而不是使用d_unsid: </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>包含 <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>這些特徵已新增至具有首碼的特徵 <code> ic </code> 規則。 因此，您可以將檔案新增至資料檔案，並以逗號分隔，如所示。 標籤可分隔UUID和特徵ID。 檔 <code> ic </code> 案中不需要前置詞。 </p> <p><b>數值ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>字串ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>具有鍵值對 </p> </td> 
   <td colname="col2"> 此檔案資料使用金鑰值配對，將資料傳入 <span class="keyword"> Audience Manager </span>。 <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[如果您需要](assets/ftp_dpm_1234_1445374061.overwrite) 其他範例，請下載範例資料檔案。 下載檔案的副檔 `.overwrite` 名為。 您可以使用簡單的文字編輯器來開啟它。

## 範例矩陣 {#examples-matrix}

下圖顯示了正確格式化傳入檔案的範例，視ID類 [型](../../../reference/ids-in-aam.md) ，以及您要新增至描述檔的 [!UICONTROL traits] 方法而定。

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID類型／操作 </th> 
   <th colname="col2" class="entry"> 使用d_sid將特徵新增至使用者設定檔 </th> 
   <th colname="col3" class="entry"> 使用d_unsid從使用者設定檔移除特徵 </th> 
   <th colname="col4" class="entry"> 傳送索引鍵值配對，以新增特徵至使用者描述檔 </th> 
   <th colname="col5" class="entry"> 使用ic首碼將特徵新增至使用者描述檔 </th> 
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
   <td colname="col1"> <p>Android裝置專用的Google廣告ID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> 範例5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> 範例6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> 範例7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> 範例8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>iOS裝置專用的Apple IDFA </p> </td> 
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

使用 [!UICONTROL trait IDs] 來傳送 [!UICONTROL trait] 資格資訊 [!DNL Audience Manager][!DNL UUIDs]。

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Example 2 {#example-2}

用 [!UICONTROL trait IDs] 於發送 [!UICONTROL trait] 取消資格資訊 [!DNL Audience Manager][!DNL UUIDs]。

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

傳送索引鍵值配對，以新增 [!UICONTROL trait] 資格資訊 [!DNL Audience Manager][!DNL UUIDs]。

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

或 

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

使用首 `ic` 碼傳送 [!UICONTROL trait] 資格資訊 [!DNL Audience Manager][!DNL UUIDs]。

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

或 

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

使用 [!UICONTROL trait IDs] 來傳送 [!UICONTROL trait] 裝置的資格 [!DNL Android] 資訊。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

使用 [!UICONTROL trait IDs] 傳送裝 [!UICONTROL trait] 置的取消資格 [!DNL Android] 資訊。

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

傳送金鑰值配對，以新增裝 [!UICONTROL trait] 置的資格 [!DNL Android] 資訊。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

或 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

使用首 `ic` 碼來傳送裝 [!UICONTROL trait] 置的資格 [!DNL Android] 資訊。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

或 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

使用 [!UICONTROL trait IDs] 來傳送 [!UICONTROL trait] 裝置的資格 [!DNL iOS] 資訊。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

使用 [!UICONTROL trait IDs] 傳送裝 [!UICONTROL trait] 置的取消資格 [!DNL iOS] 資訊。

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

傳送金鑰值配對，以新增裝 [!UICONTROL trait] 置的資格 [!DNL iOS] 資訊。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

或 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

使用首 `ic` 碼來傳送裝 [!UICONTROL trait] 置的資格 [!DNL iOS] 資訊。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

或 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

使用 [!UICONTROL trait IDs] 來傳送 [!UICONTROL trait] 的資格資訊 [!DNL DPUUIDs]。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

用 [!UICONTROL trait IDs] 於發送 [!UICONTROL trait] 取消資格資訊 [!DNL DPUUIDs]。

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

傳送索引鍵值配對，以新增 [!UICONTROL trait] 資格資訊 [!DNL DPUUIDs]。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

或 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

使用首 `ic` 碼來傳送 [!UICONTROL trait] 的資格資訊 [!DNL DPUUIDs]。

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

