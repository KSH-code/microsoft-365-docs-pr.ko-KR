---
title: 비즈니스용 Skype 및 Exchange에서 하이브리드 최신 인증 제거 또는 사용 안 함
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 하이브리드 최신 인증을 제거하거나 사용하지 않도록 설정하는 방법을 비즈니스용 Skype Exchange.
ms.openlocfilehash: efc84ead5ea8219e77391f2a8ebe51e5fa23da8c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202814"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>비즈니스용 Skype 및 Exchange에서 하이브리드 최신 인증 제거 또는 사용 안 함

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

HMA(하이브리드 최신 인증)를 사용하도록 설정하여 현재 환경에 부적소한 경우 HMA를 사용하지 않도록 설정할 수 있습니다. 이 문서에서는 방법을 설명합니다.
  
## <a name="who-is-this-article-for"></a>Who 문서가 있나요?

비즈니스용 Skype Online 또는 비즈니스용 Skype, Exchange Online 또는 On-premises에서 최신 인증을 사용하도록 설정하고 HMA를 사용하지 않도록 설정해야 하는 경우 이러한 단계가 도움이 됩니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online[](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)또는 on-premises에 있으며 혼합 토폴로지 HMA가 있으며 시작하기 전에 지원되는 토폴로지가 필요한 경우 최신 인증에서 지원되는 ' 비즈니스용 Skype 토폴로지' 문서를 참조하세요.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>하이브리드 최신 인증을 사용하지 않도록 설정하는 방법(Exchange)

1. **Exchange 실행:** Exchange 관리 셸을 열고 다음 명령을 실행합니다. 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [커넥트](/powershell/exchange/connect-to-exchange-online-powershell) PowerShell을 Exchange Online 수 있습니다. 다음 명령을 실행하여  *OAuth2ClientProfileEnabled*  플래그를 'false'으로 전환합니다.

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>하이브리드 최신 인증을 사용하지 않도록 설정하는 방법(비즈니스용 Skype)

1. **비즈니스용 Skype 관리** 셸에서 다음 명령을 비즈니스용 Skype 실행합니다.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **비즈니스용 Skype Online:** [커넥트 PowerShell을 비즈니스용 Skype 온라인을](manage-skype-for-business-online-with-microsoft-365-powershell.md) 사용할 수 있습니다. 최신 인증을 사용하지 않도록 설정하기 위해 다음 명령을 실행합니다.

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[최신 인증 개요로 다시 연결합니다.](hybrid-modern-auth-overview.md) 
