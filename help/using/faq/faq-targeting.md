---
description: 常見定位相關問題和問題。
seo-description: 常見定位相關問題和問題。
seo-title: 定位常見問題
solution: Audience Manager
title: 定位常見問題
uuid: ee96ef71-b903-4953-afc4-8ec8 e48 bd49 e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Targeting FAQ{#targeting-faq}

常見定位相關問題和問題。

<br> 

<!-- 

faq_targeting.xml

 -->

**我可以在哪裡找到Audience Manager支援的第三方資料提供者完整清單？**

See the [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) for a complete list of third-party data providers that [!DNL Audience Manager] supports.

<br> 

**如果要鎖定我在網站上從未見過第三方資料的使用者，我應該在Audience Manager或DSP中使用協力廠商資料嗎？**

答案取決於您的目標。例如，如果您的促銷活動是用來尋找新客戶使用第三方資料，則可直接使用DSP。請記住，只有當我們看到使用者時，Audience Manager才會與第三方資料供應商同步資料。如果我們以前從未見過使用者，我們的系統將不會有該網站訪客的任何資訊。對於只想使用第三方資料來定位從未瀏覽過您的屬性之使用者的促銷活動，請透過DSP建立這些區段。

<br> 

**我可以行銷個人嗎？**

Audience Manager可讓您根據共用屬性或特徵，匯總使用者並行銷他們。However, to comply with industry regulations, [!DNL Audience Manager] customers may not send personally identifiable information (PII) to our systems. 因此，您無法使用電子郵件地址、個人名稱、實體地址等。進行定位。

<br> 

**如何安全地重新定向資料？**

建議您使用伺服器到伺服器連線，與您偏好的重新定位平台交換資料。Audience Manager透過伺服器對伺服器連線，與大部分主要DSP交換資料。伺服器對伺服器資料傳輸可防止其他行為者截取您的資料並重新銷售該受眾資訊。

<br> 

**Audience Manager獨特使用者ID(UUID)是否會直接在頁面上透過ID同步連結至廣告伺服器的唯一使用者ID？**

不會。網站上的發行者或伺服器上不會進行ID同步。The Audience Manager UUID is inserted into the `u=` field of the ad server log files. 當群體傳入以進行定位時會發生此情況。DIL程式碼模組會執行此函數。此機制可讓我們將伺服器使用者ID對應至Audience Manager使用者，以進行區段效能報告。不過，如果廣告伺服器存在於網站上，則我們會直接在頁面上同步ID。

<br> 

**Audience Manager會計算從不同裝置登入不同使用者或不同獨特使用者的使用者嗎？**

[宣告ID定位可](../features/declared-ids.md#declared-id-targeting) 協助Audience Manager使用單一唯一識別碼識別跨多個裝置的訪客。但是，從定位或目的地觀點來看，這仍然是個(或以上)使用者，因為DSP無法調和這個多個ID。

<br> 

**Audience Manager可識別來自顯示和行動裝置的使用者。**

是。See [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting).

<br> 

**我可以為使用者評分線上收集的資料，並根據此模型分數重新定向使用者嗎？**

是。Audience Manager可提供資料檔案以協助您得分，但您必須與其他廠商或軟體合作以分析並排名此資訊。以關鍵值配對的形式傳送此資料至Audience Manager。我們可以處理這項資訊並將它附加至現有的使用者個人檔案。請聯絡您的合作夥伴解決方案代表，以檢閱此程序。

<br> 

**指定-個月期間的Cookie刪除率為何？**

刪除Cookie很困難。大部份的Cookie刪除來自少數刪除Cookie的訪客。不過，大部份的瀏覽器Cookie都穩定至少30天，即使某些瀏覽器的壽命可能有限。有些研究指出，超過30天的上方漏斗定位可有效消除超過30%的瀏覽器目標受眾。如您所知，特定創意訊息的30天宣傳是業界標準。從我們所見，7%的流失是正確的。

刪除Cookie會對觸及和頻率計算造成不良影響。因此，當嘗試瞭解顯示促銷活動規劃的消費者趨勢真實本質時，我們會強調行為資料的價值。我們的客戶可以運用Audience Manager區段重疊報告、最佳曝光頻率報告以及特定日期範圍內獨特使用者趨勢，以更科學地瞭解促銷活動規劃和最佳化的日期範圍。

<br> 

**Audience Manager Cookie的有效期視窗為何？**

使用者介面可讓您判斷Cookie過期間隔。You can set cookies to expire after *n* number of days or never.

<br> 

**在事件呼叫中實施促銷活動創意，是否會讓我們更具成本效益？**

視需要而定。成本是根據獨特使用者而定。如果促銷活動會產生新使用者，則會有更多成本。如果您的促銷活動覆蓋了我們已收集資料的地方，則無需支付額外費用。如果促銷活動在有顯著重疊的相關網站上執行，則新的獨特使用者會有額外的成本。

<br> 

**Audience Manager只會顯示[!UICONTROL Addressable Audiences]目標的度量[!UICONTROL Server-to-Server]和匹配率。Can you explain why we don't see these figures for Cookie and URL destinations?**

其預設為ID同步。For [!UICONTROL Server-to-Server] destinations, we transfer data offline (either real-time or batch) and we need to send the ID that the destination partner understands, so they can map it back to the browser. 區段定址數字是區段總人口數的子集。

In the case of Cookie and URL destinations, the user is already on the browser, and what [!DNL Audience Manager] sends is just the segments that the user qualified for. 目的地合作夥伴只能挑選區段對應並使用該資訊。因此，請考量Cookie和URL目的地的匹配率永遠為100%。
