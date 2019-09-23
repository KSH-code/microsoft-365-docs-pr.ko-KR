---
title: '7단계: ID 거버넌스 구성'
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
description: Azure AD 테넌트에 대한 ID 거버넌스를 이해하고 구성합니다.
ms.openlocfilehash: 1c0eab574e5436dd0c88a0b46d1916281bcf0577
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047361"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="659a5-103">7단계: ID 거버넌스 구성</span><span class="sxs-lookup"><span data-stu-id="659a5-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="659a5-104">ID 거버넌스는 직원 생산성을 보장하면서 중요한 자산에 대한 액세스를 보호, 모니터링 및 감사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="659a5-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="659a5-105">예를 들어 ID 거버넌스를 사용하는 경우 올바른 사용자에게 올바른 리소스에 대한 올바른 액세스 권한이 있는지 확인하고, 해당 액세스 권한이 시간에 따라 변경되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659a5-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="659a5-106">Azure ID(Azure Active Directory)의 ID 거버넌스에 대한 자세한 내용은 [이 문서](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="659a5-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="659a5-107">Azure AD 액세스 검토 설정</span><span class="sxs-lookup"><span data-stu-id="659a5-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="659a5-108">*이 단계는 선택사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="659a5-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="659a5-109">이 단계에서는 Azure AD 액세스 검토를 설정하여 사용자의 액세스를 검토함으로써 올바른 사용자만 계속 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="659a5-109">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="659a5-110">예:</span><span class="sxs-lookup"><span data-stu-id="659a5-110">For example:</span></span>

- <span data-ttu-id="659a5-111">새 직원이 조직에 들어오면 올바른 액세스 권한을 제공하여 생산적으로 작업할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="659a5-111">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="659a5-112">해당 직원이 다른 팀, 위치 또는 부서로 이동하게 되면 필요에 따라 이전 팀, 위치 또는 부서에 대한 액세스 권한이 제거되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="659a5-112">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="659a5-113">해당 직원이나 게스트가 조직에서 나갈 때 해당 액세스 권한이 제거되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="659a5-113">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="659a5-114">이러한 작업은 조직이 사용자 계정에 너무 많은 액세스 권한이 있는지 확인하고 산업 또는 지역 규정을 위반할 경우 벌금을 매길 수 있는 보안 감사를 받고 있는 경우에 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="659a5-114">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="659a5-115">Azure AD 액세스 검토에 대한 자세한 내용은 [이 문서](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="659a5-115">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="659a5-116">다양한 유형의 액세스 검토를 구성하려면 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="659a5-116">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="659a5-117">그룹 및 앱</span><span class="sxs-lookup"><span data-stu-id="659a5-117">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="659a5-118">Azure AD 역할</span><span class="sxs-lookup"><span data-stu-id="659a5-118">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="659a5-119">Azure 리소스 역할</span><span class="sxs-lookup"><span data-stu-id="659a5-119">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="659a5-120">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-access-reviews)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659a5-120">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="659a5-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="659a5-121">Next step</span></span>

[<span data-ttu-id="659a5-122">ID 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="659a5-122">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

