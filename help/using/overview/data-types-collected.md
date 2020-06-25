---
description: Audience Manager 可協助您收集和管理第一方、第二方及第三方資料。
seo-description: Audience Manager 可協助您收集和管理第一方、第二方及第三方資料。
seo-title: 收集的資料類型
solution: Audience Manager
title: 收集的資料類型
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: overview
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 72%

---


# 收集的資料類型 {#types-of-data-collected}

[!DNL Audience Manager] 可協助您收集和管理第一方、第二方及第三方資料。

解鎖儲存在多個孤立環境中的客戶資訊資產，是公司目前面臨的最大資料難題之一。From [!DNL CRM] databases, to registration systems, to ad servers, and so forth, companies require tools that help centralize valuable data and manage customer/audience information as a single strategic data asset. [!DNL Audience Manager] 可協助您解除鎖定孤立的客戶資訊，並管理來自多個來源的資料收集。Collected data can be managed based on data element time-to-live ([!DNL TTL]) values, which helps the publisher control data expiration across all sources. [!DNL Audience Manager] 的設計用途是協助您管理下列類型的資料：

| 資料類型 | 資料來源 |
|---|---|
| **第一方** | 客戶。資料會以線上 (從您網站上的消費者互動) 或離線方式收集。 |
| **第二方** | 策略合作夥伴和廣告商。 |
| **第三方** | 資料提供者和或交換。資料可包含意圖、人口統計、社交/生活風格、心理變數等資訊。 |

## 第一方資料收集 {#first-party-data}

First-party data collection is a main [!DNL Audience Manager] feature. 我們的客戶 (發佈商或廣告商) 希望將專屬資料當做行銷方案的基石，或針對其他資料來源進行定位和模型建模，而這個核心功能可滿足這些客戶的需求。

[!DNL Audience Manager] 與客戶合作，瞭解其資料策略，然後將該策略對應回自訂資料收集計畫。我們的合作夥伴解決方案團隊會與您合作，評估網站、原始資料訊號和其他使用者在您網站上的互動。我們將透過這些資訊，協助您建立量身打造的資料收集策略，從您詳細目錄中的不同頁面擷取使用者層級資料訊號。擷取的資料會儲存並對應回預先定義的分類法，且可隨時依您的業務需求變更進行更新。

下列範例說明如何從範例購物頁面擷取潛在資料元素。

![shopping-cart-data](assets/shopping-cart-data.png)

| 項目 | 說明 |
|---|---|
| 1 | **性別**。購物者的名字通常可看出其性別。在範例中，購物者的名字是 Mary，由此可知購物者是女性。Audience Manager 絕不會儲存姓名。 |
| 2 | **興趣**。購物車中的商品可能表示各種興趣。在範例中，Mary 花了很多錢購買健身器材。 |
| 3 | **房屋類型**。根據運送和/或帳單地址，可以推斷 Mary 是為自己還是為公司購買健身器材。 |
| 4 | **位置**。[!DNL ZIP] 在確定位置時， [!DNL IP] 代碼比地址更可靠。 |
| 5 | **促銷活動相似性**。如果購物者使用促銷代碼或禮品卡，他們很可能是尋找最優惠交易的精打細算買家。 |
| 6 | **消費能力**。Price data correlated with [!DNL ZIP+4] codes indicate spending power of a given location. |

After the raw data is collected, it gets mapped back to customer-defined traits within the [!DNL Audience Manager] platform. 分類法和資料對應都可隨時調整，不需變更資料收集程式碼。

## 第二方資料收集 {#second-party-data}

第二方資料來自策略商業夥伴 (並非發佈商資料)。收集和管理這些資訊的方式與第一方資料相同。

在第二方資料情境中，廣告商會將自己的資料資產傳送給發佈商，以便將該資訊與發佈商的資料結合，然後執行更具針對性的廣告方案。此外，發佈商可與廣告商合作以擴大其受眾群規模。In most cases, these arrangements involve contractual relationships limited to putting the [!DNL Audience Manager] container tag on the partner site to facilitate data collection and sharing.

第二方資料收集與再行銷的範例，可能包含服裝零售商收集其產品的相關資料，然後與主要合作夥伴共用這些資訊。In this case, the retailed could serve different ads across an [!DNL Audience Manager] partner site for consumers who chose various jacket colors and sizes.

![](assets/shopping-cart-traits.png)

## 第三方資料收集 {#third-party-data}

Third-party data is information collected and shared by vendors outside of [!DNL Audience Manager].

Third-party data can be used to qualify existing data [!UICONTROL segments] (for example, age, household income, and so forth), provide data that is in demand but not otherwise available, or be used in lookalike modeling against a known user base from first-party and second-party data. [!DNL Audience Manager] 可與許多第三方資料提供者合作，且可協助您瞭解這些資料提供者收集的資料類型，讓您能與每個提供者進行正確的策略交易。

>[!NOTE]
>
>如需 [!DNL Audience Manager] 支援的第三方資料提供者完整清單，請參閱 [Adobe Audience Finder](https://www.adobe-audience-finder.com/)。

[!DNL Audience Manager] 根據其他資料提供者的可用資料集與 [!DNL APIs] 其他資料提供者整合。 資料收集會在使用者瀏覽您的網站時即時執行，或是透過頻外方法執行，在使用者離開您的網站後，於合作夥伴之間同步 ID，並在伺服器之間傳輸資料。In either case, [!DNL Audience Manager] clients get the benefit of having third-party data synchronized on our platform, which means each client, or domain, does not have to perform its own synchronization. 這麼做有助於增加觸及率，以及減少頁面上的伺服器呼叫。

## 比對合作夥伴 {#match-partners}

許多客戶選擇與第三方資料比對合作夥伴合作。這些實體與具有註冊要求的網站有關係，且可根據客戶的註冊網路，透過即時比對客戶資料檔案來處理這些檔案。

![data-provider-match](assets/data-provider-match.png)
