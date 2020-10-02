---
title: GDPR 및 CCPA에 대한 Dynamics 365 데이터 주체 요청
description: 개인 데이터를 찾아서 조치를 취하고, Dynamics 365 고객의 DSR 및 CCPA 요청에 응답하는 방법을 알아보세요.
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR, CCPA
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
hideEdit: true
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: e9b6dc32fc9c9a641504afd1589dd9666bd8e248
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305348"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 및 CCPA에 대한 Dynamics 365 데이터 주체 요청

EU(유럽 연합) [GDPR(일반 데이터 보호 규정)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm)은 사용자(규정에 *데이터 주체*로 알려짐)에게 고용주 또는 다른 유형의 대리점 및 조직(*데이터 통제자* 또는 단순히 *통제자*로 지칭)이 수집한 개인 데이터를 관리할 수 있는 권한을 부여합니다. 개인 데이터는 GDPR에서는 보다 광범위하게 식별되었거나 식별 가능한 자연인과 관련된 모든 데이터로 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 부여합니다. 이러한 권한에는 개인 데이터 복사본 획득, 변경 요청, 처리 제한, 삭제 또는 다른 통제자에게 이동될 수 있도록 전자 형식으로 수신하는 권한이 포함됩니다. 데이터 주체가 통제자에게 개인 데이터에 대해 조치를 취할 것을 요구하는 공식적인 요청을 이 문서에서는 *데이터 주체 권한 요청* 또는 DSR 요청이라고 합니다.

마찬가지로 캘리포니아 소비자 개인 정보 보호법(CCPA)은 캘리포니아 소비자에게 GDPR의 데이터 주체 권리와 유사한 권리를 포함하여, 소비자의 개인 정보 삭제, 액세스 및 수신(이식성)과 같은 개인 정보 보호 권리 및 의무를 제공합니다.  또한 CCPA는 특정 공개, 실행 권리 행사 시 차별 대우로부터 보호, “판매"로 분류되는 특정 데이터 전송에 대한 "옵트아웃(opt-out)/옵트인(opt-in)" 요구도 허용합니다. 판매는 가치 있는 대가관계를 위하여 데이터 공유를 포함하도록 광범위하게 정의됩니다. CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](offering-ccpa.md) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](ccpa-faq.md)를 참조하세요.

이 가이드에서는 Microsoft 제품, 서비스 및 관리 도구를 사용하여 통제자 고객이 개인 데이터를 찾아 조치를 취함으로써 DSR 요청에 대처하는 데 도움을 주는 방법을 설명합니다. 특히 여기에는 Microsoft 클라우드에 있는 개인 데이터 또는 개인 정보를 찾고, 액세스하고, 조치를 취하는 방법이 포함됩니다. 이 가이드에 설명된 프로세스에 대한 간략한 개요는 다음과 같습니다.

- **검색:** 검색 및 검색 도구를 사용하여 DSR 요청의 대상이 될 수 있는 고객 데이터를 더 쉽게 찾을 수 있습니다. 잠재적으로 반응형 문서가 수집되면 다음 단계에 설명된 DSR 작업을 수행하여 요청에 응답할 수 있습니다. 또는 요청이 DSR 요청에 응답하기 위한 조직의 지침을 충족하지 않는다고 판단할 수 있습니다.
- **액세스:** Microsoft 클라우드에 있는 개인 데이터를 검색하고 요청될 경우 데이터 주체가 사용할 수 있는 복사본을 만듭니다.
- **수정:** 해당되는 경우 개인 데이터를 변경하거나 요청된 다른 작업을 구현합니다.
- **제한**: 다양한 온라인 서비스에 대한 라이선스를 제거하거나 가능한 경우 원하는 서비스를 꺼서 개인 데이터의 처리를 제한합니다. 다음을 수행할 수 있습니다.
- **삭제:** Microsoft 클라우드에 있는 개인 데이터를 영구적으로 제거합니다.
- **내보내기/수신(이식성):** 개인 데이터 또는 개인 정보의 전자 사본(컴퓨터가 읽을 수 있는 형식)을 데이터 주체에게 제공합니다. CCPA 하에서 개인 정보는 식별된 또는 식별 가능한 개인과 관련 있는 모든 정보입니다. 이때 개인의 비공개, 공개 또는 업무 역할이 구분되지 않습니다. 정의된 용어 "개인 정보"는 GDPR의 "개인 데이터"와 대략 일치합니다. 그러나 CCPA에는 가족 및 가정 데이터가 포함되어 있습니다. CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](offering-ccpa.md) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](ccpa-faq.md)를 참조하세요.

이 가이드의 각 섹션에서는 데이터 통제자가 Microsoft 클라우드의 개인 데이터에 대한 DSR 요청에 응답하기 위해 수행할 수 있는 기술적 절차를 간략하게 설명합니다.

## <a name="gdpr-terminology"></a>GDPR 용어

다음 목록은 본 가이드와 관련된 용어의 정의입니다.

- **통제자:** 단독으로 또는 다른 대상과 함께 개인 데이터 처리의 목적 및 방법을 결정하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다. 이러한 처리의 목적 및 방법을 연합국 법률 또는 회원국 법률에 따라 결정하는 경우, 통제자 또는 구체적인 지명 기준을 연합국 법률 또는 회원국 법률에서 제공할 수 있습니다.
- **개인 데이터 및 데이터 주체** 식별되었거나 식별 가능한 자연인(‘데이터 주체’)과 관련된 모든 정보입니다. 식별 가능한 자연인은 직간접적으로, 특히 이름, 식별 번호, 위치 데이터, 온라인 식별자 또는 해당 자연인의 신체적, 생리적, 유전적, 정신적, 경제적, 문화적 또는 사회적 ID와 같은 식별자를 참조하여 식별될 수 있는 사람입니다.
- **프로세서:** 통제자를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다.
- **고객 데이터:** 엔터프라이즈 서비스를 사용하여 고객이 Microsoft에 제공하거나 고객 대신에 Microsoft에 제공된 모든 데이터(모든 텍스트, 소리, 동영상 또는 이미지 파일 포함)입니다. 고객 데이터에는 (1) 최종 사용자의 식별 가능한 정보(예: Azure Active Directory의 사용자 이름 및 연락처 정보) 및 고객이 특정 서비스에 업로드하거나 해당 서비스에서 만드는 고객 콘텐츠(예: Azure Storage 계정에서의 고객 콘텐츠, Azure SQL 데이터베이스의 고객 콘텐츠 또는 Azure 가상 머신에 있는 고객의 가상 머신 이미지)가 포함되어 있습니다.
- **시스템 생성 로그:** Microsoft에서 생성한 로그 및 관련 데이터이며, 이는 Microsoft에서 엔터프라이즈 서비스를 제공하도록 도와줍니다. 시스템 생성 로그에는 주로 가명 처리된 데이터(예: 일반적으로 시스템에서 생성된 숫자인 고유한 식별자)가 있으며, 이 데이터는 개인을 직접 식별할 수 없지만 엔터프라이즈 서비스를 사용자에게 제공하는 데 사용됩니다. 시스템 생성 로그에는 사용자 이름과 같은 최종 사용자에 대한 식별 가능한 정보가 포함될 수도 있습니다.

## <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>사용자가 컨트롤러 책임을 충족하도록 가이드가 지원하는 방법

2부로 나누어진 이 가이드에서는 Dynamics 365 제품, 서비스 및 관리 도구를 사용하여 Microsoft 클라우드에서 데이터를 검색하고 작업하는 방법을 설명하여 GDPR에 따라 권리를 행사하는 데이터 주체의 요청에 응답하여 Microsoft 클라우드에서 데이터를 찾고 활용하도록 도와줍니다. 첫 번째 부분은 고객 데이터에 포함된 개인 데이터를 다루고, 다음 부분은 시스템 생성 로그에 캡처된 기타 가명 처리된 개인 데이터를 다룹니다.

- **1부: 고객 데이터에 포함된 개인 데이터에 대한 DSR(Data Subject Right) 요청에 응답:** 이 가이드의 1부에서는 Dynamics 365 응용 프로그램(Software as a Service)에서 온라인 서비스에 제공한 고객 데이터의 일부로 처리되는 개인 데이터를 액세스, 수정, 제한, 삭제 및 내보내는 방법을 설명합니다.
- **2부: 필명화된 데이터에 대한 데이터 주체 권한 요청에 응답:** Dynamics 365 엔터프라이즈 서비스를 사용하는 경우 Microsoft는 서비스를 제공하기 위해 일부 정보(이 문서 내에서 *시스템 생성 로그*라고 함)를 생성하며, 이 정보는 시스템에서 작업을 식별하기 위해 최종 사용자가 남겨둔 사용 공간으로 제한됩니다. 이 데이터를 추가 정보를 사용하지 않고 특정 데이터 주체에 속하는 것으로 할 수 없는 경우에도, 일부 데이터는 GDPR에서 개인용으로 간주될 수 있습니다. 이 가이드의 2부에서는 Dynamics 365에서 생성되는 시스템 생성 로그에 액세스하며 이를 삭제하고 내보내는 방법을 설명합니다.

## <a name="preparing-for-data-subject-rights-investigations"></a>데이터 주체 권리 조사 준비

데이터 주체가 권리를 행사하고 요청을 수행할 때 다음 사항을 고려하세요.

- 데이터 주체가 요청의 일부로 사용자에게 제공한 정보를 사용하여 개인과 역할(예: 직원, 고객, 공급업체)을 적절히 식별합니다. 이 정보는 이름, 직원 ID 또는 고객 번호, 기타 식별자일 수 있습니다.
- 요청의 날짜 및 시간을 기록합니다(요청을 완료하는 데 30일이 허용됨).
- 요청이 데이터 주체 요청을 허용하거나 거부하기 위한 조직의 요구 사항을 충족하는지 확인합니다. 예를 들어, 요청을 이행할 경우 귀하에게 해당되는 다른 법적, 재무적 또는 규제 의무와 충돌하지 않는지 또는 타인의 권리 및 자유를 침해하지 않는지 확인해야 합니다.
- 요청과 관련된 정보가 있는지 확인합니다.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>1단계: 고객 데이터에 포함된 개인 데이터의 데이터 주체 권한 요청에 대한 응답

다음 문서에서는 Dynamics 365에서 처리되는 고객 데이터에 포함된 개인 데이터에 대한 DSR 요청을 준비하고 대응하는 데 도움이 되는 정보를 찾을 수 있습니다. 개인 데이터가 Microsoft 개인정보취급방침에 정의된 관리자 데이터 또는 지원 데이터 등의 온라인 서비스 구독의 서비스 과정 동안 Microsoft에서 처리하는 기타 데이터 범주에 존재할 수도 있다는 사실을 숙지하는 것이 중요합니다. 이 문서는 Dynamics 365에 제공한 고객 데이터에 포함되어 있는 개인 데이터에 영향을 미치는 DSR 요청의 검색 및 관리 프로세스에서 사용자를 지원하는 내용으로 제한됩니다.

Dynamics 365는 여러 데이터 처리 기능을 SaaS(Software-as-a-Service)로 제공하는 온라인 서비스입니다. 이와 같이 Dynamics 365는 특징, 용도 또는 기타 구체적인 특성(예: 판매 데이터, 거래, 재무, HR 정보 등)에 따라 다를 수 있는 다양한 데이터 모음을 처리하도록 작성된 광범위한 기능 배열을 제공합니다. 이러한 다양성을 고려할 때 Dynamics 365는 각 응용 프로그램에서 DSR 요청이 처리될 수 있는 여러 방법에도 반영되는 고객 데이터 처리를 위한 여러 양식, 필드, 스키마, 끝점 및 논리를 제공합니다. Dynamics 365 응용 프로그램은 특정 DSR 요청을 처리하는 몇 가지 방법을 제공하므로 이 가이드에서는 각 응용 프로그램이 제공하는 기술 설명을 토대로 해당 방법을 설명합니다.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>고객 데이터 찾기

데이터 주제 권리 요청에 응답하는 첫 번째 단계는 요청의 대상이 되는 고객 데이터를 검색하고 식별하는 것입니다.

고객 데이터를 적절히 분류하는 것은 Dynamics 365 for Customer Engagement 비즈니스 애플리케이션에서 개인 데이터를 사용할 때 초석이 됩니다. 고객 관계용 Dynamics 365를 사용하면 데이터 분류에 맞게 유연하게 응용 프로그램 확장을 구축할 수 있습니다. 적절한 분류를 통해 정보를 개인 데이터로 식별할 수 있으며, 데이터 주체의 요청에 응답하여 데이터를 찾고 검색할 수 있습니다. 또한 개인 데이터를 수집하고 관리하기 위한 법적 및 규제 요건을 준수하는 데도 도움이 될 수 있습니다.

Microsoft는 데이터 주체 권리 요청에 응답하고 고객 데이터에 액세스하는 데 도움이 될 수 있는 기능을 제공합니다. 그렇지만 개인 데이터를 적절히 찾아 분류하는 것은 귀하의 책임입니다.

***Dynamics 365 for Customer Engagement***는 상세하게 찾기 검색 및 레코드 검색과 같이 레코드 내에서 개인 데이터를 검색하는 여러 방법을 제공합니다.  이러한 기능을 통해 개인 데이터를 식별하고 찾을 수 있습니다.

- [상세하게 찾기 검색](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)
- [레코드 검색](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records): 여러 레코드 유형 간에 검색 가능

Dynamics 365 for Marketing에서는 다음과 같은 추가 기능을 사용할 수 있습니다.

1. [Power BI 보고서 작성](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm): 고객 데이터를 필터링하고 식별하는 데 사용됩니다.
2. 마케팅 실무 담당자 및 목표에 대해 Insight Views를 사용하여 고객 데이터가 포함되어 있을 수 있는 추가 데이터 요소를 식별합니다.

***Dynamics 365 고객 서비스 통계***는 고객의 GDPR 요청에 응답하기 위해 [고객 데이터](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-discovery)를 찾는 데 도움이 되는 리소스 목록을 제공합니다.

***재무 및 운영용 Dynamics 365***은 고객 데이터를 검색할 수 있는 몇 가지 방법을 제공합니다. 사용자는 테넌트 관리자로서 다음 작업을 수행하여 고객 데이터를 검색할 수 있습니다.

- 개인 데이터를 빠르게 검색하려는 목적에 맞게 고객 데이터를 구성합니다. 이를 위해 [데이터 인벤토리 분류 방법](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory)을 참조하세요.
- [개인 검색 보고서](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report)를 사용하여 개인 데이터를 찾아서 수집합니다.
- [개인 검색 보고서 확장](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report): 새 엔터티를 작성하거나 기존 엔터티를 확장합니다.
- 검색 및 필터 기능을 사용하여 특정 개인 데이터를 찾은 후, Microsoft Office 내보내기 기능을 사용하여 해당 데이터를 내보내거나 브라우저 확장을 사용하여 해당 정보를 .pdf로 인쇄합니다.
- 개인 데이터를 찾아 내보내는 사용자 지정 양식을 작성합니다.
- 인증된 고객이 해당 개인 데이터를 볼 수 있도록 하는 외부 포털 또는 웹 사이트를 작성합니다.

***Dynamics 365 Business Central***은 고객 데이터를 검색할 수 있는 몇 가지 방법을 제공합니다. 자세한 내용을 확인하려면 [검색, 필터링 및 데이터 정렬](https://docs.microsoft.com/dynamics365/business-central/ui-enter-criteria-filters)를 참조하십시오.

***Dynamics 365 for Talent***는 상세하게 검색 및 필터 기능을 제공하여 특정 개인 데이터를 찾고, Microsoft Office 내보내기 기능을 사용하여 해당 데이터를 내보내거나 브라우저 확장을 사용하여 해당 정보를 .pdf로 인쇄합니다.

- [개인 검색 보고서](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report)를 사용하여 고객 데이터를 찾아 수집합니다.
- [개인 검색 보고서 확장](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report): 새 엔터티를 작성하거나 기존 엔터티를 확장합니다.

### <a name="providing-a-copy-of-customer-data"></a>고객 데이터의 복사본 제공

***Dynamics 365 for Customer Engagement***의 고객 데이터는 포괄적 인 엔티티 내보내기 기능을 사용하여 내보낼 수 있습니다. 데이터 이동성 요청을 용이하게 하기 위해 고객 데이터를 정적 Excel 파일로 내보낼 수 있습니다. Excel을 사용하면 이식 가능성 요청에 포함되도록 개인 데이터를 편집 한 다음 .csv 또는 .xml과 같이 일반적으로 사용되는 기계 가독 형식으로 저장할 수 있습니다. 또한 [Common Data Service 웹 API](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/overview)를 통해 Dynamics 365 for Customer Engagement 레코드를 내보낼 수 있습니다.

또한 Dynamics 365 for Marketing의 경우 고객이 개인 데이터가 포함되어 있을 수 있는 캡처된 고객 상호 작용에 대한 추가 레코드를 검색하는 확장 프로그램을 빌드할 수 있도록 하는 [전용 API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact)도 제공됩니다. 이 API는 백 엔드 시스템에서 모든 관련 정보를 로드한 후 하나의 이식 가능 문서로 조합합니다.

***Dynamics 365 고객 서비스 정보 활용***을 사용하면 데이터 내보내기를 사용하여 [고객 데이터 사본을 제공](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export)할 수 있습니다.

***재무 및 작업용 Dynamics 365***의 고객 데이터는 포괄적인 엔티티 내보내기 기능을 사용하여 내보내기할 수 있습니다. 테넌트 관리자는 [*데이터 관리 및 통합 엔티티*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)를 사용하여 제공된 엔터티를 활용, 엔터티를 새로 생성하거나 기존 엔티티를 확장하여 반복적인 개인 데이터를 Excel 또는 [*데이터 가져 오기 및 내보내기 작업*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)을 사용하는 여러 가지 일반 형식으로 내보낼 수 있습니다.  또는 데이터 이동성 요청을 용이하게 하기 위해 수많은 목록을 정적 Excel 파일로 내보낼 수 있습니다. 고객 데이터를 Excel로 내보낼 때 이식 가능성 요청에 포함될 개인 데이터를 편집한 다음 파일을 .csv 또는 .xml과 같이 일반적으로 사용되는 컴퓨터가 읽을 수 있는 형식으로 저장합니다. 또한 *개인 검색 보고서*를 사용하여 개인 데이터로 분류한 데이터를 데이터 주체에 제공할 수도 있습니다.

***Dynamics 365 Business Central***에서 다음 두 가지 기능을 활용하여 데이터 주체에게 고객 데이터 사본을 제공할 수 있습니다.

고객 데이터를 Excel 파일로 내보낼 수 있습니다. Excel에서 이식 가능성 요청에 포함되도록 고객 데이터를 편집하고 .csv 또는 .xml과 같이 일반적으로 사용되는 기계 가독 형식으로 저장할 수 있습니다. 자세한 내용은 [비즈니스 데이터를 Excel로 내보내기](https://docs.microsoft.com/dynamics365/business-central/about-export-data)를 참고하십시오.

***Dynamics 365 for Talent***에서 [사용자 검색 보고서 확장](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)을 사용하여 데이터 주체의 개인 데이터 사본에 대한 요청을 지원하기 위해 정보를 수집합니다.

### <a name="rectifying-customer-data"></a>고객 데이터 수정

***Dynamics 365 for Customer Engagement***는 정확하지 않거나 불완전한 고객 데이터를 수정하거나 고객 데이터를 지우기 위한 다음과 같은 방법을 제공합니다.

- “고객 데이터 찾기”에 언급된 기능을 사용하여 고객 데이터를 검색하고, 고객 관계 양식에서 데이터를 직접 편집합니다. 편집은 단일 행 수준에서 수행할 수 있으며 여러 행을 직접 수정할 수도 있습니다.
- 여러 고객 관계 레코드를 대량으로 편집하면 Microsoft Office 추가 기능을 사용하여 Microsoft Excel로 데이터를 내보내고, 변경을 수행하고, 수정한 데이터를 Excel에서 Dynamics 365 for Customer Engagement로 가져올 수 있습니다.

또한 Dynamics 365 for Marketing에 대해 다음을 수행할 수도 있습니다.

- 단일 또는 여러 행을 직접 편집하여 내 데이터 방문 페이지 업데이트
- 포함될 수 있는 편집 가능한 여러 연락처 필드가 있는 [구독 센터](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) 페이지를 준비합니다. 이 페이지에서 최종 사용자는 최대한 많이 자체 정보를 업데이트할 수 있습니다.

***Dynamics 365 고객 서비스 정보 활용***은 조직이 [고객 데이터를 수정하거나 변경](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary)할 수 있는 기능을 제공합니다.

***Dynamics 365 for Finance and Operations***에서 [*사용자 지정 도구*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)사용할 수도 있지만, 의사 결정 및 구현은 사용자의 책임입니다.

***Dynamics 365 Business Central***에서 부정확하거나 불완전한 고객 데이터를 수정하는 2가지 방법을 제공합니다.

여러 Business Central 보고서를 대량으로 빠르게 편집하려면 [Business Central Excel 추가 기능](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in)통해 목록을 Excel로 내보낸 후 여러 레코드를 수정한 후 Excel에서 수정한 데이터를 Business Central에 게시할 수 있습니다. 자세한 내용은 [비즈니스 데이터를 Excel로 내보내기](https://docs.microsoft.com/dynamics365/business-central/about-export-data)를 참조하세요.

대상 개인 데이터가 포함된 데이터 요소를 수동으로 편집하여 고객 카드의 고객 정보와 같이 모든 필드에 저장된 고객 데이터를 변경할 수 있습니다. 자세한 내용은 [데이터 입력](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)을 참조하세요.

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>비즈니스 거래 시 항목 수정에 대한 간략한 메모

일반, 고객 및 세금 원장 항목과 같은 거래 레코드는 엔터프라이즈 리소스 계획 시스템의 무결성에 필수적입니다. 재무 또는 기타 거래에 속하는 개인 데이터는 금융법(예: 세법)을 준수하거나, 사기(예: 보안 감사 추적)를 방지하거나, 산업 인증을 준수하기 위해 “있는 그대로” 유지됩니다. 따라서 Dynamics 365 for Finance and Operations 및 Dynamics 365 Business Central에서는 이러한 레코드의 데이터를 수정하지 못하도록 제한합니다.

비즈니스 거래 레코드에 개인 데이터를 저장하는 경우 데이터 주체 요청을 위해 개인 데이터를 수정, 삭제 또는 처리를 제한하는 유일한 방법은 Dynamics 365 Business Central의 [사용자 지정 기능](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index)을 사용하는 것입니다. 따라서 [데이터 주체의 데이터 수정 요청](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)에 대한 의사 결정 및 구현은 사용자의 책임입니다.

### <a name="restricting-the-processing-of-customer-data"></a>고객 데이터 처리 제한

데이터 주제로부터 고객 데이터 처리 제한 요청을 받는 경우 온라인 서비스에서 영향을 받는 고객 데이터를 쉽게 추출한 후 클라우드 응용 프로그램이 제공하는 처리 기능과는 분리되는 별도 컨테이너(즉, 온-프레미스 저장소 또는 데이터 격리 기능이 있는 별도의 웹 서비스)에 저장할 수 있습니다.

데이터 처리 블록과 같은 대체 메커니즘은 ***Dynamics 365 Business Central***에서 제공되며 이는 사용자에게 특정 데이터 주체의 레코드를 차단할 수 있는 기능을 제공합니다. 자세한 내용은 [데이터 주제에 대한 데이터 처리 제한](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject)을 참조하십시오. 레코드가 차단된 것으로 표시되면 Dynamics 365는 해당 데이터 주체의 고객 데이터 처리를 중단합니다. 차단된 레코드를 사용하는 새 트랜잭션을 만들 수는 없습니다. 예를 들어 고객 또는 영업 사원이 차단된 경우 고객에 대해 새 송장을 작성할 수 없습니다.

### <a name="deleting-customer-data"></a>고객 데이터 삭제

데이터 주체가 고객 데이터 삭제를 요청하면 다음과 같은 몇 가지 방법으로 삭제할 수 있습니다.

- 여러 Dynamics 365 레코드를 대량으로 편집하면 Microsoft Office 추가 기능을 사용하여 Microsoft Excel로 데이터를 내보내고, 변경을 수행하고, 수정한 데이터를 Excel에서 온라인 서비스로 다시 가져올 수 있습니다.
- 삭제하려는 데이터를 찾은 수 대상 고객 데이터를 포함하는 데이터 요소를 수동으로 삭제하여 모든 필드에 저장된 고객 데이터를 삭제할 수 있습니다. 예를 들어 데이터 주체를 나타내는 연락처 레코드와 개인 데이터를 포함하는 기타 레코드를 영구 삭제할 수 있습니다.

또한 Dynamics 365 Marketing의 경우 연락처를 삭제하면 개인 정보와의 상호 작용되는 데이터도 제거됩니다. 모든 사용자 지정 필드 또는 엔터티에 대해 사용자가 관련 레코드에서 모든 고객 데이터를 삭제하고 연락처 레코드와의 연결을 해제하여 모든 개인 정보가 제거되도록 시스템을 사용자 지정해야합니다. 자세한 정보는 [개발자 가이드(마케팅)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide)를 참조합니다.

***Dynamics 365 고객 서비스 정보 활용***은 조직에 [고객 데이터](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete)을 삭제할 수 있는 기능을 제공합니다.

또는 ***Dynamics 365 for Finance and Operations***에서 [*사용자 지정 도구*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)를 사용하여 고객 데이터를 지우거나 수정할 수 있습니다.

***Dynamics 365 Business Central***에서 데이터 주체가 고객 데이터에 포함될 수 있는 개인 데이터를 삭제할 것을 요청하면 다음과 같은 몇 가지 방법으로 해당 요청을 처리할 수 있습니다.

- 여러 Business Central 보고서를 대량으로 빠르게 편집하려면 [Business Central Excel 추가 기능](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in)통해 데이터를 Excel로 내보낸 후 여러 레코드를 삭제한 후 Excel에서 이러한 변경 내용을 Business Central에 다시 게시할 수 있습니다. 자세한 내용은 [비즈니스 데이터를 Excel로 내보내기](https://docs.microsoft.com/dynamics365/business-central/about-export-data)를 참조하세요.
- 대상 고객 데이터를 포함하는 데이터 요소를 수동으로 삭제하여 모든 필드에 저장된 고객 데이터를 삭제할 수 있습니다. 자세한 내용은 [데이터 입력](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)을 참조하세요.
- 고객 데이터를 직접 삭제할 수 있습니다. 예를 들어 연락처를 삭제한 후 취소된 상호 작용 로그 항목 삭제 일괄 작업을 실행하여 해당 연락처에 대한 상호 작용을 삭제합니다.
- 메모, 게시된 판매 및 구매 송장과 같이 개인 데이터가 포함된 [문서를 삭제](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents)할 수 있습니다.

개별 레코드의 대량 또는 개별적인 삭제 외에도, 해고된 작업자만 ***Dynamics 365 for Talent***에서 완전히 삭제할 수 있습니다. [다음 단계에 따라 해고된 작업자를 삭제하세요](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>고객 데이터 내보내기

데이터 이동성 요청에 응답하려면 ***Dynamics 365 for Customer Engagement***의 고객 데이터는 포괄적인 엔터티 내보내기 기능을 사용하여 내보낼 수 있습니다. 데이터 이동성 요청을 용이하게 하기 위해 고객 데이터를 정적 Excel 파일로 내보낼 수 있습니다. Excel을 사용하면 이식 가능성 요청에 포함되도록 개인 데이터를 편집 한 다음 .csv 또는 .xml과 같이 일반적으로 사용되는 기계 가독 형식으로 저장할 수 있습니다.

또한 Dynamics 365 for Marketing의 경우 고객이 개인 데이터가 포함되어 있을 수 있는 캡처된 고객 상호 작용에 대한 추가 레코드를 검색하는 확장 프로그램을 빌드할 수 있도록 하는 [전용 API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact)도 제공됩니다. 이 API는 백 엔드 시스템에서 모든 관련 정보를 로드한 후 하나의 이식 가능 문서로 조합합니다.

***Dynamics 365 고객 서비스 통계***의 경우 Azure 관리 포털을 통해 [고객 데이터를 내보내기](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export)할 수 있습니다.

***재무 및 운영을 위한 Dynamics 365***는 제공된 엔터티, 새로 생성된 엔터티 또는 확장된 엔터티가 반복 가능한 개인 데이터를 Excel로 내보낼 수 있게 하는 데이터 관리 및 통합 엔터티를 제공합니다. 또는 [데이터 가져오기 및 내보내기 작업](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)을 사용하는 기타 여러 일반적인 형식을 제공합니다.  또는 데이터 이동성 요청을 용이하게 하기 위해 수많은 목록을 정적 Excel 파일로 내보낼 수 있습니다. 고객 데이터를 Excel로 내보낼 때 이런 방식으로 이식 가능성 요청에 포함될 개인 데이터를 편집한 다음 파일을 .csv 또는 .xml과 같이 일반적으로 사용되는 컴퓨터가 읽을 수 있는 형식으로 저장합니다.

Dynamics 365 for Finance and Operations 및 ***Dynamics 365 for Talent*** 둘 다 개인 데이터로 분류한 데이터를 데이터 주제에게 제공하기 위한 사용자 검색 보고서를 제공합니다.

***Dynamics 365 Business Central***은 다음과 같은 기능을 제공합니다.

- 고객 데이터를 Excel 파일로 내보낼 수 있습니다. Excel에서 이식 가능성 요청에 포함되도록 고객 데이터를 편집하고 .csv 또는 .xml과 같이 일반적으로 사용되는 기계 가독 형식으로 저장할 수 있습니다. 자세한 내용은 [비즈니스 데이터를 Excel로 내보내기](https://docs.microsoft.com/dynamics365/business-central/about-export-data)를 참조하십시오.
- 고객 데이터를 Excel 파일로 내보낼 수 있습니다. Excel에서 이식 가능성 요청에 포함되도록 고객 데이터를 편집하고 .csv 또는 .xml과 같이 일반적으로 사용되는 기계 가독 형식으로 저장할 수 있습니다. 자세한 내용은 [비즈니스 데이터를 Excel로 내보내기](https://docs.microsoft.com/dynamics365/business-central/about-export-data)를 참조하십시오.


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>2단계: 시스템 생성 로그에 대한 DSR에 응답

또한 Microsoft는 GDPR의 광범위한 “개인 데이터” 정의에 따라 개인적인 것으로 인식될 수 있는 시스템 생성 로그를 액세스, 내보내기 및 삭제하는 기능을 사용자에게 제공합니다. GDPR에 따라 개인적인 것으로 인식될 수 있는 시스템 생성 로그의 예는 다음과 같습니다.

- 사용자 활동 로그와 같은 제품 및 서비스 사용 데이터
- 사용자 검색 요청 및 쿼리 데이터
- 시스템 기능 및 사용자나 기타 시스템의 상호 작용의 산물로서 제품 및 서비스에서 생성된 데이터

시스템 생성 로그의 데이터를 제한하거나 수정하는 기능은 지원되지 않습니다. 시스템 생성 로그 데이터는 Microsoft 클라우드 및 진단 데이터 내에서 수행되는 실제 작업으로 구성되며 이러한 데이터를 수정하면 작업의 기록 데이터가 손상되어 사기 및 보안 위험이 높아질 수 있습니다.

### <a name="accessing-and-exporting-system-generated-logs"></a>시스템 생성 로그 액세스 및 내보내기

관리자는 Dynamics 365 서비스 및 응용 프로그램의 특정 사용자의 사용과 관련된 시스템 생성 로그에 액세스할 수 있습니다. 시스템 생성 로그를 액세스하고 내보내려면

1. [Microsoft 서비스 보안 포털](https://servicetrust.microsoft.com/)로 이동한 후 Dynamics 365 전역 관리자의 자격 증명을 사용하여 로그인합니다.
2. 페이지 위쪽의 **개인 정보 보호** 드롭다운 목록에서 **데이터 주체 요청**을 클릭합니다.
3. **데이터 주체 요청** 페이지의 **시스템 생성 로그**에서 **데이터 로그 내보내기**를 클릭합니다.
    > [!NOTE]
    > **데이터 로그 내보내기**가 표시됩니다. 조직이 제출한 데이터 내보내기 요청 목록이 표시됩니다.
4. 사용자에 대한 새 요청을 만들려면 **데이터 내보내기 요청 만들기**를 클릭합니다.

새 요청을 만들면 **데이터 로그 내보내기** 페이지에 표시되므로 해당 상태를 추적할 수 있습니다. 요청이 완료되면 시스템 생성 로그에 액세스할 수 있는 링크를 클릭할 수 있습니다. 그러면 해당 로그는 요청을 만들고 30일 이내에 조직의 Azure Storage 위치로 내보내집니다. 데이터는 JSON 또는 XML과 같이 컴퓨터가 읽을 수 있는 일반적인 파일 형식으로 저장됩니다. Azure 계정 및 Azure Storage 위치가 없는 경우 조직을 위한 Azure 계정 및/또는 Azure Storage 위치를 만들어야 합니다. 그래야 데이터 로그 내보내기 도구를 통해 시스템 생성 로그를 내보낼 수 있습니다.

Azure에서는 조직이 네이티브 JSON 형식의 데이터를 지정된 Azure Storage 컨테이너로 내보낼 수 있도록 하여 해당 요청을 지원합니다. [Microsoft Azure Storage 소개 - Blob 저장소](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage) 문서를 참조하세요. 검색되는 데이터에는 서비스의 보안과 안정성을 손상시킬 수 있는 데이터가 포함되지 않습니다.

> [!IMPORTANT]
> 테넌트에서 사용자 데이터를 내보내려면 테넌트 관리자여야 합니다.

다음 표에서는 시스템 생성 로그를 액세스하고 내보내는 방법을 요약해서 설명합니다.

| | |
|:----|:---|
| | |
|**Microsoft 데이터 로그 내보내기 도구가 요청을 완료하는 데 얼마나 걸리나요?**| 이 기간은 몇 가지 요인에 따라 다를 수 있습니다. 대부분의 경우 1~2일이면 완료되지만 30일까지 소요될 수도 있습니다. |
|**어떤 형식으로 출력되나요?**| XML, CSV 또는 JSON 등의 읽을 수 있는 구조화된 컴퓨터 파일로 출력됩니다. |
|**데이터 로그 내보내기 도구는 어떤 데이터를 반환하나요?**| 데이터 로그 내보내기 도구는 Microsof에서 저장하는 시스템 생성 로그를 반환합니다. 내보낸 데이터는 Office 365, Azure 및 Dynamics를 포함하여 다양한 Office 365 서비스에 걸쳐져 있습니다. |
|***데이터 로그 내보내기 도구에 액세스하여 시스템 생성 로그에 대한 액세스 요청을 제출할 수 있는 사용자는 누구인가요?**| Dynamics 365 전역 관리자는 GDPR 로그 관리자 유틸리티에 액세스할 수 있습니다. |
|**데이터는 어떻게 사용자에게 반환되나요?**| 데이터는 조직의 Azure Storage 위치로 내보내집니다. 이 데이터를 사용자에게 표시/반환하는 방식은 조직의 관리자가 결정합니다. |
|**시스템 생성 로그의 데이터는 어떤 모습으로 표시되나요?**| JSON 형식의 시스템 생성 로그 레코드 예제: <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

### <a name="deleting-system-generated-logs"></a>시스템 생성 로그 삭제

액세스 요청을 통해 검색된 시스템 생성 로그를 삭제하려면 서비스에서 해당 사용자를 제거하고 Azure Active Directory 계정을 영구적으로 삭제해야 합니다. 사용자를 영구적으로 삭제하는 방법을 보려면 Azure 데이터 주체 요청 항목의 [5단계: 삭제](gdpr-dsr-azure.md#step-5-delete) 섹션을 참조하세요. 사용자 계정을 영구적으로 삭제하는 작업은 일단 시작하면 되돌릴 수 없다는 점에 유의하세요. 사용자 계정을 영구적으로 삭제할 경우 서비스의 보안이나 안정성을 손상시킬 수 있는 데이터를 제외하고 30일 이내에 거의 모든 Dynamics 365 서비스의 시스템 생성 로그에서 사용자의 데이터가 삭제됩니다.

## <a name="learn-more"></a>자세히 알아보기

- [Microsoft 보안 센터](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
