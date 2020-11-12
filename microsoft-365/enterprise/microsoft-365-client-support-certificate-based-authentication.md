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
ms.openlocfilehash: 2f2f5acb88e49cf7a81bd5e89c0c9c85feea6672
ms.sourcegitcommit: 86e878849a8bdd456cee6a3f49939d26223fb626
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48997806"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 클라이언트 앱 지원: 인증서 기반 인증

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

최신 인증은 인증 및 권한 부여 방법을 조합 하는 포괄적인 용어입니다. 여기에는 다음이 포함됩니다.

- 인증 방법: Multi-factor Authentication; 클라이언트 인증서 기반 인증

- 권한 부여 방법: Microsoft의 개방형 권한 부여 (OAuth) 구현

최신 인증은 ADAL 또는 MSAL과 같은 인증 라이브러리를 사용 하 여 사용 하도록 설정 됩니다. 최신 인증은 클라이언트가 Microsoft 365 리소스에 대 한 액세스를 인증 하 고 권한을 부여 하는 데 사용 됩니다. 최신 인증은 OAuth를 활용 하며 클라이언트에서 사용자 자격 증명에 액세스할 필요 없이 Microsoft 365 서비스에 액세스 하는 데 사용할 수 있는 보안 메커니즘을 제공 합니다. 로그인 할 때 사용자는 Azure Active Directory를 사용 하 여 직접 인증 하 고 반환 된 액세스/새로 고침 토큰 쌍을 받습니다. 액세스 토큰은 클라이언트에 게 Microsoft 365 테 넌 트의 해당 리소스에 대 한 액세스 권한을 부여 합니다. 새로 고침 토큰은 현재 액세스 토큰이 만료 되는 경우 새 액세스 또는 새로 고침 토큰 쌍을 가져오는 데 사용 됩니다.

최신 인증은 인증서 기반 인증과 같은 서로 다른 인증 메커니즘을 지원 합니다. Windows, Android 또는 iOS 장치의 클라이언트는 CBA (인증서 기반 인증)를 사용 하 여 장치에서 클라이언트 인증서를 사용 하 여 Azure Active Directory에 인증할 수 있습니다. 인증서는 일반적인 사용자 이름/암호 대신 Azure Active Directory에서 액세스/새로 고침 토큰 쌍을 가져오는 데 사용 됩니다.

자세한 내용은 [인증서 기반 인증](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)을 확인 하세요.

## <a name="supported-clients--platforms"></a>지원 되는 클라이언트 & 플랫폼

다음 클라이언트 및 플랫폼의 최신 버전에서는 클라이언트 내의 Azure Active Directory 계정에 로그인 할 때 인증서 기반 인증을 지원 합니다 (예: 앱에 계정을 추가 하는 경우). Microsoft 365의 플랫폼 지원에 대 한 자세한 내용은 [microsoft 365의 시스템 요구 사항을](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)참조 하세요.
<br>
<br>

| 클라이언트 | Android | iOS | Mac| Windows 10 <br> 최신 앱| Windows 10 <br> 데스크톱 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| 접근 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
| Azure 관리자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
| 회사 포털 | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 |
| Cortana | 하려고 | 하려고 | 해당 없음 | ![지원됨](../media/check-mark.png) | 해당 없음 |
| Delve | ![지원](../media/check-mark.png) | ![지원](../media/check-mark.png) | 해당 없음 | 해당 없음 | 해당 없음 |
| 면 | ![지원](../media/check-mark.png)* | ![지원](../media/check-mark.png)* | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
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
| 게시자 | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 | ![지원](../media/check-mark.png) |
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

> [!IMPORTANT]
> Edge for iOS 및 Android는 계정 추가 흐름 중에 인증서 기반 인증을 지원 합니다. Edge for iOS 및 Android에서는 웹 사이트 (일반적으로 인트라넷 사이트)에 대해 인증을 수행 하는 경우 인증서 기반 인증을 지원 하지 않습니다. 이 시나리오에서는 사용자가 인증서를 통해 인증을 받아야 하는 웹 사이트 (대개 인트라넷)를 탐색 합니다. 이는 최신 인증을 전혀 포함 하지 않으며 Microsoft 인증 라이브러리를 이용 하지 않습니다. 이는 iOS의 한계로 인해 타사 앱이 인증서가 저장 된 시스템 키 집합에 액세스 하지 못하도록 차단 하는 경우 (Apple 앱과 [Safari 웹 보기 컨트롤러](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 에서만 시스템 키 집합에 액세스할 수 있음).

 

에 지 webkit에 따라 Edge에서 시스템 키 집합에 액세스 하 여 인증서를 사용자에 게 제공할 수 없습니다. 아쉽게도 이러한 기능은 Apple의 아키텍처로 인해 의도적으로 설계 되었습니다.

## <a name="supported-powershell-modules"></a>지원 되는 PowerShell 모듈

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint 온라인 PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

