---
title: 보안 및 Office 365 센터에서 새 보안 센터로 Microsoft 365 리디렉션
description: 보안 센터에 대한 Defender에서 Office 365 보안 Microsoft 365 방법.
keywords: Microsoft 365 보안 센터, 보안 센터 Microsoft 365 시작, 보안 센터 리디렉션
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 703d3c3c9086aa2bdfada560c009e8738dffbb18
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768972"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-security-center"></a>보안 및 Office 365 센터에서 Microsoft 365 리디렉션

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender
- Office 365용 Defender

이 문서에서는 이전 Office 365 Office 365 보안 및 준수 센터(protection.office.com)에서 Microsoft 365 보안 센터(security.microsoft.com)로 자동 리디렉션을 사용하도록 설정하여 계정을 Microsoft 365 보안 센터로 라우팅하는 방법에 대해 security.microsoft.com.

## <a name="what-to-expect"></a>예상할 일
자동 리디렉션을 사용하도록 설정하고 활성화하면 Office 365 보안 및 규정 준수(protection.office.com)의 보안 관련 기능에 액세스하는 사용자는 자동으로 Microsoft 365 보안 센터( ( 로 라우팅됩니다. https://security.microsoft.com)  

변경된 내용을 자세히 알아보면 Microsoft [Defender for Office 365 보안 센터에서 Microsoft 365 있습니다.](microsoft-365-security-center-mdo.md)

자동 리디렉션이 켜져 있는 경우 사용자가 Microsoft 365 보안 및 준수 센터의 보안 기능을 사용할 때 Office 365 라우팅됩니다.

여기에는 위협 관리 섹션 및 위협 관리 대시보드 및 보고서의 기능이 포함됩니다. Office 365 보안 및 준수 센터의 항목은 보안 및 준수 센터로 Microsoft 365 않습니다.

규정 준수 관련 항목은 Microsoft 365 규정 준수 센터에서 찾을 수 있으며, 메일 흐름 관련 항목은 Exchange 관리 센터에서 찾을 수 있습니다.

규정 준수 관련 기능 또는 둘 다를 충족하는 기능 등 다른 모든 기능은 리디렉션의 영향을 받지 않습니다. Office 365 보안 경고는 리디렉션 없이 Microsoft 365 보안 센터와 Office 365 및 준수 센터 둘 다에 표시됩니다.  

### <a name="set-up-portal-redirection"></a>포털 리디렉션 설정
다음의 경우 Microsoft 365 보안 센터로 계정 라우팅을 security.microsoft.com.

1. 전역 관리자 또는 Azure Active Directory에 보안 관리자 권한이 있는지 확인합니다.
2. [보안 센터에](https://security.microsoft.com/) Microsoft 365 로그인합니다.
3. 전자 **메일 설정**  >  **포털 리디렉션으로**  >  **& 이동합니다.**  
4. 자동 리디렉션 설정을 으로 **전환합니다.**
5. 보안 **센터** 포털에 자동 리디렉션을 적용하려면 Microsoft 365 클릭합니다.

> [!NOTE]
> 리디렉션을 사용하도록 설정한 후 이 설정이 적용되는 동안 활성 세션의 계정은 세션에서출되지 않습니다. 현재 세션을 종료하고 다시 로그인한 후에 Microsoft 365 보안 센터로만 라우팅됩니다.

## <a name="can-i-go-back-to-using-the-former-portal"></a>이전 포털을 사용하여 다시 돌아갈 수 있나요?
문제가 작동하지 않는 경우 또는 Microsoft 365 보안 센터 포털을 통해 완료할 수 없는 경우 포털 피드백 옵션을 사용하여 해당 정보를 듣고 싶을 것입니다. 리디렉션에 문제가 발생하면 알려주세요.

이전 포털로 되버리기:

1. [전역 관리자로](https://security.microsoft.com/) Microsoft 365 Azure Active Directory의 보안 관리자 권한을 사용하여 보안 센터에 로그인합니다.

2. 전자 **메일 설정**  >  **포털 리디렉션으로**  >  **& 이동합니다.**   

3. 자동 리디렉션 설정을 끄기 로 **전환합니다.**

4. 메시지가 **표시될** & 공유하지 않도록 설정을 클릭합니다.

이 설정은 어떤 경우든 다시 사용하도록 설정할 수 있습니다.

사용하지 않도록 설정하면 계정이 더 이상 security.microsoft.com 라우팅되지 않습니다. 또한 이전 포털(securitycenter.windows.com 또는 securitycenter.microsoft.com.

## <a name="related-information"></a>관련 정보
- [Microsoft 365 보안 센터 개요](overview-security-center.md)
- [Microsoft 365 끝점용 Microsoft Defender](microsoft-365-security-center-mde.md)
- [Microsoft는 보안 운영을 현대화하기 위해 통합 SIEM 및 XDR을 제공합니다.](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 및 SIEM 인포그래픽](https://afrait.com/blog/xdr-versus-siem/) 
- [The New Defender](https://afrait.com/blog/the-new-defender/) 
- [Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 보안 포털 및 관리 센터](portals.md)
