---
description: 若要建立「設定檔合併規則」，請檢閱並完成本節所述每個程序中的步驟。
seo-description: 若要建立「設定檔合併規則」，請檢閱並完成本節所述每個程序中的步驟。
seo-title: 設定檔合併規則快速入門
solution: Audience Manager
title: 設定檔合併規則快速入門
uuid: 7d32c60f-467c-42dd-afa9-437fd7 c473 c
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Getting Started with Profile Merge Rules {#getting-started-with-profile-merge-rules}

To create [!UICONTROL Profile Merge Rules], review and complete the steps in each of the procedures described in this section.

<!-- merge-rules-start.xml -->

## Create a Cross-Device Data Source {#create-data-source}

To create a cross-device data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. 建立或編輯跨裝置資料來源需要管理員權限。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. 命名資料來源。
1. *(可選)* 說明資料來源。簡明扼要的說明可協助您定義資料來源的角色或目的。
1. 提供整合代碼。整合代碼是此資料來源專屬的唯一ID。
1. In the **[!UICONTROL ID Type]** list, select **[!UICONTROL Cross Device]**.
1. In the **[!UICONTROL ID Definition]** list, select an option that defines the data source type. 選項包括:
   * **[!UICONTROL Person]**：定義單一人員的ID。This ID can be mapped to multiple [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**：定義一組人員的ID。This ID can be mapped to multiple [!DNL Audience Manager] IDs.

## 資料匯出控制 {#export-controls}

[「資料匯出控制」](../../features/data-export-controls.md) 是可選的分類規則，您可套用至資料來源和目的地。當該動作違反資料隱私權或使用合約時，就無法將資料傳送至目的地。Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] 區段提供多種選項，但這對於建立跨裝置資料來源而言很重要：

* **[!UICONTROL Use as Authenticated Profile]**：根據預設，此設定可讓您使用自己的驗證資料建立一個。[!UICONTROL Profile Merge Rule]

* **[!UICONTROL Use as a Device Graph]**：此控制項僅適用於列為資料供應商的帳戶。Selecting this check box creates your data source as a device graph and lets you share it with other [!DNL Audience Manager] customers. Work with your [!DNL Audience Manager] consultant to get set up as a data provider and to specify which customers this [!UICONTROL Data Source] should be shared with. 您的顧問會透過內部布建程序來布建您的帳戶和裝置圖表共用。

* **[!UICONTROL Data retention for inactive Customer IDs]**：此控制項可讓您設定非活動中客戶ID的資料保留期間。這可判斷Audience Manager在Audience Manager平台上最後一次看到後，Audience Manager會保留客戶ID的時間。預設值為24個月(720天)。您可以設定的最小值為個月，而最大值為年。請注意，我們將所有月份計為30天。Audience Manager會執行一個程序，根據您為非活動客戶ID設定的資料保留，每周刪除一次非活動中客戶ID。

The text fields associated with these settings let you rename the [!UICONTROL Data Source] with an alias that appears in the [Profile Merge Rule options](../../features/profile-merge-rules/merge-rule-definitions.md). For example, if you add an alias to **[!UICONTROL Use as Authenticated Profile]**, that name appears in the [!UICONTROL Authenticated Profile Options] list. If you add an alias to **[!UICONTROL Use as a Device Graph]**, that name appears in the [!UICONTROL Device Options] list.

>[!MORE_贊_ this]
>
>* [建立資料來源](../../features/manage-datasources.md#create-data-source)


## Create a Profile Merge Rule {#create-profile-merge-rule}

To create a [!UICONTROL Profile Merge Rule], go to **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** and complete the steps for each section described here. 設定跨裝置資料來源後，您最多可以建立合併規則。需要管理員權限才能建立、編輯或刪除規則。All users can view and use existing [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**必要條件：** 建立一個跨裝置資料來源 [!UICONTROL Profile Merge Rule]是必要的。See [Create a Data Source](../../features/manage-datasources.md#create-data-source).

>[!TIP]
>
>See [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md) for descriptions of these different controls.

## 基本資訊 {#basic-info}

To complete the [!UICONTROL Basic Information] section:

1. Name the [!UICONTROL Profile Merge Rule].
2. *(選擇性)* 說明 [!UICONTROL Profile Merge Rule]。簡明扼要的說明可協助您定義規則的角色或目的。
3. *(選用)* 如果 **[!UICONTROL Set as default]** 要將此預設為預設 [!UICONTROL Profile Merge Rule]值，請選取。新區段會自動與預設規則關聯。

## 資料匯出控制 {#data-export-controls}

[「資料匯出控制」](../../features/data-export-controls.md) 是可選的分類規則，您可套用 [!UICONTROL Profile Merge Rule]至您的。當該動作違反資料隱私權或使用合約時，就無法將資料傳送至目的地。Skip this section if you do not use [!UICONTROL Data Export Controls].

## Profile Merge Rule Setup {#profile-merge-rule-setup}

To complete the [!UICONTROL Proflie Merge Rule Setup] section:

1. Select an **[!UICONTROL Authenticated Option]**. 選項包括:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Select an **[!UICONTROL Authenticated Profile Option]** (up to 3, maximum). These are the [cross-device data sources](../../features/profile-merge-rules/merge-rules-start.md) you have created previously.
3. 選擇 **[!UICONTROL Device Option]**. 選項包括:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Click **[!UICONTROL Save]**.

## Configure Merge Rule Code {#configure-merge-rule-code}

Follow these instructions to set up the [!UICONTROL Experience Cloud ID Service], [!UICONTROL DIL], and mobile [!DNL SDK] code to work with your merge rules.

<!-- merge-rules-configure-code.xml -->

### 必備條件

You must set up a [cross-device data source](#create-data-source) and [profile merge rules](#create-profile-merge-rule) *before* completing these procedures.

## For Experience Cloud ID Service Customers {#id-service-customers}

The [!UICONTROL Experience Cloud ID Service] and the latest version of [DIL](../../dil/dil-overview.md) are recommended when working with [!UICONTROL Profile Merge Rules]. However, you don&#39;t have to use the [!UICONTROL Experience Cloud ID Service] to work with this feature. If you&#39;re just using [!UICONTROL DIL], see the [legacy DIL section](../../features/profile-merge-rules/merge-rules-start.md#legacy-dil) below.

### 設定設定客戶ID函數

When working with the [!UICONTROL Experience Cloud ID Service], the `setCustomerIDs` function passes declared IDs to [!DNL Audience Manager]. To use a profile merge rule, you must modify `setCustomerIDs` to use the integration code specified when you created a cross-device data source. For example, say you&#39;ve created a cross-device data source with the integration code `my_datasource_ic`. 若要傳入宣告的ID，您可以將整合代碼新增至訪客ID函數，如下面修改的代碼範例所示。

#### 通用程式碼範例

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

For more information, see [Create a Cross-Device Data Source](#create-data-source) and [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html).

### Configure `DIL.create` function

The latest versions of [!UICONTROL DIL] now automatically pick up the [!UICONTROL declared ID] from the `visitorService` function in `DIL.create` (see [Declared ID Variables](../../features/declared-ids.md#declared-id-variables)). Check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>var vDIL= DIL. create({合作夥伴：「合作夥伴名稱」，visitorService：{namespace：「<i>INSERT-MCORG-ID-HERE</i>」}})；</code>
</pre>

In the namespace key-value pair, the `*`MCORG`*` variable is your [!DNL Experience Cloud] Organization ID. If you don&#39;t have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. 您需要管理員權限才能檢視此控制面板。See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### 設定SDK

See the [Configure SDKs](../../features/profile-merge-rules/merge-rules-start.md#configure-sdks) section below.

## Legacy DIL {#legacy-dil}

If you&#39;re not using [!DNL Experience Cloud ID Service] yet, you really ought to. 但是，我們瞭解移至新程式碼需要仔細思考和測試。In these cases, check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>DIL. create({partner：「合作夥伴名稱」，陳述式ID：{dpuuid：<i>dpuuid</i>，dpid：<i>dpid</i>}})；</code>
</pre>

For more information, see the legacy [!UICONTROL DIL] section in [Declared ID Variables](../../features/declared-ids.md#declared-id-variables).

### Configure SDKs {#configure-sdks-legacy-dil}

Check the methods in your [!DNL SDK] code that let you pass [!UICONTROL declared IDs] from [!DNL Android] and [!DNL iOS] mobile devices. The variable names for the [!DNL Android] and [!DNL iOS] code libraries are the same:

* `dpid`：跨裝置資料來源ID。
* `dpuuid`：( [!UICONTROL declared ID] 亦即使用者ID)。

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>語法:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid，String dpuuid)； </pre> </p> <p> <b>範例:</b> </p> <p> <pre> AudienceManager. setDpidAndDpuuid(「myDpid」，「mydpuuid」)； </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> AudienceSetDpid：dpuuid </code> </p> <p> <b>語法:</b> </p><p>
    <code class="javascript">+(void) AudienceSetDpid：(nSString*) dpid
dpuuid：(nSString*) dpuuid； </code>
 </p>
    <p> <b>範例:</b> </p><p>
    <code class="javascript">[ADBMobile AudienceSetDpid：@「290」dpuuid：@「993013939940」]； </code>
 </p>
    </td>
  </tr>
 </tbody>
</table>

See also, [Audience Manager Methods for Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) and [Audience Manager Methods for iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html).
