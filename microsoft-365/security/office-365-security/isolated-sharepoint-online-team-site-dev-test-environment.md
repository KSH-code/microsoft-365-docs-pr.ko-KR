---
title: 격리된 SharePoint Online 팀 사이트 개발/테스트 환경
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: '요약: Microsoft 365 개발/테스트 환경의 나머지 조직과 격리된 SharePoint Online 팀 사이트를 구성합니다.'
ms.openlocfilehash: 6e056cd1d930d13e1ae20f8f8d0cdc9aa886f17e
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616491"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="10b43-103">격리된 SharePoint Online 팀 사이트 개발/테스트 환경</span><span class="sxs-lookup"><span data-stu-id="10b43-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="10b43-104">**요약:** Microsoft 365 개발/테스트 환경의 나머지 조직과 격리된 SharePoint Online 팀 사이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="10b43-105">Microsoft 365의 SharePoint Online 팀 사이트는 공통 문서 라이브러리, OneNote 전자 필기장 및 기타 서비스를 사용하여 공동 작업을 위한 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-105">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="10b43-106">대부분의 경우 부서나 조직 전체에서 광범위한 액세스 및 공동 작업을 원합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-106">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="10b43-107">그러나 일부 경우에는 소규모 사용자 그룹이 공동 작업하기 위한 액세스 및 사용 권한을 긴밀하게 제어하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-107">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="10b43-108">SharePoint Online 팀 사이트에 대한 액세스와 사용자가 할 수 있는 작업을 SharePoint 그룹 및 권한 수준에 따라 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-108">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="10b43-109">기본적으로 SharePoint Online 사이트에는 세 가지 액세스 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-109">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="10b43-110">**사이트에서** 리소스를 보고 만들고 수정할 수 있는 구성원</span><span class="sxs-lookup"><span data-stu-id="10b43-110">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="10b43-111">**소유자**- 사용 권한을 변경하는 기능을 포함하여 사이트를 완전하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="10b43-112">**방문자**- 사이트에서 리소스만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-112">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="10b43-113">이 문서에서는 ProjectX라는 비밀 연구 프로젝트에 대해 격리된 SharePoint Online 팀 사이트의 구성을 단계화합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-113">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="10b43-114">액세스 요구 사항은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-114">The access requirements are:</span></span>

- <span data-ttu-id="10b43-115">프로젝트의 구성원만 사이트 및 해당 콘텐츠(문서, OneNote 전자 필기장, 페이지)에 액세스할 수 있으며 그룹 구성원을 통해 제어되는 SharePoint 권한 수준을 편집하고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="10b43-116">사이트에 대한 Admins 그룹의 사이트 작성자 및 구성원만 사이트 관리(사이트 수준 권한 수정 포함)를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="10b43-117">Microsoft 365 개발/테스트 환경에서 격리된 SharePoint Online 팀 사이트를 설정하는 세 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-117">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="10b43-118">Microsoft 365 개발/테스트 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-118">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="10b43-119">ProjectX에 대한 사용자 및 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-119">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="10b43-120">새 ProjectX SharePoint Online 팀 사이트를 만들고 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="10b43-121">[여기](https://aka.ms/catlgstack)를 클릭하여 One Microsoft 클라우드 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-121">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="10b43-122">1단계: 경량 또는 시뮬레이트된 엔터프라이즈 Microsoft 365 개발/테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="10b43-122">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="10b43-123">최소 요구 사항을 사용하여 격리된 SharePoint Online 팀 사이트를 경량 방식으로 만들하려는 경우 간단한 기본 구성의 2, 3단계의 지침을 [따릅니다.](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)</span><span class="sxs-lookup"><span data-stu-id="10b43-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="10b43-124">시뮬레이트된 엔터프라이즈 구성에서 격리된 SharePoint Online 팀 사이트를 만들하려면 [Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)테스트 환경에 대한 암호 해시 동기화의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

> [!NOTE]
> <span data-ttu-id="10b43-125">격리된 SharePoint Online 사이트를 만들 필요는 없습니다. 여기에는 시뮬레이트된 엔터프라이즈 개발/테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-125">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="10b43-126">여기서는 격리된 SharePoint Online 사이트를 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 옵션으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-126">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="10b43-127">2단계: 사용자 계정 및 액세스 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="10b43-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="10b43-128">[Office 365 PowerShell에 연결의](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) 지침을 사용하여 전역 관리자 계정으로 평가판 구독에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-128">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="10b43-129">컴퓨터(경량 Microsoft 365 개발/테스트 환경용)</span><span class="sxs-lookup"><span data-stu-id="10b43-129">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="10b43-130">CLIENT1 가상 컴퓨터(시뮬레이트된 엔터프라이즈 Microsoft 365 개발/테스트 환경용)</span><span class="sxs-lookup"><span data-stu-id="10b43-130">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="10b43-131">ProjectX SharePoint Online 팀 사이트에 대한 새 액세스 그룹을 만들 수 있도록 Windows Azure Active Directory 모듈에서 다음 명령을 Windows PowerShell 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

<span data-ttu-id="10b43-132">조직 이름(예: contosotoycompany), 위치에 대한 2자리 국가 코드를 입력한 후 Windows PowerShell 프롬프트에 대한 Microsoft Azure Active Directory 모듈에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-132">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="10b43-133">**New-MsolUser** 명령이 표시될 때 잠재 고객 디자이너 계정의 생성된 암호를 기록하여 안전한 위치에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-133">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="10b43-134">Windows PowerShell 프롬프트에 대한 Microsoft Azure Active Directory 모듈에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-134">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="10b43-135">**New-MsolUser** 명령이 표시될 때 수석 연구원 계정의 생성된 암호를 기록해두고 안전한 위치에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-135">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="10b43-136">Windows PowerShell 프롬프트에 대한 Microsoft Azure Active Directory 모듈에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-136">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="10b43-137">**New-MsolUser** 명령이 표시될 때 개발 VP 계정의 생성된 암호를 기록하여 안전한 위치에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-137">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="10b43-138">다음으로, 새 액세스 그룹에 새 계정을 추가하기 위해 Windows Azure Active Directory 모듈에서 다음 PowerShell 명령을 Windows PowerShell 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-138">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="10b43-139">결과:</span><span class="sxs-lookup"><span data-stu-id="10b43-139">Results:</span></span>

- <span data-ttu-id="10b43-140">ProjectX-Members 액세스 그룹에는 수장 디자이너 및 수리 연구원 사용자 계정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-140">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="10b43-141">ProjectX-Admins 액세스 그룹에 평가판 구독에 대한 전역 관리자 계정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-141">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="10b43-142">ProjectX-Viewers 액세스 그룹에 개발 VP 사용자 계정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-142">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="10b43-143">그림 1에서는 액세스 그룹 및 해당 구성원 자격을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-143">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="10b43-144">**그림 1:**</span><span class="sxs-lookup"><span data-stu-id="10b43-144">**Figure 1**:</span></span>

![격리된 SharePoint Online 그룹 사이트의 Microsoft 365 그룹 및 구성원 자격](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="10b43-146">3단계: 새 ProjectX SharePoint Online 팀 사이트를 만들고 격리</span><span class="sxs-lookup"><span data-stu-id="10b43-146">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="10b43-147">ProjectX에 대한 SharePoint Online 팀 사이트를 만들 경우 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-147">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="10b43-148">로컬 컴퓨터(경량 구성) 또는 CLIENT1(시뮬레이트된 엔터프라이즈 구성)에서 브라우저를 사용하여 전역 관리자 계정을 사용하여 Microsoft 365 관리 <https://admin.microsoft.com> 센터()에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-148">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="10b43-149">타일 목록에서 **SharePoint** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-149">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="10b43-150">브라우저의 새 SharePoint 탭에서 **+ 사이트 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-150">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="10b43-151">팀 **사이트 이름에** **ProjectX를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-151">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="10b43-152">개인 **정보 설정에서** 비공개를 **선택합니다. 구성원만** 이 사이트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-152">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="10b43-153">팀 **사이트 설명에서** **ProjectX에 대한 SharePoint** 사이트를 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-153">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="10b43-154">On the **Who do you want to add?** 창에서 마친 **다음을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-154">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="10b43-155">브라우저의 **새 ProjectX-Home** 탭에 있는 도구 모음에서 설정 아이콘을 클릭한 다음 사이트 **권한을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-155">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="10b43-156">**사이트 권한** 창에서 **고급 권한 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-156">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="10b43-157">새 사용 **권한:** 브라우저의 프로젝트 X 탭에서 액세스 요청 **설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-157">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="10b43-158">액세스  요청 설정 대화 상자에서  구성원이 사이트 및 개별 파일 및  폴더를 공유할 수 있도록 허용을 선택 취소하고 세 개의 확인란을 모두 선택 취소하도록 액세스 요청을 허용하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-158">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="10b43-159">목록에서 **ProjectX 구성원을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-159">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="10b43-160">**사용자 및 그룹** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-160">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="10b43-161">공유 **대화** 상자에서 **ProjectX-Members를** 입력하고 선택한 다음 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-161">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="10b43-162">브라우저에서 뒤로 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-162">Click the back button on your browser.</span></span>

15. <span data-ttu-id="10b43-163">목록에서 **ProjectX 소유자를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-163">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="10b43-164">**사용자 및 그룹** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-164">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="10b43-165">공유 **대화** 상자에서 **ProjectX-Admins를 입력하고** 선택한 다음 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-165">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="10b43-166">브라우저에서 뒤로 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-166">Click the back button on your browser.</span></span>

19. <span data-ttu-id="10b43-167">목록에서 **ProjectX 방문자를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-167">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="10b43-168">**사용자 및 그룹** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-168">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="10b43-169">공유 **대화** 상자에서 **ProjectX-Viewers를** 입력하고 선택한 다음 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-169">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="10b43-170">브라우저에서 사용자 **및 그룹** 탭을 닫고 브라우저에서 **ProjectX-Home** 탭을 클릭한 다음 사이트 권한 창을 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-170">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="10b43-171">권한 구성의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-171">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="10b43-172">ProjectX 구성원 SharePoint 그룹에는 ProjectX-Members 액세스 그룹(선임 디자이너 및 책임 연구원 사용자 계정만 포함) 및 ProjectX 그룹(전역 관리자 사용자 계정만 포함)만 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-172">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="10b43-173">ProjectX Owners SharePoint 그룹에는 ProjectX-Admins 액세스 그룹(전역 관리자 사용자 계정만 포함)만 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-173">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="10b43-174">ProjectX Visitors SharePoint 그룹에는 개발 ProjectX-Viewers 계정만 포함된 ProjectX-Viewers 액세스 그룹만 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-174">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="10b43-175">구성원은 사이트 수준 권한을 수정할 수 없습니다(이 권한은 그룹 구성원만 ProjectX-Admins 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-175">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="10b43-176">다른 사용자 계정은 사이트 또는 해당 리소스에 액세스하거나 사이트에 대한 액세스를 요청할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-176">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="10b43-177">그림 2에서는 SharePoint 그룹 및 구성원 자격을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-177">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="10b43-178">**그림 2**</span><span class="sxs-lookup"><span data-stu-id="10b43-178">**Figure 2**</span></span>

![격리된 SharePoint Online 그룹 사이트의 SharePoint Online 그룹 및 구성원 자격](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="10b43-180">이제 리드 디자이너 사용자 계정을 사용하여 액세스에 대한 설명을 하자.</span><span class="sxs-lookup"><span data-stu-id="10b43-180">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="10b43-181">브라우저에서 **ProjectX-Home** 탭을 닫은 다음 브라우저에서 **Microsoft Office 홈** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-181">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="10b43-182">전역 관리자의 이름을 클릭한 다음 **로그인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-182">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="10b43-183">리드 디자이너 계정 이름과 암호를 사용하여 Microsoft 365 관리 센터()에 <https://admin.microsoft.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-183">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="10b43-184">타일 목록에서 **SharePoint** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-184">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="10b43-185">브라우저의 새 **SharePoint** 탭에서 검색 상자에 **ProjectX를** 입력하고 검색을 활성화한 다음 **ProjectX** 팀 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-185">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="10b43-186">ProjectX 팀 사이트의 브라우저에 새 탭이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-186">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="10b43-187">설정 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-187">Click the settings icon.</span></span> <span data-ttu-id="10b43-188">사이트 사용 권한에 대한 **옵션은 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-188">Notice that there is no option for **Site Permissions**.</span></span> <span data-ttu-id="10b43-189">이 설정은 ProjectX-Admins 그룹의 구성원만 사이트에 대한 사용 권한을 수정할 수 있기 때문에 올바를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-189">This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="10b43-190">메모장 또는 선택한 텍스트 편집기를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="10b43-190">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="10b43-191">ProjectX 팀 사이트의 URL을 복사하여 메모장이나 텍스트 편집기에서 새 줄에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-191">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="10b43-192">브라우저의 **새 ProjectX-Home** 탭에서 **문서를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-192">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="10b43-193">ProjectX 문서 폴더의 URL을 복사하여 메모장이나 텍스트 편집기에서 새 줄에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-193">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="10b43-194">브라우저의 **새 ProjectX-Documents** 탭에서 Word 문서의 **> 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-194">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="10b43-195">페이지에 일부 텍스트를 입력하고 상태가 저장될 때까지 기다렸다가 **브라우저에서** 뒤로 단추를 클릭한 다음 페이지를 새로 고치십시오.</span><span class="sxs-lookup"><span data-stu-id="10b43-195">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="10b43-196">Documents **폴더에** 새Document.docx **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-196">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="10b43-197">문서의Document.docx클릭한  다음 링크 **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-197">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="10b43-198">**'Document.docx'** 공유 대화 상자의 URL을 복사하여 메모장이나 텍스트 편집기에서 새 줄에 붙여 넣은 다음 **공유 'Document.docx' 대화** 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-198">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="10b43-199">브라우저에서 **ProjectX-Documents** 및 **SharePoint** 탭을 닫은 다음 Microsoft Office **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-199">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="10b43-200">잠재 고객 디자이너 이름을 **클릭한** 다음 **로그인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-200">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="10b43-201">이제 개발 VP 사용자 계정을 사용하여 액세스에 대한 설명을 하자.</span><span class="sxs-lookup"><span data-stu-id="10b43-201">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="10b43-202">개발 VP 계정 이름과 암호를 사용하여 Microsoft 365 관리 센터()에 <https://admin.microsoft.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-202">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="10b43-203">타일 목록에서 **SharePoint** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-203">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="10b43-204">브라우저의 새 **SharePoint** 탭에서 검색 상자에 **ProjectX를** 입력하고 검색을 활성화한 다음 **ProjectX** 팀 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-204">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="10b43-205">ProjectX 팀 사이트의 브라우저에 새 탭이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-205">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="10b43-206">문서를 **클릭한** 다음 파일Document.docx **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-206">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="10b43-207">In the **Document.docx** tab in your browser, try to modify the text.</span><span class="sxs-lookup"><span data-stu-id="10b43-207">In the **Document.docx** tab in your browser, try to modify the text.</span></span> <span data-ttu-id="10b43-208">이 문서는 읽기 **전용입니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-208">You should see a message stating **This document is read-only.**</span></span> <span data-ttu-id="10b43-209">이는 개발 VP 사용자 계정에 사이트에 대한 보기 권한만 있기 때문에 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-209">This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="10b43-210">브라우저에서 \*\*\*\* **Document.docx, ProjectX-Documents** 및 **SharePoint 탭을** 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-210">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="10b43-211">홈 **Microsoft Office** 클릭하고 개발 **VP** 이름을 클릭한 다음 **로그인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-211">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="10b43-212">이제 사용 권한이 없는 사용자 계정으로의 액세스를 보여보자.</span><span class="sxs-lookup"><span data-stu-id="10b43-212">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="10b43-213">사용자 3 계정 이름과 암호를 사용하여 Microsoft 365 관리 <https://admin.microsoft.com> 센터()에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-213">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="10b43-214">타일 목록에서 **SharePoint** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-214">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="10b43-215">브라우저의 새 **SharePoint** 탭에서 검색 상자에 **ProjectX를** 입력한 다음 검색을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-215">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search.</span></span> <span data-ttu-id="10b43-216">You should see the message **Nothing here matches your search.**</span><span class="sxs-lookup"><span data-stu-id="10b43-216">You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="10b43-217">메모장이나 텍스트 편집기에서 ProjectX 사이트의 URL을 브라우저의 주소 표시줄에 복사하고 **Enter를 누르십시오.**</span><span class="sxs-lookup"><span data-stu-id="10b43-217">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="10b43-218">액세스 거부 **페이지가 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-218">You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="10b43-219">메모장이나 텍스트 편집기에서 ProjectX Documents 폴더의 URL을 브라우저의 주소 표시줄에 복사하고 **Enter를 누르십시오.**</span><span class="sxs-lookup"><span data-stu-id="10b43-219">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="10b43-220">액세스 거부 **페이지가 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-220">You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="10b43-221">메모장이나 텍스트 편집기에서 Documents.docx 파일의 URL을 브라우저의 주소 표시줄에 복사하고 Enter 를 **누르십시오.**</span><span class="sxs-lookup"><span data-stu-id="10b43-221">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="10b43-222">액세스 거부 **페이지가 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-222">You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="10b43-223">브라우저에서 **SharePoint** 탭을 닫고  Microsoft Office 탭을 클릭하고 사용자 **3** 이름을 클릭한 다음 **로그인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="10b43-223">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="10b43-224">이제 격리된 SharePoint Online 사이트를 추가 실험할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10b43-224">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="10b43-225">다음 단계</span><span class="sxs-lookup"><span data-stu-id="10b43-225">Next Step</span></span>

<span data-ttu-id="10b43-226">프로덕션 환경에 격리된 SharePoint Online 팀 사이트를 배포할 준비가 되면 [격리된 SharePoint Online 팀 사이트 디자인](design-an-isolated-sharepoint-online-team-site.md)에서 단계별 디자인 고려 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10b43-226">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="10b43-227">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10b43-227">See Also</span></span>

[<span data-ttu-id="10b43-228">격리된 SharePoint Online 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="10b43-228">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="10b43-229">클라우드 도입 TLG(테스트 랩 가이드)</span><span class="sxs-lookup"><span data-stu-id="10b43-229">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="10b43-230">시뮬레이트된 엔터프라이즈 기본 구성</span><span class="sxs-lookup"><span data-stu-id="10b43-230">The simulated enterprise base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="10b43-231">간단한 기본 구성</span><span class="sxs-lookup"><span data-stu-id="10b43-231">The lightweight base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="10b43-232">클라우드 도입 및 하이브리드 솔루션</span><span class="sxs-lookup"><span data-stu-id="10b43-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
