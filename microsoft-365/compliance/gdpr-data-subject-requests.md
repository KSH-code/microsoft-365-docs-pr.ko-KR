---
title: GDPR 및 CCPA에 대한 데이터 주체 요청
description: ''
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
titleSuffix: Microsoft GDPR
ms.openlocfilehash: fc5f4f8752d17595cfafaa39626f0d36675d7c82
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558058"
---
# <a name="data-subject-requests-and-the-gdpr-and-ccpa"></a>데이터 주체 요청과 GDPR 및 CCPA

GDPR(일반 데이터 보호 규제)는 EU(유럽 연합) 회원국 국민에게 제품과 서비스를 제공하거나 귀하 또는 귀사가 어디에 있는지 관계없이 EU 거주자의 데이터를 수집하고 분석하는 조직에 새로운 규칙을 도입합니다. 추가 세부 정보는 [GDPR 요약 항목](gdpr.md)에 있습니다.

마찬가지로 캘리포니아 소비자 개인 정보 보호법(CCPA)은 캘리포니아 소비자에게 GDPR의 데이터 주체 권리와 유사한 권리를 포함하여, 소비자의 개인 정보 삭제, 액세스 및 수신(이식성)과 같은 개인 정보 보호 권리 및 의무를 제공합니다.  또한 CCPA는 특정 공개, 실행 권리 행사 시 차별 대우로부터 보호, “판매"로 분류되는 특정 데이터 전송에 대한 "옵트아웃(opt-out)/옵트인(opt-in)" 요구도 허용합니다. 이 문서에서는 Microsoft 제품 및 서비스를 사용 하 여 GDPR 및 CCPA 하에서 DSRs(데이터 주제 요청)를 완료하는 방법에 대한 정보를 안내합니다.

- [Office 365](gdpr-dsr-Office365.md)
- [Azure](gdpr-dsr-Azure.md)
- [Intune](gdpr-dsr-Intune.md)
- [Dynamics 365](gdpr-dsr-Dynamics365.md)
- [Visual Studio 제품군](gdpr-dsr-visual-studio-family.md)
- [Azure DevOps Services](gdpr-dsr-vsts.md)
- [Microsoft 지원 및 전문 서비스](gdpr-dsr-prof-services.md)

## <a name="terminology"></a>용어

이 문서에서 사용된 GDPR 용어에 대한 유용한 정의:

- *데이터 컨트롤러(컨트롤러)*: 개인 데이터 처리의 목적과 수단을 결정하는 법인, 공공 기관, 에이전시 또는 다른 사람과 독립적으로 또는 공동으로 작업하는 기타 단체입니다.  
- *개인 데이터* 및 *데이터 주체*: 식별되거나 식별 가능한 자연인(데이터 주체)과 관련된 모든 정보. 식별 가능한 자연인은 직접 또는 간접적으로 식별될 수 있는 사람입니다.  
- *프로세서*: 컨트롤러를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 에이전시 또는 기타 단체입니다.  
- *고객 데이터*: 비즈니스 운영의 일상적인 작업에서 생성되고 저장되는 데이터입니다.

## <a name="what-is-a-dsr"></a>DSR이란 무엇인가요?

GDPR(일반 데이터 보호 규정)은 사람들(규정에서 데이터 주체)에게 고용주 또는 다른 유형의 기관이나 조직(데이터 컨트롤러 또는 간단하게 컨트롤러)에 의해 수집된 개인 데이터를 관리할 권한을 제공합니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 제공합니다. 이러한 권한에는 개인 데이터의 복사본을 얻거나, 수정을 요청하거나, 처리를 제한하거나, 삭제하거나, 다른 관리자에게 전달할 수 있도록 전자 형식으로 개인 데이터를 수신할 권한이 포함됩니다.

캘리포니아 소비자 개인 정보 보호법(CCPA)은 캘리포니아 소비자에게 GDPR의 데이터 주체 권리와 유사한 권리를 포함하여, 소비자의 개인 정보 삭제, 액세스 및 수신(이식성)과 같은 개인 정보 보호 권리 및 의무를 제공합니다.  

컨트롤러는 요청된 조치를 취하거나 DSR을 컨트롤러가 수용할 수 없는 이유에 대한 설명을 제공함으로써 각 DSR을 즉시 고려하고 실질적인 응답을 제공해야 합니다. 컨트롤러는 주어진 DSR의 적절한 처분과 관련하여 자체 법률 또는 준수 고문과 상의해야 합니다.

조직의 GDPR 준수 규칙에 따라 여러 프로세스가 DSR 완료하는 데 연관될 수 있습니다.
  
- **검색**. DSR을 완료하는 데 필요한 데이터를 결정하는 프로세스
- **액세스**. 검색된 정보의 데이터 주체에 대한 검색 및 잠재적 전송
- **수정**. 변경 또는 기타 요청된 개인 데이터 변경 사항을 구현합니다.
- **제한**. 액세스를 제한하거나 Microsoft 클라우드에서 데이터를 제거하여 개인 데이터의 액세스 또는 처리를 변경합니다.
- **내보내기**. GDPR의 "데이터 이식성(data-portability)"에서 제공하는 바와 같이 개인 데이터의 "구조화되고 일반적으로 사용되는 컴퓨터가 읽을 수 있는 형식"을 데이터 주체에 제공합니다.
- **삭제**. Microsoft 클라우드에서 개인 데이터를 영구적으로 제거합니다.

## <a name="specific-dsr-considerations"></a>특정 DSR 고려 사항

### <a name="insights-generated-by-microsoft-products-or-services"></a>Microsoft 제품 또는 서비스에서 생성된 인사이트

[인사이트](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)는 서비스(MyAnalytics 등)를 통해 생성될 수 있습니다. Office 365에는 사용자와 조직이 사용하는 인사이트를 제공하는 온라인 서비스가 포함되어 있습니다. 이러한 서비스에서 생성된 데이터를 통해 DSR과 관련된 개인 데이터가 생성될 수 있습니다. 서비스 관련 DSR 프로세스에 대한 자세한 내용은 아래 목록에 있는 링크를 참조하세요.  

### <a name="dsrs-for-system-generated-logs"></a>시스템 생성 로그용 DSRs

Microsoft에서 생성한 로그 및 관련 데이터는 GDPR의 "개인 데이터" 정의 하에 개인으로 간주되는 데이터가 포함될 수 있습니다. 시스템 생성 로그에서 데이터를 제한하거나 수정하는 기능은 지원되지 않습니다. 시스템 생성 로그의 데이터는 Microsoft 클라우드 및 진단 데이터 내에서 수행되는 실제 작업으로 구성되며, 이러한 데이터를 수정하면 작업의 기록 데이터가 손상되어 사기 및 보안 위험이 높아질 수 있습니다. Microsoft는 DSR을 완료하는 데 필요한 시스템 생성 로그에 액세스하고, 내보내고, 삭제할 수 있는 기능을 제공합니다. 예를 들어 다음과 같은 데이터가 있을 수 있습니다.  

- 사용자 활동 로그와 같은 제품 및 서비스 사용 데이터
- 사용자 검색 요청 및 쿼리 데이터
- 시스템 기능 및 사용자나 기타 시스템의 상호 작용으로 발생한 제품 및 서비스에서 생성된 데이터  

### <a name="yammer-and-kaizala"></a>Yammer 및 Kaizala

사용자 계정을 삭제해도 Yammer 및 Kaizala에 대한 시스템 생성 로그는 제거되지 않습니다. 이러한 응용 프로그램에서 데이터를 제거하려면 다음 리소스 중 하나를 참조합니다.

- [Yammer Enterprise에서 GDPR 데이터 주체 요청 관리](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [Kaizala에서 사용자의 조직 데이터 내보내기 또는 삭제](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a>국가별 클라우드

일부 국가 클라우드에서는 전역 IT 관리자가 시스템 생성 로그를 삭제해야 합니다.

### <a name="microsoft-services"></a>Microsoft 서비스

조직이나 사용자가 Microsoft 제품 및 서비스와 관련된 지원을 받기 위해 Microsoft와 함께하는 경우 이 데이터 중 일부는 개인 데이터를 포함할 수 있습니다. 자세한 내용은 [GDPR에 대한 Microsoft 고객 지원 및 전문 서비스 데이터 주체 요청](gdpr-dsr-prof-services.md)을 참조하세요.

### <a name="microsoft-controller-products"></a>Microsoft 컨트롤러 제품

경우에 따라 조직의 사용자가 Microsoft가 데이터 컨트롤러인 Microsoft 제품 또는 서비스에 액세스 할 수 있습니다. 그러한 경우 사용자는 자신의 DSR을 Microsoft에 직접 시작해야 하며 Microsoft는 사용자에게 직접 요청을 수행합니다.

### <a name="third-party-products"></a>타사 제품

Microsoft 계정 인증을 통해 액세스되는 타사 제품 및 서비스의 경우 데이터 주체 요청은 해당 타사로 전달되어야 합니다.

## <a name="data-subject-request-admin-tools"></a>데이터 주체 요청 관리 도구

- **보안 및 준수 센터**: [보안 및 준수 센터](https://aka.ms/stpsecurityandcompliance) 또는 응용 프로그램 내 기능을 통해 사용자 생성 데이터를 내보냅니다.
- **Azure AD 관리 센터**: [Azure AD 관리 센터](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/Allusers/menuId/)를 사용하여 Azure Active Directory 및 관련 서비스에서 데이터 주제를 삭제합니다.
- **Microsoft 데이터 로그 내보내기**: 시스템 생성 로그는 테넌트 관리자가 Azure에 호스트된 [Microsoft 데이터 로그 내보내기](https://aka.ms/MicrosoftGDPR)를 사용하여 내보낼 수 있습니다.

## <a name="learn-more"></a>자세히 알아보기

- [Microsoft 보안 센터](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
