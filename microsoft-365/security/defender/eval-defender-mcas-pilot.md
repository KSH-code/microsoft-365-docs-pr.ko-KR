---
title: 파일럿 Microsoft Cloud App Security 파일럿 Microsoft 365 Defender
description: 장치, Microsoft 365 Defender, 데이터 및 응용 프로그램을 보호하도록 설계된 보안 솔루션을 테스트하고 경험할 수 있도록 테스트 테스트 랩 또는 파일럿 환경을 설정하세요.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d0d452c0e9a5dbc3a9060c42921f180da7c42b90
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189259"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a>파일럿 Microsoft Cloud App Security 파일럿 Microsoft 365 Defender


**적용 대상:**
- Microsoft 365 Defender

이 문서는 사용자 환경의 평가 환경을 설정하는 프로세스의 [3단계](eval-defender-mcas-overview.md) 중 Microsoft Cloud App Security. 이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-mcas-overview.md)

다음 단계에 따라 파일럿을 설정하고 구성하여 파일럿을 Microsoft Cloud App Security.


![파일럿을 수행하기 위한 Microsoft Cloud App Security.](../../media/defender/m365-defender-mcas-pilot-steps.png)

- 1단계. [파일럿 그룹 만들기 - 특정 사용자 그룹으로 파일럿 배포 범위 지정](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [2단계. 보호 구성 - 조건부 액세스 앱 제어](#step-2-configure-protection--conditional-access-app-control)
- [3단계. 기능 사용 - 환경 보호를 위한 자습서를 진행합니다.](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a>1단계. 파일럿 그룹 만들기 - 특정 사용자 그룹으로 파일럿 배포 범위 지정

Microsoft Cloud App Security 배포 범위를 지정하는 데 사용할 수 있습니다. 스코어를 사용하면 앱에 대해 모니터링하거나 모니터링에서 제외할 특정 사용자 그룹을 선택할 수 있습니다. 사용자 그룹을 포함하거나 제외할 수 있습니다. 파일럿 배포의 범위를 지정하기 위해 [범위가 지정한 배포를 참조합니다.](/cloud-app-security/scoped-deployment)


## <a name="step-2-configure-protection--conditional-access-app-control"></a>2단계. 보호 구성 - 조건부 액세스 앱 제어

구성할 수 있는 가장 강력한 보호 중 하나는 조건부 액세스 앱 제어입니다. 이를 위해서는 Azure AD(Azure Active Directory 통합해야 합니다. 이를 통해 관련 정책(예: 정상 디바이스 요구)을 비롯한 조건부 액세스 정책을 승인된 클라우드 앱에 적용할 수 있습니다. 

Microsoft Cloud App Security 사용하여 SaaS 앱을 관리하는 첫 번째 단계는 이러한 앱을 검색한 다음 Azure AD 테넌트에 추가하는 것입니다. 검색에 도움이 필요한 경우 [네트워크에서 SaaS 앱](/cloud-app-security/tutorial-shadow-it)검색 및 관리를 참조하세요. 앱을 검색한 후 Azure AD 테넌트에 [추가합니다.](/azure/active-directory/manage-apps/add-application-portal)

다음을 수행하여 이러한 관리 작업을 시작할 수 있습니다.

- 먼저 Azure AD에서 새 조건부 액세스 정책을 만들고 "조건부 액세스 앱 제어 사용"으로 구성합니다. 그러면 요청이 Cloud App Security. 하나의 정책을 만들고 모든 SaaS 앱을 이 정책에 추가할 수 있습니다.
- 다음으로, Cloud App Security 세션 정책을 생성합니다. 적용할 각 컨트롤에 대해 정책을 하나씩 만들어야 합니다.

지원되는 앱 및 클라이언트를 비롯한 자세한 내용은 조건부 액세스 앱 제어로 Microsoft Cloud App Security [보호를 참조하세요.](/cloud-app-security/proxy-intro-aad) 

예를 들어 정책은 [SaaS 앱에 Microsoft Cloud App Security 권장 정책을 참조하세요.](../office-365-security/mcas-saas-access-policies.md) 이러한 정책은 모든 [](../office-365-security/microsoft-365-policies-configurations.md) 고객에게 시작점으로 권장되는 공통 ID 및 장치 액세스 정책 집합을 사용합니다. 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a>3단계. 기능 사용 - 환경 보호를 위한 자습서를 진행합니다. 

이 Microsoft Cloud App Security 설명서에는 위험을 검색하고 환경을 보호하는 데 도움이 되는 일련의 자습서가 포함되어 있습니다. 

다음 자습서를 Cloud App Security 사용해 보아야 합니다.

- [의심스러운 사용자 활동 감지](/cloud-app-security/tutorial-suspicious-activity)
- [위험한 사용자 조사](/cloud-app-security/tutorial-ueba)
- [위험한 OAuth 앱 조사](/cloud-app-security/investigate-risky-oauth)
- [중요한 정보 검색 및 보호](/cloud-app-security/tutorial-dlp)
- [실시간으로 조직의 모든 앱 보호](/cloud-app-security/tutorial-proxy)
- [중요한 정보 다운로드 차단](/cloud-app-security/use-case-proxy-block-session-aad)
- [관리자를 통해 파일 보호](/cloud-app-security/use-case-admin-quarantine)
- [위험한 작업 시 단계별 인증 필요](/cloud-app-security/tutorial-step-up-authentication)

데이터 검색의 고급 헌팅에 Microsoft Cloud App Security 자세한 내용은 비디오를 [참조하세요.](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa)

## <a name="next-steps"></a>다음 단계

[파일럿 환경에서 파일럿 Microsoft 365 Defender 사용하여 조사 및 대응](eval-defender-investigate-respond.md)

평가용 [개요로 Microsoft Cloud App Security](eval-defender-mcas-overview.md)

평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)
