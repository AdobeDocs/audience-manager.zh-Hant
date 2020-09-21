---
description: Audience Manager中的訪客驗證狀態會判斷新特徵資訊是寫入訪客的已驗證描述檔，還是寫入裝置描述檔，而裝置描述檔是收集資料的來源。 Audience Manager會以相同方式處理事件呼叫中的訪客ID驗證狀態UNKNOWN和LOGGED_OUT。
keywords: dpm.demdex.net
seo-description: Audience Manager中的訪客驗證狀態會判斷新特徵資訊是寫入訪客的已驗證描述檔，還是寫入裝置描述檔，而裝置描述檔是收集資料的來源。 Audience Manager會以相同方式處理事件呼叫中的訪客ID驗證狀態UNKNOWN和LOGGED_OUT。
seo-title: Audience Manager 中的訪客驗證狀態
solution: Audience Manager
title: Audience Manager 中的訪客驗證狀態
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Audience Manager 中的訪客驗證狀態{#visitor-authentication-states-in-audience-manager}

Audience Manager中的訪客驗證狀態會判斷新特徵資訊是寫入訪客的已驗證描述檔，還是寫入裝置描述檔，而裝置描述檔是收集資料的來源。 Audience Manager會以相同方式處理事件呼叫中的訪客ID驗證狀態UNKNOWN和LOGGED_OUT。

從 [!DNL Experience Cloud] ID服務v1.5+開始，此方法 `setCustomerID` 包含選用物 `AuthState` 件。 `AuthState` 根據訪客的驗證狀態 [識別訪客](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)。 [!DNL Audience Manager] 根據呼叫中傳遞的驗證狀態和您用於劃分的描述檔合併規則，以不同方式處 [理已實現的特徵](../features/profile-merge-rules/merge-rules-dashboard.md) 。

## 驗證狀態：未知 {#auth-status-unknown}

| 請求值 | **從已驗證** 的配置檔案讀取資訊 | **將新特徵** 寫入已驗證的設定檔 |
---------|----------|---------
| 0 | <ul><li>是，如果「已驗證選項合併規則」=「上次驗證的設定檔」。</li><li>否，如果「已驗證選項合併規則」=「目前已驗證的設定檔」或「無已驗證的設定檔」。</li></ul> | 否，特徵資料會新增至裝置描述檔。 |


範例呼叫（與驗證狀態對應的請求值會反白顯示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 驗證狀態：已驗證 {#auth-status-authenticated}

| 請求值 | **從已驗證** 的配置檔案讀取資訊 | **將新特徵** 寫入已驗證的設定檔 |
---------|----------|---------
| 1 | <ul><li>是，如果「已驗證選項合併規則」=「目前已驗證的設定檔」或「上次驗證的設定檔」。</li><li>否，如果「已驗證選項合併規則」=「無已驗證配置檔案」。</li></ul> | 是的，特徵資料會新增至已驗證的描述檔。 |

範例呼叫（與驗證狀態對應的請求值會反白顯示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 驗證狀態：已登出 {#auth-status-logged-out}

| 請求值 | **從已驗證** 的配置檔案讀取資訊 | **將新特徵** 寫入已驗證的設定檔 |
---------|----------|---------
| 2 | <ul><li>是，如果「已驗證選項合併規則」=「上次驗證的設定檔」</li><li>否，如果「已驗證選項合併規則」=「目前已驗證的設定檔」或「沒有已驗證的設定檔」</li></ul> | 否，特徵資料會寫入裝置描述檔。 |

範例呼叫（與驗證狀態對應的請求值會反白顯示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 在這三種情況下 [執行CID與UUID](../reference/ids-in-aam.md) 的ID同步。

>[!MORELIKETHIS]
>
>* [客戶 ID 和驗證狀態](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

