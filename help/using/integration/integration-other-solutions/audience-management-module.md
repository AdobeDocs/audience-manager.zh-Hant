---
description: 將「受眾管理模組」添加到Adobe AnalyticsAppMeasurement，以將分析資料轉發到Audience Manager，而不是讓Audience ManagerData Integration Library(DIL)代碼從頁面發送像素。
keywords: 觀眾分析；分析；ssf;伺服器端轉發
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: 實施受眾管理模組
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# 如何轉發資料 [!DNL Adobe Analytics] 至 [!DNL Audience Manager] {#implement-the-audience-management-module}

按照本教程中的步驟轉發 [!DNL Analytics] 資料 [!DNL Audience Manager] 而不是 [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL])代碼從頁面發送像素。

>[!TIP]
>
>我們建議您使用 [!DNL Adobe Experience Platform Tags] 轉發 [!UICONTROL Analytics] 資料 [!DNL Audience Manager]。 使用 [!UICONTROL Tags]，您不必手動將代碼複製到 [!DNL AppMeasurement]，如此頁所示。

## 必要條件 {#prereqs}

除了啟用本文檔中描述的擴展或實現代碼外，還必須：

* 實施 [Adobe Experience Platform身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。
* 啟用 [伺服器端轉發](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 的 [!UICONTROL Adobe Analytics Admin Console]。

## 實施 {#implementation}

有兩種方法可實現資料轉發 [!DNL Adobe Analytics] 至 [!DNL Audience Manager]，具體取決於您使用的標籤管理解決方案。

### 使用 [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] 建議您使用 [標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) 儀器的擴展 [!DNL Adobe Analytics] 和 [!DNL Audience Manager] 你的財產。 在這種情況下，您不需要手動複製任何代碼。 相反，必須在 [!DNL Analytics] 擴展，如下圖所示。 另請參閱 [Adobe Analytics分機](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) 文檔。

>[!TIP]
>
>如果安裝 [!DNL Adobe Analytics] 擴展， *不* 並安裝 [!DNL Audience Manager] 擴展。 從 [!DNL Analytics] 擴展替換 [!DNL Audience Manager] 擴展功能。

![如何實現從Adobe Analytics分機到Audience Manager的資料共用](/help/using/integration/assets/analytics-to-aam.png)

## 定義的代碼元素 {#code-elements-defined}

下表定義了代碼示例中的重要變數。

| 參數 | 說明 |
|--- |--- |
| `partner` | 必填。這是分配給您的合作夥伴名稱 [!DNL Adobe]。 它有時被稱為 [!UICONTROL partner ID] 或夥伴子域。  聯繫您 [!DNL Adobe] 顧問或 [客戶服務](https://helpx.adobe.com/tw/marketing-cloud/contact-support.html) 如果你不知道你的搭檔名字。 |
| `containerNSID` | 必填。大多數客戶可以  `"containerNSID":0` 。 但是，如果您的公司需要使用其他容器自定義ID同步，您可以在此處指定該容器ID。 |
| `uuidCookie` | 選填。此配置允許您設定 [!DNL Adobe] 第一方域的cookie。 此 [!DNL cookie] 包含 [UUID](../../reference/ids-in-aam.md) 。 |
| `visitorService` - `namespace` | 必填。的 `namespace` 如果使用 [!DNL AudienceManagement] 與 [!UICONTROL AppMeasurement] 版本2.10或更高版本。 此 [!UICONTROL AudienceManagement] 模組要求您使用 [!UICONTROL Adobe Experience Platform Identity Service] 3.3或更高版本。 <br><br>的 [!UICONTROL Experience Cloud Organization ID] 是公司在註冊時提供的ID [!UICONTROL Experience Cloud]。 在中查找您公司的組織ID [組織和帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)。 |

## 結果：資料轉發到 [!DNL Audience Manager] {#results-data-forwarding}

您 [!DNL Analytics] 實現將資料發送到 [!DNL Audience Manager] 之後：

* 已啟用 [!UICONTROL Server-Side Forwarding] （與您的顧問討論此功能）;
* 已實施 [!DNL Adobe Experience Platform Identity Service];
* 按照本教程中的實施步驟操作。

此進程將資料發送到 [!DNL Audience Manager]:

* 在頁面視圖呼叫；
* 從跟蹤的連結；
* 從視頻里程碑和心跳視頻視圖。

>[!NOTE]
>
>發送到的變數 [!DNL Audience Manager] 從 [!DNL Analytics] 使用特殊前置詞。 在建立前置詞時，您需要瞭解並考慮這些前置詞 [!DNL Audience Manager] 性狀。 有關這些前置詞的詳細資訊，請參見 [鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)。
