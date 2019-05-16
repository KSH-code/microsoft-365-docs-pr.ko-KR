---
title: '4단계: 안전한 사용자 인증 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 사용자 계정에 대한 Multi-Factor Authentication을 이해하고 구성합니다.
ms.openlocfilehash: 73e884802329765fd6a89cfb7d0e04116c17968c
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072088"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="dbad0-103">4단계: 안전한 사용자 인증 구성</span><span class="sxs-lookup"><span data-stu-id="dbad0-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="dbad0-104">다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="dbad0-104">Set up multi-factor authentication</span></span>

<span data-ttu-id="dbad0-105">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="dbad0-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="dbad0-p101">이 단계에서는 MFA(다단계 인증)를 설정하여 사용자 로그인 및 트랜잭션에 두 번째 보안 계층을 추가합니다. MFA는 사용자가 암호를 올바르게 입력한 후 추가 인증 방법을 요구합니다. MFA가 없으면 암호가 유일한 인증 방법입니다. 암호의 문제는 대부분 공격자가 추측하기 쉽거나 모르는 새 신뢰할 수 없는 자와 공유된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="dbad0-110">MFA를 사용하는 경우 두 번째 보안 계층은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="dbad0-111">스마트폰과 같이 쉽게 스푸핑되거나 복제되지 않는 개인 및 신뢰할 수 있는 장치</span><span class="sxs-lookup"><span data-stu-id="dbad0-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="dbad0-112">지문과 같은 생체 인식 특성</span><span class="sxs-lookup"><span data-stu-id="dbad0-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="dbad0-p102">MFA를 사용하도록 설정하고 사용자 계정 단위로 보조 인증 방법을 구성합니다. 사용자에게 MFA가 사용 중임을 알려, 로그인하려면 스마트폰을 필수적으로 사용해야 하는 등의 요구 사항을 이해하고 성공적으로 로그인할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span>

<span data-ttu-id="dbad0-115">자세한 내용은 [Multi-Factor Authentication 계획](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbad0-115">For more information, see [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="dbad0-p103">Microsoft Office 2010 이하 및 Apple Mail과 같은 일부 응용 프로그램에서는 MFA를 사용할 수 없습니다. 이러한 앱을 사용하려면 기존 암호 대신 "앱 암호"를 사용해야 합니다. 앱 암호를 사용하면 앱이 MFA를 무시하고 계속 작동할 수 있습니다. 앱 암호에 대한 자세한 내용은 [Office 365에 대한 앱 암호 만들기](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbad0-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="dbad0-121">테스트 랩 가이드: 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="dbad0-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="dbad0-122">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-mfa)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="dbad0-123">자격 증명 손상으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="dbad0-123">Protect against credential compromise</span></span>

<span data-ttu-id="dbad0-124">*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="dbad0-124">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="dbad0-125">이 섹션에서는 공격자가 조직의 클라우드 서비스 및 데이터에 액세스하기 위한 사용자의 계정 이름 및 암호를 파악한 경우에 발생하는 자격 증명 침해로부터 보호하는 정책 구성 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-125">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="dbad0-126">Azure AD ID 보호 기능에서는 공격자가 계정 및 그룹을 거쳐 가장 귀중한 데이터까지 이동하지 못하도록 하는 다양한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-126">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="dbad0-127">Azure AD ID 보호를 사용하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-127">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="dbad0-128">조직의 ID에서 잠재적인 취약점 확인 및 해결</span><span class="sxs-lookup"><span data-stu-id="dbad0-128">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="dbad0-p105">Azure AD는 기계 학습을 사용하여 로그인 및 로그인 후 활동과 같은 의심스러운 활동과 비정상적인 상태를 감지합니다. ID 보호는 이 데이터를 사용하여 보고서를 생성하며 사용자가 문제를 평가하고 조치를 취할 수 있도록 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-p105">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="dbad0-131">조직의 ID와 관련이 있는 의심스러운 동작을 감지하고 자동으로 대응</span><span class="sxs-lookup"><span data-stu-id="dbad0-131">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="dbad0-p106">지정된 위험 수준에 도달했을 때 감지된 문제에 자동으로 대응하는 위험 기반 정책을 구성할 수 있습니다. 이러한 정책은 Azure Active Directory와 EMS(Enterprise Mobility + Security)에서 제공하는 다른 조건부 액세스 제어에 추가로 액세스를 자동으로 차단하거나 시정 조치(예: 암호 재설정, 후속 로그인에 다단계 인증 요구)를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-p106">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="dbad0-134">의심스러운 사건을 조사하여 관리 작업으로 해결</span><span class="sxs-lookup"><span data-stu-id="dbad0-134">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="dbad0-p107">보안 사건에 대한 정보를 사용하여 위험 이벤트를 조사할 수 있습니다. 기본 워크플로를 사용하여 조사를 추적하고 암호 재설정과 같은 수정 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="dbad0-137">[Azure AD ID 보호에 대한 자세한 정보](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbad0-137">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="dbad0-138">[Azure AD ID 보호를 사용하도록 설정하는 단계](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbad0-138">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="dbad0-139">이 단계를 수행하면 Azure AD ID 보호가 사용하도록 설정되며, 이를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-139">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="dbad0-140">잠재적인 ID 취약점 해결</span><span class="sxs-lookup"><span data-stu-id="dbad0-140">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="dbad0-141">가능한 자격 증명 손상 시도 감지</span><span class="sxs-lookup"><span data-stu-id="dbad0-141">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="dbad0-142">지속적인 의심스러운 ID 사건 조사 및 해결</span><span class="sxs-lookup"><span data-stu-id="dbad0-142">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="dbad0-144">테스트 랩 가이드: Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="dbad0-144">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="dbad0-145">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-ident-prot)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="dbad0-146">테넌트 및 로그인 활동 모니터링</span><span class="sxs-lookup"><span data-stu-id="dbad0-146">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="dbad0-147">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="dbad0-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="dbad0-p108">이 단계에서는 Azure AD 보고를 사용하여 감사 로그 및 로그인 활동을 검토합니다. 두 가지 유형의 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-p108">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="dbad0-p109">**감사 로그 활동 보고서**는 Azure AD 테넌트에서 수행된 모든 작업 내역을 기록합니다. 이 보고서는 다음과 같은 질문에 대한 답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-p109">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="dbad0-152">관리자 그룹에 다른 사용자를 추가한 사람은 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="dbad0-152">Who added someone to an admin group?</span></span>
- <span data-ttu-id="dbad0-153">특정 앱에 로그인 중인 사용자는 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="dbad0-153">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="dbad0-154">발생한 암호 재설정 횟수는 몇 회인가요?</span><span class="sxs-lookup"><span data-stu-id="dbad0-154">How many password resets are happening?</span></span>

<span data-ttu-id="dbad0-p110">**로그인 활동 보고서**는 감사 로그 보고서에서 보고한 작업을 수행한 사람을 기록합니다. 이 보고서는 다음과 같은 질문에 대한 답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-p110">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="dbad0-157">조사 중인 특정 사용자의 로그인 패턴은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="dbad0-157">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="dbad0-158">하루, 일주일 또는 한 달 동안 몇 번 로그인했나요?</span><span class="sxs-lookup"><span data-stu-id="dbad0-158">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="dbad0-159">이러한 로그인 시도에 실패한 횟수와 그 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="dbad0-159">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="dbad0-160">보고서 및 보고서 액세스 방법에 대한 자세한 내용은 [Azure Active Directory 보고](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbad0-160">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="dbad0-161">이 단계를 마치면 이러한 보고서에 대해 알게 되고, 계획 및 보안을 위해 보고서를 사용하여 Azure AD 이벤트 및 활동에 대한 이해를 넓힐 수 있는 방법을 파악하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbad0-161">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>



## <a name="next-step"></a><span data-ttu-id="dbad0-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dbad0-162">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="dbad0-163">사용자에 대한 액세스 간소화</span><span class="sxs-lookup"><span data-stu-id="dbad0-163">Simplify access for users</span></span>](identity-password-reset.md) |

