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
description: 개별적으로 또는 그룹 구성원 자격에 따라 사용자 계정에 Microsoft 365 라이선스를 할당하는 방법에 대해 설명
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051535"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="8568e-103">사용자 계정에 Microsoft 365 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="8568e-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="8568e-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="8568e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8568e-105">클라우드 전용 ID 모델의 경우 만든 방법에 따라 사용자 계정에 Microsoft 365 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="8568e-106">하이브리드 ID 모델의 경우 AD DS(Active Directory 도메인 서비스) 사용자 계정이 처음으로 동기화될 때 위치 또는 Microsoft 365 라이선스가 자동으로 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="8568e-107">**라이선스 할당 전 또는 할당과 함께 사용자 위치로 각 사용자 계정을 구성해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8568e-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="8568e-108">두 경우 모두 사용자가 전자 메일 및 Microsoft Teams와 같은 Microsoft 365 서비스에 액세스할 수 있도록 사용자 계정에 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="8568e-109">그룹 구성원 자격을 통해 개별적으로 또는 자동으로 사용자 계정에 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="8568e-110">개별 사용자 계정에 Microsoft 365 라이선스를 할당하기 위해 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="8568e-111">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="8568e-111">The Microsoft 365 admin center</span></span>](../admin/manage/assign-licenses-to-users.md)
- [<span data-ttu-id="8568e-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8568e-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="8568e-113">Azure AD 관리 센터</span><span class="sxs-lookup"><span data-stu-id="8568e-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="8568e-114">그룹 기반 라이선스</span><span class="sxs-lookup"><span data-stu-id="8568e-114">Group-based licensing</span></span>

<span data-ttu-id="8568e-115">Azure AD에서 보안 그룹을 구성하여 구독 집합의 라이선스를 그룹의 모든 구성원에게 자동으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="8568e-116">이를 *그룹 기반 라이센싱* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="8568e-117">사용자 계정이 그룹에 추가되거나 제거된다면 그룹 구독 라이센스는 사용자 계정에서 자동으로 할당되거나 할당 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="8568e-118">모든 그룹 구성원에 대한 충분한 라이센스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="8568e-119">라이선스가 부족할 경우 라이선스를 사용할 수 있게 될 때까지 신규 사용자에게 라이선스가 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="8568e-120">Azure B2B 계정이 포함된 그룹에 대해 그룹 기반 라이선싱을 구성해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="8568e-121">자세한 내용은 Azure AD의 그룹 [기반 라이선싱을 참조하세요.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="8568e-121">For more informaion, see [group-based licensing in Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8568e-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8568e-122">Next steps</span></span>

<span data-ttu-id="8568e-123">라이선스가 할당된 적절한 사용자 계정 집합을 통해 이제 다음을 할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8568e-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="8568e-124">보안 구현</span><span class="sxs-lookup"><span data-stu-id="8568e-124">Implement security</span></span>](../security/defender-365-security/security-roadmap.md)
- [<span data-ttu-id="8568e-125">Microsoft 365 앱과 같은 클라이언트 소프트웨어 배포</span><span class="sxs-lookup"><span data-stu-id="8568e-125">Deploy client software, such as Microsoft 365 Apps</span></span>](/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="8568e-126">장치 관리 설정</span><span class="sxs-lookup"><span data-stu-id="8568e-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="8568e-127">서비스 및 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="8568e-127">Configure services and applications</span></span>](configure-services-and-applications.md)