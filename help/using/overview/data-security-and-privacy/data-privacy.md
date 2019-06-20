---
description: 說明Audience Manager整合並遵循一般接受的消費者隱私權和退出程序最佳實務。
seo-description: 說明Audience Manager整合並遵循一般接受的消費者隱私權和退出程序最佳實務。
seo-title: 資料隱私權
solution: Audience Manager
title: 資料隱私權
uuid: 865e7b4e-visid1-4fa4-8035-1595fc77 cd96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# 資料隱私權{#data-privacy}

說明Audience Manager整合並遵循一般接受的消費者隱私權和退出程序最佳實務。

## 資料隱私權{#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

Audience Manager識別消費者與其互動線上品牌之間的隱含合約。雙方都受惠於匿名資料元素的透明交換：

* 消費者會收到個人化內容、折扣產品優惠，以及簡化的使用者體驗。
* 品牌可獲得支援多種線上商業模型的重要營收來源。

在我們持續支援此模型時，Audience Manager仍致力於為消費者提供透明度和控制權，以及會議或超越線上行為廣告(OBA)自律原則。

## Opt-Out Management {#opt-out-management}

選擇退出文件已延長，並將其移至文件的個別部分。See [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

<!-- 

<p>  </p>
<table id="table_A1FF33B328BD451FAFF6C6B8422F928B"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.74*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Opt-Out For </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
    <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../features/declared-ids.md#declared-id-targeting"> Declared ID Targeting</a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Mobile devices </p> </td> 
    <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
      <ul id="ul_86EFAB879215403D937B5148C26A41D9"> 
       <li id="li_C0B544E8F4FE473B94A5436D3A60BDB1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices</a> </li> 
       <li id="li_26C787BAB729499A9FEDF055E9AB0637"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices</a> </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

前往客戶網站的訪客 IP 位址會傳送至 Adobe Data Processing Center (DPC)，並可能儲存該 IP 位址。視訪客的網路組態而定，IP位址可能不一定代表訪客電腦的IP位址。例如，該 IP 位址可能是網路位址轉譯 (NAT) 防火牆、HTTP Proxy 或內部閘道的外部 IP 位址。

**IP模糊化方法：** 依照「隱私權依據設計」的原則，Adobe Audience Manager允許客戶從UI啓用IP模糊化，不論是全域地理區域或特定國家。啓用此設定時，當IP位址吸收到Audience Manager時，即會立即捨棄IP位址的最後八位元(最後一部分)。Audience Manager會在處理前廢止此IP位址的此部分(包括任何選用地理查閱或IP位址記錄)。例如:

* 在可以記錄: `255.255.255.255`
* 之後: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable IP address obfuscation in the Audience Manager UI.

**地域劃分：** 如果您啓用IP位址模糊化，則IP位址的其餘位元組仍可用於Audience Manager中的地理區隔和報告。如果您未啓用IP位址模糊化，Audience Manager會使用完整的IP位址。您可以使用地理劃分功能，讓您在任一種情況下識別某個IP位置，但在使用IP模糊化時卻稍微降低精確度。IP 位址模糊化可能會顯著影響城市層級資訊的取得。取得地區和國家層級資訊只會受到輕微影響。地域劃分資料的粒度僅限於城市層級或郵遞區號層級，而非個別層級。Read more about [geo-targeting](/help/using/features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## 相關概念 {#related-concepts}

* [退出管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [隱私權與資料保留常見問題](/help/using/faq/faq-privacy.md)