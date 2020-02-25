---
title: Microsoft 365 보안 센터에서 Microsoft 위협 방지 데이터에 대한 액세스 관리
description: Microsoft 위협 방지의 데이터에 대한 권한을 관리하는 방법에 대해 알아봅니다.
keywords: 액세스, 사용 권한, MTP, Microsoft 위협 방지, M365, 보안, MCAS, MDATP, 클라우드 앱 보안, Microsoft Defender Advanced Threat Protection, 범위, 범위 지정, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 110bbe6fe48932217c9bdc009d175161fe9226cd
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235197"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="798b2-104">Microsoft 위협 방지에 대한 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="798b2-104">Manage access to Microsoft Threat Protection</span></span>

<span data-ttu-id="798b2-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="798b2-105">**Applies to:**</span></span>
- <span data-ttu-id="798b2-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="798b2-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="798b2-107">다음 Azure AD(Active Directory) 역할이 할당 된 계정은 Microsoft 위협 방지 기능 및 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="798b2-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="798b2-108">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="798b2-108">Global administrator</span></span>
- <span data-ttu-id="798b2-109">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="798b2-109">Security administrator</span></span>
- <span data-ttu-id="798b2-110">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="798b2-110">Security Operator</span></span>
- <span data-ttu-id="798b2-111">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="798b2-111">Global Reader</span></span>
- <span data-ttu-id="798b2-112">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="798b2-112">Security Reader</span></span>

<span data-ttu-id="798b2-113">이 역할을 사용하여 계정을 검토하려면 [Microsoft 365 보안 센터에서 사용 권한을 확인합니다](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="798b2-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="798b2-114">기능에 대한 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="798b2-114">Access to functionality</span></span>
<span data-ttu-id="798b2-115">특정 기능에 대한 액세스 권한은 [Azure AD 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="798b2-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="798b2-116">사용자 또는 사용자 그룹에 새 역할을 할당해야 하는 특정 기능에 액세스해야 하는 경우 전역 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="798b2-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="798b2-117">보류 중인 자동 작업 승인</span><span class="sxs-lookup"><span data-stu-id="798b2-117">Approve pending automated tasks</span></span>
<span data-ttu-id="798b2-118">[자동화된 검사 및 조치](mtp-autoir-actions.md)는 전자 메일, 전달 규칙, 파일, 유지 메커니즘 및 조사 중에 찾은 기타 아티팩트에 대한 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="798b2-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="798b2-119">명시적 승인이 필요한 보류 중인 작업을 승인하거나 거부하려면 Microsoft 365에서 할당된 특정 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="798b2-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="798b2-120">자세한 내용은 [작업 센터 사용 권한](mtp-action-center.md#required-permissions-for-action-center-tasks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="798b2-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="798b2-121">데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="798b2-121">Access to data</span></span>
<span data-ttu-id="798b2-122">Microsoft Defender ATP RBAC(역할별 액세스 제어)의 사용자 그룹에 할당된 범위를 사용하여 Microsoft 위협 방지 데이터에 대한 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="798b2-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="798b2-123">액세스 범위를 Microsoft Defender ATP에 있는 특정 디바이스 집합으로 지정하지 않은 경우 Microsoft 위협 방지의 데이터에 대해 전체 권한이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="798b2-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="798b2-124">그러나 계정 범위가 지정되면 해당 범위에 속한 디바이스에 대한 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="798b2-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="798b2-125">예를 들어, Microsoft Defender ATP 역할을 사용하는 하나의 사용자 그룹에 속하고 해당 사용자 그룹에 영업 디바이스에 대한 액세스 권한만 부여된 경우, Microsoft 위협 방지에 영업 디바이스에 대한 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="798b2-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="798b2-126">Microsoft Defender ATP의 RBAC 설정에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="798b2-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="798b2-127">Microsoft Cloud App Security 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="798b2-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="798b2-128">미리 보기 중에는, Microsoft 위협 방지에서 Cloud App Security 설정에 따라 액세스 제어를 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="798b2-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="798b2-129">Microsoft 위협 방지 데이터에 대한 액세스는 이 설정의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="798b2-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="798b2-130">관련 항목</span><span class="sxs-lookup"><span data-stu-id="798b2-130">Related topics</span></span>

- [<span data-ttu-id="798b2-131">Azure AD 역할</span><span class="sxs-lookup"><span data-stu-id="798b2-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="798b2-132">Microsoft Defender ATP RBAC</span><span class="sxs-lookup"><span data-stu-id="798b2-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="798b2-133">Cloud App Security 역할</span><span class="sxs-lookup"><span data-stu-id="798b2-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
