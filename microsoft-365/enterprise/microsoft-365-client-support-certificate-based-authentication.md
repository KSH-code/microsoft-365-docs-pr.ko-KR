---
title: 'Microsoft 365 클라이언트 앱 지원: 인증서 기반 인증'
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
description: 이 문서에서는 인증서 기반 인증에 대 한 Microsoft 365 클라이언트 앱 지원에 대 한 세부 정보를 확인 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 49ed1e329e83b73441c89de9a142bfb9dcac5395
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806697"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 클라이언트 앱 지원: 인증서 기반 인증

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

인증서 기반 인증을 사용 하면 Windows, Android 또는 iOS 장치에서 클라이언트 인증서를 사용 하 여 Azure Active Directory에 인증할 수 있습니다. 이 기능을 구성 하면 모바일 장치에서 특정 메일 및 Microsoft Office 응용 프로그램에 대 한 사용자 이름 및 암호 조합을 입력할 필요가 없습니다.

자세한 내용은 [인증서 기반 인증](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)을 확인 하세요.

## <a name="supported-clients--platforms"></a>지원 되는 클라이언트 & 플랫폼

다음 클라이언트 및 플랫폼의 최신 버전에서는 인증서 기반 인증을 지원 합니다. Microsoft 365의 플랫폼 지원에 대 한 자세한 내용은 [microsoft 365의 시스템 요구 사항을](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)참조 하세요.
<br>
<br>

| 클라이언트 | Android | iOS | Mac| Windows 10 <br> 최신 앱| Windows 10 <br> 데스크톱 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Access | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Azure 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
| 회사 포털 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 |
| Cortana | 하려고 | 하려고 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Delve | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| 면 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Excel | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Exchange Online 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Forms | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
| Office 365 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |  |
| Kaizala | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Office Lens| ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Office mobile | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Office 포털 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| OneDrive | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 하려고 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| OneNote | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Outlook | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Planner | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Power Apps | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| 전원 자동화 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Power BI | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| PowerPoint | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Project | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Publisher | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| 비즈니스용 Skype | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원](../media/check-mark.png) |
| 비즈니스용 Skype 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| SharePoint | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| SharePoint Online 관리자 | 하려고 | 하려고 | 해당 없음 | 해당 없음 | 해당 없음 |
| 스티커 메모 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Stream | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Sway | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Teams | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 하려고 |
| To Do | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 |
| Visio | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Whiteboard | 하려고 | 하려고 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Word | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| 작업 공간 분석 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
| Yammer | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 하려고 | 해당 없음 | 하려고 |

## <a name="supported-powershell-modules"></a>지원 되는 PowerShell 모듈

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint 온라인 PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

