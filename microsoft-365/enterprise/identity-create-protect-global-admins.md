---
title: 1단계:전역 관리자 계정 생성 및 보호
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 27b76671581ebd2dac32304752a85f8a6f60ac98
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067345"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="fbfc1-103">1단계: 전역 관리자 계정 생성 및 보호</span><span class="sxs-lookup"><span data-stu-id="fbfc1-103">Step 1: Create and protect your global admin accounts</span></span>

![2단계-ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="fbfc1-105">전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="fbfc1-105">Protect global administrator accounts</span></span>

<span data-ttu-id="fbfc1-106">*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="fbfc1-106">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="fbfc1-107">이 부문에서는 관리자 계정이 최대한 보호되는지 확인하여 조직에 대한 디지털 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-107">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="fbfc1-108">이렇게 하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-108">To do this, you must:</span></span>

- <span data-ttu-id="fbfc1-109">[보안 수준이 높은 암호](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)를 사용하여 1개 이상의 전용 전역 관리자 계정을 만들고 필요한 경우에만 이를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-109">Create more than one dedicated global administrator accounts with [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="fbfc1-110">필요에 따라 IT 담당자의 사용자 계정에 특정 관리자 역할(예: Exchange 관리자 또는 암호 관리자)을 할당하여 일상적인 관리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-110">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to other dedicated accounts for those roles or user accounts of IT staff as needed.</span></span>

<span data-ttu-id="fbfc1-111">또한 전용 전역 관리자 계정에 대해 다음을 수행해야 합니다:</span><span class="sxs-lookup"><span data-stu-id="fbfc1-111">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="fbfc1-112">테스트 사용자 계정을 사용자별 계정 또는 조건부 액세스 기반 Azure MFA(다단계 인증)를 테스트하여 MFA가 예상대로 올바르게 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-112">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="fbfc1-113">MFA는 스마트폰으로 보낸 인증 코드와 같은 보조 인증 형태를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-113">MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="fbfc1-114">MFA를 필요로 하고 조직에서 사용 가능한 가장 강력한 형태의 보조 인증 형식을 사용하는 전역 관리자 계정에 대한 조건부 액세스 정책을 만들고 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-114">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="fbfc1-115">자세한 내용은 [Azure 다단계 인증](identity-access-prerequisites.md#protecting-administrator-accounts)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-115">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="fbfc1-116">추가 보호에 대한 내용은 [Office 365 전역 관리자 계정 보호](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-116">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for additional protections.</span></span>

> [!Note]
> <span data-ttu-id="fbfc1-117">사이버 공격과 같은 비상 시의 유리 파손 시나리오와 같은 비상 계정은 클라우드 전용 계정으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-117">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="fbfc1-118">또한 클라우드 전용이 아닌 전역 관리자 계정 (적격 또는 영구적)을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-118">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="fbfc1-119">자세한 내용은 [Azure AD에서 비상 액세스 관리 계정의 관리](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-119">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="fbfc1-120">이 섹션의 결과는 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="fbfc1-120">The results of this section are:</span></span>

- <span data-ttu-id="fbfc1-121">구독에서 전역 관리자 역할이 할당된 사용자 계정은 새로운 전용 전역 관리자 계정뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-121">The only user accounts in your subscription that have the global admin role are the dedicated global administrator accounts.</span></span> <span data-ttu-id="fbfc1-122">다음의 Azure Active Directory PowerShell for Graph 명령으로 이를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="fbfc1-123">구독 서비스를 관리하는 다른 모든 사용자 계정에는 업무 책임과 연관된 관리자 역할이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-123">All other user accounts that manage your subscription services have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="fbfc1-124">Azure Active Directory PowerShell for Graph 모듈 설치 및 로그인에 대한 지침은 [Office 365 PowerShell에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="fbfc1-126">테스트 랩 환경에서 이 구성을 연습하려면 [전역 관리자 계정 보호 테스트 랩 가이드](protect-global-administrator-accounts-microsoft-365-test-environment.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-126">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="fbfc1-127">중간 검사점으로 이 섹션에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-global-admin)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="fbfc1-128">온디맨드 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="fbfc1-128">Set up on-demand administrators</span></span>

<span data-ttu-id="fbfc1-129">*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="fbfc1-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="fbfc1-130">이 섹션에서는 Azure AD PIM(Privileged Identity Management)을 설정하여 관리자 계정이 악의적인 사용자의 공격에 노출되는 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="fbfc1-131">PIM은 필요한 경우, 관리자 역할이 필요할 때 온디맨드식으로 적시에 할당을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-131">PIM provides on-demand, just-in-time assignment of the administrator roles when needed.</span></span>  

<span data-ttu-id="fbfc1-132">관리자 계정을 영구적 관리자로 하는 대신에 관리자 자격을 갖춘 관리자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-132">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="fbfc1-133">사용자가 필요할 때까지 관리자 역할은 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-133">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="fbfc1-134">그런 다음 관리자 계정에 특정 시간 동안 관리자 역할을 추가하기 위한 활성화 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-134">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="fbfc1-135">시간이 만료되면 PIM이 관리자 계정에서 관리자 역할을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-135">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="fbfc1-136">PIM은 Microsoft 365 E5에 포함된 Azure Active Directory Premium P2와 함께 제공됩니다. </span><span class="sxs-lookup"><span data-stu-id="fbfc1-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="fbfc1-137">또는 관리자 계정에 대해 개별 Azure Active Directory Premium P2 라이선스를 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-137">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>

<span data-ttu-id="fbfc1-138">Azure AD 테넌트 및 관리자 계정에서 Azure PIM을 사용하도록 설정하려면 [PIM 구성 절차](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-138">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="fbfc1-139">권한 있는 액세스를 사이버 공격자로부터 보호하는 포괄적인 로드맵을 마련하려면 [Azure AD의 하이브리드 및 클라우드 배포에서 권한 있는 액세스 보호](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="fbfc1-140">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pim)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="fbfc1-141">권한이 부여된 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="fbfc1-141">Privileged access management</span></span>

<span data-ttu-id="fbfc1-p109">권한이 부여된 액세스 관리는 Office 365 테넌트의 태스크 기반 활동에 대해 JIT(Just-In-Time) 액세스를 지정하는 정책을 구성하여 적용됩니다. 이 기능은 중요한 데이터에 대한 대기 없는 액세스 권한 또는 중요한 구성 설정에 대한 액세스 권한이 부여된 기존 관리자 계정을 사용할 수 있는 보안 위반으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 예를 들어, Office 365 테넌트의 조직 사서함 설정을 액세스 및 변경하기 위해 명시적 승인을 요구하는 권한이 부여된 액세스 관리 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-p109">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="fbfc1-p110">이 단계에서는 Office 365 테넌트에서 액세스 권한이 부여된 액세스 관리를 사용하도록 설정하고, 조직의 Office 365 데이터 및 구성 설정에 대한 태스크 기반 액세스에 대해 추가 보안을 제공하는 권한이 부여된 액세스 정책을 구성합니다. Office 365 조직에서 권한이 부여된 액세스로 시작하려면 다음과 같은 3가지 기본 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-p110">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>

- <span data-ttu-id="fbfc1-147">승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="fbfc1-147">Creating an approver's group</span></span>
- <span data-ttu-id="fbfc1-148">권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="fbfc1-148">Enabling privileged access</span></span>
- <span data-ttu-id="fbfc1-149">승인 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="fbfc1-149">Creating approval policies</span></span>

<span data-ttu-id="fbfc1-p111">일단 구성되고 나면, 권한이 부여된 액세스 관리는 대기 없는 관리 액세스 권한 때문에 조직이 대기 없는 권한으로 작업하고, 발생하는 취약성에 대한 보안 계층을 제공할 수 있도록 합니다. 권한이 부여된 액세스의 경우 연결된 승인 정책이 정의된 작업을 실행하려면 승인이 필요합니다. 승인 정책에 포함된 작업을 실행해야 하는 사용자는 정책에 정의된 작업을 실행하는 데 필요한 권한을 얻기 위해 액세스 승인을 요청하고 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-p111">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="fbfc1-153">Office 365 권한이 부여된 액세스 관리를 사용하도록 설정하려면 [Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-153">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="fbfc1-154">자세한 내용은 [Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-154">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="fbfc1-156">테스트 랩 환경에서 이 구성을 연습하려면 [권한이 부여된 액세스 관리 테스트 랩 가이드](privileged-access-microsoft-365-enterprise-dev-test-environment.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-156">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="fbfc1-157">중간 검사점으로 이 단계에 해당하는 [종료 조건](identity-exit-criteria.md#crit-identity-pam)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfc1-157">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="fbfc1-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fbfc1-158">Next step</span></span>

|||
|:-------|:-----|
|![2단계](../media/stepnumbers/Step2.png)| [<span data-ttu-id="fbfc1-160">암호 보호</span><span class="sxs-lookup"><span data-stu-id="fbfc1-160">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

