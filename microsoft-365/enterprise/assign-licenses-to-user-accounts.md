---
title: 사용자 계정에 Microsoft 365 라이선스 할당
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 사용자 계정에 개별적으로 또는 그룹 구성원 자격을 기반으로 Microsoft 365 라이선스를 할당 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326510"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="77e40-103">사용자 계정에 Microsoft 365 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="77e40-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="77e40-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="77e40-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="77e40-105">클라우드 전용 id 모델의 경우 작성 방법에 따라 사용자 계정에 Microsoft 365 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="77e40-106">하이브리드 id 모델의 경우 AD DS (Active Directory 도메인 서비스) 사용자 계정이 처음으로 동기화 되 면 위치 또는 Microsoft 365 라이선스가 자동으로 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="77e40-107">**각 사용자 계정은 사용자 위치를 사용 하 여 라이선스를 할당 하기 전이나 함께 구성 해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="77e40-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="77e40-108">어느 경우 든 사용자가 전자 메일 및 Microsoft 팀과 같은 Microsoft 365 서비스에 액세스할 수 있도록 사용자 계정에 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="77e40-109">사용자 계정에 개별적으로 또는 자동으로 그룹 구성원 자격을 통해 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="77e40-110">개별 사용자 계정에 Microsoft 365 라이선스를 할당 하려면 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="77e40-111">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="77e40-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="77e40-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e40-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="77e40-113">Azure AD 관리 센터</span><span class="sxs-lookup"><span data-stu-id="77e40-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="77e40-114">그룹 기반 라이선스</span><span class="sxs-lookup"><span data-stu-id="77e40-114">Group-based licensing</span></span>

<span data-ttu-id="77e40-115">Azure AD에서 보안 그룹을 구성 하 여 구독 집합의 라이선스를 그룹의 모든 구성원에 게 자동으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="77e40-116">이를 *그룹 기반 라이센싱*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="77e40-117">사용자 계정이 그룹에 추가되거나 제거된다면 그룹 구독 라이센스는 사용자 계정에서 자동으로 할당되거나 할당 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="77e40-118">모든 그룹 구성원에 대한 충분한 라이센스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="77e40-119">라이선스가 부족할 경우 라이선스를 사용할 수 있게 될 때까지 신규 사용자에게 라이선스가 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="77e40-120">Azure B2B 계정이 포함된 그룹에 대해 그룹 기반 라이선싱을 구성해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="77e40-121">자세한 informaion [AZURE AD의 그룹 기반 라이선스](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77e40-121">For more informaion, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="77e40-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="77e40-122">Next steps</span></span>

<span data-ttu-id="77e40-123">라이선스가 할당 된 적절 한 사용자 계정 집합을 사용 하 여 다음 작업을 수행할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="77e40-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="77e40-124">보안 구현</span><span class="sxs-lookup"><span data-stu-id="77e40-124">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="77e40-125">Microsoft 365 앱과 같은 클라이언트 소프트웨어 배포</span><span class="sxs-lookup"><span data-stu-id="77e40-125">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="77e40-126">장치 관리 설정</span><span class="sxs-lookup"><span data-stu-id="77e40-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="77e40-127">서비스 및 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="77e40-127">Configure services and applications</span></span>](configure-services-and-applications.md)
