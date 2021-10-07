---
title: Microsoft 365의 공동 작업 관리
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Microsoft 애플리케이션 거버넌스 기능을 구현하여 애플리케이션을 관리합니다.
ms.openlocfilehash: ca1a77c4f5a1543a000b563dde98238136b3115d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189552"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Microsoft Cloud App Security에 대한 애플리케이션 거버넌스 추가 항목(미리 보기)

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

> [!NOTE]
> 앱 거버넌스에 등록하려면 [앱 거버넌스 시작(미리 보기)](app-governance-get-started.md)을 참조하세요.

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

## <a name="a-first-glimpse-at-app-governance"></a>애플리케이션 거버넌스를 한눈에 확인

앱 거버넌스 대시보드를 보려면 [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance)(으)로 이동합니다. 앱 거버넌스 데이터를 보려면 로그인 계정에 [관리자 역할](app-governance-get-started.md#administrator-roles) 중 하나가 있어야 합니다.

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

앱 거버넌스는 Microsoft Cloud App Security 및 Microsoft 365 Defender에 경고를 보내고 Microsoft Cloud App Security 경고를 수신하여 앱 기반 보안 인시던트를 보다 자세히 분석할 수 있도록 합니다.
- 앱 거버넌스 경고는 감지 원본 필드가 "앱 거버넌스"로 설정된 경고로 Microsoft 365 Defender 경고 목록에 표시됩니다.
- 앱 거버넌스 경고는 MCAS 경고 목록에 정책 필드가 다음 중 하나로 설정된 경고로 표시됩니다.
  - Microsoft 365 OAuth 앱 거버넌스
  - Microsoft 365 OAuth 피싱 감지
  - Microsoft 365 OAuth 앱 평판
- MCAS 경고는 앱 거버넌스 경고 목록에 소스가 MCAS로 설정된 경고로 표시됩니다.

> [!NOTE]
> 경고 상태는 현재 앱 거버넌스와 Microsoft Cloud App Security 간에 동기화되고 있지 않습니다.
