---
title: 제어된 폴더 액세스 평가
description: 제어된 폴더 액세스를 통해 악성 앱에 의해 파일이 변경되지 못하게 보호하는 방법을 확인합니다.
keywords: Exploit Protection, windows 10, windows defender, 랜섬웨어, 보호, 평가, 테스트, 데모, 시도
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 708d7d271e03b127460d5b2aa2745568d920a198
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60042881"
---
# <a name="evaluate-controlled-folder-access"></a>제어된 폴더 액세스 평가

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)


[제어된 폴더 액세스는](controlled-folders.md) 의심스러운 앱 또는 악성 앱에 의해 문서 및 파일을 수정하지 못하게 보호하는 기능입니다. 제어된 폴더 액세스는 Windows Server 2019, Windows Server 2022 및 Windows 10 지원됩니다.

파일을 암호화하고 인질을 [](https://www.microsoft.com/wdsi/threats/ransomware) 보유하려는 랜섬웨어로부터 보호하는 데 특히 유용합니다.

이 문서는 제어된 폴더 액세스를 평가하는 데 도움이 됩니다. 조직에서 직접 기능을 테스트할 수 있도록 감사 모드를 사용하도록 설정하는 방법에 대해 설명되어 있습니다.

> [!TIP]
> Microsoft Defender for [Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 데모 시나리오 웹 사이트(demo.wd.microsoft.com)를 방문하여 기능이 작동하는지 확인하고 작동 방법을 확인할 수 있습니다.

## <a name="use-audit-mode-to-measure-impact"></a>감사 모드를 사용하여 영향 측정

감사 모드에서 제어된 폴더 액세스를 사용하도록 설정하여  완전히 활성화된 경우 어떤 일이 벌어질지 기록을 볼 수 있습니다. 이 기능이 조직에서 어떻게 작동할지 테스트하여 업무 앱에 영향을 주지 않는지 테스트합니다. 또한 일반적으로 특정 기간 동안 의심스러운 파일 수정 시도의 수를 알 수 있습니다.

감사 모드를 사용하도록 설정하려면 다음 PowerShell cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> 조직에서 제어된 폴더 액세스가 어떻게 작동할지 완전히 감사하려면 관리 도구를 사용하여 이 설정을 네트워크의 장치에 배포해야 합니다.
주 제어된 폴더 액세스 항목에 설명된 바와 같이 그룹 정책, Intune, MDM(모바일 장치 관리) 또는 Microsoft Endpoint Manager 설정을 구성하고 배포할 [수도 있습니다.](controlled-folders.md)

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>이벤트 뷰어에서 제어된 폴더 액세스 Windows 검토

다음 제어된 폴더 액세스 이벤트는 Microsoft/Windows/Windows/Operational 폴더의 Windows Defender 표시됩니다.

이벤트 ID | 설명
-|-
 5007 | 설정이 변경될 때의 이벤트
 1124 | 감사된 제어된 폴더 액세스 이벤트
 1123 | 차단된 제어된 폴더 액세스 이벤트

> [!TIP]
> 로그를 중앙에서 [Windows 이벤트](/windows/win32/wec/setting-up-a-source-initiated-subscription) 전달 구독을 구성할 수 있습니다. 

## <a name="customize-protected-folders-and-apps"></a>보호된 폴더 및 앱 사용자 지정

평가하는 동안 보호된 폴더 목록에 추가하거나 특정 앱에서 파일을 수정하도록 허용할 수 있습니다.

그룹 [정책,](controlled-folders.md) PowerShell 및 MDM CSP(구성 서비스 공급자)를 비롯한 관리 도구를 사용하여 기능을 구성하려면 제어된 폴더 액세스로 중요한 폴더 보호를 참조합니다.

## <a name="see-also"></a>참고 항목

* [제어된 폴더 액세스를 사용하여 중요한 폴더 보호](controlled-folders.md)
* [엔드포인트용 Microsoft Defender 평가](evaluate-mde.md)
* [감사 모드 사용](audit-windows-defender.md)
