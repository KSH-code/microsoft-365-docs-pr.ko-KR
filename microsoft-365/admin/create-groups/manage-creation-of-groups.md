---
title: Office 365 그룹을 만들 수 있는 사용자 관리
f1.keywords:
- NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Office 365 그룹을 만들 수 있는 사용자를 제어 하는 방법을 알아봅니다.
ms.openlocfilehash: a211cb3b69348a4d4a401a3c318fe019d8fd257f
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277195"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="4cf26-103">Office 365 그룹을 만들 수 있는 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="4cf26-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="4cf26-104">사용자가 Office 365 그룹을 매우 쉽게 만들 수 있으므로 다른 사람을 대신하여 이러한 그룹을 만들어 달라는 요청을 많이 받게 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="4cf26-105">그러나 비즈니스에 따라 그룹을 만들 수 있는 사용자를 제어하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="4cf26-106">이 문서에서는 **그룹을 사용하는 모든 Office 365 서비스에서** 그룹을 만드는 기능을 사용하지 않도록 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-106">This article explains how to disable the ability to create groups **in all Office 365 services that use groups**:</span></span> 
  
- <span data-ttu-id="4cf26-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="4cf26-107">Outlook</span></span>
    
- <span data-ttu-id="4cf26-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4cf26-108">SharePoint</span></span>
    
- <span data-ttu-id="4cf26-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="4cf26-109">Yammer</span></span>
    
- <span data-ttu-id="4cf26-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4cf26-110">Microsoft Teams</span></span>

- <span data-ttu-id="4cf26-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="4cf26-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="4cf26-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="4cf26-112">StaffHub</span></span>
    
- <span data-ttu-id="4cf26-113">Planner</span><span class="sxs-lookup"><span data-stu-id="4cf26-113">Planner</span></span>
    
- <span data-ttu-id="4cf26-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="4cf26-114">PowerBI</span></span>

- <span data-ttu-id="4cf26-115">로드맵</span><span class="sxs-lookup"><span data-stu-id="4cf26-115">Roadmap</span></span>
    
<span data-ttu-id="4cf26-116">특정 보안 그룹의 구성원으로 Office 365 그룹 만들기를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="4cf26-117">이를 구성 하기 위해 Windows PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="4cf26-118">이 문서에서는 필요한 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="4cf26-119">이 문서에서 설명 하는 단계에서는 특정 역할의 구성원이 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="4cf26-120">Office 365 전역 관리자는 Microsoft 365 관리 센터, Planner, 팀, Exchange, SharePoint Online 등의 모든 수단을 통해 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="4cf26-121">다른 역할은 제한 된 방법 (아래 참조)을 통해 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="4cf26-122">Exchange 관리자: Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4cf26-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4cf26-123">파트너 계층 1 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4cf26-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4cf26-124">파트너 계층 2 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4cf26-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4cf26-125">디렉터리 작성자: Azure AD</span><span class="sxs-lookup"><span data-stu-id="4cf26-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="4cf26-126">SharePoint 관리자: SharePoint 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4cf26-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="4cf26-127">팀 서비스 관리자: 팀 관리 센터, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4cf26-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="4cf26-128">사용자 관리 관리자: Microsoft 365 관리 센터, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4cf26-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="4cf26-129">이러한 역할 중 하나의 구성원인 경우 제한된 사용자에 대해 Office 365 그룹을 만든 다음 사용자를 그룹 소유자로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="4cf26-130">이 역할이 있는 사용자는 생성을 방해할 수 있는 PowerShell 설정에 관계 없이 Yammer에서 연결 된 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="4cf26-131">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cf26-131">Licensing requirements</span></span>

<span data-ttu-id="4cf26-132">그룹을 만드는 사용자를 관리 하기 위해 다음 사용자에 게 할당 된 Azure AD Premium 라이선스 또는 Azure AD Basic .EDU 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="4cf26-133">이러한 그룹 만들기 설정을 구성 하는 관리자</span><span class="sxs-lookup"><span data-stu-id="4cf26-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="4cf26-134">그룹을 만들 수 있는 보안 그룹의 구성원</span><span class="sxs-lookup"><span data-stu-id="4cf26-134">The members of the security group who are allowed to create Groups</span></span>

<span data-ttu-id="4cf26-135">다음 사용자는 Azure AD Premium 또는 Azure AD Basic .EDU 라이선스를 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="4cf26-136">Office 365 그룹의 구성원이 고 다른 그룹을 만들 수 없는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="4cf26-137">1단계: Office 365 그룹을 만들어야 하는 사용자에 대한 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="4cf26-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="4cf26-138">조직의 보안 그룹을 하나만 사용 하 여 그룹을 만들 수 있는 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="4cf26-139">그러나 다른 보안 그룹을 이 그룹의 구성원으로 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="4cf26-140">예를 들어 그룹 만들기 허용이라는 그룹이 지정된 보안 그룹이고, Microsoft 플래너 사용자 및 Exchange Online 사용자라는 그룹이 해당 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="4cf26-141">위에 나열 된 역할의 관리자는 그룹을 만들 수 있는 기능을 유지 하므로이 그룹의 구성원 일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4cf26-142">**보안 그룹** 을 사용 하 여 그룹을 만들 수 있는 사용자를 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="4cf26-143">Office 365 그룹을 사용하려고 하면 SharePoint에서 보안 그룹을 확인하므로 구성원이 SharePoint에서 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-143">If you try to use an Office 365 Group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="4cf26-144">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="4cf26-145">**그룹 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="4cf26-146">그룹 유형으로 **보안** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="4cf26-147">그룹의 이름을 기억하세요!</span><span class="sxs-lookup"><span data-stu-id="4cf26-147">Remember the name of the group!</span></span> <span data-ttu-id="4cf26-148">나중에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="4cf26-149">조직에서 그룹을 만들 수 있도록 하려는 사용자 또는 다른 보안 그룹을 추가 하 여 보안 그룹 설정을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-149">Finish setting up the security group, adding people or other security groups who you want to be able to create Groups in your org.</span></span>
    
<span data-ttu-id="4cf26-150">자세한 내용은 [Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제](../email/create-edit-or-delete-a-security-group.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4cf26-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
  
## <a name="step-2-install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="4cf26-151">2 단계: Graph 용 Azure Active Directory PowerShell의 preview 버전 설치</span><span class="sxs-lookup"><span data-stu-id="4cf26-151">Step 2: Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

<span data-ttu-id="4cf26-152">이러한 절차를 수행 하려면 Graph 용 Azure Active Directory PowerShell의 preview 버전이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-152">These procedures require the preview version of the Azure Active Directory PowerShell for Graph.</span></span> <span data-ttu-id="4cf26-153">GA 버전은 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-153">The GA version will not work.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="4cf26-154">같은 컴퓨터에 preview와 GA 버전을 동시에 모두 설치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-154">You cannot install both the preview and GA versions on the same computer at the same time.</span></span> <span data-ttu-id="4cf26-155">Windows 10, Windows Server 2016에 모듈을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-155">You can install the module on Windows 10, Windows Server 2016.</span></span>

  
<span data-ttu-id="4cf26-156">*항상*  최신 상태로 유지하는 것이 좋습니다. 이전 AzureADPreview 또는 old AzureAD 버전을 제거하고 최신 버전을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="4cf26-156">As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
1. <span data-ttu-id="4cf26-157">검색 창에 Windows PowerShell을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-157">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="4cf26-158">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span><span class="sxs-lookup"><span data-stu-id="4cf26-158">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
    
    !["관리자 권한으로 실행"으로 PowerShell을 여세요.](../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
    
3. <span data-ttu-id="4cf26-160">[ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)을 사용 하 여 RemoteSigned에 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-160">Set the policy to RemoteSigned by using [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span></span>
    
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
  
4. <span data-ttu-id="4cf26-161">설치된 모듈 확인:</span><span class="sxs-lookup"><span data-stu-id="4cf26-161">Check installed module:</span></span>
    
    ```
    Get-InstalledModule -Name "AzureAD*"
    ```

5. <span data-ttu-id="4cf26-162">이전 버전의 AzureADPreview 또는 AzureAD를 제거하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-162">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
    ```
    Uninstall-Module AzureADPreview
    ```

    <span data-ttu-id="4cf26-163">또는</span><span class="sxs-lookup"><span data-stu-id="4cf26-163">or</span></span>
  
    ```
    Uninstall-Module AzureAD
    ```

6. <span data-ttu-id="4cf26-164">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="4cf26-164">To install the latest version of AzureADPreview, run this command:</span></span>
  
    ```
    Install-Module AzureADPreview
    ```

    <span data-ttu-id="4cf26-165">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="4cf26-165">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>

<span data-ttu-id="4cf26-166">아래의 3 단계에 대해 PowerShell 창을 열어 두세요.</span><span class="sxs-lookup"><span data-stu-id="4cf26-166">Leave the PowerShell window open for Step 3, below.</span></span>
  
## <a name="step-3-run-powershell-commands"></a><span data-ttu-id="4cf26-167">3 단계: PowerShell 명령 실행</span><span class="sxs-lookup"><span data-stu-id="4cf26-167">Step 3: Run PowerShell commands</span></span>

<span data-ttu-id="4cf26-168">아래 스크립트를 메모장과 같은 텍스트 편집기 또는 [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-168">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="4cf26-169">\* \<SecurityGroupName\> \* 을 만든 보안 그룹의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-169">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="4cf26-170">예:</span><span class="sxs-lookup"><span data-stu-id="4cf26-170">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="4cf26-171">파일을 GroupCreators 저장 합니다. p s.</span><span class="sxs-lookup"><span data-stu-id="4cf26-171">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="4cf26-172">PowerShell 창에서 파일을 저장 한 위치로 이동 합니다 ("CD <FileLocation>" 형식).</span><span class="sxs-lookup"><span data-stu-id="4cf26-172">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="4cf26-173">다음 명령을 입력 하 여 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-173">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="4cf26-174">메시지가 표시 되 면 [관리자 계정으로 로그인](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-174">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="4cf26-175">스크립트의 마지막 줄에 업데이트 된 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-175">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="4cf26-177">나중에 사용 되는 보안 그룹을 변경 하려는 경우 새 보안 그룹의 이름으로 스크립트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-177">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="4cf26-178">그룹 만들기 제한을 해제 하 고 모든 사용자가 그룹을 만들 수 있도록 하려면 $GroupName를 ""로 설정 하 고 $AllowGroupCreation "True"로 설정한 후 스크립트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-178">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="4cf26-179">4 단계: 작동 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="4cf26-179">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="4cf26-180">그룹을 만드는 기능이 없어야 하는 사람의 사용자 계정으로 Office 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-180">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="4cf26-181">즉, 사용자가 만들었거나 관리자가 만든 보안 그룹의 구성원이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-181">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="4cf26-182">**Planner** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-182">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="4cf26-183">Planner의 왼쪽 탐색 창에서 **새 계획** 을 선택 하 여 계획을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-183">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="4cf26-184">계획 및 그룹 만들기가 사용 하지 않도록 설정 된다는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-184">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="4cf26-185">보안 그룹의 구성원을 사용 하 여 동일한 절차를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-185">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="4cf26-186">보안 그룹의 구성원이 그룹을 만들 수 없는 경우 해당 구성원은 해당 [OWA 사서함 정책을](https://go.microsoft.com/fwlink/?linkid=852135)통해 차단 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf26-186">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="4cf26-187">관련 문서</span><span class="sxs-lookup"><span data-stu-id="4cf26-187">Related articles</span></span>

[<span data-ttu-id="4cf26-188">Office 365 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="4cf26-188">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="4cf26-189">Azure Active Directory에서 셀프 서비스 그룹 관리 설정</span><span class="sxs-lookup"><span data-stu-id="4cf26-189">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="4cf26-190">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="4cf26-190">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="4cf26-191">그룹 설정 구성을 위한 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="4cf26-191">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
