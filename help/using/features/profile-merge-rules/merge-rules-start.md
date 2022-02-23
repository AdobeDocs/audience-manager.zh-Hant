---
description: 要建立「配置檔案合併規則」(Profile Merge Rules)，請查看並完成本節中介紹的每個步驟。
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: 設定檔合併規則快速入門
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---

# 設定檔合併規則快速入門 {#getting-started-with-profile-merge-rules}

建立 [!UICONTROL Profile Merge Rules]，審閱並完成本節中介紹的每個過程中的步驟。

<!-- merge-rules-start.xml -->

## 建立跨設備資料源 {#create-data-source}

要建立跨設備資料源，請轉到 **[!UICONTROL Audience Data > Data Sources > Add New]** 並完成此處介紹的每個部分的步驟。 建立或編輯跨設備資料源需要管理員權限。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>請參閱 [資料源設定和菜單選項](../datasources-list-and-settings.md#settings-menu-options) 中。

## 資料源詳細資訊 {#details}

完成 [!UICONTROL Data Source Details] 部分：

1. 命名資料源。
2. *（可選）* 描述資料源。 簡潔的描述有助於定義資料源的角色或用途。
3. 提供整合代碼。 整合代碼是您自己的、唯一的此資料源ID。
4. 在 **[!UICONTROL ID Type]** 清單，選擇 **[!UICONTROL Cross Device]**。
5. 在 **[!UICONTROL ID Definition]** 清單中，選擇定義資料源類型的選項。 選項包括:
   * **[!UICONTROL Person]**:定義單個人的ID。 此ID可以映射到多個 [!DNL Audience Manager] ID。
   * **[!UICONTROL Household]**:定義一組人員的ID。 此ID可以映射到多個 [!DNL Audience Manager] ID。

## 資料匯出控制 {#export-controls}

[資料導出控制項](../data-export-controls.md) 是可應用於資料源和目標的可選分類規則。 當該操作違反資料隱私或使用協定時，它們會阻止您將資料發送到目標。 如果您不使用 [!UICONTROL Data Export Controls]。

## 資料源設定 {#settings}

[!UICONTROL Data Source Settings] section提供了多個選項，但這2個選項對於建立跨設備資料源非常重要：

* **[!UICONTROL Use as Authenticated Profile]**:預設情況下，此設定允許您生成 [!UICONTROL Profile Merge Rule] 用你自己的經過驗證的資料。

* **[!UICONTROL Use as a Device Graph]**:此控制項僅對作為資料提供程式列出的帳戶可用。 選中此複選框將建立資料源作為設備圖形，並允許您與其他資料源共用 [!DNL Audience Manager] 客戶。 與 [!DNL Audience Manager] 顧問：將其設定為資料提供方，並指定此客戶 [!UICONTROL Data Source] 應該與共用。 您的顧問將通過內部資源調配流程來調配帳戶和設備圖形共用。

* **[!UICONTROL Data retention for inactive Customer IDs]**:此控制項允許您設定非活動客戶ID的資料保留期。 這將確定Audience Manager在上次在Audience Manager平台上看到客戶ID後，將客戶ID保留在資料庫中的時間。 預設值為24個月（720天）。 您可以設定的最小值為1個月，最大值為5年。 注意，我們把所有月份都算為30天。 Audience Manager根據您為非活動客戶ID設定的資料保留期，每週運行一次刪除非活動客戶ID的流程。

與這些設定關聯的文本欄位允許您更名 [!UICONTROL Data Source] 出現在 [配置檔案合併規則選項](merge-rule-definitions.md)。 例如，如果向 **[!UICONTROL Use as Authenticated Profile]**，該名稱顯示在 [!UICONTROL Authenticated Profile Options] 清單框。 如果向中添加別名 **[!UICONTROL Use as a Device Graph]**，該名稱顯示在 [!UICONTROL Device Options] 清單框。

## 建立配置檔案合併規則 {#create-profile-merge-rule}

建立 [!UICONTROL Profile Merge Rule]，轉到 **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** 並完成此處介紹的每個部分的步驟。

設定跨設備資料源後，最多可建立3個合併規則。 您可以訪問第4個配置檔案合併規則([!UICONTROL All Cross-Device Profiles])如果您註冊 [基於人的目的地](../destinations/people-based-destinations-overview.md)。

建立、編輯或刪除規則需要管理員權限。 所有用戶都可以查看和使用現有 [!UICONTROL Profile Merge Rules]。

<!-- create-profile-merge-rule.xml -->

**先決條件：** 需要跨設備資料源來構建 [!UICONTROL Profile Merge Rule]。 請參閱 [建立資料源](../manage-datasources.md#create-data-source)。

>[!TIP]
>
>請參閱 [配置檔案合併規則選項已定義](merge-rule-definitions.md) 中。

## 基本資訊 {#basic-info}

完成 [!UICONTROL Basic Information] 部分：

1. 命名 [!UICONTROL Profile Merge Rule]。
2. *（可選）* 描述 [!UICONTROL Profile Merge Rule]。 簡潔的描述可幫助您定義規則的角色或用途。
3. *（可選）* 選擇 **[!UICONTROL Set as default]** 如果要將此設定為預設值 [!UICONTROL Profile Merge Rule]。 新段會自動與預設規則關聯。

## 資料匯出控制 {#data-export-controls}

[資料導出控制項](../data-export-controls.md) 是可選的分類規則 [!UICONTROL Profile Merge Rule]。 當該操作違反資料隱私或使用協定時，它們會阻止您將資料發送到目標。 如果您不使用 [!UICONTROL Data Export Controls]。

## 配置檔案合併規則設定 {#profile-merge-rule-setup}

完成 [!UICONTROL Proflie Merge Rule Setup] 部分：

1. 選擇 **[!UICONTROL Authenticated Option]**。 選項包括:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 選擇 **[!UICONTROL Authenticated Profile Option]** （最多3個，最多）。 這些是 [跨設備資料源](merge-rules-start.md) 您以前建立過。
3. 選擇 **[!UICONTROL Device Option]**. 選項包括:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. 按一下 **[!UICONTROL Save]**.

### 使用跨設備ID作為用戶ID鍵的Adobe Campaign目標的注意事項 {#considerations}

在2019年末，我們發佈了一系列配置檔案合併規則增強功能，以提高使用跨設備ID生成的批處理檔案的準確性。 從2020年3月16日星期一開始，您的Audience Manager實例將嚴格遵守這些增強功能。 因此，使用跨設備ID映射到目標的段將停止在某些配置檔案合併規則配置中生成導出。

要確保使用跨設備ID(如Adobe Campaign)在Audience Manager實例與目標之間正確整合，請確保滿足以下要求：

1. 查看映射到Adobe Campaign聲明ID目標的段使用的配置檔案合併規則。 配置檔案合併規則必須使用 [!UICONTROL Last Authenticated Profile] 選項，因此所有經過驗證的配置檔案都可以包含在導出中。 如果您的「配置檔案合併規則」正在使用其他選項，請將其切換到 [!UICONTROL Last Authenticated Profile]。
2. 在「配置檔案合併規則」設定中選擇「Adobe Campaign聲明的ID」資料源。

>[!NOTE]
>
> 如果已達到最大數量 [!UICONTROL Profile Merge Rules] 並需要根據上述說明在配置它們方面的幫助，請聯繫「客戶服務」。

## 配置合併規則代碼 {#configure-merge-rule-code}

按照以下說明設定 [!UICONTROL Adobe Experience Platform Identity Service]。 [!UICONTROL DIL]，移動 [!DNL SDK] 用於使用合併規則的代碼。

<!-- merge-rules-configure-code.xml -->

### 必要條件

必須設定 [跨設備資料源](#create-data-source) 和 [配置檔案合併規則](#create-profile-merge-rule) *先* 完成這些步驟。

## 針對Adobe Experience Platform身份服務客戶 {#id-service-customers}

的 [!UICONTROL Adobe Experience Platform Identity Service] 以及 [DIL](../../dil/dil-overview.md) 建議使用 [!UICONTROL Profile Merge Rules]。 但是，您不必使用 [!UICONTROL Adobe Experience Platform Identity Service] 使用此功能。 如果你只是用 [!UICONTROL DIL]，請參見 [舊式DIL部分](#legacy-dil) 下。

### 配置「設定客戶ID」功能

使用 [!UICONTROL Adobe Experience Platform Identity Service]，也請參見Wiki頁。 `setCustomerIDs` 函式將聲明的ID傳遞給 [!DNL Audience Manager]。 要使用配置檔案合併規則，必須修改 `setCustomerIDs` 使用建立跨設備資料源時指定的整合代碼。 例如，假設您已建立了具有整合代碼的跨設備資料源 `my_datasource_ic`。 要傳遞已聲明的ID，應將整合代碼添加到訪問者ID函式中，如下面修改的代碼示例所示。

#### 通用代碼示例

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### 修改的代碼示例

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

有關詳細資訊，請參見 [建立跨設備資料源](#create-data-source) 和 [客戶ID和身份驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)。

### 配置 `DIL.create` 函式

最新版本 [!UICONTROL DIL] 現在自動 [!UICONTROL declared ID] 從 `visitorService` 函式 `DIL.create` （請參見） [聲明的ID變數](../declared-ids.md#declared-id-variables))。 檢查 `DIL.create` 函式，確保正確設定此設定，如下面的代碼示例所示。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

在命名空間key-value對中， `*`MCORG`*` 變數 [!DNL Experience Cloud] 組織ID。 如果您沒有此ID，可以在 [!UICONTROL Administration] 的下界 [!DNL Experience Cloud] 控制項欄。 您需要管理員權限才能查看此儀表板。 請參閱 [管理：核心服務](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)。

### 配置SDK

查看 [配置SDK](#configure-sdks-legacy-dil) 的下界。

## 舊DIL {#legacy-dil}

如果你不用 [!DNL Adobe Experience Platform Identity Service] 但是，你真的應該這麼做。 但是，我們明白，轉向新代碼需要仔細的思考和測試。 在這些情況下，檢查 `DIL.create` 函式，確保正確設定此設定，如下面的代碼示例所示。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

有關詳細資訊，請參閱舊版 [!UICONTROL DIL] 部分 [聲明的ID變數](../declared-ids.md#declared-id-variables)。

### 配置SDK {#configure-sdks-legacy-dil}

檢查您的 [!DNL SDK] 允許你通過的代碼 [!UICONTROL declared IDs] 從 [!DNL Android] 和 [!DNL iOS] 移動設備。 的變數名稱 [!DNL Android] 和 [!DNL iOS] 代碼庫相同：

* `dpid`:跨設備資料源ID。
* `dpuuid`:的 [!UICONTROL declared ID] （即用戶ID）。

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設備類型 </th> 
   <th colname="col2" class="entry"> 方法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>語法:</b> </p> <p> <pre> 公共靜態void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>範例:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
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

另請參見 [AndroidAudience Manager方法](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) 和 [Audience ManageriOS方法](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html)。

>[!MORELIKETHIS]
>
>* [建立資料來源](../manage-datasources.md#create-data-source)

