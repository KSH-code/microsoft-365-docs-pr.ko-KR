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
description: SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀의 파일에 대 한 Office 365 Advanced Threat Protection에 대해 알아봅니다.
ms.openlocfilehash: 90e84f0a4393e5097fb59b93693862a21d6d9f2f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031451"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365 ATP의 개요

사용자들은 SharePoint, OneDrive 및 Microsoft teams를 활용하여 정기적으로 파일을 공유하고 협업을 합니다. [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP)를 통해 조직은 보다 안전한 방식으로 협업을 할 수 있습니다. ATP는 팀 사이트 및 문서 라이브러리에서 악성으로 식별되는 파일을 탐지하고 차단합니다.

## <a name="how-it-works"></a>작동 방법

SharePoint 온라인, 비즈니스용 OneDrive, Microsoft teams에서의 파일이 악성으로 확인되었을 시 ATP는 해당 파일을 잠그기 위해 파일의 저장소와 직접 통합합니다. 다음의 그림은 라이브러리에서 탐지된 악성 파일의 예를 보여 줍니다.

![악성 파일로 탐지된 한 개의 파일을 포함한 비즈니스용 OneDrive에 있는 파일](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

차단된 파일이 여전히 문서 라이브러리와 웹, 모바일 또는 데스크톱 응용 프로그램에 있을지라도 차단된 파일은 열기, 복사, 이동 혹은 공유할 수 없습니다. 하지만 사용자는 차단된 파일을 삭제할 수 있습니다. 사용자의 모바일 장치에서 보이는 예시는 다음과 같습니다:

![OneDrive 모바일 앱의 비즈니스용 OneDrive에서 차단된 파일 삭제](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Microsoft 365이 구성 된 방식에 따라 사용자에 게 차단 된 파일을 다운로드 하는 기능이 있거나 없을 수 있습니다. 차단 된 파일을 다운로드 하는 작업은 사용자의 모바일 장치에 표시 되는 것과 같습니다.

![비즈니스용 OneDrive에서 차단된 파일 다운로드](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

자세한 내용은 [SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365 ATP 실행](turn-on-atp-for-spo-odb-and-teams.md)을 참조하세요.

## <a name="keep-these-points-in-mind"></a>다음의 사항을 염두에 둡니다.

- ATP는 그 설계 상 SharePoint 온라인, 비즈니스용 OneDrive 혹은 Microsoft Teams의 모든 파일을 스캔하지 않습니다. 악성 파일을 식별하기 위해 파일들은 스마트 휴리스틱과 위협 신호와 함께 공유 및 게스트 활동 이벤트를 사용하는 프로세스를 통해 비동기적으로 스캔됩니다.

- SharePoint 사이트가 [모던 경험](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)을 사용하도록 구성되었는지 확인합니다. 파일이 악성으로 확인되고 차단되었을 때 사용자는 이러한 발생을 모던 경험을 통해 확인할 수 있지만 클래식 보기에서는 확인할 수 없습니다. ATP 보호 기능은 모던 환경 또는 클래식 보기의 사용 여부에관계없이 적용됩니다; 그러나 파일이 차단되었다는 시각적 표시는 모던 경험을 통해서만 제공됩니다.

- SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft 팀에서 악성으로 식별 되는 파일은 [Office 365 Advanced Threat Protection](view-reports-for-atp.md) 및 [Explorer (및 실시간 검색)](threat-explorer.md)에 대 한 보고서에 표시 됩니다.

- ATP는 조직의 전반적인 위협 보호 전략의 일부로서 스팸 방지 및 악성코드 방지 보호 수단 외에 안전한 링크 및 안전한 첨부 파일 기능을 포함합니다. 자세한 내용은 [Office 365의 위협으로부터 보호](protect-against-threats.md)를 참조합니다.

- SharePoint 온라인 관리자는 악성으로 탐지된 파일을 사용자들이 다운로드할 수 있도록 할지 여부를 결정할 수 있습니다. 이는  DisallowInfectedFileDownload 매개 변수를 사용하여 Set-SPOTenant PowerShell cmdlet을 실행하여 결정합니다 ([SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365 ATP 실행](turn-on-atp-for-spo-odb-and-teams.md)참조).

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>SharePoint 온라인, 비즈니스용 OneDrive 및 Microsoft Teams를 위한 ATP를 통한 검역

 2018년 5월 말부터 보안&amp; 준수 센터의 [검역](quarantine-email-messages.md) 기능이 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams를 위해 ATP로 확장됩니다.

SharePoint Online의 파일 (비즈니스용 OneDrive 또는 Microsoft 팀)이 악성으로 식별 되 고 파일을 열거나 공유 하지 못하게 하는 ATP 외에 격리 된 항목 목록에 해당 파일이 포함 됩니다. 보안 &amp; 및 준수 센터에서 **위협 관리** \> **검토** \> **격리** 로 이동 하 여 **파일**을 필터링 합니다.

조직의 Microsoft 365 비즈니스 보안 팀에 참여 하 고 [보안 &amp; 및 준수 센터에서 필요한 사용 권한을](permissions-in-the-security-and-compliance-center.md)부여 하는 경우 ATP에서 악의적으로 검색 된 파일을 격리에서 다운로드, 릴리스, 보고 및 삭제할 수 있습니다.

- 파일을 **출시 및 보고** 시 해당 팀 사이트 또는 SharePoint, OneDrive의 문서 라이브러리 또는 Microsoft Teams의 파일에 있는 ATP 블록이 제거됩니다. 이후 사용자는 해당 파일의 열기, 공유 및 다운로드를 할 수 있게 됩니다. **Microsoft에 보고서 보내기** 옵션을 선택 시 해당 파일은 Microsoft에 가양성으로 보고됩니다.

- **파일을 삭제** 시 파일을 검역소에서 제거하지만 파일은 여전히 열거나 공유할 수 없도록 차단됩니다. 파일은 또한 해당 문서 라이브러리 또는 팀 사이트 (SharePoint 온라인, 비즈니스용 OneDrive 또는 Microsoft Teams)에서 삭제되어야 합니다.

- **파일을 다운로드** 시 파일을 다운로드하고 모든 가양성에 대해 분석할 수 있습니다.

## <a name="next-steps"></a>다음 단계

 - [SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365 ATP 실행](turn-on-atp-for-spo-odb-and-teams.md)

 - [SharePoint, OneDrive 또는 Microsoft Teams에서 감지한 악성 파일에 대한 정보 보기](malicious-files-detected-in-spo-odb-or-teams.md)

