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
description: 이 문서에서는 사용자에 대해 다단계 인증을 지원하는 플랫폼, 클라이언트 및 PowerShell 모듈에 대해 Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8749c05e3f7ce5dacf7d3ed1eaa46a46a20482d5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215912"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365 클라이언트 앱 지원: 다단계 인증

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

로그인에 대한 추가 보안 수준을 제공하기 위해 클라이언트는 사용자 암호와 다음을 기반으로 하는 다른 사용자 확인 방법을 모두 사용하는 MFA(다단계 인증)를 사용하도록 구성할 수 있습니다.

- 스마트폰과 같이 쉽게 복제되지 않는 소유의 항목입니다.
- 지문, 얼굴 또는 기타 생체 인식 특성과 같이 사용자가 고유하고 품사적으로 가지고 있는 것

다단계 [인증에 대해 자세히 알아보시고 을(를) 자세히 알아보아야 합니다.](/azure/active-directory/authentication/multi-factor-authentication)

## <a name="supported-clients--platforms"></a>지원되는 & 플랫폼

다음 클라이언트 및 플랫폼의 최신 버전은 다단계 인증을 지원합니다. Microsoft 365 플랫폼 지원에 대한 자세한 내용은 에 대한 시스템 요구 [Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a>지원되는 PowerShell 모듈

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint 온라인 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
