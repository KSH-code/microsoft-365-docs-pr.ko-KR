---
title: 역할 기반 액세스 제어를 사용하여 Microsoft Defender 보안 센터에 세분화된 액세스 권한 부여
description: 보안 작업 내에서 역할 및 그룹을 만들어 포털에 대한 액세스 권한을 부여합니다.
keywords: rbac, 역할, 기반, 액세스, 제어, 그룹, 제어, 계층, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071879"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="5c54c-104">역할 기반 액세스 제어를 사용하여 포털 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="5c54c-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c54c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5c54c-105">**Applies to:**</span></span>
- <span data-ttu-id="5c54c-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5c54c-106">Azure Active Directory</span></span>
- <span data-ttu-id="5c54c-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="5c54c-107">Office 365</span></span>

> <span data-ttu-id="5c54c-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5c54c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5c54c-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="5c54c-110">RBAC(역할 기반 액세스 제어)를 사용하면 보안 작업 팀 내에 역할 및 그룹을 만들어 포털에 대한 적절한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="5c54c-111">만드는 역할 및 그룹에 따라 포털에 액세스할 수 있는 사용자가 보고 할 수 있는 작업을 세분화하여 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="5c54c-112">대규모 지역 분산 보안 운영 팀은 일반적으로 계층 기반 모델을 채택하여 보안 포털에 대한 액세스를 할당하고 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="5c54c-113">일반적인 계층에는 다음 세 가지 수준이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="5c54c-114">계층</span><span class="sxs-lookup"><span data-stu-id="5c54c-114">Tier</span></span> | <span data-ttu-id="5c54c-115">설명</span><span class="sxs-lookup"><span data-stu-id="5c54c-115">Description</span></span>
:---|:---
<span data-ttu-id="5c54c-116">계층 1</span><span class="sxs-lookup"><span data-stu-id="5c54c-116">Tier 1</span></span> | <span data-ttu-id="5c54c-117">**로컬 보안 운영 팀/IT 팀**</span><span class="sxs-lookup"><span data-stu-id="5c54c-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="5c54c-118">이 팀은 일반적으로 지리적 위치 내에 포함된 경고를 조사하고 활성 수정이 필요한 경우 계층 2로 에스컬레이터합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="5c54c-119">계층 2</span><span class="sxs-lookup"><span data-stu-id="5c54c-119">Tier 2</span></span> | <span data-ttu-id="5c54c-120">**지역 보안 운영 팀**</span><span class="sxs-lookup"><span data-stu-id="5c54c-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="5c54c-121">이 팀은 해당 지역의 모든 장치를 보고 수정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="5c54c-122">계층 3</span><span class="sxs-lookup"><span data-stu-id="5c54c-122">Tier 3</span></span> | <span data-ttu-id="5c54c-123">**전역 보안 운영 팀**</span><span class="sxs-lookup"><span data-stu-id="5c54c-123">**Global security operations team**</span></span> <br> <span data-ttu-id="5c54c-124">이 팀은 보안 전문가로 구성하며 포털에서 모든 작업을 보고 수행할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="5c54c-125">Endpoint RBAC용 Defender는 선택 계층 또는 역할 기반 모델을 지원하도록 설계되었습니다. 또한 역할이 볼 수 있는 역할, 액세스할 수 있는 장치 및 수행할 수 있는 작업에 대한 세부적인 제어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="5c54c-126">RBAC 프레임워크는 다음 컨트롤을 중심으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="5c54c-127">**특정 작업을 취할 수 있는 사용자 제어**</span><span class="sxs-lookup"><span data-stu-id="5c54c-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="5c54c-128">사용자 지정 역할을 만들고 세분성으로 액세스할 수 있는 끝점용 Defender 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="5c54c-129">**특정 장치 그룹 또는 그룹에 대한 정보를 볼 수 있는 사용자 제어**</span><span class="sxs-lookup"><span data-stu-id="5c54c-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="5c54c-130">[이름,](machine-groups.md) 태그, 도메인 등의 특정 기준에 따라 장치 그룹을 만든 다음 특정 Azure AD(Azure Active Directory) 사용자 그룹을 사용하여 역할 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="5c54c-131">역할 기반 액세스를 구현하려면 관리자 역할을 정의하고, 해당 권한을 할당하고, 역할에 할당된 Azure AD 사용자 그룹을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="5c54c-132">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="5c54c-132">Before you begin</span></span>
<span data-ttu-id="5c54c-133">RBAC를 사용하려면 먼저 사용 권한을 부여할 수 있는 역할과 RBAC를 켜는 경우의 결과를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="5c54c-134">이 기능을 사용하도록 설정하기 전에 Azure AD에서 전역 관리자 역할 또는 보안 관리자 역할을 가지며, Azure AD 그룹이 포털에서 잠겨 있는 위험을 줄일 준비가 되어 있는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="5c54c-135">Microsoft Defender 보안 센터에 처음 로그인하면 모든 액세스 권한이 부여되거나 읽기 전용 액세스 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="5c54c-136">모든 액세스 권한은 Azure AD에서 보안 관리자 또는 전역 관리자 역할이 있는 사용자에게 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="5c54c-137">읽기 전용 액세스 권한은 Azure AD에서 보안 읽기 권한자 역할이 있는 사용자에게 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="5c54c-138">Endpoint용 Defender 전역 관리자 역할이 있는 사용자는 장치 그룹 연결 및 Azure AD 사용자 그룹 할당에 관계없이 모든 장치에 무제한으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="5c54c-139">처음에는 Azure AD 전역 관리자 또는 보안 관리자 권한이 있는 사용자만 Microsoft Defender 보안 센터에서 역할을 만들고 할당할 수 있으므로 Azure AD에서 올바른 그룹을 준비하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="5c54c-140">**역할 기반 액세스 제어를 설정하면 읽기 전용 권한이 있는 사용자(예: Azure AD 보안 읽기 권한자 역할에 할당된 사용자)가 역할에 할당될 때까지 액세스 권한을 잃게 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="5c54c-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="5c54c-141">관리자 권한이 있는 사용자에게는 모든 권한이 있는 기본 기본 제공 Endpoint 전역 관리자 역할이 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="5c54c-142">RBAC를 사용하기로 옵트인(opt in)한 후 Azure AD Global 또는 Security Administrators가 아닌 추가 사용자를 끝점 전역 관리자 역할에 대한 Defender에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="5c54c-143">RBAC를 사용하기로 옵트인(opt in)한 후 처음 포털에 로그인할 때처럼 초기 역할로 되전할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c54c-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="5c54c-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5c54c-144">Related topic</span></span>
- [<span data-ttu-id="5c54c-145">끝점용 Microsoft Defender에서 장치 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="5c54c-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
