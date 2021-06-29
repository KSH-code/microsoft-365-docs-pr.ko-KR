---
title: 보안 센터에서 Microsoft 365 Defender 데이터에 대한 액세스 Microsoft 365 관리
description: 2013에서 데이터에 대한 사용 권한을 관리하는 방법을 Microsoft 365 Defender
keywords: 액세스, 사용 권한, Microsoft 365 Defender, M365, 보안, MCAS, Cloud App Security, 끝점용 Microsoft Defender, 범위, 범위 지정, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 738315c446fd57d4cd027de92eb77b0029f84323
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177531"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="af347-104">전역 역할을 사용하여 Microsoft 365 Defender 액세스 Azure Active Directory 관리</span><span class="sxs-lookup"><span data-stu-id="af347-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="af347-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="af347-105">**Applies to:**</span></span>
- <span data-ttu-id="af347-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af347-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="af347-107">액세스 권한을 관리하는 방법에는 두 가지가 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af347-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="af347-108">**AD(Azure Active Directory 전역 역할) 역할**</span><span class="sxs-lookup"><span data-stu-id="af347-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="af347-109">**사용자 지정 역할 액세스**</span><span class="sxs-lookup"><span data-stu-id="af347-109">**Custom role access**</span></span>

<span data-ttu-id="af347-110">다음 **AD(Global Azure Active Directory)** 역할이 할당된 계정은 Microsoft 365 Defender 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af347-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="af347-111">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="af347-111">Global administrator</span></span>
- <span data-ttu-id="af347-112">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="af347-112">Security administrator</span></span>
- <span data-ttu-id="af347-113">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="af347-113">Security Operator</span></span>
- <span data-ttu-id="af347-114">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="af347-114">Global Reader</span></span>
- <span data-ttu-id="af347-115">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="af347-115">Security Reader</span></span>

<span data-ttu-id="af347-116">이 역할을 사용하여 계정을 검토하려면 [Microsoft 365 보안 센터에서 사용 권한을 확인합니다](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="af347-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="af347-117">**사용자 지정 역할** 액세스는 Microsoft Microsoft 365 Defender 새로운 기능으로, Microsoft Defender 365의 특정 데이터, 작업 및 기능에 대한 액세스를 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="af347-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="af347-118">사용자 지정 역할은 전역 Azure AD 역할보다 더 많은 제어를 제공하여 필요한 최소 허용 역할만 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af347-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="af347-119">전역 Azure AD 역할 외에 사용자 지정 역할을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af347-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="af347-120">[사용자 지정 역할에 대해 자세히 알아보시고 을(를) 자세히 알아보아야 합니다.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="af347-120">[Learn more about custom roles](custom-roles.md).</span></span>

> [!NOTE]
> <span data-ttu-id="af347-121">이 문서는 전역 역할 관리에만 Azure Active Directory 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af347-121">This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="af347-122">사용자 지정 역할 기반 액세스 제어 사용에 대한 자세한 내용은 역할 기반 액세스 제어에 대한 사용자 지정 [역할을 참조하세요.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="af347-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="af347-123">기능에 대한 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="af347-123">Access to functionality</span></span>
<span data-ttu-id="af347-124">특정 기능에 대한 액세스 권한은 [Azure AD 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="af347-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="af347-125">사용자 또는 사용자 그룹에 새 역할을 할당해야 하는 특정 기능에 액세스해야 하는 경우 전역 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="af347-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="af347-126">보류 중인 자동 작업 승인</span><span class="sxs-lookup"><span data-stu-id="af347-126">Approve pending automated tasks</span></span>
<span data-ttu-id="af347-127">[자동화된 검사 및 조치](m365d-autoir-actions.md)는 전자 메일, 전달 규칙, 파일, 유지 메커니즘 및 조사 중에 찾은 기타 아티팩트에 대한 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af347-127">[Automated investigation and remediation](m365d-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="af347-128">명시적 승인이 필요한 보류 중인 작업을 승인하거나 거부하려면 Microsoft 365에서 할당된 특정 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af347-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="af347-129">자세한 내용은 [작업 센터 사용 권한](m365d-action-center.md#required-permissions-for-action-center-tasks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af347-129">To learn more, see [Action center permissions](m365d-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="af347-130">데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="af347-130">Access to data</span></span>
<span data-ttu-id="af347-131">액세스 Microsoft 365 Defender 액세스는 Microsoft Defender for Endpoint RBAC(역할 기반 액세스 제어)의 사용자 그룹에 할당된 범위를 사용하여 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af347-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="af347-132">액세스 범위가 끝점용 Defender의 특정 장치 집합으로 지정되지 않은 경우 액세스 범위에 있는 데이터에 대한 모든 권한이 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="af347-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="af347-133">그러나 계정 범위가 지정되면 해당 범위에 속한 디바이스에 대한 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="af347-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="af347-134">예를 들어 Microsoft Defender for Endpoint 역할이 있는 사용자 그룹에만 속하고 해당 사용자 그룹에 판매 장치에 대한 액세스 권한이 부여된 경우 영업 장치에 대한 데이터만 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="af347-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="af347-135">끝점용 Microsoft Defender의 RBAC 설정에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="af347-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="af347-136">Microsoft Cloud App Security 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="af347-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="af347-137">미리 보기 중에 Microsoft 365 Defender 설정에 따라 액세스 제어를 Cloud App Security 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af347-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="af347-138">이러한 Microsoft 365 Defender 데이터에 대한 액세스는 이러한 설정의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af347-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="af347-139">관련 주제</span><span class="sxs-lookup"><span data-stu-id="af347-139">Related topics</span></span>
- [<span data-ttu-id="af347-140">역할 기반 액세스 제어에서 사용자 지정 역할 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af347-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="af347-141">Azure AD 역할</span><span class="sxs-lookup"><span data-stu-id="af347-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="af347-142">끝점 RBAC용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="af347-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="af347-143">Cloud App Security 역할</span><span class="sxs-lookup"><span data-stu-id="af347-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)
