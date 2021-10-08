---
title: 공격 표면 감소 규칙 평가
description: 공격 표면 감소가 사용자 지정 데모 도구를 사용하여 공격을 차단하고 방지하는 방법을 참조하세요.
keywords: 공격 표면 감소, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 평가, 테스트, 데모
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 79ba3d241a913ca967c590c856e53d4073e76f3f
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2021
ms.locfileid: "60239819"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>공격 표면 감소 규칙 평가

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

공격 표면 감소 규칙은 일반적으로 맬웨어가 장치 또는 네트워크를 손상시킬 때 사용하는 작업을 방지하는 데 도움이 됩니다. 공격 표면 감소 규칙은 맬웨어 및 랜섬웨어에 사용되는 많은 일반적인 진입점을 닫는 데 도움이 됩니다.

다음 버전 및 버전의 디바이스를 실행하는 장치에 대해 공격 표면 감소 규칙을 Windows.

- Windows 10 Pro 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- Windows 10 Enterprise 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- Windows 서버, [버전 1803(반기 채널)](/windows-server/get-started/whats-new-in-windows-server-1803) 이상
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
-  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2) 
- Windows Server 2022

> [!WARNING]
> 공격 서비스 축소 규칙을 Windows Server 2016 예기치 않은 결과가 발생하고 서버 성능에 영향을 줄 수 있습니다. 지원되지 않는 플랫폼에 공격 표면 감소 규칙을 사용하도록 설정하거나 배포하지 않는 것이 좋습니다.

감사 모드를 사용하도록 설정하여 [](audit-windows-defender.md) 조직에서 기능을 직접 테스트하여 공격 표면 감소 규칙을 평가하는 방법을 알아보십시오.

> [!TIP]
> Microsoft Defender for [Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 데모 시나리오 웹 사이트(demo.wd.microsoft.com)를 방문하여 기능이 작동하는지 확인하고 작동 방법을 확인할 수 있습니다.

## <a name="use-audit-mode-to-measure-impact"></a>감사 모드를 사용하여 영향 측정

감사 모드에서 공격 표면 감소 규칙을 사용하도록 설정하여 기능이 완전히 활성화된 경우 차단된 앱의 레코드를 볼 수 있습니다. 이 기능이 조직에서 어떻게 작동할지 테스트하여 업무 앱에 영향을 주지 않는지 테스트합니다. 또한 일반 사용 중에 규칙이 얼마나 자주 발생하게 될지 알 수 있습니다.

감사 모드에서 공격 표면 감소 규칙을 사용하도록 설정하려면 다음 PowerShell cmdlet을 사용 합니다.

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

여기서 는 공격 표면 감소 규칙의 `<rule ID>` [GUID 값입니다.](attack-surface-reduction-rules.md)

감사 모드에서 추가된 모든 공격 표면 축소 규칙을 사용하도록 설정하려면 다음 PowerShell cmdlet을 사용 합니다.

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> 조직에서 공격 표면 감소 규칙이 어떻게 작동할지 완전히 감사하려면 관리 도구를 사용하여 이 설정을 네트워크의 장치에 배포해야 합니다.

그룹 정책, Intune 또는 MDM(모바일 장치 관리) CSP(구성 서비스 공급자)를 사용하여 설정을 구성하고 배포할 수도 있습니다. 자세한 내용은 주 공격 표면 [감소 규칙 문서에서 자세히](attack-surface-reduction.md) 알아보십시오.

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>이벤트 뷰어에서 공격 Windows 검토

차단된 앱을 검토하려면 Microsoft-Windows-Windows Defender/작동 로그에서 이벤트 뷰어를 열고 이벤트 ID 1121을 필터링합니다. 다음 표에는 모든 네트워크 보호 이벤트가 나열됩니다.

이벤트 ID | 설명
-|-
 5007 | 설정이 변경될 때의 이벤트
 1121 | 차단 모드에서 공격 표면 감소 규칙이 발생하면 이벤트
 1122 | 감사 모드에서 공격 표면 감소 규칙이 발생하면 이벤트

## <a name="customize-attack-surface-reduction-rules"></a>공격 표면 감소 규칙 사용자 지정

평가하는 동안 각 규칙을 개별적으로 구성하거나 특정 파일 및 프로세스가 기능으로 평가되지 못하도록 제외할 수 있습니다.

그룹 [정책 및](customize-attack-surface-reduction.md) MDM CSP 정책을 포함하여 관리 도구를 사용하여 기능을 구성하는 방법에 대한 자세한 내용은 공격 표면 축소 규칙 사용자 지정을 참조하세요.

## <a name="see-also"></a>참고 항목

- [공격 표면 감소 규칙을 사용하여 공격 표면 감소](attack-surface-reduction.md)
- [감사 모드를 사용하여 감사 Windows Defender](audit-windows-defender.md)
- [공격 표면 감소 FAQ](attack-surface-reduction.md)
