---
description: 本檔案涵蓋與Audience manager通用資料保護規則(GDPR)相關的技術細節，並說明如何將GDPR要求提交給Audience Manager。
seo-description: 本檔案涵蓋與Audience manager通用資料保護規則(GDPR)相關的技術細節，並說明如何將GDPR要求提交給Audience Manager。
seo-title: GDPR 對 Audience Manager 的影響
solution: Audience Manager
title: GDPR 對 Audience Manager 的影響
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 98914987331ce31bc8d3e67647d5b8273b287d4c

---


# GDPR 對 Audience Manager 的影響{#gdpr-in-audience-manager}

本檔案涵蓋與Audience manager通用資料保護規則(GDPR)相關的技術細節，並說明如何將GDPR要求提交給Audience Manager。

## Experience cloud中的GDPR檔案 {#gdpr-documentation}

在閱讀Audience manager的詳細資訊之前，我們建議您先閱讀以下連結的歐洲通用資料保護規則(GDPR)的Experience cloud資料：

* [GDPR與您的業務](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [GDPR白皮書](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [GDPR 術語](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

以下各節說明GDPR對Audience manager的意義，以及如何將GDPR請求提交給Audience Manager。

## GDPR請求類型及如何提出GDPR請求 {#types-of-gdpr-requests}

身為Audience Manager客戶，您可以透過 **[GDPR客戶服務UI](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** ，或呼叫 **[GDPR API，提交個別的GDPR要求以存取和刪除客戶資料](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)**。 You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). 如果您有任何疑問，請聯絡客戶服務：gdprsupport@adobe.com。

## 存取資料 {#access-data}

我們瞭解您承諾在30天內履行您的GDPR客戶要求。 因此，我們會盡快處理您的資料存取要求。

**請求**

您可以透過 **[GDPR Client Services UI](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** ，或呼叫 **[GDPR API](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** (請參閱 `access` 動作)來記錄資料存取要求。 無論何種情況，您都必須使用您要提交資料存取要求的Audience manager識別碼上傳JSON。 在 **[Experience Cloud GDPR檔案中查看格式正確的JSON外觀](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** （尤其是在頁面中搜尋「POST請求格式」）。 或者，您可 **[以下載範例JSON](assets/access_request.json)**。

**回應**

存取資料請求的回應包含特徵和區段總數、特徵類型、特徵和區段的說明，以及個別資料來源名稱的摘要。 「存取」回應也會包含可存取資料控制器的第二方和第三方資料，以及第一方資料。 當跨 [!UICONTROL declared IDs] 裝置CRM ID或客戶Cookie ID等在GDPR請求中傳送時，Audience manager會包含來自所有連結裝置的存取回應（每個宣告的ID最多100個裝置）。

**回應狀態**

如果回應中有來自Audience manager的任何錯誤，這些錯誤會以回應中的錯誤代碼呈現。 我們有錯 [誤代碼清單](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)，您可在此找到有關傳回錯誤的更多資訊。

**範例回應**

範例存取回應可能如下所示。 在此範例中，資料主體的ID是Cookie ID。 他們符合數個特徵，屬於少數群體。 Cookie ID會連結至行動ID。 此範例也包含他們使用之手機的中繼資料。

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

下表依資料存取回應中所有傳回欄位的說明，依其顯示順序排列。

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>欄位 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>The user ID for the data that follows. 這是您在GDPR資料存取要求中提供的ID，或連結至您所提供之其中一個宣告ID的ID。 The ID types are described in the  Audience Manager Identifiers section.<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>亦稱為資料來源。請參閱「 <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience manager識別碼</a> 」區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>namespace/資料來源的 ID。See <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (IDs)</a> for all the accepted values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 整合程式碼 </code> </p> </td> 
   <td colname="col2"> <p>整合代碼是資料來源的好記名稱，可協助您比使用資料來源ID更輕鬆地追蹤資料來源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料提供者名稱 </code> </p> </td> 
   <td colname="col2"> <p>The name of the owner of the data source. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">For first party data, this is the customer's own company name. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">For second party data, this is the name of the partner company. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">For third party data, this is the name of the data partner. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 類型 </code> </p> </td> 
   <td colname="col2"> <p>您要求 GDPR 資料存取權限的 ID 類型。Accepted types are listed in the  Audience Manager Identifiers section.<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> warnings</code> </p> </td> 
   <td colname="col2"> <p>Warnings return further information related to the data access request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 標題 </code> </p> </td> 
   <td colname="col2"> <p>Brief information about the warning. </p> <p>The two warnings you may receive are: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Device Data </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Incomplete request </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 說明 </code> </p> </td> 
   <td colname="col2"> <p>您收到警告的更詳細說明： </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Device Data - Contains data from all users of this device </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">請求不完整——未完成Audience manager資料的擷取。 有些資訊可能遺失。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料 </code> </p> </td> 
   <td colname="col2"> <p>與此使用者ID關聯的特徵和區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>與使用者ID關聯的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 名稱</code> </p> </td> 
   <td colname="col2"> <p>特徵的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 類型</code> </p> </td> 
   <td colname="col2"> <p>特徵類型。 可能的值包括: </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>你自己的特徵</i> ，第一個派對。 </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>屬於您</i> 「合作夥伴」特徵的第二方。 請閱讀我們 <a href="../../overview/data-types-collected.md#second-party-data"> 的第二方資料文章</a> ，以取得詳細資訊。 </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>協力廠商</i> ，針對透過Audience Marketplace從資料合作夥伴取得的 <a href="../../features/audience-marketplace/audience-marketplace.md"> 特徵</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 說明</code> </p> </td> 
   <td colname="col2"> <p>用幾個字來說明特徵的目的或功能。 這是選填欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>套用 <a href="../../features/data-export-controls.md"> 至此特徵資料來源的</a> 「資料匯出控制」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料提供者名稱</code> </p> </td> 
   <td colname="col2"> <p>此特徵所屬的資料來源擁有者的名稱。 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">對於第一方資料，這是客戶自己的公司名稱。 </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">對於第二方資料，這是合作夥伴公司的名稱。 </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">對於第三方資料，這是資料合作夥伴的名稱。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 最後實現</code> </p> </td> 
   <td colname="col2"> <p>資料主體上次符合此特徵的確切時間。 日期格式為YYYY-MM-DD。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 區段 </code> </p> </td> 
   <td colname="col2"> <p>此使用者所屬的區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 名稱</code> </p> </td> 
   <td colname="col2"> <p>區段的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 說明</code> </p> </td> 
   <td colname="col2"> <p>請用幾個字來說明此區段。 這是選填欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>套 <a href="../../features/data-export-controls.md"> 用至此區段資料來源</a> ，資料匯出控制項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料提供者名稱</code> </p> </td> 
   <td colname="col2"> <p>此區段所屬之資料來源的擁有者名稱。 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">對於第一方資料，這是客戶自己的公司名稱。 </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">對於第二方資料，這是合作夥伴公司的名稱。 </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">對於第三方資料，這是資料合作夥伴的名稱。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>The exact time that the Data Subject last qualified for this segment. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 活動</code> </p> </td> 
   <td colname="col2"> <p>Indicates whether the Data Subject is currently qualified for this segment. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 連結 </code> </p> </td> 
   <td colname="col2"> <p>Additional ID that this ID has been linked to. Information is returned on: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (data source) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">整合程式碼 </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">資料提供者名稱 </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>All these fields are described in the first rows of this table. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> linking datetime</code> </p> </td> 
   <td colname="col2"> <p>ID同步事件建立ID間連結的確切時間。 The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> device metadata </code> </p> </td> 
   <td colname="col2"> <p>Information about the device. This information includes the fields below. Note that not all fields are returned for all device types. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Hardware information </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>裝置製造商 </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>裝置的行銷名稱 </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>裝置型號 </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>設備作業系統(OS)的名稱 </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>作業系統版本 </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>裝置廠商 </p> </li> 
     </ul> </p> <p> <p>注意：只有在您提交下列任一項時，我們才會傳回裝置中繼資料： 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">行動ID </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager ID </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud ID </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 刪除資料 {#delete-data}

我們瞭解您承諾在30天內履行您的GDPR客戶要求。 因此，我們會盡快處理您的資料刪除要求。

**請求**

您可以透過 **[GDPR Client Services UI](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** ，或呼叫 **[GDPR API](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** (請參 `delete` 閱動作)來記錄資料刪除要求。 無論何種情況，您都必須使用您要提交資料存取要求的Audience manager識別碼上傳JSON。 在 [Experience Cloud GDPR檔案中查看格式正確的JSON外觀](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) （尤其是在頁面中搜尋「POST請求格式」）。 或者，您可 **[以下載範例JSON](assets/delete_request.json)**。

**回應**

為了回應資料刪除請求，我們刪除了與各自Audience manager識別碼關聯的特徵和區段。 此外，Audience manager會永久退出進一步資料收集，並移除個別Id對應，此時資料主體的個別Audience manager識別碼。 當在GDPR請求中傳送宣告的ID（例如跨裝置CRM Id或客戶Cookie ID）時，Audience Manager會在所有連結的裝置上執行必要的刪除動作（每個宣告的ID最多100個裝置）。

## 退出請求 {#opt-out-request}

如需退出要求，請參閱我們有關退出管 [理的檔案](../../overview/data-security-and-privacy/opt-out-management.md)。

## Audience manager識別碼(ID) {#aam-ids}

將GDPR請求提交至Adobe Audience Manager時，您必須包含下列其中一個識別碼(ID)。 您可以在我們的Audience Manager ID索引中，找到有關ID [格式的詳細資訊](../../reference/ids-in-aam.md)。

### Adobe Audience Manager唯一使用者ID

**使用者ID**:aam_uuid

**Definition: Adobe Audience Manager Unique User ID**

**命名空間ID**:0

>[!NOTE]
>
>您也可以使用CORE命名空間。 請參閱第二個JSON範例。

**JSON中的範例**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

### Adobe Experience Cloud ID

**User ID: mid**

**定義**:Adobe Experience Cloud ID，先前稱為訪客ID或Marketing Cloud ID

**命名空間ID**:4

>[!NOTE]
>
>您也可以使用ECID命名空間。 請參閱第二個JSON範例。

**JSON中的範例**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

### Customer ID

**User ID: cid**

**定義**:客戶ID，例如您為匿名網站訪客設定的Cookie，或離線系統的CRM ID，或雜湊的使用者名稱

**命名空間ID**:客戶專屬。 請從您的Audience manager例項中尋找。

**JSON中的範例**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

### 行動廣告ID

**使用者ID**:d_cid

**定義**:行動廣告ID。
>[!IMPORTANT]
>
> 如果您使用Mobile SDK，則您也應傳送Experience Cloud ID(MID)以及行動廣告ID，以取得完整的GDPR存取和刪除回應。

**命名空間 ID**:

* IDFA:二零九一五年
* GAID:二零九一四年

**JSON中的範例**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

### 整合程式碼

**使用者ID**: d_cid_ic

**定義**:資料來源的整合代碼。 在Adobe Experience Cloud隱私權核心服務的API要求中，您可以使用此功能來取代資料來源ID /命名空間ID。

**命名空間ID**:不適用

JSON中的範例：

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
