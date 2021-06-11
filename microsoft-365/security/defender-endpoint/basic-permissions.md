---
title: 기본 사용 권한을 사용하여 액세스 Microsoft Defender 보안 센터
description: 기본 권한을 사용하여 끝점 포털용 Microsoft Defender에 액세스하는 방법을 배워야 합니다.
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
ms.technology: mde
ms.openlocfilehash: 2d022e903111c498d6f3b7411857748fcb637b64
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844661"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="26483-104">기본 권한을 사용하여 포털에 액세스</span><span class="sxs-lookup"><span data-stu-id="26483-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="26483-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="26483-105">**Applies to:**</span></span>
- <span data-ttu-id="26483-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="26483-106">Azure Active Directory</span></span>
- <span data-ttu-id="26483-107">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="26483-107">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="26483-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26483-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="26483-109">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="26483-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="26483-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="26483-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="26483-111">기본 사용 권한 관리를 사용하려면 아래 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26483-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="26483-112">다음 솔루션 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26483-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="26483-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="26483-113">Azure PowerShell</span></span>
- <span data-ttu-id="26483-114">Azure Portal</span><span class="sxs-lookup"><span data-stu-id="26483-114">Azure portal</span></span>

<span data-ttu-id="26483-115">사용 권한에 대한 세부적인 제어를 위해 역할 기반 액세스 [제어로 전환합니다.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="26483-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="26483-116">사용자를 사용하여 사용자 액세스 Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="26483-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="26483-117">다음 권한 수준 중 하나를 사용하여 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26483-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="26483-118">모든 액세스(읽기 및 쓰기)</span><span class="sxs-lookup"><span data-stu-id="26483-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="26483-119">읽기 전용 액세스</span><span class="sxs-lookup"><span data-stu-id="26483-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="26483-120">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="26483-120">Before you begin</span></span>

- <span data-ttu-id="26483-121">설치 Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26483-121">Install Azure PowerShell.</span></span> <span data-ttu-id="26483-122">자세한 내용은 를 설치 및 구성하는 [방법을 Azure PowerShell.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)</span><span class="sxs-lookup"><span data-stu-id="26483-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="26483-123">PowerShell cmdlet은 상승된 명령줄에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26483-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="26483-124">커넥트 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="26483-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="26483-125">자세한 내용은 [커넥트-MsolService를 참조하십시오.](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="26483-125">For more information, see [Connect-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="26483-126">**모든 액세스**</span><span class="sxs-lookup"><span data-stu-id="26483-126">**Full access**</span></span> <br>
<span data-ttu-id="26483-127">모든 권한이 있는 사용자는 로그인하고, 모든 시스템 정보를 보고, 경고를 해결하고, 심층 분석을 위해 파일을 제출하고, 온보더링 패키지를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26483-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="26483-128">모든 액세스 권한을 할당하려면 사용자를 "보안 관리자" 또는 "전역 관리자" AAD 기본 제공 역할에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26483-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="26483-129">**읽기 전용 액세스**</span><span class="sxs-lookup"><span data-stu-id="26483-129">**Read-only access**</span></span> <br>
<span data-ttu-id="26483-130">읽기 전용 액세스 권한이 있는 사용자는 로그인하고 모든 경고 및 관련 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26483-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="26483-131">경고 상태를 변경하거나, 심층 분석을 위해 파일을 제출하거나, 상태 변경 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26483-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="26483-132">읽기 전용 액세스 권한을 할당하려면 사용자를 "보안 읽기 권한자" Azure AD 기본 제공 역할에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26483-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="26483-133">다음 단계에 따라 보안 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26483-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="26483-134">읽기 **및 쓰기 액세스의** 경우 다음 명령을 사용하여 사용자를 보안 관리자 역할에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26483-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="26483-135">읽기 **전용 액세스의** 경우 다음 명령을 사용하여 사용자를 보안 읽기 프로그램 역할에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26483-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="26483-136">자세한 내용은 를 사용하여 그룹 구성원 추가 [또는 제거를 Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="26483-136">For more information, see [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="26483-137">Azure Portal을 사용하여 사용자 액세스 할당</span><span class="sxs-lookup"><span data-stu-id="26483-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="26483-138">자세한 내용은 [을(를)](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)사용할 수 있는 사용자에게 관리자 및 비 관리자 역할 할당을 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="26483-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="26483-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="26483-139">Related topic</span></span>

- [<span data-ttu-id="26483-140">RBAC를 사용하여 포털 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="26483-140">Manage portal access using RBAC</span></span>](rbac.md)
