---
description: 本文件說明您可在資料隱私權請求中使用的 Audience Manager ID 類型。
seo-description: 本文件說明您可在資料隱私權請求中使用的 Audience Manager ID 類型。
seo-title: Audience Manager 識別碼 (ID)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Audience Manager 識別碼 (ID)
translation-type: ht
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f
workflow-type: ht
source-wordcount: '253'
ht-degree: 100%

---


# Audience Manager 識別碼 (ID) {#aam-ids}

將[資料隱私權請求](data-privacy-requests.md)提交至 Adobe Audience Manager 時，您必須加入下列其中一個識別碼 (ID)。您可以在 [Audience Manager ID 索引](../../reference/ids-in-aam.md)中，找到有關 ID 格式的詳細資訊。

## Adobe Audience Manager 不重複使用者 ID

* **使用者 ID**：`aam_uuid`
* **定義**：Adobe Audience Manager 不重複使用者 ID
* **命名空間 ID**：0

**JSON 範例**：

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
>您也可以使用 [!DNL CORE] 命名空間。

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

* **使用者 ID**：`mid`
* **定義**：[!DNL Adobe Experience Cloud ID]，前身為 [!DNL Visitor ID] 或 [!DNL Marketing Cloud ID]
* **命名空間 ID**：4

>[!NOTE]
>
>您也可以使用 [!DNL ECID] 命名空間。請參閱第二個 [!DNL JSON] 範例。

**JSON 範例**：

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

## 客戶 ID

**使用者 ID**：`cid`

**定義**：客戶 ID，例如您為匿名網站訪客設定的 Cookie，或是離線系統的 [!DNL CRM] ID 或雜湊使用者名稱。

**命名空間 ID**：客戶專屬。請從您的 Audience Manager 例項中尋找。

**JSON 範例**：

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

## 行動廣告 ID

**使用者 ID**：`d_cid`

**定義**：行動廣告 ID。

**命名空間 ID**：

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

如需詳細資訊，請參閱[全域資料來源](../../features/global-data-sources.md)。

>[!IMPORTANT]
>
> 如果您有使用 Mobile [!DNL SDK]，那麼您也應傳送 Experience Cloud ID (`MID`) 以及行動廣告 ID，以取得完整的存取和刪除回應。

**JSON 範例**：

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

**使用者 ID**：`d_cid_ic`

**定義**：資料來源的整合程式碼。在向 [!DNL Adobe Experience Cloud Privacy Core Service] 發出的 [!DNL API] 請求中，可以使用這個 ID 來取代資料來源 ID / 命名空間 ID。

**命名空間 ID**：不適用

**JSON 範例**：

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
