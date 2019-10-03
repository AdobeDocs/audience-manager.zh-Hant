---
description: 說明Audience manager整合及符合與消費者隱私權和退出程式相關的公認最佳實務。
seo-description: 說明Audience manager整合及符合與消費者隱私權和退出程式相關的公認最佳實務。
seo-title: 資料隱私權
solution: Audience Manager
title: 資料隱私權
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# 資料隱私權{#data-privacy}

說明Audience manager整合及符合與消費者隱私權和退出程式相關的公認最佳實務。

## 資料隱私權{#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

Audience Manager recognizes the implicit pact between consumers and the online brands with which they interact. Both parties benefit from the transparent exchange of anonymous data elements:

* Consumers receive personalized content, discounted product offers, and streamlined user experiences.
* 品牌可獲得重要的營收來源，以支援多種線上商業模型。

在我們持續支援此模式時，Audience manager仍致力於為消費者提供透明度和控制，並符合或超越線上行為廣告(OBA)自律原則。

## 退出管理 {#opt-out-management}

退出說明檔案已延長，並移至我們說明檔案的另一部份。 請參 [閱退出管理](../../overview/data-security-and-privacy/opt-out-management.md)。

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

## 收集IP位址和IP位址模糊化 {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** IP模糊化方法：Adobe Audience manager遵循「依設計隱私權」的原則，允許客戶在UI中啟用模糊化，不論是全球各地區或特定國家／地區 [!DNL IP] 。 當您啟用此設定時，當將位址收錄到Audience manager中時，會立即捨棄 [!DNL IP] 該位址的最後八位 [!DNL IP] 元（最後一部分）。 Audience manager會在處理前(包括任何選用的地理查閱或 [!DNL IP] 記錄位址之前)放棄此部分 [!DNL IP] 位址。 例如:

* 在可以記錄: `255.255.255.255`
* 之後: `255.255.255.0`

>[!NOTE]
>
>請參 [閱IP位址模糊化](/help/using/features/administration/ip-obfuscation.md) ，以瞭解如何在Audience Manager UI [!DNL IP] 中啟用位址模糊化。

觀看以下影片，瞭解位址模糊 [!DNL IP] 化在Audience manager中的運作方式。

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=chi_hant)

**** 地域劃分：如果您啟 [!DNL IP] 用位址模糊化，位址的其餘八位元仍 [!DNL IP] 可用於Audience manager中的地域劃分和報告。 如果您未啟用位 [!DNL IP] 址模糊化，Audience manager會使用完整位 [!DNL IP] 址。 您可以使用「地理區段」功能，在任何情況下都可 [!DNL IP] 以依地理區域識別位置，但在使用模糊化時會略 [!DNL IP] 有降低精確度。 Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. 取得地區和國家一級的資訊只會受到輕微影響。 「地理區段」資料的粒度僅限城市層級或郵遞區號層級，而非個別層級。 進一步瞭解 [地理定位](/help/using/features/traits/trait-geotarget-keys.md) ，以及如何使用地理變數設定特徵。

## 相關概念 {#related-concepts}

* [退出管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [隱私權與資料保留常見問題](/help/using/faq/faq-privacy.md)