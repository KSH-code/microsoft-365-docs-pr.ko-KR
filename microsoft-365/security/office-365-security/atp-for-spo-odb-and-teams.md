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
description: SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams의 파일에 대한 Microsoft Defender for Office 365에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9b69d2b6f075539f411da971a314c127843b945a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917573"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6559b-103">SharePoint, OneDrive 및 Microsoft Teams를 위한 안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="6559b-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6559b-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="6559b-104">**Applies to**</span></span>
- [<span data-ttu-id="6559b-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="6559b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6559b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6559b-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="6559b-107">Office [365용 Microsoft Defender의](office-365-atp.md) SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한 첨부 파일은 [Microsoft 365의](virus-detection-in-spo.md)일반적인 바이러스 감지 엔진에 의해 업로드 시 이미 검사된 파일에 대한 추가 보호 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="6559b-108">SharePoint, OneDrive 및 Microsoft Teams의 안전한 첨부 파일은 팀 사이트 및 문서 라이브러리에서 악성으로 식별된 기존 파일을 검색하고 차단하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="6559b-109">SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한 첨부 파일은 기본적으로 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="6559b-110">켜기 위해 [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)및 Microsoft Teams에 대한 안전한 첨부 파일 켜기 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="6559b-111">SharePoint, OneDrive 및 Microsoft Teams의 안전한 첨부 파일 작동 방식</span><span class="sxs-lookup"><span data-stu-id="6559b-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="6559b-112">SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한 첨부 파일을 사용하도록 설정하고 파일을 악성으로 식별하면 파일이 파일 저장소와 직접 통합되어 잠겨집니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="6559b-113">다음 이미지는 라이브러리에서 검색된 악성 파일의 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-113">The following image shows an example of a malicious file detected in a library.</span></span>

![악성 파일로 탐지된 한 개의 파일을 포함한 비즈니스용 OneDrive에 있는 파일](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="6559b-115">차단된 파일은 문서 라이브러리 및 웹, 모바일 또는 데스크톱 응용 프로그램에 계속 나열되어도 파일을 열거나 복사하거나 이동하거나 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="6559b-116">그러나 차단된 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="6559b-117">다음은 차단된 파일이 모바일 장치에서 어떻게 보이는지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![OneDrive 모바일 앱의 비즈니스용 OneDrive에서 차단된 파일 삭제](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="6559b-119">기본적으로 사용자들은 차단된 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="6559b-120">다음은 차단된 파일을 다운로드할 때의 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![비즈니스용 OneDrive에서 차단된 파일 다운로드](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="6559b-122">SharePoint Online 관리자는 사용자가 악성 파일을 다운로드하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="6559b-123">자세한 내용은 [SharePoint Online PowerShell을 사용하여](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)사용자가 악성 파일을 다운로드하지 못하게 방지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6559b-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="6559b-124">파일이 악의적인 것으로 감지된 사용자 경험에 대한 자세한 내용은 [SharePoint Online, OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)또는 Microsoft Teams에서 악성 파일이 발견될 때 할 일 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6559b-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6559b-125">SharePoint, OneDrive 및 Microsoft Teams의 안전한 첨부 파일에서 검색된 악성 파일에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="6559b-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="6559b-126">Office 365용 Microsoft Defender에서 악성으로 식별된 파일은 [Office 365용 Microsoft Defender](view-reports-for-atp.md) 및 탐색기(및 실시간 검색)에 대한 보고서에 [나타납니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="6559b-126">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="6559b-127">2018년 5월을 현재, Office 365용 Microsoft Defender에 의해 파일이 악성으로 식별되면 파일을 검지에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-127">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="6559b-128">자세한 내용은 [Use the Security & Compliance Center to manage quarantined files를 참조하세요.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)</span><span class="sxs-lookup"><span data-stu-id="6559b-128">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="6559b-129">다음의 사항을 염두에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-129">Keep these points in mind</span></span>

- <span data-ttu-id="6559b-130">Office 365용 Defender는 SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft Teams의 모든 단일 파일을 검색하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="6559b-131">이것은 정상적인 현상입니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-131">This is by design.</span></span> <span data-ttu-id="6559b-132">파일이 비동기적으로 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="6559b-133">이 프로세스에서는 공유 및 게스트 활동 이벤트를 스마트 추적 및 위협 신호와 함께 사용하여 악성 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="6559b-134">SharePoint 사이트가 최신 환경을 사용하도록 구성되어 [있는지 확인](/sharepoint/guide-to-sharepoint-modern-experience)</span><span class="sxs-lookup"><span data-stu-id="6559b-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="6559b-135">Office 365 보호용 Defender는 최신 환경 또는 클래식 보기 사용 여부에 따라 적용됩니다. 그러나 파일이 차단된 시각적 표시기는 최신 환경에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="6559b-136">SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한 첨부 파일은 EOP(Exchange Online Protection)의 스팸 방지 및 맬웨어 방지 보호와 Office 365용 Microsoft Defender의 안전한 링크 및 안전한 첨부 파일을 포함하는 조직의 전반적인 위협 방지 전략의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6559b-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6559b-137">자세한 내용은 [Office 365에서 위협으로부터 보호를 참조합니다.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="6559b-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>