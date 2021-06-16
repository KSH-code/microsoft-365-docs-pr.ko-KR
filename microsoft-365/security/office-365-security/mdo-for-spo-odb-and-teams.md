---
title: SharePoint, OneDrive 및 Microsoft Teams를 위한 안전한 첨부 파일
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Office 365 Online, Office 365 및 SharePoint 파일용 Microsoft Defender에 대해 비즈니스용 OneDrive Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7aa375020ce05ca1d484bb7ed18b8cf7a6e7d04e
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932845"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bb019-103">SharePoint, OneDrive 및 Microsoft Teams를 위한 안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="bb019-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bb019-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="bb019-104">**Applies to**</span></span>
- [<span data-ttu-id="bb019-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="bb019-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bb019-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb019-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="bb019-107">[Microsoft Defender](whats-new-in-defender-for-office-365.md) for SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한 첨부 파일은 Office 365 에서 일반적인 바이러스 검색 엔진에 의해 업로드 시 이미 검색된 파일에 대한 추가 보호 [계층을 Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="bb019-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="bb019-108">SharePoint, OneDrive 및 Microsoft Teams 안전한 첨부 파일은 팀 사이트 및 문서 라이브러리에서 악성으로 식별된 기존 파일을 검색하고 차단하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="bb019-109">기본 설정, SharePoint, OneDrive 및 Microsoft Teams 안전한 첨부 파일은 기본적으로 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="bb019-110">이 기능을 켜면 에 대해 안전한 첨부 파일 SharePoint, OneDrive [및 Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bb019-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="bb019-111">파일, SharePoint, OneDrive 및 Microsoft Teams 안전한 첨부 Microsoft Teams 방법</span><span class="sxs-lookup"><span data-stu-id="bb019-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="bb019-112">파일, SharePoint, OneDrive Microsoft Teams 안전한 첨부 파일을 사용하도록 설정하고 파일을 악성으로 식별하면 파일이 파일 저장소와 직접 통합되어 잠겨집니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="bb019-113">다음 그림은 라이브러리에서 검색되는 악성 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-113">The following image shows an example of a malicious file detected in a library.</span></span>

![악성 파일로 탐지된 한 개의 파일을 포함한 비즈니스용 OneDrive에 있는 파일](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="bb019-115">차단된 파일은 문서 라이브러리 및 웹, 모바일 또는 데스크톱 응용 프로그램에 계속 나열되어도 파일을 열거나 복사하거나 이동하거나 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="bb019-116">그러나 차단된 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="bb019-117">다음은 차단된 파일이 모바일 장치에서 어떻게 보이는지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![OneDrive 모바일 앱의 비즈니스용 OneDrive에서 차단된 파일 삭제](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="bb019-119">기본적으로 사용자들은 차단된 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="bb019-120">다음은 차단된 파일을 다운로드할 때의 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![비즈니스용 OneDrive에서 차단된 파일 다운로드](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="bb019-122">SharePoint 온라인 관리자는 사용자가 악성 파일을 다운로드하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="bb019-123">자세한 내용은 [SharePoint Online PowerShell을](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)사용하여 사용자가 악성 파일을 다운로드하지 못하게 방지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb019-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="bb019-124">파일이 악의적인 것으로 감지된 사용자 경험에 대한 자세한 내용은 SharePoint [Online,](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)OneDrive 또는 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb019-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bb019-125">안전한 첨부 파일에서 검색된 파일, SharePoint, OneDrive 파일에 대한 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bb019-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="bb019-126">SharePoint, OneDrive 및 Microsoft Teams 안전한 첨부 파일로 식별된 파일은 Office 365 및 탐색기(및 실시간 검색)에 [대한 Microsoft Defender에](view-reports-for-mdo.md) 대한 보고서에 [나타납니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="bb019-126">Files that are identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="bb019-127">2018년 5월을 현재, 파일, SharePoint, OneDrive 및 Microsoft Teams 안전한 첨부 파일로 식별된 파일은 또한 검사에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-127">As of May 2018, when a file is identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, the file is also available in quarantine.</span></span> <span data-ttu-id="bb019-128">자세한 내용은 [Manage quarantined files in Defender for Office 365.](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="bb019-128">For more information, see [Manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="bb019-129">다음의 사항을 염두에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-129">Keep these points in mind</span></span>

- <span data-ttu-id="bb019-130">Office 365 Defender는 SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft Teams 검색하지 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb019-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="bb019-131">이것은 정상적인 현상입니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-131">This is by design.</span></span> <span data-ttu-id="bb019-132">파일이 비동기적으로 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="bb019-133">이 프로세스에서는 공유 및 게스트 활동 이벤트를 스마트 추적 및 위협 신호와 함께 사용하여 악성 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="bb019-134">최신 환경을 SharePoint 사이트가 구성되어 [있는지 확인](/sharepoint/guide-to-sharepoint-modern-experience)</span><span class="sxs-lookup"><span data-stu-id="bb019-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="bb019-135">Office 365 보호를 위한 Defender는 최신 환경 또는 클래식 보기가 사용되는지 여부에 따라 적용됩니다. 그러나 파일이 차단된 시각적 표시기는 최신 환경에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb019-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="bb019-136">SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한 첨부 파일은 EOP(Exchange Online Protection)의 스팸 방지 및 맬웨어 방지 보호를 포함하는 조직의 전반적인 위협 방지 전략과 Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb019-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="bb019-137">자세한 내용은 [에서 위협으로부터 보호를 Office 365.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="bb019-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
