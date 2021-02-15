---
title: Microsoft 365 전역 관리자 계정 보호
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
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
description: 이 문서에서는 Microsoft 365 구독에 대한 전역 관리자 액세스를 보호하는 데 대한 정보를 제공합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15c497e02b139ea6af4aabba9f3e9ab65a1205be
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445410"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="7bb0b-103">Microsoft 365 전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="7bb0b-103">Protect your Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="7bb0b-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7bb0b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7bb0b-105">정보 수집 및 피싱 공격을 비롯한 Microsoft 365 구독의 보안 위반은 일반적으로 Microsoft 365 전역 관리자 계정의 자격 증명을 침해하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-105">Security breaches of a Microsoft 365 subscription, including information harvesting and phishing attacks, are typically done by compromising the credentials of a Microsoft 365 global administrator account.</span></span> <span data-ttu-id="7bb0b-106">클라우드의 보안은 사용자와 Microsoft 간의 파트너 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-106">Security in the cloud is a partnership between you and Microsoft:</span></span>
  
- <span data-ttu-id="7bb0b-107">Microsoft 클라우드 서비스는 신뢰할 수 있는 보안 기반을 토대로 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-107">Microsoft cloud services are built on a foundation of trust and security.</span></span> <span data-ttu-id="7bb0b-108">Microsoft는 데이터 및 응용 프로그램을 보호하는 데 도움이 되는 보안 제어 및 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-108">Microsoft provides you security controls and capabilities to help you protect your data and applications.</span></span>
    
- <span data-ttu-id="7bb0b-109">데이터 및 ID와 보호에 대한 책임, 프레미스 리소스의 보안 및 제어하는 클라우드 구성 요소의 보안을 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-109">You own your data and identities and the responsibility for protecting them, the security of your on-premises resources, and the security of cloud components you control.</span></span>
    
<span data-ttu-id="7bb0b-110">Microsoft는 조직을 보호하는 데 도움이 되는 기능을 제공하지만 사용하는 경우만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-110">Microsoft provides capabilities to help protect your organization, but they are effective only if you use them.</span></span> <span data-ttu-id="7bb0b-111">사용하지 않는 경우 공격에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-111">If you do not use them, you may be vulnerable to attack.</span></span> <span data-ttu-id="7bb0b-112">전역 관리자 계정을 보호하기 위해 Microsoft는 다음에 대한 자세한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-112">To protect your global administrator accounts, Microsoft is here to help you with detailed instructions to:</span></span>
  
1. <span data-ttu-id="7bb0b-113">전용 Microsoft 365 전역 관리자 계정을 만들고 필요한 경우만 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-113">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary.</span></span>
    
2. <span data-ttu-id="7bb0b-114">전용 Microsoft 365 전역 관리자 계정에 대해 다단계 인증을 구성하고 가장 강력한 형태의 보조 인증을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-114">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts and use the strongest form of secondary authentication.</span></span>
    
> [!Note]
> <span data-ttu-id="7bb0b-115">이 문서에서는 전역 관리자 계정에 중점을 두지만 구독의 데이터에 액세스할 수 있는 광범위한 권한이 있는 추가 계정(예: eDiscovery 관리자 또는 보안 또는 규정 준수 관리자 계정)을 동일한 방식으로 보호해야 하는지 여부를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-115">Although this article is focused on global administrator accounts, you should consider whether additional accounts with wide-ranging permissions to access the data in your subscription, such as eDiscovery administrator or security or compliance administrator accounts, should be protected in the same way.</span></span> <br > <span data-ttu-id="7bb0b-116">전역 관리자 계정은 라이선스를 추가하지 않고 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-116">A global administrator account can be created without adding any licenses.</span></span>
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a><span data-ttu-id="7bb0b-117">1단계.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-117">Step 1.</span></span> <span data-ttu-id="7bb0b-118">전용 Microsoft 365 전역 관리자 계정을 만들고 필요한 경우만 사용</span><span class="sxs-lookup"><span data-stu-id="7bb0b-118">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary</span></span>

<span data-ttu-id="7bb0b-119">사용자 계정에 역할을 할당하는 등 전역 관리자 권한이 필요한 관리 작업은 비교적 적습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-119">There are relatively few administrative tasks, such as assigning roles to user accounts, that require global administrator privileges.</span></span> <span data-ttu-id="7bb0b-120">따라서 전역 관리자 역할이 할당된 일상적인 사용자 계정을 사용하는 대신 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-120">Therefore, instead of using everyday user accounts that have been assigned the global admin role, do these steps:</span></span>
  
1. <span data-ttu-id="7bb0b-121">전역 관리자 역할이 할당된 사용자 계정 집합을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-121">Determine the set of user accounts that have been assigned the global admin role.</span></span> <span data-ttu-id="7bb0b-122">Microsoft 365 관리 센터에서 또는 다음 Azure AD(Azure Active) Directory PowerShell for Graph 명령을 사용하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-122">You can do this in the Microsoft 365 admin center or with the following Azure Active (Azure AD) Directory PowerShell for Graph command:</span></span>
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. <span data-ttu-id="7bb0b-123">전역 관리자 역할이 할당된 사용자 계정으로 Microsoft 365 구독에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-123">Sign into your Microsoft 365 subscription with a user account that has been assigned the global admin role.</span></span>
    
3. <span data-ttu-id="7bb0b-124">최대 4개의 전용 전역 관리자 사용자 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-124">Create up to a maximum of four dedicated global administrator user accounts.</span></span> <span data-ttu-id="7bb0b-125">**12자 이상 강력한 암호를 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="7bb0b-125">**Use strong passwords at least 12 characters long.**</span></span> <span data-ttu-id="7bb0b-126">자세한 [내용은 강력한](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 암호 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-126">See [Create a strong password](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) for more information.</span></span> <span data-ttu-id="7bb0b-127">새 계정의 암호를 안전한 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-127">Store the passwords for the new accounts in a secure location.</span></span> 
    
4. <span data-ttu-id="7bb0b-128">각 새 전용 전역 관리자 사용자 계정에 전역 관리자 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-128">Assign the global admin role to each of the new dedicated global administrator user accounts.</span></span>
    
5. <span data-ttu-id="7bb0b-129">Microsoft 365에서 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-129">Sign out of Microsoft 365.</span></span>
    
6. <span data-ttu-id="7bb0b-130">새 전용 전역 관리자 사용자 계정 중 하나를 통해 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-130">Sign in with one of the new dedicated global administrator user accounts.</span></span>
    
7. <span data-ttu-id="7bb0b-131">1단계에서 전역 관리자 역할이 할당된 각 기존 사용자 계정에 대해:</span><span class="sxs-lookup"><span data-stu-id="7bb0b-131">For each existing user account that had been assigned the global admin role from step 1:</span></span>
    
  - <span data-ttu-id="7bb0b-132">전역 관리자 역할을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-132">Remove the global admin role.</span></span>
    
  - <span data-ttu-id="7bb0b-133">해당 사용자의 직무 및 책임에 적합한 관리자 역할을 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-133">Assign admin roles to the account that are appropriate to that user's job function and responsibility.</span></span> <span data-ttu-id="7bb0b-134">Microsoft 365의 다양한 관리자 역할에 대한 자세한 내용은 관리자 역할 [정보를 참조하세요.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-134">For more information about various admin roles in Microsoft 365, see [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>
    
8. <span data-ttu-id="7bb0b-135">Microsoft 365에서 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-135">Sign out of Microsoft 365.</span></span>
    
<span data-ttu-id="7bb0b-136">결과는 다음을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-136">The results should be:</span></span>
  
- <span data-ttu-id="7bb0b-137">구독에서 전역 관리자 역할이 할당된 사용자 계정은 새로운 전용 전역 관리자 계정 집합뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-137">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="7bb0b-138">다음 PowerShell 명령을 사용하여 이를 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-138">Verify this with the following PowerShell command:</span></span>
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- <span data-ttu-id="7bb0b-139">구독을 관리하는 다른 모든 일상적인 사용자 계정에는 업무 책임과 연관된 관리자 역할이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-139">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>
    
<span data-ttu-id="7bb0b-140">이 순간부터는 전역 관리자 권한이 필요한 작업에만 전용 전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-140">From this moment onward, you sign in with the dedicated global administrator accounts only for tasks that require global administrator privileges.</span></span> <span data-ttu-id="7bb0b-141">다른 모든 Microsoft 365 관리는 사용자 계정에 다른 관리 역할을 할당하여 수행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-141">All other Microsoft 365 administration must be done by assigning other administration roles to user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7bb0b-142">이 경우 일상적인 사용자 계정으로 로그인하고 전용 전역 관리자 계정으로 로그인하기 위한 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-142">This does require additional steps to sign out as your everyday user account and sign in with a dedicated global administrator account.</span></span> <span data-ttu-id="7bb0b-143">그러나 전역 관리자 작업에는 가끔씩만 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-143">But this only needs to be done occasionally for global administrator operations.</span></span> <span data-ttu-id="7bb0b-144">전역 관리자 계정 위반 후 Microsoft 365 구독을 복구하려면 훨씬 더 많은 단계가 필요하다는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-144">Consider that recovering your Microsoft 365 subscription after a global administrator account breach requires a lot more steps.</span></span>
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="7bb0b-145">2단계.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-145">Step 2.</span></span> <span data-ttu-id="7bb0b-146">전용 Microsoft 365 전역 관리자 계정에 대해 다단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="7bb0b-146">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="7bb0b-147">MFA(다단계 인증)에는 계정 이름 및 암호 이외에 추가 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-147">Multi-factor authentication (MFA) requires additional information beyond the account name and password.</span></span> <span data-ttu-id="7bb0b-148">Microsoft 365는 다음 추가 확인 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-148">Microsoft 365 supports these additional verification methods:</span></span>
  
- <span data-ttu-id="7bb0b-149">Microsoft Authenticator 앱</span><span class="sxs-lookup"><span data-stu-id="7bb0b-149">The Microsoft Authenticator app</span></span>

- <span data-ttu-id="7bb0b-150">전화 통화</span><span class="sxs-lookup"><span data-stu-id="7bb0b-150">A phone call</span></span>
    
- <span data-ttu-id="7bb0b-151">문자 메시지를 통해 임의로 생성된 확인 코드</span><span class="sxs-lookup"><span data-stu-id="7bb0b-151">A randomly generated verification code sent through a text message</span></span>
    
- <span data-ttu-id="7bb0b-152">스마트 카드(가상 또는 실제)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-152">A smart card (virtual or physical)</span></span>
    
- <span data-ttu-id="7bb0b-153">생체 인식 장치</span><span class="sxs-lookup"><span data-stu-id="7bb0b-153">A biometric device</span></span>
    
>[!Note]
><span data-ttu-id="7bb0b-154">NIST(National Institute of Standards and Technology) 표준을 준수해야 하는 조직의 경우 전화 통화 또는 문자 메시지 기반의 추가 확인 방법을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-154">For organizations that must adhere to National Institute of Standards and Technology (NIST) standards, the use of a phone call or text message-based additional verification methods are restricted.</span></span> <span data-ttu-id="7bb0b-155">자세한 [내용을 보려면 여기를](https://pages.nist.gov/800-63-FAQ/#q-b01) 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-155">Click [here](https://pages.nist.gov/800-63-FAQ/#q-b01) for the details.</span></span>
>

<span data-ttu-id="7bb0b-156">클라우드에만 저장된 사용자 계정(클라우드 전용 ID 모델)을 사용하는 중소기업인 경우 각 전용 전역 관리자 계정에 대해 스마트폰으로 전송된 전화 통화 또는 문자 메시지 확인 코드를 사용하여 MFA를 구성하도록 [MFA를](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-156">If you are a small business that is using user accounts stored only in the cloud (the cloud-only identity model), [set up MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) to configure MFA using a phone call or a text message verification code sent to a smart phone for each dedicated global administrator account.</span></span>
    
<span data-ttu-id="7bb0b-157">Microsoft 365 하이브리드 ID 모델을 사용하는 대규모 조직인 경우 더 많은 확인 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-157">If you are a larger organization that is using a Microsoft 365 hybrid identity model, you have more verification options.</span></span> <span data-ttu-id="7bb0b-158">더 강력한 보조 인증 방법을 위한 보안 인프라가 이미 있는 경우 [MFA를](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) 설정하고 적절한 확인 방법을 위해 각 전용 전역 관리자 계정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-158">If you have the security infrastructure already in place for a stronger secondary authentication method, [set up MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) and configure each dedicated global administrator account for the appropriate verification method.</span></span>
  
<span data-ttu-id="7bb0b-159">원하는 강력한 인증 방법에 대한 보안 인프라가 설정되지 않은 경우 Microsoft 365 MFA에 대해 작동할 경우 Microsoft Authenticator 앱, 전화 통화 또는 전역 관리자 계정의 스마트폰으로 전송된 문자 메시지 확인 코드를 중간 보안 조치로 사용하여 MFA로 전용 전역 관리자 계정을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-159">If the security infrastructure for the desired stronger verification method is not in place and functioning for Microsoft 365 MFA, we strongly recommend that you configure dedicated global administrator accounts with MFA using the Microsoft Authenticator app, a phone call, or a text message verification code sent to a smart phone for your global administrator accounts as an interim security measure.</span></span> <span data-ttu-id="7bb0b-160">MFA에서 제공하는 추가 보호 없이는 전용 전역 관리자 계정을 그대로 두지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-160">Do not leave your dedicated global administrator accounts without the additional protection provided by MFA.</span></span>
  
<span data-ttu-id="7bb0b-161">자세한 내용은 [Microsoft 365의 MFA를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-161">For more information, see [MFA for Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).</span></span>
  
<span data-ttu-id="7bb0b-162">MFA 및 PowerShell을 사용하여 Microsoft 365 서비스에 연결하기 위해 다음 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-162">To connect to Microsoft 365 services with MFA and PowerShell, see these articles:</span></span>

- [<span data-ttu-id="7bb0b-163">사용자 계정, 그룹 및 라이선스용 Microsoft 365용 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7bb0b-163">PowerShell for Microsoft 365 for user accounts, groups, and licenses</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="7bb0b-164">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7bb0b-164">Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [<span data-ttu-id="7bb0b-165">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7bb0b-165">Exchange Online</span></span>](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [<span data-ttu-id="7bb0b-166">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7bb0b-166">SharePoint Online</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [<span data-ttu-id="7bb0b-167">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="7bb0b-167">Skype for Business Online</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a><span data-ttu-id="7bb0b-168">엔터프라이즈 조직을 위한 추가 보호</span><span class="sxs-lookup"><span data-stu-id="7bb0b-168">Additional protections for enterprise organizations</span></span>

<span data-ttu-id="7bb0b-169">이러한 추가 방법을 사용하여 전역 관리자 계정 및 전역 관리자 계정을 사용하는 구성이 가능한 한 안전하게 유지되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-169">Use these additional methods to ensure that your global administrator account, and the configuration that you perform using it, are as secure as possible.</span></span>
  
### <a name="privileged-access-workstation"></a><span data-ttu-id="7bb0b-170">권한이 부여된 액세스 Workstation</span><span class="sxs-lookup"><span data-stu-id="7bb0b-170">Privileged access workstation</span></span>

<span data-ttu-id="7bb0b-171">권한이 높은 작업을 가능한 한 안전하게 실행하도록 보장하기 위해 PAW(권한 있는 액세스 작업)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-171">To ensure that the execution of highly privileged tasks is as secure as possible, use a privileged access workstation (PAW).</span></span> <span data-ttu-id="7bb0b-172">PAW는 전역 관리자 계정이 필요한 Microsoft 365 구성과 같은 중요한 구성 작업에만 사용되는 전용 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-172">A PAW is a dedicated computer that is only used for sensitive configuration tasks, such as Microsoft 365 configuration that requires a global administrator account.</span></span> <span data-ttu-id="7bb0b-173">이 컴퓨터는 인터넷 검색 또는 전자 메일에 매일 사용되지 않는 것이 인터넷 공격 및 위협으로부터 더 잘 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-173">Because this computer is not used daily for Internet browsing or email, it is better protected from Internet attacks and threats.</span></span>
  
<span data-ttu-id="7bb0b-174">PAW를 설정하는 방법에 대한 지침은 [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-174">For instructions on how to set up a PAW, see [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw).</span></span>

<span data-ttu-id="7bb0b-175">Azure AD 테넌트 및 관리자 계정에서 Azure PIM을 사용하도록 설정하려면 [PIM 구성 절차](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-175">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="7bb0b-176">권한 있는 액세스를 사이버 공격자로부터 보호하는 포괄적인 로드맵을 마련하려면 [Azure AD의 하이브리드 및 클라우드 배포에서 권한 있는 액세스 보호](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-176">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

### <a name="azure-ad-privileged-identity-management"></a><span data-ttu-id="7bb0b-177">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="7bb0b-177">Azure AD Privileged Identity Management</span></span>

<span data-ttu-id="7bb0b-178">전역 관리자 계정에 전역 관리자 역할을 영구적으로 할당하는 대신 Azure AD PIM(Privileged Identity Management)을 사용하여 필요할 때 전역 관리자 역할의 정시에 할당을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-178">Rather than having your global administrator accounts be permanently assigned the global administrator role, you can use Azure AD Privileged Identity Management (PIM) to enable on-demand, just-in-time assignment of the global administrator role when it is needed.</span></span>
  
<span data-ttu-id="7bb0b-179">전역 관리자 계정은 영구 관리자에서 적격 관리자로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-179">Your global administrator accounts go from being permanent admins to eligible admins.</span></span> <span data-ttu-id="7bb0b-180">전역 관리자 역할은 누군가가 필요로 할 때까지 비활성입니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-180">The global administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="7bb0b-181">그런 다음 정품 인증 프로세스를 완료하여 미리 정해진 기간 동안 전역 관리자 계정에 전역 관리자 역할을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-181">You then complete an activation process to add the global administrator role to the global administrator account for a predetermined amount of time.</span></span> <span data-ttu-id="7bb0b-182">시간이 만료되면 PIM은 전역 관리자 계정에서 전역 관리자 역할을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-182">When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>
  
<span data-ttu-id="7bb0b-183">PIM을 사용하고 이 프로세스를 통해 전역 관리자 계정이 악의적인 사용자의 공격 및 사용에 취약해집니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-183">Using PIM and this process significantly reduces the amount of time that your global administrator accounts are vulnerable to attack and use by malicious users.</span></span>

<span data-ttu-id="7bb0b-184">PIM은 Microsoft 365 E5에 포함된 Azure Active Directory Premium P2와 함께 제공됩니다. </span><span class="sxs-lookup"><span data-stu-id="7bb0b-184">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="7bb0b-185">또는 관리자 계정에 대해 개별 Azure Active Directory Premium P2 라이선스를 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-185">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>
  
<span data-ttu-id="7bb0b-186">자세한 내용은 [Azure AD Privileged Identity Management를 참조하세요.](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-186">For more information, see [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>
  

### <a name="privileged-access-management"></a><span data-ttu-id="7bb0b-187">권한이 부여된 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="7bb0b-187">Privileged access management</span></span>

<span data-ttu-id="7bb0b-p121">권한이 부여된 액세스 관리는 테넌트의 태스크 기반 활동에 대해 JIT(Just-In-Time) 액세스를 지정하는 정책을 구성하여 적용됩니다. 이 기능은 중요한 데이터에 대한 대기 없는 액세스 권한 또는 중요한 구성 설정에 대한 액세스 권한이 부여된 기존 관리자 계정을 사용할 수 있는 보안 위반으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 예를 들어, 테넌트의 조직 사서함 설정을 액세스 및 변경하기 위해 명시적 승인을 요구하는 권한이 부여된 액세스 관리 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-p121">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="7bb0b-p122">이 단계에서는 테넌트에서 액세스 권한이 부여된 액세스 관리를 사용하도록 설정하고, 조직의 데이터 및 구성 설정에 대한 태스크 기반 액세스에 대해 추가 보안을 제공하는 권한이 부여된 액세스 정책을 구성합니다. 조직에서 권한이 부여된 액세스로 시작하려면 다음과 같은 3가지 기본 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-p122">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization. There are three basic steps to get started with privileged access in your organization:</span></span>

- <span data-ttu-id="7bb0b-193">승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="7bb0b-193">Creating an approver's group</span></span>
- <span data-ttu-id="7bb0b-194">권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="7bb0b-194">Enabling privileged access</span></span>
- <span data-ttu-id="7bb0b-195">승인 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="7bb0b-195">Creating approval policies</span></span>

<span data-ttu-id="7bb0b-196">권한이 부여된 액세스 관리를 통해 조직은 0인 권한으로 운영할 수 있으며 이러한 상주 관리 액세스로 인하여 취약점에 대한 방어 계층을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-196">Privileged access management enables your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="7bb0b-197">권한이 부여된 액세스에는 연결된 승인 정책이 정의된 작업을 실행하기 위한 승인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-197">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="7bb0b-198">승인 정책에 포함된 작업을 실행해야 하는 사용자는 액세스 승인을 요청하고 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-198">Users needing to execute tasks included in the approval policy must request and be granted access approval.</span></span>

<span data-ttu-id="7bb0b-199">권한이 부여된 액세스 관리를 사용하도록 설정하려면 권한 있는 액세스 관리 [구성을 참조합니다.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-199">To enable privileged access management, see [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span></span>

<span data-ttu-id="7bb0b-200">자세한 내용은 [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-200">For more information, see [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a><span data-ttu-id="7bb0b-201">Microsoft 365 로깅을 위한 SIEM(보안 정보 및 이벤트 관리) 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="7bb0b-201">Security information and event management (SIEM) software for Microsoft 365 logging</span></span>

<span data-ttu-id="7bb0b-202">서버에서 실행되는 SIEM 소프트웨어는 응용 프로그램 및 네트워크 하드웨어에 의해 생성된 보안 경고 및 이벤트에 대한 실시간 분석을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-202">SIEM software run on a server performs real-time analysis of security alerts and events created by applications and network hardware.</span></span> <span data-ttu-id="7bb0b-203">SIEM 서버가 Microsoft 365 보안 경고 및 이벤트를 분석 및 보고 기능에 포함하도록 허용하기 위해 Azure AD를 SEIM에 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-203">To allow your SIEM server to include Microsoft 365 security alerts and events in its analysis and reporting functions, integrate Azure AD into you SEIM.</span></span> <span data-ttu-id="7bb0b-204">[Azure 로그 통합 소개를 참조하세요.](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-204">See [Introduction to Azure Log Integration](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview).</span></span>

## <a name="next-step"></a><span data-ttu-id="7bb0b-205">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7bb0b-205">Next step</span></span>

<span data-ttu-id="7bb0b-206">Microsoft 365 구독의 ID를 설정하는 경우 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-206">If you're setting up identity for your Microsoft 365 subscription, see:</span></span>

- <span data-ttu-id="7bb0b-207">[클라우드 전용 ID를](cloud-only-identities.md) 사용하는 경우 클라우드 전용 ID</span><span class="sxs-lookup"><span data-stu-id="7bb0b-207">[Cloud-only identities](cloud-only-identities.md) if you're using cloud-only identity</span></span>
- <span data-ttu-id="7bb0b-208">[하이브리드 ID를 사용하는](prepare-for-directory-synchronization.md) 경우 디렉터리 동기화 준비</span><span class="sxs-lookup"><span data-stu-id="7bb0b-208">[Prepare for directory synchronization](prepare-for-directory-synchronization.md) if you're using hybrid identity</span></span>

  
## <a name="see-also"></a><span data-ttu-id="7bb0b-209">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bb0b-209">See also</span></span>

[<span data-ttu-id="7bb0b-210">Microsoft 365 보안 로드맵</span><span class="sxs-lookup"><span data-stu-id="7bb0b-210">Microsoft 365 security roadmap</span></span>](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
