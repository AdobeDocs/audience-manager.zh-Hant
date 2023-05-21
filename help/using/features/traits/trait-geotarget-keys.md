---
description: 描述可用於針對具有跨Audience Manager帳戶中所有屬性的地理變數的用戶的通用平台級鍵值對。
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: 使用平台層級的索引鍵進行地理定位
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 366589d51601f438999bfdc6a10c306eb1186742
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 3%

---

# 使用平台層級的索引鍵進行地理定位 {#geotargeting-with-platform-level-keys}

描述可用於針對具有跨Audience Manager帳戶中所有屬性的地理變數的用戶的通用平台級鍵值對。

<!-- c_tb_platform_vars.xml -->

## 平台級變數的用途 {#platform-variables}

平台級變數允許您從特定站點傳入資料，並使其可用於在所有屬性中定位 [!DNL Audience Manager] 帳戶。 這些變數由 [鍵值對](../../reference/key-value-pairs-explained.md) 鍵前置詞為 `d_` 如下所示。

## 向平台級鍵添加值 {#adding-values}

對於某些平台級鍵，您可以自行指定值。 與其他密鑰相關聯 [!DNL IP] 在事件調用中傳入的地址。 在這兩種情況下，在中生成特徵時仍需要指定值 [!UICONTROL Trait Builder]。

## 用戶定義的平台級密鑰 {#user-defined-keys}

如果您已經或正在建立定義和收集鍵值對的流程，則使用此選項。 如果要使用IP地址預定義的密鑰，請繼續下一節。 在用戶定義鍵的情況下，使用以下鍵值對生成特徵時，可指定值：

| 金鑰 | 針對目標 |
|---|---|
| `d_zx` | 郵遞區號(例如， `d_zx=10022`)。 |

## 由IP地址定義的平台級密鑰 {#keys-ip-address}

我們合作 [數字特使](https://www.digitalenvoy.com/) 獲取和更新以下鍵的人口和地理資料。 這些鍵的值由匹配 [!DNL IP] 地理和人口資料。 但是，在中建立key-value對時，仍必須輸入value參數 [!UICONTROL Trait Builder]。

| 金鑰 | 針對目標 |
|--- |--- |
| d_area_code | [北美地區代碼](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)。  例如： <ul><li>**性狀**:d_area_code=801</li><li>**特性名稱**:猶他州</li></ul> |
| d_city | 城鎮。 下載 [城市清單](assets/d_city.txt)。  例如： <ul><li>特徵：d_city=波恩</li><li>特性名稱：波恩</li></ul> **提示**:您可以使用 `d_city` 耦合 `d_country` 以確保你的目標不是兩個名字相同的城市。 通過使用 `d_postal_code`。 |
| d_國家 | 值對應於ISO國家/地區代碼。 有關代碼的可搜索清單，請參閱 [ISO線上瀏覽平台](https://www.iso.org/obp/ui/#home)。 <br>  針對聯合王國是唯一不遵守ISO 3166的特例。 在英國，應使用&quot;UK&quot;而不是&quot;GB&quot;進行目標定位。  為了針對荷屬安地列斯群島，自2010年以來已棄用代碼&quot;AN&quot;。 該地區已分為五個獨立的領土單位。 這意味著，在荷屬安地列斯群島，不應使用&quot;AN&quot;，而應使用&quot;CW&quot;、&quot;SX&quot;和&quot;BQ&quot;的國家代碼的組合。  例如：  <br>  特徵：d_country=CZ  <br>  特性名稱：捷克 <br>  特徵：d_country=UK <br>  特性名稱：英國  <br>  特徵：d_country=CW或d_country=SX或d_country=BQ  <br>  特性名稱：荷屬安地列斯群島 |
| d_dma_code | 城域DMA代碼。 下載 [DMA區域清單](assets/DMAregions.csv) 格式。  例如： <ul><li>特徵：d_dma_code=807</li><li>特性名稱：舊金山</li></ul> |
| d_lat | Latitude（例如d_lat=40.75）。 下載 [緯度清單](assets/d_lat.txt)。 |
| d_long | 經度（例如d_long=73.98）。 下載 [縱向清單](assets/d_long.txt)。 |
| d_postal_code | 郵遞區號（不包括擴展+4代碼）。 下載  [郵遞區號清單](assets/d_postal_code.txt)。  例如： <ul><li>特徵：d_postal_code=84004 </li><li>特性名稱：阿爾卑斯</li></ul> |
| d_狀態 | 美國州的2個字元縮寫。 下載 [狀態代碼清單](assets/d_state.txt)。  例如： <ul><li>特徵：d_state=NY </li><li>特性名稱：紐約</li></ul>d_state包含不同國家/地區的不同狀態的重複值。 例如，d_state == &quot;on&quot;匹配多個狀態：安大略省（加拿大）、翁多（奈及利亞）、奧沙納（納米比亞）。 我們建議將此信號與d_country等其它信號相結合，以便更具體地理目標。 |
| d_區域 | 區域字母數字ID 下載 [區域清單](assets/Country_RegionCodes_City.csv)。  然後，您可以使用此清單將區域ID與區域名稱匹配。 |
| d_isp | ISP/組織。 下載 [ISP清單](assets/d_isp.txt)。 |

清單 [所有基於位置的信號](assets/all.txt) 按以下順序排列： `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)

