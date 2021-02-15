---
title: 'Microsoft 365 클라이언트 앱 지원: 단일 Sign-On'
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
description: 이 문서에서는 Microsoft 365에 대한 Single Sign-On을 지원하는 플랫폼, 클라이언트 및 PowerShell 모듈에 대해 자세히 알아보고 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a685f04ed64a89cda026ff9380aac7c6c2b3ea4
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097201"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Microsoft 365 클라이언트 앱 지원: 단일 Sign-On

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

SSO(Single Sign-On)는 사용자가 Azure Active Directory의 응용 프로그램에 로그인할 때 보안과 편의성을 제공합니다. Single Sign-On을 사용하면 한 계정으로 한 번 로그인하여 도메인 가입 장치, SaaS(Software as a Service) 응용 프로그램 및 웹 응용 프로그램에 액세스할 수 있습니다.

Single [Sign-On에 대해 자세히 알아보시고.](/azure/active-directory/manage-apps/what-is-single-sign-on)

## <a name="supported-clients--platforms"></a>지원되는 & 플랫폼

다음 클라이언트 및 플랫폼의 최신 버전은 Single Sign-On을 지원합니다. Microsoft 365의 플랫폼 지원에 대한 자세한 내용은 [Microsoft 365의 시스템](/microsoft-365/microsoft-365-and-office-resources)요구 사항을 참조하세요.
<br>
<br>

| 클라이언트 | Android | iOS | Mac| Windows 10 <br> 최신 앱| Windows 10 <br> 데스크톱 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Access | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| 회사 포털 | 해당 없음 | ![지원](../media/check-mark.png) | 계획 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Cortana | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Delve | 계획 | ![지원됨](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Edge | ![지원](../media/check-mark.png) | 계획 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Excel | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Kaizala | ![지원](../media/check-mark.png) | 계획 | 해당 없음 | 해당 없음 | 해당 없음 |
| Office Lens| ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Office 모바일 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Office 포털 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| OneDrive | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 계획 | ![지원](../media/check-mark.png) | 계획 |
| OneNote | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 계획 |
| Outlook | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 계획 | ![지원](../media/check-mark.png) |
| Planner | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Power Apps | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 계획 | 해당 없음 |
| Power Automate | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Power BI | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원](../media/check-mark.png) | 계획 |
| PowerPoint | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Project | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| 게시자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| 비즈니스용 Skype | 계획 | 계획 | 해당 없음 | 해당 없음 | 해당 없음 |
| SharePoint | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| 스티커 메모 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Stream | 계획 | 계획 | 해당 없음 | 해당 없음 | 해당 없음 |
| Sway | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Teams | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 계획 | 해당 없음 | 계획 |
| To Do | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Visio | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Whiteboard | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Word | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Yammer | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 계획 |

## <a name="supported-powershell-modules"></a>지원되는 PowerShell 모듈

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint 온라인 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
