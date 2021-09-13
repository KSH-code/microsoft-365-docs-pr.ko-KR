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
description: 이 문서에서는 인증서 기반 인증에 Microsoft 365 클라이언트 앱 지원에 대한 세부 정보를 제공합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bef1a684ba1ebe2eaba90677cd726cc190e342db
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215962"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 클라이언트 앱 지원: 인증서 기반 인증

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

최신 인증은 인증 및 권한 부여 방법의 조합을 위한 우산 용어입니다. 이러한 메서드는 다음과 같습니다.

- **인증 방법:** 다단계 인증 클라이언트 인증서 기반 인증.
- **권한 부여 방법:** Microsoft의 OAuth(Open Authorization) 구현

ADAL(Active Directory 인증 라이브러리) 또는 MSAL(Microsoft 인증 라이브러리)과 같은 인증 라이브러리를 사용하여 최신 인증을 사용할 수 있습니다. 최신 인증은 클라이언트가 리소스에 대한 액세스 권한을 인증하고 권한을 부여하는 Microsoft 365 것입니다. 최신 인증은 OAuth를 사용하며 클라이언트가 사용자 자격 증명에 액세스하지 않고도 Microsoft 365 서비스에 액세스할 수 있는 보안 메커니즘을 제공합니다. 로그인 시 사용자는 로그인 시 직접 인증을 Azure Active Directory 액세스/새로 고침 토큰 쌍을 받게 됩니다. 액세스 토큰은 클라이언트에게 테넌트의 적절한 리소스에 대한 Microsoft 365 부여합니다. 새로 고침 토큰은 현재 액세스 토큰이 만료될 때 새 액세스 또는 새로 고침 토큰 쌍을 얻는 데 사용됩니다.

최신 인증은 인증서 기반 인증과 같은 다양한 인증 메커니즘을 지원합니다. Windows, Android 또는 iOS 장치의 클라이언트는 CBA(인증서 기반 인증)를 사용하여 장치에서 클라이언트 Azure Active Directory 인증할 수 있습니다. 일반적인 사용자 이름/암호 대신 인증서를 사용하여 사용자 이름에서 액세스/새로 고침 토큰 쌍을 Azure Active Directory.

인증서 기반 [인증에 대해 자세히 알아보시다.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>지원되는 & 플랫폼

다음 클라이언트 및 플랫폼의 최신 버전은 클라이언트 내의 Azure Active Directory 계정에 로그인할 때(예: 앱에 계정을 추가할 때) 인증서 기반 인증을 지원합니다. Microsoft 365 플랫폼 지원에 대한 자세한 내용은 에 대한 시스템 요구 [Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

> [!NOTE]
> iOS 및 Android용 Edge는 계정 추가 흐름 중에 인증서 기반 인증을 지원합니다. iOS 및 Android용 에지에서는 일반적으로 인트라넷 사이트인 웹 사이트에 대해 인증을 수행할 때 인증서 기반 인증을 지원하지 않습니다. <br><br>  이 시나리오에서는 사용자가 웹 사이트(일반적으로 인트라넷)로 이동하여 사용자가 인증서를 통해 인증해야 하는 웹 사이트로 이동합니다. 이는 최신 인증과 관련이 없는 것이 아니며 Microsoft 인증 라이브러리를 활용하지 않습니다. 이는 iOS의 제한 때문에: iOS는 타사 앱이 인증서가 저장된 시스템 키채인에 액세스하지 못하게 합니다(Apple 앱과 [Safari webview 컨트롤러만](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 시스템 키체인에 액세스할 수 있습니다). <br><br> Edge는 웹 사이트 렌더링을 위해 [WebKit](https://developer.apple.com/documentation/webkit) 프레임워크를 사용하게 됐기 때문에 Edge는 시스템 키채인에 액세스하여 사용자에게 인증서를 선택할 수 없습니다. 안타깝게도 Apple의 아키텍처로 인해 디자인되었습니다.

## <a name="supported-powershell-modules"></a>지원되는 PowerShell 모듈

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint 온라인 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
