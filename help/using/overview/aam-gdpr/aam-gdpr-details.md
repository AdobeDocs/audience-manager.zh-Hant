---
description: 本文件涵蓋Audience Manager通用資料保護規則(GDPR)的相關技術，並示範如何提交GDPR要求至Audience Manager。
seo-description: 本文件涵蓋Audience Manager通用資料保護規則(GDPR)的相關技術，並示範如何提交GDPR要求至Audience Manager。
seo-title: GDPR 對 Audience Manager 的影響
solution: Audience Manager
title: GDPR 對 Audience Manager 的影響
uuid: ed23a478-32be-460d-be03-a735317 f7 c0 f
translation-type: tm+mt
source-git-commit: b791e22e9c8c848a8fc14c6d6494f77c9e7335dc

---


# GDPR 對 Audience Manager 的影響{#gdpr-in-audience-manager}

本文件涵蓋Audience Manager通用資料保護規則(GDPR)的相關技術，並示範如何提交GDPR要求至Audience Manager。

## GDPR Documentation in the Experience Cloud {#gdpr-documentation}

在閱讀Audience Manager具體資訊之前，我們建議您瀏覽以下連結的歐洲通用資料保護規則(GDPR)的Experience Cloud教材：

* [GDPR與您的業務](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [GDPR白皮書](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [GDPR 術語](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

以下章節說明GDPR對Audience Manager的意義，以及如何提交GDPR要求至Audience Manager。

## Types of GDPR Requests and How to Make a GDPR Request {#types-of-gdpr-requests}

As an Audience Manager customer, you can submit individual GDPR requests to access and delete customer data, either through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)**. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). 如果您有任何疑問，請在gdprsupport@adobe.com聯絡客戶服務。

## 存取資料 {#access-data}

我們瞭解您致力於在30天內收到GDPR客戶要求。因此，我們會盡量盡快處理您的資料存取要求。

**請求**

You can log data access requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `access` action). 無論何種情況，您都必須使用您送出資料存取要求的Audience Manager識別碼上傳JSON。See what a well-formed JSON looks like in the **[Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (specifically, search in page for &quot;POST request format&quot;). Or, you can **[download a sample JSON](assets/access_request.json)**.

**回應**

存取資料請求的回應包含特徵和區段總數的摘要、特徵類型、特徵和區段描述以及個別資料來源名稱。存取回應也將包含資料掌控者存取的第二方和第三方資料以及第一方資料。When [!UICONTROL declared IDs] such as cross device CRM IDs or customer cookie IDs are sent in GDPR requests, Audience Manager will include the Access response from all the linked devices (up to 100 devices per declared ID).

**回應狀態**

如果回應中有Audience Manager發生任何錯誤，回應中會出現錯誤代碼。We have a [list of error codes](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md), where you can find more information about the returned errors.

**回應範例**

範例存取回應可能類似於下方。在此範例中，資料主體的ID是Cookie ID。他們符合數個特性，屬於幾個細分。Cookie ID會連結至行動ID。此範例也包含他們使用的手機中繼資料。

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

下表包含資料存取回應中所有傳回欄位的說明，依上述順序顯示。

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
   <td colname="col2"> <p>後續資料的使用者ID。這是您在GDPR資料存取要求中提供的ID，或是連結至您所提供之其中一個ID的ID。The ID types are described in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>亦稱為資料來源。See the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>namespace/資料來源的 ID。See <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (IDs)</a> for all the accepted values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 整合程式碼 </code> </p> </td> 
   <td colname="col2"> <p>整合代碼是資料來源的好記名稱，可協助您比使用資料來源ID更輕鬆追蹤資料來源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料提供者名稱 </code> </p> </td> 
   <td colname="col2"> <p>資料來源擁有者的名稱。 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">對於第一方資料，此為客戶自己的公司名稱。 </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">對於第二方資料，這是合作夥伴公司的名稱。 </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">對於第三方資料，這是資料合作夥伴的名稱。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 類型 </code> </p> </td> 
   <td colname="col2"> <p>您要求 GDPR 資料存取權限的 ID 類型。Accepted types are listed in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 警告</code> </p> </td> 
   <td colname="col2"> <p>警告會傳回與資料存取要求相關的進一步資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 標題 </code> </p> </td> 
   <td colname="col2"> <p>關於警告的簡短資訊。 </p> <p>您可能收到的兩個警告包括： </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">裝置資料 </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">請求不完整 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 說明 </code> </p> </td> 
   <td colname="col2"> <p>您收到警告的詳細說明： </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">裝置資料-包含此裝置所有使用者的資料 </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">不完整的請求-無法擷取Audience Manager資料。有些資訊可能遺失。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料 </code> </p> </td> 
   <td colname="col2"> <p>與此使用者ID關聯的特徵和區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>與使用者ID相關聯的特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 名稱</code> </p> </td> 
   <td colname="col2"> <p>特徵的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 類型</code> </p> </td> 
   <td colname="col2"> <p>特徵類型。可能的值包括: </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>第一方</i> 符合您自身特徵。 </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>屬於您合作夥伴特徵的第二方</i> 。Read our <a href="../../overview/data-types-collected.md#second-party-data"> Second Party Data</a> article for more information. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>第三方</i> 針對資料合作夥伴取得的特性，透過 <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>取得。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 說明</code> </p> </td> 
   <td colname="col2"> <p>說明特徵或函數的一些字詞。這是選用欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料匯出控制</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this trait's data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料提供者名稱</code> </p> </td> 
   <td colname="col2"> <p>此特徵所屬之資料來源擁有者的名稱。 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">對於第一方資料，此為客戶自己的公司名稱。 </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">對於第二方資料，這是合作夥伴公司的名稱。 </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">對於第三方資料，這是資料合作夥伴的名稱。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 最後實現</code> </p> </td> 
   <td colname="col2"> <p>資料主體上次符合此特徵的確切時間。日期格式為YYYY-MM-DD。 </p> </td> 
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
   <td colname="col2"> <p>說明此區段的一些字詞。這是選用欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料匯出控制</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this segment's data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料提供者名稱</code> </p> </td> 
   <td colname="col2"> <p>此區段所屬之資料來源擁有者的名稱。 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">對於第一方資料，此為客戶自己的公司名稱。 </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">對於第二方資料，這是合作夥伴公司的名稱。 </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">對於第三方資料，這是資料合作夥伴的名稱。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 最後實現</code> </p> </td> 
   <td colname="col2"> <p>「資料主體」上次符合此區段資格的確切時間。日期格式為YYYY-MM-DD。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> active</code> </p> </td> 
   <td colname="col2"> <p>指出資料主體目前是否符合此區段資格。Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 連結 </code> </p> </td> 
   <td colname="col2"> <p>此ID已連結到的其他ID。資訊會傳回： </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace(資料來源) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">整合程式碼 </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">資料提供者名稱 </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>所有這些欄位都會在此表格的第一列中說明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 連結日期時間</code> </p> </td> 
   <td colname="col2"> <p>ID同步事件在ID之間建立連結的確切時間。日期格式為YYYY-MM-DD。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 裝置中繼資料 </code> </p> </td> 
   <td colname="col2"> <p>裝置相關資訊。此資訊包括下列欄位。請注意，並非所有裝置類型都會傳回所有欄位。 </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>硬體資訊 </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>裝置製造商 </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>裝置的行銷名稱 </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>裝置模型 </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>裝置作業系統(OS)的名稱 </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>OS版本 </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>裝置供應商 </p> </li> 
     </ul> </p> <p> <p>注意：當您送出下列其中一個時，我們只傳回裝置中繼資料： 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">行動ID </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager ID </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud ID </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 刪除資料 {#delete-data}

我們瞭解您致力於在30天內收到GDPR客戶要求。因此，我們會盡量盡快處理您的資料刪除請求。

**請求**

You can log data deletion requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `delete` action). 無論何種情況，您都必須使用您送出資料存取要求的Audience Manager識別碼上傳JSON。See what a well-formed JSON looks like in the [Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) (specifically, search in page for &quot;POST request format&quot;). Or, you can **[download a sample JSON](assets/delete_request.json)**.

**回應**

回應資料刪除請求，我們刪除與個別Audience Manager識別碼關聯的特徵和區段。此外，Data主體的個別Audience Manager識別碼將會永久退出Audience Manager的資料收集，並移除個別的ID對應。當已宣告的ID(例如跨裝置CRM ID或客戶Cookie ID)以GDPR請求傳送時，Audience Manager會對所有連結的裝置執行必要的刪除動作(每個宣告ID最多100個裝置)。

## Opt-out Request {#opt-out-request}

For opt-out requests, please refer to our documentation on [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

## Audience Manager Identifiers (IDs) {#aam-ids}

提交GDPR請求至Adobe Audience Manager時，必須包含下列其中一個識別碼(ID)。You can find more information on the ID formats in our [Index of Audience Manager IDs](../../reference/ids-in-aam.md).

### Adobe Audience Manager獨特使用者ID

**使用者ID**：aam_ uuid

**定義**：Adobe Audience Manager獨特使用者ID

**命名空間ID**：0

>[!NOTE]
>
>您也可以使用核心命名空間。請參閱第二個JSON範例。

**JSON範例**：

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

**使用者ID**：mid

**定義**：Adobe Experience Cloud ID(先前稱為訪客ID或Marketing Cloud ID)

**命名空間ID**：4

>[!NOTE]
>
>您也可以使用ECID命名空間。請參閱第二個JSON範例。

**JSON範例**：

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

**使用者ID**：cid

**定義**：客戶ID，例如您為匿名網站訪客設定的Cookie，或來自離線系統或雜湊使用者名稱的CRM ID

**命名空間ID**：特定客戶。請從Audience Manager實例尋找。

**JSON範例**：

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

**使用者ID**：d_ cid

**定義**：行動廣告ID。
>[!IMPORTANT]
>
> 如果您使用Mobile SDK，則也應傳送Experience Cloud ID(MID)以及行動廣告ID，以取得完整的GDPR存取和刪除回應。

**命名空間 ID**:

* IDFA：20915
* GAID：20914

**JSON範例**：

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

**使用者ID**：d_ cid_ ic

**定義**：資料來源的整合代碼。您可以使用這項功能，而不是在API要求至Adobe Experience Cloud隱私核心服務中的資料來源ID/namespace ID。

**命名空間ID**：不適用

JSON範例：

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
