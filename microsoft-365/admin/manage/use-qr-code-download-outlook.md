---
title: QR 코드를 사용하여 모바일 앱에 Outlook 로그인
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: QR 코드를 사용하여 모바일 앱을 인증하고 다운로드하는 Outlook 대해 자세히 알아보습니다.
ms.openlocfilehash: c13fbeabd320c64925165ba16797d5a3471961ad
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391342"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>QR 코드를 사용하여 모바일 앱에 Outlook 로그인

> [!IMPORTANT]
> 이 기능은 조직에서 대상 지정 릴리스를 설정한 조직에서만 사용할 Microsoft 365 관리 센터. 대상 지정 릴리스를 켜고 작동 방식에 대한 자세한 내용은 표준 또는 대상 지정 릴리스 옵션 설정 [을 참조하세요.](release-options-in-office-365.md) 앞으로 몇 주 후에 공개 미리 보기를 통해 더 많은 조직으로 확장할 예정입니다. 공개 미리 보기를 사용하면 미리 보기 기능을 Microsoft 365 있습니다.

관리자는 Microsoft 365 사용자 이름과 암호를 입력하지 않고도 모바일 장치에서 Outlook 또는 iOS용 앱에 로그인할 수 있습니다. QR 코드를 검사하면 사용자는 모바일에서 안전하게 인증하고 Outlook 수 있습니다.

웹용 Outlook 다른 데스크톱 Outlook 응용 프로그램에서는 모바일 장치에서 앱을 사용할 수 Outlook 알림을 볼 수 있습니다. 이러한 알림은 관리자가 Powershell을 사용하여 관리할 Exchange 있습니다. 사용자가 모바일 장치에서 앱을 다운로드하기 위해 SMS 문자 메시지를 보내면 컴퓨터에 QR 코드가 표시됩니다. QR 코드를 스캔하여 휴대폰 또는 태블릿에서 Outlook 수 있습니다. 이 QR 코드는 한 번만 교환할 수 있는 짧은 라이브 토큰입니다.

> [!NOTE]
> 경우에 따라 사용자가 컴퓨터에서 다시 인증하여 QR 코드를 생성해야 합니다.

## <a name="use-exchange-powershell"></a>PowerShell Exchange 사용

이 기능은 기본적으로 켜져 있습니다. 이 기능을 사용하지 않도록 설정하기 위해 아래 단계를 따르세요.

1. [커넥트 powerShell을 Exchange 합니다.](/powershell/exchange/connect-to-exchange-online-powershell)
2. PowerShell을 사용하여 사용자에게 모바일 앱에 대한 알림을 Outlook 수 있습니다. 이렇게 하면 QR 코드 로그인 흐름이 표시되지 않습니다.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>관련 콘텐츠

[표준 또는 대상 지정 릴리스 옵션](release-options-in-office-365.md) 설정(문서)\
[Set-OrganizationConfig(문서)](/powershell/module/exchange/set-organizationconfig)