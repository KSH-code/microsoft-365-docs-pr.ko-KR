---
title: Microsoft 365 id 거 버 넌 스 관리
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
description: Microsoft 365 id 거 버 넌 스 기능을 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d5bcafb5b452e693bf3ff706c436a9986eeeae76
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328547"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="c8e1a-103">Microsoft 365 id 거 버 넌 스 관리</span><span class="sxs-lookup"><span data-stu-id="c8e1a-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="c8e1a-104">ID 거버넌스는 직원 생산성을 보장하면서 중요한 자산에 대한 액세스를 보호, 모니터링 및 감사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="c8e1a-105">예를 들어 ID 거버넌스를 사용하는 경우 올바른 사용자에게 올바른 리소스에 대한 올바른 액세스 권한이 있는지 확인하고, 해당 액세스 권한이 시간에 따라 변경되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="c8e1a-106">자세한 내용은 azure [Active Directory에 대 한 id 관리 개요 (AZURE AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="c8e1a-107">Azure AD 액세스 검토 설정</span><span class="sxs-lookup"><span data-stu-id="c8e1a-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="c8e1a-108">Azure AD 액세스 검토를 통해 사용자의 액세스를 검토 하 여 적절 한 사용자만 계속 액세스 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="c8e1a-109">예:</span><span class="sxs-lookup"><span data-stu-id="c8e1a-109">For example:</span></span>

- <span data-ttu-id="c8e1a-110">새 직원이 조직에 들어오면 올바른 액세스 권한을 제공하여 생산적으로 작업할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="c8e1a-111">해당 직원이 다른 팀, 위치 또는 부서로 이동하게 되면 필요에 따라 이전 팀, 위치 또는 부서에 대한 액세스 권한이 제거되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="c8e1a-112">해당 직원이나 게스트가 조직에서 나갈 때 해당 액세스 권한이 제거되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="c8e1a-113">이러한 작업은 조직이 사용자 계정에 너무 많은 액세스 권한이 있는지 확인하고 산업 또는 지역 규정을 위반할 경우 벌금을 매길 수 있는 보안 감사를 받고 있는 경우에 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="c8e1a-114">자세한 내용은 [access 검토용 개요](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="c8e1a-115">PIM(Azure AD Privileged Identity Management)에서는 Azure AD, Azure 및 기타 Microsoft 클라우드 서비스에서 리소스에 대한 액세스 권한을 보호하기 위해 조정된 추가 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-115">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="c8e1a-116">Azure AD PIM은 디렉터리, Office 365, Azure 리소스 역할 등 회사의 리소스를 보호하는 데 도움이 되는 포괄적인 관리 제어 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-116">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="c8e1a-117">다른 양식의 액세스를 사용하는 경우와 마찬가지로 조직은 액세스 검토를 사용하여 관리자 역할의 모든 사용자에 대해 정기 액세스 재인증을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-117">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="c8e1a-118">Azure AD PIM은 Microsoft 365 Enterprise의 E5 버전에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-118">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="c8e1a-119">다양한 유형의 액세스 검토를 구성하려면 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-119">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="c8e1a-120">그룹 및 앱</span><span class="sxs-lookup"><span data-stu-id="c8e1a-120">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="c8e1a-121">Azure AD 역할</span><span class="sxs-lookup"><span data-stu-id="c8e1a-121">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="c8e1a-122">Azure 리소스 역할</span><span class="sxs-lookup"><span data-stu-id="c8e1a-122">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="c8e1a-123">Azure AD 자격 관리 설정</span><span class="sxs-lookup"><span data-stu-id="c8e1a-123">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="c8e1a-124">Wiht Azure AD 자격 관리에서는 액세스 요청 워크플로, 액세스 할당, 검토 및 만료를 자동화 하 여 확장에서 id 및 액세스 수명 주기를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-124">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="c8e1a-125">직원은 다양 한 그룹, 응용 프로그램 및 사이트에 액세스 하 여 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-125">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="c8e1a-126">이러한 액세스 관리는 요구 사항이 변경 되거나, 새 응용 프로그램이 추가 되거나, 사용자에 게 추가 액세스 권한이 필요한 경우에 어려움이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-126">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="c8e1a-127">다른 조직과 공동 작업을 수행 하는 경우 다른 조직의 사용자가 조직의 리소스에 액세스 해야 하는 사람을 알지 못할 수 있으며, 외부 사용자는 조직에서 사용 중인 응용 프로그램, 그룹 또는 사이트를 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-127">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="c8e1a-128">Azure AD 자격 관리를 통해 내부 및 외부 사용자를 위해 그룹, 응용 프로그램 및 SharePoint 사이트에 대 한 액세스를 보다 효율적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-128">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="c8e1a-129">자세한 내용은 [AZURE AD 자격 관리 개요](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8e1a-129">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
