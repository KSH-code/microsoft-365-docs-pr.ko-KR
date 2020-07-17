---
title: 보안 & 준수 센터에서 코어 eDiscovery 사례의 보류에 사용자를 추가 하는 스크립트 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: 스크립트를 실행 하 여 보안 & 준수 센터에서 eDiscovery 사례와 관련 된 새 보류에 사서함 & 비즈니스용 OneDrive 사이트에 추가 하는 방법을 알아봅니다.
ms.openlocfilehash: cfa7e176c3974d51fbcc87866c1482277d6010e1
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016311"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="2f1d9-103">스크립트를 사용 하 여 중요 eDiscovery 사례에서 보류에 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="2f1d9-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="2f1d9-104">보안 & 준수 센터에서는 eDiscovery 사례를 만들고 관리 하는 데 관련 된 시간이 오래 걸리는 작업을 자동화할 수 있는 PowerShell cmdlet을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-104">The Security & Compliance Center provides PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="2f1d9-105">현재는 보안 & 준수 센터에서 eDiscovery 사례 도구를 사용 하 여 많은 수의 custodian 콘텐츠 위치를 유지 하는 데 시간이 오래 걸리고 준비를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-105">Currently, using the eDiscovery case tool in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="2f1d9-106">예를 들어 보류를 만들기 전에 보류 하려는 각 비즈니스용 OneDrive 사이트의 URL을 수집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="2f1d9-107">그런 다음 보류 하려는 각 사용자에 대해 해당 사서함 및 비즈니스용 OneDrive 사이트를 보류에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="2f1d9-108">향후 릴리스된 보안 & 준수 센터에서이 작업을 수행 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-108">In future releases of the Security & Compliance Center, this will get easier to do.</span></span> <span data-ttu-id="2f1d9-109">그때까지이 문서의 스크립트를 사용 하 여이 프로세스를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-109">Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="2f1d9-110">이 스크립트는 URL의 **contoso** , https://contoso-my.sharepoint.com) 기존 eDiscovery 사례 이름, 사례와 연결 된 새 보류의 이름, 유지 하려는 사용자의 전자 메일 주소 목록, 쿼리 기반 보존을 만들려는 경우 사용할 검색 쿼리 등의 조직 내 사이트 도메인 이름을 입력 하 라는 메시지를 표시 합니다 (예:</span><span class="sxs-lookup"><span data-stu-id="2f1d9-110">The script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="2f1d9-111">그런 다음 스크립트는 목록에 있는 각 사용자의 비즈니스용 OneDrive 사이트에 대 한 URL을 가져오고, 새로 보존을 만든 다음 목록에 있는 각 사용자에 대 한 비즈니스용 OneDrive 사이트를 보류에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-111">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="2f1d9-112">또한이 스크립트는 새로 보존에 대 한 정보가 포함 된 로그 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-112">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="2f1d9-113">이 작업을 수행 하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="2f1d9-114">1단계: SharePoint Online 관리 셸 설치</span><span class="sxs-lookup"><span data-stu-id="2f1d9-114">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="2f1d9-115">2 단계: 사용자 목록 생성</span><span class="sxs-lookup"><span data-stu-id="2f1d9-115">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="2f1d9-116">3 단계: 스크립트를 실행 하 여 보류 만들기 및 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="2f1d9-116">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="2f1d9-117">보류에 사용자를 추가 하기 전에</span><span class="sxs-lookup"><span data-stu-id="2f1d9-117">Before you add users to a hold</span></span>

- <span data-ttu-id="2f1d9-118">3 단계에서 스크립트를 실행 하려면 보안 & 준수 센터 및 SharePoint Online 관리자에서 eDiscovery 관리자 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-118">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="2f1d9-119">자세한 내용은 [Office 365 보안 & 준수 센터에서 eDiscovery 사용 권한 할당](assign-ediscovery-permissions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-119">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="2f1d9-120">최대 1000 개의 사서함과 100 사이트를 보안 & 준수 센터에서 eDiscovery 사례와 연결 된 보류에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-120">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="2f1d9-121">보존 하려는 모든 사용자에 게 비즈니스용 OneDrive 사이트가 있는 경우이 문서의 스크립트를 사용 하 여 최대 100 명의 사용자를 보류에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-121">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="2f1d9-122">2 단계에서 만든 사용자 목록과 3 단계의 스크립트를 같은 폴더에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-122">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="2f1d9-123">이를 통해 스크립트를 보다 쉽게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-123">That will make it easier to run the script.</span></span>

- <span data-ttu-id="2f1d9-124">이 스크립트는 기존 사례와 연결 된 새 보류에 사용자 목록을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-124">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="2f1d9-125">스크립트를 실행 하기 전에 보류를 연결 하려는 대/소문자를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-125">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="2f1d9-126">스크립트에 최소 오류 처리가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-126">The script includes minimal error handling.</span></span> <span data-ttu-id="2f1d9-127">이 기본 목적은 사서함과 각 사용자의 비즈니스용 OneDrive 사이트를 보류 하 고 쉽게 사용할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-127">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="2f1d9-p108">이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-p108">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="2f1d9-133">1단계: SharePoint Online 관리 셸 설치</span><span class="sxs-lookup"><span data-stu-id="2f1d9-133">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="2f1d9-134">첫 번째 단계는 SharePoint Online 관리 셸을 로컬 컴퓨터에 아직 설치 하지 않은 경우 설치 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-134">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="2f1d9-135">이 절차에서 셸을 사용할 필요는 없지만 3 단계에서 실행 하는 스크립트에 필요한 필수 구성 요소를 포함 하기 때문에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-135">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="2f1d9-136">이러한 필수 구성 요소를 통해 스크립트가 SharePoint Online과 통신 하 여 비즈니스용 OneDrive 사이트용 Url을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-136">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="2f1d9-137">[Sharepoint Online 관리 셸 Windows PowerShell 환경 설정](https://go.microsoft.com/fwlink/p/?LinkID=286318) 으로 이동 하 여 1 단계와 2 단계를 수행 하 여 로컬 컴퓨터에 SharePoint Online 관리 셸을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-137">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="2f1d9-138">2 단계: 사용자 목록 생성</span><span class="sxs-lookup"><span data-stu-id="2f1d9-138">Step 2: Generate a list of users</span></span>

<span data-ttu-id="2f1d9-139">3 단계의 스크립트에서는 eDiscovery 사례와 연결 된 보류를 만들고 사용자 목록의 사서함 및 비즈니스용 OneDrive 사이트를 보류에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-139">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="2f1d9-140">텍스트 파일에 전자 메일 주소를 입력 하거나, Windows PowerShell에서 명령을 실행 하 여 전자 메일 주소 목록을 가져오고이를 파일 (3 단계에서 스크립트를 저장할 동일한 폴더에 있음)에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-140">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="2f1d9-141">다음은 Exchange Online 조직에 연결 된 원격 PowerShell을 사용 하 여 실행 하는 PowerShell 명령으로, 조직의 모든 사용자에 대 한 전자 메일 주소 목록을 가져오고이를 HoldUsers.txt 이라는 텍스트 파일에 저장 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-141">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="2f1d9-142">이 명령을 실행 한 후에는 텍스트 파일을 열고 속성 이름이 포함 된 헤더를 제거 `PrimarySmtpAddress` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-142">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="2f1d9-143">그런 다음 3 단계에서 만들 보류에 추가할 사용자에 대 한 전자 메일 주소를 제외 하 고 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-143">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="2f1d9-144">전자 메일 주소 목록 앞 이나 뒤에 빈 행이 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-144">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="2f1d9-145">3 단계: 스크립트를 실행 하 여 보류 만들기 및 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="2f1d9-145">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="2f1d9-146">이 단계에서 스크립트를 실행 하면 다음 정보를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-146">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="2f1d9-147">스크립트를 실행 하기 전에이 정보를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-147">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="2f1d9-148">**사용자 자격 증명:** 스크립트는 사용자의 자격 증명을 사용 하 여 원격 PowerShell을 통해 보안 & 준수 센터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-148">**Your user credentials:** The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="2f1d9-149">또한 이러한 자격 증명을 사용 하 여 SharePoint Online에 액세스 하 여 사용자 목록에 대 한 비즈니스용 OneDrive Url을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-149">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="2f1d9-150">**내 사이트 도메인의 이름입니다.** 내 사이트 도메인은 조직 내 모든 비즈니스용 OneDrive를 포함 하는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-150">**Name of your MySite domain:** The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="2f1d9-151">예를 들어 내 사이트 도메인의 URL이 인 경우 **https://contoso-my.sharepoint.com** `contoso` 스크립트에서 내 사이트 도메인 이름을 묻는 메시지를 표시 하는 경우를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-151">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span>

- <span data-ttu-id="2f1d9-152">**사례 이름:** 기존 사례 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-152">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="2f1d9-153">스크립트는이 사례와 연결 된 새 보류를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-153">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="2f1d9-154">**보류의 이름입니다.** 스크립트에서 만들고 지정 된 사례와 연결 하는 보류의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-154">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="2f1d9-155">**쿼리 기반 보존에 대 한 검색 쿼리:** 지정 된 검색 조건을 충족 하는 콘텐츠만 보존 되도록 쿼리 기반 보존을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-155">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="2f1d9-156">모든 콘텐츠를 보류 상태로 설정 하려면 검색 쿼리를 **입력** 하 라는 메시지가 표시 되 면 enter 키를 누르기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-156">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="2f1d9-157">**보류 설정 여부를 지정 합니다.** 스크립트를 만든 후에는 해당 보류를 사용 하도록 설정할 수도 있고, 스크립트를 사용 하지 않고 보류를 만들도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-157">**Whether or not to turn on the hold:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="2f1d9-158">스크립트를 설정 하지 않은 경우 나중에 보안 & 준수 센터에서 또는 다음 PowerShell 명령을 실행 하 여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-158">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="2f1d9-159">**사용자 목록이 포함 된 텍스트 파일의 이름** -2 단계의 텍스트 파일 이름으로, 보류에 추가할 사용자의 목록이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-159">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="2f1d9-160">이 파일이 스크립트와 같은 폴더에 있는 경우에는 파일의 이름 (예: HoldUsers.txt)을 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-160">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="2f1d9-161">텍스트 파일이 다른 폴더에 있으면 파일의 전체 경로 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-161">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="2f1d9-162">스크립트에서 입력 해야 하는 정보를 수집한 후 마지막 단계는 스크립트를 실행 하 여 새 보류를 만들고 사용자를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-162">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="2f1d9-163">파일 이름 접미사를 사용 하 여 Windows PowerShell 스크립트 파일에 다음 텍스트를 저장 `.ps1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-163">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="2f1d9-164">예를 들면 `AddUsersToHold.ps1`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-164">For example, `AddUsersToHold.ps1`.</span></span>

  ```powershell
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
      }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. <span data-ttu-id="2f1d9-165">로컬 컴퓨터에서 Windows PowerShell을 열고 스크립트를 저장 한 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-165">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="2f1d9-166">스크립트를 실행 합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="2f1d9-166">Run the script; for example:</span></span>

      ```powershell
    .\AddUsersToHold.ps1
      ```

4. <span data-ttu-id="2f1d9-167">스크립트에서 묻는 메시지가 표시 되는 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-167">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="2f1d9-168">이 스크립트는 Security & 준수 센터 PowerShell에 연결한 다음 eDiscovery 사례에 새로 보존을 만들고 사서함 및 비즈니스용 OneDrive를 목록의 사용자에 게 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-168">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="2f1d9-169">보안 & 준수 센터의 **eDiscovery** 페이지에서 해당 사례로 이동 하 여 새 보존을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-169">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span> 

<span data-ttu-id="2f1d9-170">스크립트 실행이 완료 되 면 다음 로그 파일이 만들어지고 스크립트가 있는 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-170">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="2f1d9-171">**LocationsOnHold.txt:** 스크립트에서 성공적으로 보류 된 사서함 및 비즈니스용 OneDrive 사이트의 목록이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-171">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="2f1d9-172">**LocationsNotOnHold.txt:** 스크립트가 보류 되지 않은 사서함 및 비즈니스용 OneDrive 사이트의 목록이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-172">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="2f1d9-173">사용자에 게 사서함이 있지만 비즈니스용 OneDrive 사이트가 아닌 경우에는 보류 되지 않은 비즈니스용 OneDrive 사이트 목록에 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-173">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="2f1d9-174">**GetCaseHoldPolicy.txt:** 새 보류를 만든 후 스크립트가 실행 된 새 보류에 대 한 **new-caseholdpolicy** cmdlet의 출력을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-174">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="2f1d9-175">이 cmdlet이 반환 하는 정보에는 사서함과 비즈니스용 OneDrive 사이트를 보류 하는 사용자 목록과 보류를 사용 하거나 사용 하지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-175">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="2f1d9-176">**GetCaseHoldRule.txt:** 새 보류를 만든 후 스크립트가 실행 된 새 보류에 대 한 **new-caseholdrule** cmdlet의 출력을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-176">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="2f1d9-177">이 cmdlet이 반환 하는 정보에는 스크립트를 사용 하 여 쿼리 기반 보존을 만든 경우 검색 쿼리가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f1d9-177">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
