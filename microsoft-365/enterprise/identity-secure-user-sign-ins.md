---
title: '3단계: 사용자 로그인 보안 및 관리'
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
description: 사용자가 Windows 장치 및 Microsoft 365에 더욱 안전하게 로그인할 수 있습니다.
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633516"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="553db-103">3단계: 사용자 로그인 보안 및 관리</span><span class="sxs-lookup"><span data-stu-id="553db-103">Step 3: Secure and manage your user sign-ins</span></span>

![2단계-ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="553db-105">비즈니스용 Windows Hello 사용</span><span class="sxs-lookup"><span data-stu-id="553db-105">Use Windows Hello for Business</span></span>

<span data-ttu-id="553db-106">*이 단계는 선택 사항이며 Microsoft 365 E3 및 E5 버전에 모두 적용됩니다*</span><span class="sxs-lookup"><span data-stu-id="553db-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="553db-107">Windows 10 Enterprise의 비즈니스용 windows Hello는 Windows 장치에 로그인할 때 암호를 강력한 2 단계 인증으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="553db-107">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="553db-108">2단계 인증 요소는 장치에 연결된 새로운 유형의 사용자 자격 증명과 생체 인식 또는 PIN입니다.</span><span class="sxs-lookup"><span data-stu-id="553db-108">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="553db-109">자세한 내용은 [비즈니스용 Windows Hello 개요](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="553db-109">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="553db-110">Azure 다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="553db-110">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="553db-111">*이 단계는 선택 사항이며 Microsoft 365 E3 및 E5 버전에 모두 적용됩니다*</span><span class="sxs-lookup"><span data-stu-id="553db-111">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="553db-112">이 단계에서는 Azure 다단계 MFA (Multi-Factor Authentication)를 설정하여 사용자 로그인 및 트랜잭션에 두 번째 보안 계층을 추가합니다.
</span><span class="sxs-lookup"><span data-stu-id="553db-112">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="553db-113">사용자가 암호를 올바르게 입력한 후 MFA는 추가 확인 방법을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="553db-113">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="553db-114">MFA가 없으면 암호가 유일한 인증 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="553db-114">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="553db-115">암호는 종종 공격자가 쉽게 추측하거나 신뢰할 수 없는 사용자와 본인도 모르게 공유되는 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="553db-115">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="553db-116">MFA를 사용하는 경우 두 번째 보안 계층은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="553db-116">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="553db-117">스마트폰과 같이 쉽게 스푸핑되거나 복제되지 않는 개인 및 신뢰할 수 있는 장치</span><span class="sxs-lookup"><span data-stu-id="553db-117">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="553db-118">지문과 같은 생체 인식 특성</span><span class="sxs-lookup"><span data-stu-id="553db-118">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="553db-119">MFA를 사용하도록 설정하고 Azure AD(Azure Active Directory) 그룹을 사용하여 파일럿 사용자, 지리적 지역 또는 부서 등의 지정된 사용자 세트로 MFA를 롤아웃할 수 있는 [조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)을 통해 보조 인증 방법을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="553db-119">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="553db-120">사용자에게 MFA가 사용 중임을 알려, 로그인하려면 스마트폰을 필수적으로 사용해야 하는 등의 요구 사항을 이해하고 성공적으로 로그인할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="553db-120">Make sure to let your users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="553db-121">자세한 내용은 [클라우드 기반 Azure 다단계 인증 배포 계획](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="553db-121">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="553db-123">테스트 랩 가이드: Azure 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="553db-123">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="553db-124">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-mfa)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="553db-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="553db-125">자격 증명 손상으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="553db-125">Protect against credential compromise</span></span>

<span data-ttu-id="553db-126">*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="553db-126">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="553db-127">이 섹션에서는 공격자가 조직의 클라우드 서비스 및 데이터에 액세스하기 위한 사용자의 계정 이름 및 암호를 파악한 경우에 발생하는 자격 증명 침해로부터 보호하는 정책 구성 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="553db-127">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="553db-128">Azure AD ID Protection은 공격자가 사용자 계정의 자격 증명을 손상시키지 못하도록 하는데 도움이 되는 다양한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="553db-128">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="553db-129">Azure AD ID 보호를 사용하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="553db-129">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="553db-130">조직의 ID에서 잠재적인 취약점 확인 및 해결</span><span class="sxs-lookup"><span data-stu-id="553db-130">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="553db-131">Azure AD는 기계 학습을 사용하여 로그인 및 로그인 후 활동과 같은 변칙 및 의심스러운 활동을 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="553db-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="553db-132">이 데이터를 사용하여 Azure AD ID 보호는 문제를 평가하고 조치를 취하는 데 도움이 되는 보고서 및 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="553db-132">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="553db-133">조직의 ID와 관련이 있는 의심스러운 동작을 감지하고 자동으로 대응</span><span class="sxs-lookup"><span data-stu-id="553db-133">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="553db-134">지정된 위험 수준에 도달했을 때 검색된 문제에 자동으로 대응하는 위험 기반 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="553db-134">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="553db-135">Azure AD 및 Microsoft Intune에서 제공하는 다른 조건부 액세스 제어 외에도, 이러한 정책은 액세스를 자동으로 차단하거나 암호 재설정을 포함하는 수정 조치를 취하고, 후속 로그인에 대해 Azure 다단계 인증을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="553db-135">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="553db-136">의심스러운 사건을 조사하여 관리 작업으로 해결</span><span class="sxs-lookup"><span data-stu-id="553db-136">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="553db-p107">보안 사건에 대한 정보를 사용하여 위험 이벤트를 조사할 수 있습니다. 기본 워크플로를 사용하여 조사를 추적하고 암호 재설정과 같은 수정 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="553db-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="553db-139">[Azure AD ID 보호에 대한 자세한 정보](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="553db-139">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="553db-140">[Azure AD ID 보호를 사용하도록 설정하는 단계](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="553db-140">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="553db-141">이 단계를 수행하면 Azure AD ID 보호가 사용하도록 설정되며, 이를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="553db-141">The results of this step are that you've enabled Azure AD Identity Protection and you are using it to:</span></span>

- <span data-ttu-id="553db-142">잠재적인 ID 취약점 해결</span><span class="sxs-lookup"><span data-stu-id="553db-142">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="553db-143">가능한 자격 증명 손상 시도 감지</span><span class="sxs-lookup"><span data-stu-id="553db-143">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="553db-144">지속적인 의심스러운 ID 사건 조사 및 해결</span><span class="sxs-lookup"><span data-stu-id="553db-144">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="553db-146">테스트 랩 가이드: Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="553db-146">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="553db-147">중간 검사점으로 이 섹션에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-ident-prot)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="553db-147">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![4단계](../media/stepnumbers/Step4.png)| [<span data-ttu-id="553db-149">사용자 계정 추가</span><span class="sxs-lookup"><span data-stu-id="553db-149">Add your user accounts</span></span>](identity-add-user-accounts.md) |
