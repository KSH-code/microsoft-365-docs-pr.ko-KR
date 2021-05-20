---
title: Microsoft 365 그룹에서 게스트 액세스 관리
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: 게스트를 Microsoft 365 그룹에 추가하고 게스트 사용자를 보고 PowerShell을 사용하여 게스트 액세스를 제어하는 방법을 알아보세요.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571940"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="e0429-103">Microsoft 365 그룹에서 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="e0429-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="e0429-104">기본적으로 Microsoft 365 그룹에 대한 게스트 액세스는 조직에 대해 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="e0429-105">관리자는 전체 조직에 대한 그룹에 대한 게스트 액세스를 허용할지 또는 개별 그룹에 대한 액세스를 허용할지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="e0429-106">그룹이 켜져 있는 경우 그룹 구성원은 웹에서 Outlook 통해 게스트 사용자를 Microsoft 365 그룹에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="e0429-107">초대장은 승인을 위해 그룹 소유자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="e0429-108">승인되면 게스트 사용자가 디렉터리 및 그룹에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="e0429-109">네이티브 모드 또는 [EU Geo에](/yammer/manage-security-and-compliance/manage-data-compliance) 있는 Yammer Enterprise 네트워크는 네트워크 게스트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="e0429-110">Microsoft 365 연결된 Yammer 그룹은 현재 게스트 액세스를 지원하지 않지만 Yammer 네트워크에서 연결되지 않은 외부 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="e0429-111">지침은 [Yammer 외부 그룹 만들기 및 관리를](/yammer/work-with-external-users/create-and-manage-external-groups) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0429-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="e0429-112">그룹의 게스트 액세스는 종종 SharePoint 또는 Teams 포함하는 광범위한 시나리오의 일부로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="e0429-113">이러한 서비스에는 자체 게스트 공유 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="e0429-114">그룹, SharePoint 및 Teams 통해 게스트 공유를 설정하는 전체 지침은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0429-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="e0429-115">게스트와 현장에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="e0429-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="e0429-116">게스트와 팀으로 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="e0429-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="e0429-117">그룹 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="e0429-117">Manage groups guest access</span></span>

<span data-ttu-id="e0429-118">그룹에서 게스트 액세스를 사용하도록 설정하거나 사용하지 않도록 설정하려면 Microsoft 365 관리 센터에서 게스트 액세스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="e0429-119">관리 센터에서 **모든** 설정 조직 설정 표시 \>  \>  및 **서비스** 탭에서 Microsoft 365 **그룹을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0429-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="e0429-120">Microsoft 365 **그룹** 페이지에서 조직 외부의 사람들이 그룹 리소스에 액세스하도록 할지 또는 그룹 소유자가 조직 외부의 사람들을 그룹에 추가하도록 할지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="e0429-121">관리자 센터에서 Microsoft 365 그룹에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="e0429-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="e0429-122">게스트가 디렉터리에 이미 있는 경우 Microsoft 365 관리 센터에서 그룹에 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="e0429-123">(동적 멤버십이 있는 그룹은 [Azure Active Directory.)](/azure/active-directory/enterprise-users/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="e0429-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="e0429-124">관리 센터에서 그룹 그룹   >  페이지로 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0429-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="e0429-125">게스트를 추가할 그룹을 클릭하고 **멤버** 탭에서 **모두 보기 및 구성원 관리를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="e0429-126">**멤버 추가를** 선택하고 추가할 게스트의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="e0429-127">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-127">Select **Save**.</span></span>

<span data-ttu-id="e0429-128">디렉터리에 게스트를 직접 추가하려면 [Azure 포털에서 Azure Active Directory B2B 공동 작업 사용자를 추가할](/azure/active-directory/b2b/add-users-administrator)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="e0429-129">게스트의 정보를 편집하려면 Azure Active Directory 사용하여 사용자의 프로필 [정보를 추가하거나 업데이트할](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0429-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="e0429-130">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="e0429-130">Related content</span></span>

<span data-ttu-id="e0429-131">[특정 그룹에서 게스트 사용자를](../../solutions/per-group-guest-access.md) 차단합니다(기사)</span><span class="sxs-lookup"><span data-stu-id="e0429-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>

<span data-ttu-id="e0429-132">[Microsoft 365 관리 센터의 그룹 구성원](add-or-remove-members-from-groups.md) 관리(문서)</span><span class="sxs-lookup"><span data-stu-id="e0429-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>
  
<span data-ttu-id="e0429-133">[Azure Active Directory 액세스](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) 리뷰(기사)</span><span class="sxs-lookup"><span data-stu-id="e0429-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>

<span data-ttu-id="e0429-134">[세트-AzureADUser(문서)](/powershell/module/azuread/set-azureaduser)</span><span class="sxs-lookup"><span data-stu-id="e0429-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>