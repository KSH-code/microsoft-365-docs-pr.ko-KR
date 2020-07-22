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
ms.openlocfilehash: a56d9599824ac1436c6f875661bcd573c1f6b1ca
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204746"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="57094-103">Microsoft 365 그룹에서 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="57094-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="57094-104">기본적으로 Microsoft 365 그룹에 대 한 게스트 액세스는 조직에서 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="57094-105">관리자는 전체 조직에 대 한 그룹 또는 개별 그룹에 대 한 게스트 액세스를 허용할지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="57094-106">이 옵션이 설정 되 면 그룹 구성원은 웹에서 Outlook을 통해 게스트 사용자를 Microsoft 365 그룹에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="57094-107">초대는 승인을 위해 그룹 소유자에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57094-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="57094-108">승인 된 게스트 사용자는 디렉터리와 그룹에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57094-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="57094-109">기본 모드 또는 [EU 지역](https://go.microsoft.com/fwlink/?linkid=2107357) 에 있는 Yammer Enterprise 네트워크는 네트워크 게스트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="57094-110">Microsoft 365 연결 된 Yammer 그룹은 현재 게스트 액세스를 지원 하지 않지만, Yammer 네트워크에 연결 되지 않은 외부 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="57094-111">지침은 [Yammer에서 외부 그룹 만들기 및 관리](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57094-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="57094-112">그룹의 게스트 액세스는 SharePoint 또는 팀이 포함 된 보다 광범위 한 시나리오의 일부로 사용 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="57094-113">이러한 서비스에는 자체 게스트 공유 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="57094-114">그룹, SharePoint 및 팀에서 게스트 공유를 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57094-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="57094-115">게스트와 현장에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="57094-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="57094-116">게스트와 팀으로 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="57094-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="57094-117">그룹 관리 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="57094-117">Manage groups guest access</span></span>

<span data-ttu-id="57094-118">그룹에서 게스트 액세스를 사용 하도록 설정 하거나 사용 하지 않도록 설정 하려면 Microsoft 365 관리 센터에서이 작업을 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57094-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="57094-119">관리 센터에서 **모든 설정 표시** 조직 설정으로 이동 하 여 \> **Settings** \> **Org settings** **서비스** 탭에서 **Microsoft 365 그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="57094-120">**Microsoft 365 그룹** 페이지에서 조직 외부의 사용자에 게 그룹 리소스에 대 한 액세스를 허용할지, 아니면 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="57094-121">관리 센터에서 Microsoft 365 그룹에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="57094-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="57094-122">게스트가 디렉터리에 이미 있는 경우 Microsoft 365 관리 센터에서 사용자를 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="57094-123">관리 센터에서 **그룹**  >  **그룹** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="57094-124">게스트를 추가할 그룹을 클릭 하 고 **구성원** 탭에서 **모두 보기 및 구성원 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="57094-125">**구성원 추가**를 선택 하 고 추가 하려는 게스트의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="57094-126">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-126">Select **Save**.</span></span>

<span data-ttu-id="57094-127">게스트를 디렉터리에 직접 추가 하려는 경우 [azure portal에서 Azure Active DIRECTORY B2B 공동 작업 사용자를 추가할](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="57094-128">게스트 정보를 편집 하려는 경우 [Azure Active Directory를 사용 하 여 사용자의 프로필 정보를 추가 하거나 업데이트할](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="57094-129">특정 그룹의 게스트 사용자 차단</span><span class="sxs-lookup"><span data-stu-id="57094-129">Block guest users from a specific group</span></span>

<span data-ttu-id="57094-130">대부분의 그룹에 대 한 게스트 액세스를 허용 하지만 게스트 액세스를 차단 하려는 경우에는 Microsoft PowerShell을 사용 하 여 개별 그룹에 대 한 게스트 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-130">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="57094-131">그룹 수준 게스트 액세스 설정을 변경 하려면 [Graph에 대 한 Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 의 preview 버전 (모듈 이름 **AzureADPreview**)을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-131">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="57094-132">이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-132">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="57094-133">AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-133">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="57094-134">미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-134">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="57094-135">이러한 명령을 실행 하려면 전역 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-135">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="57094-136">*/<GroupName/>* 게스트 액세스를 차단 하려는 그룹의 이름으로 변경 되는 다음 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-136">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="57094-137">설정을 확인 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-137">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="57094-138">확인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-138">The verification looks like this:</span></span>
    
![게스트 그룹 액세스가 false로 설정 되었음을 보여 주는 PowerShell 창의 스크린샷](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="57094-140">도메인을 기반으로 게스트 액세스 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="57094-140">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="57094-141">특정 도메인을 사용 하는 게스트 사용자를 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-141">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="57094-142">예를 들어 회사 (Contoso)에 다른 회사 (Fabrikam)와의 협력 관계가 있으면 사용자가 자신의 그룹에 해당 게스트를 추가할 수 있도록 허용 목록에 Fabrikam을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-142">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="57094-143">자세한 내용은 [특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57094-143">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="57094-144">전체 주소 목록에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="57094-144">Add guests to the global address list</span></span>

<span data-ttu-id="57094-145">기본적으로 게스트는 Exchange 전체 주소 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-145">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="57094-146">아래에 나와 있는 단계를 사용 하 여 게스트가 전체 주소 목록에 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-146">Use the steps listed below to make a guest visible in the global address list.</span></span> <span data-ttu-id="57094-147">Exchange Online 관리 센터에서 게스트를 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-147">Be sure the guest is visible in the Exchange Online admin center.</span></span> <span data-ttu-id="57094-148">새 게스트가 추가 된 후 표시 되는 데는 약간의 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-148">New guests may take a short time to appear there after they're added.</span></span>

<span data-ttu-id="57094-149">다음을 실행 하 여 게스트 사용자의 ObjectID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="57094-149">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="57094-150">그런 후에는 ObjectID, GivenName, 성, DisplayName 및 TelephoneNumber에 적절 한 값을 사용 하 여 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57094-150">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="57094-151">관련 문서</span><span class="sxs-lookup"><span data-stu-id="57094-151">Related articles</span></span>

[<span data-ttu-id="57094-152">Microsoft 365 관리 센터에서 그룹 멤버 자격 관리</span><span class="sxs-lookup"><span data-stu-id="57094-152">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="57094-153">Azure Active Directory 액세스 검토</span><span class="sxs-lookup"><span data-stu-id="57094-153">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="57094-154">AzureADUser</span><span class="sxs-lookup"><span data-stu-id="57094-154">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
