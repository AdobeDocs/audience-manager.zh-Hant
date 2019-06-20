---
description: 這些是可定址對象使用的特殊特性。「活動中對象」和「資料來源同步特性」位於「對象資料>特性>對象特徵」中。
seo-description: 這些是可定址對象使用的特殊特性。「活動中對象」和「資料來源同步特性」位於「對象資料>特性>對象特徵」中。
seo-title: 作用中對象特徵和資料來源同步特徵
solution: Audience Manager
title: 作用中對象特徵和資料來源同步特徵
uuid: b4f145ab-f343-4d71-86d1-5d03 f7 b03809
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Active Audience Traits and Data Source Synced Traits {#active-audience-traits-and-data-source-synced-traits}

These are special traits used by [!UICONTROL Addressable Audiences]. [!UICONTROL Active Audience][!UICONTROL Data Source Synced Traits][!UICONTROL Audience Data > Traits > Audience Traits]且位於其中。

>[!NOTE]
>
>存取權限需要管理員權限。

## Active Audience Traits {#active-audience-traits}

[!UICONTROL Active Audience] 特徵包含 [!DNL Audience Manager] 帳戶中管理的所有裝置。You can use an [!UICONTROL Active Audience Trait] like other traits when you build or edit segments. Also, [Addressable Audiences](../../features/addressable-audiences.md) requires this trait to generate overlap data. All accounts have an [!UICONTROL Active Audience] trait by default. 無法刪除此特徵。

## Data Source Synced Traits {#data-source-synced-traits}

[!UICONTROL Data Source Synced Traits] 會出現 [!UICONTROL Audience Traits] 在資料夾中，當您 [建立或編輯資料來源](../../features/manage-datasources.md#create-data-source) 並套用下列任一設定時：

![](assets/datasource_synced.png)

[!UICONTROL Data Source Synced Traits] 追蹤所有與資料來源關聯的使用者。You can use a [!UICONTROL Data Source Synched Trait] like other traits when you build or edit segments. When you create a [!UICONTROL Data Source Synced Trait], the trait name matches the name used by your data source. 編輯資料來源以變更特徵名稱。無法刪除這些特性。

>[!TIP]
>
>[!UICONTROL Data Source Synced Traits] 非常實用。按一下特徵名稱以檢查特徵摘要頁面上的量度。If your selected trait returns data, that indicates the ID synchronization process is set up properly and pushing data to [!DNL Audience Manager].

>[!MORE_贊_ this]
>
>* [可定址對象](../../features/addressable-audiences.md)

