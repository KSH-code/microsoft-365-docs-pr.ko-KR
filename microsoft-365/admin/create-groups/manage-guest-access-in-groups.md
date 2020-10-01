---
title: Microsoft 365 그룹에서 게스트 액세스 관리
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Microsoft 365 그룹에 게스트를 추가 하 고, 게스트 사용자를 보고, PowerShell을 사용 하 여 게스트 액세스를 제어 하는 방법을 알아봅니다.
ms.openlocfilehash: 640a35cbb1a3eb395453b224cadcf0d0db82fab8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326522"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="7a8c3-103">Microsoft 365 그룹에서 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="7a8c3-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="7a8c3-104">기본적으로 Microsoft 365 그룹에 대 한 게스트 액세스는 조직에서 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="7a8c3-105">관리자는 전체 조직에 대 한 그룹 또는 개별 그룹에 대 한 게스트 액세스를 허용할지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="7a8c3-106">이 옵션이 설정 되 면 그룹 구성원은 웹에서 Outlook을 통해 게스트 사용자를 Microsoft 365 그룹에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="7a8c3-107">초대는 승인을 위해 그룹 소유자에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="7a8c3-108">승인 된 게스트 사용자는 디렉터리와 그룹에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="7a8c3-109">기본 모드 또는 [EU 지역](https://go.microsoft.com/fwlink/?linkid=2107357) 에 있는 Yammer Enterprise 네트워크는 네트워크 게스트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="7a8c3-110">Microsoft 365 연결 된 Yammer 그룹은 현재 게스트 액세스를 지원 하지 않지만, Yammer 네트워크에 연결 되지 않은 외부 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="7a8c3-111">지침은 [Yammer에서 외부 그룹 만들기 및 관리](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="7a8c3-112">그룹의 게스트 액세스는 SharePoint 또는 팀이 포함 된 보다 광범위 한 시나리오의 일부로 사용 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="7a8c3-113">이러한 서비스에는 자체 게스트 공유 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="7a8c3-114">그룹, SharePoint 및 팀에서 게스트 공유를 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="7a8c3-115">게스트와 현장에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="7a8c3-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="7a8c3-116">게스트와 팀으로 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="7a8c3-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="7a8c3-117">그룹 관리 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="7a8c3-117">Manage groups guest access</span></span>

<span data-ttu-id="7a8c3-118">그룹에서 게스트 액세스를 사용 하도록 설정 하거나 사용 하지 않도록 설정 하려면 Microsoft 365 관리 센터에서이 작업을 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="7a8c3-119">관리 센터에서 **모든 설정 표시** 조직 설정으로 이동 하 여 \> **Settings** \> **Org settings** **서비스** 탭에서 **Microsoft 365 그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="7a8c3-120">**Microsoft 365 그룹** 페이지에서 조직 외부의 사용자에 게 그룹 리소스에 대 한 액세스를 허용할지, 아니면 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="7a8c3-121">관리 센터에서 Microsoft 365 그룹에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="7a8c3-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="7a8c3-122">게스트가 디렉터리에 이미 있는 경우 Microsoft 365 관리 센터에서 사용자를 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="7a8c3-123">관리 센터에서 **그룹**  >  **그룹** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="7a8c3-124">게스트를 추가할 그룹을 클릭 하 고 **구성원** 탭에서 **모두 보기 및 구성원 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="7a8c3-125">**구성원 추가**를 선택 하 고 추가 하려는 게스트의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="7a8c3-126">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-126">Select **Save**.</span></span>

<span data-ttu-id="7a8c3-127">게스트를 디렉터리에 직접 추가 하려는 경우 [azure portal에서 Azure Active DIRECTORY B2B 공동 작업 사용자를 추가할](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="7a8c3-128">게스트 정보를 편집 하려는 경우 [Azure Active Directory를 사용 하 여 사용자의 프로필 정보를 추가 하거나 업데이트할](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8c3-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="7a8c3-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a8c3-129">See also</span></span>

[<span data-ttu-id="7a8c3-130">특정 그룹의 게스트 사용자 차단</span><span class="sxs-lookup"><span data-stu-id="7a8c3-130">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="7a8c3-131">Microsoft 365 관리 센터에서 그룹 멤버 자격 관리</span><span class="sxs-lookup"><span data-stu-id="7a8c3-131">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="7a8c3-132">Azure Active Directory 액세스 검토</span><span class="sxs-lookup"><span data-stu-id="7a8c3-132">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="7a8c3-133">AzureADUser</span><span class="sxs-lookup"><span data-stu-id="7a8c3-133">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
