---
description: 說明平台層級索引鍵值配對的共用，您可以透過地理變數在Audience Manager帳戶中的所有屬性中鎖定使用者。
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: 使用平台層級索引鍵的Geotargeting
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 366589d51601f438999bfdc6a10c306eb1186742
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# 使用平台層級索引鍵的Geotargeting {#geotargeting-with-platform-level-keys}

說明平台層級索引鍵值配對的共用，您可以透過地理變數在Audience Manager帳戶中的所有屬性中鎖定使用者。

<!-- c_tb_platform_vars.xml -->

## 平台層級變數的用途 {#platform-variables}

平台層級變數可讓您取得從特定網站傳入的資料，並使其可用於在[!DNL Audience Manager]帳戶中的所有屬性中進行目標定位。 這些變數由[索引鍵值配對](../../reference/key-value-pairs-explained.md)組成，其索引鍵前置詞為`d_`，如下所示。

## 將值新增至平台層級的索引鍵 {#adding-values}

對於某些平台層級的索引鍵，您可以自行指定值。 與其他人一樣，金鑰與事件呼叫中傳入的對應[!DNL IP]位址相關聯。 不論使用何種方法，在[!UICONTROL Trait Builder]中建置特徵時，您仍需指定值。

## 使用者定義的平台層級索引鍵 {#user-defined-keys}

如果您已有或正在建立定義並收集索引鍵/值組的程式，則請利用此選項。 如果要使用IP位址預先定義的金鑰，請繼續下一節。 在使用使用者定義索引鍵的情況下，您可在使用下列索引鍵值配對建立特徵時指定值：

| 索引鍵 | 目標定位 |
|---|---|
| `d_zx` | 郵遞區號（例如`d_zx=10022`）。 |

## 由IP位址定義的平台層級金鑰 {#keys-ip-address}

我們與[數位特使](https://www.digitalenvoy.com/)合作，以取得並更新以下金鑰的人口統計和地理資料。 這些金鑰的值是透過比對[!DNL IP]位址與對應的地理和人口統計資料來決定。 不過，在[!UICONTROL Trait Builder]中建立索引鍵/值組時，您仍須輸入value引數。

| 索引鍵 | 目標定位 |
|--- |--- |
| d_area_code | [北美區域碼](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)。  例如： <ul><li>**特徵**： d_area_code=801</li><li>**特徵名稱**： Utah</li></ul> |
| d_city | 城鎮。 下載[城市清單](assets/d_city.txt)。  例如： <ul><li>特徵： d_city=bonn</li><li>特徵名稱：波恩</li></ul> **提示**：您可以搭配使用`d_city`與`d_country`，以確定您未鎖定位於不同國家/地區且名稱相同的兩個城市。 使用`d_postal_code`可更具體說明您的目標定位。 |
| d_country | 值對應至ISO國家/地區代碼。 如需可搜尋的程式碼清單，請參閱[ISO線上瀏覽平台](https://www.iso.org/obp/ui/#home)。 <br>  針對英國目標是唯一不遵守ISO 3166的特殊情況。 在英國的目標定位中，您應該使用「UK」而非「GB」。  若要將目標鎖定在荷屬安地列斯，自2010年起已棄用程式碼「AN」。 該地區已解散，成為五個獨立的領土單位。 這表示在荷屬安地列斯群島進行目標定位時，您不應使用「AN」，而應使用「CW」、「SX」和「BQ」的國家代碼組合。  例如： <br>  特徵： d_country=CZ <br>  特徵名稱：捷克共和國<br>  特徵： d_country=UK <br>  特徵名稱：英國<br>  特徵： d_country=CW OR d_country=SX OR d_country=BQ <br>  特徵名稱：荷屬安地列斯 |
| d_dma_code | 大都會區域DMA代碼。 下載[DMA區域清單](assets/DMAregions.csv) （.csv格式）。  例如： <ul><li>特徵： d_dma_code=807</li><li>特徵名稱：舊金山</li></ul> |
| d_lat | 緯度（例如d_lat=40.75）。 下載[緯度清單](assets/d_lat.txt)。 |
| d_long | 經度（例如d_long=73.98）。 下載[經度清單](assets/d_long.txt)。 |
| d_postal_code | 郵遞區號（排除擴充的+4代碼）。 下載[郵遞區號清單](assets/d_postal_code.txt)。  例如： <ul><li>特徵：d_postal_code=84004 </li><li>特徵名稱： Alpine</li></ul> |
| d_state | 美國州的2個字元縮寫。 下載[狀態碼清單](assets/d_state.txt)。  例如： <ul><li>特徵：d_state=NY </li><li>特徵名稱：紐約</li></ul>d_state包含不同國家/地區之不同狀態的重複值。 例如，d_state==「on」會比對多個州：安大略（在加拿大）、翁多（在奈及利亞）、奧沙納（在納米比亞）。 建議您將此訊號與其他訊號（例如d_country）結合，以取得更具體的地理定位。 |
| d_region | 地區英數字元ID。 下載[區域清單](assets/Country_RegionCodes_City.csv)。  然後，您可以使用此清單來比對地區ID與地區名稱。 |
| d_isp | ISP/組織 下載[ISP清單](assets/d_isp.txt)。 |

[所有以位置為基礎的訊號](assets/all.txt)清單包含以上所有訊號，順序如下： `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)
