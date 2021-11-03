---
title: 보안 팀이 집에서 작업할 수 있는 상위 12개 작업
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.prod: m365-security
ms.technology: m365d
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: 랜섬웨어, 피싱 및 악의적인 첨부 파일을 포함하여 사이버 위협으로부터 비즈니스 전자 메일 및 데이터를 보호합니다.
ms.openlocfilehash: 071b89bf941bf1c572dc90e9befe6d6c29b33bc5
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724718"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>보안 팀이 집에서 작업할 수 있는 상위 12개 작업

[Microsoft와](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) 같고 갑자기 주 가정 기반 인력을 지원하고 있는 경우 조직이 최대한 안전하게 작업할 수 있도록 지원하기를 원합니다. 이 문서에서는 보안 팀이 가장 중요한 보안 기능을 최대한 빨리 구현할 수 있도록 작업에 우선 순위를 지정합니다.

![집에서 작업을 지원하기 위해 이러한 상위 작업을 수행합니다.](../media/security/security-support-remote-work.png)

Microsoft의 비즈니스 계획 중 하나를 사용하는 중소 규모 조직인 경우 다음 리소스를 대신 참조하세요.

- [비즈니스 계획에 대한 보안 Office 365 Microsoft 365 10가지 방법](../admin/security-and-compliance/secure-your-business-data.md)
- [Microsoft 365 대한 정보(Microsoft 365](../campaigns/index.md) 비즈니스에 대한 권장 보안 구성 포함)

엔터프라이즈 계획을 사용하는 고객의 경우 서비스 계획에 적용되는 다음 표에 나열된 작업을 완료하는 것이 좋습니다. 엔터프라이즈 요금제로 Microsoft 365 대신 구독을 결합하는 경우 다음에 유의하세요.

- Microsoft 365 E3 EMS(Enterprise Mobility + Security) E3 및 Azure AD P1이 포함됩니다.
- Microsoft 365 E5 EMS E5 및 Azure AD P2 포함

****

|단계|작업|모든 Office 365 Enterprise 계획|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1|[Azure AD MFA(다단계 인증) 사용](#1-enable-azure-ad-multi-factor-authentication-mfa)|![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[위협으로부터 보호](#2-protect-against-threats)|![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3 |[Microsoft Defender for Office 365](#3-configure-microsoft-defender-for-office-365)|||![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4|[ID에 맞게 Microsoft Defender 구성](#4-configure-microsoft-defender-for-identity)|||![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5|[Microsoft 365 Defender 켜기](#5-turn-on-microsoft-365-defender)|||![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[휴대폰 및 태블릿에 대한 Intune 모바일 앱 보호 구성](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Intune 앱 보호를 포함하여 게스트에 대한 MFA 및 조건부 액세스 구성](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[장치 관리에 PC 등록 및 호환 PC 필요](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[클라우드 연결에 맞게 네트워크 최적화](#9-optimize-your-network-for-cloud-connectivity)|![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[사용자 교육](#10-train-users)|![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|11 |[Microsoft Cloud App Security 시작](#11-get-started-with-microsoft-cloud-app-security)|||![포함](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12 |[위협 모니터링 및 조치 수행](#12-monitor-for-threats-and-take-action)|![포함.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함](../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

시작하기 전에 보안 [센터에서](./defender/microsoft-secure-score.md) Microsoft 365 보안 점수를 Microsoft 365 합니다. 중앙 집중식 대시보드에서 ID, 데이터, 앱, 장치 및 인프라에 대한 Microsoft 365 모니터링하고 개선할 수 있습니다. 권장 보안 기능을 구성하거나, 보안 관련 작업(예: 보고서 보기)을 수행하거나, 타사 응용 프로그램 또는 소프트웨어를 사용하여 권장 사항을 해결하기 위한 포인트가 부여됩니다. 이 문서의 권장 작업은 점수를 높입니다.

![Microsoft 보안 점수 스크린샷.](../media/secure-score.png)

## <a name="1-enable-azure-ad-multi-factor-authentication-mfa"></a>1: Azure AD MFA(다단계 인증) 사용

집에서 근무하는 직원의 보안을 개선하기 위해 할 수 있는 가장 좋은 한 가지 일은 MFA를 켜는 것입니다. 아직 프로세스가 준비되지 않은 경우 이를 긴급 파일럿으로 취급하고, 정체된 직원을 지원할 준비가 되어 있는지를 확인 합니다. 하드웨어 보안 장치를 배포할 수 없는 경우 생체 인식 및 Windows Hello 같은 스마트폰 인증 앱을 Microsoft Authenticator.

일반적으로 MFA를 요구하기 전에 사용자에게 다단계 인증을 위해 14일간 디바이스를 등록하도록 하는 것이 좋습니다. 그러나 인력이 갑자기 집에서 작업하는 경우 먼저 MFA를 보안 우선 순위로 요구하고 필요한 사용자가 도움을 줄 수 있도록 준비합니다.

이러한 정책을 적용하는 데는 몇 분 정도 걸릴 수 있지만, 며칠 동안 사용자를 지원할 준비가 됩니다.

****

|계획|권장 사항|
|---|---|
|Microsoft 365 계획(Azure AD P1 또는 P2가 없는 경우)|[Azure AD](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)에서 보안 기본값을 사용하도록 설정 합니다. Azure AD의 보안 기본값에는 사용자 및 관리자를 위한 MFA가 포함됩니다.|
|Microsoft 365 E3(Azure AD P1 사용)|[공통 조건부 액세스 정책](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)을 사용하여 다음 정책을 구성합니다. <br/>- [관리자에게 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br/>- [모든 사용자에 대해 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br/> - [레거시 인증 차단](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)|
|Microsoft 365 E5(Azure AD P2 사용)|Azure AD ID 보호를 활용하여 다음 두 정책을 만들어 Microsoft의 [권장 조건부 액세스 및 관련 정책 집합](./office-365-security/identity-access-policies.md)을 구현하세요.<br/> - [로그인 위험이 중간 이상인 경우 MFA 필요](./office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br/>- [최신 인증을 지원하지 않는 클라이언트 차단](./office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br/>- [위험이 높은 사용자는 암호를 변경해야 함](./office-365-security/identity-access-policies.md#high-risk-users-must-change-password)|
|

## <a name="2-protect-against-threats"></a>2: 위협으로부터 보호

모든 Microsoft 365 계획에는 다양한 위협 방지 기능이 포함되어 있습니다. 이러한 기능에 대한 보호 기능을 강화하는 데 몇 분 정도 걸립니다.

- 맬웨어 방지 보호 기능
- 악의적인 URL 및 파일로부터 보호
- 피싱 방지 보호 기능
- 스팸 방지 보호 기능

[시작점으로](office-365-security/protect-against-threats.md) 사용할 Office 365 지침은 보안 위협으로부터 보호를 참조하세요.

## <a name="3-configure-microsoft-defender-for-office-365"></a>3: 사용자에 대해 Microsoft Defender Office 365

microsoft Defender for Office 365 및 Microsoft 365 E5 Office 365 E5 전자 메일 메시지, 링크(URL) 및 공동 작업 도구로 위협되는 악의적인 위협에 대해 조직을 보호합니다. 이 경우 구성하는 데 몇 시간이 걸릴 수 있습니다.

Microsoft Defender for Office 365:

- 첨부 파일 및 악의적인 콘텐츠에 대한 링크를 검사하는 지능형 시스템을 사용하여 알 수 없는 전자 메일 위협으로부터 조직을 실시간으로 보호합니다. 이러한 자동화된 시스템에는 강력한 데이터 분석 플랫폼,추론 및 기계 학습 모델이 포함됩니다.
- 사용자가 팀 사이트 및 문서 라이브러리에서 악성 파일을 식별하고 차단하여 사용자가 파일을 공동 작업하고 공유할 때 조직을 보호합니다.
- 기계 학습 모델 및 고급 가장 감지 알고리즘을 적용하여 피싱 공격을 방지합니다.

계획 요약을 포함한 개요는 에 대한 [Defender for Office 365.](./office-365-security/defender-for-office-365.md)

전역 관리자는 다음 보호를 구성할 수 있습니다.

- [안전한 링크 정책 설정](office-365-security/set-up-safe-links-policies.md)
- [링크의 전역 금고 구성](office-365-security/configure-global-settings-for-safe-links.md)
- [안전한 첨부 파일 정책 설정](office-365-security/set-up-safe-attachments-policies.md)

이러한 워크로드에 대해 Exchange Online 및 SharePoint Online 관리자와 함께 Office 365 구성해야 합니다.

- [Microsoft Defender for Endpoint for SharePoint, OneDrive 및 Microsoft Teams](office-365-security/mdo-for-spo-odb-and-teams.md)

## <a name="4-configure-microsoft-defender-for-identity"></a>4: ID에 맞게 Microsoft Defender 구성

[ID용 Microsoft Defender](/azure-advanced-threat-protection/what-is-atp)는 온-프레미스 Active Directory 신호를 활용하여 조직에서 일어나는 고급 위협, ID 손상 및 악의적인 내부자 작업을 식별, 감지 및 조사하는 클라우드 기반 보안 솔루션입니다. 다음으로 이 단계에 집중합니다. 이는 프레미스 및 클라우드 인프라를 보호하고, 종속성 또는 선행 요구가 없는 것이고, 즉각적인 혜택을 제공할 수 있기 때문에 이 단계에 집중합니다.

- 신속하게 [설치하려면 Microsoft Defender for Identity Quickstarts를](/azure-advanced-threat-protection/install-atp-step1) 참조합니다.
- 비디오 [시청: ID용 Microsoft Defender 소개](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Microsoft [Defender for Identity](/azure-advanced-threat-protection/what-is-atp#whats-next) 배포의 세 단계 검토

## <a name="5-turn-on-microsoft-365-defender"></a>5: 설정 Microsoft 365 Defender

이제 Microsoft Defender for Office 365 ID용 Microsoft Defender를 구성한 후 하나의 대시보드에서 이러한 기능의 결합된 신호를 볼 수 있습니다. [Microsoft 365 Defender](./defender/microsoft-365-defender.md) 경고, 인시던트, 자동화된 조사 및 대응, 고급 헌팅(ID용 Microsoft Defender, Office 365용 Defender, 끝점용 Microsoft Defender 및 Microsoft Cloud App Security)을 단일 창으로 security.microsoft.com [ ](https://security.microsoft.com).

![MTP 대시보드 그림입니다.](../media/top-ten-security-remote-work-mtp-dashboard.png)

서비스용 Defender를 하나 이상 구성한 Office 365 MTP를 켜야 합니다. MTP에 새로운 기능이 지속적으로 추가됩니다. 미리 보기 기능을 받기 위해 옵트인(opt in)을 고려합니다.

- [MTP에 대해 자세히 알아보시다](./defender/microsoft-365-defender.md)
- [MTP 켜기](./defender/m365d-enable.md)
- [미리 보기 기능 옵트인](./defender/preview.md)

## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: 휴대폰 및 태블릿에 대한 Intune 모바일 앱 보호 구성

Microsoft Intune MAM(모바일 응용 프로그램 관리)을 사용하면 이러한 장치를 관리하지 않고도 휴대폰 및 태블릿에서 조직의 데이터를 관리하고 보호할 수 있습니다. 작동 방식은 다음과 같습니다.

- 관리되는 디바이스의 앱과 허용되는 동작을 결정하는 APP(앱 보호 정책)을 만들 수 있습니다(예: 관리되는 앱의 데이터가 관리되지 않는 앱에 복사되지 못하도록 방지). 각 플랫폼(iOS, Android)에 대해 하나의 정책을 만들 수 있습니다.
- 앱 보호 정책을 만들고 나면 Azure AD에서 승인된 앱 및 APP 데이터 보호를 요구하는 조건부 액세스 규칙을 만들어 이러한 정책을 적용합니다.

앱 보호 정책에는 많은 설정이 포함됩니다. 다행히 모든 설정에 대해 알아보고 옵션에 가중치가 를 사용할 필요는 없습니다. Microsoft에서는 시작점을 권장하여 설정 구성을 쉽게 적용할 수 있습니다. 앱 보호 정책을 사용하는 데이터 [보호 프레임워크에는](/mem/intune/apps/app-protection-framework) 선택할 수 있는 세 가지 수준이 포함되어 있습니다.

더욱이 Microsoft는 조건부 액세스 및 관련 정책 집합으로 이 앱 보호 프레임워크를 조정하여 모든 조직이 시작점으로 사용하는 것이 좋습니다. 이 문서의 지침을 사용하여 MFA를 구현한 경우 이 방법의 절반을 사용할 수 있습니다.

모바일 앱 보호를 구성하려면 일반 ID 및 장치 액세스 정책의 [지침을 사용합니다.](./office-365-security/identity-access-policies.md)

 1. APP 데이터 [보호 정책 적용](./office-365-security/identity-access-policies.md#apply-app-data-protection-policies) 지침을 사용하여 iOS 및 Android에 대한 정책을 만들 수 있습니다. 기준 보호를 위해 수준 2(향상된 데이터 보호)를 권장합니다.
 2. 승인된 앱 및 [APP 보호를 요구하는 조건부 액세스 규칙을 생성합니다.](./office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: Intune 모바일 앱 보호를 포함하여 게스트에 대한 MFA 및 조건부 액세스 구성

다음으로, 계속해서 공동 작업하고 게스트와 작업할 수 있도록 하자. Microsoft 365 E3 사용 중일 때 모든 사용자에 대해 MFA를 구현한 경우 설정됩니다.

Microsoft 365 E5 요금제를 사용 중일 때 위험 기반 MFA에 대해 Azure Identity Protection을 활용하는 경우 Azure AD ID 보호가 게스트로 확장되지 않는 것이기 때문에 몇 가지 조정을 해야 합니다.

- 게스트 및 외부 사용자에 대해 MFA를 항상 요구하는 새 조건부 액세스 규칙을 만들 수 있습니다.
- 위험 기반 MFA 조건부 액세스 규칙을 업데이트하여 게스트 및 외부 사용자를 제외합니다.

공용 정책 [](./office-365-security/identity-access-policies-guest-access.md) 업데이트의 지침을 사용하여 게스트 및 외부 액세스를 허용 및 보호하여 게스트 액세스가 Azure AD에서 작동하는 방법을 이해하고 영향을 받는 정책을 업데이트합니다.

만든 Intune 모바일 앱 보호 정책과 승인된 앱 및 APP 보호를 요구하는 조건부 액세스 규칙이 게스트 계정에 적용되어 조직 데이터를 보호하는 데 도움이 됩니다.

> [!NOTE]
> 호환 PC를 요구하기 위해 장치 관리에 PC를 이미 등록한 경우 장치 준수를 적용하는 조건부 액세스 규칙에서 게스트 계정을 제외해야 합니다.

## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: 장치 관리에 PC 등록 및 호환 PC 필요

몇 가지 방법으로 직원의 장치를 등록할 수 있습니다. 각 방법은 장치 소유권(개인 또는 회사), 장치 유형(iOS, Windows, Android) 및 관리 요구 사항(재설정, 선호도, 잠금)에 따라 다릅니다. 이 경우 정렬하는 데 시간이 다소 걸릴 수 있습니다. 에서 [장치 등록을 Microsoft Intune.](/mem/intune/enrollment/)

가장 빠른 방법은 장치용 자동 등록을 설정하는 [Windows 10 것입니다.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

다음 자습서를 활용할 수 있습니다.

- [Autopilot을 사용하여 Intune에서 Windows 장치 등록](/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Apple ABM(Business Manager)에서 Apple의 회사 장치 등록 기능을 사용하여 Intune에서 iOS/iPadOS 장치 등록](/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

장치를 등록한 후 일반 [ID](./office-365-security/identity-access-policies.md) 및 장치 액세스 정책의 지침을 사용하여 이러한 정책을 만들 수 있습니다.

- [장치 준수 정책](./office-365-security/identity-access-policies.md#define-device-compliance-policies) 정의 - 권장되는 설정에는 바이러스 Windows 10 요구하는 것이 포함됩니다. 업데이트가 Microsoft 365 E5 끝점용 Microsoft Defender를 사용하여 직원 디바이스의 상태 모니터링 다른 운영 체제에 대한 준수 정책에 바이러스 백신 보호 및 엔드포인트 보호 소프트웨어가 포함되어 있는지 확인
- [호환 PC 필요](./office-365-security/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) - 장치 준수 정책을 적용하는 Azure AD의 조건부 액세스 규칙입니다.

한 조직만 장치를 관리할 수 있으므로 Azure AD의 조건부 액세스 규칙에서 게스트 계정을 제외해야 합니다. 장치 준수가 필요한 정책에서 게스트 및 외부 사용자를 제외하지 않는 경우 이러한 정책은 이러한 사용자를 차단합니다. 자세한 내용은 공용 정책 업데이트를 참조하여 게스트 및 외부 액세스를 허용하고 [보호합니다.](./office-365-security/identity-access-policies-guest-access.md)

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: 클라우드 연결에 맞게 네트워크 최적화

많은 직원이 빠르게 집에서 일할 수 있도록 하는 경우 이러한 갑작스러운 연결 패턴 전환은 회사 네트워크 인프라에 큰 영향을 줄 수 있습니다. 많은 네트워크가 클라우드 서비스를 채택하기 전에 확장 및 설계했습니다. 대부분의 경우 네트워크는 원격 작업자에 대한 내성적이지만 모든 사용자가 동시에 원격으로 사용되지는 않습니다.

VPN 중앙 집중자, 중앙 네트워크 발신 장비(예: proxies 및 데이터 손실 방지 장치), 중앙 인터넷 대역폭, 백하울 MPLS 회로, NAT 기능 등의 네트워크 요소는 전체 비즈니스를 사용하는 부하로 인해 갑자기 부담이 매우 많이 하게 됩니다. 결과적으로, 집에서 작업하는 데 적응하는 사용자의 경우 성능 및 생산성이 좋지 않은 사용자 환경이 됩니다.

일반적으로 회사 네트워크를 통해 트래픽을 다시 라우팅하여 제공된 보호 중 일부는 사용자가 액세스하는 클라우드 앱에서 제공됩니다. 이 문서의 이 단계에 도달한 경우 서비스 및 데이터에 대한 정교한 클라우드 보안 Microsoft 365 구현했습니다. 이러한 컨트롤이 준비되면 원격 사용자의 트래픽을 해당 컨트롤로 직접 라우팅할 Office 365. 여전히 다른 응용 프로그램에 액세스하기 위한 VPN 링크가 필요한 경우 분할 터널링을 구현하여 성능과 사용자 환경을 크게 개선할 수 있습니다. 조직에서 합의를 이루면 협정 네트워크 팀이 하루 이내에 이 작업을 수행할 수 있습니다.

자세한 내용은 Docs에서 다음 리소스를 참조하세요.

- [개요: VPN 분할 터널링을 사용하여 원격 사용자에 대한 연결 최적화](/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Office 365 VPN 분할 터널링 구현](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

이 항목에 대한 최근 블로그 문서:

- [원격 직원의 트래픽을 빠르게 최적화하고 & 부하를 줄이는 방법](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [보안 전문가와 IT가 오늘날의 고유한 원격 작업 시나리오에서 최신 보안 제어를 달성할 수 있는 다른 방법](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="10-train-users"></a>10: 사용자 교육

사용자를 교육하면 사용자 및 보안 운영 팀에 많은 시간과 좌절을 저장할 수 있습니다. 잘 아는 사용자는 첨부 파일을 열거나 의심스러운 전자 메일 메시지의 링크를 클릭할 가능성이 낮아 의심스러운 웹 사이트를 방지할 가능성이 더 습니다.

하버드 Kennedy [학교](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) 사이버 보안 캠페인 핸드북은 피싱 공격을 식별하기 위한 교육을 포함하여 조직 내에서 강력한 보안 인식 문화를 설정하기 위한 훌륭한 지침을 제공합니다.

Microsoft 365 조직의 사용자에게 알리는 데 도움이 되는 다음 리소스를 제공합니다.

****

|개념|리소스|
|---|---|
|Microsoft 365|[사용자 지정 가능한 학습 경로](/office365/customlearning/) <p>이러한 리소스는 조직의 최종 사용자를 위한 교육을 구성하는 데 도움이 될 수 있습니다.|
|Microsoft 365 보안|[Learning 모듈: 기본 제공 지능형 보안 기능으로 조직을 Microsoft 365](/learn/modules/security-with-microsoft-365) <p>이 모듈에서는 보안 기능이 함께 Microsoft 365 방법을 설명하고 이러한 보안 기능의 이점을 설명할 수 있습니다.|
|다단계 인증|[2단계 인증: 추가 확인 페이지란?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>이 문서는 최종 사용자가 다단계 인증이 무엇일지와 조직에서 사용되는 이유를 이해하는 데 도움이 됩니다.|
|

이 지침 외에도 사용자는 이 문서에 설명된 작업을 수행하여 해커와 맬웨어로부터 계정 및 장치를 [보호하는 것이 좋습니다.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) 이러한 작업은 다음과 같습니다.

- 강력한 암호 사용
- 장치 보호
- 관리되지 않는 Windows 10 및 Mac PC에서 보안 기능 사용

또한 다음 문서에서 권장하는 작업을 수행하여 사용자가 개인 전자 메일 계정을 보호하는 것이 좋습니다.

- [Outlook.com 전자 메일 계정 보호](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [2단계 인증을 사용하여 Gmail 계정 보호](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Microsoft Cloud App Security

[Microsoft Cloud App Security](/cloud-app-security) 풍부한 가시성, 데이터 이동 제어 및 정교한 분석을 통해 모든 클라우드 서비스에서 사이버 위협을 식별하고 퇴치할 수 있습니다. Cloud App Security 시작하면 이상 검색 정책이 자동으로 사용되지만 Cloud App Security 동안 7일의 초기 학습 기간이 있습니다. 이 기간 동안 모든 이상 검색 알림이 발생하지는 않습니다.

지금 Cloud App Security 시작하세요. 나중에 좀 더 정교한 모니터링 및 제어를 설정할 수 있습니다.

- [빠른 시작: 시작 Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)
- [즉각적 동작 분석 및 이상 검색 기능 사용](/cloud-app-security/anomaly-detection-policy)
- [자세한 내용은 Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [새 기능 검토](/cloud-app-security/release-notes)
- [기본 설정 지침 참조](/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: 위협 모니터링 및 조치 수행

Microsoft 365 상태를 모니터링하고 적절한 조치를 취하는 여러 가지 방법이 포함되어 있습니다. 가장 좋은 시작 지점은 조직의 Microsoft 보안 점수와 주의가 필요한 모든 경고 또는 엔터티를 볼 수 있는 Microsoft 365 보안 센터( [https://security.microsoft.com](https://security.microsoft.com) )입니다. [](./defender/microsoft-secure-score.md)

- [사이트 포털 Microsoft 365 Defender 시작](./defender/microsoft-365-defender.md#the-microsoft-365-defender-portal)
- [보안 포털을 Microsoft 365](./defender/portals.md)

## <a name="next-steps"></a>다음 단계

축하합니다! 가장 중요한 보안 보호 중 일부를 빠르게 구현할 수 있으며 조직은 훨씬 더 안전합니다. 이제 위협 방지 기능(끝점용 Microsoft Defender 포함), 데이터 분류 및 보호 기능, 관리 계정 보호를 더욱 강화할 준비가 완료되었습니다. 보안에 대한 더 심층적인 보안 권장 Microsoft 365 [BDM(Microsoft 365 Security for Business Decision Makers)을 참조하세요.](Microsoft-365-security-for-bdm.md)

또한 에서 Microsoft의 새로운 보안 [센터를 docs.microsoft.com/security.](/security)