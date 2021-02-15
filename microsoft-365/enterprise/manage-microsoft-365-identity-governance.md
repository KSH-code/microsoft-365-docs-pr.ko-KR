---
title: Microsoft 365 ID 거버넌스 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 ID 거버넌스 기능을 사용하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370349"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="8e24c-103">Microsoft 365 ID 거버넌스 관리</span><span class="sxs-lookup"><span data-stu-id="8e24c-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="8e24c-104">ID 거버넌스는 직원 생산성을 보장하면서 중요한 자산에 대한 액세스를 보호, 모니터링 및 감사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="8e24c-105">예를 들어 ID 거버넌스를 사용하는 경우 올바른 사용자에게 올바른 리소스에 대한 올바른 액세스 권한이 있는지 확인하고, 해당 액세스 권한이 시간에 따라 변경되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="8e24c-106">자세한 내용은 Azure AD(Azure Active Directory)에 대한 ID [거버넌스 개요를 참조하세요.](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)</span><span class="sxs-lookup"><span data-stu-id="8e24c-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="8e24c-107">Azure AD 액세스 검토 설정</span><span class="sxs-lookup"><span data-stu-id="8e24c-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="8e24c-108">Azure AD 액세스 검토를 사용하면 사용자 액세스를 검토하여 올바른 사용자만 계속 액세스할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="8e24c-109">예:</span><span class="sxs-lookup"><span data-stu-id="8e24c-109">For example:</span></span>

- <span data-ttu-id="8e24c-110">새 직원이 조직에 들어오면 올바른 액세스 권한을 제공하여 생산적으로 작업할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="8e24c-111">해당 직원이 다른 팀, 위치 또는 부서로 이동하게 되면 필요에 따라 이전 팀, 위치 또는 부서에 대한 액세스 권한이 제거되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="8e24c-112">해당 직원이나 게스트가 조직에서 나갈 때 해당 액세스 권한이 제거되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="8e24c-113">이러한 작업은 조직이 사용자 계정에 너무 많은 액세스 권한이 있는지 확인하고 산업 또는 지역 규정을 위반할 경우 벌금을 매길 수 있는 보안 감사를 받고 있는 경우에 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="8e24c-114">자세한 내용은 액세스 검토 [개요를 참조하세요.](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)</span><span class="sxs-lookup"><span data-stu-id="8e24c-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="8e24c-115">다양한 유형의 액세스 검토를 구성하려면 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e24c-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="8e24c-116">그룹 및 앱</span><span class="sxs-lookup"><span data-stu-id="8e24c-116">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="8e24c-117">Azure AD 역할</span><span class="sxs-lookup"><span data-stu-id="8e24c-117">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="8e24c-118">Azure 리소스 역할</span><span class="sxs-lookup"><span data-stu-id="8e24c-118">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="8e24c-119">Azure AD 권리 관리 설정</span><span class="sxs-lookup"><span data-stu-id="8e24c-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="8e24c-120">Wiht Azure AD 권리 부여 관리를 사용하면 액세스 요청 워크플로, 액세스 할당, 검토 및 만료를 자동화하여 ID를 관리하고 액세스 수명 주기를 대규모로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="8e24c-121">직원은 작업을 수행하기 위해 다양한 그룹, 응용 프로그램 및 사이트에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="8e24c-122">요구 사항이 변경되거나, 새 응용 프로그램이 추가되거나, 사용자에게 추가 액세스 권한이 필요하기 때문에 이 액세스를 관리하는 것은 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="8e24c-123">다른 조직과 공동 작업을 할 때 다른 조직의 사용자가 조직의 리소스에 액세스해야 하는지 알 수 없는 경우 외부 사용자가 조직에서 사용 하는 응용 프로그램, 그룹 또는 사이트를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="8e24c-124">Azure AD 권리 부여 관리를 사용하면 내부 및 외부 사용자를 위한 그룹, 응용 프로그램 및 SharePoint 사이트에 대한 액세스를 보다 효율적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e24c-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="8e24c-125">자세한 내용은 Azure AD 권리 관리 [개요를 참조하세요.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)</span><span class="sxs-lookup"><span data-stu-id="8e24c-125">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
