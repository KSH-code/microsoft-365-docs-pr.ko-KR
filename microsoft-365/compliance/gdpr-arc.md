---
title: GDPR에 대한 책임 준비 상태 검사 목록
description: 이 문서에서는 Microsoft 제품 및 서비스를 사용할 때 GDPR을 지원하기 위한 정보에 액세스하는 책임 준비 상태 점검 목록에 대해 알아봅니다.
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR
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
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 6952545060a524ef92af6e1e7a063da7091b0860
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214813"
---
# <a name="support-your-gdpr-program-with-accountability-readiness-checklists"></a>책임 준비 상태 검사 목록으로 GDPR 프로그램 지원

GDPR(일반 데이터 보호 규제)는 EU(유럽 연합) 회원국 국민에게 제품과 서비스를 제공하거나 귀하 또는 귀사가 어디에 있는지 관계없이 EU 거주자의 데이터를 수집하고 분석하는 조직에 새로운 규칙을 도입합니다.  추가 세부 정보는 [GDPR 요약 항목](gdpr.md)에 있습니다.

## <a name="accountability-readiness-checklists"></a>책임 준비 상태 검사 목록

Microsoft 제품 및 서비스를 사용할 때 GDPR을 지원하는 데 필요한 정보에 편리하게 액세스할 수 있도록 책임 준비 상태 점검 목록이 제공됩니다. 검사 목록에는 GDPR 하에 발생할 수 있는 잠재적 의무를 열거하고 조직의 준수를 지원하는 데 사용할 수 있는 정보가 표시됩니다.

4개의 Microsoft 제품 및 서비스 제품군에 대한 특정 지침이 있습니다.

- [Office 365](gdpr-arc-Office365.md)
- [Dynamics 365](gdpr-arc-Dynamics365.md)
- [Azure](gdpr-arc-Azure.md)
- [Microsoft 지원 및 전문 서비스](gdpr-arc-prof-services.md)

GDPR 타일의 고객 관리 컨트롤에서 컨트롤 ID 및 컨트롤 제목을 참조하여 [준수 관리자](compliance-manager.md)를 통해 이 검사 목록의 항목을 관리할 수 있습니다.

검사 목록에는 아래 나열된 GDPR을 지원하는 개인 정보 보호 프로그램에 대한 4가지 기본 고려 사항 범주와 예제 요구 사항이 포함됩니다.

1. 데이터 수집 및 처리 조건

    - 동의 획득 시기는 언제인가요?  
    - 목적 식별 및 문서화  
    - 개인 정보 보호 영향 평가

2. 데이터 주체 권리  

    - PII 보안 주체(데이터 주체)의 정보 결정  
    - 동의를 수정하거나 철회하는 메커니즘 제공

3. 기본적으로 계획적인 개인 정보 보호  

    - 수집 제한  
    - 식별 수준 준수  
    - 임시 파일

4. 데이터 보호 및 보안  

    - 조직 및 컨텍스트 이해  
    - 계획  
    - 정보 보안 정책

## <a name="customer-agreements"></a>고객 계약

- **온라인 서비스 약관**: [온라인 서비스 약관](https://go.microsoft.com/fwlink/p/?linkid=2052208)에서 GDPR과 관련된 Microsoft 계약 조항을 찾을 수 있습니다.
- **Microsoft 제품 약관**: Microsoft는 모든 볼룸 라이선스 고객으로 [GDPR 조항 약정](https://go.microsoft.com/fwlink/p/?linkid=2052213)을 확장합니다.
- **데이터 보호 부록**: Microsoft 서비스는 Microsoft 컨설팅 서비스 고객과 기타 고객으로 [이러한 약정을 확장](https://go.microsoft.com/fwlink/p/?linkid=2052215)합니다.

## <a name="gdpr-compliance-controls"></a>GDPR 규정 준수 제어

- **준수 관리자 사용**: Microsoft에서 [준수 관리자](compliance-manager.md)를 사용하여 GDPR 의무 지원하기 위한 검토 및 통합 제어입니다.
- **GDPR 제어 맵핑**: Microsoft의 GDPR 규정 준수 제어의 [포괄적인 맵핑](https://go.microsoft.com/fwlink/p/?linkid=2052220)에 액세스합니다.

## <a name="records-of-processing-for-processors"></a>프로세서에 대한 처리 기록

당사가 컨트롤러 고객에게 프로세서로서 제공하는 온라인 서비스의 규모와 폭 때문에, 당사는 고객이 처리 기록을 추구하는 서비스를 식별하고 당사가 제공하는 온라인 도구에서 관련 로그를 검색할 것으로 기대합니다. 예를 들어 고객이 어떤 유형의 처리 활동을 추구하는지 확인하기 위한 Azure에 대한 처리 기록에 대한 것입니다.

### <a name="azure-logs"></a>Azure 로그

일반적으로 고객은 활동 로그 및 잠재적으로는 진단 로그에 관심을 가질 수 있습니다.

- **활동 로그**: [활동 로그](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)는 구독의 리소스에서 수행되는 작업에 대한 통찰력을 제공합니다. 활동 로그는 작업의 개시자, 발생 시간 및 상태를 결정하는 데 도움이 될 수 있습니다.
- **진단 로그**: [진단 로그](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)는 모든 리소스에서 내보낸 모든 로그입니다. 이러한 로그에는 Windows 이벤트 시스템 로그, Azure 저장소 로그, Key Vault 감사 로그, 응용 프로그램 게이트웨이 액세스 및 방화벽 로그가 포함됩니다.
- **로그 보관**: 모든 진단 로그는 아카이브를 위해 중앙 집중식 및 암호화된 Azure 저장 계정에 기록합니다. 보존 기간은 최대 730일로 사용자 구성이 가능하여 조직별 보존 요건을 충족합니다. 이러한 로그는 Azure 모니터링 로그에 연결되어 대시보드 보고를 처리, 저장 및 관리합니다.

### <a name="other-logs"></a>기타 로그

또한 다음 모니터링 솔루션이 이 아키텍처의 일부로 설치됩니다. 고객의 책임은 FedRAMP 보안 제어에 맞게 이러한 솔루션을 구성하는 것입니다.

- [AD 평가](https://docs.microsoft.com/azure/azure-monitor/insights/ad-assessment): Active Directory 상태 검사 솔루션은 정기적으로 서버 환경의 위험과 상태를 평가하고 배포된 서버 인프라에 특화된 권장 사항의 우선 순위를 제공합니다.
- [맬웨어 방지 평가](https://docs.microsoft.com/azure/security-center/security-center-services?tabs=features-windows#supported-endpoint-protection-solutions-): 맬웨어 방지 솔루션은 악성코드, 위협 및 보호 상태에 대해 보고합니다.
- [Azure 자동화](https://docs.microsoft.com/azure/automation/automation-hybrid-runbook-worker): Azure 자동화 솔루션은 runbook을 저장 및 실행하고 관리합니다.
- [보안 및 감사](https://docs.microsoft.com/azure/security-center/security-center-introduction): 보안 및 감사 대시보드는 보안 도메인, 주요 문제, 탐지, 위협 인텔리전스 및 일반적인 보안 쿼리에 대한 메트릭을 제공하여 리소스의 보안 상태에 대한 높은 수준의 통찰력을 제공합니다.
- [SQL 평가](https://docs.microsoft.com/azure/azure-monitor/insights/sql-assessment): SQL 상태 검사 솔루션은 정기적으로 서버 환경의 위험과 상태를 평가하고 고객에게 배포된 서버 인프라에 특화된 권장 사항의 우선 순위를 제공합니다.
- [업데이트 관리](https://docs.microsoft.com/azure/automation/update-management/update-mgmt-overview): 업데이트 관리 솔루션을 사용하면 사용 가능한 업데이트의 상태 및 필요한 업데이트를 설치하는 과정을 포함한 운영 체제 보안 업데이트의 고객 관리가 가능합니다.
- [에이전트 상태](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth): 에이전트 상태 솔루션은 얼마나 많은 에이전트가 배치되고 그들의 지리적 분포와 응답하지 않는 에이전트의 수와 운영 데이터를 제출하는 에이전트의 수를 보고합니다.
- [Azure 활동 로그](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log): 활동 로그 분석 솔루션은 고객에 대한 모든 Azure 구독에 걸친 Azure 활동 로그를 분석하는 데 도움을 줍니다.
- [변경 내용 추적](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log): 변경 내용 추적 솔루션을 사용하면 고객이 환경의 변화를 쉽게 파악할 수 있습니다.

Azure의 기술 및 보안 조치에 대한 자세한 내용은 컨트롤러 고객이 [Azure 보안 문서](https://docs.microsoft.com/azure/security/)를 방문해야 합니다. Microsoft는 고객 데이터가 개인 데이터인지 여부를 알 수 없기 때문에 Azure는 모든 고객 데이터를 개인 데이터로 처리하므로 고객은 모든 관련 자료가 관련 대상인 것으로 생각할 수 있습니다.

### <a name="processor-information"></a>프로세서 정보

고객이 프로세서에 대한 정보 처리 기록이 필요할 수 있는 또 다른 제품은 Office 365입니다. Office 365와 관련된 정보를 보려면 [보안 및 준수 센터에서 감사 로그 검색](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 문서를 참조하세요.

보안 및 준수 센터를 사용하여 Dynamics 365에 대한 정보를 볼 수도 있습니다.  보안 및 준수 센터 페이지를 보려면 올바른 라이선스가 있는지 확인합니다. [보안 및 준수 센터 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) 문서를 사용하여 라이선스에 대해 자세히 알아보세요. Dynamics 365 이벤트를 검색하려면 [보안 및 준수 센터](https://protection.office.com/unifiedauditlog)에서 통합 감사 로그를 참조하세요.

### <a name="professional-services-information"></a>전문 서비스 정보

전문 서비스의 경우, 고객이 제공한 전문 서비스 지원 데이터가 고객의 대리인에 의해 지원 엔지니어에게 제공됩니다.  이는 고객이 온라인 제품 포털, 서비스 허브 또는 휴대폰을 통해 서비스 요청을 제출할 때 발생할 수 있습니다.

이 정보는 CRM 시스템에 저장되며 다음 목적으로만 사용됩니다.

- 기술 지원, 전문 기획, 조언, 안내, 데이터 마이그레이션, 배포 및 솔루션/소프트웨어 개발 서비스를 제공하는 등 전문 서비스 제공.  
- 문제 해결(보안 사고를 포함한 문제 예방, 탐지, 조사, 완화 및 복구) 및 
- 지속적인 개선(최신 업데이트를 설치하고 신뢰성, 효율, 품질 및 보안을 개선하는 등 전문 서비스 유지). 

지원 운영의 규모로 인해 Microsoft는 제품 그룹 기반 CRM 시스템을 운영합니다. 처리 기록은 해당 시스템에 포함됩니다.
처리 기록은 CRM 시스템 내에서 유지 관리되는 레코드에 반영됩니다.  대부분의 경우 서비스 요청 기록은 포털 또는 서비스 허브에서 확인할 수 있습니다.
포털에서 사용할 수 없는 특정 세부 정보 또는 데이터 처리에 대한 다른 질문에 대해서는 기술 계정 관리자에게 문의하거나 [Microsoft 기술 지원](https://support.microsoft.com/contactus/)에 문의하세요.

## <a name="learn-more"></a>자세히 알아보기

- [Microsoft 보안 센터](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
