---
title: SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀의 파일에 대 한 Office 365 Advanced Threat Protection에 대해 알아봅니다.
ms.openlocfilehash: e4a711d6554ffcb8e291d5b2154120d078995e94
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815412"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365 ATP의 개요

People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams. With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner. ATP helps detect and block files that are identified as malicious in team sites and document libraries.

## <a name="how-office-365-atp-operates"></a>Office 365 ATP 작동 방식

When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file. The following image shows an example of a malicious file detected in a library.

![악성 파일로 탐지된 한 개의 파일을 포함한 비즈니스용 OneDrive에 있는 파일](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared. People can, however, delete a blocked file. Here's an example of what that looks like on a user's mobile device:

![OneDrive 모바일 앱의 비즈니스용 OneDrive에서 차단된 파일 삭제](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Microsoft 365이 구성 된 방식에 따라 사용자에 게 차단 된 파일을 다운로드 하는 기능이 있거나 없을 수 있습니다. 차단 된 파일을 다운로드 하는 작업은 사용자의 모바일 장치에 표시 되는 것과 같습니다.

![비즈니스용 OneDrive에서 차단된 파일 다운로드](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

자세한 내용은 [SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365 ATP 실행](turn-on-atp-for-spo-odb-and-teams.md)을 참조하세요.

## <a name="keep-these-points-in-mind"></a>다음의 사항을 염두에 둡니다.

- ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams. This is by design. Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.

- Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view. ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.

- SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft 팀에서 악성으로 식별 되는 파일은 [Office 365 Advanced Threat Protection](view-reports-for-atp.md) 및 [Explorer (및 실시간 검색)](threat-explorer.md)에 대 한 보고서에 표시 됩니다.

- ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments. To learn more, see [Protect against threats in Office 365](protect-against-threats.md).

- A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious. This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>SharePoint 온라인, 비즈니스용 OneDrive 및 Microsoft Teams를 위한 ATP를 통한 검역

 2018년 5월 말부터 보안&amp; 준수 센터의 [검역](quarantine-email-messages.md) 기능이 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams를 위해 ATP로 확장됩니다.

SharePoint Online의 파일 (비즈니스용 OneDrive 또는 Microsoft 팀)이 악성으로 식별 되 고 파일을 열거나 공유 하지 못하게 하는 ATP 외에 격리 된 항목 목록에 해당 파일이 포함 됩니다. (보안 &amp; 준수 센터에서 **위협 관리** 검토 격리로 이동 하 여 \> **Review** \> **Quarantine** **파일**을 필터링 합니다.

조직의 Microsoft 365 비즈니스 보안 팀에 참여 하 고 [보안 및 &amp; 준수 센터에서 필요한 사용 권한을](permissions-in-the-security-and-compliance-center.md)부여 하는 경우 ATP에서 악의적으로 검색 된 파일을 격리에서 다운로드, 릴리스, 보고 및 삭제할 수 있습니다.

- **Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams. Users are then able to open, share, and download the file. And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.

- **Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared. The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).

- **파일을 다운로드** 시 파일을 다운로드하고 모든 가양성에 대해 분석할 수 있습니다.

## <a name="next-steps"></a>다음 단계

 - [SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365 ATP 실행](turn-on-atp-for-spo-odb-and-teams.md)

 - [SharePoint, OneDrive 또는 Microsoft Teams에서 감지한 악성 파일에 대한 정보 보기](malicious-files-detected-in-spo-odb-or-teams.md)

