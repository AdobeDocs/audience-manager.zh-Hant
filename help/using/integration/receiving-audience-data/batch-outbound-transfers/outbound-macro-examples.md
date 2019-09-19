---
description: 一些常用宏用於建立出站檔案模板的示例。
seo-description: 一些常用宏用於建立出站檔案模板的示例。
seo-title: 輸出巨集範例
solution: Audience Manager
title: 輸出巨集範例
uuid: 823d85d4-d683-45cf-9e60-c12b7d52a498
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 輸出巨集範例 {#outbound-macro-examples}

一些常用宏用於建立出站檔案模板的示例。

>[!NOTE]
>
>在表中，粗體 **類型** (boldface type)用其相關輸出標識每個宏。 對於格式示例，已添 `<` 加了符 `>` 號以幫助以視覺化方式分隔每個宏。

## 檔案名宏 {#file-name-macros}

有關可用宏和定義的清單，請參 [閱出站模板宏](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)。

<table id="table_B5073597219B470298EE614902DACAE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 格式和輸出示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>輸出： <code> ftp_215_ 888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>輸出： <code> ftp_215_888_ 20915_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>輸出： <code> ftp_ 215_888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>輸出： </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">完整： <code> ftp_215_888_ full_1449756724.sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">增量： <code> ftp_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>輸出： </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP: <code> ftp_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3: <code> s3_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 時間戳記 </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;_&lt;admin&gt;&lt;.sync&gt; </code> </p> <p>輸出： <code> ftp_215_888_iter_ 1449756724.sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 標題行宏 {#header-macros}

有關可用宏和定義的清單，請參 [閱出站模板宏](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)。

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 格式和輸出示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 頁籤 </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;ORDER_ID&gt; &lt;TAB&gt;&lt;SYNC_TYPE&gt; </code> </p> <p>輸出： <code> 888 full.sync </code> </p> <p>在輸出中，非打印製表符字元分隔每個元素。 </p> </td>
  </tr>
 </tbody>
</table>

## 檔案內容宏 {#file-content-macros}

有關可用宏和定義的清單，請參 [閱出站模板宏](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)。

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 格式和輸出示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>輸出： <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>輸出： <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUIDS </code> </p> </td> 
   <td colname="col2"> <p>請參閱下方的個別章節。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;DP_UUID&gt; &lt;REMOVED_SEGMENT_LIST;separator=" "&gt; </code> </p> <p>輸出： <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;DP_UUID&gt; &lt;SEGMENT_LIST;separator=" "&gt; </code> </p> <p>輸出： <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p><b>格式:</b> </p> <p> 
     <code>
       {"AdvertiserId":"&lt;PIDALIAS&gt;", "DataCenterId": 2,"TDID":"&lt;DP_UUID&gt;", "Data":[&lt;SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;""名稱":""&lt;seg."CURLY_BRACKET&gt;};separator=","&gt;&lt;if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)&gt;&lt;逗號&gt;&lt;endif&gt;&lt;REMOVED_SEGMENT_LIST:{seg|&lt;OPEN_SURCY_BRACKET&gt;":"&lt;seg.alias&gt;", "TtlInInInMinutel":0&lt;關閉_CURLY_BRACKET&gt;}；分隔符=","&gt;]} </code></p><p><b>輸出：</b></p> <p>
     <code>//第一個範例{"AdvertiserId":"12345", "DataCenterId": 2, "TDID":"dfd215e4-8d6b-4fdb-90b9-fab4456f2c9d","Data":[{"Name":"4321"}} //第二個範例{"AdvertiserId":"12345", "DataCenterId": 2,"TDID":"9099e8fe-ababb-5114-abaa-28bdaa053ca","Data":[{"Name":"4321"},{"Name":"987","TtlInMinutes":0}, {"Name":"654","TtlInMinutes":0}]} </code></p> <p> <p>注意： 在第一個示例中，宏僅返回 <code> SEGMENT_LIST的資料，因 </code> 為 <code> REMOVED_SEGMENT_LIST </code> 為空。 第二個示例返回兩個宏的資料。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>格式: </p> <p> <code> &lt;PID&gt;&lt;TAB&gt;&lt;UUID&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt;&lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.alias&gt;,&lt;OUTPUT_ATTRIBUTE_VALUE&gt;,&lt;seg.lastUpdateTime&gt;&amp;}&gt; </code> </p> <p>輸出： </p> <p> <code> 1159 00088008579683653741516297509717335000 17t0aj01b120hp1 0 5,103714,1,1344114661000&amp;5,103713,1,1343250661000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 頁籤 </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>輸出： <code> 123456 UUID1 UUID2 UUID3 </code> </p> <p>在輸出中，非打印製表符字元分隔每個元素。 </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>格式： <code> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator="|"&gt; </code> </p> <p>輸出： <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID` 範例

為協助您瞭解巨集輸 `DPUUID` 出資料的方式，我們假設我們有2 `DPID`個對應 `DPUUID`至如下所示：

* DPID `1111` 對應至DPUUID `AAAA` (timestamp = 1) `BBBB` 和(timestamp = 2)。
* DPID `2222` 對應至DPUUID `CCCC`。

有了這些條件，下表列舉了一些可能的格式字串及其輸出。

<table id="table_6A6D94F994C1475BB09126BA0B815B1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 映射條件 </th> 
   <th colname="col2" class="entry"> 宏格式 </th> 
   <th colname="col3" class="entry"> 輸出 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>傳回單一DPID的所有映射 </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUIDS;format="dpids=1111|maxMappings=0|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","AAAA"],["1111","BBB"]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>針對所有DPID傳回最多1個對應 </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUIDS;format="dpids=1111,222|maxMappings=1|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","BBB"],["2222","CCC"]] </code> </p> <p>對於DPID <code> 1111 </code>，巨集只會對應至DPUUID <code> BBBB, </code> 因為該ID的時間戳記較大。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳回單一DPID的最多2個映射 </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUIDS;format="dpids=2222|maxMappings=2|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["2222","CCC"]] </code> </p> <p>即使 <code> maxMappings=2 </code>，此巨集也只會傳回1個DPUUID到DPUUID映射，因為指定的DPID只有一個DPUUID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

[輸出範本巨集](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)