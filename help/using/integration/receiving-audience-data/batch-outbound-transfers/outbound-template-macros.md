---
description: 列出可用來建立對外範本的巨集。這些檔案名稱包括檔案名稱巨集、標題巨集和內容巨集。
seo-description: 列出可用來建立對外範本的巨集。這些檔案名稱包括檔案名稱巨集、標題巨集和內容巨集。
seo-title: 輸出範本巨集
solution: Audience Manager
title: 輸出範本巨集
uuid: dec082d3-306b-4ff5-afb2-418bd543 d0 d0
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# 輸出範本巨集 {#outbound-template-macros}

列出可用來建立對外範本的巨集。這些檔案名稱包括檔案名稱巨集、標題巨集和內容巨集。

## 檔案名稱和檔案標題巨集 {#file-name-header-macros}

表格列出並說明您可以在檔案名稱中使用的巨集，以及定義標題欄位。如需程式碼範例，請參閱 [「輸出巨集範例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)」。

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 巨集 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_ SOH </code> </p> </td> 
   <td colname="col2"> <p>非列印ASCII字元。它表示一列或一個內容區段的開頭。它也可以用來分隔檔案中的資料欄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_ DPID </code> </p> </td> 
   <td colname="col2"> <p>使用者ID金鑰資料提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>訂單/目的地ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ ALIAS </code> </p> </td> 
   <td colname="col2"> <p>訂單/目的地ID的別名。 </p> <p>別名已設定在管理UI中。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNum </code> </p> </td> 
   <td colname="col2"> <p>表示將傳出檔案分割為多個部分。以零件編號取代檔案名稱中的SPLITNUM區段，零件編號為零，確保SITLUM區段最少個字元。</p>
   <p>SPLITNUM巨集不需要被&lt;&gt;字元包圍。</p><p>範例： <code>&lt; Sync_ TYPE&gt;_&lt; ORDER_ ID&gt;_&lt; DPID&gt;_&lt; SYXCH_ MODE&gt;_&lt;時間戳記&gt; SPITNUM. csv</code>
<p>s3_123456_9999_ full_1566906141001.csv</p> 
<p>s3_123456_9999_ full_1566906142.csv</p> 
<p>s3_123456_9999_ full_15669061431003.csv</p> 
<p>上述範例中的最後三位數(001,002,003)為SPLITNum識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 同步_ MODE </code> </p> </td> 
   <td colname="col2"> <p>指出同步類型並包括： </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> 完整 </code>：完全同步。 </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> ier </code>：漸進式同步。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 同步_類型 </code> </p> </td> 
   <td colname="col2"> <p>指出資料傳輸方法並包括： </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>作為分隔符號，此巨集會在欄位之間插入標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 時間戳記 </code> </p> </td> 
   <td colname="col2"> <p>10位數、UTC、Unix時間戳記。 </p> <p>它也可以格式化為 <code> &lt; TimeSTAMP；format=「yyyYMMDHHMSS」&gt; </code> 遵循Java日期/時間戳記格式規則。 </p> </td> 
  </tr>

</tbody> 
</table>

## 內容巨集 {#content-macros}

用於格式化資料檔案內容的巨集。如需程式碼範例，請參閱 [「輸出巨集範例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)」。

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 巨集 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CONTRY_ CLUEY_ CASTAR </code> </p> </td> 
   <td colname="col2"> <p>插入關閉的大括號}字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> 資料提供者唯一使用者識別碼 </span>。 </p> <p>這是您傳送資料至傳出檔案中之資料合作夥伴的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID_ LIST </code> </p> </td> 
   <td colname="col2"> <p>傳回包含資料合作夥伴多個ID的清單。如果您擁有一個大型組織，具有多個分部或其他可與您共用資料的組織群組，這個情況很有用。此巨集會傳回這些下屬群組的ID清單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUID </code> </p> </td> 
   <td colname="col2"> <p>此巨集的輸出會將資料提供者ID(DPID)對應至相關的唯一使用者ID(DPUUID)。此巨集必須具有格式字串，才能控制其輸出。範例輸出看起來類似下列： </p> <p> <code> 「dpids= dpid1，dpid2，… dpid n| maxMapTypes= n| format= json」 </code> </p> <p><code> maxMapping </code> 設定會決定您希望巨集傳回多少映射。<code> 當maxMATPapping=0 </code>時，此巨集會傳回每個指定DPID的所有對應。資料會按照時間戳記(最近一個)排序，並傳回具有最大時間戳記的結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SESION_ LIST&amp;&amp; REEMENT_ SERGE_ LIST) endif </code> </p> </td> 
   <td colname="col2"> <p>此巨集組合會建立條件陳述式，列出使用者屬於並已移除的區段。如果兩個條件都未符合或沒有資料，它會傳回空字串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Open_ Curly_ ASTAR </code> </p> </td> 
   <td colname="col2"> <p>插入一個開放的大括號{字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_ OUT </code> </p> </td> 
   <td colname="col2"> <p>不再提倡。請勿使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>訂單或目的地ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Output_ Attribute_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>不再提倡。請勿使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Output_ Attribute_ Value </code> </p> </td> 
   <td colname="col2"> <p>傳回 <code> 靜態 </code> 、硬式編碼值1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>合作夥伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALAS </code> </p> </td> 
   <td colname="col2"> <p>訂單/目的地ID的別名。 </p> <p>別名已設定在管理UI中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 已移除_ SERGE_ LIST </code> </p> </td> 
   <td colname="col2"> <p>傳回已移除的區段清單(如果有的話)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Segment_ LIST </code> </p> </td> 
   <td colname="col2"> <p>傳回清單中的區段清單。接受下列選擇性引數： </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> Segmentid </code>：區段ID。不再提倡。使用 <code> sid </code>。 </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>：客戶區段ID。不再提倡。使用 <code> sid </code>。 </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>：區段ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>：傳回 <code> 個 </code>靜態硬碼值，將資料識別為區段資料。 </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> 別名 </code>：已過時。請勿使用。 </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> laxpdateTime </code>：Unix時間戳記，指出上次區段的實現時間。 </li> 
    </ul> <p>將這些變數放入巨集後面的巨括號後面。例如，此程式碼會將結果與垂直號分隔」|「字元： <code> &lt; SERGE_ LIST：{seg|&lt; seg. type&gt;，&lt; seg. sid&gt;}；separator=」，&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ TICETS </code> </p> </td> 
   <td colname="col2"> <p>傳回 <code> 1 </code>，作為靜態的硬式編碼值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 同步_ MODE </code> </p> </td> 
   <td colname="col2"> <p>指出同步類型並包括： </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> 完整 </code>：完全同步。 </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> ier </code>：漸進式同步。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 同步_類型 </code> </p> </td> 
   <td colname="col2"> <p>指出資料傳輸方法並包括： </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>作為分隔符號，此巨集會在欄位之間插入標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>傳回特性清單。接受下列選擇性引數： </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>：依數值ID識別特徵類型。傳回: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 用於 </code> 識別傳入工作的DPM特徵(離線、上線)。 </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 用來識別規則型特徵(透過DCS登入)的3 </code> 。 </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> TraiID </code>：特徵ID。 </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> 已實現 </code>：最後一次實現特徵。Unix時間戳記。 </li> 
    </ul> <p>將這些變數放入巨集後面的巨括號後面。例如，此程式碼會將結果與垂直號分隔。|「字元： <code> &lt; TRAIT_ LIST：{traines|&lt; traces. id&gt;，&lt; traces. lastImplementation&gt;}；separator=」，」 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> 使用者ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [輸出巨集範例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

