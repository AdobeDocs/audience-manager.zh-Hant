---
description: 說明您可用來在Audience Manager帳戶中透過所有屬性以地理變數定位使用者的常見平台層級索引鍵值配對。
seo-description: 說明您可用來在Audience Manager帳戶中透過所有屬性以地理變數定位使用者的常見平台層級索引鍵值配對。
seo-title: 使用平台層級的索引鍵進行地理定位
solution: Audience Manager
title: 使用平台層級的索引鍵進行地理定位
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---


# 使用平台層級的索引鍵進行地理定位 {#geotargeting-with-platform-level-keys}

說明您可用來在Audience Manager帳戶中透過所有屬性以地理變數定位使用者的常見平台層級索引鍵值配對。

<!-- c_tb_platform_vars.xml -->

## 平台層級變數的用途 {#platform-variables}

平台層級變數可讓您從特定網站傳入資料，並讓其適用於帳戶中所有屬性的定 [!DNL Audience Manager] 位。 這些變數由鍵值 [配對組成](../../reference/key-value-pairs-explained.md) ，鍵前置詞 `d_` 如下所示。

## 向平台級鍵添加值 {#adding-values}

對於某些平台層級的金鑰，您可以自行指定值。 與其他人一起，密鑰與在事件呼 [!DNL IP] 叫時傳遞的對應地址相關聯。 在這兩種情況下，您仍需要在中建立特徵時指定值 [!UICONTROL Trait Builder]。

## 用戶定義的平台級密鑰 {#user-defined-keys}

您可使用下列索引鍵值配對來建立特徵時指定值：

| 金鑰 | 針對定位 |
|---|---|
| `d_zx` | 郵遞區號(例如 `d_zx=10022`)。 |

## 由IP位址定義的平台層級金鑰 {#keys-ip-address}

我們與 [Digital Envoy合作](https://www.digitalenvoy.com/) ，以取得並更新下列金鑰的人口統計和地理資料。 這些鍵的值是通過將地址與相應的地 [!DNL IP] 理和人口統計資料匹配來確定的。 不過，在中建立鍵值對時，仍必須輸入值參數 [!UICONTROL Trait Builder]。

| 金鑰 | 針對定位 |
|--- |--- |
| d_area_code | [北美地區代碼](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)。  例如： <ul><li>**特徵**:  d_area_code=801</li><li>**特徵名稱**: 猶他州</li></ul> |
| d_city | 城鎮。 下載城 [市清單](assets/d_city.txt)。  例如： <ul><li>特徵：  d_city=bonn</li><li>特徵名稱： 波恩</li></ul> **提示**: 您可搭配使 `d_city` 用，以確 `d_country` 定您不會針對不同國家／地區兩個同名城市。 您可以使用，在您的定位中更具體 `d_postal_code`。 |
| d_country | 值對應於ISO國家代碼。 如需可搜尋的程式碼清單，請參閱 [ISO線上瀏覽平台](https://www.iso.org/obp/ui/#home)。 <br>  針對英國是唯一不遵守ISO 3166的特殊情況。 您應使用「UK」而非「GB」來定位英國。  若要鎖定荷屬安地列斯群島，自2010年起，已淘汰程式碼&quot;AN&quot;。 該地區已分成五個獨立的領土單位。 這意味著，在荷屬安地列斯群島，不應使用&quot;AN&quot;，而應使用&quot;CW&quot;、&quot;SX&quot;和&quot;BQ&quot;的國家代碼組合。  例如：  <br>  特徵：  d_country=CZ特 <br>徵名稱： 捷克共 <br>和國特徵：  d_country=UK特 <br>徵名稱： 英國特 <br>徵：  d_country=CW OR d_country=SX OR d_country=BQ特徵 <br>名稱： 荷屬安地列斯群島 |
| d_dma_code | 城域DMA代碼。 下載 [DMA地區清單](assets/DMAregions.csv) （.csv格式）。  例如： <ul><li>特徵：  d_dma_code=807</li><li>特徵名稱： 舊金山</li></ul> |
| d_lat | Latitude（例如d_lat=40.75）。 下載緯度 [度清單](assets/d_lat.txt)。 |
| d_long | 經度（例如d_long=73.98）。 下載經 [度清單](assets/d_long.txt)。 |
| d_postal_code | 郵遞區號（排除擴充的+4代碼）。 下載郵 [遞區號清單](assets/d_postal_code.txt)。  例如： <ul><li>特徵：  d_postal_code=84004 </li><li>特徵名稱： 阿爾卑斯</li></ul> |
| d_state | 美國各州的縮寫為2個字元。 下載狀 [態代碼清單](assets/d_state.txt)。  例如： <ul><li>特徵：  d_state=NY </li><li>特徵名稱： 紐約</li></ul>d_state包含不同國家／地區不同狀態的重複值。 例如，d_state == &quot;on&quot;符合多個狀態： 安大略省（加拿大）、翁多（奈及利亞）、奧沙納（納米比亞）。 我們建議將此訊號與d_country等其他訊號相連，以取得更詳細的地理定位。 |
| d_region | 地區字母數字ID。 下載地 [區清單](assets/Country_RegionCodes_City.csv)。  然後，您可以使用此清單，將地區ID與地區名稱相符。 |
| d_isp | ISP/組織。 下載 [ISP清單](assets/d_isp.txt)。 |

所有基於 [位置的信號清單](assets/all.txt) ，按以下順序包括上述所有信號： `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)

