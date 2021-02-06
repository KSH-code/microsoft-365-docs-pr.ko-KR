---
title: 스크립트를 사용하여 Core eDiscovery 사례에서 보류에 사용자 추가
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: 스크립트를 실행하여 Microsoft 365 규정 준수 & eDiscovery 사례와 연결된 새 보류에 비즈니스용 OneDrive 사이트를 추가하는 방법을 학습합니다.
ms.openlocfilehash: 72fd9b8e7b63b36399d055e2eb710e8b53967e44
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126441"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="234bf-103">스크립트를 사용하여 Core eDiscovery 사례에서 보류에 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="234bf-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="234bf-104">보안 & 준수 센터 PowerShell에서는 eDiscovery 사례 만들기 및 관리와 관련된 시간이 많이 걸리는 작업을 자동화할 수 있는 cmdlet을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="234bf-105">현재 Security & 준수 센터에서 Core eDiscovery 사례를 사용하여 많은 수의 보유자 콘텐츠 위치를 보류하는 데는 많은 시간 및 준비가 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="234bf-106">예를 들어 보류를 만들기 전에 보류할 각 비즈니스용 OneDrive 사이트의 URL을 수집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="234bf-107">그런 다음 보류하려는 각 사용자에 대해 사서함 및 해당 비즈니스용 OneDrive 사이트를 보류에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="234bf-108">이 문서의 스크립트를 사용하여 이 프로세스를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="234bf-109">이 스크립트는 조직의 내 사이트 도메인 이름(예: URL, 기존 `contoso` eDiscovery 사례의 이름, 사례와 연결된 새 보류의 이름, 보류할 사용자의 전자 메일 주소 목록 및 쿼리 기반 보류를 만들 경우 사용할 검색 쿼리)을 묻는 메시지를 https://contoso-my.sharepoint.com) 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="234bf-110">그런 다음 스크립트는 목록의 각 사용자에 대한 비즈니스용 OneDrive 사이트의 URL을 다운로드하고 새 보류를 만든 다음 목록의 각 사용자에 대한 사서함 및 비즈니스용 OneDrive 사이트를 보류에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="234bf-111">또한 스크립트는 새 보류에 대한 정보가 포함된 로그 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="234bf-112">이를 수행하기 위한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="234bf-113">1단계: SharePoint Online 관리 셸 설치</span><span class="sxs-lookup"><span data-stu-id="234bf-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="234bf-114">2단계: 사용자 목록 생성</span><span class="sxs-lookup"><span data-stu-id="234bf-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="234bf-115">3단계: 스크립트를 실행하여 보류 만들기 및 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="234bf-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="234bf-116">보류에 사용자를 추가하기 전에</span><span class="sxs-lookup"><span data-stu-id="234bf-116">Before you add users to a hold</span></span>

- <span data-ttu-id="234bf-117">3단계에서 스크립트를 실행하기 위해 Security & 준수 센터에서 eDiscovery 관리자 역할 그룹의 구성원이자 SharePoint Online 관리자 역할 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="234bf-118">자세한 내용은 Office 365 보안 및 준수 센터에서 [eDiscovery & 참조하세요.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="234bf-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="234bf-119">보안 및 준수 센터의 eDiscovery 사례와 연결된 보류에 최대 1,000개 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="234bf-120">보류하려는 모든 사용자에게 비즈니스용 OneDrive 사이트가 있는 경우 이 문서의 스크립트를 사용하여 보류에 최대 100명 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="234bf-121">2단계에서 만든 사용자 목록과 3단계의 스크립트를 동일한 폴더에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="234bf-122">이를 통해 스크립트를 보다 쉽게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="234bf-123">이 스크립트는 기존 사례와 연결된 새 보류에 사용자 목록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="234bf-124">스크립트를 실행하기 전에 보류와 연결하려는 사례가 만들어지야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="234bf-125">이 문서의 스크립트는 보안 및 준수 센터 PowerShell & SharePoint Online 관리 셸에 연결할 때 최신 인증을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="234bf-126">Microsoft 365 또는 Microsoft 365 GCC 조직인 경우와 같은 스크립트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="234bf-127">Office 365 Germany 조직, Microsoft 365 GCC High 조직 또는 Microsoft 365 DoD 조직인 경우 스크립트를 편집하여 성공적으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="234bf-128">특히 줄을 편집하고 `Connect-IPPSSession` *ConnectionUri* 및 *AzureADAuthorizationEndpointUri* 매개 변수(및 조직 유형에 적합한 값)를 사용하여 보안 & 준수 센터 PowerShell에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="234bf-129">자세한 내용은 보안 및 준수 센터 [PowerShell에 연결의 & 참조하세요.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)</span><span class="sxs-lookup"><span data-stu-id="234bf-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="234bf-130">이 스크립트는 보안 및 준수 & PowerShell 및 SharePoint Online 관리 셸에서 자동으로 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="234bf-131">스크립트에는 최소한의 오류 처리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-131">The script includes minimal error handling.</span></span> <span data-ttu-id="234bf-132">주요 목적은 각 사용자의 사서함 및 비즈니스용 OneDrive 사이트를 빠르고 쉽게 보류하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="234bf-p109">이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="234bf-138">1단계: SharePoint Online 관리 셸 설치</span><span class="sxs-lookup"><span data-stu-id="234bf-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="234bf-139">첫 번째 단계는 SharePoint Online 관리 셸이 로컬 컴퓨터에 아직 설치되어 있지 않은 경우 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="234bf-140">이 절차에서 셸을 사용할 필요는 없지만 3단계에서 실행한 스크립트에 필요한 필수 요구가 포함되어 있기 때문에 셸을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="234bf-141">이러한 선행 작업을 통해 스크립트가 SharePoint Online과 통신하여 비즈니스용 OneDrive 사이트의 URL을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="234bf-142">[SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) 관리 셸 Windows PowerShell 환경으로 이동한 다음 1단계 및 2단계를 수행하여 로컬 컴퓨터에 SharePoint Online 관리 셸을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="234bf-143">2단계: 사용자 목록 생성</span><span class="sxs-lookup"><span data-stu-id="234bf-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="234bf-144">3단계의 스크립트는 eDiscovery 사례와 연결된 보류를 만들고 사용자 목록의 사서함 및 비즈니스용 OneDrive 사이트를 보류에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="234bf-145">텍스트 파일에 전자 메일 주소를 입력하기만 하면 되거나 Windows PowerShell 명령을 실행하여 전자 메일 주소 목록을 다운로드하여 파일에 저장할 수 있습니다(스크립트를 3단계에서 저장할 폴더와 동일한 폴더에 위치).</span><span class="sxs-lookup"><span data-stu-id="234bf-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="234bf-146">다음은 Exchange Online 조직에 연결된 원격 PowerShell을 사용하여 실행되는 PowerShell 명령으로, 조직의 모든 사용자에 대한 전자 메일 주소 목록을 다운로드하고 이 전자 메일 주소를 HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="234bf-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="234bf-147">이 명령을 실행한 후 텍스트 파일을 열고 속성 이름이 포함된 헤더를  `PrimarySmtpAddress` 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="234bf-148">그런 다음 3단계에서 만들 보류에 추가할 사용자의 전자 메일 주소를 제외한 모든 전자 메일 주소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="234bf-149">전자 메일 주소 목록 앞이나 뒤의 빈 행이 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="234bf-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="234bf-150">3단계: 스크립트를 실행하여 보류 만들기 및 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="234bf-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="234bf-151">이 단계에서 스크립트를 실행하면 다음 정보를 입력하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="234bf-152">스크립트를 실행하기 전에 이 정보를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="234bf-153">**사용자 자격 증명:** 스크립트는 자격 증명을 사용하여 원격 PowerShell을 사용하여 보안 & 준수 센터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-153">**Your user credentials:** The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="234bf-154">또한 이러한 자격 증명을 사용하여 SharePoint Online에 액세스하여 사용자 목록에 대한 비즈니스용 OneDrive URL을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="234bf-155">**내 사이트 도메인의 이름:** 내 사이트 도메인은 조직의 모든 비즈니스용 OneDrive 사이트를 포함하는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-155">**Name of your My Site domain:** The My Site domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="234bf-156">예를 들어 내 사이트 도메인의 URL이면 스크립트에서 내 사이트 도메인의 이름을 묻는 메시지를 표시하는 경우 **https://contoso-my.sharepoint.com**  `contoso` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-156">For example, if the URL for your My Site domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your My Site domain.</span></span>

- <span data-ttu-id="234bf-157">**사례의 이름:** 기존 사례의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-157">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="234bf-158">스크립트는 이 사례와 연결된 새 보류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-158">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="234bf-159">**보류의 이름:** 스크립트가 만들고 지정된 사례와 연결되는 보류의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-159">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="234bf-160">**쿼리 기반 보류에 대한 검색 쿼리:** 지정한 검색 조건을 충족하는 콘텐츠만 보류할 수 있도록 쿼리 기반 보류를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-160">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="234bf-161">모든 콘텐츠를 보류할 수 있습니다. 검색 쿼리를 묻는 메시지가 표시될 때 **Enter를** 누르기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-161">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="234bf-162">**보류 켜기 또는 해제:** 스크립트를 만든 후 보류를 켜거나 스크립트를 사용하도록 설정하지 않고 보류를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-162">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="234bf-163">스크립트를 켜지 않은 경우 나중에 보안 및 준수 센터에서 또는 다음 PowerShell 명령을 실행하여 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-163">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="234bf-164">**사용자 목록이** 있는 텍스트 파일의 이름 - 보류에 추가할 사용자 목록이 포함된 2단계의 텍스트 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-164">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="234bf-165">이 파일이 스크립트와 동일한 폴더에 있는 경우 파일의 이름(예: HoldUsers.txt)을 입력하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-165">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="234bf-166">텍스트 파일이 다른 폴더에 있는 경우 파일의 전체 경로 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-166">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="234bf-167">스크립트에서 요청하는 정보를 수집한 후 마지막 단계는 스크립트를 실행하여 새 보류를 만들고 사용자를 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-167">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="234bf-168">파일 이름 접미사로 Windows PowerShell 스크립트 파일에 다음 텍스트를 `.ps1` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-168">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="234bf-169">예를 들면 `AddUsersToHold.ps1`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-169">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="234bf-170">로컬 컴퓨터에서 스크립트를 Windows PowerShell 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-170">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="234bf-171">스크립트를 실행합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="234bf-171">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="234bf-172">스크립트에서 요청하는 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-172">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="234bf-173">스크립트는 보안 & 준수 센터 PowerShell에 연결한 다음 eDiscovery 사례에 새 보류를 만들고 목록의 사용자에 대한 사서함 및 비즈니스용 OneDrive를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-173">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="234bf-174">보안 및 준수 센터의 **eDiscovery** & 사례로 이동하여 새 보류를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-174">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="234bf-175">스크립트 실행이 완료되면 다음 로그 파일을 만들고 스크립트가 있는 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-175">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="234bf-176">**LocationsOnHold.txt:** 스크립트가 보류된 사서함 및 비즈니스용 OneDrive 사이트 목록이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-176">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="234bf-177">**LocationsNotOnHold.txt:** 스크립트가 보류되지 않은 사서함 및 비즈니스용 OneDrive 사이트 목록이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-177">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="234bf-178">사용자에게 사서함이 있지만 비즈니스용 OneDrive 사이트는 없는 경우 사용자는 보류되지 않은 비즈니스용 OneDrive 사이트 목록에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-178">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="234bf-179">**GetCaseHoldPolicy.txt:** 새 보류를 만들고 나서 스크립트가 실행된 새 보류에 대한 **Get-CaseHoldPolicy** cmdlet의 출력을 포함</span><span class="sxs-lookup"><span data-stu-id="234bf-179">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="234bf-180">이 cmdlet이 반환하는 정보에는 사서함 및 비즈니스용 OneDrive 사이트가 보류된 사용자 목록과 보류를 사용할 수 있는지 여부가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-180">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="234bf-181">**GetCaseHoldRule.txt:** 새 보류를 만들고 나서 스크립트가 실행된 새 보류에 대한 **Get-CaseHoldRule** cmdlet의 출력을 포함</span><span class="sxs-lookup"><span data-stu-id="234bf-181">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="234bf-182">이 cmdlet이 반환하는 정보에는 스크립트를 사용하여 쿼리 기반 보류를 만든 경우 검색 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="234bf-182">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
