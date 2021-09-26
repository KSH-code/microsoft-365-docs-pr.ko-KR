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
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: QR 코드를 사용하여 Outlook 모바일을 인증하고 다운로드하는 방법을 알아보세요.
ms.openlocfilehash: 0b47e60f29d3730701750a1b122f782c53122603
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775813"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>QR 코드를 사용하여 Outlook 모바일 앱에 로그인

Microsoft 365 관리자는 사용자가 사용자 이름과 암호를 입력하지 않고도 모바일 장치에서 Android 또는 iOS용 Outlook 앱에 로그인하도록 설정할 수 있습니다. 사용자는 QR 코드를 스캔하여 Outlook 모바일에 안전하게 인증하고 로그인할 수 있습니다.

웹용 Outlook 또는 기타 데스크톱 Outlook 응용 프로그램에서 사용자는 모바일 장치에서 Outlook을 사용할 수 있음을 알리는 알림을 볼 수 있습니다. 이러한 알림은 관리자가 Exchange PowerShell을 사용하여 관리할 수 있습니다. 사용자가 자신에게 SMS 문자 메시지를 보내 모바일 장치에 앱을 다운로드하도록 선택하면 QR 코드가 컴퓨터에 나타납니다. QR 코드를 스캔하여 휴대폰이나 태블릿에서 Outlook에 로그인할 수 있습니다. 이 QR 코드는 한 번만 사용할 수 있는 단기 토큰입니다.

알림은 다음 조건이 충족되는 경우에만 생성됩니다.

1. 테넌트에 대해 QR 코드 환경이 활성화되어 있습니다(이 환경은 기본적으로 활성화되어 있음).

2. 사용자가 아직 iOS 및 Android용 Outlook을 사용하고 있지 않습니다.

3. 사용자가 읽기 창에서 비어 있는 상태입니다(첫 번째 이메일을 자동으로 여는 옵션을 선택하지 않음).

4. 사용자가 알림을 닫지 않았습니다.

> [!NOTE]
> 어떤 경우에는 사용자가 QR 코드를 생성하기 위해 컴퓨터에서 다시 인증해야 합니다.

## <a name="use-exchange-powershell"></a>Exchange PowerShell 사용

이 기능은 기본적으로 켜져 있습니다. 이 기능을 비활성화하려면 아래 단계를 따르세요.

1. [Exchange PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell).
2. PowerShell을 사용하여 Outlook 모바일 앱에 대해 사용자에게 알리는 알림을 비활성화할 수 있습니다. 또한 QR 코드 로그인 흐름이 표시되지 않습니다.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>관련된 컨텐츠

[표준 또는 대상 출시 옵션 설정](release-options-in-office-365.md)(문서)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)(문서)
