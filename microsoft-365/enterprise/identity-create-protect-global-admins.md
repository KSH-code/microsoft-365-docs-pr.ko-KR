---
title: 1단계:전역 관리자 계정 생성 및 보호
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 전역 관리자 계정은 자격 증명의 노출로부터 안전하게 유지하기 위해 특별한 처리가 필요합니다.
ms.openlocfilehash: 72de7d683a9c2a080f7be69e585d16d8122cd46d
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370215"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>1단계: 전역 관리자 계정 생성 및 보호

![2단계-ID](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>전역 관리자 계정 보호

*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 부문에서는 관리자 계정이 최대한 보호되는지 확인하여 조직에 대한 디지털 공격을 방지합니다. 이렇게 하려면 다음을 수행해야 합니다.

- [보안 수준이 높은 암호](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)를 사용하여 1개 이상의 전용 전역 관리자 계정을 만들고 필요한 경우에만 이를 사용합니다.
- 필요에 따라 IT 담당자의 사용자 계정에 특정 관리자 역할(예: Exchange 관리자 또는 암호 관리자)을 할당하여 일상적인 관리를 수행합니다.

또한 전용 전역 관리자 계정에 대해 다음을 수행해야 합니다:

1. 테스트 사용자 계정을 사용자별 계정 또는 조건부 액세스 기반 Azure MFA(다단계 인증)를 테스트하여 MFA가 예상대로 올바르게 작동하는지 확인합니다. MFA는 스마트폰으로 보낸 인증 코드와 같은 보조 인증 형태를 필요로 합니다.
2. MFA를 필요로 하고 조직에서 사용 가능한 가장 강력한 형태의 보조 인증 형식을 사용하는 전역 관리자 계정에 대한 조건부 액세스 정책을 만들고 활성화합니다. 자세한 내용은 [Azure 다단계 인증](identity-access-prerequisites.md#protecting-administrator-accounts)을 참조하세요.

추가 보호에 대한 내용은 [Office 365 전역 관리자 계정 보호](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations)를 참조하세요.

> [!Note]
> 사이버 공격과 같은 비상 시의 유리 파손 시나리오와 같은 비상 계정은 클라우드 전용 계정으로 만들어야 합니다. 또한 클라우드 전용이 아닌 전역 관리자 계정 (적격 또는 영구적)을 사용할 수도 있습니다. 자세한 내용은 [Azure AD에서 비상 액세스 관리 계정의 관리](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)를 참조하세요.

이 섹션의 결과는 다음과 같습니다:

- 구독에서 전역 관리자 역할이 할당된 사용자 계정은 새로운 전용 전역 관리자 계정뿐입니다. 다음의 Azure Active Directory PowerShell for Graph 명령으로 이를 확인하십시오. 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- 구독 서비스를 관리하는 다른 모든 사용자 계정에는 업무 책임과 연관된 관리자 역할이 할당되어 있습니다.

> [!Note]
> Azure Active Directory PowerShell for Graph 모듈 설치 및 로그인에 대한 지침은 [Office 365 PowerShell에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)을 참조하십시오.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  테스트 랩 환경에서 이 구성을 연습하려면 [전역 관리자 계정 보호 테스트 랩 가이드](protect-global-administrator-accounts-microsoft-365-test-environment.md)를 참조하세요. |
|||

중간 검사점으로 이 섹션에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-global-admin)을 확인할 수 있습니다.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>온디맨드 관리자 설정

*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*

이 섹션에서는 Azure AD PIM(Privileged Identity Management)을 설정하여 관리자 계정이 악의적인 사용자의 공격에 노출되는 시간을 줄일 수 있습니다. PIM은 필요한 경우, 관리자 역할이 필요할 때 온디맨드식으로 적시에 할당을 제공합니다.  

관리자 계정을 영구적 관리자로 하는 대신에 관리자 자격을 갖춘 관리자가 됩니다. 사용자가 필요할 때까지 관리자 역할은 비활성화됩니다. 그런 다음 관리자 계정에 특정 시간 동안 관리자 역할을 추가하기 위한 활성화 프로세스를 완료 합니다. 시간이 만료되면 PIM이 관리자 계정에서 관리자 역할을 제거합니다.

PIM은 Microsoft 365 Enterprise E5에 포함된 Azure Active Directory Premium P2와 함께 가용합니다. 또는 관리자 계정에 대해 개별 Azure Active Directory Premium P2 라이선스를 구매할 수 있습니다.

Azure AD 테넌트 및 관리자 계정에서 Azure PIM을 사용하도록 설정하려면 [PIM 구성 절차](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)를 참조하세요.

권한 있는 액세스를 사이버 공격자로부터 보호하는 포괄적인 로드맵을 마련하려면 [Azure AD의 하이브리드 및 클라우드 배포에서 권한 있는 액세스 보호](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)를 참조하세요.

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pim)을 확인할 수 있습니다.


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>권한이 부여된 액세스 관리

권한이 부여된 액세스 관리는 Office 365 테넌트의 태스크 기반 활동에 대해 JIT(Just-In-Time) 액세스를 지정하는 정책을 구성하여 적용됩니다. 이 기능은 중요한 데이터에 대한 대기 없는 액세스 권한 또는 중요한 구성 설정에 대한 액세스 권한이 부여된 기존 관리자 계정을 사용할 수 있는 보안 위반으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 예를 들어, Office 365 테넌트의 조직 사서함 설정을 액세스 및 변경하기 위해 명시적 승인을 요구하는 권한이 부여된 액세스 관리 정책을 구성할 수 있습니다.

이 단계에서는 Office 365 테넌트에서 액세스 권한이 부여된 액세스 관리를 사용하도록 설정하고, 조직의 Office 365 데이터 및 구성 설정에 대한 태스크 기반 액세스에 대해 추가 보안을 제공하는 권한이 부여된 액세스 정책을 구성합니다. Office 365 조직에서 권한이 부여된 액세스로 시작하려면 다음과 같은 3가지 기본 단계를 수행합니다.

- 승인자 그룹 만들기
- 권한 있는 액세스 사용
- 승인 정책 만들기

일단 구성되고 나면, 권한이 부여된 액세스 관리는 대기 없는 관리 액세스 권한 때문에 조직이 대기 없는 권한으로 작업하고, 발생하는 취약성에 대한 보안 계층을 제공할 수 있도록 합니다. 권한이 부여된 액세스의 경우 연결된 승인 정책이 정의된 작업을 실행하려면 승인이 필요합니다. 승인 정책에 포함된 작업을 실행해야 하는 사용자는 정책에 정의된 작업을 실행하는 데 필요한 권한을 얻기 위해 액세스 승인을 요청하고 받아야 합니다.

Office 365 권한이 부여된 액세스 관리를 사용하도록 설정하려면 [Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 항목을 참조하세요.

자세한 내용은 [Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) 항목을 참조하세요.


|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  테스트 랩 환경에서 이 구성을 연습하려면 [권한이 부여된 액세스 관리 테스트 랩 가이드](privileged-access-microsoft-365-enterprise-dev-test-environment.md)를 참조하세요. |
|||

중간 검사점으로 이 단계에 해당하는 [종료 조건](identity-exit-criteria.md#crit-identity-pam)을 확인하세요.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![2단계](./media/stepnumbers/Step2.png)| [암호 보호](identity-secure-your-passwords.md) |

