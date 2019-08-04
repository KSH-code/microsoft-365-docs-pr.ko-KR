---
title: '2단계: 권한이 부여된 ID 보안'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 관리자 계정의 최대 보호를 위한 계정의 이해 및 구성.
ms.openlocfilehash: 8a1d232ffc0242766d79b2e4884582f3b5524d22
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074058"
---
# <a name="step-2-secure-your-privileged-identities"></a>2단계: 권한이 부여된 ID 보안

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>전역 관리자 계정 보호

*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 부문에서는 관리자 계정이 최대한 보호되는지 확인하여 조직에 대한 디지털 공격을 방지합니다. 이렇게 하려면 다음을 수행해야 합니다.

- 매우 [강력한 암호](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)를 사용하여 전용 전역 관리자 계정을 만들고 필요한 경우에만 이를 사용합니다.
- 필요에 따라 IT 담당자의 사용자 계정에 특정 관리자 역할(예: Exchange 관리자 또는 암호 관리자)을 할당하여 일상적인 관리를 수행합니다.

또한 전용 전역 관리자 계정에 대해 다음을 수행해야 합니다.

1. 테스트 사용자 계정을 사용자별 계정 또는 조건부 액세스 기반 MFA(다단계 인증)를 테스트하여 MFA가 예상대로 올바르게 작동하는지 확인합니다. MFA는 스마트폰으로 전송되는 인증 코드와 같은 보조 인증 형식을 요구합니다.
2. 각 전용 Office 365 전역 관리자 계정에 대해 MFA를 구성하고 조직에서 사용 가능한 가장 강력한 형태의 보조 인증을 사용합니다. 자세한 내용은 [다단계 인증](identity-multi-factor-authentication.md#identity-mfa)을 참조하세요.
2. 조건부 액세스 정책을 사용하여 전역 관리자 계정에 대해 MFA를 요구합니다. 자세한 내용은 [관리자 계정 보호](identity-access-prerequisites.md#protecting-administrator-accounts)를 참조하세요.

구성에 대한 자세한 내용은 [Office 365 전역 관리자 계정 보호](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)를 참조하세요.

> [!Note]
> 조직에서는 사이버 공격과 같은 비상 시나리오를 위해 클라우드 전용 ID를 사용하여 전역 관리자와 같은 권한 있는 계정을 만들어야 합니다. 자세한 내용은 [Azure AD의 비상 액세스 관리 계정 관리](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)를 참조하세요.

이 부문의 결과는 다음과 같습니다:

- 구독에서 전역 관리자 역할이 할당된 사용자 계정은 새로운 전용 전역 관리자 계정 집합뿐입니다. 다음의 Azure Active Directory PowerShell for Graph 명령으로 이를 확인하십시오. 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- 구독을 관리하는 다른 모든 일상적인 사용자 계정에는 업무 책임과 연관된 관리자 역할이 할당되어 있습니다.

> [!Note]
> Azure Active Directory PowerShell for Graph 모듈 설치 및 로그인에 대한 지침은 [Office 365 PowerShell에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)을 참조하십시오.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 전역 관리자 계정 보호](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-global-admin)을 확인할 수 있습니다.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a>주문형 전역 관리자 설정

*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*

이 부문에서는 Azure AD PIM(Privileged Identity Management)을 설정하여 전역 관리자 계정이 악의적인 사용자의 공격에 노출되는 시간을 줄일 수 있습니다. PIM은 필요한 경우, 전역 관리자 역할이 필요할 때 적시에 할당을 제공합니다.  

전역 관리자 계정은 영구 관리자가 되지 않고 적격 관리자가 됩니다. 전역 관리자 역할은 누군가가 필요로 하기 전까지는 비활성화되어 있습니다. 그러면 활성화 프로세스를 완료하여 일정 기간 전역 관리자 계정에 전역 관리자 역할을 추가합니다. 시간이 만료되면 PIM은 전역 관리자 계정에서 전역 관리자 역할을 제거합니다.

PIM은 Microsoft 365 Enterprise E5에 포함된 Azure Active Directory Premium P2에서 제공됩니다. 또는 전역 관리자 계정용 개별 Azure Active Directory Premium P2 라이선스를 구매할 수 있습니다.

Azure AD 테넌트 및 전역 관리자 계정에서 Azure PIM을 사용하도록 설정하려면 [PIM 구성 방법](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)을 참조하세요.

권한 있는 액세스를 사이버 공격자로부터 보호하는 포괄적인 로드맵을 마련하려면 [Azure AD의 하이브리드 및 클라우드 배포에서 권한 있는 액세스 보호](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)를 참조하세요.

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pim)을 확인할 수 있습니다.


## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [하이브리드 ID 구성](identity-azure-ad-connect.md) |

