---
description: 本材料包含客戶和合作夥伴提出的與歐洲通用資料保護規則(GDPR)相關的一些最常見問題，以及Adobe Audience manager作為資料處理者如何解決各種GDPR要求。
seo-description: 本材料包含客戶和合作夥伴提出的與歐洲通用資料保護規則(GDPR)相關的一些最常見問題，以及Adobe Audience manager作為資料處理者如何解決各種GDPR要求。
seo-title: GDPR 常見問題集
solution: Audience Manager
title: GDPR 常見問題集
uuid: e52cad27-6a44-45ee-8524-6080adb86cc8
translation-type: tm+mt
source-git-commit: 98914987331ce31bc8d3e67647d5b8273b287d4c

---


# GDPR 常見問題集{#gdpr-faq}

本材料包含客戶和合作夥伴提出的與歐洲通用資料保護規則(GDPR)相關的一些最常見問題，以及Adobe Audience manager作為資料處理者如何解決各種GDPR要求。

在本文中，我們針對Audience manager中有關GDPR準備性的問題。 請確定您也閱讀 [Experience Cloud GDPR常見問答集。](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)

GDPR於2018年5月25日生效，其主要目標是讓歐盟（資料主體）的個人擁有對個人資料的更多控制權，同時透過更完善的歐盟內部統一法規簡化國際企業的法規環境。 Adobe Audience manager團隊已視需要增強服務和流程，以支援您的消費者資料主體的存取和刪除要求，這是Adobe GDPR整備的一部分。

## GDPR辭彙表 {#gdpr-glossay}

熟悉與GDPR相關的關鍵術語。 我們強調了下列最常用的術語。

<br> 

**** 資料控制器：GDPR將「掌控者」定義為「...法人……這是個人或與其他人共同決定處理個人資料的目的和手段的。」Audience manager客戶是資料掌控者。 客戶可控制在Audience manager中管理資料的方式。

<br> 

**** 資料處理器：「處理者」是「...法人。.代表控制者處理個人資料」。 在Audience Manager（Adobe的資料管理平台或DMP）中，Adobe會以「資料處理者」的身分處理透過DMP處理、儲存及服務的任何個人資料。 Adobe僅會根據資料掌控者的許可和指示（例如，如我們與客戶的合約所載）處理個人資料。

<br> 

**** 資料主體：個人資料相關的個人。 在Audience Manager中，資料主體是Audience manager客戶的消費者或使用者。 如果Audience manager直接從資料主體收到請求，這些請求將轉送至個別的Adobe客戶。

<br> 

**** 同意：「同意」系指「他／她以聲明或明確肯定行動自由表示、具體、知情且明確表示資料主體意願的任何指示，表示同意處理與他／她有關的個人資料」。 同意是資料掌控者的責任，而非透過Audience manager的Adobe。

<br> 

**** 存取：資料主體有權要求資料掌控者確認掌控者是否處理其個人資料。 當資料掌控者確實處理資料主體的個人資料時，必須提供個人資料的存取權及副本。 資料掌控者可要求Adobe協助處理資料主體的存取要求。

<br> 

**** 刪除：GDPR概述「被遺忘權」或「擦除權」。資料主體有權要求資料掌控者清除其個人資料。 資料掌控者可與其處理者（包括Adobe）合作，以支援從資料主體刪除要求。

<br> 

**** 更正：資料主體有權要求資料掌控者修正不準確的個人資料。 資料掌控者可與處理者（包括Adobe）合作，以支援資料主體的更正要求。

<br> 

**** Audience manager識別碼(ID):Adobe Audience manager會儲存各種類型的ID。 Audience Manager [（觀眾管理員）頁面中的](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids) GDPR提供這些ID的摘要、其對應的資料來源，以及簡要說明。 向Adobe提供請求時，請參考這些ID，以針對您的資料主體提出刪除或存取請求。

<br> 

**** 個人資料：GDPR擴展了個人資料的定義。 在GDPR之下，Audience manager中的任何資料都可依客戶使用案例分類為個人資料。

<br> 

**** 禁止的資料：Audience manager禁止客戶吸收可直接識別身分的資訊，例如名字和姓氏、電子郵件ID、CRM ID，這些資訊可用來直接識別個人。 Adobe Experience cloud解決方案也禁止敏感資訊。 如需這些要求的詳細資訊，請參閱您與Adobe的合約。 如果需要將這些類型的資料點納入Audience Manager中，請洽詢您的Adobe諮詢團隊，以取得在擷取前散列這些ID的建議。

<br> 

## 管理個人GDPR權利 {#manage-ind-gdpr-rights}

**管理選擇加入／取得同意**

當資料掌控者需要同意時，GDPR不會改變，它會改變取得同意的方式。 在某些行銷活動需要同意的情況下，消費者同意必須有效（例如，沒有預先勾選的方塊或預設）、未打包及提供服務不得以「資料主體」給予同意為條件。 有時甚至需要重新整理某些同意，才能繼續使用後續的資料。

身為資料處理者，Adobe無法就取得同意提供法律建議。 請洽詢您的法律團隊以取得指導。 我們建議您與同意管理解決方案供應商(例如 [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 或 [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) )合作，以就此提供更佳建議。 Adobe已與數家此類供應商合作，透過Adobe Launch協助此項整合。

Audience manager客戶可將廣告或個人化等不同使用案例的使用者同意儲存為Audience Manager中的特徵。 然後，建立具有這些特徵的區段時，將只包含針對每個使用案例提供個別同意的使用者。 請注意，使用此方法不會停止資料收集，但只會在您傳送要啟動的區段時影響資料的使用。 當使用者撤回其同意時，您可以使用傳入的Audience Manager批次程式或Audience manager選擇退出程式，從使用者個人檔案中移除這些特徵 [](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) ，如下所述。

<br> 

**管理退出／撤回同意**

您可透過「您的隱私權選擇」頁面，管理Adobe Experience cloud的 [退出選項](https://www.adobe.com/privacy/opt-out.html#customeruse) 。 單鍵功能可讓您的使用者控制Adobe Experience cloud廣告解決方案（包括Audience Manager）收集的資料，並選擇退出。 具體而言，請參 [閱「隱私權選擇](https://www.adobe.com/privacy/opt-out.html#customeruse) 」頁面的「企業客戶」一節。 若為不支援協力廠商Cookie的瀏覽器，請參閱「宣告 [的ID定位」](../../features/declared-ids.md#declared-id-targeting)。 若為行動裝置，請擷取相關的Audience manager識別碼，並呼叫Audience Manager退出API，如「宣告的ID退出」 [範例所述](../../features/declared-ids.md#opt-out-examples)。 之後，您就可以使用Mobile SDK的退出API停止這些使用者的所有資料收集——請參閱 [Android裝置](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html)[和iOS裝置](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)。 您可以在 [Audience Manager選擇退出檔案中找到選擇退出的其他詳細資訊](../../overview/data-security-and-privacy/opt-out-management.md)。

<br> 

**將Audience Manager GDPR存取權和刪除請求提交至Adobe**

您可以透過 [GDPR客戶端服務UI](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) ，或呼叫 [GDPR API，提交個別的GDPR存取和刪除請求](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-id-onboarding.md)。 任何 [Audience manager識別碼](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)，都可在請求中提交，以及其各自的命名空間ID（資料來源ID）。 如果您提交跨裝置識別碼（例如CRM ID）,Audience manager將對已驗證的個人檔案以及連結至該個人檔案的裝置ID採取動作。 建議客戶盡可能使用Audience Manager唯一使用者ID(AAM UUID)。

<br> 

**管理存取請求**

在2018年5月25日之前，Audience manager支援手動存取Audience manager中與唯一ID相關的特徵、客戶ID和區段。 截至2018年5月25日，我們以上述方式支援這些要求，並增強了各種產品和服務。 除了特徵、客戶ID、區段外，對「存取」要求的回應還包含特徵和區段總數、特徵類型、特徵和區段的說明，以及個別資料來源名稱的摘要。 訪問響應還包括可由資料控制器訪問的第二方和第三方資料以及第一方資料。 請參閱資料存 [取要求中的更多資訊](../../overview/aam-gdpr/aam-gdpr-details.md#access-data)。

<br> 

**管理刪除請求**

在2018年5月25日之前，Audience manager支援手動刪除Audience manager中與唯一ID相關的特徵、客戶ID和區段。 GDPR生效後，我們以上述方式支援這些要求，並增強了各種產品與服務。 除了刪除操作外，「資料主體」的個別Audience manager識別碼將被選擇不再進行進一步的資料收集，而且會移除個別的ID對應。 請參閱資料刪 [除請求中的更多資訊](../../overview/aam-gdpr/aam-gdpr-details.md#delete-data)。

<br> 

**第二方資料提供者與管理同意**

第二方資料提供者通常也是資料掌控者，並擁有從資料主體取得任何必要同意的程式，以便與其第二方資料合作夥伴共用資料。 Audience Manager客戶有責任判斷第二方資料提供者是否已取得您使用案例的必要同意。 有關取得同意的詳細資訊，請參閱上文。

<br> 

**第三方資料提供者與管理同意**

資料提供者也是資料掌控者，擁有取得同意及管理存取／刪除／更正要求的程式。 Adobe主動要求資料提供者在 [](https://www.adobe-audience-finder.com/) Adobe Audience Finder中更新其公司個人檔案資訊，並提供使用者資料收集的其他資訊。 資訊將來自資料提供者，其目標是在2018年第2季前更新工具。 但是，由每位Audience manager客戶決定第三方資料提供者已取得該客戶使用案例的必要同意。 Adobe不就第三方資料供應商針對特定使用案例所取得或報告之同意之範圍或效力提出任何陳述。

<br> 

**刪除觀眾啟動要求的影響**

Audience manager會傳送資料主體的取消區段資訊，要求刪除特定資料，以通知啟動合作夥伴有關刪除要求。 不過，有些啟動合作夥伴：1)無法支援Adobe的取消區隔（或移除區隔）要求，及／或2)無法接收我們以少於30天的頻率提供的更新。 在這些情況下，Audience Manager客戶無法透過Audience Manager以自動方式傳送刪除要求給啟動合作夥伴。 GDPR合作 [夥伴取消細分檔案](../../overview/aam-gdpr/aam-gdpr-partners.md) ，提供所有啟動合作夥伴取消細分功能和資料交換頻率的相關資訊。

<br> 

**Audience manager中的資料保留**

將適當、安全且及時的資料保留原則套用至您的資料，是遵守GDPR的重要一環。 Audience Manager客戶可定義所需的TTL（存留時間），以設定特徵和區段的自訂保留期。 我們已將()和訂 [!UICONTROL Customer Data Feeds] 單的 [!UICONTROL CDF]保留 [!UICONTROL Batch Outbound] 期縮短至8天。 我們也將針對非作用中的CRM設定檔和ID映射套用保留期。 請在我們的資料保留常見問答集中，找到有關保留期 [間的詳細資訊](../../faq/faq-privacy.md)。

<br> 

**管理資料更正請求**

鑑於Audience manager不是資料來源，Audience manager中資料修正的角色有限。 修正可能表示「資料主體」已要求取消其資格，使其不符合不正確的特徵／區段，或符合所需的特徵／區段。 Audience Manager客戶可選擇針對使用者個人檔案擷取相關訊號／特徵／區段，並透過離線資料擷取傳送此資訊至Audience Manager。 請注意，如果使用者重複其行為，將會繼續符合原始特徵和區段的資格。

<br> 

**跨邊界資料傳輸**

GDPR並不禁止在歐洲以外傳輸資料。 它要求對歐洲資料的隱私保護在資料傳輸時始終有效。 請造訪 [Adobe隱私權中心](https://www.adobe.com/privacy/eudatatransfers.html) ，瞭解更多資訊。

<br> 

## Audience manager客戶（資料掌控者）的GDPR準備指引 {#gdpr-readiness-guidance}

我們建議在資料治理和組織就緒性方面採取主動行動。 這可確保您的消費者資料會針對存取或刪除要求的相關程式進行組織，您的團隊將可以管理這些要求，而您的消費者（資料主體）將擁有與您品牌相異的正面體驗。

請注意，身為您的資料處理者，Adobe無法就GDPR要求及取得資料主體同意的程式提供法律建議。 請洽詢您的法律顧問，以取得貴組織遵守GDPR的指引。

<br> 

**資料治理：開始思考如何在Audience manager例項中管理您的消費者資料**

* 檢閱行銷團隊用來識別Audience manager中使用者的各種客戶ID，以及其儲存資料來源。 這將簡化請求的處理（例如刪除或存取），因為您的團隊在Audience manager中擷取某些資料類型之前，會先雜湊某些資料類型。
* IDFA/GAID行動裝置ID用於Audience manager的多個使用案例。 如果您使用Adobe Mobile SDK，請務必提交Experience Cloud ID(MID)以及IDFA/GAID，以確保GDPR回應完整。
* 隨著個人資料的定義越來越廣泛，IP位址可能會被視為您所在地區的個人資料。 主動與Adobe Consulting合作，模糊最後八位元。
* 確定在資料主體提出GDPR請求時確認其身分的驗證／驗證策略和流程。
* 請考慮使 [用「資料匯出控制](../../features/data-export-controls.md) 」來封鎖對儲存個人資料之技術的受眾啟動。 例如，具有第三方資料的區段不應匯集至電子郵件服務供應商。 設定以 [!UICONTROL Data Export Control] 確保組織中沒有人會意外啟用此資料。
* 開始使用 [基於角色的訪問控制](../../features/administration/administration-overview.md) ，以確保適當的團隊能夠訪問預定的資料。
* 請考慮適 [合資料的](../../faq/faq-privacy.md#data-retention-faq) 「保留期」。
* 審查身分連結、隱私權政策和法律要求，以瞭解何時何地將身分組系結在一起；透過Audience Manager的設定檔合併規 [則適當使用](../../features/profile-merge-rules/merge-rules-overview.md)。

<br> 

**組織就緒性：建立業務流程**

* 識別接收／回應資料主體要求的程式。 考慮建立自動化工具，將請求提交至Audience Manager。
* 在您的DMP卓越中心指定隱私權聯絡點。 將貴組織的隱私權聯絡點與您的Audience manager產品使用團隊連絡，以瞭解如何管理輸入ID需求。
* 在與資料主體共用之前先進行資料審查。 記錄您所採取的步驟，協助您建立責任。

