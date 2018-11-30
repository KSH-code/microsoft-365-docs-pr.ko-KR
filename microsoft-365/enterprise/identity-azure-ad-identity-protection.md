---
title: '6단계: 자격 증명 손상으로부터 보호'
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
description: Azure AD ID 보호를 이해하고 구성합니다.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870363"
---
# <a name="step-6-protect-against-credential-compromise"></a><span data-ttu-id="aee73-103">6단계: 자격 증명 손상으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="aee73-103">Step 6: Protect against credential compromise</span></span>

<span data-ttu-id="aee73-104">*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="aee73-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="aee73-p101">이 단계에서는 공격자가 사용자 계정 이름 및 암호를 확인하여 조직의 클라우드 서비스와 데이터에 액세스할 수 있는 자격 증명 손상으로부터 보호하는 정책을 구성하는 방법을 알아봅니다. Azure AD ID 보호는 공격자가 사용자 계정 및 그룹을 탐색하고 이후 가장 중요한 데이터에 액세스하는 것을 방지하도록 도와주는 몇 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aee73-p101">In Step 15, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="aee73-107">Azure AD ID 보호를 사용하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee73-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="aee73-108">조직의 ID에서 잠재적인 취약점 확인 및 해결</span><span class="sxs-lookup"><span data-stu-id="aee73-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="aee73-p102">Azure AD는 기계 학습을 사용하여 로그인 및 로그인 후 활동과 같은 의심스러운 활동과 비정상적인 상태를 감지합니다. ID 보호는 이 데이터를 사용하여 보고서를 생성하며 사용자가 문제를 평가하고 조치를 취할 수 있도록 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aee73-p102">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="aee73-111">조직의 ID와 관련이 있는 의심스러운 동작을 감지하고 자동으로 대응</span><span class="sxs-lookup"><span data-stu-id="aee73-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="aee73-p103">지정된 위험 수준에 도달했을 때 감지된 문제에 자동으로 대응하는 위험 기반 정책을 구성할 수 있습니다. 이러한 정책은 Azure Active Directory와 EMS(Enterprise Mobility + Security)에서 제공하는 다른 조건부 액세스 제어에 추가로 액세스를 자동으로 차단하거나 시정 조치(예: 암호 재설정, 후속 로그인에 다단계 인증 요구)를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee73-p103">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="aee73-114">의심스러운 사건을 조사하여 관리 작업으로 해결</span><span class="sxs-lookup"><span data-stu-id="aee73-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="aee73-p104">보안 사건에 대한 정보를 사용하여 위험 이벤트를 조사할 수 있습니다. 기본 워크플로를 사용하여 조사를 추적하고 암호 재설정과 같은 수정 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee73-p104">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="aee73-117">[Azure AD ID 보호에 대한 자세한 정보](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aee73-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="aee73-118">[Azure AD ID 보호를 사용하도록 설정하는 단계](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aee73-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="aee73-119">이 단계를 수행하면 Azure AD ID 보호가 사용하도록 설정되며, 이를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee73-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="aee73-120">잠재적인 ID 취약점 해결</span><span class="sxs-lookup"><span data-stu-id="aee73-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="aee73-121">가능한 자격 증명 손상 시도 감지</span><span class="sxs-lookup"><span data-stu-id="aee73-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="aee73-122">지속적인 의심스러운 ID 사건 조사 및 해결</span><span class="sxs-lookup"><span data-stu-id="aee73-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="aee73-124">테스트 랩 가이드: Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="aee73-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="aee73-125">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-ident-prot)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee73-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="aee73-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="aee73-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="aee73-127">디렉터리 동기화</span><span class="sxs-lookup"><span data-stu-id="aee73-127">Synchronize directories</span></span>](identity-azure-ad-connect.md) |


