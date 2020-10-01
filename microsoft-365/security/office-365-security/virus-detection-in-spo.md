---
title: SharePoint Online, OneDrive 및 Microsoft 팀의 기본 제공 바이러스 방지
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
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
description: 사용자가 업로드 하 고 사용자가 파일을 다운로드 하거나 동기화 하지 못하게 하는 파일에서 SharePoint Online이 바이러스를 감지 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327990"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="5be71-103">SharePoint Online, OneDrive 및 Microsoft 팀의 기본 제공 바이러스 방지</span><span class="sxs-lookup"><span data-stu-id="5be71-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5be71-104">Microsoft 365에서는 사용자가 SharePoint Online, OneDrive 및 Microsoft 팀에 업로드 하는 파일을 검색 하는 일반적인 바이러스 검색 엔진을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-104">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="5be71-105">이 보호는 SharePoint Online, OneDrive 및 Microsoft 팀이 포함 된 모든 구독에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-105">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5be71-106">기본 제공 바이러스 백신 기능은 바이러스를 포함 하는 데 도움을 주는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-106">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="5be71-107">사용자 환경에 대 한 맬웨어를 방어 하기 위한 단일 방어선이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-107">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="5be71-108">모든 고객은 다양 한 계층에서 맬웨어 방지 보호 기능을 조사 및 구현 하 고 엔터프라이즈 인프라를 보호 하기 위한 모범 사례를 적용할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-108">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="5be71-109">전략과 모범 사례에 대 한 자세한 내용은 [보안 로드맵](security-roadmap.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5be71-109">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="5be71-110">감염 된 파일을 SharePoint Online에 업로드 한 경우 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="5be71-110">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="5be71-111">Microsoft 365 바이러스 검색 엔진은 SharePoint Online 내에서 비동기적으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-111">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="5be71-112">**업로드 시 모든 파일이 자동으로 검색 되지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="5be71-112">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="5be71-113">추론에서는 검색할 파일을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-113">Heuristics determine the files to scan.</span></span> <span data-ttu-id="5be71-114">파일이 바이러스를 포함 하는 것을 발견 하면 파일에 플래그를 지정 하 여 다시 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-114">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="5be71-115">2018 년 4 월에는 검색 된 파일에 대 한 250MB 제한이 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-115">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="5be71-116">수행 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-116">Here's what happens:</span></span>

1. <span data-ttu-id="5be71-117">사용자가 파일을 SharePoint Online에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-117">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="5be71-118">SharePoint Online은 파일이 검색 조건을 충족 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-118">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="5be71-119">바이러스 검색 엔진이 파일을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-119">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="5be71-120">바이러스가 발견 되 면 바이러스 엔진은 파일에서 감염 되었음을 나타내는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-120">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="5be71-121">사용자가 브라우저를 사용 하 여 감염 된 파일을 다운로드 하려고 하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="5be71-121">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="5be71-122">파일이 감염 된 경우 사용자는 브라우저를 사용 하 여 SharePoint Online에서 파일을 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-122">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="5be71-123">수행 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-123">Here's what happens:</span></span>

1. <span data-ttu-id="5be71-124">사용자가 웹 브라우저를 열고 SharePoint Online에서 감염 된 파일을 다운로드 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-124">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="5be71-125">사용자에 게 바이러스가 감지 되었음을 알리는 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-125">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="5be71-126">기본적으로 사용자에 게는 파일을 다운로드 하 여 자체 장치에서 바이러스 백신 소프트웨어를 사용 하 여 치료 하려고 할 수 있는 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-126">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="5be71-127">관리자는 바이러스 백신 경고 창 에서도 사용자가 감염 된 파일을 다운로드 하지 못하도록 SharePoint Online PowerShell의 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) Cmdlet에 *DisallowInfectedFileDownload* 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-127">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="5be71-128">자세한 내용은 [SharePoint Online PowerShell을 사용 하 여 사용자가 악성 파일을 다운로드 하지 못하도록](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5be71-128">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="5be71-129">*DisallowInfectedFileDownload* 매개 변수를 사용 하도록 설정 하면 검색/차단 된 파일에 대 한 액세스가 사용자 및 관리자에 대해 완전히 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-129">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="5be71-130">OneDrive 동기화 클라이언트가 감염 된 파일을 동기화 하려고 할 때 수행 되는 작업</span><span class="sxs-lookup"><span data-stu-id="5be71-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="5be71-131">OneDrive 동기화 클라이언트는 바이러스를 포함 하는 파일을 다운로드 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-131">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="5be71-132">동기화 클라이언트에서는 파일을 동기화 할 수 없다는 알림을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a><span data-ttu-id="5be71-133">Office 365 Advanced Threat Protection을 사용한 확장 기능</span><span class="sxs-lookup"><span data-stu-id="5be71-133">Extended capabilities with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="5be71-134">Microsoft 365 조직에서 구독에 포함 되거나 추가 기능으로 구매한 [Office 365 Advanced Threat Protection (atp)](office-365-atp.md) 을 사용 하는 경우 SharePoint, OneDrive 및 Microsoft 팀에서 atp가 향상 된 보고 및 보호 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5be71-134">Microsoft 365 organizations that have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) included in their subscription or purchased as an add-on can enable ATP for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="5be71-135">자세한 내용은 [SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP](atp-for-spo-odb-and-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5be71-135">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="5be71-136">추가 정보</span><span class="sxs-lookup"><span data-stu-id="5be71-136">More information</span></span>

<span data-ttu-id="5be71-137">SharePoint Online, OneDrive 및 Microsoft 팀의 바이러스 백신에 대 한 자세한 내용은 [위협 으로부터 보호](protect-against-threats.md) 를 참조 하 고 [SharePoint, OneDrive 및 MICROSOFT 팀에서 ATP를 켜십시오](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5be71-137">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
