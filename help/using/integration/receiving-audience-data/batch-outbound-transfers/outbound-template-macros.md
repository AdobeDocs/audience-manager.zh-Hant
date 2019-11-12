---
description: 列出可用於建立出站模板的宏。 這些宏包括檔案名宏、標題宏和內容宏。
seo-description: 列出可用於建立出站模板的宏。 這些宏包括檔案名宏、標題宏和內容宏。
seo-title: 輸出範本巨集
solution: Audience Manager
title: 輸出範本巨集
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
translation-type: tm+mt
source-git-commit: 94984d14be6febf4de3ee3e0e79fba432e1cb15f

---


# 輸出範本巨集 {#outbound-template-macros}

列出可用於建立出站模板的宏。 這些宏包括檔案名宏、標題宏和內容宏。

## 檔案名和檔案標題宏 {#file-name-header-macros}

該表列出並說明了可在檔案名中使用的宏，以及定義標題欄位。 如需程式碼範例，請參 [閱對外巨集範例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)。

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>非列印ASCII字元。 它指示行或內容部分的開始。 它也可用來分隔檔案中的資料欄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>使用者ID金鑰資料提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> 允許為出站訂單建立多行題頭。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>訂單／目標ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>訂單／目標ID的別名。 </p> <p>別名是在管理員UI中設定。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>表示將出站檔案拆分為多個部分。 將檔案名中的SPLITNUM部分替換為零件編號前面帶零，確保SPLITNUM部分至少有三個字元。</p>
   <p>SPLITNUM宏不需要由&lt;&gt;字元包圍。</p><p>範例: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>上述範例中的最後三位(001,002,003)是SPLITNUM識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>指示同步類型並包括： </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>:完全同步。 </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>:增量同步。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>表示資料傳輸方法，包括： </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>此巨集用作分隔符號，可在欄位之間插入索引標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>10位數的UTC、Unix時間戳記。 </p> <p>也可以按照Java日期／時 <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> 間戳格式規則進行格式化。 </p> </td> 
  </tr>

</tbody> 
</table>

## 內容巨集 {#content-macros}

用於格式化資料檔案內容的宏。 如需程式碼範例，請參 [閱對外巨集範例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)。

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>插入右括弧}字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> 資料提供者唯一使用者識別 </span>碼。 </p> <p>這是您在傳出檔案中傳送資料給的資料合作夥伴的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>傳回包含資料合作夥伴多個ID的清單。 如果您有一個大型組織，其中包含多個子組織或允許您與其共用資料的其他組織組，則此功能非常有用。 此巨集會傳回這些附屬群組的ID清單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>此巨集的輸出會將資料提供者ID(DPID)對應至相關的唯一使用者ID(DPUUID)。 此宏必須具有格式字串才能控制其輸出。 範例輸出看起來類似下列： </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p>設 <code> maxMappings </code> 置確定要返回宏的映射數。 當 <code> maxMappings=0 </code>時，此宏返回每個指定DPID的所有映射。 資料會依時間戳記（最新的先行）排序，並傳回最大時間戳記優先的結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>此宏組合會建立條件語句，列出用戶屬於和已從中刪除的段。 如果兩個條件都不符合或沒有資料，則會傳回空字串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>插入一個左括弧{字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>不再提倡。請勿使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>訂單或目標ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>不再提倡。請勿使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>傳回 <code> 1 </code> 為靜態、硬式編碼值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>合作夥伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>訂單／目標ID的別名。 </p> <p>別名是在管理員UI中設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>傳回已移除的區段清單（如果有）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>傳回清單中的區段清單。 接受以下可選參數： </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>:區段ID。 不再提倡。使用 <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>:客戶區段ID。 不再提倡。使用 <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>:區段ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>:傳回 <code> 5 </code>靜態、硬式編碼值，將資料識別為區段資料。 </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: 已過時. 請勿使用。 </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>:Unix時間戳記，指示上次實現段的時間。 </li> 
    </ul> <p>將這些變數放在巨集後面的大括弧中。 例如，此程式碼會以垂直號"|"字元分隔結果： <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>傳 <code> 1 </code>回靜態、硬式編碼值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>指示同步類型並包括： </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>:完全同步。 </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>:增量同步。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>表示資料傳輸方法，包括： </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>此巨集用作分隔符號，可在欄位之間插入索引標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>傳回特徵清單。 接受以下可選參數： </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>:依數值ID識別特徵類型。 傳回: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> 識別DPM特徵（離線，由傳入工作加入）。 </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> 識別規則型特徵（即時，透過DCS登入）。 </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>:特徵ID。 </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>:上次這個特徵實現時。 Unix時間戳記。 </li> 
    </ul> <p>將這些變數放在巨集後面的大括弧中。 例如，此程式碼會以垂直號"|"字元分隔結果： <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager使 </span> 用者ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [輸出巨集範例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

