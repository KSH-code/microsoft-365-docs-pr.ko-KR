---
title: '2단계: 권한이 부여된 ID 보안'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 관리자 계정의 최대 보호를 위한 계정의 이해 및 구성.
ms.openlocfilehash: 0be82fc6f431001c69e79a0a26007c54a87424c3
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353090"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="213f4-103">2단계: 권한이 부여된 ID 보안</span><span class="sxs-lookup"><span data-stu-id="213f4-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="213f4-104">전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="213f4-104">Protect global administrator accounts</span></span>

<span data-ttu-id="213f4-105">*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="213f4-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="213f4-106">이 부문에서는 관리자 계정이 최대한 보호되는지 확인하여 조직에 대한 디지털 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="213f4-107">이렇게 하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-107">To do this, you must:</span></span>

- <span data-ttu-id="213f4-108">매우 [강력한 암호](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)를 사용하여 전용 전역 관리자 계정을 만들고 필요한 경우에만 이를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="213f4-109">필요에 따라 IT 담당자의 사용자 계정에 특정 관리자 역할(예: Exchange 관리자 또는 암호 관리자)을 할당하여 일상적인 관리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="213f4-110">또한 전용 전역 관리자 계정에 대해 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="213f4-p102">테스트 사용자 계정을 사용자별 계정 또는 조건부 액세스 기반 MFA(다단계 인증)를 테스트하여 MFA가 예상대로 올바르게 작동하는지 확인합니다. MFA는 스마트폰으로 전송되는 인증 코드와 같은 보조 인증 형식을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="213f4-p103">각 전용 Office 365 전역 관리자 계정에 대해 MFA를 구성하고 조직에서 사용 가능한 가장 강력한 형태의 보조 인증을 사용합니다. 자세한 내용은 [다단계 인증](identity-multi-factor-authentication.md#identity-mfa)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="213f4-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) for more information.</span></span>
2. <span data-ttu-id="213f4-p104">조건부 액세스 정책을 사용하여 전역 관리자 계정에 대해 MFA를 요구합니다. 자세한 내용은 [관리자 계정 보호](identity-access-prerequisites.md#protecting-administrator-accounts)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="213f4-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="213f4-117">구성에 대한 자세한 내용은 [Office 365 전역 관리자 계정 보호](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="213f4-117">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="213f4-p105">조직에서는 사이버 공격과 같은 비상 시나리오를 위해 클라우드 전용 ID를 사용하여 전역 관리자와 같은 권한 있는 계정을 만들어야 합니다. 자세한 내용은 [Azure AD의 비상 액세스 관리 계정 관리](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="213f4-p105">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="213f4-120">이 부문의 결과는 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="213f4-120">The results of this section are:</span></span>

- <span data-ttu-id="213f4-121">구독에서 전역 관리자 역할이 할당된 사용자 계정은 새로운 전용 전역 관리자 계정 집합뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-121">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="213f4-122">다음의 Azure Active Directory PowerShell for Graph 명령으로 이를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="213f4-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="213f4-123">구독을 관리하는 다른 모든 일상적인 사용자 계정에는 업무 책임과 연관된 관리자 역할이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-123">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="213f4-124">Azure Active Directory PowerShell for Graph 모듈 설치 및 로그인에 대한 지침은 [Office 365 PowerShell에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="213f4-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="213f4-126">테스트 랩 가이드: 전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="213f4-126">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="213f4-127">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-global-admin)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="213f4-128">주문형 전역 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="213f4-128">Set up on-demand global administrators</span></span>

<span data-ttu-id="213f4-129">*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="213f4-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="213f4-130">이 부문에서는 Azure AD PIM(Privileged Identity Management)을 설정하여 전역 관리자 계정이 악의적인 사용자의 공격에 노출되는 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="213f4-131">PIM은 필요한 경우, 전역 관리자 역할이 필요할 때 적시에 할당을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-131">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="213f4-p108">전역 관리자 계정은 영구 관리자가 되지 않고 적격 관리자가 됩니다. 전역 관리자 역할은 누군가가 필요로 하기 전까지는 비활성화되어 있습니다. 그러면 활성화 프로세스를 완료하여 일정 기간 전역 관리자 계정에 전역 관리자 역할을 추가합니다. 시간이 만료되면 PIM은 전역 관리자 계정에서 전역 관리자 역할을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-p108">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="213f4-p109">PIM은 Microsoft 365 Enterprise E5에 포함된 Azure Active Directory Premium P2에서 제공됩니다. 또는 전역 관리자 계정용 개별 Azure Active Directory Premium P2 라이선스를 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-p109">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="213f4-138">Azure AD 테넌트 및 전역 관리자 계정에서 Azure PIM을 사용하도록 설정하려면 [PIM 구성 방법](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="213f4-138">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="213f4-139">권한 있는 액세스를 사이버 공격자로부터 보호하는 포괄적인 로드맵을 마련하려면 [Azure AD의 하이브리드 및 클라우드 배포에서 권한 있는 액세스 보호](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="213f4-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="213f4-140">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pim)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="213f4-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="213f4-141">다음 단계</span><span class="sxs-lookup"><span data-stu-id="213f4-141">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="213f4-142">하이브리드 ID 구성</span><span class="sxs-lookup"><span data-stu-id="213f4-142">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

