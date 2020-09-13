---
title: 집에서 작업을 지원 하기 위한 보안 팀을 위한 상위 12 개 작업
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: 랜 섬 웨어, 피싱 및 악의적 첨부 파일을 포함 하 여 사이버 위협 으로부터 비즈니스 전자 메일 및 데이터를 보호 합니다.
ms.openlocfilehash: f364b4100efb3d8b9ab4eda2e370794ca4f0f469
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547977"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>집에서 작업을 지원 하기 위한 보안 팀을 위한 상위 12 개 작업

[Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) 와의 동시에 사용자가 주로 홈 기반 직원을 지 원하는 경우에는 조직이 가능한 한 안전 하 게 작동 하는지 확인 하는 데 도움이 될 것입니다. 이 문서에서는 보안 팀이 가장 중요 한 보안 기능을 최대한 신속 하 게 구현 하기 위한 작업을 우선적으로 설명 합니다. 

중소 규모 조직에서 Microsoft의 비즈니스 계획 중 하나를 사용 하는 경우에는 대신 다음 리소스를 참조 하세요.
- [Office 365 및 Microsoft 365 비즈니스 계획을 보호 하는 10 가지 주요 방법](../admin/security-and-compliance/secure-your-business-data.md) 
- [캠페인에 대 한 Microsoft 365](https://docs.microsoft.com/microsoft-365/campaigns/?view=o365-worldwide) (Microsoft 365 Business에 대 한 권장 보안 구성 포함)

  
기업 계획을 사용 하는 고객의 경우 서비스 요금제에 적용 되는 다음 표에 나열 된 작업을 완료 하는 것이 좋습니다. Microsoft 365 enterprise 요금제를 구입 하는 대신 구독을 결합 하는 경우 다음 사항에 유의 하세요.
- Microsoft 365 E3에는 EMS (Enterprise Mobility + Security) E3 및 Azure AD P1이 포함 되어 있습니다.
- Microsoft 365 E5에는 EMS E5와 Azure AD P2가 포함 되어 있습니다.
  
||**작업**| 모든 Office 365 Enterprise 요금제|**Microsoft 365 E3** |**Microsoft 365 E5**|
|:-----|:-----|:-----|:-----|:-----|
|1       |[Azure MFA (Multi-factor Authentication) 사용](#1-enable-azure-multi-factor-authentication-mfa)   |   ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)   | ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|2      | [위협으로부터 보호](#2-protect-against-threats) |![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png) |  ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)       | ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|3       |  [Office 365 Advanced Threat Protection 구성](#3-configure-office-365-advanced-threat-protection)  |   |      |  ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|4       | [Azure ATP (Advanced Threat Protection) 구성](#4-configure-azure-advanced-threat-protection)   |   |      |  ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|5      |   [Microsoft 위협 방지 설정](#5-turn-on-microsoft-threat-protection)  |  |      | ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|6       | [전화 및 태블릿에서 Intune 모바일 앱 보호 구성](#6-configure-intune-mobile-app-protection-for-phones-and-tablets) |    |  ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)       |  ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|7      | [Intune 앱 보호를 포함 하 여 게스트에 대 한 MFA 및 조건부 액세스 구성](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)  |    |  ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)     | ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|8       |  [Pc를 장치 관리에 등록 하 고 준수 Pc 필요](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)   |  | ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)        | ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|9       | [클라우드 연결용 네트워크 최적화](#9-optimize-your-network-for-cloud-connectivity)  |  ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png) |![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|10    | [사용자 교육](#10-train-users) |    ![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png) |![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|11  |[Microsoft Cloud App Security 시작](#11-get-started-with-microsoft-cloud-app-security) |  |  |![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)   |
|12  |[위협 모니터링 및 작업 수행](#12-monitor-for-threats-and-take-action) |![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![시킨](../media/d238e041-6854-4a78-9141-049224df0795.png)  |
| | | |


   
시작 하기 전에 Microsoft 365 보안 센터에서 [microsoft 365 보안 점수](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) 를 확인 하세요. 중앙 집중식 대시보드에서 Microsoft 365 id, 데이터, 앱, 장치 및 인프라에 대 한 보안을 모니터링 하 고 향상 시킬 수 있습니다. 권장 되는 보안 기능을 구성 하 고, 보고서 보기와 같은 보안 관련 작업을 수행 하거나, 타사 응용 프로그램 또는 소프트웨어를 사용 하 여 권장 주소를 지정 하기 위한 사항이 제공 됩니다. 이 문서의 권장 작업은 점수를 높입니다.
  
![Microsoft 보안 점수 스크린샷](../media/secure-score.png)
  
## <a name="1-enable-azure-multi-factor-authentication-mfa"></a>1: MFA (다단계 인증)를 사용 하도록 설정
집에서 작업 하는 직원에 대 한 보안을 개선 하기 위해 수행할 수 있는 가장 좋은 방법은 MFA를 켜는 것입니다. 아직 프로세스가 없는 경우에는이를 응급 파일럿으로 취급 하 고, 직원이 중단 되는 직원 들에 게 도움을 받을 수 있도록 지원 서비스를 제공 해야 합니다. 하드웨어 보안 장치를 배포할 수 없는 것 처럼 Windows Hello 생체 인식 및 smartphone 인증 앱 (예를 들어 Microsoft 인증자)을 사용 합니다.

일반적으로 Microsoft는 MFA를 요구 하기 전에 사용자에 게 14 일간의 장치를 등록 하 여 다단계 인증을 제공 하는 것이 좋습니다. 그러나 직원 들이 집에서 갑자기 작업 하는 경우에는 보안 우선 순위로 MFA를 요구 하 고 필요한 사용자에 게 도움이 되도록 준비 해야 합니다. 

이러한 정책을 적용 하는 데 몇 분 정도 걸리지만 다음 며칠 동안 사용자를 지원할 준비가 되었습니다.  


|계획  |권장 사항  |
|---------|---------|
|Microsoft 365 계획 (Azure AD P1 또는 P2 제외)     |[Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)에서 보안 기본값을 사용하도록 설정 합니다. Azure AD의 보안 기본값에는 사용자 및 관리자를 위한 MFA가 포함됩니다.   |
|Microsoft 365 E3 (Azure AD P1 포함)     | [공통 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)을 사용하여 다음 정책을 구성합니다. <br>- [관리자에게 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [모든 사용자에 대해 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [레거시 인증 차단](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (Azure AD P2 포함)     | Azure AD ID 보호를 활용하여 다음 두 정책을 만들어 Microsoft의 [권장 조건부 액세스 및 관련 정책 집합](../enterprise/identity-access-policies.md)을 구현하세요.<br> - [로그인 위험이 중간 이상인 경우 MFA 필요](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [최신 인증을 지원하지 않는 클라이언트 차단](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [위험이 높은 사용자는 암호를 변경해야 함](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |


  
## <a name="2-protect-against-threats"></a>2: 위협 으로부터 보호

모든 Microsoft 365 계획에는 다양 한 위협 방지 기능이 포함 되어 있습니다. 이 기능에 대 한 Bumping을 보호 하려면 몇 분 정도 걸립니다.
- 맬웨어 방지 보호 기능
- 악의적인 Url 및 파일 로부터의 보호
- 피싱 방지 보호 기능
- 스팸 방지 보호 기능

시작 점으로 사용할 수 있는 지침에 대해서는 [Office 365의 위협 으로부터 보호](office-365-security/protect-against-threats.md) 를 참조 하세요.
    

## <a name="3-configure-office-365-advanced-threat-protection"></a>3: Office 365 Advanced Threat Protection 구성

Microsoft 365 E5 및 Office 365 E5에 포함 된 Office 365 Advanced Threat Protection (ATP)은 전자 메일 메시지, 링크 (Url) 및 공동 작업 도구로 인해 야기 되는 악의적인 위협 으로부터 조직을 보호 합니다. 이 작업을 구성 하는 데 몇 시간이 걸릴 수 있습니다.

Office 365 ATP:
- 악성 콘텐츠를 위한 첨부 파일 및 링크를 검사 하는 지능형 시스템을 사용 하 여 알 수 없는 전자 메일 위협 으로부터 조직에서 실시간으로 보호 합니다. 이러한 자동화 된 시스템에는 강력한 샌드 박싱 플랫폼, 추론 및 기계 학습 모델이 포함 되어 있습니다. 
- 사용자가 팀 사이트 및 문서 라이브러리에서 악의적인 파일을 식별 하 고 차단 하 여 파일을 공동 작업 하 고 공유할 때 조직을 보호 합니다. 
- Avert 피싱 공격에 기계 학습 모델 및 고급 가장 검색 알고리즘을 적용 합니다. 

계획 요약을 포함 하 여 개요를 보려면 [Office 365 Advanced Threat Protection](office-365-security/office-365-atp.md)를 참조 하세요.

전역 관리자는 이러한 보호를 구성할 수 있습니다.
- [ATP 안전한 링크 설정](office-365-security/set-up-atp-safe-links-policies.md)
- [ATP 안전한 첨부 파일 정책 설정](office-365-security/set-up-atp-safe-attachments-policies.md)
- [사용자 지정 "재작성 금지" URL 목록 설정](office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
- [차단된 사용자 지정 URL 목록 설정](office-365-security/set-up-a-custom-blocked-urls-list-atp.md)

Exchange Online 관리자 및 SharePoint Online 관리자와 협력 하 여 이러한 작업에 대 한 ATP를 구성 해야 합니다.
- [SharePoint, OneDrive 및 Microsoft Teams의 ATP 켜기](office-365-security/turn-on-atp-for-spo-odb-and-teams.md)

## <a name="4-configure-azure-advanced-threat-protection"></a>4: Azure Advanced Threat Protection 구성

[AZURE ATP (Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) )는 온-프레미스 Active Directory 신호를 활용 하 여 고급 위협, 손상 된 id 및 조직에서 보낸 악의적인 참가자 작업을 식별, 감지 및 조사 하기 위한 클라우드 기반 보안 솔루션입니다. 다음에는 온-프레미스 및 클라우드 인프라를 보호 하 고, 종속성 이나 필수 구성 요소가 없으며, 즉각적인 이점을 제공할 수 있으므로 중점적으로 설명 합니다.


- 설치를 빠르게 받으려면 [AZURE ATP 퀵 스타트](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) 를 참조 하세요. 
- [비디오 보기: AZURE ATP 소개](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [AZURE ATP 배포의 세 단계](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next) 검토

## <a name="5-turn-on-microsoft-threat-protection"></a>5: Microsoft Threat Protection 설정

Office 365 ATP 및 Azure ATP가 구성 되었으므로 한 대시보드에서 이러한 기능 으로부터 결합 된 신호를 볼 수 있습니다. MTP ( [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) )는 작업 (Azure Atp, OFFICE 365 ATP, MICROSOFT Defender ATP 및 Microsoft Cloud App Security)에서 경고, 문제, 자동화 된 조사 및 응답을 함께 제공 하며 [security.microsoft.com](https://security.microsoft.com)에서 단일 창으로 진행 됩니다. 
<br>

![MTP 대시보드 그림](../media/top-ten-security-remote-work-mtp-dashboard.png)
<br><br>
Advanced threat protection 서비스를 하나 이상 구성한 후에 MTP를 켜십시오. 새 기능은 MTP에 계속적으로 추가 됩니다. 미리 보기 기능을 받으려면 옵트인을 고려 하세요.

- [MTP에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [MTP 켜기](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide)
- [미리 보기 기능에 대 한 옵트인](https://docs.microsoft.com/microsoft-365/security/mtp/preview?view=o365-worldwide)


## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: 휴대폰 및 태블릿에서 Intune 모바일 앱 보호 구성

Microsoft Intune MAM (모바일 응용 프로그램 관리)를 사용 하면 이러한 장치를 관리 하지 않고도 휴대폰 및 태블릿에서 조직의 데이터를 관리 하 고 보호할 수 있습니다. 작동 방식은 다음과 같습니다.
- 장치에서 관리 되는 앱을 결정 하는 앱 (앱 보호 정책)과 관리 되는 응용 프로그램의 데이터가 관리 되지 않는 앱에 복사 되는 것을 방지 하는 것과 같은 허용 되는 동작을 만듭니다. 각 플랫폼 (iOS, Android)에 대해 하나의 정책을 만듭니다.
- 앱 보호 정책을 만든 후에는 승인 된 앱 및 앱 데이터 보호를 요구 하도록 Azure AD에서 조건부 액세스 규칙을 만들어이를 적용 합니다.

앱 보호 정책에는 여러 설정이 포함 됩니다. 다행히도, 모든 설정에 대 한 정보를 파악 하 고 옵션을 평가 하지 않아도 됩니다. Microsoft는 시작 지점을 추천 하 여 설정 구성을 쉽게 적용할 수 있도록 합니다. [앱 보호 정책을 사용 하는 데이터 보호 프레임 워크](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) 에는 세 가지 수준 중에서 선택할 수 있습니다. 

또한 Microsoft는이 앱 보호 프레임 워크에 조건부 액세스 및 관련 정책 집합을 조정 하는 것이 좋지만, 모든 조직은 시작 점으로 사용 하는 것이 좋습니다. 이 문서의 지침을 사용 하 여 MFA를 구현한 경우 절반으로 진행 됩니다.

모바일 앱 보호를 구성 하려면 [일반 id 및 장치 액세스 정책](../enterprise/identity-access-policies.md)에 있는 지침을 사용 합니다.
 1. [앱 데이터 보호 정책 적용](../enterprise/identity-access-policies.md#apply-app-data-protection-policies) 지침을 사용 하 여 IOS 및 Android 용 정책을 만듭니다. 기본 보호에는 수준 2 (향상 된 데이터 보호)가 권장 됩니다. 
 2. [승인 된 앱 및 앱 보호가 필요한](../enterprise/identity-access-policies.md#require-approved-apps-and-app-protection)조건부 액세스 규칙을 만듭니다. 

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: Intune 모바일 앱 보호를 포함 하 여 게스트에 대 한 MFA 및 조건부 액세스 구성

다음으로, 게스트와 계속 해 서 공동 작업 및 작업할 수 있도록 합니다. Microsoft 365 E3 요금제를 사용 중이 고 모든 사용자에 대해 MFA를 구현한 경우에는가 설정 됩니다. 

Microsoft 365 E5 요금제를 사용 하는 경우에는 위험 기반 MFA에 대 한 Azure Id 보호 기능을 활용 하 고 있다면 몇 가지 조정 작업을 수행 해야 합니다 (Azure AD Identity Protection이 게스트로 확장 되지 않으므로).
- 게스트 및 외부 사용자에 대해 MFA를 항상 필요로 하는 새 조건부 액세스 규칙을 만듭니다.
- Guest 및 외부 사용자를 제외 하도록 위험 기반 MFA 조건부 액세스 규칙을 업데이트 합니다.

[게스트 및 외부 액세스를 허용 및 보호 하기 위한 일반 정책 업데이트](../enterprise/identity-access-policies-guest-access.md) 의 지침을 사용 하 여 게스트 액세스가 Azure AD에서 작동 하는 방식을 이해 하 고 영향을 받는 정책을 업데이트 합니다. 

사용자가 만든 Intune 모바일 앱 보호 정책 및 조건부 액세스 규칙을 함께 사용 하 여 승인 된 앱 및 앱 보호를 요구 하 고, 게스트 계정에 적용 되며, 조직 데이터를 보호 하는 데 도움이 됩니다. 

> [!NOTE]
> 장치 관리에 Pc를 이미 등록 하 여 준수 Pc를 요구 하는 경우에도 장치 준수를 적용 하는 조건부 액세스 규칙에서 게스트 계정을 제외 해야 합니다. 


## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: Pc를 장치 관리에 등록 하 고 준수 Pc 필요

직원의 장치를 등록 하는 방법에는 여러 가지가 있습니다. 각 방법은 디바이스 소유권(개인 또는 회사), 디바이스 유형(iOS, Windows, Android) 및 관리 요구 사항(재설정, 선호도, 잠금)에 따라 다릅니다. 이 작업은 정렬 하는 데 다소 시간이 걸릴 수 있습니다. 자세한 내용은 [Microsoft Intune에서 장치 등록을](https://docs.microsoft.com/mem/intune/enrollment/)참조 하세요. 

[Windows 10 장치에 대 한 자동 등록을 설정](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)하는 것이 가장 빠른 방법입니다. 

다음 자습서를 활용할 수도 있습니다.
- [Autopilot을 사용 하 여 Intune에서 Windows 장치 등록](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Intune에서 apple Business Manager (ABM)의 회사 장비 등록 기능을 사용 하 여 iPadOS에서 iOS/장치를 등록 합니다.](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

장치를 등록 한 후 [일반 id 및 장치 액세스 정책](../enterprise/identity-access-policies.md) 에 설명 된 지침을 사용 하 여 다음 정책을 만듭니다.
- [장치 준수 정책 정의](../enterprise/identity-access-policies.md#define-device-compliance-policies) -Windows 10에 권장 되는 설정에는 바이러스 백신 보호가 필요 합니다. Microsoft 365 E5가 있는 경우 Microsoft Defender Advanced Threat Protection을 사용 하 여 직원 장치의 상태를 모니터링 합니다. 다른 운영 체제에 대 한 준수 정책에는 바이러스 백신 보호 및 최종 지점 보호 소프트웨어가 포함 되어 있어야 합니다. 
- [준수 Pc 필요](../enterprise/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) -이는 장치 준수 정책을 적용 하는 Azure AD의 조건부 액세스 규칙입니다.

한 조직 에서만 장치를 관리할 수 있으므로 Azure AD의 조건부 액세스 규칙에서 게스트 계정을 제외 해야 합니다. 장치 준수를 요구 하는 정책에서 게스트 및 외부 사용자를 제외 하지 않으면 이러한 정책은 이러한 사용자를 차단 합니다. 자세한 내용은 [게스트 및 외부 액세스를 허용 하 고 보호 하기 위해 일반 정책 업데이트](../enterprise/identity-access-policies-guest-access.md)를 참조 하세요.

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: 클라우드 연결용 네트워크 최적화

집에서 대규모 직원을 빠르게 사용할 수 있도록 설정 하는 경우이 급격 한 연결 패턴 전환이 회사 네트워크 인프라에 큰 영향을 줄 수도 있습니다. 많은 네트워크는 클라우드 서비스를 채택 하기 전에 확장 되 고 설계 되었습니다. 대부분의 경우 네트워크는 원격 작업자를 허용 하지만 모든 사용자가 동시에 원격으로 사용 하도록 설계 되지 않았습니다.

VPN 집중 장치, 중앙 네트워크 송신 장비 (예: 프록시 및 데이터 손실 방지 장치), 중앙 인터넷 대역폭, MPLS 회로, NAT 기능 등의 네트워크 요소를 사용 하는 경우에는 전체 비즈니스의 부하로 인해 상당한 부담을 초래 하 게 됩니다. 최종 결과로 성능이 저하 되 고, 가정에서 작업을 수행 하는 사용자에 게 뛰어난 사용자 환경에 대 한 만족도가 저하 됩니다.

회사 네트워크를 통해 전송 되는 트래픽 라우팅을 통해 전통적으로 제공 되는 일부 보호 기능은 사용자가 액세스 하는 클라우드 앱에서 제공 합니다. 이 문서의이 단계에 도달 하면 Microsoft 365 서비스 및 데이터에 대 한 정교한 클라우드 보안 컨트롤 집합을 구현 해야 합니다. 이러한 컨트롤을 사용 하는 경우 원격 사용자의 트래픽을 Office 365로 직접 라우팅할 수 있습니다. 다른 응용 프로그램에 액세스 하기 위한 VPN 링크가 여전히 필요한 경우 분할 터널링을 구현 하 여 성능 및 사용자 환경을 대폭 개선할 수 있습니다. 조직에서 계약을 받은 후에는 잘 조정 된 네트워크 팀이 하루 이내에이 작업을 수행할 수 있습니다.


자세한 내용은 문서에서 다음 리소스를 참조 하세요.
- [개요: VPN 분할 터널링을 사용 하 여 원격 사용자에 대 한 연결 최적화](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Office 365 VPN 분할 터널링 구현](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

이 항목에 대 한 최신 블로그 문서:
- [원격 직원의 트래픽을 빠르게 최적화 하 & 인프라에 대 한 부하 절감](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [보안 전문가 및 IT가 오늘날의 고유한 원격 작업 시나리오에서 최신 보안 제어 기능을 구현 하는 다른 방법](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)


## <a name="10-train-users"></a>10: 사용자 교육

교육 사용자는 사용자 및 보안 운영 팀에 게 많은 시간과 노력을 절감할 수 있습니다. 숙련 된 사용자는 첨부 파일을 열거나 불확실 한 전자 메일 메시지의 링크를 클릭 하거나 의심 스러운 웹 사이트를 피하는 것이 더 쉽습니다. 

Harvard Kennedy School [Cybersecurity 캠페인 안내서](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) 에서는 피싱 공격을 식별 하기 위한 교육 사용자를 포함 하 여 조직 내에서 보안을 보다 강력 하 게 인식 하는 방법을 제공 합니다. 

Microsoft 365에서는 조직에서 사용자에 게 알릴 수 있도록 다음과 같은 리소스를 제공 합니다.

|개념  |리소스  |
|---------|---------|
|Microsoft 365     |[사용자 지정 가능한 학습 경로](https://docs.microsoft.com/office365/customlearning/) <p>이러한 리소스를 통해 조직의 최종 사용자에 게 교육을 추가 하는 데 도움이 될 수 있습니다.        |
|Microsoft 365 보안 |[학습 모듈: 기본 제공 되는 Microsoft 365의 지능형 보안을 사용 하 여 조직 보호](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>이 모듈을 사용 하 여 Microsoft 365 보안 기능이 함께 작동 하는 방식에 대해 설명 하 고 이러한 보안 기능의 이점을 구체화할 수 있습니다. |
|다단계 인증     | [2 단계 인증: 추가 확인 페이지 란?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>이 문서에서는 최종 사용자가 다단계 인증을 이해 하 고 조직에서이를 사용 하는 이유를 파악 하는 데 도움이 됩니다.    |
| | |

이 지침 외에도, 사용자가 [해커 및 맬웨어로부터 계정 및 장치를 보호](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)하는이 문서에서 설명 하는 작업을 수행 하는 것이 좋습니다. 이러한 작업은 다음과 같습니다.
  
- 강력한 암호 사용
    
- 장치 보호 
    
- Windows 10 및 Mac Pc에서 보안 기능 사용 (관리 되지 않는 장치)
    
또한 사용자는 다음 문서에서 권장 하는 작업을 수행 하 여 개인 전자 메일 계정을 보호 하는 것이 좋습니다.
  
- [Outlook.com 전자 메일 계정 보호](https://support.microsoft.com/en-us/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
    
- [2 단계 인증을 사용 하 여 Gmail 계정 보호](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)


## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Microsoft Cloud App Security 시작

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) 는 모든 클라우드 서비스에서 cyberthreats를 식별 하 고 공격 하기 위한 다양 한 가시성, 데이터 이동에 대 한 제어 및 정교한 분석 기능을 제공 합니다. Cloud App Security를 시작한 후에는 변칙 검색 정책이 자동으로 사용 하도록 설정 되지만 Cloud App Security에서는 일부 변칙 검색 알림이 발생 하지 않는 7 일 동안의 초기 학습 기간이 적용 됩니다.

지금 클라우드 앱 보안을 시작 하세요. 나중에 보다 복잡 한 모니터링과 컨트롤을 설정할 수 있습니다.

- [퀵 스타트: Cloud App Security 시작](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [즉각적인 행동 분석 및 변칙 검색 받기](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [Microsoft Cloud App Security에 대 한 자세한 정보](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [새로운 기능 및 기능 검토](https://docs.microsoft.com/cloud-app-security/release-notes)
- [기본 설치 지침 참조](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: 위협 모니터링 및 조치 수행

Microsoft 365에는 상태를 모니터링 하 고 적절 한 조치를 취하는 몇 가지 방법이 포함 되어 있습니다. 가장 좋은 출발점은 Microsoft 365 보안 센터 ( [https://security.microsoft.com](https://security.microsoft.com) )로, 조직의 [Microsoft 보안 점수](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score?view=o365-worldwide)와 주의가 필요한 경고나 엔터티를 볼 수 있습니다.

- [Microsoft 365 보안 센터 시작 하기](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center?view=o365-worldwide)
- [보고서 모니터링 및 보기](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting?view=o365-worldwide)
- [Microsoft 365에서 보안 포털을 참조 하세요.](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>다음 단계

축하합니다! 가장 중요 한 보안 보호 중 일부를 빠르게 구현 했으며 조직이 보다 안전 합니다. 이제는 위협 방지 기능 (Microsoft Defender Advanced Threat Protection), 데이터 분류 및 보호 기능, 관리 계정 보안 등을 계속 진행할 준비가 되었습니다. Microsoft 365에 대 한 체계적인 조직적 보안 권장 사항에 대 한 자세한 내용은 [microsoft 365 security For Business 의사 결정권자 (BDMs)](Microsoft-365-security-for-bdm.md)를 참조 하십시오. 

또한 [docs.microsoft.com/security](https://docs.microsoft.com/security)에서 Microsoft의 새 보안 센터를 방문 하세요. 
