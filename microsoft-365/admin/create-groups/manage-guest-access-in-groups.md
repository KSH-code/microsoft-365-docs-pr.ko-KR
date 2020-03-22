---
title: Office 365 그룹에서 게스트 액세스 관리
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
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Office 365 그룹에 게스트를 추가 하 고, 게스트 사용자를 보고, PowerShell을 사용 하 여 게스트 액세스를 제어 하는 방법을 알아봅니다.
ms.openlocfilehash: e76718ccb20843b252c939be48653c61c7c1f0a9
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894506"
---
# <a name="manage-guest-access-in-office-365-groups"></a><span data-ttu-id="a5e1c-103">Office 365 그룹에서 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="a5e1c-103">Manage guest access in Office 365 Groups</span></span>

<span data-ttu-id="a5e1c-104">기본적으로 Office 365 그룹에 대 한 게스트 액세스는 조직에서 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-104">By default, guest access for Office 365 groups is turned on for your organization.</span></span> <span data-ttu-id="a5e1c-105">관리자는 전체 조직에 대 한 그룹 또는 개별 그룹에 대 한 게스트 액세스를 허용할지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="a5e1c-106">이 옵션이 설정 되 면 그룹 구성원이 게스트 사용자를 웹에서 Outlook을 통해 Office 365 그룹에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-106">When it's turned on, group members can invite guest users to an Office 365 group through Outlook on Web.</span></span> <span data-ttu-id="a5e1c-107">초대는 승인을 위해 그룹 소유자에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-107">Invitations are sent to the group owner for approval.</span></span>

> [!Note]
> <span data-ttu-id="a5e1c-108">기본 모드 또는 [EU 지역](https://go.microsoft.com/fwlink/?linkid=2107357) 에 있는 Yammer Enterprise 네트워크는 네트워크 게스트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-108">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="a5e1c-109">Office 365 연결 된 Yammer 그룹은 현재 게스트 액세스를 지원 하지 않지만, Yammer 네트워크에 연결 되지 않은 외부 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-109">Office 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="a5e1c-110">지침은 [Yammer에서 외부 그룹 만들기 및 관리](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-110">See [Create and manage external groups in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) for instructions.</span></span>

### <a name="edit-guest-information"></a><span data-ttu-id="a5e1c-111">게스트 정보 편집</span><span class="sxs-lookup"><span data-stu-id="a5e1c-111">Edit guest information</span></span>

<span data-ttu-id="a5e1c-112">승인 된 게스트 사용자는 디렉터리와 그룹에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-112">Once approved, the guest user is added to the directory and the group.</span></span>

<span data-ttu-id="a5e1c-113">그룹의 게스트 액세스는 SharePoint 또는 팀이 포함 된 보다 광범위 한 시나리오의 일부로 사용 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-113">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="a5e1c-114">이러한 서비스에는 자체 게스트 공유 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-114">These services have their own guest sharing settings.</span></span> <span data-ttu-id="a5e1c-115">그룹, SharePoint 및 팀에서 게스트 공유를 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-115">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="a5e1c-116">게스트와 현장에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="a5e1c-116">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="a5e1c-117">게스트와 팀으로 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="a5e1c-117">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="a5e1c-118">그룹 관리 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="a5e1c-118">Manage groups guest access</span></span>

<span data-ttu-id="a5e1c-119">그룹에서 게스트 액세스를 사용 하도록 설정 하거나 사용 하지 않도록 설정 하려면 Microsoft 365 관리 센터에서이 작업을 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-119">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="a5e1c-120">관리 센터에서 **설정** \> **설정** 으로 이동 하 여 **Office 365 그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-120">In the admin center, go to the **Settings** \> **Settings** and select **Office 365 Groups**.</span></span>
  
2. <span data-ttu-id="a5e1c-121">**Office 365 그룹** 페이지에서 조직 외부의 사용자에 게 그룹 리소스에 대 한 액세스를 허용 하거나 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-121">On the **Office 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a><span data-ttu-id="a5e1c-122">관리 센터에서 Office 365 그룹에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="a5e1c-122">Add guests to an Office 365 group from the admin center</span></span>

<span data-ttu-id="a5e1c-123">게스트가 디렉터리에 이미 있는 경우 Microsoft 365 관리 센터에서 사용자를 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-123">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="a5e1c-124">관리 센터에서 **그룹** > **그룹** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="a5e1c-125">게스트를 추가할 그룹을 클릭 하 고 **구성원** 탭에서 **모두 보기 및 구성원 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="a5e1c-126">**구성원 추가**를 선택 하 고 추가 하려는 게스트의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="a5e1c-127">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-127">Select **Save**.</span></span>

<span data-ttu-id="a5e1c-128">게스트를 디렉터리에 직접 추가 하려는 경우 [azure portal에서 Azure Active DIRECTORY B2B 공동 작업 사용자를 추가할](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="a5e1c-129">게스트 정보를 편집 하려는 경우 [Azure Active Directory를 사용 하 여 사용자의 프로필 정보를 추가 하거나 업데이트할](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="a5e1c-130">특정 그룹의 게스트 사용자 차단</span><span class="sxs-lookup"><span data-stu-id="a5e1c-130">Block guest users from a specific group</span></span>

<span data-ttu-id="a5e1c-131">대부분의 그룹에 대 한 게스트 액세스를 허용 하지만 게스트 액세스를 차단 하려는 경우에는 Microsoft PowerShell을 사용 하 여 개별 그룹에 대 한 게스트 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-131">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="a5e1c-132">그룹 수준 게스트 액세스 설정을 변경 하려면 [Graph에 대 한 Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 의 preview 버전 (모듈 이름 **AzureADPreview**)을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-132">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="a5e1c-133">이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-133">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="a5e1c-134">AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-134">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="a5e1c-135">미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-135">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="a5e1c-136">이러한 명령을 실행 하려면 전역 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-136">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="a5e1c-137">게스트 액세스를 차단 하려는 그룹 \* / \* 의 이름으로 변경 되는 다음 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-137">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="a5e1c-138">설정을 확인 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-138">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="a5e1c-139">확인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-139">The verification looks like this:</span></span>
    
![게스트 그룹 액세스가 false로 설정 되었음을 보여 주는 PowerShell 창의 스크린샷](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="a5e1c-141">도메인을 기반으로 게스트 액세스 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="a5e1c-141">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="a5e1c-142">특정 도메인을 사용 하는 게스트 사용자를 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-142">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="a5e1c-143">예를 들어 회사 (Contoso)에 다른 회사 (Fabrikam)와의 협력 관계가 있으면 사용자가 자신의 그룹에 해당 게스트를 추가할 수 있도록 허용 목록에 Fabrikam을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-143">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="a5e1c-144">자세한 내용은 [특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-144">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="a5e1c-145">전체 주소 목록에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="a5e1c-145">Add guests to the global address list</span></span>

<span data-ttu-id="a5e1c-146">기본적으로 게스트는 Exchange 전체 주소 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-146">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="a5e1c-147">아래에 나와 있는 단계를 사용 하 여 게스트가 전체 주소 목록에 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-147">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="a5e1c-148">다음을 실행 하 여 게스트 사용자의 ObjectID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-148">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="a5e1c-149">그런 후에는 ObjectID, GivenName, 성, DisplayName 및 TelephoneNumber에 적절 한 값을 사용 하 여 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e1c-149">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="a5e1c-150">관련 문서</span><span class="sxs-lookup"><span data-stu-id="a5e1c-150">Related articles</span></span>

[<span data-ttu-id="a5e1c-151">Microsoft 365 관리 센터에서 그룹 멤버 자격 관리</span><span class="sxs-lookup"><span data-stu-id="a5e1c-151">Manage Group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="a5e1c-152">Azure Active Directory 액세스 검토</span><span class="sxs-lookup"><span data-stu-id="a5e1c-152">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="a5e1c-153">AzureADUser</span><span class="sxs-lookup"><span data-stu-id="a5e1c-153">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
