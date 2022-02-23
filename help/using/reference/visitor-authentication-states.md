---
description: Audience Manager中的訪問者認證狀態確定新特性資訊是寫入訪問者的認證配置檔案還是寫入設備配置檔案，其中從設備配置檔案收集資料。 Audience Manager以相同方式處理事件調用中的訪問者ID身份驗證狀態UNKNOWN和LOGGED_OUT。
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Audience Manager 中的訪客驗證狀態
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Audience Manager 中的訪客驗證狀態{#visitor-authentication-states-in-audience-manager}

Audience Manager中的訪問者認證狀態確定新特性資訊是寫入訪問者的認證配置檔案還是寫入設備配置檔案，其中從設備配置檔案收集資料。 Audience Manager以相同方式處理事件調用中的訪問者ID身份驗證狀態UNKNOWN和LOGGED_OUT。

從 [!DNL Experience Cloud] ID服務v1.5+, `setCustomerID` 方法包括可選 `AuthState` 的雙曲餘切值。 `AuthState` 根據訪問者 [身份驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)。 [!DNL Audience Manager] 根據呼叫中傳遞的身份驗證狀態和 [配置檔案合併規則](../features/profile-merge-rules/merge-rules-dashboard.md) 用於分割。

## 身份驗證狀態：未知 {#auth-status-unknown}

| 請求值 | 從已驗證的配置檔案讀取資訊 | 將新特徵寫入已驗證的配置檔案 |
|---|---|---|
| 0 | <ul><li>是，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles]。</li><li>不，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] 或 [!UICONTROL No Authenticated Profile]。</li></ul> | 否，特性資料被添加到設備配置檔案。 |

示例調用（與驗證狀態對應的請求值被突出顯示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 身份驗證狀態：已驗證 {#auth-status-authenticated}

| 請求值 | 從已驗證的配置檔案讀取資訊 | 將新特徵寫入已驗證的配置檔案 |
|---|---|---|
| 1 | <ul><li>是，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] 或 [!UICONTROL Last Authenticated Profiles]。</li><li>不，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile]。</li></ul> | 是的，特徵資料被添加到經過驗證的配置檔案中。 |

示例調用（與驗證狀態對應的請求值被突出顯示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 身份驗證狀態：註銷(_O) {#auth-status-logged-out}

| 請求值 | 從已驗證的配置檔案讀取資訊 | 將新特徵寫入已驗證的配置檔案 |
|---|---|---|
| 2 | <ul><li>是，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles]。</li><li>不，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] 或 [!UICONTROL No Authenticated Profile]。</li></ul> | 不，特性資料被寫入設備配置檔案。 |

示例調用（與驗證狀態對應的請求值被突出顯示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 執行ID同步 [CID和UUID](../reference/ids-in-aam.md) 在所有三個案例中。

>[!MORELIKETHIS]
>
>* [客戶 ID 和驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)

