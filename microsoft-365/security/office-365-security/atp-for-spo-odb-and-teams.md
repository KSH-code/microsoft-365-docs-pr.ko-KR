---
title: SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
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
description: SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀의 파일에 대 한 Office 365 Advanced Threat Protection에 대해 알아봅니다.
ms.openlocfilehash: e536809c74abbe87e1250acda3f3922180cfae97
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446266"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Office 365에서 SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP [atp (Advanced Threat Protection)](office-365-atp.md) 는 [microsoft 365의 일반적인 바이러스 검색 엔진](virus-detection-in-spo.md)을 통해 업로드 시간에 이미 검색 된 파일에 대 한 추가 보호 계층을 제공 합니다. SharePoint, OneDrive 및 Microsoft 팀의 ATP는 팀 사이트 및 문서 라이브러리에서 악의적으로 식별 되는 기존 파일을 검색 하 고 차단 하는 데 도움이 됩니다.

SharePoint, OneDrive 및 Microsoft 팀의 ATP는 기본적으로 사용 하도록 설정 되어 있지 않습니다. 이 기능을 설정 하려면 [SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP 끄기를](turn-on-atp-for-spo-odb-and-teams.md)참조 하세요.

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint, OneDrive 및 Microsoft 팀의 ATP가 작동 하는 방식

SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP를 사용 하도록 설정 하 고 해당 파일을 악성으로 식별 하면 파일이 파일 저장소와 직접 통합 된 기능을 사용 하 여 잠깁니다. 다음 그림에서는 라이브러리에서 검색 된 악성 파일의 예를 보여 줍니다.

![악성 파일로 탐지된 한 개의 파일을 포함한 비즈니스용 OneDrive에 있는 파일](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

차단 된 파일은 여전히 문서 라이브러리 및 웹, 모바일 또는 데스크톱 응용 프로그램에 나열 되지만 사용자는 파일을 열거나 복사 하거나 이동 하거나 공유할 수 없습니다. 하지만 차단 된 파일은 삭제할 수 있습니다.

다음은 차단 된 파일이 모바일 장치에 표시 되는 결과의 예입니다.

![OneDrive 모바일 앱의 비즈니스용 OneDrive에서 차단된 파일 삭제](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

기본적으로 사용자는 차단 된 파일을 다운로드할 수 있습니다. 차단 된 파일을 다운로드 하는 방법은 모바일 장치에서 다음과 같습니다.

![비즈니스용 OneDrive에서 차단된 파일 다운로드](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online 관리자는 사용자가 악성 파일을 다운로드 하지 못하도록 방지할 수 있습니다. 자세한 내용은 [SharePoint Online PowerShell을 사용 하 여 사용자가 악성 파일을 다운로드 하지 못하도록](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)합니다 .를 참조 하세요.

파일이 악성으로 검색 되었을 때의 사용자 환경에 대 한 자세한 내용은 [SharePoint Online, OneDrive 또는 Microsoft 팀에서 악의적인 파일을 찾은 경우 수행할](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)작업을 참조 하십시오.

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive 및 Microsoft 팀에서 ATP가 검색 한 악성 파일에 대 한 정보 보기

ATP에서 악의적으로 식별 된 파일은 [Office 365 Advanced Threat Protection](view-reports-for-atp.md) 과 [Explorer (및 실시간 검색)](threat-explorer.md)에 대 한 보고서에 표시 됩니다.

파일을 ATP에서 악의적으로 식별 한 경우에는이 파일을 격리 에서도 사용할 수 2018. 자세한 내용은 [Security & 준수 센터를 사용 하 여 격리 된 파일 관리](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)를 참조 하세요.

## <a name="keep-these-points-in-mind"></a>다음의 사항을 염두에 둡니다.

- ATP는 SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft 팀에서 모든 단일 파일을 검색 하지 않습니다. 이것은 정상적인 현상입니다. 파일은 비동기적으로 검색 됩니다. 이 프로세스에서는 공유 및 게스트 활동 이벤트와 스마트 추론 및 위협 신호를 함께 사용 하 여 악성 파일을 식별 합니다.

- SharePoint 사이트가 [최신 환경을](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)사용 하도록 구성 되었는지 확인 합니다. ATP 보호는 최신 환경이 나 클래식 보기가 사용 되는지 여부에 관계 없이 적용 됩니다. 그러나 파일이 차단 된 시각적 표시기는 최신 환경 에서만 사용할 수 있습니다.

- SharePoint, OneDrive 및 Microsoft 팀은 Exchange Online Protection (EOP)의 스팸 방지 및 맬웨어 방지 보호 기능을 비롯 하 여 Office 365 ATP의 안전한 링크 및 안전한 첨부 파일을 포함 하는 조직의 전반적인 위협 보호 전략에 속합니다. 자세한 내용은 [Office 365에서 위협 으로부터 보호](protect-against-threats.md)를 참조 하세요.
