---
title: '비즈니스용 Microsoft 365로 Google 파일 마이그레이션 '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Mover를 사용하여 Google 파일을 비즈니스용 Microsoft 365로 마이그레이션하는 방법을 학습합니다.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913577"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="fdabe-103">비즈니스용 Microsoft 365로 Google 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="fdabe-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="fdabe-104">비즈니스용 Microsoft 365로 이동하면 Google Drive에서 파일을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="fdabe-105">Mover 앱을 사용하여 개인 및 공유 드라이브에서 파일을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="fdabe-106">자세한 내용은 [Mover 클라우드 마이그레이션을 참조하세요.](/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="fdabe-106">For more information, see [Mover Cloud Migration](/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="fdabe-107">Mover는 파일의 복사본을 만들어 비즈니스용 Microsoft 365로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="fdabe-108">원본 파일은 Google Drives에도 그대로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="fdabe-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="fdabe-109">Before you start</span></span>

<span data-ttu-id="fdabe-110">모든 사용자는 비즈니스용 Microsoft 365에 로그인하고 비즈니스용 OneDrive를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="fdabe-111">이 작업을 위해 [](https://office.com)office.com 으로 이동하여 비즈니스용 Microsoft 365 자격 증명으로 로그인한 다음 OneDrive를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="fdabe-112">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="fdabe-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="fdabe-113">Mover 설치</span><span class="sxs-lookup"><span data-stu-id="fdabe-113">Install Mover</span></span>

1. <span data-ttu-id="fdabe-114">에서 Google Workspace 관리 콘솔에 [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="fdabe-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="fdabe-115">앱   >  **Google Workspace Marketplace 앱** 도메인 설치 목록에 앱  >  **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="fdabe-116">Mover를 검색하고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="fdabe-117">도메인 **설치 를 선택한** 다음 계속 **을 계속합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="fdabe-118">사용 권한을 검토하고 사용 약관에 동의할 확인란을 선택한 다음 **허용,** **다음,** 완료를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="fdabe-119">커넥터 만들기 및 마이그레이션 실행</span><span class="sxs-lookup"><span data-stu-id="fdabe-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="fdabe-120">Google **Workspace Marketplace 앱으로 돌아오기**</span><span class="sxs-lookup"><span data-stu-id="fdabe-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="fdabe-121">브라우저를 새로 고치고 **Mover 앱을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="fdabe-122">아래로 스크롤하여 유니버설 탐색 링크를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="fdabe-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="fdabe-123">새 **커넥터 승인을 선택하고** G **Suite(관리자)를** 찾은 다음 **승인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="fdabe-124">원하는 **경우 표시 이름** 을 변경한 다음 **승인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="fdabe-125">Google 관리자 계정을 선택하고 사용 권한을 검토한 다음 허용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="fdabe-126">Mover는 검색된 팀 드라이브 및 사용자 드라이브의 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="fdabe-127">대상 **선택에서** **새** 커넥터 승인을 선택하고 **Office 365를** 찾은 다음 **승인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="fdabe-128">Azure Active Directory에서 Mover 앱에 대한 사용 권한을 부여하려면 에서 로 [aka.ms/Office365MoverAuth.](https://aka.ms/Office365MoverAuth)</span><span class="sxs-lookup"><span data-stu-id="fdabe-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="fdabe-129">**Office 365 Mover**, **Permissions**, **Grant admin consent for your company을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="fdabe-130">계정을 선택하고 사용 권한을 검토하고 수락을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="fdabe-131">속성을 **선택하고** 사용자 할당이 **필요한지** 확인을 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="fdabe-132">Mover 앱으로 돌아가서 표시 이름 을 변경하고 원하는 경우 **승인을** 선택한 다음 Microsoft 관리자 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="fdabe-133">Mover는 검색된 SharePoint Online(또는 SPO) 사이트 및 사용자 수에 대해 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="fdabe-134">마이그레이션 **설정 계속,** **사용자** 추가를 선택한 다음 자동으로 사용자 검색 **및 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="fdabe-135">Mover 앱은 Google의 원본 경로에서 Microsoft 365의 대상 경로로 드라이브를 매핑하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="fdabe-136">드라이브가 자동으로 매핑되지 않는 경우 나중에 공유 드라이브를 SharePoint 문서 라이브러리로 마이그레이션하는 데 사용할 대상 경로를 CSV 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="fdabe-137">이 경우 마이그레이션된 파일이라는 SharePoint 사이트를 추가하고 문서 페이지의 URL을 기록했습니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="fdabe-138">그런 다음 원본 경로, 대상 경로 및 태그 형식을 사용하여 CSV 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="fdabe-139">자세한 내용은 을 [aka.ms/movercsv.](/sharepointmigration/mover-create-migration-csv)</span><span class="sxs-lookup"><span data-stu-id="fdabe-139">For details see [aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="fdabe-140">대상 경로 URL을 추가할 때 공유 문서 다음에 있는 모든 것을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="fdabe-141">예를 들어 이 전체 URL은 작동하지 않습니다. `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="fdabe-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="fdabe-142">다음으로 변경합니다. `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="fdabe-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="fdabe-143">CSV 파일이 준비되면 마이그레이션 **작업,** 마이그레이션에 **추가,** **업로드할 파일 선택을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="fdabe-144">CSV 파일로 이동하여 선택한 다음 열기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="fdabe-145">마이그레이션할 파일을 가진 사용자 드라이브를 선택한 다음 사용자 마이그레이션 **시작 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="fdabe-146">마이그레이션 정보를 검토하고 마이그레이션을 시작할 때를 선택하고 사용 약관에 동의한 다음 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fdabe-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="fdabe-147">Mover 앱은 마이그레이션 프로세스가 완료되면 알려주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdabe-147">The Mover app will inform you when the migration process is complete.</span></span>