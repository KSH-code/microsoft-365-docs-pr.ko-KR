---
title: '4단계: 안전한 사용자 인증 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 사용자 계정에 대한 Multi-Factor Authentication을 이해하고 구성합니다.
ms.openlocfilehash: 2a4a0926a08ae8279523219a2d7a2386ea0c6742
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981849"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="7be6d-103">4단계: 안전한 사용자 인증 구성</span><span class="sxs-lookup"><span data-stu-id="7be6d-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="7be6d-104">다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="7be6d-104">Set up multi-factor authentication</span></span>

<span data-ttu-id="7be6d-105">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7be6d-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7be6d-p101">이 단계에서는 MFA(다단계 인증)를 설정하여 사용자 로그인 및 트랜잭션에 두 번째 보안 계층을 추가합니다. MFA는 사용자가 암호를 올바르게 입력한 후 추가 인증 방법을 요구합니다. MFA가 없으면 암호가 유일한 인증 방법입니다. 암호의 문제는 대부분 공격자가 추측하기 쉽거나 모르는 새 신뢰할 수 없는 자와 공유된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="7be6d-110">MFA를 사용하는 경우 두 번째 보안 계층은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="7be6d-111">스마트폰과 같이 쉽게 스푸핑되거나 복제되지 않는 개인 및 신뢰할 수 있는 장치</span><span class="sxs-lookup"><span data-stu-id="7be6d-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="7be6d-112">지문과 같은 생체 인식 특성</span><span class="sxs-lookup"><span data-stu-id="7be6d-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="7be6d-113">MFA를 사용하도록 설정하고 Azure AD(Azure Active Directory) 그룹을 사용하여 파일럿 사용자, 지리적 지역 또는 부서 등의 지정된 사용자 세트로 MFA를 롤아웃할 수 있는 [조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)을 통해 보조 인증 방법을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-113">You'll enable MFA and configure the secondary authentication method with [conditional access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="7be6d-114">사용자에게 MFA가 사용 중임을 알려, 로그인하려면 스마트폰을 필수적으로 사용해야 하는 등의 요구 사항을 이해하고 성공적으로 로그인할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-114">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="7be6d-115">자세한 내용은 [Multi-Factor Authentication 계획](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7be6d-115">For more information, see [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="7be6d-p103">Microsoft Office 2010 이하 및 Apple Mail과 같은 일부 응용 프로그램에서는 MFA를 사용할 수 없습니다. 이러한 앱을 사용하려면 기존 암호 대신 "앱 암호"를 사용해야 합니다. 앱 암호를 사용하면 앱이 MFA를 무시하고 계속 작동할 수 있습니다. 앱 암호에 대한 자세한 내용은 [Office 365에 대한 앱 암호 만들기](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7be6d-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7be6d-121">테스트 랩 가이드: 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="7be6d-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="7be6d-122">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-mfa)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="7be6d-123">잘못된 암호 방지</span><span class="sxs-lookup"><span data-stu-id="7be6d-123">Prevent bad passwords</span></span>

<span data-ttu-id="7be6d-124">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7be6d-124">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7be6d-125">사용자가 쉽게 확인할 수 있는 암호를 만들지 못하도록 하려면 전역 금지 암호 목록과 사용자가 지정한 선택적 사용자 지정 금지 암호 목록을 사용하는 Azure AD 암호 보호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-125">To prevent users from creating easily determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="7be6d-126">예를 들어, 다음과 같이 조직에 맞는 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-126">For example, you can specify terms that are specific to your organization, such as"</span></span>

- <span data-ttu-id="7be6d-127">브랜드 이름</span><span class="sxs-lookup"><span data-stu-id="7be6d-127">Brand names</span></span>
- <span data-ttu-id="7be6d-128">제품 이름</span><span class="sxs-lookup"><span data-stu-id="7be6d-128">Product names</span></span>
- <span data-ttu-id="7be6d-129">위치(예: 본사)</span><span class="sxs-lookup"><span data-stu-id="7be6d-129">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="7be6d-130">회사 관련 내부 조건</span><span class="sxs-lookup"><span data-stu-id="7be6d-130">Company-specific internal terms</span></span>
- <span data-ttu-id="7be6d-131">특정 회사 의미를 갖는 약어</span><span class="sxs-lookup"><span data-stu-id="7be6d-131">Abbreviations that have specific company meaning.</span></span>

<span data-ttu-id="7be6d-132">[클라우드](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) 및 [온-프레미스 AD DS(Active Directory Domain Services)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)에 대해 잘못된 암호를 금지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-132">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="7be6d-133">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-password-prot)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="7be6d-134">자격 증명 손상으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="7be6d-134">Protect against credential compromise</span></span>

<span data-ttu-id="7be6d-135">*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7be6d-135">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7be6d-136">이 섹션에서는 공격자가 조직의 클라우드 서비스 및 데이터에 액세스하기 위한 사용자의 계정 이름 및 암호를 파악한 경우에 발생하는 자격 증명 침해로부터 보호하는 정책 구성 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-136">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="7be6d-137">Azure AD ID 보호 기능에서는 공격자가 계정 및 그룹을 거쳐 가장 귀중한 데이터까지 이동하지 못하도록 하는 다양한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-137">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="7be6d-138">Azure AD ID 보호를 사용하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-138">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="7be6d-139">조직의 ID에서 잠재적인 취약점 확인 및 해결</span><span class="sxs-lookup"><span data-stu-id="7be6d-139">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="7be6d-140">Azure AD는 기계 학습을 사용하여 로그인 및 로그인 후 활동과 같은 변칙 및 의심스러운 활동을 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-140">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span> <span data-ttu-id="7be6d-141">이 데이터를 사용하여 Azure AD ID 보호는 문제를 평가하고 조치를 취하는 데 도움이 되는 보고서 및 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-141">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="7be6d-142">조직의 ID와 관련이 있는 의심스러운 동작을 감지하고 자동으로 대응</span><span class="sxs-lookup"><span data-stu-id="7be6d-142">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="7be6d-143">지정된 위험 수준에 도달했을 때 검색된 문제에 자동으로 대응하는 위험 기반 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-143">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="7be6d-144">Azure AD 및 Microsoft Intune에서 제공하는 다른 조건부 액세스 제어 외에도, 이러한 정책은 액세스를 자동으로 차단하거나 암호 재설정을 포함하는 수정 조치를 취하고, 후속 로그인에 대해 Multi-Factor Authentication을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-144">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="7be6d-145">의심스러운 사건을 조사하여 관리 작업으로 해결</span><span class="sxs-lookup"><span data-stu-id="7be6d-145">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="7be6d-p108">보안 사건에 대한 정보를 사용하여 위험 이벤트를 조사할 수 있습니다. 기본 워크플로를 사용하여 조사를 추적하고 암호 재설정과 같은 수정 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-p108">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="7be6d-148">[Azure AD ID 보호에 대한 자세한 정보](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7be6d-148">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="7be6d-149">[Azure AD ID 보호를 사용하도록 설정하는 단계](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7be6d-149">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="7be6d-150">이 단계를 수행하면 Azure AD ID 보호가 사용하도록 설정되며, 이를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-150">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="7be6d-151">잠재적인 ID 취약점 해결</span><span class="sxs-lookup"><span data-stu-id="7be6d-151">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="7be6d-152">가능한 자격 증명 손상 시도 감지</span><span class="sxs-lookup"><span data-stu-id="7be6d-152">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="7be6d-153">지속적인 의심스러운 ID 사건 조사 및 해결</span><span class="sxs-lookup"><span data-stu-id="7be6d-153">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7be6d-155">테스트 랩 가이드: Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="7be6d-155">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="7be6d-156">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-ident-prot)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-156">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="7be6d-157">테넌트 및 로그인 활동 모니터링</span><span class="sxs-lookup"><span data-stu-id="7be6d-157">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="7be6d-158">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7be6d-158">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7be6d-p109">이 단계에서는 Azure AD 보고를 사용하여 감사 로그 및 로그인 활동을 검토합니다. 두 가지 유형의 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-p109">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="7be6d-p110">**감사 로그 활동 보고서**는 Azure AD 테넌트에서 수행된 모든 작업 내역을 기록합니다. 이 보고서는 다음과 같은 질문에 대한 답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-p110">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="7be6d-163">관리자 그룹에 다른 사용자를 추가한 사람은 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="7be6d-163">Who added someone to an admin group?</span></span>
- <span data-ttu-id="7be6d-164">특정 앱에 로그인 중인 사용자는 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="7be6d-164">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="7be6d-165">발생한 암호 재설정 횟수는 몇 회인가요?</span><span class="sxs-lookup"><span data-stu-id="7be6d-165">How many password resets are happening?</span></span>

<span data-ttu-id="7be6d-p111">**로그인 활동 보고서**는 감사 로그 보고서에서 보고한 작업을 수행한 사람을 기록합니다. 이 보고서는 다음과 같은 질문에 대한 답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-p111">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="7be6d-168">조사 중인 특정 사용자의 로그인 패턴은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="7be6d-168">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="7be6d-169">하루, 일주일 또는 한 달 동안 몇 번 로그인했나요?</span><span class="sxs-lookup"><span data-stu-id="7be6d-169">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="7be6d-170">이러한 로그인 시도에 실패한 횟수와 그 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="7be6d-170">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="7be6d-171">보고서 및 보고서 액세스 방법에 대한 자세한 내용은 [Azure Active Directory 보고](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7be6d-171">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="7be6d-172">이 단계를 마치면 이러한 보고서에 대해 알게 되고, 계획 및 보안을 위해 보고서를 사용하여 Azure AD 이벤트 및 활동에 대한 이해를 넓힐 수 있는 방법을 파악하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7be6d-172">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="7be6d-173">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7be6d-173">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="7be6d-174">사용자에 대한 액세스 간소화</span><span class="sxs-lookup"><span data-stu-id="7be6d-174">Simplify access for users</span></span>](identity-password-reset.md) |

