---
title: 'Microsoft 365 클라이언트 앱 지원: 다단계 인증'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft 365에 대해 다단계 인증을 지원하는 플랫폼, 클라이언트 및 PowerShell 모듈에 대해 자세히 알아보고 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdec611fc595cdc15abb0fc1fb7a998f7a615ff7
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097483"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365 클라이언트 앱 지원: 다단계 인증

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

로그인에 대한 추가 보안 수준을 제공하기 위해 클라이언트가 MFA(Multi-Factor Authentication)를 사용하도록 구성할 수 있습니다. 이 인증에서는 다음을 기반으로 사용자 암호와 추가 사용자 확인 방법을 모두 사용합니다.

- 스마트폰과 같이 쉽게 복제되지 않는 소유의 항목입니다.
- 지문, 얼굴 또는 기타 생체 인식 특성과 같이 사용자가 고유하고 세밀하게 가지고 있는 것

다단계 [인증에 대해 자세히 알아보습니다.](/azure/active-directory/authentication/multi-factor-authentication)

## <a name="supported-clients--platforms"></a>지원되는 & 플랫폼

다음 클라이언트 및 플랫폼의 최신 버전은 다단계 인증을 지원합니다. Microsoft 365의 플랫폼 지원에 대한 자세한 내용은 [Microsoft 365의 시스템](/microsoft-365/microsoft-365-and-office-resources)요구 사항을 참조하세요.
<br>
<br>

| 클라이언트 | Android | iOS | Mac| Windows 10 <br> 최신 앱| Windows 10 <br> 데스크톱 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Access | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Azure Admin | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
| 회사 포털 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 |
| Cortana | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Delve | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Edge | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Excel | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Exchange Online 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| 양식 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
| Office 365 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |  |
| Kaizala | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Office Lens| ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Office 모바일 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Office 포털 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| OneDrive | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| OneNote | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Outlook | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Planner | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Power Apps | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Power Automate | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Power BI | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| PowerPoint | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Project | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Publisher | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| 비즈니스용 Skype | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원](../media/check-mark.png) |
| 비즈니스용 Skype 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| SharePoint를 입력하세요. | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| SharePoint Online 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| 스티커 메모 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Stream | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Sway | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Teams | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원](../media/check-mark.png) |
| To Do | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 |
| Visio | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Whiteboard | 계획 | ![지원됨](../media/check-mark.png) | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Word | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| 작업 공간 분석 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
| Yammer | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>지원되는 PowerShell 모듈

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint 온라인 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)