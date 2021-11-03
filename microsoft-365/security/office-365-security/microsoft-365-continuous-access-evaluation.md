---
title: 엔터프라이즈용 Microsoft 365 지속적인 Microsoft 365 평가
description: Microsoft 365 Azure AD에 대한 조건부 액세스 평가가 활성 사용자 세션을 능동적으로 종료하고 거의 실시간으로 테넌트 정책 변경을 적용하는 방법에 대해 설명합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
ms.technology: mdo
ms.openlocfilehash: 1625f266bff322bf77f6eeaeb0d0690853587dad
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661989"
---
# <a name="continuous-access-evaluation-for-microsoft-365"></a>사용자에 대한 지속적인 액세스 Microsoft 365

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)

인증에 OAuth 2.0을 사용하는 최신 클라우드 서비스는 일반적으로 액세스 토큰 만료를 사용하여 사용자 계정의 액세스를 해지합니다. 실제로 이는 관리자가 사용자 계정의 액세스를 해지하는 경우에도 액세스 토큰이 만료될 때까지 계속 액세스할 수 있는 권한을 Microsoft 365 기본적으로 초기 해지 이벤트가 발생된 후 최대 1시간까지 사용되었습니다.  

Azure AD(Microsoft 365 및 Azure Active Directory)에 대한 조건부 액세스 평가는 활성 사용자 세션을 사전적으로 종료하고 액세스 토큰 만료를 사용하지 않고 거의 실시간으로 테넌트 정책 변경을 적용합니다. Azure AD는 사용자 계정 또는 테넌트가 사용자 계정의 인증 상태를 재평가해야 하는 방식으로 변경된 경우 연속 액세스 평가가 가능한 Microsoft 365 서비스(예: SharePoint, Teams 및 Exchange)에 알렸다. 

기존 액세스 토큰을 사용하여 Outlook 클라이언트가 Exchange 액세스 평가가 가능한 클라이언트가 서비스에 의해 거부되고 새 Azure AD 인증을 묻는 메시지가 표시됩니다. 그 결과 거의 실시간으로 사용자 계정 및 정책 변경이 적용됩니다.  

몇 가지 추가 이점은 다음과 같습니다.

- 조직 외부에서 유효한 액세스 토큰을 복사하고 내보내는 악의적인 내부자에 대해 지속적인 액세스 평가는 Azure AD IP 주소 위치 정책을 통해 이 토큰을 사용할 수 없습니다. 지속적인 액세스 평가를 통해 Azure AD는 정책을 지원되는 Microsoft 365 서비스에 동기화하여 액세스 토큰이 정책의 IP 주소 범위 외부에서 서비스에 액세스하려고 할 때 서비스에서 토큰을 거부합니다. 

- 지속적인 액세스 평가는 토큰 새로 고침을 더 적게 요구하여 탄력성을 향상합니다. 지원 서비스는 재인식 요구에 대한 사전 알림을 수신하기 때문에 Azure AD는 수명이 긴 토큰을 1시간 이상 발급할 수 있습니다. 수명이 긴 토큰을 사용할 경우 클라이언트는 Azure AD에서 토큰 새로 고침을 자주 요청하지 않습니다. 따라서 사용자 환경은 더 탄력적입니다.

다음은 연속 액세스 평가로 사용자 액세스 제어 보안을 향상시키는 몇 가지 예입니다. 

- 사용자 계정의 암호가 손상되어 관리자가 기존 세션을 모두 무효화하고 계정에서 암호를 Microsoft 365 관리 센터. 거의 실시간으로 모든 기존 사용자 세션이 Microsoft 365 무효화됩니다. 

- Word에서 문서를 작업하는 사용자가 관리자가 정의하고 승인한 IP 주소 범위에 없는 공용 커피숍으로 태블릿을 갖습니다. 커피숍에서 사용자의 문서 액세스가 즉시 차단됩니다. 

이 Microsoft 365 현재 다음을 통해 연속 액세스 평가가 지원됩니다.

- Exchange, SharePoint 및 Teams 서비스를 제공합니다. 
- Outlook, Teams, Office 및 OneDrive, Win32, iOS, Android 및 Mac 클라이언트에서 사용할 수 있습니다. 

Microsoft는 지속적인 액세스 평가를 Microsoft 365 서비스 및 클라이언트를 추가로 지원하고 있습니다. 

연속 액세스 평가는 모든 버전의 Office 365 Microsoft 365. 조건부 액세스 정책을 구성하려면 모든 Azure AD Premium P1 버전에 포함된 조건부 액세스 Microsoft 365 필요합니다.

>[!Note]
>연속 [액세스 평가의](/azure/active-directory/conditional-access/concept-continuous-access-evaluation#limitations) 제한은 이 문서를 참조하세요.
>

## <a name="scenarios-supported-by-microsoft-365"></a>지원되는 Microsoft 365 

연속 액세스 평가는 두 가지 유형의 이벤트를 지원합니다. 

- 중요 이벤트는 사용자가 액세스 권한을 잃게 하는 이벤트입니다. 
- 조건부 액세스 정책 평가는 사용자가 관리자 정의 정책에 따라 리소스에 액세스할 수 없는 경우 발생합니다.  

중요 이벤트는 다음과 같습니다. 

- 사용자 계정을 사용할 수 없습니다. 
- 암호 변경 
- 사용자 세션 해지 
- 사용자에 대해 다단계 인증 사용 
- Azure AD ID 보호의 액세스 평가에 따라 계정 [위험 증가](/azure/active-directory/identity-protection/overview-identity-protection)

조건부 액세스 정책 평가는 사용자 계정이 더 이상 신뢰할 수 있는 네트워크에서 연결되지 않습니다. 

다음 Microsoft 365 서비스는 현재 Azure AD의 이벤트를 수신하여 지속적인 액세스 평가를 지원하고 있습니다.  

| 적용 유형  | Exchange | SharePoint | Teams |
|:-------|:-----|:-------|:-------|
| **중요 이벤트:** |  |  |  |
| 사용자 해지 | 지원 | 지원 | 지원 |
| 사용자 위험 | 지원됨 | 지원되지 않음 | 지원되지 않음 |
| **조건부 액세스 정책 평가:** |  |  |  |
| IP 주소 위치 정책 | 지원 | 지원* | 지원 |

* SharePoint Office 브라우저 액세스는 엄격한 모드를 사용하도록 설정하여 즉각적인 IP 정책 적용을 지원합니다. 엄격한 모드가 없는 경우 액세스 토큰 수명은 1시간입니다.   

조건부 액세스 정책을 설정하는 방법에 대한 자세한 내용은 이 문서를 [참조하세요.](/azure/active-directory/conditional-access/overview)

## <a name="microsoft-365-clients-supporting-continuous-access-evaluation"></a>Microsoft 365 평가를 지원하는 클라이언트 

Microsoft 365 평가를 지원하는 클라이언트는 캐시된 사용자 토큰이 지속적인 액세스 평가 사용이 가능한 Microsoft 365 서비스에 의해 거부되는 경우 다시 인증을 위해 사용자 세션을 Azure AD로 리디렉션하는 클레임 챌린지(클레임 챌린지)를 지원합니다.  

다음 클라이언트는 웹, Win32, iOS, Android 및 Mac에서 지속적인 액세스 평가를 지원합니다. 

- Outlook 
- Teams 
- Office*
- SharePoint 
- OneDrive 

* 웹용 응용 Office 클레임 챌린지가 지원되지 않습니다.

연속 액세스 평가를 지원하지 않는 클라이언트의 경우 기본적으로 Microsoft 365 토큰 수명은 1시간으로 남아 있습니다.    

## <a name="see-also"></a>참고 항목

- [지속적인 액세스 평가](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
- [조건부 액세스 설명서](/azure/active-directory/conditional-access/overview)
- [Azure AD ID 보호 설명서](/azure/active-directory/identity-protection/overview-identity-protection)
