---
title: PowerShell을 SharePoint 온라인 사이트 그룹 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
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
description: 이 문서에서는 PowerShell을 사용하여 온라인 사이트 Microsoft 365 관리하기 위한 SharePoint 있습니다.
ms.openlocfilehash: bcc7a00a6114a6fa2ba8aa02520267bd03a0abf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909541"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="7012f-103">PowerShell을 SharePoint 온라인 사이트 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="7012f-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="7012f-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7012f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7012f-105">Microsoft 365 관리 센터를 사용할 수 있는 경우 PowerShell을 사용하여 Microsoft 365 온라인 SharePoint 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7012f-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="7012f-106">Before you begin</span></span>

<span data-ttu-id="7012f-107">이 문서의 절차를 수행하려면 SharePoint 온라인에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="7012f-108">자세한 내용은 커넥트 [PowerShell을 SharePoint 참조하세요.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="7012f-108">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="7012f-109">PowerShell을 SharePoint Online Microsoft 365 보기</span><span class="sxs-lookup"><span data-stu-id="7012f-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="7012f-110">SharePoint 관리 센터에는 사이트 그룹을 관리하기 위한 몇 가지 사용이 간편한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="7012f-111">예를 들어 사이트의 그룹과 그룹 구성원을 봐야 하는 경우를 `https://litwareinc.sharepoint.com/sites/finance` 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="7012f-112">다음과 같은 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="7012f-113">SharePoint 관리 센터에서 활성 **사이트를** 클릭한 다음 사이트의 URL을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="7012f-114">사이트 페이지에서 페이지 **오른쪽 설정** 있는 사이트 아이콘을 클릭한 다음 사이트 사용 권한을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7012f-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="7012f-115">확인하려는 다음 사이트에 대해 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="7012f-116">PowerShell을 사용하여 그룹 목록을 Microsoft 365 다음 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

<span data-ttu-id="7012f-117">다음 두 가지 방법으로 온라인 관리 셸 명령 프롬프트에서 이 SharePoint 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="7012f-118">명령을 메모장(또는 다른 텍스트 편집기)에 복사하고 **$siteURL** 변수의 값을 수정하고 명령을 선택한 다음 SharePoint 온라인 관리 셸 명령 프롬프트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="7012f-119">그러면 PowerShell이 프롬프트에서 **>>** 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="7012f-120">Enter를 눌러 명령을 `foreach` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="7012f-121">명령을 메모장(또는 다른 텍스트 편집기)에 복사하고  $siteURL 변수의 값을 수정한 다음 이 텍스트 파일을 적절한 폴더에 이름과 .ps1 확장명으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="7012f-122">그런 다음 경로와 파일 이름을 지정하여 SharePoint Online 관리 셸 명령 프롬프트에서 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="7012f-123">예제 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="7012f-124">두 경우 모두 이와 유사한 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-124">In both cases, you should see something similar to this:</span></span>

![SharePoint 온라인 사이트 그룹](../media/SPO-site-groups.png)

<span data-ttu-id="7012f-126">이러한 그룹은 사이트에 대해 만들어진 모든 그룹 및 해당 그룹에 할당된 `https://litwareinc.sharepoint.com/sites/finance` 모든 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="7012f-127">그룹 이름은 구성원과 그룹 이름을 구분하는 데 도움이 있도록 노란색입니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="7012f-128">또 다른 예로, 모든 SharePoint 온라인 사이트에 대한 그룹 및 모든 그룹 구성원을 나열하는 명령 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a><span data-ttu-id="7012f-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7012f-129">See also</span></span>

[<span data-ttu-id="7012f-130">커넥트 PowerShell을 SharePoint 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7012f-130">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="7012f-131">PowerShell을 SharePoint 온라인 사이트 만들기 및 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="7012f-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="7012f-132">PowerShell을 사용하여 SharePoint 온라인 사용자 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="7012f-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="7012f-133">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="7012f-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7012f-134">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="7012f-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)