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
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Microsoft 365 그룹을 만들 수 있는 사용자를 제어 하는 방법을 알아봅니다.
ms.openlocfilehash: d6e6c6d9caff2ac7c13d03dad97b73906a509f46
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307862"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="d7ad1-103">Microsoft 365 그룹을 만들 수 있는 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="d7ad1-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="d7ad1-104">기본적으로 모든 사용자는 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="d7ad1-105">이 방법은 사용자가 도움을 요청 하지 않고 공동 작업을 시작할 수 있기 때문에 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="d7ad1-106">비즈니스에서 그룹을 만들 수 있는 사용자를 제한 해야 하는 경우이 문서의 절차를 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="d7ad1-107">그룹을 만들 수 있는 사용자를 제한 하면 다음을 포함 하 여 액세스를 위해 그룹을 사용 하는 모든 서비스에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="d7ad1-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="d7ad1-108">Outlook</span></span>
    
- <span data-ttu-id="d7ad1-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d7ad1-109">SharePoint</span></span>
    
- <span data-ttu-id="d7ad1-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="d7ad1-110">Yammer</span></span>
    
- <span data-ttu-id="d7ad1-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7ad1-111">Microsoft Teams</span></span>

- <span data-ttu-id="d7ad1-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="d7ad1-112">Microsoft Stream</span></span>

- <span data-ttu-id="d7ad1-113">Planner</span><span class="sxs-lookup"><span data-stu-id="d7ad1-113">Planner</span></span>
    
- <span data-ttu-id="d7ad1-114">PowerBI (클래식)</span><span class="sxs-lookup"><span data-stu-id="d7ad1-114">PowerBI (classic)</span></span>
    
- <span data-ttu-id="d7ad1-115">웹/로드맵 용 프로젝트</span><span class="sxs-lookup"><span data-stu-id="d7ad1-115">Project for the web / Roadmap</span></span>
    
<span data-ttu-id="d7ad1-116">Microsoft 365 그룹 만들기를 특정 보안 그룹의 구성원으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-116">You can restrict Microsoft 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="d7ad1-117">이를 구성 하기 위해 Windows PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="d7ad1-118">이 문서에서는 필요한 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="d7ad1-119">이 문서에서 설명 하는 단계에서는 특정 역할의 구성원이 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="d7ad1-120">Office 365 전역 관리자는 Microsoft 365 관리 센터, Planner, 팀, Exchange, SharePoint Online 등의 모든 수단을 통해 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="d7ad1-121">다른 역할은 제한 된 방법 (아래 참조)을 통해 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="d7ad1-122">Exchange 관리자: Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d7ad1-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="d7ad1-123">파트너 계층 1 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d7ad1-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="d7ad1-124">파트너 계층 2 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d7ad1-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="d7ad1-125">디렉터리 작성자: Azure AD</span><span class="sxs-lookup"><span data-stu-id="d7ad1-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="d7ad1-126">SharePoint 관리자: SharePoint 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d7ad1-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="d7ad1-127">팀 서비스 관리자: 팀 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d7ad1-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="d7ad1-128">사용자 관리 관리자: Microsoft 365 관리 센터, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d7ad1-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="d7ad1-129">이러한 역할 중 하나의 구성원 인 경우 제한 된 사용자에 대 한 Microsoft 365 그룹을 만든 다음 사용자를 그룹 소유자로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="d7ad1-130">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7ad1-130">Licensing requirements</span></span>

<span data-ttu-id="d7ad1-131">그룹을 만드는 사용자를 관리 하기 위해 다음 사용자에 게 할당 된 Azure AD Premium 라이선스 또는 Azure AD Basic .EDU 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="d7ad1-132">이러한 그룹 만들기 설정을 구성 하는 관리자</span><span class="sxs-lookup"><span data-stu-id="d7ad1-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="d7ad1-133">그룹을 만들 수 있는 보안 그룹의 구성원</span><span class="sxs-lookup"><span data-stu-id="d7ad1-133">The members of the security group who are allowed to create groups</span></span>
 
> [!NOTE]
> <span data-ttu-id="d7ad1-134">Azure 라이선스를 할당 하는 방법에 대 한 자세한 내용은 [Azure Active Directory 포털에서 라이선스 할당 또는 제거](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="d7ad1-135">다음 사용자는 Azure AD Premium 또는 Azure AD Basic .EDU 라이선스를 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="d7ad1-136">Microsoft 365 그룹의 구성원이 고 다른 그룹을 만들 수 없는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="d7ad1-137">1 단계: Microsoft 365 그룹을 만들어야 하는 사용자에 대 한 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="d7ad1-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="d7ad1-138">조직의 보안 그룹을 하나만 사용 하 여 그룹을 만들 수 있는 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="d7ad1-139">그러나 다른 보안 그룹을 이 그룹의 구성원으로 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-139">But, you can nest other security groups as members of this group.</span></span>

<span data-ttu-id="d7ad1-140">위에 나열 된 역할의 관리자는 그룹을 만들 수 있는 기능을 유지 하므로이 그룹의 구성원 일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7ad1-141">**보안 그룹** 을 사용 하 여 그룹을 만들 수 있는 사용자를 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-141">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="d7ad1-142">Microsoft 365 그룹을 사용 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-142">Using a Microsoft 365 group is not supported.</span></span> 
    
1. <span data-ttu-id="d7ad1-143">관리 센터에서 [그룹 페이지로](https://admin.microsoft.com/adminportal/home#/groups)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-143">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="d7ad1-144">**그룹 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-144">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="d7ad1-145">그룹 유형으로 **보안** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-145">Choose **Security** as the group type.</span></span> <span data-ttu-id="d7ad1-146">그룹의 이름을 기억하세요!</span><span class="sxs-lookup"><span data-stu-id="d7ad1-146">Remember the name of the group!</span></span> <span data-ttu-id="d7ad1-147">나중에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-147">You'll need it later.</span></span>
  
4. <span data-ttu-id="d7ad1-148">조직에서 그룹을 만들 수 있도록 하려는 사용자 또는 다른 보안 그룹을 추가 하 여 보안 그룹 설정을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-148">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="d7ad1-149">자세한 내용은 [Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-149">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="d7ad1-150">2단계: PowerShell 명령 실행</span><span class="sxs-lookup"><span data-stu-id="d7ad1-150">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="d7ad1-151">그룹 수준 게스트 액세스 설정을 변경 하려면 AzureAD (module name **AzureADPreview**)의 [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 의 preview 버전을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-151">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="d7ad1-152">이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-152">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="d7ad1-153">AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-153">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="d7ad1-154">미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-154">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="d7ad1-155">아래 스크립트를 메모장과 같은 텍스트 편집기 또는 [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-155">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="d7ad1-156">*\<SecurityGroupName\>* 만든 보안 그룹의 이름으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-156">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="d7ad1-157">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="d7ad1-157">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="d7ad1-158">GroupCreators.ps1으로 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-158">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="d7ad1-159">PowerShell 창에서 파일을 저장 한 위치로 이동 합니다 ("CD <FileLocation> " 형식).</span><span class="sxs-lookup"><span data-stu-id="d7ad1-159">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="d7ad1-160">다음 명령을 입력 하 여 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-160">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="d7ad1-161">메시지가 표시 되 면 [관리자 계정으로 로그인](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-161">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

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

<span data-ttu-id="d7ad1-162">스크립트의 마지막 줄에 업데이트 된 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-162">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="d7ad1-164">나중에 사용 되는 보안 그룹을 변경 하려는 경우 새 보안 그룹의 이름으로 스크립트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-164">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="d7ad1-165">그룹 만들기 제한을 해제 하 고 모든 사용자가 그룹을 만들 수 있도록 하려면 $GroupName를 ""로 설정 하 고 $AllowGroupCreation "True"로 설정한 후 스크립트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-165">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="d7ad1-166">3단계: 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="d7ad1-166">Step 3: Verify that it works</span></span>

<span data-ttu-id="d7ad1-167">변경 내용이 적용 되려면 30 분 이상이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-167">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="d7ad1-168">다음을 수행 하 여 새 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-168">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="d7ad1-169">그룹을 만들 수 없는 사용자 계정을 사용 하 여 Microsoft 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-169">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="d7ad1-170">즉, 사용자가 만들었거나 관리자가 만든 보안 그룹의 구성원이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-170">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="d7ad1-171">**Planner** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-171">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="d7ad1-172">Planner의 왼쪽 탐색 창에서 **새 계획** 을 선택 하 여 계획을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-172">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="d7ad1-173">계획 및 그룹 만들기가 사용 하지 않도록 설정 된다는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-173">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="d7ad1-174">보안 그룹의 구성원을 사용 하 여 동일한 절차를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-174">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="d7ad1-175">보안 그룹의 구성원이 그룹을 만들 수 없는 경우 해당 구성원은 해당 [OWA 사서함 정책을](https://go.microsoft.com/fwlink/?linkid=852135)통해 차단 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ad1-175">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="d7ad1-176">관련 문서</span><span class="sxs-lookup"><span data-stu-id="d7ad1-176">Related articles</span></span>

[<span data-ttu-id="d7ad1-177">Office 365 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="d7ad1-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="d7ad1-178">Azure Active Directory에서 셀프 서비스 그룹 관리 설정</span><span class="sxs-lookup"><span data-stu-id="d7ad1-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="d7ad1-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="d7ad1-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="d7ad1-180">그룹 설정 구성을 위한 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="d7ad1-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
