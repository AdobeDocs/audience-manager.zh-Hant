---
description: 若要建立設定檔合併規則檢閱，並完成本節所述各步驟中的步驟。
seo-description: 若要建立設定檔合併規則檢閱，並完成本節所述各步驟中的步驟。
seo-title: 設定檔合併規則快速入門
solution: Audience Manager
title: 設定檔合併規則快速入門
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: 個人資料合併
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: b8c8f35376c5a8a85fa4eeace7b447385ee9f339
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 4%

---

# 設定檔合併規則快速入門 {#getting-started-with-profile-merge-rules}

要建立[!UICONTROL Profile Merge Rules]，請查看並完成本節中介紹的每個過程中的步驟。

<!-- merge-rules-start.xml -->

## 建立跨裝置資料來源 {#create-data-source}

若要建立跨裝置資料來源，請前往&#x200B;**[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;並完成此處所述各節的步驟。 建立或編輯跨裝置資料來源需要管理員權限。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>有關這些不同控制項的說明，請參閱[資料源設定和菜單選項](../datasources-list-and-settings.md#settings-menu-options)。

## 資料來源詳細資訊 {#details}

要完成[!UICONTROL Data Source Details]部分：

1. 為資料來源命名。
2. *（選用）* 說明資料來源。簡潔的說明可協助您定義資料來源的角色或用途。
3. 提供整合程式碼。 整合代碼是您專屬的此資料來源唯一ID。
4. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;清單中，選擇&#x200B;**[!UICONTROL Cross Device]**。
5. 在&#x200B;**[!UICONTROL ID Definition]**&#x200B;清單中，選擇定義資料源類型的選項。 選項包括:
   * **[!UICONTROL Person]**:定義單一人員的ID。此ID可對應至多個[!DNL Audience Manager] ID。
   * **[!UICONTROL Household]**:定義一組人員的ID。此ID可對應至多個[!DNL Audience Manager] ID。

## 資料匯出控制 {#export-controls}

[資料匯](../data-export-controls.md) 出控制項是可選的分類規則，可套用至資料來源和目的地。如此一來，當動作違反資料隱私權或使用合約時，您就無法將資料傳送至目的地。 如果不使用[!UICONTROL Data Export Controls]，請跳過此部分。

## 資料來源設定 {#settings}

[!UICONTROL Data Source Settings] 區段提供多個選項，但這2個選項對於建立跨裝置資料來源很重要：

* **[!UICONTROL Use as Authenticated Profile]**:依預設，此設定可讓您使用自己的已 [!UICONTROL Profile Merge Rule] 驗證資料來建立。

* **[!UICONTROL Use as a Device Graph]**:此控制項僅適用於列為資料提供者的帳戶。選中此複選框將建立您的資料源作為設備圖形，並允許您與其他[!DNL Audience Manager]客戶共用該資料源。 與您的[!DNL Audience Manager]顧問合作，以設定為資料提供者，並指定應與哪些客戶共用此[!UICONTROL Data Source]。 您的顧問會透過內部布建程式布建您的帳戶和裝置圖表共用。

* **[!UICONTROL Data retention for inactive Customer IDs]**:此控制項可讓您設定非作用中客戶ID的資料保留期。這決定了Audience Manager在Audience Manager平台上最後一次看到客戶ID後，將客戶ID保留在資料庫中的時間長度。 預設值為24個月（720天）。 您可設定的最小值為1個月，最大值為5年。 請注意，我們會將所有月份計為30天。 Audience Manager會根據您為非作用中客戶ID所設定的資料保留率，執行每週刪除非作用中客戶ID一次的程式。

與這些設定關聯的文本欄位允許您使用出現在[配置檔案合併規則選項](merge-rule-definitions.md)中的別名更名[!UICONTROL Data Source]。 例如，如果向&#x200B;**[!UICONTROL Use as Authenticated Profile]**&#x200B;添加別名，該名稱將出現在[!UICONTROL Authenticated Profile Options]清單中。 如果向&#x200B;**[!UICONTROL Use as a Device Graph]**&#x200B;添加別名，該名稱將出現在[!UICONTROL Device Options]清單中。

## 建立設定檔合併規則 {#create-profile-merge-rule}

若要建立[!UICONTROL Profile Merge Rule]，請前往&#x200B;**[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]**&#x200B;並完成此處所述每個區段的步驟。

設定跨裝置資料來源後，您最多可以建立3個合併規則。 如果您註冊[以人物為基礎的目的地](../destinations/people-based-destinations-overview.md)，便可存取第4個設定檔合併規則([!UICONTROL All Cross-Device Profiles])。

建立、編輯或刪除規則需要管理員權限。 所有用戶都可以查看和使用現有的[!UICONTROL Profile Merge Rules]。

<!-- create-profile-merge-rule.xml -->

**必要條件：** 建置需要跨裝置資料來 [!UICONTROL Profile Merge Rule]源。請參閱[建立資料源](../manage-datasources.md#create-data-source)。

>[!TIP]
>
>有關這些不同控制項的說明，請參閱[定義的配置檔案合併規則選項](merge-rule-definitions.md)。

## 基本資訊 {#basic-info}

要完成[!UICONTROL Basic Information]部分：

1. 將[!UICONTROL Profile Merge Rule]命名為。
2. *（選用）* 說明 [!UICONTROL Profile Merge Rule]。簡潔的說明可協助您定義規則的角色或用途。
3. *（選用）* 選 **[!UICONTROL Set as default]** 取是否要將此設為預設 [!UICONTROL Profile Merge Rule]。新區段會自動與預設規則相關聯。

## 資料匯出控制 {#data-export-controls}

[資料匯](../data-export-controls.md) 出控制是可套用至的選用分類規 [!UICONTROL Profile Merge Rule]則。如此一來，當動作違反資料隱私權或使用合約時，您就無法將資料傳送至目的地。 如果不使用[!UICONTROL Data Export Controls]，請跳過此部分。

## 設定檔合併規則設定 {#profile-merge-rule-setup}

要完成[!UICONTROL Proflie Merge Rule Setup]部分：

1. 選擇&#x200B;**[!UICONTROL Authenticated Option]**。 選項包括:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 選取&#x200B;**[!UICONTROL Authenticated Profile Option]**（最多3個，最大值）。 這些是您先前建立的[跨裝置資料來源](merge-rules-start.md)。
3. 選擇 **[!UICONTROL Device Option]**. 選項包括:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. 按一下 **[!UICONTROL Save]**.

### 使用跨裝置ID作為使用者ID索引鍵的Adobe Campaign目的地考量事項 {#considerations}

2019年底，我們推出了一系列「設定檔合併規則」增強功能，以改善使用跨裝置ID產生批次檔案的準確度。 從2020年3月16日星期一開始，您的Audience Manager例項將嚴格遵循這些增強功能。 因此，使用跨裝置ID對應至目的地的區段，在某些「設定檔合併規則」設定中將不再產生匯出項目。

若要確保您的Audience Manager例項與使用跨裝置ID的目的地(例如Adobe Campaign)之間的正確整合，請務必符合下列需求：

1. 檢閱對應至您Adobe Campaign宣告ID目的地之區段所使用的設定檔合併規則。 設定檔合併規則必須使用[!UICONTROL Last Authenticated Profile]選項，因此所有已驗證的設定檔皆可包含在匯出中。 如果您的設定檔合併規則使用不同的選項，請將其切換至[!UICONTROL Last Authenticated Profile]。
2. 在「設定檔合併規則」設定中選取「Adobe Campaign宣告ID」資料來源。

>[!NOTE]
>
> 如果您已達到最大數量[!UICONTROL Profile Merge Rules] ，並需要根據上述指示進行配置的協助，請聯絡客戶服務。

## 配置合併規則代碼 {#configure-merge-rule-code}

請依照下列指示，設定[!UICONTROL Adobe Experience Platform Identity Service]、[!UICONTROL DIL]和行動[!DNL SDK]程式碼，以便搭配您的合併規則運作。

<!-- merge-rules-configure-code.xml -->

### 必要條件

您必須先設定[跨裝置資料來源](#create-data-source)和[設定檔合併規則](#create-profile-merge-rule) *,*&#x200B;才能完成這些程式。

## 適用於Adobe Experience Platform Identity Service客戶 {#id-service-customers}

使用[!UICONTROL Profile Merge Rules]時，建議使用[!UICONTROL Adobe Experience Platform Identity Service]和最新版本的[DIL](../../dil/dil-overview.md)。 不過，您不必使用[!UICONTROL Adobe Experience Platform Identity Service]即可使用此功能。 如果您只使用[!UICONTROL DIL]，請參閱下方的[舊版DIL區段](#legacy-dil)。

### 設定客戶ID函式

使用[!UICONTROL Adobe Experience Platform Identity Service]時，`setCustomerIDs`函式會將宣告ID傳遞至[!DNL Audience Manager]。 若要使用設定檔合併規則，您必須修改`setCustomerIDs`，以使用建立跨裝置資料來源時指定的整合代碼。 例如，假設您已使用整合代碼`my_datasource_ic`建立跨裝置資料來源。 若要傳入宣告ID，您會將整合代碼新增至訪客ID函式，如下方修改的程式碼範例所示。

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

最新版本的[!UICONTROL DIL]現在會自動從`DIL.create`中的`visitorService`函式擷取[!UICONTROL declared ID]（請參閱[宣告ID變數](../declared-ids.md#declared-id-variables)）。 檢查您的`DIL.create`函式，確定已正確設定，如下列程式碼範例所示。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

在命名空間索引鍵值配對中，`*`MCORG`*`變數為您的[!DNL Experience Cloud]組織ID。 如果您沒有此ID，可以在[!DNL Experience Cloud]控制面板的[!UICONTROL Administration]區段中找到。 您需要管理員權限才能檢視此控制面板。 請參閱[管理：核心服務](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/manage-users-and-products/admin-getting-started.html)。

### 配置SDK

請參閱下方的[設定SDK](#configure-sdks-legacy-dil)一節。

## 舊版DIL {#legacy-dil}

如果您尚未使用[!DNL Adobe Experience Platform Identity Service]，您確實應該使用。 但是，我們明白，要改用新代碼，需要經過仔細的思考和測試。 在這些情況下，請檢查`DIL.create`函式，以確定如下列程式碼範例所示，已正確設定此設定。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

如需詳細資訊，請參閱[宣告ID變數](../declared-ids.md#declared-id-variables)中的舊版[!UICONTROL DIL]區段。

### 配置SDK {#configure-sdks-legacy-dil}

檢查[!DNL SDK]程式碼中可讓您從[!DNL Android]和[!DNL iOS]行動裝置傳遞[!UICONTROL declared IDs]的方法。 [!DNL Android]和[!DNL iOS]程式碼程式庫的變數名稱相同：

* `dpid`:跨裝置資料來源ID。
* `dpuuid`:( [!UICONTROL declared ID] 即使用者ID)。

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

另請參閱[適用於Android的Audience Manager方法](https://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html)和適用於iOS的[Audience Manager方法](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html)。

>[!MORELIKETHIS]
>
>* [建立資料來源](../manage-datasources.md#create-data-source)

