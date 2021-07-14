---
title: Microsoft 365의 공동 작업 관리
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Microsoft 애플리케이션 거버넌스 기능을 구현하여 애플리케이션을 관리합니다.
ms.openlocfilehash: 63bd6684bc041c3c82ba6b8ddcc28c2600182b26
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430699"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Microsoft Cloud App Security에 대한 애플리케이션 거버넌스 추가 항목(미리 보기)

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

사이버 공격은 온-프레미스 및 클라우드 인프라에 배포한 앱을 악용하는 방식에서 점점 더 정교해지며 권한 상승, 측면 이동 및 데이터 유출을 위한 출발점이 됩니다. 잠재적인 위험을 파악하고 이러한 유형의 공격을 차단하려면 앱 규정 준수 상태를 명확히 파악하여 앱이 비정상적인 동작을 보이는 시기를 신속하게 식별하고 이러한 동작이 환경, 데이터 및 사용자에게 위험을 줄 때 대응해야 합니다.

Microsoft Cloud App Security의 앱 거버넌스 추가 기능은 Microsoft Graph API를 통해 Microsoft 365 데이터에 액세스하는 OAuth 지원 앱용으로 설계된 보안 및 정책 관리 기능입니다. 애플리케이션 거버넌스는 실행 가능한 인사이트와 자동화된 정책 경고 및 작업을 통해 이러한 애플리케이션과 사용자가 Microsoft 365에 저장된 중요 데이터에 액세스, 사용 및 공유하는 방법에 대한 완벽한 가시성, 문제 해결 및 거버넌스를 제공합니다.

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

애플리케이션 거버넌스는 다음과 같은 포괄적인 기능을 제공합니다.

- **인사이트**: 단일 대시보드에서 테넌트에 있는 Microsoft 365 플랫폼에 대한 모든 타사 앱 보기를 확인하세요. 모든 앱의 상태 및 경고 활동을 확인하고 이에 반응하거나 응답할 수 있습니다.
- **거버넌스**: 애플리케이션 및 사용자 패턴과 동작에 대한 사전 예방적 또는 사후 대응적 정책을 생성하고, 사용자가 비준수 또는 악성 애플리케이션을 사용하지 못하도록 보호하고 위험한 애플리케이션에 대한 액세스를 데이터에 제한하세요.
- **탐지**: 앱 작업에 이상 징후가 있고 비준수, 악성 또는 위험한 앱을 사용하는 경우 경고 및 알림을 받습니다.
- **업데이트 적용**: 업데이트 적용 기능과 함께 업데이트 적용 컨트롤을 사용하여 비정상적인 앱 작업 탐지에 적시 대응하세요.

애플리케이션 거버넌스는 Microsoft 365 애플리케이션 에코시스템에서 필수적인 플랫폼 기반 솔루션입니다. 애플리케이션 거버넌스는 Azure AD(Azure Active Directory)에 등록된 OAuth 지원 애플리케이션을 감독 및 관리하고 Microsoft Graph API를 통해 데이터에 액세스합니다. 애플리케이션 거버넌스는 IT 인프라의 보안 및 규정 준수 상태를 강화하는 데 도움이 되는 애플리케이션 동작 제어 기능을 제공합니다.

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a>애플리케이션 거버넌스를 한눈에 확인

애플리케이션 거버넌스 대시보드를 보려면 [https://aka.ms/appgovernance](https://aka.ms/appgovernance)(으)로 이동하세요. 앱 거버넌스 데이터를 보려면 로그인 계정에 [ 관리자 역할 ](app-governance-get-started.md#administrator-roles) 중 하나가 있어야 합니다.

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a>애플리케이션 거버넌스를 Azure AD 및 Microsoft Cloud App Security와 통합합니다.

애플리케이션 거버넌스, Azure AD 및 Microsoft Cloud App Security는 서로 다른 데이터 집합을 수집하여 제공합니다.

- App Governance는 API 레벨에서 앱의 활동에 대한 자세한 정보를 제공합니다.
- Azure AD는 앱 로그인에 대한 기본 앱 메타데이터와 세부 정보를 제공합니다.
- Microsoft Cloud App Security는 앱 위험 정보를 제공합니다.

앱 거버넌스, Azure AD 및 Microsoft Cloud App Security 전반에서 정보를 공유하면 한 포털에 집계 정보를 표시하고 다른 포털에 연결하여 자세한 정보를 확인할 수 있습니다. 다음은 몇 가지 예입니다.

- 애플리케이션 거버넌스의 애플리케이션 로그인 정보:

  애플리케이션 거버넌스 포털에서 각 애플리케이션에 대해 집계된 로그인 작업을 확인하고 Azure Active Directory 관리 센터에 다시 연결하여 로그인 이벤트에 대한 세부 정보를 확인할 수 있습니다.

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- Microsoft Cloud App Security 포털의 API 사용량 정보:

  Microsoft Cloud App Security 포털에서 API 사용 수준 및 Aggregate 데이터 전송을 확인하고 애플리케이션 거버넌스 포털에 연결하여 자세한 내용을 확인할 수 있습니다.

다음은 통합에 대한 요약입니다.

![애플리케이션 거버넌스를 Azure AD 및 Microsoft Cloud App Security와 통합합니다.](..\media\manage-app-protection-governance\mapg-integration.png)

또한 애플리케이션 거버넌스는 Microsoft Cloud App Security 및 Microsoft 365 Defender에 알림을 보내고, 애플리케이션 거버넌스는 Microsoft Cloud App Security로부터 알림을 수신하여 애플리케이션 기반 보안 문제를 보다 상세하게 분석할 수 있도록 지원합니다.

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->

## <a name="using-app-governance"></a>앱 거버넌스 사용

애플리케이션 거버넌스를 사용하여 잠재적으로 악의적이거나 잘못된 애플리케이션으로부터 테넌트 및 테넌트 데이터를 보호하는 것은 다음 세 가지 핵심 기능에 속합니다.

| 기능 | 설명 |
|:-------|:-----|
| [애플리케이션 가시성 및 인사이트](app-governance-visibility-insights-overview.md) | 테넌트에 있는 Microsoft 365 애플리케이션의 트래픽 및 작업을 모든 각도에서 확인할 수 있습니다. |
| [향상된 거버넌스를 위한 애플리케이션 정책](app-governance-app-policies-overview.md) | 사전 예방적 또는 사후 대응적 애플리케이션 정책을 생성하여 Microsoft 3635 애플리케이션에 대한 거버넌스를 적용할 수 있습니다. |
| [탐지 및 업데이트 적용](app-governance-detect-remediate-overview.md) | 플랫폼 탐지 경고 또는 정책 생성 탐지 경고를 기반으로 앱의 비정상적인 앱 동작을 모니터링하고 앱 정책 설정에 따라 자동으로 또는 수동으로 업데이트를 적용합니다. |
|||
