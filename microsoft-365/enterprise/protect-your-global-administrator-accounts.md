---
title: 전역 Microsoft 365 계정 보호
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: 이 문서에서는 사용자 구독에 대한 전역 관리자 액세스를 보호하는 Microsoft 365 제공합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3a43c8b6ac5389be99581302c249e431853ba99b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215782"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>전역 Microsoft 365 계정 보호

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

정보 수집 및 피싱 공격을 포함하여 Microsoft 365 구독의 보안 위반은 일반적으로 전역 관리자 계정의 자격 증명을 Microsoft 365 수행됩니다. 클라우드의 보안은 사용자와 Microsoft 간의 파트너 관계입니다.
  
- Microsoft 클라우드 서비스는 신뢰 및 보안을 토대로 구축됩니다. Microsoft는 데이터 및 응용 프로그램을 보호하는 데 도움이 되는 보안 제어 및 기능을 제공합니다.
    
- 데이터 및 ID와 데이터 보호에 대한 책임, 사내 리소스의 보안 및 제어하는 클라우드 구성 요소의 보안을 소유합니다.
    
Microsoft는 조직을 보호하는 데 도움이 되는 기능을 제공하지만 사용하는 경우만 유효합니다. 사용하지 않는 경우 공격에 취약할 수 있습니다. 전역 관리자 계정을 보호하기 위해 Microsoft는 다음에 대한 자세한 지침을 제공합니다.
  
1. 전역 Microsoft 365 전용 관리자 계정을 만들고 필요한 경우만 사용하세요.
    
2. 전역 관리자 계정에 대해 전용 Microsoft 365 다단계 인증을 구성하고 가장 강력한 형태의 보조 인증을 사용하세요.
    
> [!Note]
> 이 문서는 전역 관리자 계정에 초점을 맞추지만 구독의 데이터에 액세스할 수 있는 광범위한 권한이 있는 추가 계정(예: eDiscovery 관리자 또는 보안 또는 규정 준수 관리자 계정)을 동일한 방식으로 보호해야 하는지 여부를 고려해야 합니다. <br > 라이선스를 추가하지 않고 전역 관리자 계정을 만들 수 있습니다.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>1단계. 전역 Microsoft 365 전용 관리자 계정을 만들고 필요한 경우만 사용

사용자 계정에 역할을 할당하는 등 전역 관리자 권한이 필요한 관리 작업은 비교적 적습니다. 따라서 전역 관리자 역할이 할당된 일상적인 사용자 계정을 사용하는 대신 다음 단계를 수행합니다.
  
1. 전역 관리자 역할이 할당된 사용자 계정 집합을 결정하십시오. 이 작업을 Microsoft 365 관리 센터 Azure AD(Azure Active) 디렉터리 PowerShell을 사용하여 이 작업을 Graph 있습니다.
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. 전역 관리자 역할이 Microsoft 365 계정으로 Microsoft 365 구독에 로그인합니다.
    
3. 최대 4개의 전용 전역 관리자 사용자 계정을 만들 수 있습니다. **12자 이상 강력한 암호를 사용하세요.** 자세한 [내용은 강력한](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 암호 만들기를 참조하세요. 새 계정의 암호를 안전한 위치에 저장합니다. 
    
4. 각 새 전용 전역 관리자 사용자 계정에 전역 관리자 역할을 할당합니다.
    
5. 로그인에서 Microsoft 365.
    
6. 새 전용 전역 관리자 사용자 계정 중 하나를 통해 로그인합니다.
    
7. 1단계에서 전역 관리자 역할이 할당된 각 기존 사용자 계정에 대해 다음을 진행합니다.
    
  - 전역 관리자 역할을 제거합니다.
    
  - 해당 사용자의 직무 및 책임에 적합한 관리자 역할을 계정에 할당합니다. 관리자 역할의 다양한 관리자 역할에 대한 자세한 Microsoft 365 관리자 역할 [정보를 참조하세요.](/office365/admin/add-users/about-admin-roles)
    
8. 로그인에서 Microsoft 365.
    
결과는 다음을 따라야 합니다.
  
- 구독에서 전역 관리자 역할이 할당된 사용자 계정은 새로운 전용 전역 관리자 계정 집합뿐입니다. 다음 PowerShell 명령을 사용하여 이를 확인 합니다.
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- 구독을 관리하는 다른 모든 일상적인 사용자 계정에는 업무 책임과 연관된 관리자 역할이 할당되어 있습니다.
    
이 순간부터 전역 관리자 권한이 필요한 작업에만 전용 전역 관리자 계정으로 로그인합니다. 다른 모든 Microsoft 365 관리는 사용자 계정에 다른 관리 역할을 할당하여 수행되어야 합니다.
  
> [!NOTE]
> 이 경우 일상적인 사용자 계정으로 로그인하고 전용 전역 관리자 계정으로 로그인하기 위한 추가 단계가 필요합니다. 그러나 전역 관리자 작업에는 가끔씩만 이 작업을 수행해야 합니다. 전역 관리자 계정 위반 후 Microsoft 365 구독을 복구하려면 훨씬 더 많은 단계가 필요하다는 것을 고려하세요.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>2단계. 전용 전역 관리자 계정에 대해 다단계 Microsoft 365 구성

MFA(다단계 인증)에는 계정 이름 및 암호 이외에 추가 정보가 필요합니다. Microsoft 365 추가 확인 방법을 지원할 수 있습니다.
  
- Microsoft Authenticator 앱

- 전화 통화
    
- 문자 메시지를 통해 임의로 생성된 확인 코드
    
- 스마트 카드(가상 또는 실제)
    
- 생체 인식 장치
    
>[!Note]
>NIST(National Institute of Standards and Technology) 표준을 준수해야 하는 조직의 경우 전화 통화 또는 문자 메시지 기반의 추가 확인 방법을 사용할 수 없습니다. 자세한 [내용은 여기를](https://pages.nist.gov/800-63-FAQ/#q-b01) 클릭하세요.
>

클라우드에만 저장된 사용자 계정(클라우드 전용 ID 모델)을 사용하는 중소기업인 경우 각 전용 전역 관리자 계정에 대해 스마트폰으로 전송된 전화 통화 또는 문자 메시지 확인 코드를 사용하여 MFA를 구성하도록 [MFA를](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) 설정하세요.
    
하이브리드 ID 모델을 사용하는 대규모 조직인 Microsoft 365 더 많은 확인 옵션이 있습니다. 더 강력한 보조 인증 방법에 대한 보안 인프라가 이미 있는 경우 [MFA를](../admin/security-and-compliance/set-up-multi-factor-authentication.md) 설정하고 적절한 확인 방법을 위해 각 전용 전역 관리자 계정을 구성합니다.
  
원하는 강력한 확인 방법에 대한 보안 인프라가 설정되지 않은 경우 Microsoft 365 MFA에 대해 작동할 경우 중간 보안 조치로 Microsoft Authenticator 앱, 전화 통화 또는 전역 관리자 계정에 대해 스마트폰으로 전송된 문자 메시지 확인 코드를 사용하여 MFA로 전용 전역 관리자 계정을 구성하는 것이 좋습니다. MFA에서 제공하는 추가 보호 없이는 전용 전역 관리자 계정을 그대로 두지 않습니다.
  
자세한 내용은 에 [대한 MFA를 Microsoft 365.](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
  
MFA Microsoft 365 PowerShell을 사용하여 Microsoft 365 서비스에 연결하기 위해 다음 문서를 참조합니다.

- [사용자 계정, Microsoft 365 및 라이선스에 대한 PowerShell](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](/microsoftteams/teams-powershell-install)
- [Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [비즈니스용 Skype Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>엔터프라이즈 조직을 위한 추가 보호

이러한 추가 방법을 사용하여 전역 관리자 계정 및 이를 사용하여 수행하는 구성이 가능한 한 안전하게 유지되도록 합니다.
  
### <a name="privileged-access-workstation"></a>권한이 부여된 액세스 Workstation

권한이 높은 작업의 실행이 가능한 한 안전하도록 보장하기 위해 권한이 부여된 PAW(액세스 Workstation)를 사용합니다. PAW는 전역 관리자 계정이 필요한 Microsoft 365 구성과 같은 중요한 구성 작업에만 사용되는 전용 컴퓨터입니다. 이 컴퓨터는 인터넷 검색이나 전자 메일에 매일 사용되지 않는 것이 좋기 때문에 인터넷 공격 및 위협으로부터 보호하는 것이 좋습니다.
  
PAW를 설정하는 방법에 대한 지침은 을 [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices) 참조하세요.

Azure AD 테넌트 및 관리자 계정에서 Azure PIM을 사용하도록 설정하려면 [PIM 구성 절차](/azure/active-directory/active-directory-privileged-identity-management-configure)를 참조하세요.

권한 있는 액세스를 사이버 공격자로부터 보호하는 포괄적인 로드맵을 마련하려면 [Azure AD의 하이브리드 및 클라우드 배포에서 권한 있는 액세스 보호](/azure/active-directory/admin-roles-best-practices)를 참조하세요.

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

전역 관리자 계정에 전역 관리자 역할이 영구적으로 할당되지 않고, 필요한 경우 Azure AD Privileged Identity Management(PIM)를 사용하여 필요할 때 전역 관리자 역할의 정시에 할당할 수 있습니다.
  
전역 관리자 계정은 영구 관리자에서 적격 관리자로 변경됩니다. 전역 관리자 역할은 누군가가 필요로 할 때까지 비활성입니다. 그런 다음 정품 인증 프로세스를 완료하여 미리 정해진 시간 동안 전역 관리자 계정에 전역 관리자 역할을 추가합니다. 시간이 만료되면 PIM은 전역 관리자 계정에서 전역 관리자 역할을 제거합니다.
  
PIM과 이 프로세스를 사용하는 경우 전역 관리자 계정이 악의적인 사용자의 공격 및 사용에 취약해집니다.

PIM은 Microsoft 365 E5에 포함된 Azure Active Directory Premium P2와 함께 제공됩니다.  또는 관리자 계정에 대해 개별 Azure Active Directory Premium P2 라이선스를 구매할 수 있습니다.
  
자세한 내용은 Azure AD 2016을 [Privileged Identity Management.](/azure/active-directory/active-directory-privileged-identity-management-configure)
  

### <a name="privileged-access-management"></a>권한이 부여된 액세스 관리

권한이 부여된 액세스 관리는 테넌트의 태스크 기반 활동에 대해 JIT(Just-In-Time) 액세스를 지정하는 정책을 구성하여 적용됩니다. 이 기능은 중요한 데이터에 대한 대기 없는 액세스 권한 또는 중요한 구성 설정에 대한 액세스 권한이 부여된 기존 관리자 계정을 사용할 수 있는 보안 위반으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 예를 들어, 테넌트의 조직 사서함 설정을 액세스 및 변경하기 위해 명시적 승인을 요구하는 권한이 부여된 액세스 관리 정책을 구성할 수 있습니다.

이 단계에서는 테넌트에서 액세스 권한이 부여된 액세스 관리를 사용하도록 설정하고, 조직의 데이터 및 구성 설정에 대한 태스크 기반 액세스에 대해 추가 보안을 제공하는 권한이 부여된 액세스 정책을 구성합니다. 조직에서 권한이 부여된 액세스로 시작하려면 다음과 같은 3가지 기본 단계를 수행합니다.

- 승인자 그룹 만들기
- 권한 있는 액세스 사용
- 승인 정책 만들기

권한이 부여된 액세스 관리를 통해 조직은 제로 스위딩 권한으로 운영할 수 있으며 이러한 상주 관리 액세스로 인하여 취약점에 대한 방어 계층을 제공할 수 있습니다. 권한이 부여된 액세스에는 연결된 승인 정책이 정의된 작업을 실행하기 위한 승인이 필요합니다. 승인 정책에 포함된 작업을 실행해야 하는 사용자는 액세스 승인을 요청하고 부여해야 합니다.

권한 있는 액세스 관리를 사용하도록 설정하려면 [Configure privileged access management을 참조합니다.](/office365/securitycompliance/privileged-access-management-configuration)

자세한 내용은 [Privileged access management를 참조하십시오.](/office365/securitycompliance/privileged-access-management-overview)

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>보안 정보 및 이벤트 관리(SIEM) 로깅을 Microsoft 365 소프트웨어

서버에서 실행되는 SIEM 소프트웨어는 응용 프로그램 및 네트워크 하드웨어에서 만든 보안 경고 및 이벤트를 실시간으로 분석합니다. SIEM 서버에서 분석 및 보고 기능에 Microsoft 365 보안 경고 및 이벤트를 포함하도록 허용하기 위해 Azure AD를 SEIM에 통합합니다. 에 [대한 소개를 Azure Log Integration.](/azure/security/security-azure-log-integration-overview)

## <a name="next-step"></a>다음 단계

Microsoft 365 ID를 설정하는 경우 다음을 참조하세요.

- [클라우드 전용 ID를](cloud-only-identities.md) 사용하는 경우 클라우드 전용 ID
- [하이브리드 ID를](prepare-for-directory-synchronization.md) 사용하는 경우 디렉터리 동기화 준비

  
## <a name="see-also"></a>참고 항목

[Microsoft 365 로드맵](/office365/securitycompliance/security-roadmap)