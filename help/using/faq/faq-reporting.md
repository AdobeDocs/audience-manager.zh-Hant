---
description: 常見報告相關問題與問題。
seo-description: 常見報告相關問題與問題。
seo-title: 報表常見問答集
solution: Audience Manager
title: 報表常見問答集
uuid: 78cd6c86-8a4a-4748-ab71-b6 e8 d6078 c94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 報表常見問答集{#reporting-faq}

常見報告相關問題與問題。

<br> 

<!-- 

faq_reports.xml

 -->

**對於新上線的特性，為甚麼[!UICONTROL Trait Graph]有時候顯示低於預期數字或0？**

Sometimes, after you upload traits, the [!UICONTROL Trait Graph] doesn't show any results or shows lower than expected numbers. 當我們收到的資料量太大時，傳入處理工作就無法完成吸收此資訊，直到該日期的報告截止日期為止。

As a result, this data is sent to the reporting system late and won't show up in the 1-day reporting interval which is used for plotting the [!UICONTROL Trait Graph]. However, you can view this data in the 7, 14, 30, and 60-day report intervals in a [Trend](../reporting/trend-reports.md#trend-report-overview) or [General Report](../reporting/general-reports.md#general-reports-overview) on the following day.

<br> 

**[!UICONTROL Overlap]報表中缺少部分區段。Where are they?**

為了協助降低計算需求，這些報告忽略了結果中重要資料的統計資料。您的區段不會遺失，因為它們並未產生有意義的結果，或您可以定位的有用使用者群組。另請參閱:

* [報告與資料取樣方法](../reporting/report-sampling.md)
* [在重疊和一般報表中計算獨特使用者](../reporting/unique-user-counts.md)。

<br> 

**如果我執行電子郵件行銷促銷活動，如何判斷重新導向使用者是否來自該促銷活動或其他來源？**

將促銷活動特定的查詢字串附加至您要監視之網站區域的URL。接著，設定特徵規則以擷取此變數。For example, if your URL passes in a campaign ID like this, `www.test123.com/electronics?campaign=123`, then create a trait rule to capture that data from the `h_referer` variable with a trait rule that looks for a header like `h_referer = 'campaign=123'`).

<br> 

**即時和區段人口總數之間有何差異？**

* **即時：** 在某個時段內，屬於區段一部分且在您的屬性上活躍的獨特使用者數量( [!DNL Audience Manager] 亦即，必須已記錄該使用者特定時段內的活動)。

* **區段總人口數：** 目前在該區段中分類之所有使用者的匯總。

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**我的區段只包含一個特徵。當我查看報告量度時，他們的計數不會相符。是什麼原因?**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**我傳入檔案，而我的收件收據會顯示大量成功處理的記錄，但報告顯示的數量較低。為什麽？**

In the backend, onboarded data gets attached only to users that are still active in AAM (user must have had recent [!UICONTROL DCS] activity in the past 120 days). Therefore, if you onboard data for users that have already expired in [!DNL Audience Manager], [!UICONTROL Inbound] might tell you that a certain number of user records were onboarded, but if these users have not had any recent activity, this data is dropped when it reaches our [!UICONTROL User Profile Store] and reporting will surface that.

<br> 

**為甚麼我的跨裝置已登錄特性的特徵獨特項目遠高於已登錄記錄的總數？**

如果您將檔案上線給跨裝置資料提供者以隱藏客戶ID，Audience Manager會執行查閱，以取得所有與已登錄客戶ID關聯的裝置ID。Audience Manager接著將已登錄特性指派給與客戶ID關聯的裝置ID。

例如，假設您已註冊100個記錄。每個客戶ID平均都有關聯的三個裝置ID。因此，已登入的特徵指派給300個裝置ID。

單一跨裝置客戶ID可與多個裝置ID關聯的原因有兩個：

* 使用者從多部電腦/瀏覽器登入相同的跨裝置帳戶。
* 使用者正在清除Cookie。注意：使用者未活動達120天後，即會刪除「放棄」Cookie。

<br> 

**為甚麼[!UICONTROL Total Trait Realizations]我的孤立特性永遠是0？**

[!UICONTROL Total Trait Realizations] 對應頁面載入。[!UICONTROL Total Trait Realizations] 提供即時觸發的次數。此數字僅適用於規則型特徵。Onboarded traits always show [!UICONTROL Total Trait Realizations] as 0.

<br> 

**我建立了特徵，[!UICONTROL Trait Graph]而顯示[!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population]的數量大於。Is this normal?**

You are seeing this because the [!UICONTROL Unique Trait Realizations] are real-time metrics, but the reporting jobs we do to calculate the [!UICONTROL Total Trait Population] are not real-time. The [!UICONTROL Total Trait Population] should be larger than the [!UICONTROL Unique Trait Realizations] within a couple of days.
