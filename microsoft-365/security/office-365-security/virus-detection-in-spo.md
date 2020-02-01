---
title: SharePoint Online에서의 바이러스 탐지
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Office 365은 사용자가 SharePoint Online에 업로드 하는 파일에서 바이러스를 검색 하 여 맬웨어 로부터 환경을 보호 하는 데 도움이 됩니다. 업로드 후 파일에서 바이러스를 검사 합니다. 파일이 감염 된 것으로 확인 되 면 사용자가 파일을 다운로드 하거나 동기화 할 수 없도록 속성이 설정 됩니다.
ms.openlocfilehash: 1a41c5bb00e7169878206be2db076af0b0745e30
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598005"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="68122-105">SharePoint Online에서의 바이러스 탐지</span><span class="sxs-lookup"><span data-stu-id="68122-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="68122-106">Office 365은 사용자가 SharePoint Online에 업로드 하는 파일에서 바이러스를 검색 하 여 맬웨어 로부터 환경을 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68122-106">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="68122-107">파일을 업로드 한 후 바이러스가 검색 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68122-107">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="68122-108">파일이 감염 된 것으로 확인 되 면 사용자가 파일을 다운로드 하거나 동기화 할 수 없도록 속성이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68122-108">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="68122-109">SharePoint Online의 이러한 바이러스 백신 기능은 바이러스를 포함 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="68122-109">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="68122-110">사용자 환경에 대 한 맬웨어를 방어 하기 위한 단일 방어선이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="68122-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="68122-111">모든 고객은 다양 한 계층에서 맬웨어 방지 보호 기능을 평가 및 구현 하 고 엔터프라이즈 인프라를 보호 하기 위한 모범 사례를 적용할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="68122-111">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="68122-112">전략과 모범 사례에 대 한 자세한 내용은 [보안 로드맵](security-roadmap.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="68122-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="68122-113">감염 된 파일을 SharePoint Online에 업로드 한 경우 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="68122-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="68122-114">Office 365에서는 일반적인 바이러스 검색 엔진을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="68122-114">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="68122-115">엔진은 SharePoint Online 내에서 비동기적으로 실행 되며 업로드 후 일부 파일을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="68122-115">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="68122-116">휴리스틱은 검색할 파일을 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68122-116">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="68122-117">바이러스를 포함 하는 파일을 찾으면 다시 다운로드할 수 없도록 플래그가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68122-117">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="68122-118">2018 년 4 월에는 검색 된 파일에 대 한 250MB 제한이 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="68122-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="68122-119">수행 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68122-119">Here's what happens:</span></span>
  
1. <span data-ttu-id="68122-120">사용자가 파일을 SharePoint Online에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="68122-120">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="68122-121">SharePoint Online은 파일이 검색 조건을 충족 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68122-121">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="68122-122">바이러스 검색 엔진이 파일을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="68122-122">The virus detection engine scans the file.</span></span>
    
4. <span data-ttu-id="68122-123">바이러스가 발견 되 면 바이러스 엔진은 파일에서 감염 되었음을 나타내는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68122-123">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="68122-124">사용자가 브라우저를 사용 하 여 감염 된 파일을 다운로드 하려고 하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="68122-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="68122-125">파일이 바이러스에 감염 된 경우 사용자는 브라우저를 사용 하 여 SharePoint Online에서 파일을 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68122-125">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="68122-126">수행 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68122-126">Here's what happens:</span></span>
  
1. <span data-ttu-id="68122-127">사용자가 웹 브라우저를 열고 SharePoint Online에서 감염 된 파일을 다운로드 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="68122-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="68122-128">사용자에 게 바이러스가 감지 되었음을 알리는 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68122-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="68122-129">사용자에 게 파일을 다운로드 하 고 자체 바이러스 백신 소프트웨어를 사용 하 여 복구를 시도할 수 있는 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68122-129">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="68122-130">**DisallowInfectedFileDownload** 매개 변수와 함께 set-spotenant cmdlet을 사용 하 여 바이러스 백신 경고 창 에서도 검색 된 파일을 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68122-130">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="68122-131">[DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68122-131">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="68122-132">OneDrive 동기화 클라이언트가 감염 된 파일을 동기화 하려고 할 때 수행 되는 작업</span><span class="sxs-lookup"><span data-stu-id="68122-132">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="68122-133">사용자가 새 OneDrive 동기화 클라이언트 (excel.exe) 또는 이전 비즈니스용 OneDrive 동기화 클라이언트 (Groove)를 사용 하 여 파일을 동기화 하는지 여부에 관계 없이 파일에 바이러스가 포함 되어 있으면 동기화 클라이언트에서 다운로드 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68122-133">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="68122-134">동기화 클라이언트에서는 파일을 동기화 할 수 없다는 알림을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="68122-134">The sync client will display a notification that the file can't be synced.</span></span>
  

