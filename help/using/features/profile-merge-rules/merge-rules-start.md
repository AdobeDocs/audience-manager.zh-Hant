---
description: 要建立配置檔案合併規則審查並完成本節所述每個過程的步驟。
seo-description: 要建立配置檔案合併規則審查並完成本節所述每個過程的步驟。
seo-title: 設定檔合併規則快速入門
solution: Audience Manager
title: 設定檔合併規則快速入門
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: dc22ed98b51b5633532bab45a79a14ee14dba5f5
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 4%

---


# 設定檔合併規則快速入門 {#getting-started-with-profile-merge-rules}

要建立[!UICONTROL Profile Merge Rules]，請查看並完成本節中介紹的每個過程的步驟。

<!-- merge-rules-start.xml -->

## 建立跨設備資料源{#create-data-source}

若要建立跨裝置資料來源，請前往&#x200B;**[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;並完成此處說明之每個章節的步驟。 建立或編輯跨裝置資料來源時，需要有管理員權限。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>如需這些不同控制項的說明，請參閱[資料來源設定和功能表選項](../datasources-list-and-settings.md#settings-menu-options)。

## 資料源詳細資訊{#details}

要完成[!UICONTROL Data Source Details]部分：

1. 命名資料來源。
2. *（可選）* 說明資料來源。簡明的說明可協助您定義資料來源的角色或用途。
3. 提供整合程式碼。 整合程式碼是您專屬的唯一ID，用於此資料來源。
4. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;清單中，選擇&#x200B;**[!UICONTROL Cross Device]**。
5. 在&#x200B;**[!UICONTROL ID Definition]**&#x200B;清單中，選擇定義資料源類型的選項。 選項包括:
   * **[!UICONTROL Person]**:定義單一人員的ID。此ID可以映射至多個[!DNL Audience Manager] ID。
   * **[!UICONTROL Household]**:定義一組人員的ID。此ID可以映射至多個[!DNL Audience Manager] ID。

## 資料匯出控制 {#export-controls}

[「資料匯](../data-export-controls.md) 出控制」是可套用至資料來源和目的地的選用分類規則。當該動作違反資料隱私或使用協定時，您無法將資料傳送至目的地。 如果您不使用[!UICONTROL Data Export Controls]，請略過本節。

## 資料源設定{#settings}

[!UICONTROL Data Source Settings] section提供了多個選項，但這2個選項對於建立跨設備資料源非常重要：

* **[!UICONTROL Use as Authenticated Profile]**:依預設選取，此設定可讓您使用您自己 [!UICONTROL Profile Merge Rule] 的驗證資料建立。

* **[!UICONTROL Use as a Device Graph]**:此控制項僅適用於列為資料提供者的帳戶。選取此核取方塊會將資料來源建立為裝置圖表，並讓您與其他[!DNL Audience Manager]客戶共用。 與您的[!DNL Audience Manager]顧問合作，以設定為資料提供者，並指定應與哪些客戶共用此[!UICONTROL Data Source]。 您的顧問將透過內部布建程式來布建您的帳戶和裝置圖形共用。

* **[!UICONTROL Data retention for inactive Customer IDs]**:此控制項可讓您設定非作用中客戶ID的資料保留期。這會決定客戶ID上次在Audience Manager平台上顯示後，Audience Manager在我們的資料庫中保留多久的時間。 預設值為24個月（720天）。 您可設定的最小值為1個月，最大值為5年。 請注意，我們會將所有月份計算為30天。 Audience Manager會根據您為非作用中客戶ID設定的資料保留率，執行每週刪除非作用中客戶ID一次的程式。

與這些設定關聯的文本欄位允許您使用出現在[配置檔案合併規則選項](merge-rule-definitions.md)中的別名更名[!UICONTROL Data Source]。 例如，如果向&#x200B;**[!UICONTROL Use as Authenticated Profile]**&#x200B;添加別名，該名稱將出現在[!UICONTROL Authenticated Profile Options]清單中。 如果向&#x200B;**[!UICONTROL Use as a Device Graph]**&#x200B;添加別名，該名稱將出現在[!UICONTROL Device Options]清單中。

## 建立配置檔案合併規則{#create-profile-merge-rule}

若要建立[!UICONTROL Profile Merge Rule]，請前往&#x200B;**[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]**&#x200B;並完成此處所述各節的步驟。

在設定跨裝置資料來源後，最多可建立3個合併規則。 如果您註冊「以人為本的目的地」[，您就可以存取第4個描述檔合併規則([!UICONTROL All Cross-Device Profiles])。](../destinations/people-based-destinations-overview.md)

建立、編輯或刪除規則需要管理員權限。 所有使用者皆可檢視並使用現有的[!UICONTROL Profile Merge Rules]。

<!-- create-profile-merge-rule.xml -->

**必要條** 件：建立跨裝置資料來源是必要的 [!UICONTROL Profile Merge Rule]。請參閱[建立資料來源](../manage-datasources.md#create-data-source)。

>[!TIP]
>
>如需這些不同控制項的說明，請參閱[描述檔合併規則選項定義](merge-rule-definitions.md)。

## 基本資訊 {#basic-info}

要完成[!UICONTROL Basic Information]部分：

1. 命名[!UICONTROL Profile Merge Rule]。
2. *（可選）* 說明 [!UICONTROL Profile Merge Rule]。簡明的說明可協助您定義規則的角色或用途。
3. *（可選）* 如 **[!UICONTROL Set as default]** 果要將其設定為預設值，請選擇 [!UICONTROL Profile Merge Rule]。新區段會自動與預設規則關聯。

## 資料匯出控制 {#data-export-controls}

[資料匯出](../data-export-controls.md) 控制項是可套用至您的選用分類規則 [!UICONTROL Profile Merge Rule]。當該動作違反資料隱私或使用協定時，您無法將資料傳送至目的地。 如果您不使用[!UICONTROL Data Export Controls]，請略過本節。

## 配置檔案合併規則設定{#profile-merge-rule-setup}

要完成[!UICONTROL Proflie Merge Rule Setup]部分：

1. 選擇&#x200B;**[!UICONTROL Authenticated Option]**。 選項包括:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 選擇&#x200B;**[!UICONTROL Authenticated Profile Option]**（最多3個，最多）。 這些是您先前建立的[跨裝置資料來源](merge-rules-start.md)。
3. 選擇 **[!UICONTROL Device Option]**. 選項包括:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. 按一下 **[!UICONTROL Save]**.

### 使用跨裝置ID作為使用者ID索引鍵{#considerations}的Adobe促銷活動目標注意事項

在2019年底，我們推出了一系列的描述檔合併規則增強功能，以改善使用跨裝置ID產生的批次檔案的精確度。 從2020年3月16日星期一開始，您的Audience Manager例項將嚴格執行這些增強功能。 因此，使用跨裝置ID映射至目的地的區段，會停止在某些「描述檔合併規則」設定中產生匯出。

若要使用跨裝置ID（例如Adobe Campaign）確保Audience Manager實例與目標之間的正確整合，請確定您符合下列需求：

1. 檢閱對應至Adobe Campaign Declared ID目的地的區段所使用的描述檔合併規則。 配置檔案合併規則必須使用[!UICONTROL Last Authenticated Profile]選項，因此所有已驗證的配置檔案都可以包含在導出中。 如果您的「描述檔合併規則」使用不同的選項，請將其切換為[!UICONTROL Last Authenticated Profile]。
2. 在「描述檔合併規則」設定中，選取「Adobe Campaign Declared ID」資料來源。

>[!NOTE]
>
> 如果您已達到最多[!UICONTROL Profile Merge Rules]數量，並需要根據上述指示進行配置的協助，請聯絡客戶服務。

## 配置合併規則代碼{#configure-merge-rule-code}

請依照下列指示，設定[!UICONTROL Adobe Experience Platform Identity Service]、[!UICONTROL DIL]和行動裝置[!DNL SDK]程式碼，以搭配您的合併規則運作。

<!-- merge-rules-configure-code.xml -->

### 必要條件

在&#x200B;*完成這些過程之前，必須設定[跨設備資料源](#create-data-source)和[配置檔案合併規則](#create-profile-merge-rule)*。

## 針對Adobe Experience Platform Identity Service客戶{#id-service-customers}

使用[!UICONTROL Profile Merge Rules]時，建議使用[!UICONTROL Adobe Experience Platform Identity Service]和最新版[DIL](../../dil/dil-overview.md)。 但是，您不必使用[!UICONTROL Adobe Experience Platform Identity Service]來使用此功能。 如果您只使用[!UICONTROL DIL]，請參閱下方的[legacy DIL section](#legacy-dil)。

### 設定客戶ID函式

使用[!UICONTROL Adobe Experience Platform Identity Service]時，`setCustomerIDs`函式會將聲明的ID傳遞至[!DNL Audience Manager]。 若要使用描述檔合併規則，您必須修改`setCustomerIDs`，以使用建立跨裝置資料來源時指定的整合代碼。 例如，假設您已使用整合程式碼`my_datasource_ic`建立跨裝置資料來源。 若要傳入宣告的ID，您應將整合程式碼新增至訪客ID函式，如下所修改的程式碼範例所示。

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

如需詳細資訊，請參閱[建立跨裝置資料來源](#create-data-source)和[客戶ID和驗證狀態](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)。

### 配置`DIL.create`函式

[!UICONTROL DIL]的最新版本現在會自動從`DIL.create`的`visitorService`函式中擷取[!UICONTROL declared ID]（請參閱[宣告的ID變數](../declared-ids.md#declared-id-variables)）。 請檢查`DIL.create`函式，以確定已正確設定此值，如下面的代碼示例所示。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

在namespace鍵值對中，`*`MCORG`*`變數是您的[!DNL Experience Cloud]組織ID。 如果您沒有此ID，則可在[!DNL Experience Cloud]控制面板的[!UICONTROL Administration]區段中找到它。 您需要管理員權限才能檢視此控制面板。 請參閱[管理：核心服務](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/manage-users-and-products/admin-getting-started.html)。

### 設定SDK

請參閱下方的[設定SDK](#configure-sdks-legacy-dil)一節。

## 舊版DIL {#legacy-dil}

如果您尚未使用[!DNL Adobe Experience Platform Identity Service]，您應該使用。 但是，我們瞭解到，改用新程式碼需要仔細的思考和測試。 在這些情況下，請檢查`DIL.create`函式，以確定此設定正確，如下面的程式碼範例所示。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

如需詳細資訊，請參閱[Declared ID變數](../declared-ids.md#declared-id-variables)中的舊版[!UICONTROL DIL]一節。

### 設定SDK {#configure-sdks-legacy-dil}

檢查[!DNL SDK]程式碼中的方法，讓您從[!DNL Android]和[!DNL iOS]行動裝置傳遞[!UICONTROL declared IDs]。 [!DNL Android]和[!DNL iOS]程式碼庫的變數名稱相同：

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

另請參閱「Android適用的[Audience Manager方法」和「iOS適用的](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html)Audience Manager方法」。](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html)[

>[!MORELIKETHIS]
>
>* [建立資料來源](../manage-datasources.md#create-data-source)

