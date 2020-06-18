---
description: 報表的相關常見疑問與問題。
seo-description: 報表的相關常見疑問與問題。
seo-title: 報表常見問題集
solution: Audience Manager
title: 報表常見問題集
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 100%

---


# 報表常見問題集{#reporting-faq}

報表的相關常見疑問與問題。

<br> 

<!-- 

faq_reports.xml

 -->

**針對新的已上線特徵，為何[!UICONTROL Trait Graph]有時會顯示低於預期的數字或 0？**

上傳特徵後，有時 [!UICONTROL Trait Graph] 不會顯示任何結果或顯示低於預期的數字。當我們收到的資料量非常龐大，以致於傳入處理工作無法在當天的報表截止期限之前將這些資訊擷取完成，就會發生此情況。

因此，這些資料會延遲傳送至報表系統，且不會在用於製作 [!UICONTROL Trait Graph] 的 1 日報表間隔內顯示。不過，您可以在 7、14、30 和 60 日的報表間隔中，於次日在[趨勢](../reporting/trend-reports.md#trend-report-overview)或[一般報表](../reporting/general-reports.md#general-reports-overview)中檢視這些資料。

<br> 

**[!UICONTROL Overlap]報表中缺少某些區段。它們在哪裡？**

為協助降低計算需求，這些報表會忽略結果中不具統計價值的資料。您的區段沒有消失，而是因為不會產生有意義的結果或您可定位的有用使用者群而被系統捨棄。另請參閱：

* [報表與資料取樣方法](../reporting/report-sampling.md)
* [計算重疊和一般報表中的不重複使用者數](../reporting/unique-user-counts.md)。

<br> 

**如果我執行電子郵件行銷活動，如何判斷經過重新導向的使用者是從該行銷活動還是從其他來源進入我的網站？**

請將行銷活動專屬的查詢字串附加至您要監控之網站區段的 URL。接下來，設定要用於擷取此變數的特徵規則。例如，若您的 URL 傳入的行銷活動 ID 類似 `www.test123.com/electronics?campaign=123`，那麼可建立一個特徵規則，使用會尋找類似 `h_referer = 'campaign=123'` 標題的特徵規則，從 `h_referer` 變數中擷取該資料。

<br> 

**即時和總區段母體計數之間有何差異？**

* **即時：**&#x200B;在指定時段內屬於區段且在您的屬性上處於為作用中狀態的不重複使用者人數 (也就是 [!DNL Audience Manager] 必須已記錄該使用者在特定時段內的活動)。

* **總區段母體：**&#x200B;目前分類至該區段的所有使用者的彙總。

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**我有一個區段只包含一個特徵。我查看「報表」量度時發現其中的數量不符。原因是什麼？**

請參閱[區段產生器的特徵和區段母體資料](../features/segments/segment-builder-data.md)。

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**我傳入一個檔案，而我的傳入接收訊息顯示已成功處理大量記錄，但報表中顯示的數量卻少很多。為什麽會這樣？**

在後端，已上線的資料只會附加至在 AAM 中仍處於作用中狀態的使用者 (使用者在過去 120 天內必須有最近的 [!DNL DCS] 活動)。因此，如果您將已在 [!DNL Audience Manager] 中失效的使用者之資料上線，[!UICONTROL Inbound] 可能會告訴您某個數量的使用者記錄已上線，但如果這些使用者近期未曾進行任何活動，當資料傳至我們的 [!UICONTROL User Profile Store] 後，系統將會捨棄這些資料，並反映在報表中。

<br> 

**為什麼我跨裝置已上線特徵的不重複特徵數遠高於已上線記錄的總數？**

某個跨裝置資料提供者將客戶 ID 作為輸入資料，如果您將該提供者的檔案上線，Audience Manager 會執行查閱，以取得與每個已上線客戶 ID 相關聯的所有裝置 ID。接著 Audience Manager 會將已上線的特徵指派給與客戶 ID 相關聯的裝置 ID。

例如，假設您已將 100 筆記錄上線。平均而言，AAM 會將每個客戶 ID 與三個裝置 ID 建立關聯。因此，已上線的特徵會指派給 300 個裝置 ID。

一個跨裝置客戶 ID 可與多個裝置 ID 建立關聯的原因有兩個：

* 使用者從多部電腦/瀏覽器登入相同的跨裝置帳戶。
* 使用者正在清除其 Cookie。注意：「已放棄」Cookie 會在使用者 120 天無活動後刪除。

<br> 

**為什麼我已上線特徵的[!UICONTROL Total Trait Realizations]一直都是 0？**

[!UICONTROL Total Trait Realizations] 對應至頁面載入次數。[!UICONTROL Total Trait Realizations] 會即時提供特定特徵引發的次數。此數字只會針對規則型特徵進行計算。已上線的特徵會一律將 [!UICONTROL Total Trait Realizations] 顯示為 0。

<br> 

**我建立了一個特徵，而[!UICONTROL Trait Graph]顯示的[!UICONTROL Unique Trait Realizations]數量比的[!UICONTROL Total Trait Population]還多。這個情況正常嗎？**

您之所以看到這個情況，是因為 [!UICONTROL Unique Trait Realizations] 為即時量度，但我們用來計算 [!UICONTROL Total Trait Population] 的報表工作並非即時執行。幾天內 [!UICONTROL Total Trait Population] 應該會比 [!UICONTROL Unique Trait Realizations] 還多。
