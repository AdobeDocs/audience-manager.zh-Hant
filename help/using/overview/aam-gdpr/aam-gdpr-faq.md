---
description: 本材料包含我們的客戶和合作夥伴與歐洲通用資料保護規則(GDPR)相關的一些最常見問題，以及Adobe Audience Manager如何解決各種GDPR需求。
seo-description: 本材料包含我們的客戶和合作夥伴與歐洲通用資料保護規則(GDPR)相關的一些最常見問題，以及Adobe Audience Manager如何解決各種GDPR需求。
seo-title: GDPR 常見問題集
solution: Audience Manager
title: GDPR 常見問題集
uuid: e52dc27-6a44-45ee-8524-6080adb86cc8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# GDPR 常見問題集{#gdpr-faq}

本材料包含我們的客戶和合作夥伴與歐洲通用資料保護規則(GDPR)相關的一些最常見問題，以及Adobe Audience Manager如何解決各種GDPR需求。

在本文中，我們將討論Audience Manager中有關GDPR準備的問題。Make sure you also read the [Experience Cloud GDPR FAQ.](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)

GDPR將於2018年月25日生效，主要目標是讓歐盟(資料主體)的個人(資料主體)更能掌控其個人資料，同時透過歐盟更統一的法規簡化跨國企業的法規環境。作為Adobe GDPR準備的一部分，Adobe Audience Manager團隊已視需要增強服務和程序，以支援從資料主體、消費者存取及刪除要求。

## GDPR Glossary {#gdpr-glossay}

熟悉與GDPR相關的重要詞彙。我們已強調下列最常用的詞語。

<br> 

**資料掌控者：** GDPR將「控制器」定義為「…法律人員…單獨或與其他人決定處理個人資料的目的和方式。」Audience Manager客戶是資料掌控者。客戶可控制在Audience Manager中管理資料的方式。

<br> 

**資料處理方：** 「處理器」是指代表控制器處理個人資料的「…法人…」。在Audience Manager的環境中(Adobe的資料管理平台或DMP)，Adobe會透過DMP對其處理和商店和服務的任何個人資料進行「資料處理方」。Adobe僅依據資料掌控者的許可和指示處理個人資料(例如我們與客戶簽訂的協議)。

<br> 

**資料主體：** 個人資料相關的個人。在Audience Manager的環境中，資料主體是Audience Manager客戶的消費者或使用者。如果Audience Manager直接從Data主體接收請求，這些請求將轉送給相應的Adobe客戶。

<br> 

**同意：** 同意意指「任何免費、具體、知情及明確的資料主體願望」，依聲明或明確肯定行動，表示同意處理與其相關之個人資料。同意是資料掌控者的責任，而非經由Audience Manager的Adobe。

<br> 

**存取：** 資料主體有權要求資料掌控者確認控制器是否處理其個人資料。若資料掌控者處理資料主體的個人資料，則必須提供個人資料的存取權和復本。資料掌控者可能會要求Adobe協助來自資料主體的存取要求。

<br> 

**刪除：** GDPR概述「被遺忘權利」或「權利的權利」。」資料主體有權要求資料掌控者擦除其個人資料。資料掌控者與其處理器(包括Adobe)合作，以支援資料主體的刪除要求。

<br> 

**更正：** 資料主體有權要求資料掌控者重新認證不準確的個人資料。資料掌控者與處理器(包括Adobe)合作，以支援資料主體的更正要求。

<br> 

**Audience Manager識別碼(ID)：** Adobe Audience Manager會儲存各種ID類型。The [GDPR in Audience Manager](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids) page provides a summary of these IDs, their corresponding data sources, and brief descriptions. 向Adobe提供請求時，請參考這些ID以刪除或存取資料主體的請求。

<br> 

**個人資料：** GDPR擴展了個人資料的定義。根據GDPR，Audience Manager中的任何資料都可以依據客戶使用案例分類為個人資料。

<br> 

**禁止的資料：** Audience Manager禁止客戶吸收直接識別資訊，例如名字和姓氏、電子郵件ID、CRM ID，可用來直接識別個人。Adobe Experience Cloud解決方案也禁止敏感資訊。如需這些需求的詳細資訊，請參閱您與Adobe的合約。如果需要吸收這些類型的資料點至Audience Manager，請洽詢您的Adobe諮詢團隊，取得在擷取這些ID之前的雜湊建議。

<br> 

## Managing Individual GDPR Rights {#manage-ind-gdpr-rights}

**管理選擇加入/取得許可**

GDPR在資料掌控者需要同意時不會變更，它會變更如何取得許可。在某些行銷活動需要徵求同意的情況下，消費者同意必須生效(例如未事先勾選的方塊或沈默)、未搭售及服務提供不受資料主體同意。有時可能需要重新整理某些需要重新整理的實例，才能繼續使用資料。

身為您的資料處理方，Adobe無法提供取得許可的法律建議。請洽詢您的法律團隊以尋求指導。We recommend that you work with a consent management solution providers such as [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) or [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) to provide better recommendations on this. Adobe已與數家供應商合作，協助透過Adobe Launch進行此項整合。

Audience Manager客戶可以將使用者同意，例如廣告或個人化等各種使用案例儲存在Audience Manager中。然後，建立具有這些特性的區段，則僅包含每個使用案例的使用者。請注意，使用此方法並不會停止資料收集，但只會影響您傳送區段進行啓動時的資料使用情形。When users withdraw their consent, you can remove these traits from user profile using the Audience Manager [inbound batch process](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) or Audience Manager opt-out process as detailed below.

<br> 

**管理退出/撤回許可**

Opt out can be managed for the Adobe Experience Cloud via the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page. 點按功能可讓您的使用者控制和選擇退出Adobe Experience Cloud廣告解決方案(包括Audience Manager)。Specifically, see the [business customer section](https://www.adobe.com/privacy/opt-out.html#customeruse) of the Privacy Choices page. For Browsers that do not support third-party cookies, see [Declared ID targeting](../../features/declared-ids.md#declared-id-targeting). For mobile devices, please retrieve the relevant Audience Manager identifiers and call the Audience Manager opt-out APIs as mentioned in the [Declared ID Opt-Out examples](../../features/declared-ids.md#opt-out-examples). Following that, you can cease all data collection for those users with the opt out APIs from Mobile SDK - see [Android devices](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) and [iOS devices](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html). You can find additional details for opt-out in the [Audience Manager Opt-Out Documentation](../../overview/data-security-and-privacy/opt-out-management.md).

<br> 

**提交Audience Manager GDPR存取及刪除請求至Adobe**

You can submit Individual GDPR requests for Access and Delete either through the [GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md) or by calling the [GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-id-onboarding.md). Any [Audience Manager identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids), can be submitted in the requests along with their respective namespace IDs (data source IDs). 如果您送出跨裝置識別碼(例如CRM ID)，Audience Manager將會對已驗證的描述檔以及連結到它的裝置ID採取動作。建議客戶盡可能使用Audience Manager獨特使用者ID(AAM UUID)。

<br> 

**管理存取要求**

在2018年月25日之前，Audience Manager會手動存取Audience Manager內唯一ID的特性、客戶ID和區段。自2018年月25日起，我們以上述各種產品和服務增強方式支援這些要求。除了特徵、客戶ID、存取要求的回應外，存取請求還包括特徵和區段總數的摘要、特徵類型、特徵和區段的說明以及各自的資料來源名稱。存取回應也包括資料掌控者可存取的第二方和第三方資料以及第一方資料。See more in [Data Access Requests](../../overview/aam-gdpr/aam-gdpr-details.md#access-data).

<br> 

**管理刪除要求**

2018年月25日之前，Audience Manager支援手動刪除特徵、客戶ID和與Audience Manager內唯一ID關聯的區段。GDPR生效後，我們將依照上述各種產品和服務增強功能來支援這些要求。除了刪除作業外，資料主體的個別Audience Manager識別碼也會選擇退出，並移除個別的ID對應。See more in [Data Deletion Requests](../../overview/aam-gdpr/aam-gdpr-details.md#delete-data).

<br> 

**第二方資料供應商與管理許可**

第二方資料供應商通常也是資料掌控者，並擁有從資料主體取得與其第二方資料合作夥伴共用資料所需的任何許可。Audience Manager客戶有責任判斷第二方資料供應商是否已獲得您使用案例的必要許可。有關取得許可的詳細資訊，請參閱上文。

<br> 

**第三方資料供應商與管理許可**

資料供應商也是資料掌控者，擁有取得同意及管理存取/刪除/更正要求的程序。Adobe is proactively requesting that Data Providers update their company profile information within [Adobe Audience Finder](https://www.adobe-audience-finder.com/) with additional information on user data collection. 資料將由資料供應商提供，其目標是在2018年季度之前更新此工具。不過，每位Audience Manager客戶決定第三方資料供應商已獲得該客戶使用案例的必要許可。Adobe不對第三方資料供應商針對特定使用案例所取得或報告之同意範圍或有效性提出聲明。

<br> 

**刪除請求對觀眾啓動的影響**

Audience Manager會傳送取消要求給啓動合作夥伴，將要求刪除某些資料的資料主體取消區段資訊。不過，有些啓動合作夥伴：1)無法支援Adobe及/或2)無法從我們接收的更新頻率小於30天。在這種情況下，Audience Manager客戶無法透過Audience Manager自動傳送刪除要求給啓動合作夥伴。[「GDPR合作夥伴取消區段」文件](../../overview/aam-gdpr/aam-gdpr-partners.md) 提供所有啓動合作夥伴的資料交換功能與頻率的相關資訊。

<br> 

**Audience Manager中的資料保留**

對資料套用適當、安全且及時的資料保留政策是遵守GDPR的重要部分。Audience Manager客戶可定義必要的TTL(存留時間)，以設定特徵和區段上的自訂保留期。We have reduced the retention period for [!UICONTROL Customer Data Feeds] ( [!UICONTROL CDF]) and [!UICONTROL Batch Outbound] orders to 8 days. 我們也將針對非活動中CRM描述檔和ID對應套用保留期。Please find the more details about retention periods in our [Data Retention FAQ](../../faq/faq-privacy.md).

<br> 

**管理資料更正請求**

由於Audience Manager不是資料來源，Audience Manager中的資料修正角色有限。更正可能表示資料主體要求不合格的特徵/區段或符合所需特徵/區段的資格。Audience Manager客戶可選擇針對使用者描述檔擷取相關訊號/特徵/區段，並透過離線資料擷取將此資訊傳送至Audience Manager。請注意，使用者若重復其行為，將繼續獲得原始特徵和區段的資格。

<br> 

**跨境資料傳輸**

GDPR禁止歐洲以外地區傳輸資料。在傳輸資料時，歐洲資料的隱私保護會持續存在。Visit the [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) to learn more.

<br> 

## GDPR Readiness Guidance for Audience Manager Customers (Data Controllers) {#gdpr-readiness-guidance}

我們建議在資料治理和組織準備就緒方面積極主動。如此可確保您的消費者資料針對存取或刪除要求的相關程序進行組織，您的團隊將啓用並有能力管理這些要求，而您的消費者(資料主體)將擁有正面、與眾不同的品牌體驗。

請注意，作為您的資料處理方，Adobe無法針對GDPR要求以及從您的資料主體取得同意的程序提供法律建議。請諮詢您的法律顧問，以取得貴組織遵循GDPR的指引。

<br> 

**資料治理：開始思考如何在Audience Manager實例中管理消費者資料**

* 檢閱行銷團隊用於識別Audience Manager中使用者的各種客戶ID，以及儲存它們的資料來源。這將簡化請求的處理程序(例如刪除或存取)，因為在Audience Manager擷取之前，某些資料類型會被您的團隊雜湊處理。
* AIDFA/GAID行動裝置ID用於Audience Manager中的多個使用案例。如果您使用Adobe Mobile SDK，請務必送出Experience Cloud ID(MID)以及IDFA/GAID以確保GDPR回應已完成。
* 隨著個人資料的定義變得更豐富，IP位址可能會被視為您所在地區的個人資料。主動與Adobe Consulting互動，使最後八位數字模糊化。
* 確定驗證/驗證政策與程序，用於確認資料主體進行GDPR請求時的身分。
* Consider using [Data Export Controls](../../features/data-export-controls.md) to block audience activation to technologies that house personal data. 例如，含有第三方資料的區段不應匯集至電子郵件服務供應商。Set a [!UICONTROL Data Export Control] to ensure that no one in your organization can accidentally activate this data.
* Begin utilizing [Role Based Access Controls](../../features/administration/administration-overview.md) to ensure the right teams have access to intended data.
* Consider appropriate [retention periods](../../faq/faq-privacy.md#data-retention-faq) for the data.
* Review identity linkage and privacy policies and legal requirements to see when and where it is appropriate to tie identity sets together; use appropriately via Audience Manager’s [Profile Merge Rules](../../features/profile-merge-rules/merge-rules-overview.md).

<br> 

**組織準備就緒：建立商業程序**

* 識別接收/回應資料主體要求的程序。考慮建立自動化工具，提交要求至Audience Manager。
* 在您的DMP卓越中心任命隱私權聯絡人。連接組織的隱私權聯絡人與Audience Manager產品使用團隊的聯繫，以瞭解如何管理輸入ID需求。
* 在與資料主體分享之前，先進行資料審查。記錄您制定的步驟，以協助您建立問責。

