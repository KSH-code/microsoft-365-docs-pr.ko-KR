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
ms.openlocfilehash: fe601cdb6ea130e904f8b7526dc265cd19e2ab77
ms.sourcegitcommit: 0ed93816e2c1e6620e68bd1c0f00390062911606
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59483846"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive 및 Microsoft Teams를 위한 안전한 첨부 파일

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

금고 [microsoft Defender](whats-new-in-defender-for-office-365.md) for SharePoint, OneDrive 및 Microsoft Teams 첨부 파일은 Office 365 의 일반적인 바이러스 검색 엔진에 의해 비동기적으로 검사된 파일에 대한 추가 보호 [계층을 Microsoft 365.](virus-detection-in-spo.md) 금고 SharePoint, OneDrive 및 Microsoft Teams 첨부 파일은 팀 사이트 및 문서 라이브러리에서 악성으로 식별된 기존 파일을 검색하고 차단하는 데 도움이 됩니다.

금고 SharePoint, OneDrive 및 Microsoft Teams 첨부 파일은 기본적으로 사용하도록 설정되지 않습니다. 이 기능을 켜면 에 대한 금고 첨부 파일 [SharePoint,](turn-on-mdo-for-spo-odb-and-teams.md)OneDrive 및 Microsoft Teams.

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>금고, SharePoint 및 OneDrive 첨부 Microsoft Teams 방법

금고, SharePoint, OneDrive 및 Microsoft Teams 첨부 파일을 사용하도록 설정하고 파일을 악성으로 식별하면 파일이 파일 저장소와 직접 통합되어 잠겨 있습니다. 다음 그림은 라이브러리에서 검색되는 악성 파일의 예입니다.

![악성으로 비즈니스용 OneDrive 파일이 있는 파일.](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

차단된 파일은 문서 라이브러리 및 웹, 모바일 또는 데스크톱 응용 프로그램에 계속 나열되어도 파일을 열거나 복사하거나 이동하거나 공유할 수 없습니다. 그러나 차단된 파일을 삭제할 수 있습니다.

다음은 차단된 파일이 모바일 장치에서 어떻게 보이는지의 예입니다.

![모바일 앱에서 차단된 비즈니스용 OneDrive 삭제 OneDrive 삭제합니다.](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

기본적으로 사용자들은 차단된 파일을 다운로드할 수 있습니다. 다음은 차단된 파일을 다운로드할 때의 모양입니다.

![차단된 파일을 비즈니스용 OneDrive.](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint 온라인 관리자는 사용자가 악성 파일을 다운로드하지 못하게 할 수 있습니다. 자세한 내용은 [SharePoint Online PowerShell을](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)사용하여 사용자가 악성 파일을 다운로드하지 못하게 방지를 참조하세요.

파일이 악의적인 것으로 감지된 사용자 경험에 대한 자세한 내용은 SharePoint [Online,](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)OneDrive 또는 Microsoft Teams.

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>검색된 파일, 파일 및 금고 첨부 파일에서 검색된 SharePoint OneDrive 정보를 Microsoft Teams

금고, OneDrive 및 SharePoint 및 Microsoft Teams에 대한 첨부 파일로 악성으로 식별된 파일은 Office 365 및 탐색기(및 실시간 [검색)에 대한 Microsoft Defender에](view-reports-for-mdo.md) 대한 보고서에 [나타납니다.](threat-explorer.md)

금고, SharePoint, OneDrive 및 Microsoft Teams 파일에서 파일을 악성으로 식별한 경우 해당 파일은 관리자만이 Microsoft Teams 사용할 수 있습니다. 자세한 내용은 [Manage quarantined files in Defender for Office 365.](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)

## <a name="keep-these-points-in-mind"></a>다음의 사항을 염두에 둡니다.

- Office 365 Defender는 SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft Teams 검색하지 Microsoft Teams. 이것은 정상적인 현상입니다. 파일이 비동기적으로 검색됩니다. 이 프로세스에서는 공유 및 게스트 활동 이벤트를 스마트 추적 및 위협 신호와 함께 사용하여 악성 파일을 식별합니다.

- 최신 환경을 SharePoint 사이트가 구성되어 [있는지 확인](/sharepoint/guide-to-sharepoint-modern-experience) Office 365 보호를 위한 Defender는 최신 환경 또는 클래식 보기가 사용되는지 여부에 따라 적용됩니다. 그러나 파일이 차단된 시각적 표시기는 최신 환경에서만 사용할 수 있습니다.

- 금고 SharePoint, OneDrive 및 Microsoft Teams 첨부 파일은 EOP(Exchange Online Protection)의 스팸 방지 및 맬웨어 방지 보호뿐만 아니라 금고 링크 및 맬웨어 방지를 포함하는 조직의 전반적인 위협 방지 전략에 금고 Microsoft Defender for Office 365. 자세한 내용은 [에서 위협으로부터 보호를 Office 365.](protect-against-threats.md)
