---
title: PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.openlocfilehash: 0c6ca6a4165b616097405a9de178c254aa489a3c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429989"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="0a872-103">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="0a872-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="0a872-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="0a872-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0a872-105">Microsoft 365 관리자는 사용자 계정, 라이선스 및 그룹을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a872-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="0a872-106">이러한 작업의 대부분은 Microsoft 365 관리 센터에서 수행할 수 있지만, PowerShell에서는 일부 작업이 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="0a872-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="0a872-107">자세한 내용은 다음 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a872-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="0a872-108">사용자 계정</span><span class="sxs-lookup"><span data-stu-id="0a872-108">User accounts</span></span>

- [<span data-ttu-id="0a872-109">사용자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="0a872-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0a872-110">사용자 계정 보기</span><span class="sxs-lookup"><span data-stu-id="0a872-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0a872-111">사용자 계정 속성 구성</span><span class="sxs-lookup"><span data-stu-id="0a872-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0a872-112">사용자 계정에 역할 할당</span><span class="sxs-lookup"><span data-stu-id="0a872-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0a872-113">사용자 계정 삭제 및 복원</span><span class="sxs-lookup"><span data-stu-id="0a872-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0a872-114">사용자 계정 차단</span><span class="sxs-lookup"><span data-stu-id="0a872-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="0a872-115">라이선스 및 서비스</span><span class="sxs-lookup"><span data-stu-id="0a872-115">Licenses and services</span></span>
- [<span data-ttu-id="0a872-116">라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="0a872-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0a872-117">라이선스 사용자 및 허가되지 않은 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="0a872-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0a872-118">사용자 계정에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="0a872-118">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0a872-119">계정 라이선스 및 서비스 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="0a872-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0a872-120">서비스에 액세스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0a872-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="0a872-121">Sway에 액세스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0a872-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="0a872-122">사용자 라이선스를 할당하는 동안 서비스에 대한 액세스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0a872-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="0a872-123">사용자 계정에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="0a872-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="0a872-124">그룹</span><span class="sxs-lookup"><span data-stu-id="0a872-124">Groups</span></span>
- [<span data-ttu-id="0a872-125">그룹 멤버 자격 유지 관리</span><span class="sxs-lookup"><span data-stu-id="0a872-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="0a872-126">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="0a872-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
