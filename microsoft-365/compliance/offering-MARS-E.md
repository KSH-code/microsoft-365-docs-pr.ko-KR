---
title: 거래소에 대한 최소 허용 위험 표준 (MARS-E) 2.0 프레임워크
description: Microsoft는 미국의 거래소에 대한 최소 허용 위험 표준 (MARS-E)을 준수합니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 27ef305d8f8df0469ec4d6d5f98b5c96127f0387
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859608"
---
# <a name="minimum-acceptable-risk-standards-for-exchanges-mars-e-20-framework"></a>거래소에 대한 최소 허용 위험 표준 (MARS-E) 2.0 프레임워크

## <a name="mars-e-20-framework-overview"></a>MARS-E 2.0 프레임워크의 개요

2012년, Medicare 및 Medicaid 서비스 센터 (CMS)는 CMS 정보 보안 및 개인 정보 보호 프로그램에 따라 거래소에 대한 최소 허용 위험 표준 (MARS-E)을 발표했습니다. 지침, 요구 사항 및 서식 파일을 포함 하는 문서 제품군은 환자보호 및 부담적정보험법 (ACA)및 ACA에 적용되는 보건복지부 규정을 다루기 위해 고안되었습니다. NIST (National Institute of Standards and Technology) 특별 간행물 800-53은 ACA에서 규정한 건강 정보 교환 및 마켓플레이스간의 모든 시스템, 인터페이스 및 연결에 대한 보안 및 준수 요구 사항을 설정하는 상위 프레임워크 역할을 합니다.

MARS-E가 출시된 후 NIST는 응용 프로그램 보안을 포함하여 온라인 보안에 대해 증가하는 문제를 해결하기 위해 특별 간행물 800-53r4 업데이트를 발표했습니다. 여기에는 내부자 및 고급 영구적 위협; 공급망 위험; 모바일 및 클라우드 컴퓨팅 시스템의 신뢰성, 보증 및 복원력이 포함됩니다. 그런 다음 CMS는 MARS-E 프레임워크를 개정하여 2015년 MARS-E 2.0을 게시하여 NIST 800.53r4의 업데이트된 컨트롤 및 매개 변수와 일치하도록 했습니다.

이 업데이트에서는 개인 식별이 가능한 정보, 보호된 건강 정보 및 연방 납세 정보를 포함하여 보호되는 데이터에 대해 거래소에서의 기밀성, 무결성 및 가용성을 다룹니다. MARS-E 2.0 프레임워크는 이러한 보호된 데이터를 보호하는 것을 목표로 하며 거래소, 마켓플레이스 (연방, 주, 주 Medicaid 또는 어린이 건강 보험 프로그램 (CHIP) 에이전시) 및 지원 계약자를 포함한 모든 ACA 관리 기관에 적용됩니다.

## <a name="microsoft-and-mars-e-20-framework"></a>Microsoft와 MARS-E 2.0 프레임워크

현재 MARS-E에 대한 공식적인 승인 및 인증 프로세스는 없습니다. 그러나 Microsoft Azure 플랫폼 서비스는 FedRAMP 감사를 받고 보통 영향 수준으로, Azure Government는 높은 영향 수준으로 평가되었고, 이는 FedRAMP 표준에 따라 부여됩니다. 이러한 표준은 MARS-E에 특별히 초점을 맞추지는 않지만 MARS-E 컨트롤 요구 사항과 목표가 면밀하게 부합하는 면이 있어 Azure에서 데이터의 기밀성, 무결성 및 가용성을 보호하기 위해 제공됩니다.

Microsoft 클라우드에서의 MARS-E 2.0 프레임워크의 혜택에 대해 자세히 알아보세요. [MARS-E 배경 설명 다운로드](https://aka.ms/mars-e-backgrounder)

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure 및 Azure Government](https://aka.ms/AzureCompliance)
- Intune

## <a name="audits-reports-and-certificates"></a>감사, 보고서 및 인증서

Microsoft 비즈니스 클라우드 서비스는 매년 FedRAMP 인증 프로세스에 대해 모니터링 및 평가됩니다.

## <a name="frequently-asked-questions"></a>자주하는 질문

**이 표준은 누구에게 적용되나요?**

MARS-E는 거래소 또는 마켓플레이스 (연방, 주, Medicaid, 및 기본 건강 프로그램을 관리하는 CHIP 기관 포함)와 모든 계약 업체 및 하청 업체를 포함한 모든 ACA 관리 기관에 적용됩니다.

**Microsoft는 Azure 및 Azure Government가 이 표준을 준수하는 지를 어떻게 보여줄 수 있나요?**

FedRAMP 인증을 위해 제 3자가 준비한 정식 감사 보고서를 사용하여, Microsoft는 이러한 보고서 내에서 MARS-E 보안 및 개인 정보 컨트롤 요구 사항을 충족하는 Azure 기능을 보여줌으로서 관련 컨트롤이 무엇인지 보여줄 수 있습니다. Microsoft에서 구현한 감사 통제 수단은 Azure 플랫폼에 저장된 데이터의 기밀성, 무결성 및 가용성을 보호하고 Microsoft의 책임으로 식별된 MARS-E에 정의된 해당 규제 요건을 준수하는 데 도움이 됩니다.

**이 표준에 따른 규정 준수를 유지하기 위한 Microsoft의 책임은 무엇인가요?**

Microsoft는 Azure 플랫폼이 관리하는 [온라인 서비스 약관](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31) 및 해당 SLA (서비스 수준 계약)에 정의된 조항을 충족함을 보증합니다. 이러한 SLA는 Azure 플랫폼에 대한 보안 유지하고 시스템을 모니터링하기에 적합한 통제 수단을 구현하고 관리하기 위한 Microsoft의 책임을 정의합니다.

**우리 회사에 Microsoft의 MARS-E 규정 준수 자격획득 노력을 사용할 수 있나요?**

예. FedRAMP 표준에 대한 외부 감사 보고서는 Azure 플랫폼의 보안 및 개인 정보 보호 상태를 유지하기 위해 Microsoft에서 구현한 통제 수단의 유효성을 입증합니다. Azure 및 Azure Government 고객은 이러한 관련 보고서에 설명된 감사 통제 수단을 고유의 FedRAMP 및 MARS-E 위험 분석 및 자격 획득을 위한 노력의 일부로 활용할 수 있습니다.

## <a name="resources"></a>리소스

- MARS-E 규정 지침, MARS-E 문서 제품군, 버전 2.0
    - [볼륨 II: 거래소에 대한 최소 허용 위험 표준](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/2-MARS-E-v2-0-Minimum-Acceptable-Risk-Standards-for-Exchanges-11102015.pdf)
    - [볼륨 III: 거래소에 대한 최소 허용 위험 보안 및 개인 정보 컨트롤 카탈로그](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/3-MARS-E-v2-0-Catalog-of-Security-and-Privacy-Controls-11102015.pdf)
- [온라인 서비스용 Microsoft 규정 준수 프레임워크 백서](https://aka.ms/compliance-framework)
- [Microsoft 온라인 서비스 사용 약관](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>제공 사항의 배경 설명 다운로드

이 제공 사항에 대한 배경 설명 문서가 필요한가요? [PDF](https://download.microsoft.com/download/7/C/2/7C2690A7-19CC-4EED-A47A-B43CC418790A/MARS-E-Compliance.pdf)를 다운로드합니다.
