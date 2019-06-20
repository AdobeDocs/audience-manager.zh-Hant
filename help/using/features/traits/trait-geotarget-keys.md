---
description: 說明通用平台層級金鑰-值配對，您可以用此配對來定位使用者管理員帳戶中所有屬性的地理變數。
seo-description: 說明通用平台層級金鑰-值配對，您可以用此配對來定位使用者管理員帳戶中所有屬性的地理變數。
seo-title: 使用平台層級索引鍵進行地理定位
solution: Audience Manager
title: 使用平台層級索引鍵進行地理定位
uuid: c7e4cffe-e564-404e-a565-be5 fb2 fb519
translation-type: tm+mt
source-git-commit: c5c57423bcba8d4b3974a04c46dc7c7afc7484a0

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

說明通用平台層級金鑰-值配對，您可以用此配對來定位使用者管理員帳戶中所有屬性的地理變數。

<!-- c_tb_platform_vars.xml -->

## Purpose of Platform-level Variables {#platform-variables}

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Adding Values to Platform Level Keys {#adding-values}

對於部分平台層級的索引鍵，您可以自行指定值。With others, the keys are associated with corresponding [!DNL IP] addresses passed in on an event call. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## User Defined Platform-Level Keys {#user-defined-keys}

您可以在使用這些索引鍵值配對建立特徵時指定值：

| 金鑰 | 用於定位 |
|---|---|
| `d_zx` | ZIP code (e.g., `d_zx=10022`). |

## Platform Level Keys Defined by IP Address {#keys-ip-address}

We work with [Digital Envoy](https://www.digitalenvoy.com/) to obtain and update the demographic and geographic data for the keys below. The values for these keys are determined by matching [!DNL IP] addresses to corresponding geographic and demographic data. However, you&#39;ll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

| 金鑰 | 用於定位 |
|--- |--- |
| d_ registration_ code | [北美洲地區代碼](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)。例如: <ul><li>**特徵**：d_ action_ code=801</li><li>**特徵名稱**：猶他</li></ul> |
| d_ city | 城市和城鎮。Download the [cities list](assets/d_city.txt).  例如: <ul><li>特徵：d_ city= bon</li><li>特徵名稱：Bonn</li></ul> **秘訣**：您可以搭配使用 `d_city``d_country` ，確定您不定位兩個不同國家/地區同名的城市。You can be even more specific in your targeting by using `d_postal_code`. |
| d_ country | 值對應於ISO國家代碼。For a searchable list of codes, see the [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>針對英國的定位是唯一不遵守ISO3166的特殊案例。在英國，您應使用「英國」而非「GB」做為目標。為了鎖定荷屬安地列斯群島，自2010年以來，已淘汰「AN」程式碼。該區域已分為五個領土單位。The impliation is that for targeting in the herland Antillies，you should not use「AN」，but instruct of the country code for「CW」，「SX」and「BQ.」For example:  <br>  Trait:  d_country=CZ  <br>  Trait Name: Czech Republic <br>  Trait:  d_country=UK <br>  Trait Name: United Kingdom  <br>  Trait:  d_country=CW OR d_country=SX OR d_country=BQ  <br>  Trait Name: Netherlands Antilles |
| d_ dma_ code | Metropolitan區域DMA代碼。Download the [DMA region list](assets/DMAregions.csv) (.csv format).  例如: <ul><li>特徵：d_ dma_ code=807</li><li>特徵名稱：舊金山</li></ul> |
| d_ lat | 緯度(例如d_ lat=40.75)。Download the [latitudes list](assets/d_lat.txt). |
| d_ long | 發行者(例如d_ long=73.98)。Download the [longitudes list](assets/d_long.txt). |
| d_ public_ code | 郵遞區號(排除延長的+代碼)。Download the  [postal codes list](assets/d_postal_code.txt).  例如: <ul><li>特徵：d_ publish_ code=84004 </li><li>特徵名稱：Alpine</li></ul> |
| d_ state | 個字元縮寫。Download the [states codes list](assets/d_state.txt).  例如: <ul><li>特徵：d_ state= NY </li><li>特徵名稱：紐約</li></ul>d_ state包含不同國家/地區的重復值。例如，d_ state==「on」符合多個狀態：安大略省(位於加拿大)、安大略省、納米比亞(納米比亞)。我們建議將這個訊號與d_ country等其他人配對，以獲得更具體的地理定位。 |
| d_ region | 區域英數ID。Download the [region list](assets/Country_RegionCodes_City.csv).  然後，您可以使用此清單將地區ID比對至地區名稱。 |
| d_ sp | ISP/組織。Download the [ISP List](assets/d_isp.txt). |

[所有基於位置的訊號](assets/all.csv) 清單包含上述所有訊號，順序如下： `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_贊_ this]
>
>* [關鍵變數的首碼需求](../../features/traits/trait-variable-prefixes.md)

