---
title: PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/13/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 26b9ff81-93b0-4251-beaf-3c9f1d7c80c8
description: PowerShell을 사용 하 여 Microsoft 365 사용자 계정, 라이선스 및 그룹을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d3745b9365c67615efe32881408d1a717b8dbbed
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371539"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="0cf76-103">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="0cf76-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="0cf76-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="0cf76-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0cf76-105">Microsoft 365 관리자는 사용자 계정, 라이선스 및 그룹을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf76-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="0cf76-106">이러한 작업의 대부분은 Microsoft 365 관리 센터에서 수행할 수 있지만, PowerShell에서는 일부 작업이 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="0cf76-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="0cf76-107">자세한 내용은 다음 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0cf76-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="0cf76-108">사용자 계정</span><span class="sxs-lookup"><span data-stu-id="0cf76-108">User accounts</span></span>

- [<span data-ttu-id="0cf76-109">사용자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="0cf76-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-110">사용자 계정 보기</span><span class="sxs-lookup"><span data-stu-id="0cf76-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-111">사용자 계정 속성 구성</span><span class="sxs-lookup"><span data-stu-id="0cf76-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-112">사용자 계정에 역할 할당</span><span class="sxs-lookup"><span data-stu-id="0cf76-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-113">사용자 계정 삭제 및 복원</span><span class="sxs-lookup"><span data-stu-id="0cf76-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-114">사용자 계정 차단</span><span class="sxs-lookup"><span data-stu-id="0cf76-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-115">암호</span><span class="sxs-lookup"><span data-stu-id="0cf76-115">Passwords</span></span>](manage-passwords-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="0cf76-116">라이선스 및 서비스</span><span class="sxs-lookup"><span data-stu-id="0cf76-116">Licenses and services</span></span>
- [<span data-ttu-id="0cf76-117">라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="0cf76-117">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-118">라이선스 사용자 및 허가되지 않은 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="0cf76-118">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-119">사용자 계정에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="0cf76-119">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-120">계정 라이선스 및 서비스 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="0cf76-120">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-121">서비스에 액세스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0cf76-121">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="0cf76-122">Sway에 액세스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0cf76-122">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="0cf76-123">사용자 라이선스를 할당하는 동안 서비스에 대한 액세스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0cf76-123">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="0cf76-124">사용자 계정에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="0cf76-124">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="0cf76-125">그룹</span><span class="sxs-lookup"><span data-stu-id="0cf76-125">Groups</span></span>
- [<span data-ttu-id="0cf76-126">보안 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="0cf76-126">Manage security groups</span></span>](manage-security-groups-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-127">보안 그룹 구성원 유지 관리</span><span class="sxs-lookup"><span data-stu-id="0cf76-127">Maintain security group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0cf76-128">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="0cf76-128">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
