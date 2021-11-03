---
title: 보안 및 Office 365 센터에서 새 보안 및 준수 센터로 Microsoft 365 Defender
description: 에 대한 Defender에서 사용자 Office 365 Microsoft 365 Defender.
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
ms.openlocfilehash: e6b7df942ee117c0f23a97516c75d64131e0770d
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60698408"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>Office 365 및 준수 센터에서 계정으로 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender
- Office 365용 Defender

이 문서에서는 이전 Microsoft 365 Defender 보안 및 준수 센터(protection.office.com)에서 Microsoft 365 Defender Office 365(security.microsoft.com)로 자동 리디렉션을 사용하도록 설정하여 계정을 Microsoft 365 Defender 방법에 대해 security.microsoft.com.

## <a name="what-to-expect"></a>예상할 일

자동 리디렉션을 사용하도록 설정하고 활성화하면 Office 365 보안 및 규정 준수(protection.office.com)의 보안 관련 기능에 액세스하는 사용자는 자동으로 Microsoft 365 Defender(security.microsoft.com)로 라우팅됩니다.

변경된 내용을 자세히 알아보시고 Microsoft [Defender for Office 365 에서 Microsoft 365 Defender.](microsoft-365-security-center-mdo.md)

자동 리디렉션을 설정하면 사용자가 Microsoft 365 Defender 및 준수 센터에서 보안 기능을 사용할 때 Office 365 라우팅됩니다.

여기에는 위협 관리 섹션, 경고(경고 및 경고 정책 보기) 및 위협 관리 대시보드 및 보고서의 기능이 포함됩니다. 보안 및 Office 365 관련이 없는 항목은 보안 및 준수 센터의 항목으로 Microsoft 365 Defender.

규정 준수 관련 항목은 Microsoft 365 규정 준수 센터 있으며 메일 흐름 관련 항목은 Exchange 관리 센터에서 찾을 수 있습니다.

규정 준수 관련 기능 또는 둘 다를 충족하는 기능 등 다른 모든 기능은 리디렉션의 영향을 받지 않습니다.

### <a name="set-up-portal-redirection"></a>포털 리디렉션 설정

2021년 10월 초부터 포털 리디렉션이 자동으로 또는 기본적으로 수행됩니다. 그러나 일시적으로 사용하지 않도록 설정해야 하는 경우 해당 단계가 따릅니다.

<!--To start routing accounts to Microsoft 365 Defender at security.microsoft.com:

1. Make sure you're a global administrator or have security administrator permissions in Azure Active directory.
2. [Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.
3. Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.  
4. Toggle the Automatic redirection setting to **On**.
5. Click **Enable** to apply automatic redirection to Microsoft 365 Defender.

> [!NOTE]
> After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.-->

## <a name="can-i-go-back-to-using-the-former-portal"></a>이전 포털을 사용하여 다시 돌아갈 수 있나요?

문제가 작동하지 않는 경우 또는 사용자 검색을 통해 완료할 수 Microsoft 365 Defender 경우 포털 피드백 옵션을 사용하여 해당 정보를 듣고 싶을 것입니다. 리디렉션에 문제가 발생하면 알려주세요.

이전 포털로 되버리기:

1. [전역 관리자로](https://security.microsoft.com/) 로그인하거나 Microsoft 365 Defender Azure Active Directory에서 보안 관리자 권한을 사용하여 계정으로 로그인합니다.

2. 전자 **메일 설정**  >  **포털 리디렉션으로**  >  **& 이동합니다.**

3. 자동 리디렉션 설정을 끄기 로 **전환합니다.**

4. 메시지가 **표시될** & 공유하지 않도록 설정을 클릭합니다.

이 설정은 어떤 경우든 다시 사용하도록 설정할 수 있습니다.

## <a name="related-information"></a>관련 정보
- [Microsoft 365 Defender 개요](overview-security-center.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft는 보안 운영을 현대화하기 위해 통합 SIEM 및 XDR을 제공합니다.](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 및 SIEM 인포그래픽](https://afrait.com/blog/xdr-versus-siem/) 
- [`The New Defender`](https://afrait.com/blog/the-new-defender/) 
- [Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 보안 포털 및 관리 센터](portals.md)
