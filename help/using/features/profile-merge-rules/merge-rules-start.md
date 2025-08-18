---
description: 若要建立「設定檔合併規則」，請檢閱並完成本節所述每個程式中的步驟。
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: 設定檔合併規則快速入門
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 1%

---

# 設定檔合併規則快速入門 {#getting-started-with-profile-merge-rules}

若要建立[!UICONTROL Profile Merge Rules]，請檢閱並完成本節中說明的每個程式中的步驟。

<!-- merge-rules-start.xml -->

## 建立跨裝置資料Source {#create-data-source}

若要建立跨裝置資料來源，請前往&#x200B;**[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;並完成此處所述每個區段的步驟。 需要管理員許可權才能建立或編輯跨裝置資料來源。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>如需這些不同控制項的說明，請參閱[資料Source設定和功能表選項](../datasources-list-and-settings.md#settings-menu-options)。

## 資料Source詳細資料 {#details}

若要完成[!UICONTROL Data Source Details]區段：

1. 為資料來源命名。
2. *（選擇性）*&#x200B;說明資料來源。 簡潔的說明可協助您定義資料來源的角色或用途。
3. 提供整合程式碼。 整合程式碼是您針對此資料來源擁有的唯一ID。
4. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;清單中，選取&#x200B;**[!UICONTROL Cross Device]**。
5. 在&#x200B;**[!UICONTROL ID Definition]**&#x200B;清單中，選取定義資料來源型別的選項。 選項包括:
   * **[!UICONTROL Person]**：定義單一人員的識別碼。 此ID可對應至多個[!DNL Audience Manager] ID。
   * **[!UICONTROL Household]**：定義一組人員的ID。 此ID可對應至多個[!DNL Audience Manager] ID。

## 資料匯出控制 {#export-controls}

[資料匯出控制項](../data-export-controls.md)是選擇性分類規則，可套用至資料來源和目的地。 當動作違反資料隱私權或使用合約時，這些功能會防止您將資料傳送至目的地。 如果您不使用[!UICONTROL Data Export Controls]，請略過此章節。

## 資料Source設定 {#settings}

[!UICONTROL Data Source Settings]區段提供多個選項，但這2個選項對於建立跨裝置資料來源很重要：

* **[!UICONTROL Use as Authenticated Profile]**：依預設選取，此設定可讓您使用自己的已驗證資料建置[!UICONTROL Profile Merge Rule]。

* **[!UICONTROL Use as a Device Graph]**：此控制項僅適用於列為資料提供者的帳戶。 選取此核取方塊會將您的資料來源建立為裝置圖表，並讓您與其他[!DNL Audience Manager]客戶共用。 與您的[!DNL Audience Manager]顧問合作，以設定為資料提供者，並指定與哪些客戶共用此[!UICONTROL Data Source]。 您的顧問將透過內部布建程式布建您的帳戶和裝置圖表共用。

* **[!UICONTROL Data retention for inactive Customer IDs]**：此控制項可讓您設定非作用中客戶ID的資料保留期間。 這會決定Audience Manager將客戶ID在Audience Manager平台上最後一次看到後，保留在資料庫中的時間。 預設值為24個月（720天）。 您可以設定的最小值為1個月，最大值為5年。 請注意，我們會將所有月份計為30天。 Audience Manager會根據您為非作用中客戶ID設定的資料保留，執行每週刪除一次非作用中客戶ID的程式。

與這些設定關聯的文字欄位可讓您以出現在[!UICONTROL Data Source]設定檔合併規則選項[中的別名重新命名](merge-rule-definitions.md)。 例如，如果您將別名新增至「**[!UICONTROL Use as Authenticated Profile]**」，則該名稱會顯示在「[!UICONTROL Authenticated Profile Options]」清單中。 如果您將別名新增至「**[!UICONTROL Use as a Device Graph]**」，則該名稱會顯示在「[!UICONTROL Device Options]」清單中。

## 建立設定檔合併規則 {#create-profile-merge-rule}

若要建立[!UICONTROL Profile Merge Rule]，請前往&#x200B;**[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]**&#x200B;並完成此處所述每個區段的步驟。

設定跨裝置資料來源後，您最多可以建立3個合併規則。 如果您註冊[!UICONTROL All Cross-Device Profiles]以人物為基礎的目的地[，即可存取第4個設定檔合併規則(](../destinations/people-based-destinations-overview.md))。

建立、編輯或刪除規則需要管理員許可權。 所有使用者都可以檢視及使用現有的[!UICONTROL Profile Merge Rules]。

<!-- create-profile-merge-rule.xml -->

**必要條件：**&#x200B;需要跨裝置資料來源才能建置[!UICONTROL Profile Merge Rule]。 請參閱[建立資料Source](../manage-datasources.md#create-data-source)。

>[!TIP]
>
>如需這些不同控制項的說明，請參閱[定義的設定檔合併規則選項](merge-rule-definitions.md)。

## 基本資訊 {#basic-info}

若要完成[!UICONTROL Basic Information]區段：

1. 為[!UICONTROL Profile Merge Rule]命名。
2. *（選擇性）*&#x200B;說明[!UICONTROL Profile Merge Rule]。 簡潔的說明可協助您定義規則的角色或用途。
3. *（選擇性）*&#x200B;若要將此設定為預設&#x200B;**[!UICONTROL Set as default]**，請選取[!UICONTROL Profile Merge Rule]。 新區段會自動與預設規則相關聯。

## 資料匯出控制 {#data-export-controls}

[資料匯出控制項](../data-export-controls.md)是選擇性分類規則，可套用至[!UICONTROL Profile Merge Rule]。 當動作違反資料隱私權或使用合約時，這些功能會防止您將資料傳送至目的地。 如果您不使用[!UICONTROL Data Export Controls]，請略過此章節。

## 設定檔合併規則設定 {#profile-merge-rule-setup}

若要完成[!UICONTROL Proflie Merge Rule Setup]區段：

1. 選取&#x200B;**[!UICONTROL Authenticated Option]**。 選項包括:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 選取&#x200B;**[!UICONTROL Authenticated Profile Option]** （最多3個）。 這些是您先前已建立的[跨裝置資料來源](merge-rules-start.md)。
3. 選取&#x200B;**[!UICONTROL Device Option]**。 選項包括:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. 按一下 **[!UICONTROL Save]**。

### 使用跨裝置ID作為使用者ID金鑰的Adobe Campaign目的地考量事項 {#considerations}

2019年底，我們發佈了一系列設定檔合併規則增強功能，以改進使用跨裝置ID產生批次檔案的準確性。 自2020年3月16日星期一起，您的Audience Manager執行個體將嚴格遵循這些增強功能。 因此，使用跨裝置ID對應至目的地的區段，在某些設定檔合併規則設定中將會停止產生匯出專案。

為確保您的Audience Manager執行個體與使用跨裝置ID (例如Adobe Campaign)的目的地之間正確整合，請確定您符合下列需求：

1. 檢閱對應至您Adobe Campaign宣告ID目的地的區段所使用的設定檔合併規則。 設定檔合併規則必須使用[!UICONTROL Last Authenticated Profile]選項，所以所有已驗證的設定檔都可以包含在匯出中。 如果您的設定檔合併規則使用不同的選項，請將其切換為[!UICONTROL Last Authenticated Profile]。
2. 在設定檔合併規則設定中選取Adobe Campaign宣告ID資料來源。

>[!NOTE]
>
> 如果您已達到[!UICONTROL Profile Merge Rules]的數量上限，並需要根據上述指示進行設定的協助，請聯絡客戶服務。

## 設定合併規則程式碼 {#configure-merge-rule-code}

請依照這些指示，設定[!UICONTROL Adobe Experience Platform Identity Service]、[!UICONTROL DIL]和行動[!DNL SDK]程式碼以搭配您的合併規則使用。

<!-- merge-rules-configure-code.xml -->

### 先決條件

您必須先設定[跨裝置資料來源](#create-data-source)和[設定檔合併規則](#create-profile-merge-rule) *，然後*&#x200B;才能完成這些程式。

## 適用於Adobe Experience Platform Identity Service客戶 {#id-service-customers}

使用[!UICONTROL Adobe Experience Platform Identity Service]時，建議使用[和最新版本的](../../dil/dil-overview.md)DIL[!UICONTROL Profile Merge Rules]。 不過，您不必使用[!UICONTROL Adobe Experience Platform Identity Service]即可使用此功能。 如果您只使用[!UICONTROL DIL]，請參閱下方的[舊版DIL區段](#legacy-dil)。

### 設定設定客戶ID函式

使用[!UICONTROL Adobe Experience Platform Identity Service]時，`setCustomerIDs`函式會將宣告ID傳遞給[!DNL Audience Manager]。 若要使用設定檔合併規則，您必須修改`setCustomerIDs`以使用您建立跨裝置資料來源時指定的整合代碼。 例如，假設您已使用整合代碼`my_datasource_ic`建立跨裝置資料來源。 若要傳入宣告ID，您可以將整合程式碼新增至訪客ID函式，如下方修改的程式碼範例所示。

#### 一般程式碼範例

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### 修改後的程式碼範例

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

如需詳細資訊，請參閱[建立跨裝置資料Source](#create-data-source)和[客戶ID與驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=zh-Hant)。

### 設定`DIL.create`函式

最新版本的[!UICONTROL DIL]現在會自動從[!UICONTROL declared ID]中的`visitorService`函式中擷取`DIL.create` （請參閱[宣告識別碼變數](../declared-ids.md#declared-id-variables)）。 請檢查您的`DIL.create`函式，確定已正確設定（如下列程式碼範例所示）。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

在名稱空間機碼值組中，`*`MCORG`*`變數是您的[!DNL Experience Cloud]組織識別碼。 如果您沒有此ID，可以在[!UICONTROL Administration]儀表板的[!DNL Experience Cloud]區段中找到。 您需要管理員許可權才能檢視此儀表板。 請參閱[管理：核心服務](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=zh-Hant)。

### 設定SDK

請參閱下方的[設定SDK](#configure-sdks-legacy-dil)區段。

## 舊版DIL {#legacy-dil}

如果您尚未使用[!DNL Adobe Experience Platform Identity Service]，您確實應該使用。 但我們瞭解，使用新程式碼需要進行審慎的思考和測試。 在這些情況下，請檢查您的`DIL.create`函式，以確定已正確設定它，如下列程式碼範例所示。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

如需詳細資訊，請參閱[!UICONTROL DIL]宣告ID變數[中的舊版](../declared-ids.md#declared-id-variables)區段。

### 設定SDK {#configure-sdks-legacy-dil}

檢查您的[!DNL SDK]程式碼中可讓您從[!UICONTROL declared IDs]和[!DNL Android]行動裝置傳遞[!DNL iOS]的方法。 [!DNL Android]和[!DNL iOS]程式碼程式庫的變數名稱相同：

* `dpid`：跨裝置資料來源識別碼。
* `dpuuid`： [!UICONTROL declared ID] （即使用者識別碼）。

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置型別 </th> 
   <th colname="col2" class="entry"> 方法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>語法:</b> </p> <p> <pre> 公用靜態void setDpidAndDpuuid（字串dpid，字串dpuuid）； </pre> </p> <p> <b>範例:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid"，"myDpuuid")； </pre> </p> </td> 
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
      &lbrack;ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"&rbrack;;
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

另請參閱適用於Android的[Audience Manager方法](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html?lang=zh-Hant)和適用於iOS的[Audience Manager方法](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html?lang=zh-Hant)。

>[!MORELIKETHIS]
>
>* [建立資料來源](../manage-datasources.md#create-data-source)
