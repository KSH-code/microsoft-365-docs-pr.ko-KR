---
title: PowerShell을 사용하여 SharePoint Online 사이트 만들기 및 사용자 추가
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: '요약: PowerShell을 사용하여 새 SharePoint Online 사이트를 만든 다음 해당 사이트에 사용자 및 그룹을 추가합니다.'
ms.openlocfilehash: 28a51cc39fe838f6c7f9c50e9d750d28e5d830c4
ms.sourcegitcommit: 24ccb910ffac4d065c512a57c5decd9dd19ef4c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594921"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="6ae93-103">PowerShell을 사용하여 SharePoint Online 사이트 만들기 및 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="6ae93-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="6ae93-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="6ae93-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6ae93-105">Microsoft 365용 PowerShell을 사용하여 SharePoint Online 사이트를 만들고 사용자를 추가할 때 Microsoft 365 관리 센터에서보다 훨씬 빠르고 반복적으로 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6ae93-106">Microsoft 365 관리 센터에서 수행할 수 없는 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="6ae93-107">SharePoint Online에 연결</span><span class="sxs-lookup"><span data-stu-id="6ae93-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="6ae93-108">이 항목의 절차를 수행하려면 SharePoint Online에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="6ae93-109">자세한 내용은 [SharePoint Online PowerShell에 연결을 참조하세요.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="6ae93-109">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="6ae93-110">1단계: PowerShell을 사용하여 새 사이트 모음 만들기</span><span class="sxs-lookup"><span data-stu-id="6ae93-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="6ae93-111">제공된 예제 코드와 메모장으로 만든 .csv 파일과 PowerShell을 사용하여 여러 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="6ae93-112">이 절차에서는 괄호로 표시된 자리 표시자 정보를 자체 사이트 및 테넌트 관련 정보로 바 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="6ae93-113">이 프로세스를 통해 단일 파일을 만들고 해당 파일을 사용하는 단일 PowerShell 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="6ae93-114">이렇게 하면 반복 및 이식이 가능한 작업이 모두 수행될 수 있으며, 긴 명령을 SharePoint Online 관리 셸에 입력할 때 발생할 수 있는 많은 오류가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="6ae93-115">이 절차에는 두 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-115">There are two parts to this procedure.</span></span> <span data-ttu-id="6ae93-116">먼저 .csv 파일을 만든 다음 PowerShell을 사용하여 해당 .csv 파일을 참조합니다. 이 파일을 사용하여 사이트를 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="6ae93-117">PowerShell cmdlet은 .csv 파일을 가져와 파일의 첫 번째 줄을 열 머리더로 읽는 중괄호 안의 루프에 파이프합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="6ae93-118">그런 다음 PowerShell cmdlet은 나머지 레코드를 계속하고, 각 레코드에 대해 새 사이트 모음을 만들고, 열 헤더에 따라 사이트 모음의 속성을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="6ae93-119">.csv 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="6ae93-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="6ae93-120">리소스 할당량 매개 변수는 클래식 사이트에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="6ae93-121">최신 사이트에서 이 매개 변수를 사용하는 경우 더이상 사용되지 않을 것 같은 경고 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span> 

1. <span data-ttu-id="6ae93-122">메모장을 열고 다음 텍스트 블록을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-122">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="6ae93-123">여기서 *테넌트는* 테넌트의  이름이고 소유자는 기본 사이트 모음 관리자의 역할을 부여할 테넌트의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="6ae93-124">메모장에서 Ctrl+H를 눌러 대량으로 빠르게 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="6ae93-125">바탕 화면에 파일을 파일로 **SiteCollections.csv.**</span><span class="sxs-lookup"><span data-stu-id="6ae93-125">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="6ae93-126">이 또는 다른 .csv 또는 Windows PowerShell 스크립트 파일을 사용하기 전에 관련이 없는 문자나 인쇄할 수 없는 문자가 없는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="6ae93-127">이렇게 하려면 Word에서 파일을 열고 리본 메뉴에서 단락 아이콘을 클릭하여 인쇄할 수 없는 문자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="6ae93-128">불필요한 인쇄할 수 없는 문자가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="6ae93-129">예를 들어 파일 끝의 마지막 단락 표시 뒤에는 단락 표시가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="6ae93-130">Windows PowerShell 명령 실행</span><span class="sxs-lookup"><span data-stu-id="6ae93-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="6ae93-131">메시지 Windows PowerShell 다음 명령을 입력하거나 복사하여 붙여넣고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="6ae93-132">여기서 *MyAlias는* 사용자 별칭과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-132">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="6ae93-133">메시지 메시지가 Windows PowerShell 기다렸다가 다시 표시될 때까지 기다렸다가</span><span class="sxs-lookup"><span data-stu-id="6ae93-133">Wait for the Windows PowerShell prompt to reappear.</span></span> <span data-ttu-id="6ae93-134">1~2분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-134">It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="6ae93-135">메시지 Windows PowerShell 다음 cmdlet을 입력하거나 복사하여 붙여넣고 Enter 키</span><span class="sxs-lookup"><span data-stu-id="6ae93-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="6ae93-136">목록의 새 사이트 모음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-136">Note the new site collections in the list.</span></span> <span data-ttu-id="6ae93-137">예제 CSV 파일을 사용하면 **TeamSite01, Blog01,** **Project01** 및  **Community01** 사이트 모음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="6ae93-138">그거에요.</span><span class="sxs-lookup"><span data-stu-id="6ae93-138">That’s it.</span></span> <span data-ttu-id="6ae93-139">만든 .csv 파일과 단일 사이트 모음 명령을 사용하여 여러 사이트 모음을 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="6ae93-140">이제 사용자를 만들고 이러한 사이트에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="6ae93-141">2단계: 사용자 및 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="6ae93-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="6ae93-p110">이제 사용자를 만들어 사이트 모음 그룹에 추가할 수 있습니다. 그런 다음 .csv 파일을 사용하여 새 그룹 및 사용자를 대량 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-p110">Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="6ae93-144">다음 절차에서는 예제 사이트 TeamSite01, Blog01, Project01 및 Community01을 계속 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="6ae93-145">.csv 및 .ps1 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="6ae93-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="6ae93-146">메모장을 열고 다음 텍스트 블록을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-146">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/><span data-ttu-id="6ae93-147">여기서 *테넌트는* 테넌트 이름과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-147">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="6ae93-148">바탕 화면에 파일을 **GroupsAndPermissions.csv.**</span><span class="sxs-lookup"><span data-stu-id="6ae93-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="6ae93-149">새 메모장 인스턴스를 열고 다음 텍스트 블록을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-149">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/><span data-ttu-id="6ae93-150">*테넌트가* 테넌트 이름과 같고 사용자 *이름은* 기존 사용자의 사용자 이름과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="6ae93-151">파일을 데스크톱에 파일로 **Users.csv.**</span><span class="sxs-lookup"><span data-stu-id="6ae93-151">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="6ae93-152">새 메모장 인스턴스를 열고 다음 텍스트 블록을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-152">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="6ae93-153">여기서 MyAlias는 현재 로그온되어 있는 사용자의 사용자 이름과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="6ae93-154">바탕 화면에 파일을 **UsersAndGroups.ps1.**</span><span class="sxs-lookup"><span data-stu-id="6ae93-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="6ae93-155">이 스크립트는 간단한 Windows PowerShell 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="6ae93-156">이제 UsersAndGroup.ps1 스크립트를 실행하여 사용자와 그룹을 여러 사이트 모음에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="6ae93-157">UsersAndGroups.ps1 스크립트 실행</span><span class="sxs-lookup"><span data-stu-id="6ae93-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="6ae93-158">SharePoint Online 관리 셸로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-158">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="6ae93-159">메시지 Windows PowerShell 다음 줄을 입력하거나 복사하여 붙여넣고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="6ae93-160">확인 프롬프트에서 **Y를 누르고**</span><span class="sxs-lookup"><span data-stu-id="6ae93-160">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="6ae93-161">메시지 Windows PowerShell 다음을 입력하거나 복사하여 붙여넣고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="6ae93-162">여기서 *MyAlias는* 사용자 이름과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-162">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="6ae93-p112">프롬프트가 반환될 때까지 기다렸다가 계속 진행합니다. 먼저 작성된 그룹이 표시되고, 사용자를 추가하면 그룹 목록이 반복적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae93-p112">Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ae93-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ae93-166">See also</span></span>

[<span data-ttu-id="6ae93-167">SharePoint Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="6ae93-167">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="6ae93-168">PowerShell을 사용하여 SharePoint Online 사이트 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="6ae93-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="6ae93-169">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="6ae93-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6ae93-170">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="6ae93-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
