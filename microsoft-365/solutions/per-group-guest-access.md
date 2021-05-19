---
title: 게스트를 특정 그룹에 추가하지 못하도록 방지
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: 게스트가 특정 그룹에 추가되지 않도록 하는 방법에 대해 자세히 알아보기
ms.openlocfilehash: 1db2055f3e546c05905dbf4c854333387112f06e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538930"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="7886d-103">게스트가 특정 Microsoft 365 또는 팀에 추가되지 Microsoft Teams 방지</span><span class="sxs-lookup"><span data-stu-id="7886d-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="7886d-104">대부분의 그룹 및 팀에 대한 게스트 액세스를 허용하지만 게스트 액세스를 차단하려는 경우 개별 그룹 및 팀에 대한 게스트 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="7886d-105">(팀에 대한 게스트 액세스를 차단하는 것은 연결된 그룹에 대한 게스트 액세스를 차단하여 수행됩니다.) 이렇게 하면 새 게스트가 추가되지 않지만 그룹 또는 팀에 이미 있는 게스트는 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="7886d-106">조직에서 민감도 레이블을 사용하는 경우 그룹 기준으로 게스트 액세스를 제어하는 데 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="7886d-107">이 작업을 하는 방법에 대한 자세한 내용은 민감도 레이블을 사용하여 Microsoft Teams, 그룹 및 Microsoft 365 사이트의 콘텐츠를 [SharePoint 합니다.](../compliance/sensitivity-labels-teams-groups-sites.md)</span><span class="sxs-lookup"><span data-stu-id="7886d-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span> <span data-ttu-id="7886d-108">가능한 한 이 방법을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="7886d-109">Microsoft PowerShell을 사용하여 그룹 설정 변경</span><span class="sxs-lookup"><span data-stu-id="7886d-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="7886d-110">PowerShell을 사용하여 개별 그룹에 새 게스트를 추가하지 못하게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="7886d-111">팀의 연결된 SharePoint 별도의 게스트 공유 [컨트롤이 있습니다.](/sharepoint/change-external-sharing-site)</span><span class="sxs-lookup"><span data-stu-id="7886d-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="7886d-112">그룹 수준 게스트 액세스 설정을 변경하려면 Azure Active Directory [PowerShell의](/powershell/azure/active-directory/install-adv2) Graph(모듈 이름 **AzureADPreview)를** 사용하여 다음을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="7886d-113">이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="7886d-114">AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="7886d-115">미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="7886d-116">이러한 명령을 실행하려면 전역 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="7886d-117">다음 스크립트를 실행하여 게스트 액세스를 차단하려는 그룹의 이름으로 */<GroupName/>* 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="7886d-118">설정을 확인하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="7886d-119">확인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-119">The verification looks like this:</span></span>
    
![게스트 그룹 액세스가 false로 설정되어 있는 PowerShell 창의 스크린샷.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="7886d-121">도메인에 따라 게스트 액세스 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="7886d-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="7886d-122">특정 도메인을 사용하는 게스트를 허용하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="7886d-123">예를 들어 비즈니스(Contoso)가 다른 비즈니스(Fabrikam)와 파트너 관계가 있는 경우 사용자가 해당 게스트를 그룹에 추가할 수 있도록 허용 목록에 Fabrikam을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="7886d-124">자세한 내용은 특정 조직의 B2B 사용자에 대한 초대 허용 또는 [차단을 참조하세요.](/azure/active-directory/b2b/allow-deny-list)</span><span class="sxs-lookup"><span data-stu-id="7886d-124">For more information, see [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="7886d-125">전체 주소 목록에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="7886d-125">Add guests to the global address list</span></span>

<span data-ttu-id="7886d-126">기본적으로 게스트는 전체 주소 Exchange 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="7886d-127">아래에 나열된 단계를 사용하여 게스트를 전체 주소 목록에 표시하세요.</span><span class="sxs-lookup"><span data-stu-id="7886d-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="7886d-128">다음을 실행하여 게스트의 ObjectID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="7886d-129">그런 다음 ObjectID, GivenName, Surname, DisplayName 및 TelephoneNumber에 적절한 값을 사용하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7886d-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="7886d-130">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7886d-130">Related topics</span></span>

[<span data-ttu-id="7886d-131">공동 작업 거버넌스 계획 단계별</span><span class="sxs-lookup"><span data-stu-id="7886d-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="7886d-132">공동 작업 거버넌스 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="7886d-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="7886d-133">Microsoft 365 관리 센터에서 그룹 구성원 관리</span><span class="sxs-lookup"><span data-stu-id="7886d-133">Manage Group membership in the Microsoft 365 admin center</span></span>](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="7886d-134">Azure Active Directory 액세스 검토</span><span class="sxs-lookup"><span data-stu-id="7886d-134">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="7886d-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="7886d-135">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)