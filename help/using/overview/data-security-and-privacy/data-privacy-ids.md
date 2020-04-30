---
description: 本檔案涵蓋您可在資料隱私權要求中使用的Audience Manager ID類型。
seo-description: 本檔案涵蓋您可在資料隱私權要求中使用的Audience Manager ID類型。
seo-title: Audience Manager識別碼(ID)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Audience Manager識別碼(ID)
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Audience Manager識別碼(ID) {#aam-ids}

將資料 [隱私權要求](data-privacy-requests.md) 送出至Adobe Audience Manager時，您必須包含下列其中一個識別碼(ID)。 您可以在我們的Audience Manager ID索引中，找到有關ID [格式的詳細資訊](../../reference/ids-in-aam.md)。

## Adobe Audience Manager唯一使用者ID

* **使用者 ID**: `aam_uuid`
* **定義**: Adobe Audience Manager唯一使用者ID
* **命名空間ID**: 0

**JSON 範例**:

```json
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

>[!NOTE]
>
>You can also use the [!DNL CORE] namespace.

```json
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

## Adobe Experience Cloud ID

* **使用者 ID**: `mid`
* **定義**: [!DNL Adobe Experience Cloud ID]，先前稱為 [!DNL Visitor ID] 或 [!DNL Marketing Cloud ID]
* **命名空間ID**: 4

>[!NOTE]
>
>You can also use the [!DNL ECID] namespace. 請參閱第二個 [!DNL JSON] 範例。

**JSON 範例**:

```json
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

```json
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

## Customer ID

**使用者 ID**: `cid`

**定義**: 客戶ID，例如您為匿名網站訪客設定的Cookie，或離線系統的 [!DNL CRM] ID或雜湊使用者名稱。

**命名空間ID**: 客戶專屬。 請從您的Audience Manager例項中尋找。

**JSON 範例**:

```json
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

## 行動廣告ID

**使用者 ID**: `d_cid`

**定義**: 行動廣告ID。

**命名空間 ID**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

如需詳 [細資訊，請參閱全域資料](../../features/global-data-sources.md) 來源。

>[!IMPORTANT]
>
> 如果您使用Mobile, [!DNL SDK]則您也應傳送Experience Cloud ID(`MID`)和行動廣告ID，以取得完整的「存取」和「刪除」回應。

**JSON 範例**:

```json
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

## 整合程式碼

**使用者 ID**: `d_cid_ic`

**定義**: 資料來源的整合代碼。 在請求中，可以使用這個來取代資料來源ID /命名空 [!DNL API] 間ID [!DNL Adobe Experience Cloud Privacy Core Service]。

**命名空間ID**: 不適用

**JSON 範例**:

```json
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
