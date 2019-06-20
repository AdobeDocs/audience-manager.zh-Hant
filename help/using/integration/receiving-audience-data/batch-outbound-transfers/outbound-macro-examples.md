---
description: 一些常見巨集如何用來建立對外檔案範本的範例。
seo-description: 一些常見巨集如何用來建立對外檔案範本的範例。
seo-title: 輸出巨集範例
solution: Audience Manager
title: 輸出巨集範例
uuid: 823d85d4-d683-45cf-9e60-c12 b7 d52 a498
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 輸出巨集範例 {#outbound-macro-examples}

一些常見巨集如何用來建立對外檔案範本的範例。

>[!NOTE]
>
>In the tables, **boldface** type identifies each macro with its related output. For the format examples, the `<` `>` symbols have been added to help visually separate each macro.

## File Name Macros {#file-name-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_B5073597219B470298EE614902DACAE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 巨集 </th> 
   <th colname="col2" class="entry"> 格式與輸出範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_215_ 888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_ DPID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_215_888_ 20915_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_ 215_888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 同步_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>輸出： </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">Full: <code> ftp_215_888_ full_1449756724.sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">Incremental: <code> ftp_215_888_ iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 同步_類型 </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>輸出： </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP: <code> ftp_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3: <code> s3_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 時間戳記 </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;_&lt;admin&gt;&lt;.sync&gt; </code> </p> <p>Output: <code> ftp_215_888_iter_ 1449756724.sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header Row Macros {#header-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 巨集 </th> 
   <th colname="col2" class="entry"> 格式與輸出範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;ORDER_ID&gt; &lt;TAB&gt;&lt;SYNC_TYPE&gt; </code> </p> <p>Output: <code> 888 full.sync </code> </p> <p>在輸出中，非列印標籤字元會分隔每個元素。 </p> </td>
  </tr>
 </tbody>
</table>

## File Content Macros {#file-content-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 巨集 </th> 
   <th colname="col2" class="entry"> 格式與輸出範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUID </code> </p> </td> 
   <td colname="col2"> <p>請參閱下方的個別章節。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 已移除_ SERGE_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt; &lt;REMOVED_SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Segment_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt; &lt;SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SESION_ LIST&amp;&amp; REEMENT_ SERGE_ LIST) endif </code> </p> </td> 
   <td colname="col2"> <p><b>格式:</b> </p> <p> 
     <code>{「adadtiserId」：「&lt; PIDALAS&gt;」、「dataEnterId」：2，「TID」：「&lt; DP_ UUID&gt;」、「資料」：[&lt; SERGE_ LIST：{seg|&lt; OPEN_ CURLY_ CASTAR&gt;「名稱」：「&lt; seg. alias&gt;&lt; CLOSE_ Curly_ CASC&gt;}；distracter=」，」&gt;&lt; if(SLOME_ LIST&amp;&amp; ENDEMENT_ SERGE_ LIST)&gt;&lt; COMA&gt;&lt; endif&gt;&lt; REEMERATED_ SERGE_ LIST：{seg|&lt; OPEN_ CURLY_ CASTAR&gt;「名稱」：「&lt; seg. alias&gt;」，「ttlineMines」：&lt; CLOSE_ CurLY_ CASTALL&gt;}；separator=」，&gt;]} </code>
 </p><p><b>輸出：</b></p> <p>
     <code>//First範例{「adadserId」：「12345」、「dataEnterId」：2，「TID」：「dfd215e4-8d6b-4fdb-90b9-fab4456 f2 c9 d」，「資料」：[{「Name」：「4321」}]}//Second範例{「adadtiserv」：「12345」、「dataEnterId」：2，「TID」：「9099e8-abab-5114-aba-28bdaa0539 ca」，「資料」：[{「Name」：「4321」}、{「Name」：「987」，「ttlineMines」：0}，{「Name」：「654」，「ttlineMines」：0}]} </code>
 </p> <p> <p>Note:  In the first example, the macro only returns data for <code> SEGMENT_LIST </code> because <code> REMOVED_SEGMENT_LIST </code> is empty. 第二個範例會傳回兩個巨集的資料。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ TICETS </code> </p> </td> 
   <td colname="col2"> <p>格式: </p> <p> <code> &lt; PID&gt;&lt; TAB&gt;&lt; UUID&gt;&lt; UUID&gt;&lt; TAB&gt;&lt; DP_ UUID&gt;&lt; TAB&gt;&lt; SET_ TELICES&gt;&lt; TAB&gt;&lt; OPT_ OUT&gt;&lt; TAB&gt;&lt; SECTION_ LIST：{seg|&lt; seg. type&gt;，&lt; seg. alias&gt;，&lt; OUTPUT_ Attribute_ Value&gt;，&lt; seg. ladpdateTime&gt;&amp;}&gt; </code> </p> <p>輸出： </p> <p> <code> 11590008800857968836968564574151629750975075000，17t0aj01b120p1，11247114,1,1343114,1,1343250,1,1343250661000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> <p>在輸出中，非列印標籤字元會分隔每個元素。 </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> TRAIT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator="|"&gt; </code> </p> <p>Output: <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID` 範例

To help you understand how the `DPUUID` macro outputs data, lets assume we have 2 `DPID`s mapped to `DPUUID`s as shown below:

* DPID `1111` maps to DPUUIDs `AAAA` (timestamp = 1) and `BBBB` (timestamp = 2).
* DPID `2222` maps to DPUUID `CCCC`.

根據這些條件，下表列舉一些可能的格式字串及其輸出。

<table id="table_6A6D94F994C1475BB09126BA0B815B1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對應條件 </th> 
   <th colname="col2" class="entry"> 巨集格式 </th> 
   <th colname="col3" class="entry"> 輸出 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>針對單一DPID傳回所有對應 </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUID；format=「dpids=1111| maxMapTPS=0| format= json」&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [[「1111」、「AAAA」]、[「1111」、「BBB」]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>針對所有DPIDs傳回最多個對應 </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUID；format=「dpids=1111,2222| maxMapTPS=1| format= json」&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [[「1111」、「BBB」]、[「2222」、「CCCC」]] </code> </p> <p>For DPID <code> 1111 </code>, the macro maps to DPUUID <code> BBBB </code> only because that ID has the larger timestamp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>針對單一DPID傳回最多個映射 </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUID；format=「dpids=2222| maxMapTPS=2| format= json」&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [[「222」、「CCCC」]] </code> </p> <p><code> 即使maxMATPTS=2 </code>，此巨集只會傳回1DPID至DPUUID對應，因為指定的DPID只有一個DPUUID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

[輸出範本巨集](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)