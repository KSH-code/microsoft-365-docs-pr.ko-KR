---
title: QR 코드를 사용하여 Outlook 모바일 앱에 로그인
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
description: QR 코드를 사용하여 Outlook 모바일을 인증하고 다운로드하는 방법을 학습합니다.
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242357"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>QR 코드를 사용하여 Outlook 모바일 앱에 로그인

> [!IMPORTANT]
> 이 기능은 Microsoft 365 관리 센터에서 대상 지정 릴리스를 설정한 조직에서만 사용할 수 있습니다. 대상 지정 릴리스를 켜고 작동 방식에 대한 자세한 내용은 표준 또는 대상 지정 릴리스 옵션 설정을 [참조하세요.](release-options-in-office-365.md) 공개 미리 보기를 통해 몇 주 후에 더 많은 조직으로 확장할 예정입니다. 공개 미리 보기에서는 Microsoft 365 기능에 미리 액세스할 수 있습니다.

Microsoft 365 관리자는 사용자가 사용자 이름과 암호를 입력하지 않고도 모바일 장치에서 Android 또는 iOS용 Outlook 앱에 로그인하도록 할 수 있습니다. QR 코드를 검사하면 사용자는 안전하게 인증하고 Outlook 모바일에 로그인할 수 있습니다.

웹용 Outlook 또는 기타 데스크톱 Outlook 응용 프로그램에서는 사용자가 모바일 장치에서 Outlook을 사용할 수 있는 경우를 알리는 알림이 표시될 수 있습니다. 이러한 알림은 관리자가 Exchange Powershell을 사용하여 관리할 수 있습니다. 사용자가 모바일 장치에서 앱을 다운로드하기 위해 SMS 문자 메시지를 보내면 컴퓨터에 QR 코드가 표시됩니다. QR 코드를 검사하여 휴대폰 또는 태블릿에서 Outlook에 로그인할 수 있습니다. 이 QR 코드는 한 번만 교환할 수 있는 짧은 라이브 토큰입니다.

> [!NOTE]
> 경우에 따라 사용자가 컴퓨터에서 다시 인증하여 QR 코드를 생성해야 합니다.

## <a name="use-exchange-powershell"></a>Exchange PowerShell 사용

이 기능은 기본적으로 켜져 있습니다. 이 기능을 사용하지 않도록 설정하기 위해 아래 단계를 따르세요.

1. [Exchange PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. PowerShell을 사용하여 사용자에게 Outlook 모바일 앱에 대해 알리는 알림을 사용하지 않도록 설정할 수 있습니다. 이렇게 하면 QR 코드 로그인 흐름이 표시되지 않습니다.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

관련 항목

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
