---
title: '2단계: 전역 관리자 계정 보호'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 관리자 계정을 이해하고 최대한 보호하도록 구성합니다.
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870356"
---
# <a name="step-2-protect-global-administrator-accounts"></a>2단계: 전역 관리자 계정 보호

*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

이 단계에서는 관리자 계정이 최대한 보호되는지 확인하여 조직에 대한 디지털 공격을 방지합니다. 이렇게 하려면 다음을 수행해야 합니다.

- 매우 [강력한 암호](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)를 사용하여 전용 전역 관리자 계정을 만들고 필요한 경우에만 이를 사용합니다.
- 필요에 따라 IT 담당자의 사용자 계정에 특정 관리자 역할(예: Exchange 관리자 또는 암호 관리자)을 할당하여 일상적인 관리를 수행합니다.

또한 전용 전역 관리자 계정에 대해 다음을 수행해야 합니다.

1. 테스트 사용자 계정을 사용자별 계정 또는 조건부 액세스 기반 MFA(다단계 인증)를 테스트하여 MFA가 예상대로 올바르게 작동하는지 확인합니다. MFA는 스마트폰으로 전송되는 인증 코드와 같은 보조 인증 형식을 요구합니다.
2. 각 전용 Office 365 전역 관리자 계정에 대해 MFA를 구성하고 조직에서 사용 가능한 가장 강력한 형태의 보조 인증을 사용합니다. 자세한 내용은 [다단계 인증](identity-multi-factor-authentication.md)을 참조하세요.
2. 조건부 액세스 정책을 사용하여 전역 관리자 계정에 대해 MFA를 요구합니다. 자세한 내용은 [관리자 계정 보호](identity-access-prerequisites.md#protecting-administrator-accounts)를 참조하세요.
4. Office 365 Cloud App Security 정책을 사용하여 전역 관리자 계정 활동을 모니터링합니다. 자세한 내용은 [Office 365에 대한 향상된 보안 구성](infoprotect-configure-increased-security-office-365.md)을 참조하세요.

구성에 대한 자세한 내용은 [Office 365 전역 관리자 계정 보호](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)를 참조하세요.

> [!Note]
> 조직에서는 사이버 공격과 같은 비상 시나리오를 위해 클라우드 전용 ID를 사용하여 전역 관리자와 같은 권한 있는 계정을 만들어야 합니다. 자세한 내용은 [Azure AD의 비상 액세스 관리 계정 관리](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)를 참조하세요.

이 단계의 결과는 다음과 같습니다.

- 구독에서 전역 관리자 역할이 있는 사용자 계정만 새로운 전용 전역 관리자 계정 집합입니다. 다음 Windows Azure AD V2 PowerShell 명령을 사용하여 이를 확인하세요. 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- 구독을 관리하는 다른 모든 일상적인 사용자 계정에는 해당 업무와 연관된 관리자 역할이 할당되어 있습니다.

> [!Note]
> Azure AD V2 PowerShell 모듈 설치 및 로그인에 대한 지침은 [Office 365 PowerShell에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)을 참조하세요.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 전역 관리자 계정 보호](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-global-admin)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [주문형 전역 관리자 설정](identity-privileged-identity-management.md) |

