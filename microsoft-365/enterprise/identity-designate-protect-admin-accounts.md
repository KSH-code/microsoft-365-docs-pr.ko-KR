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
# <a name="step-2-protect-global-administrator-accounts"></a><span data-ttu-id="a895d-103">2단계: 전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="a895d-103">Step 2: Protect global administrator accounts</span></span>

<span data-ttu-id="a895d-104">*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="a895d-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="a895d-p101">이 단계에서는 관리자 계정이 최대한 보호되는지 확인하여 조직에 대한 디지털 공격을 방지합니다. 이렇게 하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a895d-p101">In Step 5, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. To do this, you must:</span></span>

- <span data-ttu-id="a895d-107">매우 [강력한 암호](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)를 사용하여 전용 전역 관리자 계정을 만들고 필요한 경우에만 이를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a895d-107">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="a895d-108">필요에 따라 IT 담당자의 사용자 계정에 특정 관리자 역할(예: Exchange 관리자 또는 암호 관리자)을 할당하여 일상적인 관리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a895d-108">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="a895d-109">또한 전용 전역 관리자 계정에 대해 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a895d-109">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="a895d-p102">테스트 사용자 계정을 사용자별 계정 또는 조건부 액세스 기반 MFA(다단계 인증)를 테스트하여 MFA가 예상대로 올바르게 작동하는지 확인합니다. MFA는 스마트폰으로 전송되는 인증 코드와 같은 보조 인증 형식을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="a895d-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="a895d-p103">각 전용 Office 365 전역 관리자 계정에 대해 MFA를 구성하고 조직에서 사용 가능한 가장 강력한 형태의 보조 인증을 사용합니다. 자세한 내용은 [다단계 인증](identity-multi-factor-authentication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a895d-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md) for more information.</span></span>
2. <span data-ttu-id="a895d-p104">조건부 액세스 정책을 사용하여 전역 관리자 계정에 대해 MFA를 요구합니다. 자세한 내용은 [관리자 계정 보호](identity-access-prerequisites.md#protecting-administrator-accounts)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a895d-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>
4. <span data-ttu-id="a895d-p105">Office 365 Cloud App Security 정책을 사용하여 전역 관리자 계정 활동을 모니터링합니다. 자세한 내용은 [Office 365에 대한 향상된 보안 구성](infoprotect-configure-increased-security-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a895d-p105">Use an Office 365 Cloud App Security policy to monitor global administrator account activity. See [Information protection for Microsoft 365 Enterprise](infoprotect-configure-increased-security-office-365.md) for more information.</span></span>

<span data-ttu-id="a895d-118">구성에 대한 자세한 내용은 [Office 365 전역 관리자 계정 보호](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a895d-118">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="a895d-p106">조직에서는 사이버 공격과 같은 비상 시나리오를 위해 클라우드 전용 ID를 사용하여 전역 관리자와 같은 권한 있는 계정을 만들어야 합니다. 자세한 내용은 [Azure AD의 비상 액세스 관리 계정 관리](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a895d-p106">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="a895d-121">이 단계의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a895d-121">The results of this step are:</span></span>

- <span data-ttu-id="a895d-p107">구독에서 전역 관리자 역할이 있는 사용자 계정만 새로운 전용 전역 관리자 계정 집합입니다. 다음 Windows Azure AD V2 PowerShell 명령을 사용하여 이를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a895d-p107">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts. Verify this with the following Windows Azure AD V2 PowerShell command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="a895d-124">구독을 관리하는 다른 모든 일상적인 사용자 계정에는 해당 업무와 연관된 관리자 역할이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a895d-124">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="a895d-125">Azure AD V2 PowerShell 모듈 설치 및 로그인에 대한 지침은 [Office 365 PowerShell에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a895d-125">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a895d-127">테스트 랩 가이드: 전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="a895d-127">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="a895d-128">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-global-admin)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a895d-128">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a895d-129">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a895d-129">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="a895d-130">주문형 전역 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="a895d-130">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |

