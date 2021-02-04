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
description: 이 문서에서는 인증서 기반 인증에 대한 Microsoft 365 클라이언트 앱 지원에 대한 세부 정보를 제공합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7ab5e4a2575796e37a115b36a4f78add20414ef
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097261"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 클라이언트 앱 지원: 인증서 기반 인증

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

최신 인증은 인증 및 권한 부여 방법의 조합을 위한 우연한 용어입니다. 여기에는 다음이 포함됩니다.

- **인증 방법:** 다단계 인증; 클라이언트 인증서 기반 인증.
- **권한 부여 방법:** Microsoft의 OAuth(Open Authorization) 구현

ADAL(Active Directory 인증 라이브러리) 또는 MSAL(Microsoft 인증 라이브러리)과 같은 인증 라이브러리를 사용하여 최신 인증을 사용할 수 있습니다. 최신 인증은 클라이언트가 Microsoft 365 리소스에 대한 액세스 권한을 인증하고 권한을 부여하는 데 사용하는 인증입니다. 최신 인증은 OAuth를 활용하고 클라이언트가 사용자 자격 증명에 액세스하지 않고도 Microsoft 365 서비스에 액세스할 수 있는 안전한 메커니즘을 제공합니다. 로그인 시 사용자는 Azure Active Directory에 직접 인증하고 그에 대한 대가로 액세스/새로 고침 토큰 쌍을 수신합니다. 액세스 토큰은 클라이언트에게 Microsoft 365 테넌트의 적절한 리소스에 대한 액세스 권한을 부여합니다. 새로 고침 토큰은 현재 액세스 토큰이 만료될 때 새 액세스 또는 새로 고침 토큰 쌍을 얻는 데 사용됩니다.

최신 인증은 인증서 기반 인증과 같은 다양한 인증 메커니즘을 지원합니다. Windows, Android 또는 iOS 장치의 클라이언트는 CBA(인증서 기반 인증)를 사용하여 장치의 클라이언트 인증서를 사용하여 Azure Active Directory에 인증할 수 있습니다. 인증서는 일반적인 사용자 이름/암호 대신 Azure Active Directory에서 액세스/새로 고침 토큰 쌍을 얻는 데 사용됩니다.

인증서 기반 인증에 [대해 자세히 알아보습니다.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>지원되는 & 플랫폼

다음 클라이언트 및 플랫폼의 최신 버전은 클라이언트 내에서 Azure Active Directory 계정에 로그인할 때(예: 앱에 계정을 추가할 때) 인증서 기반 인증을 지원합니다. Microsoft 365의 플랫폼 지원에 대한 자세한 내용은 [Microsoft 365의 시스템](/microsoft-365/microsoft-365-and-office-resources)요구 사항을 참조하세요.
<br>
<br>

| 클라이언트 | Android | iOS | Mac| Windows 10 <br> 최신 앱| Windows 10 <br> 데스크톱 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Access | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Azure Admin | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
| 회사 포털 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 |
| Cortana | 계획 | 계획 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Delve | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Edge<sup>1</sup> | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Excel | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| Exchange Online 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| 양식 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
| Office 365 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |  |
| Kaizala | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Office Lens| ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Office 모바일 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Office 포털 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| OneDrive | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 계획 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
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
| SharePoint Online 관리자 | 계획 | 계획 | 해당 없음 | 해당 없음 | 해당 없음 |
| 스티커 메모 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Stream | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| Sway | 해당 없음 | 해당 없음 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Teams | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 계획 |
| To Do | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 |
| Visio | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Whiteboard | 계획 | 계획 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Word | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) |
| 작업 공간 분석 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
| Yammer | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 계획 | 해당 없음 | 계획 |

>[!NOTE]
><sup>iOS</sup> 및 Android용 1 Edge는 계정 흐름 추가 중에 인증서 기반 인증을 지원합니다. iOS 및 Android용 에지에서는 일반적으로 인트라넷 사이트인 웹 사이트에 대해 인증을 수행할 때 인증서 기반 인증을 지원하지 않습니다. <br><br>  이 시나리오에서는 사용자가 웹 사이트(일반적으로 인트라넷)로 이동하여 사용자가 인증서를 통해 인증해야 하는 웹 사이트로 이동합니다. 이 경우 최신 인증이 사용되지는 않습니다. Microsoft 인증 라이브러리를 활용하지는 않습니다. iOS의 제한 때문에 iOS에서는 타사 앱이 인증서가 저장된 시스템 키체인에 액세스할 수 없습니다(Apple 앱과 [Safari webview](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 컨트롤러만 시스템 키체인에 액세스할 수 있습니다). <br><br> Edge는 웹 사이트 렌더링을 위해 [WebKit](https://developer.apple.com/documentation/webkit) 프레임워크를 사용하게 때문에 Edge는 시스템 키체인에 액세스하여 사용자에게 인증서 선택을 제공하지 못합니다. 안타깝게도 Apple의 아키텍처 때문에 디자인되었습니다.

## <a name="supported-powershell-modules"></a>지원되는 PowerShell 모듈

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint 온라인 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

