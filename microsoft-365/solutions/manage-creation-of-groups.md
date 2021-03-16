---
title: Microsoft 365 그룹을 만들 수 있는 사용자 관리
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Microsoft 365 그룹을 만들 수 있는 사용자를 제어하는 방법을 학습합니다.
ms.openlocfilehash: f2d1a2062d43af750a84984aab66329ed6a4db22
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819705"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="dc3f1-103">Microsoft 365 그룹을 만들 수 있는 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="dc3f1-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="dc3f1-104">기본적으로 모든 사용자는 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="dc3f1-105">이 방법은 사용자가 IT의 지원 없이 공동 작업을 시작할 수 있도록 하여 권장되는 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="dc3f1-106">비즈니스에서 그룹을 만들 수 있는 사용자만 제한해야 하는 경우 이 문서의 절차에 따라 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="dc3f1-107">그룹을 만들 수 있는 사용자 수를 제한하면 다음을 비롯한 액세스에 대한 그룹을 사용 하는 모든 서비스에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="dc3f1-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="dc3f1-108">Outlook</span></span>
- <span data-ttu-id="dc3f1-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="dc3f1-109">SharePoint</span></span>
- <span data-ttu-id="dc3f1-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="dc3f1-110">Yammer</span></span>
- <span data-ttu-id="dc3f1-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc3f1-111">Microsoft Teams</span></span>
- <span data-ttu-id="dc3f1-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="dc3f1-112">Microsoft Stream</span></span>
- <span data-ttu-id="dc3f1-113">Planner</span><span class="sxs-lookup"><span data-stu-id="dc3f1-113">Planner</span></span>
- <span data-ttu-id="dc3f1-114">Power BI(클래식)</span><span class="sxs-lookup"><span data-stu-id="dc3f1-114">Power BI (classic)</span></span>
- <span data-ttu-id="dc3f1-115">웹용 프로젝트/로드맵</span><span class="sxs-lookup"><span data-stu-id="dc3f1-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="dc3f1-116">Microsoft 365 그룹 만들기를 특정 Microsoft 365 그룹 또는 보안 그룹의 구성원으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-116">You can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span> <span data-ttu-id="dc3f1-117">이를 구성하기 위해 다음을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="dc3f1-118">이 문서에서는 필요한 단계를 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="dc3f1-119">이 문서의 단계에서는 특정 역할의 구성원이 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="dc3f1-120">Office 365 전역 관리자는 Microsoft 365 관리 센터, Planner, Teams, Exchange 및 SharePoint Online과 같은 모든 수단을 통해 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="dc3f1-121">다른 역할은 아래에 나열된 제한된 수단을 통해 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="dc3f1-122">Exchange 관리자: Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc3f1-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="dc3f1-123">파트너 계층 1 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc3f1-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="dc3f1-124">파트너 계층 2 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc3f1-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="dc3f1-125">디렉터리 작성자: Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc3f1-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="dc3f1-126">SharePoint 관리자: SharePoint 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc3f1-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="dc3f1-127">Teams 서비스 관리자: Teams 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc3f1-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="dc3f1-128">사용자 관리자: Microsoft 365 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="dc3f1-128">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="dc3f1-129">이러한 역할 중 하나의 구성원인 경우 제한된 사용자에 대해 Microsoft 365 그룹을 만든 다음 사용자를 그룹의 소유자로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="dc3f1-130">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc3f1-130">Licensing requirements</span></span>

<span data-ttu-id="dc3f1-131">그룹을 만드는 사용자 관리를 위해 다음 사용자에게 할당된 Azure AD Premium 라이선스 또는 Azure AD Basic EDU 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="dc3f1-132">이러한 그룹 만들기 설정을 구성하는 관리자</span><span class="sxs-lookup"><span data-stu-id="dc3f1-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="dc3f1-133">그룹을 만들 수 있는 그룹의 구성원</span><span class="sxs-lookup"><span data-stu-id="dc3f1-133">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="dc3f1-134">[Azure 라이선스를 할당하는](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) 방법에 대한 자세한 내용은 Azure Active Directory 포털에서 라이선스 할당 또는 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="dc3f1-135">다음 사용자에게 할당된 Azure AD Premium 또는 Azure AD Basic EDU 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="dc3f1-136">Microsoft 365 그룹의 구성원이자 다른 그룹을 만들 수 없는 사용자</span><span class="sxs-lookup"><span data-stu-id="dc3f1-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="dc3f1-137">1단계: Microsoft 365 그룹을 만들어야 하는 사용자를 위한 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="dc3f1-137">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="dc3f1-138">조직에서 그룹을 만들 수 있는 그룹을 제어하는 데는 하나의 그룹만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-138">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="dc3f1-139">그러나 다른 그룹을 이 그룹의 구성원으로 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-139">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="dc3f1-140">위에 나열된 역할의 관리자는 이 그룹의 구성원이 아니어도 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="dc3f1-141">관리 센터에서 그룹 [페이지로 이동합니다.](https://admin.microsoft.com/adminportal/home#/groups)</span><span class="sxs-lookup"><span data-stu-id="dc3f1-141">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="dc3f1-142">그룹 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dc3f1-142">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="dc3f1-143">원하는 그룹 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-143">Choose the group type you want.</span></span> <span data-ttu-id="dc3f1-144">그룹의 이름을 기억하세요!</span><span class="sxs-lookup"><span data-stu-id="dc3f1-144">Remember the name of the group!</span></span> <span data-ttu-id="dc3f1-145">나중에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-145">You'll need it later.</span></span>

4. <span data-ttu-id="dc3f1-146">그룹 설정을 완료하고, 그룹에서 그룹을 만들 수 있도록 하려는 사용자 또는 다른 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-146">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="dc3f1-147">자세한 내용은 Microsoft [365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)관리 센터에서 보안 그룹 만들기, 편집 또는 삭제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-147">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="dc3f1-148">2단계: PowerShell 명령 실행</span><span class="sxs-lookup"><span data-stu-id="dc3f1-148">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="dc3f1-149">그룹 수준 게스트 액세스 설정을 변경하려면 [AzureAD(AzureAD)(모듈](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 이름 **AzureADPreview)의** Azure Active Directory PowerShell 미리 보기 버전을 사용하여 다음을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-149">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="dc3f1-150">이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-150">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="dc3f1-151">AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-151">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="dc3f1-152">미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-152">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="dc3f1-153">아래 스크립트를 메모장과 같은 텍스트 편집기로 복사하거나 ISE Windows PowerShell [복사합니다.](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="dc3f1-153">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="dc3f1-154">을 만든 그룹의 *\<GroupName\>* 이름으로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-154">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="dc3f1-155">예:</span><span class="sxs-lookup"><span data-stu-id="dc3f1-155">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="dc3f1-156">파일을 다른 파일로 GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-156">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="dc3f1-157">PowerShell 창에서 파일을 저장한 위치로 이동합니다("CD"를 <FileLocation> 입력).</span><span class="sxs-lookup"><span data-stu-id="dc3f1-157">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="dc3f1-158">다음을 입력하여 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-158">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="dc3f1-159">메시지가 [표시될 때](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-159">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
    $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="dc3f1-160">스크립트의 마지막 줄에 업데이트된 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-160">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="dc3f1-162">앞으로 사용되는 그룹을 변경하려는 경우 새 그룹의 이름으로 스크립트를 다시 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-162">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="dc3f1-163">그룹 만들기 제한을 해제하고 모든 사용자가 그룹을 만들 수 있도록 다시 허용하려는 경우 $GroupName ""로 설정하고 $AllowGroupCreation "True"로 설정하고 스크립트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-163">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="dc3f1-164">3단계: 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="dc3f1-164">Step 3: Verify that it works</span></span>

<span data-ttu-id="dc3f1-165">변경 내용을 적용하는 데 30분 이상 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-165">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="dc3f1-166">다음을 수행하여 새 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-166">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="dc3f1-167">그룹을 만들 수 있는 능력이 없는 사용자의 사용자 계정으로 Microsoft 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-167">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="dc3f1-168">즉, 사용자가 만든 그룹의 구성원이나 관리자가 아닌 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-168">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="dc3f1-169">**Planner 타일을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-169">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="dc3f1-170">Planner의 **왼쪽** 탐색에서 새 계획을 선택하여 계획을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-170">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="dc3f1-171">계획 및 그룹 만들기를 사용하지 않도록 설정했다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-171">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="dc3f1-172">그룹의 구성원과 동일한 절차를 다시 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc3f1-172">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="dc3f1-173">그룹의 구성원이 그룹을 만들 수 없는 경우 해당 OWA 사서함 정책을 통해 차단되지 [않는지 검사합니다.](https://go.microsoft.com/fwlink/?linkid=852135)</span><span class="sxs-lookup"><span data-stu-id="dc3f1-173">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc3f1-174">관련 주제</span><span class="sxs-lookup"><span data-stu-id="dc3f1-174">Related topics</span></span>

[<span data-ttu-id="dc3f1-175">공동 작업 거버넌스 계획 단계별</span><span class="sxs-lookup"><span data-stu-id="dc3f1-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="dc3f1-176">공동 작업 거버넌스 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="dc3f1-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="dc3f1-177">Office 365 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="dc3f1-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="dc3f1-178">Azure Active Directory에서 셀프 서비스 그룹 관리 설정</span><span class="sxs-lookup"><span data-stu-id="dc3f1-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="dc3f1-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="dc3f1-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="dc3f1-180">그룹 설정 구성을 위한 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="dc3f1-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
