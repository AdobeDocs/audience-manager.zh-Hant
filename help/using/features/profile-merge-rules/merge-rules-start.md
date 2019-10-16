---
description: 要建立配置檔案合併規則審查並完成本節所述每個過程的步驟。
seo-description: 要建立配置檔案合併規則審查並完成本節所述每個過程的步驟。
seo-title: 描述檔合併規則快速入門
solution: Audience Manager
title: 描述檔合併規則快速入門
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# 描述檔合併規則快速入門 {#getting-started-with-profile-merge-rules}

要建立 [!UICONTROL Profile Merge Rules]、查看並完成本節所述各步驟中的步驟。

<!-- merge-rules-start.xml -->

## 建立跨裝置資料來源 {#create-data-source}

若要建立跨裝置資料來源，請前往並完 **[!UICONTROL Audience Data > Data Sources > Add New]** 成此處說明之每個章節的步驟。 建立或編輯跨裝置資料來源時，需要有管理員權限。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>如需這 [些不同控制項的說明](../datasources-list-and-settings.md#settings-menu-options) ，請參閱資料來源設定和功能表選項。

## 資料來源詳細資料 {#details}

要完成該部 [!UICONTROL Data Source Details] 分：

1. 命名資料來源。
2. *（選擇性）* ，說明資料來源。 簡明的說明可協助您定義資料來源的角色或用途。
3. 提供整合程式碼。 整合程式碼是您專屬的唯一ID，用於此資料來源。
4. 在清單 **[!UICONTROL ID Type]** 中，選擇 **[!UICONTROL Cross Device]**。
5. 在清單 **[!UICONTROL ID Definition]** 中，選擇定義資料源類型的選項。 選項包括:
   * **[!UICONTROL Person]**:定義單一人員的ID。 此ID可以對應至多個 [!DNL Audience Manager] ID。
   * **[!UICONTROL Household]**:定義一組人員的ID。 此ID可以對應至多個 [!DNL Audience Manager] ID。

## 資料匯出控制 {#export-controls}

[「資料匯出控制](../data-export-controls.md) 」是可套用至資料來源和目的地的選用分類規則。 當該動作違反資料隱私或使用協定時，您無法將資料傳送至目的地。 如果您未使用，請略過本節 [!UICONTROL Data Export Controls]。

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] section提供了多個選項，但這2個選項對於建立跨設備資料源非常重要：

* **[!UICONTROL Use as Authenticated Profile]**:依預設選取，此設定可讓您使用您自己的 [!UICONTROL Profile Merge Rule] 驗證資料來建立。

* **[!UICONTROL Use as a Device Graph]**:此控制項僅適用於列為資料提供者的帳戶。 選取此核取方塊會將資料來源建立為裝置圖表，並讓您與其他客戶共 [!DNL Audience Manager] 用。 與您的顧 [!DNL Audience Manager] 問合作，以設定資料提供者身分，並指定應與哪些 [!UICONTROL Data Source] 客戶共用此資料。 您的顧問將透過內部布建程式來布建您的帳戶和裝置圖形共用。

* **[!UICONTROL Data retention for inactive Customer IDs]**:此控制項可讓您設定非作用中客戶ID的資料保留期。 這會決定客戶ID上次在Audience manager平台上顯示後，Audience manager在我們的資料庫中保留多久的時間。 預設值為24個月（720天）。 您可設定的最小值為1個月，最大值為5年。 請注意，我們會將所有月份計算為30天。 Audience manager會根據您為非作用中客戶ID設定的資料保留率，執行每週刪除非作用中客戶ID一次的程式。

與這些設定關聯的文本欄位允許您使用「配置檔案合 [!UICONTROL Data Source] 並規則」選項中顯示的別名來 [更名](merge-rule-definitions.md)。 例如，如果向中添加別名， **[!UICONTROL Use as Authenticated Profile]**&#x200B;該名稱將出現在列 [!UICONTROL Authenticated Profile Options] 表中。 如果向中添加別名， **[!UICONTROL Use as a Device Graph]**&#x200B;該名稱將出現在列 [!UICONTROL Device Options] 表中。

>[!MORE_LIKE_THIS]
>
>* [建立資料來源](../manage-datasources.md#create-data-source)


## 建立描述檔合併規則 {#create-profile-merge-rule}

若要建立 [!UICONTROL Profile Merge Rule]，請前往並 **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** 完成此處所述各節的步驟。 在設定跨裝置資料來源後，最多可建立3個合併規則。 建立、編輯或刪除規則需要管理員權限。 所有使用者皆可檢視和使用現有 [!UICONTROL Profile Merge Rules]。

<!-- create-profile-merge-rule.xml -->

**** 必要條件：需要跨裝置資料來源才能建立 [!UICONTROL Profile Merge Rule]。 請參 [閱建立資料來源](../manage-datasources.md#create-data-source)。

>[!TIP]
>
>如需這 [些不同控制項的說明](merge-rule-definitions.md) ，請參閱描述檔合併規則選項定義。

## 基本資訊 {#basic-info}

要完成該部 [!UICONTROL Basic Information] 分：

1. 命名 [!UICONTROL Profile Merge Rule]。
2. *（可選）* ，請說明 [!UICONTROL Profile Merge Rule]。 簡明的說明可協助您定義規則的角色或用途。
3. *（可選）* ，如 **[!UICONTROL Set as default]** 果要將其設定為預設值，請選擇 [!UICONTROL Profile Merge Rule]。 新區段會自動與預設規則關聯。

## 資料匯出控制 {#data-export-controls}

[「資料匯出控制](../data-export-controls.md) 」是可套用至您的選擇性分類規則 [!UICONTROL Profile Merge Rule]。 當該動作違反資料隱私或使用協定時，您無法將資料傳送至目的地。 如果您未使用，請略過本節 [!UICONTROL Data Export Controls]。

## 配置檔案合併規則設定 {#profile-merge-rule-setup}

要完成該部 [!UICONTROL Proflie Merge Rule Setup] 分：

1. 選取 **[!UICONTROL Authenticated Option]**。 選項包括:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 選取 **[!UICONTROL Authenticated Profile Option]** （最多3個，最多）。 這些是您 [先前建立的跨裝置](merge-rules-start.md) 資料來源。
3. 選擇 **[!UICONTROL Device Option]**. 選項包括:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Click **[!UICONTROL Save]**.

## 設定合併規則代碼 {#configure-merge-rule-code}

請依照下列指示來設定 [!UICONTROL Experience Cloud ID Service]、 [!UICONTROL DIL]和行動 [!DNL SDK] 程式碼，以搭配您的合併規則運作。

<!-- merge-rules-configure-code.xml -->

### 必備條件

您必須先設定跨 [裝置資料來源](#create-data-source) ，並設 [定描述檔合併規](#create-profile-merge-rule) 則 *,* 才能完成這些程式。

## 針對Experience Cloud ID服務客戶 {#id-service-customers}

使 [!UICONTROL Experience Cloud ID Service] 用時建議使用 [DIL](../../dil/dil-overview.md) 和最新版本 [!UICONTROL Profile Merge Rules]。 不過，您不必使用此 [!UICONTROL Experience Cloud ID Service] 功能即可。 如果您只是使用，請 [!UICONTROL DIL]參閱下 [方的舊版DIL](#legacy-dil) 。

### 設定客戶ID函式

使用時，函 [!UICONTROL Experience Cloud ID Service]數將 `setCustomerIDs` 聲明的ID傳遞給 [!DNL Audience Manager]。 若要使用描述檔合併規則，您必須修 `setCustomerIDs` 改以使用建立跨裝置資料來源時指定的整合代碼。 例如，假設您已使用整合程式碼建立跨裝置資料來源 `my_datasource_ic`。 若要傳入宣告的ID，您應將整合程式碼新增至訪客ID函式，如下所修改的程式碼範例所示。

#### 一般程式碼範例

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### 修改的程式碼範例

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

如需詳細資訊，請 [參閱建立跨裝置資料來源](#create-data-source) 、客 [戶ID和驗證狀態](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html)。

### 配置函 `DIL.create` 數

最新版本 [!UICONTROL DIL] 現在會自動從中的 [!UICONTROL declared ID] 函 `visitorService` 數中取出(請 `DIL.create` 參閱 [Declared ID Variables](../declared-ids.md#declared-id-variables))。 檢查函 `DIL.create` 數，以確定此設定正確，如下列程式碼範例所示。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

在namespace鍵值配對中， `*`MCORG`*` 變數是您的 [!DNL Experience Cloud] 組織ID。 如果您沒有此ID，您可以在控制面板的區 [!UICONTROL Administration] 段中找 [!DNL Experience Cloud] 到。 您需要管理員權限才能檢視此控制面板。 See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### 設定SDK

請參閱 [下方的](#configure-sdks-legacy-dil) 「設定SDK」。

## 舊版DIL {#legacy-dil}

如果你還沒用， [!DNL Experience Cloud ID Service] 你真該用。 但是，我們瞭解到，改用新程式碼需要仔細的思考和測試。 在這些情況下，請檢查 `DIL.create` 您的函式，以確定此設定正確，如下面的程式碼範例所示。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

如需詳細資訊，請參閱「宣告的ID [!UICONTROL DIL] 變數」中 [的舊版章節](../declared-ids.md#declared-id-variables)。

### 設定SDK {#configure-sdks-legacy-dil}

檢查程式碼中可 [!DNL SDK] 讓您從行動裝置 [!UICONTROL declared IDs] 傳 [!DNL Android] 遞的 [!DNL iOS] 方法。 程式碼庫和程 [!DNL Android] 式碼 [!DNL iOS] 庫的變數名稱相同：

* `dpid`:跨裝置資料來源ID。
* `dpuuid`:( [!UICONTROL declared ID] 亦即使用者ID)。

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置類型 </th> 
   <th colname="col2" class="entry"> 方法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>語法:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>範例:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>語法:</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>範例:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

另請參閱「 [iOS適用的Android適用的Audience Manager方法](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) 」 [和「iOS適用的Audience Manager方法」](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html)。
