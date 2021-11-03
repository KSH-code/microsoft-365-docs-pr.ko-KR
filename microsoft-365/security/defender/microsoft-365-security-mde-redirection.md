---
title: 끝점용 Microsoft Defender에서 계정으로 Microsoft 365 Defender
description: 계정 및 세션을 끝점용 Defender에서 계정으로 리디렉션하는 Microsoft 365 Defender.
keywords: Microsoft 365 Defender, 보안 센터 리디렉션 Microsoft 365 Defender 시작
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 30a0e3b61e004ffe6c78e3b7a2d15b7b190253d9
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724658"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>끝점용 Microsoft Defender에서 계정으로 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender
- 엔드포인트용 Defender

SIEM 및 XDR(Extended detection and response)을 통해 위협 방지에 대한 Microsoft의 도메인 간 접근 방식에 맞춰 Microsoft Defender Advanced Threat Protection을 끝점용 Microsoft Defender로 변경하고 통합된 단일 포털인 Microsoft 365 Defender.

이 가이드에서는 이전 Microsoft Defender for Microsoft 365 Defender Endpoint 포털(securitycenter.windows.com 또는 securitycenter.microsoft.com)에서 Microsoft 365 Defender 포털(security.microsoft.com)으로 자동 리디렉션을 사용하도록 설정하여 계정을 security.microsoft.com.

> [!NOTE]
> Microsoft Defender for Endpoint Microsoft 365 Defender Microsoft Defender 보안 센터에서 액세스 권한을 부여하는 방법과 동일한 방식으로 관리되는 보안 서비스 [공급자(MSSP)에](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 대한 액세스 권한을 [부여할 수 있습니다.](./mssp-access.md)

## <a name="what-to-expect"></a>예상할 일

자동 리디렉션을 사용하도록 설정하면 securitycenter.windows.com 또는 securitycenter.microsoft.com 에서 이전 Microsoft Defender for Endpoint 포털에 액세스하는 계정은 Microsoft 365 Defender 포털로 security.microsoft.com.

변경된 내용을 자세히 알아보시고, Microsoft [Defender for Endpoint in Microsoft 365 Defender.](microsoft-365-security-center-mde.md)

여기에는 전자 메일 알림의 링크, SIEM API 호출에서 반환된 링크 등 이전 securitycenter.windows.com 포털을 향한 링크를 포함하여 브라우저를 통해 이전 포털에 직접 액세스하기 위한 리디렉션이 포함됩니다.  

 전자 메일 알림 또는 SIEM API의 외부 링크에는 현재 두 포털에 대한 링크가 포함되어 있습니다. 리디렉션을 사용하도록 설정하면 이전 링크가 Microsoft 365 Defender 때까지 두 링크가 모두 연결되지 않습니다. 새 링크를 채택하는 것이 Microsoft 365 Defender.

링크 및 라우팅에 대한 자세한 내용은 아래 표를 참조하세요.
## <a name="siem-api-routing"></a>SIEM API 라우팅

| 속성 | 리디렉션이 해제된 경우 대상 | 리디렉션이 ON인 경우 대상 |
|---------|---------|---------|
| LinkToWDATP | 알림 페이지의 securitycenter.windows.com | 알림 페이지의 security.microsoft.com |
| IncidentLinkToWDATP | 인시던트 securitycenter.windows.com | 인시던트 security.microsoft.com |
| LinkToMTP | 알림 페이지의 security.microsoft.com | 알림 페이지의 security.microsoft.com |
| IncidentLinkToMTP | 인시던트 security.microsoft.com | 인시던트 security.microsoft.com |

## <a name="email-alert-notifications"></a>전자 메일 알림

| 속성 | 리디렉션이 해제된 경우 대상** | 리디렉션이 ON인 경우 대상 |
|---------|---------|---------|
| 경고 페이지 | 알림 페이지의 securitycenter.windows.com | 알림 페이지의 security.microsoft.com |
| 인시던트 페이지 |인시던트 securitycenter.windows.com | 인시던트 security.microsoft.com |
| 보안 센터 포털의 경고 페이지 | 알림 페이지의 security.microsoft.com | 알림 페이지의 security.microsoft.com |
| 보안 센터 포털의 인시던트 페이지 | 인시던트 security.microsoft.com | 인시던트 security.microsoft.com |

## <a name="when-does-this-take-effect"></a>이 방식은 언제 적용하나요?

사용하도록 설정하면 일부 계정에 대해 이 업데이트가 거의 즉시 적용될 수 있습니다. 그러나 리디렉션이 조직의 모든 계정에 전파하는 데 더 오래 걸릴 수 있습니다. 이 설정이 적용된 동안 활성 세션의 계정은 해당 세션에서출되지 않습니다. 현재 세션을 종료하고 다시 로그인한 Microsoft 365 Defender 계정으로만 라우팅됩니다.  

### <a name="set-up-portal-redirection"></a>포털 리디렉션 설정

다음을 위해 라우팅 계정을 Microsoft 365 Defender.

1. 전역 관리자 또는 보안 관리자 권한이 있는지 Azure Active Directory.

2. [로그인하여](https://security.microsoft.com/) Microsoft 365 Defender.

3. 끝점 **설정**  >    >  **리디렉션으로**  >  **이동하거나** [여기를 클릭합니다.](https://security.microsoft.com/preferences2/portal_redirection)  

4. 자동 리디렉션 설정을 으로 **전환합니다.**

5. 사용 **을** 클릭하여 자동 리디렉션을 Microsoft 365 Defender.

>[!IMPORTANT]
>이 설정을 사용하도록 설정하면 활성 사용자 세션이 종료되지 않습니다. 이 설정이 적용되는 동안 활성 세션에 있는 계정은 현재 세션을 종료하고 Microsoft 365 Defender 다시 로그인한 후에만 활성 세션으로 연결됩니다.

>[!NOTE]
>이 설정을 사용하도록 설정하거나 사용하지 않도록 설정하려면 전역 관리자 또는 Azure Active Directory 권한이 있어야 합니다.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>이전 포털을 사용하여 다시 돌아갈 수 있나요?

If something isn't working for you or if there's anything you're unable to complete through Microsoft 365 Defender, we want to hear it. 리디렉션과 관련한 문제가 발생하는 경우 피드백 제출 보내기 양식을 사용하여 알려주는 것이 권장됩니다.

이전의 Microsoft Defender for Endpoint 포털로 되 되 관리:

1. [전역 관리자로](https://security.microsoft.com/) 로그인하거나 Microsoft 365 Defender Azure Active Directory에서 보안 관리자 권한을 사용하여 계정으로 로그인합니다.

2. 끝점 **설정** 일반 포털  >    >    >  **리디렉션으로 이동하거나** 여기에서 [페이지를 열 수 있습니다.](https://security.microsoft.com/preferences2/portal_redirection)  

3. 자동 리디렉션 설정을 끄기 로 **전환합니다.**

4. 메시지가 **표시될** & 공유하지 않도록 설정을 클릭합니다.

이 설정은 어떤 경우든 다시 사용하도록 설정할 수 있습니다. 

사용하지 않도록 설정하면 계정이 더 이상 security.microsoft.com 라우팅되지 않습니다. securitycenter.windows.com 또는 이전 포털에 다시 securitycenter.microsoft.com. 

## <a name="related-information"></a>관련 정보
- [Microsoft 365 Defender 개요](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft는 보안 운영을 현대화하기 위해 통합 SIEM 및 XDR을 제공합니다.](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 및 SIEM 인포그래픽](https://afrait.com/blog/xdr-versus-siem/) 
- [`The New Defender`](https://afrait.com/blog/the-new-defender/) 
- [Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 보안 포털 및 관리 센터](portals.md)
