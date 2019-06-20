---
description: 本文說明建立特徵規則時，您必須附加至關鍵變數的首碼。
seo-description: 本文說明建立特徵規則時，您必須附加至關鍵變數的首碼。
seo-title: 關鍵變數的首碼需求
solution: Audience Manager
title: 關鍵變數的首碼需求
uuid: df2ef9c8-606a-45f9-a836-859f856 a7 b4 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Prefix Requirements for Key Variables {#prefix-requirements-for-key-variables}

本文說明建立特徵規則時，您必須附加至關鍵變數的首碼。

<!-- r_tb_variable_prefixes.xml -->

## 關鍵變數首碼的用途

When you create [!UICONTROL Trait Builder] rules, it is important to preface the key variable with a recommended prefix. These prefixes identify the type of data passed in and help avoid namespace conflicts within [!DNL Audience Manager]. 一般而言，您可以為變數提供變數，但如果關鍵變數名稱不符合事件呼叫中的變數名稱，則不會處理規則的資料。

## 關鍵變數的首碼

The following table defines the common prefixes used by [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 關鍵變數首碼 </th> 
   <th colname="col2" class="entry"> 識別變數 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>為客戶量身打造。這是從您自己的屬性傳送的關鍵資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 層級。This data is uniform across the <span class="keyword"> Audience Manager</span> ecosystem. See <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a> for a more complete list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>That contains <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP header</a> information. Includes header parameters such as <code> referer</code>,<code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Note: For customers using DIL versions older than 9.0, data collection using the <code> h_referer</code> signal will not work on Safari browsers. With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, Safari browsers may classify the demdex.net domain as a tracker and will truncate the referrer on the data collection request to only contain the origin instead of the full URL. See <a href="../../dil/dil-overview.md#get-implement-dil-code">Getting and Implementing DIL Code</a> for the latest DIL version.. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Our <span class="wintitle"> Data Collection Servers</span> allow passing of private parameters. Basically, any parameter that starts with <code> p_</code> will be used for trait evaluation, but it will not be logged downstream, nor stored. </p> <p>Example: given <code> /event?p_age=23</code> and a trait like <code> YoungPeople = p_age &lt; 25</code>, the trait will be realized, but the <code> p_age=23</code> key-value pair will be dropped after the request and will not be logged. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [基本資訊概述](../../features/traits/create-onboarded-rule-based-traits.md)
>* [管理特徵規則](../../features/traits/manage-trait-rules.md#managing-trait-rules)

