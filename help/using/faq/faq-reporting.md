---
description: 常見的報告相關問題和問題。
seo-description: 常見的報告相關問題和問題。
seo-title: 報表常見問答集
solution: Audience Manager
title: 報表常見問答集
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 報表常見問答集{#reporting-faq}

常見的報告相關問題和問題。

<br> 

<!-- 

faq_reports.xml

 -->

**對於新的已登入特徵，為何有時[!UICONTROL Trait Graph]顯示低於預期的數字或0?**

有時，上傳特徵後，不 [!UICONTROL Trait Graph] 會顯示任何結果或顯示低於預期的數字。 當我們收到的資料量如此龐大，以至於傳入處理工作在當天的報告截止日期之後無法完成擷取此資訊時，就會發生此情況。

因此，此資料會延遲傳送至報告系統，不會在用於繪製的1天報告間隔內顯示 [!UICONTROL Trait Graph]。 不過，您可以在7、14、30和60天的報告間隔中，於次日在趨勢 [報告](../reporting/trend-reports.md#trend-report-overview)[](../reporting/general-reports.md#general-reports-overview) 或一般報告中檢視此資料。

<br> 

**某些區段在報表中遺[!UICONTROL Overlap]失。 他們在哪？**

為協助降低計算需求，這些報告會忽略結果中統計上微不足道的資料。 您的區段不會遺失，而是會因為沒有產生有意義的結果或您可鎖定的有用使用者群組而被捨棄。 另請參閱:

* [報告與資料取樣方法](../reporting/report-sampling.md)
* [計算重疊和一般報表中的獨特使用者](../reporting/unique-user-counts.md)。

<br> 

**如果我執行電子郵件行銷促銷活動，如何判斷重新導向的使用者是從該促銷活動還是從其他來源進入我的網站？**

將促銷活動特定查詢字串附加至您要監控之網站區段的URL。 接著，設定特徵規則以擷取此變數。 例如，若您的URL傳入類似的促銷活動ID中， `www.test123.com/electronics?campaign=123`則建立特徵規則以從變數中擷取該資料，其特徵規則會尋找類似標題的 `h_referer` 特徵規則 `h_referer = 'campaign=123'`)。

<br> 

**即時和總區段人口計數之間有何差異？**

* **** 即時：在指定時段內屬於區段並在您的屬性上作用的獨特使用者人數（亦即，該使用者在特定時段內必須已記錄活動）。 [!DNL Audience Manager]

* **** 區段總人口：目前分類於該區段之所有使用者的匯總。

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**我有一個區段，只包含一個特徵。 當我檢視「報告」量度時，其計數不符。 是什麼原因?**

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

**I I Inbound a file and my Inbound receipt shows a mugh of successfully processed records, but reporting shows lover number. 為什麽？**

在後端，已登入的資料僅會附加至在AAM中仍在作用中的使用者(使用者在過去120天 [!UICONTROL DCS] 內必須有最近的活動)。 因此，如果您為已過期的使用者登入資料 [!DNL Audience Manager], [!UICONTROL Inbound][!UICONTROL User Profile Store] 可能會告訴您已登入特定數量的使用者記錄，但如果這些使用者尚未進行任何近期活動，則會在資料送達我們後，將會捨棄此資料，而報告會呈現此資料。

<br> 

**為什麼我跨裝置已登入特徵的特徵獨特性遠高於已登入記錄的總數？**

如果您將跨裝置資料提供者的檔案載入客戶ID之外，Audience manager會執行查閱，以取得與每個已登入的客戶ID相關聯的所有裝置ID。 然後，Audience manager會將已登入的特徵指派給與客戶ID關聯的裝置ID。

例如，假設您已登入100個記錄。 平均而言，AAM會針對每個客戶ID關聯三個裝置ID。 因此，已登入的特徵會指派給300個裝置ID。

單一跨裝置客戶ID可與多個裝置ID關聯有兩個原因：

* 使用者從多部電腦／瀏覽器登入相同的跨裝置帳戶。
* 使用者正在清除其Cookie。 注意：「已放棄」Cookie會在使用者120天未活動後刪除。

<br> 

**為什麼我[!UICONTROL Total Trait Realizations]的長相總是0?**

[!UICONTROL Total Trait Realizations] 對應至頁面載入。 [!UICONTROL Total Trait Realizations] 提供特定特徵即時引發的次數。 此數字僅針對規則型特徵計算。 已登入的特徵一律 [!UICONTROL Total Trait Realizations] 顯示為0。

<br> 

**我建立了一個特徵，[!UICONTROL Trait Graph]而且顯示的數量比[!UICONTROL Unique Trait Realizations]的大[!UICONTROL Total Trait Population]。 這正常嗎？**

您之所以看到這一點，是 [!UICONTROL Unique Trait Realizations] 因為這些是即時度量，但我們用來計算的報表 [!UICONTROL Total Trait Population] 工作並非即時。 在 [!UICONTROL Total Trait Population] 幾天內應該 [!UICONTROL Unique Trait Realizations] 比大。
