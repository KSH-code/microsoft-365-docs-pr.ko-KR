---
title: 그룹을 만들 수 있는 사용자 관리
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Microsoft 365 그룹을 만들 수 있는 사용자를 제어 하는 방법을 알아봅니다.
ms.openlocfilehash: b64e7ac96c5a0e38583d00f8a61bd47c5304cf45
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761677"
---
# <a name="manage-who-can-create-groups"></a><span data-ttu-id="6e8ed-103">그룹을 만들 수 있는 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="6e8ed-103">Manage who can create Groups</span></span>

  
<span data-ttu-id="6e8ed-104">사용자가 Microsoft 365 그룹을 쉽게 만들 수 있으므로 다른 사람을 대신 하 여이를 만드는 요청을 많이 받게 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-104">Because it's so easy for users to create Microsoft 365 groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="6e8ed-105">그러나 비즈니스에 따라 그룹을 만들 수 있는 사용자를 제어하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="6e8ed-106">이 문서에서는 다음과 같은 그룹을 사용 하는 모든 Microsoft 365 서비스에서 그룹을 만드는 기능을 사용 하지 않도록 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-106">This article explains how to disable the ability to create groups in all Microsoft 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="6e8ed-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="6e8ed-107">Outlook</span></span>
    
- <span data-ttu-id="6e8ed-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="6e8ed-108">SharePoint</span></span>
    
- <span data-ttu-id="6e8ed-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="6e8ed-109">Yammer</span></span>
    
- <span data-ttu-id="6e8ed-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e8ed-110">Microsoft Teams</span></span>

- <span data-ttu-id="6e8ed-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="6e8ed-111">Microsoft Stream</span></span>

- <span data-ttu-id="6e8ed-112">Planner</span><span class="sxs-lookup"><span data-stu-id="6e8ed-112">Planner</span></span>
    
- <span data-ttu-id="6e8ed-113">PowerBI</span><span class="sxs-lookup"><span data-stu-id="6e8ed-113">PowerBI</span></span>

- <span data-ttu-id="6e8ed-114">웹 및 로드맵 용 프로젝트</span><span class="sxs-lookup"><span data-stu-id="6e8ed-114">Project for the web and Roadmap</span></span>
    
<span data-ttu-id="6e8ed-115">Microsoft 365 그룹 만들기를 특정 보안 그룹의 구성원으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-115">You can restrict Microsoft 365 group creation to the members of a particular security group.</span></span> <span data-ttu-id="6e8ed-116">이를 구성 하기 위해 Windows PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-116">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="6e8ed-117">이 문서에서는 필요한 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-117">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="6e8ed-118">이 문서에서 설명 하는 단계에서는 특정 역할의 구성원이 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-118">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="6e8ed-119">전역 관리자는 Microsoft 365 관리 센터, Planner, 팀, Exchange, SharePoint Online 등의 모든 방법을 통해 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-119">Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="6e8ed-120">다른 역할은 제한 된 방법 (아래 참조)을 통해 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-120">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="6e8ed-121">Exchange 관리자: Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6e8ed-121">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="6e8ed-122">파트너 계층 1 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6e8ed-122">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="6e8ed-123">파트너 계층 2 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6e8ed-123">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="6e8ed-124">디렉터리 작성자: Azure AD</span><span class="sxs-lookup"><span data-stu-id="6e8ed-124">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="6e8ed-125">SharePoint 관리자: SharePoint 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6e8ed-125">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="6e8ed-126">팀 서비스 관리자: 팀 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6e8ed-126">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="6e8ed-127">사용자 관리 관리자: Microsoft 365 관리 센터, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6e8ed-127">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="6e8ed-128">이러한 역할 중 하나의 구성원 인 경우 제한 된 사용자에 대 한 Microsoft 365 그룹을 만든 다음 사용자를 그룹 소유자로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-128">If you're a member of one of these roles, you can create Microsoft 365 groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="6e8ed-129">이 역할이 있는 사용자는 생성을 방해할 수 있는 PowerShell 설정에 관계 없이 Yammer에서 연결 된 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-129">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="6e8ed-130">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e8ed-130">Licensing requirements</span></span>

<span data-ttu-id="6e8ed-131">그룹을 만드는 사용자를 관리 하기 위해 다음 사용자에 게 할당 된 Azure AD Premium 라이선스 또는 Azure AD Basic .EDU 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-131">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="6e8ed-132">이러한 그룹 만들기 설정을 구성 하는 관리자</span><span class="sxs-lookup"><span data-stu-id="6e8ed-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="6e8ed-133">그룹을 만들 수 있는 보안 그룹의 구성원</span><span class="sxs-lookup"><span data-stu-id="6e8ed-133">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="6e8ed-134">Azure 라이선스를 할당 하는 방법에 대 한 자세한 내용은 [Azure Active Directory 포털에서 라이선스 할당 또는 제거](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="6e8ed-135">다음 사용자는 Azure AD Premium 또는 Azure AD Basic .EDU 라이선스를 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="6e8ed-136">Microsoft 365 그룹의 구성원이 고 다른 그룹을 만들 수 없는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="6e8ed-137">1 단계: Microsoft 365 그룹을 만들어야 하는 사용자에 대 한 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="6e8ed-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="6e8ed-138">조직의 보안 그룹을 하나만 사용 하 여 그룹을 만들 수 있는 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="6e8ed-139">그러나 다른 보안 그룹을 이 그룹의 구성원으로 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="6e8ed-140">예를 들어 그룹 만들기 허용이라는 그룹이 지정된 보안 그룹이고, Microsoft 플래너 사용자 및 Exchange Online 사용자라는 그룹이 해당 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="6e8ed-141">위에 나열 된 역할의 관리자는 그룹을 만들 수 있는 기능을 유지 하므로이 그룹의 구성원 일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e8ed-142">**보안 그룹** 을 사용 하 여 그룹을 만들 수 있는 사용자를 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="6e8ed-143">Microsoft 365 그룹을 사용 하려고 하면 구성원이 보안 그룹을 확인 하므로 SharePoint에서 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-143">If you try to use a Microsoft 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="6e8ed-144">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="6e8ed-145">**그룹 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="6e8ed-146">그룹 유형으로 **보안** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="6e8ed-147">그룹의 이름을 기억하세요!</span><span class="sxs-lookup"><span data-stu-id="6e8ed-147">Remember the name of the group!</span></span> <span data-ttu-id="6e8ed-148">나중에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="6e8ed-149">조직에서 그룹을 만들 수 있도록 하려는 사용자 또는 다른 보안 그룹을 추가 하 여 보안 그룹 설정을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-149">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="6e8ed-150">자세한 내용은 [Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제](../email/create-edit-or-delete-a-security-group.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="6e8ed-151">2단계: PowerShell 명령 실행</span><span class="sxs-lookup"><span data-stu-id="6e8ed-151">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="6e8ed-152">그룹 수준 게스트 액세스 설정을 변경 하려면 AzureAD (module name **AzureADPreview**)의 [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 의 preview 버전을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-152">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="6e8ed-153">이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-153">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="6e8ed-154">AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-154">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="6e8ed-155">미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-155">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="6e8ed-156">아래 스크립트를 메모장과 같은 텍스트 편집기 또는 [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-156">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="6e8ed-157">*\<SecurityGroupName\>* 만든 보안 그룹의 이름으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-157">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="6e8ed-158">예시:</span><span class="sxs-lookup"><span data-stu-id="6e8ed-158">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="6e8ed-159">GroupCreators.ps1으로 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-159">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="6e8ed-160">PowerShell 창에서 파일을 저장 한 위치로 이동 합니다 ("CD <FileLocation> " 형식).</span><span class="sxs-lookup"><span data-stu-id="6e8ed-160">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="6e8ed-161">다음 명령을 입력 하 여 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-161">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="6e8ed-162">메시지가 표시 되 면 [관리자 계정으로 로그인](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-162">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="6e8ed-163">스크립트의 마지막 줄에 업데이트 된 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-163">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="6e8ed-165">나중에 사용 되는 보안 그룹을 변경 하려는 경우 새 보안 그룹의 이름으로 스크립트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-165">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="6e8ed-166">그룹 만들기 제한을 해제 하 고 모든 사용자가 그룹을 만들 수 있도록 하려면 $GroupName를 ""로 설정 하 고 $AllowGroupCreation "True"로 설정한 후 스크립트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-166">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="6e8ed-167">3단계: 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="6e8ed-167">Step 3: Verify that it works</span></span>

<span data-ttu-id="6e8ed-168">변경 내용이 적용 되려면 30 분 이상이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-168">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="6e8ed-169">다음을 수행 하 여 새 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-169">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="6e8ed-170">그룹을 만들 수 없는 사용자 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-170">Sign in with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="6e8ed-171">즉, 사용자가 만들었거나 관리자가 만든 보안 그룹의 구성원이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-171">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="6e8ed-172">**Planner** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-172">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="6e8ed-173">Planner의 왼쪽 탐색 창에서 **새 계획** 을 선택 하 여 계획을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-173">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="6e8ed-174">계획 및 그룹 만들기가 사용 하지 않도록 설정 된다는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-174">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="6e8ed-175">보안 그룹의 구성원을 사용 하 여 동일한 절차를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-175">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="6e8ed-176">보안 그룹의 구성원이 그룹을 만들 수 없는 경우 해당 구성원은 해당 [OWA 사서함 정책을](https://go.microsoft.com/fwlink/?linkid=852135)통해 차단 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8ed-176">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="6e8ed-177">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6e8ed-177">Related articles</span></span>

[<span data-ttu-id="6e8ed-178">Office 365 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="6e8ed-178">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="6e8ed-179">Azure Active Directory에서 셀프 서비스 그룹 관리 설정</span><span class="sxs-lookup"><span data-stu-id="6e8ed-179">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="6e8ed-180">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="6e8ed-180">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="6e8ed-181">그룹 설정 구성을 위한 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="6e8ed-181">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
