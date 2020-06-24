---
title: GDPR 및 CCPA에 대한 Intune 데이터 주체 요청
description: 개인 데이터를 찾아서 조치를 취하고, Microsoft Intune 사용 고객의 DSR 및 CCPA 요청에 응답하는 방법을 알아보세요.
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.custom:
- seo-marvel-mar2020
hideEdit: true
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a9dd161edd740aa97e97afa02a6c53933a6ac211
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817657"
---
# <a name="intune-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 및 CCPA에 대한 Intune 데이터 주체 요청

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR.

마찬가지로 캘리포니아 소비자 개인 정보 보호법(CCPA)은 캘리포니아 소비자에게 GDPR의 데이터 주체 권리와 유사한 권리를 포함하여, 소비자의 개인 정보 삭제, 액세스 및 수신(이식성)과 같은 개인 정보 보호 권리 및 의무를 제공합니다.  또한 CCPA는 특정 공개, 실행 권리 행사 시 차별 대우로부터 보호, “판매"로 분류되는 특정 데이터 전송에 대한 "옵트아웃(opt-out)/옵트인(opt-in)" 요구도 허용합니다. 판매는 가치 있는 대가관계를 위하여 데이터 공유를 포함하도록 광범위하게 정의됩니다. CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](offering-ccpa.md) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](ccpa-faq.md)를 참조하세요.

이 가이드에서는 Microsoft 제품, 서비스 및 관리 도구를 사용하여 통제자 고객이 개인 데이터를 찾아 조치를 취함으로써 DSR에 대처하는 데 도움을 주는 방법을 설명합니다. 특히 여기에는 Microsoft 클라우드에 있는 개인 데이터 또는 개인 정보를 찾고, 액세스하고, 조치를 취하는 방법이 포함됩니다. 이 가이드에 설명된 프로세스에 대한 간략한 개요는 다음과 같습니다.

- **검색:** 검색 및 검색 도구를 사용하여 DSR의 대상이 될 수 있는 고객 데이터를 더 쉽게 찾을 수 있습니다. 잠재적으로 반응형 문서가 수집되면 다음 단계에 설명된 DSR 작업을 수행하여 요청에 응답할 수 있습니다. 또는 요청이 DSR에 응답하기 위한 조직의 지침을 충족하지 않는다고 판단할 수 있습니다.
- **액세스:** Microsoft 클라우드에 있는 개인 데이터를 검색하고, 요청될 경우 데이터 주체가 사용할 수 있는 복사본을 만듭니다.
- **수정:** 해당되는 경우 개인 데이터를 변경하거나 요청된 다른 작업을 구현합니다.
- **제한** 다양한 Azure 서비스에 대한 라이선스를 제거하거나 가능한 경우 원하는 서비스를 꺼서 개인 데이터의 처리를 제한합니다. Microsoft 클라우드에서 데이터를 제거하고 온-프레미스 또는 다른 위치에 보존할 수도 있습니다.
- **삭제:** Microsoft 클라우드에 있는 개인 데이터를 영구적으로 제거합니다.
- **내보내기/수신(이식성):** 개인 데이터 또는 개인 정보의 전자 사본(컴퓨터가 읽을 수 있는 형식)을 데이터 주체에게 제공합니다. CCPA 하에서 개인 정보는 식별된 또는 식별 가능한 개인과 관련 있는 모든 정보입니다. 이때 개인의 비공개, 공개 또는 업무 역할이 구분되지 않습니다. 정의된 "개인 정보"라는 용어는 GDPR에 따른 "개인 데이터"와 대략 일치합니다. 그러나 CCPA에는 가족 및 가정 데이터가 포함되어 있습니다. CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](offering-ccpa.md) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](ccpa-faq.md)를 참조하세요.

이 가이드의 각 섹션에서는 데이터 통제자가 Microsoft 클라우드의 개인 데이터에 대한 DSR에 응답하기 위해 수행할 수 있는 기술적 절차를 간략하게 설명합니다.

#### <a name="terminology"></a>용어

다음은 이 가이드와 관련된 용어의 정의입니다.

- **통제자:** 단독으로 또는 다른 대상과 함께 개인 데이터 처리의 목적 및 방법을 결정하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다. 이러한 처리의 목적 및 방법을 연합국 법률 또는 회원국 법률에 따라 결정하는 경우, 통제자 또는 구체적인 지명 기준을 연합국 법률 또는 회원국 법률에서 제공할 수 있습니다.
- **개인 데이터 및 데이터 주체** 식별되었거나 식별 가능한 자연인(‘데이터 주체’)과 관련된 모든 정보입니다. 식별 가능한 자연인은 직간접적으로, 특히 이름, 식별 번호, 위치 데이터, 온라인 식별자 또는 해당 자연인의 신체적, 생리적, 유전적, 정신적, 경제적, 문화적 또는 사회적 ID와 같은 식별자를 참조하여 식별될 수 있는 사람입니다.
- **프로세서:** 통제자를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다.
- **고객 데이터:** 엔터프라이즈 서비스를 사용하여 고객이 Microsoft에 제공하거나 고객 대신에 Microsoft에 제공된 모든 데이터(모든 텍스트, 소리, 동영상 또는 이미지 파일 포함)입니다. 고객 데이터에는 (1) 최종 사용자의 식별 가능한 정보(예: Azure Active Directory의 사용자 이름 및 연락처 정보) 및 고객이 특정 서비스에 업로드하거나 해당 서비스에서 만드는 고객 콘텐츠(예: Azure Storage 계정에서의 고객 콘텐츠, Azure SQL 데이터베이스의 고객 콘텐츠 또는 Azure 가상 머신에 있는 고객의 가상 머신 이미지)가 포함되어 있습니다.
- **시스템 생성 로그:** Microsoft에서 생성한 로그 및 관련 데이터이며, 이는 Microsoft에서 엔터프라이즈 서비스를 제공하도록 도와줍니다. 시스템 생성 로그에는 주로 가명 처리된 데이터(예: 일반적으로 시스템에서 생성된 숫자인 고유한 ID)가 있으며, 이 데이터는 개인을 직접 식별할 수 없지만 엔터프라이즈 서비스를 사용자에게 전달하는 데 사용됩니다. 시스템 생성 로그에는 사용자 이름과 같은 최종 사용자에 대한 식별 가능한 정보가 포함될 수도 있습니다.

#### <a name="how-to-use-this-guide"></a>이 가이드를 사용하는 방법

이 가이드의 다음 두 부분으로 구성됩니다.

- **1부: 고객 데이터에 대한 데이터 주체 요청에 응답:** 이 가이드 1부에서는 데이터를 작성한 애플리케이션에서 데이터를 액세스, 수정, 제한, 삭제 및 내보내는 방법을 설명합니다. 이 섹션에서는 최종 사용자의 고객 콘텐츠 및 식별 가능 정보에 대해 DSR을 실행하는 방법을 자세히 설명합니다.
- **2부: 시스템 생성 로그에 대한 데이터 주 체 요청에 응답:** Microsoft의 엔터프라이즈 서비스를 사용할 경우, Microsoft는 서비스를 제공하기 위해 시스템 생성 로그라고 알려진 정보를 생성합니다. 이 가이드의 2부에서는 Azure에서 이러한 정보를 액세스, 삭제 및 내보내는 방법을 설명합니다.

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Azure Active Directory 및 Microsoft Intune에 대한 DSR 이해

When considering services provided to enterprise customers, execution of DSRs must always be understood within the context of a specific Azure Active Directory (AAD) tenant. Notably, DSRs are always executed within a given AAD tenant. If a user is participating in multiple tenants, it is important to emphasize that a given DSR is *only* executed within the context of the specific tenant the request was received within. This is critical to understand as it means the execution of a DSR by one enterprise customer **will not** impact the data of an adjacent enterprise customer.

The same also applies for Microsoft Intune provided to an enterprise customer: execution of a DSR against an Intune account *associated with an AAD tenant* **will only** pertain to data within the tenant. In addition, it is important to understand the following when handling Intune accounts within a tenant:

- If an Intune user creates an Azure subscription, the subscription will be handled as if it were an AAD tenant. Consequently, DSRs are scoped within the tenant as described above.
- If an Azure subscription created via an Intune account is deleted, **it will not affect** the actual Intune account. Again, as noted above, DSRs executing within the Azure subscription are limited to the scope of the tenant itself.

DSRs against an Intune account itself, **outside a given tenant**, are executed via the Consumer Privacy Dashboard. Please refer to the Windows Data Subject Request Guide for further details.

## <a name="part-1-dsr-guide-for-customer-data"></a>1부: 고객 데이터에 대한 DSR 가이드

### <a name="executing-dsrs-against-customer-data"></a>고객 데이터에 대해 DSR 실행

Microsoft provides the ability to access, delete, and export certain Customer Data through the Azure Portal and also directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as *in-product experiences*). Details regarding such in-product experiences are described in the respective services' reference documentation.

>[!IMPORTANT]  
>Services supporting in-product DSRs require direct usage of the service's application programming interface (API) or user interface (UI), describing applicable CRUD (create, read, update, delete) operations. Consequently, execution of DSRs within a given service must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services' reference documentation for further details.

### <a name="step-1-discover"></a>1단계: 검색

The first step in responding to a DSR is to find the personal data that is the subject of the request. This first step - finding and reviewing the personal data at issue - will help you determine whether a DSR meets your organization's requirements for honoring or declining a DSR. For example, after finding and reviewing the personal data at issue, you may determine the request doesn't meet your organization's requirements because doing so may adversely affect the rights and freedoms of others.

After you find the data, you can then perform the specific action to satisfy the request by the data subject. For details, see the following:

- [데이터 수집](https://docs.microsoft.com/intune/privacy-data-collect)
- [데이터 저장 및 처리](https://docs.microsoft.com/intune/privacy-data-store-process)
- [개인 데이터 보기](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>2단계: 액세스

After you've found Customer Data containing personal data that is potentially responsive to a DSR, it is up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions you have deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data.

데이터 주체에 사본을 제공할 때는 다른 데이터 주체에 대한 개인 정보와 모든 기밀 정보를 제거하거나 편집해야 할 수 있습니다.

다음은 DSR 액세스 요청에 대한 응답으로 데이터 복사본을 다운로드하는 방법을 설명합니다.

#### <a name="azure-active-directory"></a>Azure Active Directory Domain Services

Microsoft는 엔터프라이즈 고객의 테넌트 관리자에게 DSR 액세스 요청을 관리하는 기능을 제공하는 포털 및 제품 내 환경을 제공합니다. DSR 액세스 요청을 사용하며 사용자의 개인 데이터((a) 최종 사용자에 대한 ID 정보 및 (b) 시스템 생성 로그)에 액세스할 수 있습니다.

#### <a name="service-specific-interfaces"></a>서비스 관련 인터페이스

Microsoft Intune은 사용자 인터페이스(UI) 또는 기존 응용 프로그래밍 인터페이스(API)를 통해 직접 [고객 데이터를 검색](#step-1-discover)할 수 있는 능력을 제공합니다.

### <a name="step-3-rectify"></a>3단계: 수정

If a data subject has asked you to rectify the personal data that resides in your organization's data, you and your organization will have to determine whether it's appropriate to honor the request. Rectifying the data may include taking actions such as editing, redacting, or removing personal data from a document or other type or item.

As a data processor, Microsoft does not offer the ability to correct system-generated logs as it reflects factual activities and constitutes a historical record of events within Microsoft services. With respect to Intune, admins can't update device or app specific information. If an end user wants to correct any personal data (like the device name), they must do so directly on their device. Such changes are synchronized the next time they connect to Intune.

### <a name="step-4-restrict"></a>4단계: 제한

데이터 주체가 개인 데이터 처리를 제한하도록 요청할 수 있습니다. Azure 포털과 기존 API(Application Programming Interface) 또는 UI(사용자 인터페이스)를 제공합니다. 이러한 환경은 엔터프라이즈 고객의 테넌트 관리자에게 데이터 내보내기 및 데이터 삭제의 조합을 통해 그와 같은 DSR을 관리할 수 있는 기능을 제공합니다. 자세한 내용은 [개인 데이터 처리](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data)를 참조하세요.

### <a name="step-5-delete"></a>5단계: 삭제

The "right to erasure" by the removal of personal data from an organization's Customer Data is a key protection in the GDPR. Removing personal data includes removing all personal data and system-generated logs, except audit log information. For details, see [Delete end user personal data](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).

## <a name="part-2-system-generated-logs"></a>2부: 시스템 생성 로그

Audit logs provide tenant admins with a record of activities that generate a change in Microsoft Intune. Audit logs are available for many manage activities and typically create, update (edit), delete, and assign actions. Remote tasks that generate audit events can also be reviewed. These audit logs may contain personal data from users whose devices are enrolled in Intune. Admins can't delete audit logs. For details, see [Audit personal data](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).

## <a name="notify-about-exporting-or-deleting-issues"></a>내보내기 또는 삭제 문제에 대한 알림

Azure Portal에서 데이터를 내보내거나 삭제하는 동안 문제가 발생하면 Azure Portal **도움말 + 지원** 블레이드로 이동하여 **등록 관리 > 기타 보안 및 준수 요청 > 개인 정보 보호 블레이드 및 GDPR 요청**에서 새 티켓을 제출합니다.

## <a name="learn-more"></a>자세한 정보

- [Microsoft 보안 센터](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
