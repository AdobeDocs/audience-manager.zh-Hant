---
description: 說明常用的平台層級索引鍵值配對，您可用來鎖定具有地理變數的使用者，並鎖定Audience Manager帳戶中所有屬性的使用者。
seo-description: 說明常用的平台層級索引鍵值配對，您可用來鎖定具有地理變數的使用者，並鎖定Audience Manager帳戶中所有屬性的使用者。
seo-title: 使用平台層級的索引鍵進行地理定位
solution: Audience Manager
title: 使用平台層級的索引鍵進行地理定位
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: 特徵
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 4%

---

# 使用平台層級的索引鍵進行地理定位 {#geotargeting-with-platform-level-keys}

說明常用的平台層級索引鍵值配對，您可用來鎖定具有地理變數的使用者，並鎖定Audience Manager帳戶中所有屬性的使用者。

<!-- c_tb_platform_vars.xml -->

## 平台層級變數{#platform-variables}的用途

平台層級變數可讓您取用從特定網站傳入的資料，並讓其可用於[!DNL Audience Manager]帳戶中所有屬性的定位。 這些變數由[key-value對](../../reference/key-value-pairs-explained.md)組成，鍵首碼為`d_`，如下所示。

## 將值新增至平台層級索引鍵{#adding-values}

對於某些平台層級索引鍵，您可以自行指定值。 與其他地址相關聯的密鑰與在事件調用中傳入的相應[!DNL IP]地址相關聯。 無論是哪種情況，您在[!UICONTROL Trait Builder]中建立特徵時仍需指定值。

## 用戶定義的平台級鍵{#user-defined-keys}

使用下列索引鍵值配對建立特徵時，請指定值：

| 金鑰 | 目標定位 |
|---|---|
| `d_zx` | 郵遞區號（例如`d_zx=10022`）。 |

## 由IP地址{#keys-ip-address}定義的平台級別密鑰

我們與[Digital Envoy](https://www.digitalenvoy.com/)合作，取得並更新下列金鑰的人口統計和地理資料。 這些鍵的值是通過將[!DNL IP]地址匹配到相應的地理和人口統計資料來確定的。 不過，在[!UICONTROL Trait Builder]中建立機碼 — 值組時，您仍須輸入值參數。

| 金鑰 | 目標定位 |
|--- |--- |
| d_area_code | [北美地區代碼](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)。例如： <ul><li>**特徵**:d_area_code=801</li><li>**特徵名稱**:猶他州</li></ul> |
| d_city | 城鎮。 下載[城市清單](assets/d_city.txt)。  例如： <ul><li>特徵： d_city=bonn</li><li>特徵名稱：波恩</li></ul> **提示**:您可以 `d_city` 搭配使 `d_country` 用，以確定您鎖定的目標並非兩個名稱相同且位於不同國家/地區的城市。使用`d_postal_code`可在目標定位中更具體。 |
| d_country | 值對應於ISO國家/地區代碼。 有關代碼的可搜索清單，請參閱[ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home)。 <br>  針對英國的目標定位是唯一不遵守ISO 3166的特殊情況。在英國，您應使用「UK」而非「GB」來進行目標定位。  為了鎖定荷屬安地列斯群島，自2010年起已棄用程式碼「AN」。 該地區已分為五個獨立的領土單位。 這意味著，在荷屬安地列斯群島進行目標定位時，不應使用&quot;AN&quot;，而應使用&quot;CW&quot;、&quot;SX&quot;和&quot;BQ&quot;的國家/地區代碼的組合。  例如： <br>  特徵： d_country=CZ <br>  特徵名稱：捷克共和國<br>  特徵： d_country=UK <br>  特徵名稱：聯合王國<br>  特徵： d_country=CW OR d_country=SX OR d_country=BQ <br>  特徵名稱：荷屬安地列斯 |
| d_dma_code | 城域DMA代碼。 下載[DMA地區清單](assets/DMAregions.csv)（.csv格式）。  例如： <ul><li>特徵： d_dma_code=807</li><li>特徵名稱：舊金山</li></ul> |
| d_lat | 緯度（例如d_lat=40.75）。 下載[緯度清單](assets/d_lat.txt)。 |
| d_long | 經度（例如d_long=73.98）。 下載[經度清單](assets/d_long.txt)。 |
| d_postal_code | 郵遞區號（排除延伸+4代碼）。 下載[郵遞區號清單](assets/d_postal_code.txt)。  例如： <ul><li>特徵： d_postal_code=84004 </li><li>特徵名稱：阿爾派</li></ul> |
| d_state | 美國州的2個字元縮寫。 下載[狀態代碼清單](assets/d_state.txt)。  例如： <ul><li>特徵： d_state=NY </li><li>特徵名稱：紐約</li></ul>d_state包含不同國家/地區中不同狀態的重複值。 例如，d_state == &quot;on&quot;可匹配多個狀態：安大略（加拿大）、翁多（奈及利亞）、奧沙納（納米比亞）。 我們建議將此訊號與d_country等其他訊號結合，以便進行更具體的地理定位。 |
| d_region | 地區英數字元ID。 下載[地區清單](assets/Country_RegionCodes_City.csv)。  然後，您可以使用此清單來比對地區ID與地區名稱。 |
| d_isp | ISP/組織。 下載[ ISP清單](assets/d_isp.txt)。 |

[所有基於位置的信號](assets/all.txt)清單按以下順序包括上述所有信號：`d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)

