---
title: Office 365용 Microsoft Defender에서 새 Microsoft 365 보안 센터로 계정 리디렉션
description: Office 365용 Defender에서 Microsoft 365 보안 센터로 리디렉션하는 방법
keywords: Microsoft 365 보안 센터, Microsoft 365 보안 센터 시작, 보안 센터 리디렉션
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072679"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Office 365용 Microsoft Defender에서 Microsoft 365 보안 센터로 계정 리디렉션

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender
- Office 365용 Defender

이 문서에서는 이전 Microsoft 보안 및 준수 센터(protection.office.com 또는 securitycenter.microsoft.com)에서 Microsoft 365 보안 센터(security.microsoft.com)로 자동 리디렉션을 사용하도록 설정하여 계정을 Microsoft 365 보안 센터로 라우팅하는 방법에 대해 security.microsoft.com.

>[!NOTE]
> Office 365 E5 및 Office P2용 Microsoft Defender 고객에게만 포털 리디렉션 기능을 사용할 수 있습니다.

## <a name="what-to-expect"></a>예상할 일
자동 리디렉션을 사용하도록 설정하고 활성화하면 Office 365 보안 및 규정 준수(protection.office.com)의 보안 관련 기능에 액세스하는 사용자가 Microsoft 365 보안 센터() 로 자동으로 라우팅됩니다. https://security.microsoft.com)  

변경된 내용을 자세히 알아보시고, Microsoft 365 보안 센터에서 [Office 365용 Microsoft Defender를 사용할 수 있습니다.](microsoft-365-security-center-mdo.md)

자동 리디렉션을 설정하면 사용자가 Office 365 보안 및 준수 센터의 보안 기능을 사용할 때 Microsoft 365 보안 센터로 라우팅됩니다.

여기에는 위협 관리 섹션 및 위협 관리 대시보드 및 보고서의 기능이 포함됩니다. 보안과 관련이 없는 Office 365 보안 및 준수 센터의 항목은 Microsoft 365 보안 센터로 리디렉션되지 않습니다.

준수 관련 항목은 Microsoft 365 규정 준수 센터에서 찾을 수 있으며, 메일 흐름 관련 항목은 Exchange 관리 센터에서 찾을 수 있습니다.

규정 준수 관련 기능 또는 둘 다를 충족하는 기능 등 다른 모든 기능은 리디렉션의 영향을 받지 않습니다. Office 365 보안 경고는 리디렉션 없이 Microsoft 365 보안 센터와 Office 365 보안 및 준수 센터 둘 다에 표시됩니다.  

### <a name="set-up-portal-redirection"></a>포털 리디렉션 설정
다음을 통해 Microsoft 365 보안 센터로 계정 라우팅을 security.microsoft.com.

1. 전역 관리자 또는 Azure Active Directory에 보안 관리자 권한이 있는지 확인합니다.
2. [](https://security.microsoft.com/) Microsoft 365 보안 센터에 로그인합니다.
3. 설정 전자  >  **메일 및 & 포털**  >  **리디렉션으로 이동합니다.**  
4. 자동 리디렉션 설정을 으로 **전환합니다.**
5. Microsoft  365 보안 센터 포털에 자동 리디렉션을 적용하려면 사용 을 클릭합니다.

> [!NOTE]
> 리디렉션을 사용하도록 설정한 후 이 설정이 적용되는 동안 활성 세션의 계정은 세션에서출되지 않습니다. 현재 세션을 종료하고 다시 로그인한 후에만 Microsoft 365 보안 센터로 라우팅됩니다.

## <a name="can-i-go-back-to-using-the-former-portal"></a>이전 포털을 사용하여 다시 돌아갈 수 있나요?
문제가 작동하지 않는 경우 또는 Microsoft 365 보안 센터 포털을 통해 완료할 수 없는 경우 포털 피드백 옵션을 사용하여 해당 정보를 듣고 싶을 것입니다. 리디렉션에 문제가 발생하면 비공개 미리 보기를 통해 직접 PM 친구에게 연락하거나 피드백 제출 보내기 양식을 통해 알려주세요.

이전 포털로 되버리기:

1. [전역 관리자로](https://security.microsoft.com/) Microsoft 365 보안 센터에 로그인하거나 Azure Active Directory에서 보안 관리자 권한을 사용하여 계정으로 로그인합니다.

2. 설정 **끝점**  >  **일반 포털**  >    >  **리디렉션으로 이동합니다.**  

3. 자동 리디렉션 설정을 끄기 로 **전환합니다.**

4. 메시지가 **표시될** & 공유하지 않도록 설정을 클릭합니다.

이 설정은 어떤 경우든 다시 사용하도록 설정할 수 있습니다.

사용하지 않도록 설정하면 계정이 더 이상 security.microsoft.com 라우팅되지 않습니다. securitycenter.windows.com 또는 이전 포털에 다시 securitycenter.microsoft.com.

## <a name="related-information"></a>관련 정보
- [Microsoft 365 보안 센터 개요](overview-security-center.md)
- [Microsoft 365 보안 센터의 끝점용 Microsoft Defender](microsoft-365-security-center-mde.md)
- [Microsoft는 보안 운영을 현대화하기 위해 통합 SIEM 및 XDR을 제공합니다.](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 및 SIEM 인포그래픽](https://afrait.com/blog/xdr-versus-siem/) 
- [The New Defender](https://afrait.com/blog/the-new-defender/) 
- [About Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 보안 포털 및 관리 센터](portals.md)