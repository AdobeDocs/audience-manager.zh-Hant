---
description: Audience Manager中的訪客驗證狀態會決定新特徵資訊會寫入訪客已驗證的設定檔中，還是寫入資料收集來源裝置設定檔中。 Audience Manager會以相同方式處理事件呼叫中的訪客ID驗證狀態UNKNOWN和LOGGED_OUT。
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Audience Manager中的訪客驗證狀態
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Audience Manager中的訪客驗證狀態{#visitor-authentication-states-in-audience-manager}

Audience Manager中的訪客驗證狀態會決定新特徵資訊會寫入訪客已驗證的設定檔中，還是寫入資料收集來源裝置設定檔中。 Audience Manager會以相同方式處理事件呼叫中的訪客ID驗證狀態UNKNOWN和LOGGED_OUT。

從[!DNL Experience Cloud] ID服務1.5版以後的版本開始，`setCustomerID`方法包含選用的`AuthState`物件。 `AuthState`會根據訪客的[驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)來識別訪客。 [!DNL Audience Manager]會根據呼叫中傳遞的驗證狀態以及您用於細分的[設定檔合併規則](../features/profile-merge-rules/merge-rules-dashboard.md)，以不同方式處理已實現的特徵。

## 驗證狀態：未知 {#auth-status-unknown}

| 請求值 | 從已驗證的設定檔讀取資訊 | 將新特徵寫入已驗證的設定檔 |
|---|---|---|
| 0 | <ul><li>是，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles]。</li><li>否，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles]或[!UICONTROL No Authenticated Profile]。</li></ul> | 否，特徵資料會新增至裝置設定檔。 |

呼叫範例（與驗證狀態對應的請求值會醒目提示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 驗證狀態： AUTHENTICATED {#auth-status-authenticated}

| 請求值 | 從已驗證的設定檔讀取資訊 | 將新特徵寫入已驗證的設定檔 |
|---|---|---|
| 1 | <ul><li>是，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles]或[!UICONTROL Last Authenticated Profiles]。</li><li>否，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile]。</li></ul> | 是，特徵資料會新增至已驗證的設定檔。 |

呼叫範例（與驗證狀態對應的請求值會醒目提示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 驗證狀態：LOGGED_OUT {#auth-status-logged-out}

| 請求值 | 從已驗證的設定檔讀取資訊 | 將新特徵寫入已驗證的設定檔 |
|---|---|---|
| 2 | <ul><li>是，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles]。</li><li>否，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles]或[!UICONTROL No Authenticated Profile]。</li></ul> | 否，特徵資料會寫入裝置設定檔中。 |

呼叫範例（與驗證狀態對應的請求值會醒目提示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>在所有三種情況下，[!DNL Audience Manager]都會在[CID和UUID](../reference/ids-in-aam.md)之間執行ID同步處理。

>[!MORELIKETHIS]
>
>* [客戶 ID 和驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)
