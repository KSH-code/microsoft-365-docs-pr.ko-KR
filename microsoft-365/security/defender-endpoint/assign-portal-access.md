---
title: 사용자 액세스 권한을 Microsoft Defender 보안 센터
description: 끝점용 Microsoft Defender 포털에 대한 읽기 및 쓰기 또는 읽기 전용 권한을 할당합니다.
keywords: 사용자 역할 할당, 읽기 및 쓰기 액세스 할당, 읽기 전용 액세스 할당, 사용자, 사용자 역할, 역할
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164774"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="957eb-104">사용자 액세스 권한을 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="957eb-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="957eb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="957eb-105">**Applies to:**</span></span>
- <span data-ttu-id="957eb-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="957eb-106">Azure Active Directory</span></span>
- <span data-ttu-id="957eb-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="957eb-107">Office 365</span></span>
- <span data-ttu-id="957eb-108">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="957eb-108">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="957eb-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="957eb-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="957eb-110">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="957eb-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="957eb-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="957eb-112">Endpoint용 Defender는 사용 권한을 관리하는 두 가지 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="957eb-113">**기본 사용 권한 관리:** 모든 권한 또는 읽기 전용으로 사용 권한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="957eb-114">**RBAC(역할** 기반 액세스 제어) : 역할을 정의하고, 역할에 Azure AD 사용자 그룹을 할당하고, 사용자 그룹에 장치 그룹에 대한 액세스 권한을 부여하여 세분화된 사용 권한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="957eb-115">RBAC에 대한 자세한 내용은 역할 기반 액세스 제어를 사용하여 포털 [액세스 관리를 참조하세요.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="957eb-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="957eb-116">기본 권한을 이미 할당한 경우 언제든지 RBAC로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="957eb-117">전환하기 전에 다음을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="957eb-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="957eb-118">모든 권한이 있는 사용자(Azure AD에서 전역 관리자 또는 보안 관리자 디렉터리 역할이 할당된 사용자)에는 자동으로 끝점 관리자 역할에 대한 기본 Defender가 할당되며, 이 사용자에게는 모든 액세스 권한도 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="957eb-119">RBAC로 전환한 후 추가 Azure AD 사용자 그룹을 끝점용 Defender 관리자 역할에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="957eb-120">Endpoint 관리자 역할에 대한 Defender 관리자 역할에 할당된 사용자만 RBAC를 사용하여 사용 권한을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="957eb-121">읽기 전용 액세스 권한이 있는 사용자(보안 읽기 권한이 있는 사용자)는 역할이 할당될 때까지 포털에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="957eb-122">Azure AD 사용자 그룹만 RBAC에서 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="957eb-123">RBAC로 전환한 후 기본 사용 권한 관리를 사용하여 다시 전환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="957eb-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="957eb-124">관련 항목</span><span class="sxs-lookup"><span data-stu-id="957eb-124">Related topics</span></span>

- [<span data-ttu-id="957eb-125">기본 권한을 사용하여 포털에 액세스</span><span class="sxs-lookup"><span data-stu-id="957eb-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="957eb-126">RBAC를 사용하여 포털 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="957eb-126">Manage portal access using RBAC</span></span>](rbac.md)
