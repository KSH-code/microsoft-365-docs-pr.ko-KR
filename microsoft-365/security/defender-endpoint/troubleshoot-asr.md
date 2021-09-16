---
title: 공격 표면 감소 규칙 문제 해결
description: 끝점용 Microsoft Defender의 공격 표면 축소 규칙 문제를 해결하기 위한 리소스 및 샘플 코드입니다.
keywords: 문제 해결, 오류, 수정, windows defender eg, asr, 규칙, hips, 문제 해결, 감사, 제외, 가극적, 손상, 차단, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1e4e32864c2541cfc0cf14602ec954d5e643f309
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59402145"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>공격 표면 감소 규칙 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

공격 표면 [감소 규칙을](attack-surface-reduction.md) 사용하는 경우 다음과 같은 문제가 있을 수 있습니다.

- 규칙은 파일, 처리 또는 수행하지 말아야 할 다른 작업(가음성)을 차단합니다.
- 규칙이 설명된 바와 같이 작동하지 않습니다. 또는 규칙이 처리해야 하는 파일 또는 프로세스를 차단하지 않습니다(거짓 부정).

이러한 문제를 해결하는 네 가지 단계가 있습니다.

1. [선행 준비 확인](#confirm-prerequisites)
2. [감사 모드를 사용하여 규칙 테스트](#use-audit-mode-to-test-the-rule)
3. [지정된 규칙에](#add-exclusions-for-a-false-positive) 대한 제외 추가(가음성의 경우)
4. [지원 로그 제출](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>선행 준비 확인

공격 표면 감소 규칙은 다음 조건이 있는 디바이스에서만 작동합니다.

- 끝점은 Windows 10 Enterprise 버전 1709(Fall Creators Update라고도 알려지기)를 실행하고 있습니다.

- 끝점에서 단독 Microsoft Defender 바이러스 백신 보호 앱으로 사용하고 있습니다. [다른 바이러스 백신 앱을 사용하는 경우 자체적으로 Microsoft Defender 바이러스 백신 수 없습니다.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

- [실시간 보호가](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 사용됩니다.

- 감사 모드를 사용할 수 없습니다. 공격 표면 감소 규칙  사용에 설명된 바와 같이 그룹 정책을 사용하여 규칙을 사용 안 하도록 설정(값: **0)로** [설정](enable-attack-surface-reduction.md)

이러한 선행 단계가 모두 충족된 경우 다음 단계로 진행하여 감사 모드에서 규칙을 테스트합니다.

## <a name="use-audit-mode-to-test-the-rule"></a>감사 모드를 사용하여 규칙 테스트

Windows Defender 테스트 demo.wd.microsoft.com 웹 사이트를 방문하여 [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 공격 표면 감소 규칙이 일반적으로 장치의 미리 구성된 시나리오 및 프로세스에서 작동하고 있는지 확인하거나, 보고 규칙만 사용하도록 설정하는 감사 모드를 사용할 수 있습니다.

데모 도구를 [](evaluate-attack-surface-reduction.md) 사용하여 공격 표면 감소 규칙이 어떻게 작동하여 문제가 발생하는 특정 규칙을 테스트하는지 확인하려면 다음 지침을 따르세요.

1. 테스트할 특정 규칙에 대해 감사 모드를 사용하도록 설정하십시오. 그룹 정책을 사용하여 공격  표면 감소 규칙 사용에 설명된 바와 같이 규칙을 감사 모드(값: **2)로** [설정](enable-attack-surface-reduction.md) 감사 모드를 사용하면 규칙이 파일 또는 프로세스를 보고할 수 있지만 계속 실행할 수 있습니다.

2. 문제를 일으키는 활동(예: 차단해야 하지만 허용되는 파일 또는 프로세스를 열거나 실행)을 실행합니다.

3. [공격 표면 감소](attack-surface-reduction.md) 규칙 이벤트 로그를 검토하여 규칙이 사용으로 설정된 경우 규칙이 파일 또는 프로세스를 차단하는지 **확인합니다.**

규칙이 차단할 것으로 예상하는 파일 또는 프로세스를 차단하지 않는 경우 먼저 감사 모드를 사용하도록 설정되어 있는지 확인합니다.

감사 모드는 다른 기능 또는 자동화된 PowerShell 스크립트를 통해 테스트할 수 있으며 테스트가 완료된 후 사용하지 않도록 설정되지 않은 것일 수 있습니다.

데모 도구 및 감사 모드를 사용하여 규칙을 테스트한 경우 공격 표면 감소 규칙이 미리 구성된 시나리오에서 작동하지만 규칙이 예상대로 작동하지 않는 경우 상황에 따라 다음 섹션 중 하나를 진행합니다.

1. 공격 표면 감소 규칙이 차단하지 말아야 할 것을 차단하는 경우(가음성으로도 알려져) 먼저 공격 표면 축소 규칙 제외를 추가할 [수 있습니다.](#add-exclusions-for-a-false-positive)

2. 공격 표면 감소 규칙이 차단해야 하는 것을 차단하지 않는 경우(거짓 부정) 바로 마지막 단계로 진행하여 진단 데이터를 수집하고 에 문제를 제출할 [수 있습니다.](#collect-diagnostic-data-for-file-submissions)

## <a name="add-exclusions-for-a-false-positive"></a>가짓 긍정에 대한 제외 추가

공격 표면 감소 규칙이 차단하지 말아야 할 것을 차단하는 경우(가음성으로도 알려지며) 제외를 추가하여 공격 표면 감소 규칙이 제외된 파일 또는 폴더를 평가하지 못하게 방지할 수 있습니다.

제외를 추가하는 방법에 대한 자세한 내용은 공격 표면 [축소 사용자 지정을 참조합니다.](customize-attack-surface-reduction.md)

> [!IMPORTANT]
> 제외할 개별 파일 및 폴더를 지정할 수는 있지만 개별 규칙을 지정할 수는 없습니다.
> 즉, 제외된 파일 또는 폴더는 모든 ASR 규칙에서 제외됩니다.

## <a name="report-a-false-positive-or-false-negative"></a>가짓 긍정 또는 거짓 부정 보고

보안 [Windows Defender](https://www.microsoft.com/wdsi/filesubmission) 웹 기반 제출 양식을 사용하여 네트워크 보호에 대해 거짓 부정 또는 가긍성 보고를 합니다. E5 Windows 연결된 모든 경고에 대한 링크를 [제공할 수도 있습니다.](alerts-queue.md)

## <a name="collect-diagnostic-data-for-file-submissions"></a>파일 전송에 대한 진단 데이터 수집

공격 표면 감소 규칙에 대한 문제를 보고하는 경우 Microsoft 지원 및 엔지니어링 팀에서 문제를 해결하는 데 사용할 수 있는 진단 데이터를 수집하고 제출해야 합니다.

1. 승강된 명령 프롬프트를 열고 Windows Defender 변경합니다.

   ```console
   cd "c:\program files\windows defender"
   ```

2. 다음 명령을 실행하여 진단 로그를 생성합니다.

   ```console
   mpcmdrun -getfiles
   ```

3. 기본적으로 에 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 저장됩니다. 파일을 제출 양식에 첨부합니다.

## <a name="related-articles"></a>관련 문서

- [공격 표면 감소 규칙](attack-surface-reduction.md)
- [공격 표면 감소 규칙 사용](enable-attack-surface-reduction.md)
- [공격 표면 감소 규칙 평가](evaluate-attack-surface-reduction.md)
