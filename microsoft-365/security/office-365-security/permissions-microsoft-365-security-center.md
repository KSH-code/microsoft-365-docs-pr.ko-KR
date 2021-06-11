---
title: Microsoft 365 Defender 포털 사용 권한
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 관리자는 Microsoft 365 Defender 포털에서 보안과 관련된 모든 작업에 대한 사용 권한을 관리하는 법을 배웁니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e810b0146803d22246db6d4248d7d4a6a203834b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879027"
---
# <a name="permissions-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="028c0-103">Microsoft 365 Defender 포털 사용 권한</span><span class="sxs-lookup"><span data-stu-id="028c0-103">Permissions in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="028c0-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="028c0-104">**Applies to**</span></span>
- [<span data-ttu-id="028c0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="028c0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="028c0-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="028c0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="028c0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="028c0-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="028c0-108">모든 Microsoft 365 서비스를 포괄하는 보안 시나리오를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-108">You need to manage security scenarios that span all the Microsoft 365 services.</span></span> <span data-ttu-id="028c0-109">또한 조직의 적절한 사람에게 적절한 관리자 권한을 부여할 수 있는 유연성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-109">And you need the flexibility to give the right admin permissions to the right people in your organization.</span></span>

<span data-ttu-id="028c0-110"><https://security.microsoft.com>의 Microsoft 365 Defender 포털은 Microsoft 365에서 보안 작업을 수행하는 사용자의 사용 권한을 직접 관리할 수 ​​있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-110">The Microsoft 365 Defender portal at <https://security.microsoft.com> supports directly managing permissions for users who perform security tasks in Microsoft 365.</span></span> <span data-ttu-id="028c0-111">Microsoft 365 Defender 포털을 사용하여 사용 권한을 관리하면 보안과 관련된 모든 작업에 대한 사용 권한을 중앙에서 관리할 수 ​​있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-111">By using the Microsoft 365 Defender portal to manage permissions, you can manage permissions centrally for all tasks related to security.</span></span>

<span data-ttu-id="028c0-112">Microsoft 365 Defender 포털에서 사용 권한을 관리하려면 **권한 및 역할** 또는 <https://security.microsoft.com/securitypermissions>(으)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-112">To manage permissions in the Microsoft 365 Defender portal, go to **Permissions & roles** or <https://security.microsoft.com/securitypermissions>.</span></span> <span data-ttu-id="028c0-113">이 작업을 수행하려면 Microsoft 365 Defender 포털의 **전역 관리자** 이거나 **조직 관리** 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-113">You need to be a **global administrator** or a member of the **Organization Management** role group in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="028c0-114">특히 **역할 관리** 역할을 통해 사용자는 Microsoft 365 Defender 포털에서 역할 그룹을 보고, 만들고, 수정할 수 있으며, 기본적으로 이 역할은 **조직 관리** 역할 그룹에만 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-114">Specifically, the **Role Management** role allows users to view, create, and modify role groups in the Microsoft 365 Defender portal, and by default, that role is assigned only to the **Organization Management** role group.</span></span>

> [!NOTE]
> <span data-ttu-id="028c0-115">Microsoft 365 규정 준수 센터 사용 권한에 관한 자세한 내용은 [Microsoft 365 규정 준수 센터 사용 권한](../../compliance/microsoft-365-compliance-center-permissions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-115">For information about permissions in the Microsoft 365 compliance center, see [Permissions in the Microsoft 365 compliance center](../../compliance/microsoft-365-compliance-center-permissions.md).</span></span>

## <a name="relationship-of-members-roles-and-role-groups"></a><span data-ttu-id="028c0-116">구성원, 역할 및 역할 그룹의 관계</span><span class="sxs-lookup"><span data-stu-id="028c0-116">Relationship of members, roles, and role groups</span></span>

<span data-ttu-id="028c0-117">Microsoft 365 Defender 포털의 사용 권한은 RBAC(역할 기반 액세스 제어) 사용 권한 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-117">Permissions in the Microsoft 365 Defender portal are based on the role-based access control (RBAC) permissions model.</span></span> <span data-ttu-id="028c0-118">RBAC는 대부분 Microsoft 365 서비스에서 사용하는 것과 동일한 사용 권한 모델이므로 이러한 서비스의 사용 권한 구조에 익숙하다면 Microsoft 365 Defender 포털에서 사용 권한을 부여하는 작업이 매우 익숙하게 느껴질 것입니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-118">RBAC is the same permissions model that's used by most Microsoft 365 services, so if you're familiar with the permission structure in these services, granting permissions in the Microsoft 365 Defender portal will be very familiar.</span></span>

<span data-ttu-id="028c0-119">**역할** 은 일련의 작업을 수행할 수 있는 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-119">A **role** grants the permissions to do a set of tasks.</span></span>

<span data-ttu-id="028c0-120">**역할 그룹** 은 사람들이 Microsoft 365 Defender 포털에서 작업을 수행할 수 있도록 하는 역할 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-120">A **role group** is a set of roles that lets people do their jobs in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="028c0-121">예를 들어, 공격 시뮬레이터 관리자 역할 그룹에는 공격 시뮬레이션 교육의 모든 측면을 만들고 관리하는 공격 시뮬레이터 관리자 역할이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-121">For example, the Attack Simulator Administrators role group includes the Attack Simulator Admin role to create and manage all aspects of attack simulation training.</span></span>

<span data-ttu-id="028c0-122">Microsoft 365 Defender 포털에는 사용자가 할당해야 할 가장 일반적인 작업과 기능에 대한 기본 역할 그룹이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-122">The Microsoft 365 Defender portal includes default role groups for the most common tasks and functions that you'll need to assign.</span></span> <span data-ttu-id="028c0-123">일반적으로 개별 사용자를 기본 역할 그룹에 **구성원** 으로 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-123">Generally, we recommend simply adding individual users as **members** to the default role groups.</span></span>

![역할 그룹에 역할 및 멤버의 관계를 보여 주는 다이어그램](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="028c0-125">Microsoft 365 Defender 포털의 역할 및 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="028c0-125">Roles and role groups in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="028c0-126">Microsoft 365 Defender 포털의 **권한 및 역할** 에서는 다음과 같은 역할 및 역할 그룹 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-126">The following types of roles and role groups are available in **Permissions & roles** in the Microsoft 365 Defender portalr:</span></span>

- <span data-ttu-id="028c0-127">**Azure AD 역할**: 역할과 할당된 사용자는 볼 수 있지만 Microsoft 365 Defender 포털에서 직접 관리할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-127">**Azure AD roles**: You can view the roles and assigned users, but you can't manage them directly in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="028c0-128">Azure AD 역할은 **모든** Microsoft 365 서비스에 대한 사용 권한을 할당하는 중앙 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-128">Azure AD roles are central roles that assign permissions for **all** Microsoft 365 services.</span></span>

- <span data-ttu-id="028c0-129">**이메일 및 공동 작업 역할**: 보안 및 준수 센터에서 제공되는 역할과 동일한 역할 그룹이지만 이 역할은 Microsoft 365 Defender 포털에서 직접 관리할 수 ​​있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-129">**Email & collaboration roles**: These are the same role groups that are available in the Security & Compliance Center, but you can manage them directly in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="028c0-130">여기에서 할당하는 사용 권한은 Microsoft 365 Defender 포털과 Microsoft 365 규정 준수 센터, 보안 및 준수 센터에 고유하며, 다른 Microsoft 365 워크로드에 필요한 모든 사용 권한에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-130">The permissions that you assign here are specific to the Microsoft 365 Defender portal, the Microsoft 365 compliance center, and the Security & Compliance Center, and don't cover all of the permissions that are needed in other Microsoft 365 workloads.</span></span>

![Microsoft 365 Defender 포털의 사용 권한 및 역할 페이지](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="028c0-132">Microsoft 365 Defender 포털의 Azure Active Directory 역할</span><span class="sxs-lookup"><span data-stu-id="028c0-132">Azure AD roles in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="028c0-133">**이메일 및 공동 작업 역할** \> **권한 및 역할** \> **Azure AD 역할** \> **역할**(또는 직접 <https://security.microsoft.com/aadpermissions>)(으)로 이동하면 이 섹션에서 설명하는 Azure AD 역할이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-133">When you go **Email & collaboration roles** \> **Permissions & roles** \> **Azure AD roles** \> **Roles** (or directly to <https://security.microsoft.com/aadpermissions>) you'll see the Azure AD roles that are described in this section.</span></span>

<span data-ttu-id="028c0-134">역할을 선택하면 역할 및 사용자 할당에 대한 설명이 포함된 세부 정보 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-134">When you select a role, a details flyout that contains the description of the role and the user assignments appears.</span></span> <span data-ttu-id="028c0-135">그러나 이러한 할당을 관리하려면 세부 정보 플라이아웃에서 **Azure AD에서 구성원 관리** 를 클릭해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-135">But to manage those assignments, you need to click **Manage members in Azure AD** in the details flyout.</span></span>

![Azure Active Directory의 권한 관리 링크](../../media/permissions-manage-in-azure-ad-link.png)

<span data-ttu-id="028c0-137">자세한 내용은 [Azure Active Directory에서 관리자 역할 보기 및 할당](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-137">For more information, see [View and assign administrator roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<br>

****

|<span data-ttu-id="028c0-138">역할</span><span class="sxs-lookup"><span data-stu-id="028c0-138">Role</span></span>|<span data-ttu-id="028c0-139">설명</span><span class="sxs-lookup"><span data-stu-id="028c0-139">Description</span></span>|
|---|---|
|<span data-ttu-id="028c0-140">**전역 관리자**</span><span class="sxs-lookup"><span data-stu-id="028c0-140">**Global administrator**</span></span>|<span data-ttu-id="028c0-141">모든 Microsoft 365 서비스의 모든 관리 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-141">Access to all administrative features in all Microsoft 365 services.</span></span> <span data-ttu-id="028c0-142">전역 관리자만 다른 관리자 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-142">Only global administrators can assign other administrator roles.</span></span> <span data-ttu-id="028c0-143">자세한 내용은 [전역 관리자 / 회사 관리자](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-143">For more information, see [Global Administrator / Company Administrator](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).</span></span>|
|<span data-ttu-id="028c0-144">**규정 준수 데이터 관리자**</span><span class="sxs-lookup"><span data-stu-id="028c0-144">**Compliance data administrator**</span></span>|<span data-ttu-id="028c0-145">Microsoft 365에서 조직의 데이터를 추적하고, 보호가 설정되었는지 확인하고, 위험을 완화하는 데 도움이 되는 모든 문제에 대한 인사이트를 얻으세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-145">Keep track of your organization's data across Microsoft 365, make sure it's protected, and get insights into any issues to help mitigate risks.</span></span> <span data-ttu-id="028c0-146">자세한 내용은 [규정 준수 데이터 관리자](/azure/active-directory/roles/permissions-reference#compliance-data-administrator)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-146">For more information, see [Compliance Data Administrator](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).</span></span>|
|<span data-ttu-id="028c0-147">**규정 준수 관리자**</span><span class="sxs-lookup"><span data-stu-id="028c0-147">**Compliance administrator**</span></span>|<span data-ttu-id="028c0-148">조직이 모든 규정 요구 사항을 준수하고, eDiscovery 사례를 관리하며, Microsoft 365 위치, ID 및 앱 전반에서 데이터 관리 정책을 유지하도록 돕습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-148">Help your organization stay compliant with any regulatory requirements, manage eDiscovery cases, and maintain data governance policies across Microsoft 365 locations, identities, and apps.</span></span> <span data-ttu-id="028c0-149">자세한 내용은 [규정 준수 관리자](/azure/active-directory/roles/permissions-reference#compliance-administrator)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-149">For more information, see [Compliance Administrator](/azure/active-directory/roles/permissions-reference#compliance-administrator).</span></span>|
|<span data-ttu-id="028c0-150">**보안 운영자**</span><span class="sxs-lookup"><span data-stu-id="028c0-150">**Security operator**</span></span>|<span data-ttu-id="028c0-151">Microsoft 365 사용자, 디바이스 및 콘텐츠에 대한 활성 위협을 보고, 조사하고, 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-151">View, investigate, and respond to active threats to your Microsoft 365 users, devices, and content.</span></span> <span data-ttu-id="028c0-152">자세한 내용은 [보안 운영자](/azure/active-directory/roles/permissions-reference#security-operator)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-152">For more information, see [Security Operator](/azure/active-directory/roles/permissions-reference#security-operator).</span></span>|
|<span data-ttu-id="028c0-153">**보안 읽기 권한자**</span><span class="sxs-lookup"><span data-stu-id="028c0-153">**Security reader**</span></span>|<span data-ttu-id="028c0-154">Microsoft 365 사용자, 디바이스 및 콘텐츠에 대한 활성 위협을 보고 조사하나 (보안 운영자와는 달리) 조치를 취하여 대응할 권한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-154">View and investigate active threats to your Microsoft 365 users, devices, and content, but (unlike the Security operator) they do not have permissions to respond by taking action.</span></span> <span data-ttu-id="028c0-155">자세한 내용은 [보안 읽기 권한자](/azure/active-directory/roles/permissions-reference#security-reader)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-155">For more information, see [Security Reader](/azure/active-directory/roles/permissions-reference#security-reader).</span></span>|
|<span data-ttu-id="028c0-156">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="028c0-156">**Security administrator**</span></span>|<span data-ttu-id="028c0-157">보안 정책을 관리하고, Microsoft 365 제품 전반에서 보안 분석 및 보고서를 검토하고, 위협 상황에 대한 최신 정보를 파악하여 조직의 전반적인 보안을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-157">Control your organization's overall security by managing security policies, reviewing security analytics and reports across Microsoft 365 products, and staying up-to-speed on the threat landscape.</span></span> <span data-ttu-id="028c0-158">자세한 내용은 [보안 관리자](/azure/active-directory/roles/permissions-reference#security-administrator)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-158">For more information, see [Security Administrator](/azure/active-directory/roles/permissions-reference#security-administrator).</span></span>|
|<span data-ttu-id="028c0-159">**전역 읽기 권한자**</span><span class="sxs-lookup"><span data-stu-id="028c0-159">**Global reader**</span></span>|<span data-ttu-id="028c0-160">**전역 관리자** 역할의 읽기 전용 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-160">The read-only version of the **Global administrator** role.</span></span> <span data-ttu-id="028c0-161">Microsoft 365 전반의 모든 설정 및 관리 정보를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-161">View all settings and administrative information across Microsoft 365.</span></span> <span data-ttu-id="028c0-162">자세한 내용은 [전역 읽기 권한자](/azure/active-directory/roles/permissions-reference#global-reader)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-162">For more information, see [Global Reader](/azure/active-directory/roles/permissions-reference#global-reader).</span></span>|
|<span data-ttu-id="028c0-163">**공격 시뮬레이션 관리자**</span><span class="sxs-lookup"><span data-stu-id="028c0-163">**Attack simulation administrator**</span></span>|<span data-ttu-id="028c0-164">[공격 시뮬레이션](attack-simulation-training.md) 생성, 시뮬레이션 실행/예약, 시뮬레이션 결과 검토의 모든 측면을 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-164">Create and manage all aspects of [attack simulation](attack-simulation-training.md) creation, launch/scheduling of a simulation, and the review of simulation results.</span></span> <span data-ttu-id="028c0-165">자세한 내용은 [공격 시뮬레이션 관리자](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-165">For more information, see [Attack Simulation Administrator](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).</span></span>|
|<span data-ttu-id="028c0-166">**공격 페이로드 작성자**</span><span class="sxs-lookup"><span data-stu-id="028c0-166">**Attack payload author**</span></span>|<span data-ttu-id="028c0-167">공격 페이로드를 생성하지만 실제로 시작하거나 예약하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-167">Create attack payloads but not actually launch or schedule them.</span></span> <span data-ttu-id="028c0-168">자세한 내용은 [공격 페이로드 작성자](/azure/active-directory/roles/permissions-reference#attack-payload-author)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-168">For more information, see [Attack Payload Author](/azure/active-directory/roles/permissions-reference#attack-payload-author).</span></span>|
|

### <a name="email--collaboration-roles-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="028c0-169">Microsoft 365 Defender 포털의 이메일 및 공동 작업 역할</span><span class="sxs-lookup"><span data-stu-id="028c0-169">Email & collaboration roles in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="028c0-170">**이메일 및 공동 작업 역할** \> **권한 및 역할** \> **이메일 및 공동 작업 역할** \> **역할**(또는 <https://security.microsoft.com/emailandcollabpermissions>로 직접) 보안 및 준수 센터에서 사용할 수 있는 동일한 역할 그룹을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-170">When you go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles** (or directly to <https://security.microsoft.com/emailandcollabpermissions>) you'll see the same role groups that are available in the Security & Compliance Center.</span></span>

<span data-ttu-id="028c0-171">해당 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028c0-171">For complete information about these role groups, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

#### <a name="modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="028c0-172">Microsoft 365 Defender 포털의 이메일 및 공동 작업 역할 멤버십 수정</span><span class="sxs-lookup"><span data-stu-id="028c0-172">Modify Email & collaboration role membership in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="028c0-173">Microsoft 365 Defender 포털에서 **이메일 및 공동 작업 역할** \> **사용 권한 및 역할** \> **이메일 및 공동 작업 역할** \> **역할** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-173">In the Microsoft 365 Defender portal, go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles**.</span></span>

2. <span data-ttu-id="028c0-174">열리는 **권한** 페이지의 목록에서 수정할 역할 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-174">In the **Permissions** page that opens, select the role group that you want to modify from the list.</span></span> <span data-ttu-id="028c0-175">**이름** 열 헤더를 클릭하여 이름별로 목록을 정렬하거나 **검색** ![검색 아이콘](../../media/m365-cc-sc-search-icon.png)을 클릭하여 역할 그룹을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-175">You can click on the **Name** column header to sort the list by name, or you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find the role group.</span></span>

3. <span data-ttu-id="028c0-176">표시되는 역할 그룹 세부 정보 플라이아웃의 **구성원** 섹션에서 **수정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-176">In the role group details flyout that appears, click **Edit** in the **Members** section.</span></span>

4. <span data-ttu-id="028c0-177">표시되는 **구성원 선택 편집** 페이지에서 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-177">In the **Editing choose members** page that appears, do one of the following steps:</span></span>
   - <span data-ttu-id="028c0-178">역할 그룹 구성원이 없으면 **구성원 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-178">If there are no role group members, click **Choose members**.</span></span>
   - <span data-ttu-id="028c0-179">기존 역할 그룹 구성원이있는 경우 **수정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-179">If there are existing role group members, click **Edit**</span></span>

5. <span data-ttu-id="028c0-180">표시되는 **구성원 선택** 플라이아웃에서 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-180">In the **Choose members** flyout that appears, do one of the following steps:</span></span>

   - <span data-ttu-id="028c0-181">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-181">Click **Add**.</span></span> <span data-ttu-id="028c0-182">표시되는 사용자 목록에서 한 명 이상의 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-182">In the list of users that appears, select one or more users.</span></span> <span data-ttu-id="028c0-183">또는 **검색** ![검색 아이콘](../../media/m365-cc-sc-search-icon.png)을 클릭하여 사용자를 찾고 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-183">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select users.</span></span>

     <span data-ttu-id="028c0-184">추가 할 사용자를 선택한 후 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-184">When you've selected the users that you want to add, click **Add**.</span></span>

   - <span data-ttu-id="028c0-185">**제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-185">Click **Remove**.</span></span> <span data-ttu-id="028c0-186">기존 구성원 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-186">Select one or more of the existing members.</span></span> <span data-ttu-id="028c0-187">또는 **검색** ![검색 아이콘](../../media/m365-cc-sc-search-icon.png)을 클릭하여 구성원을 찾고 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-187">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select members.</span></span>

     <span data-ttu-id="028c0-188">제거할 사용자를 선택했으면 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-188">When you've selected the users that you want to remove, click **Remove**.</span></span>

6. <span data-ttu-id="028c0-189">**구성원 선택** 플라이아웃으로 돌아가서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-189">Back on the **Choose members** flyout, click **Done**.</span></span>

7. <span data-ttu-id="028c0-190">**구성원 선택 편집** 페이지로 돌아가서 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-190">Back on the **Editing choose members** page, click **Save**.</span></span>

8. <span data-ttu-id="028c0-191">역할 그룹 세부 정보 플라이아웃으로 돌아가서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="028c0-191">Back on the role group details flyout, click **Done**.</span></span>
