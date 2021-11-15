---
title: 끝점 ASR 규칙에 대한 Microsoft Defender 보고 및 문제 해결
description: 이 항목에서는 끝점 ASR 규칙에 대한 Microsoft Defender를 보고하고 문제를 해결하는 방법을 설명
keywords: 공격 표면 감소 규칙, asr, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.custom:
- asr
- admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: fd23f0cdf35a9b7e236a957fed0922192091beb3
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963158"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-endpoint-asr-rules"></a>끝점 ASR 규칙에 대한 Microsoft Defender 보고 및 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft 365 보안 센터는 Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ID,</a> 데이터, 장치, 앱 및 인프라 전체의 보안을 모니터링하고 관리하기 위한 새로운 인터페이스입니다. Microsoft 365 보안 센터를 통해 조직의 보안 상태를 쉽게 검토할 수 있으며 디바이스, 사용자 및 앱을 구성하는 작업을 비롯하여 의심스러운 활동에 대해 알림을 받을 수 있습니다. Microsoft 365 보안 센터는 보안 관리자와 보안 운영 팀이 조직을 더 효과적으로 관리하고 보호하는 데 도움을 줄 수 있도록 설계되었습니다. 의 Microsoft 365 보안 센터를 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a> 방문합니다.

Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">보안</a>센터에서 현재 ASR 규칙 구성 및 자산의 이벤트를 전체적으로 살펴 볼 수 있습니다. 이러한 보고서를 채우기 위해 디바이스를 끝점용 Microsoft Defender 서비스에 온보딩해야 합니다.
다음은 Microsoft 365 보안 센터의 스크린샷입니다(보고서  장치 공격 표면 \>  \> **감소).** 장치 수준에서 공격 **표면** 감소 규칙 창에서 **구성을** 선택합니다. 다음 화면이 표시되어 특정 장치를 선택하고 개별 ASR 규칙 구성을 확인할 수 있습니다.

:::image type="content" source="images/asrrulesnew.png" lightbox="images/asrrulesnew.png" alt-text="ASR 규칙 화면.":::

## <a name="microsoft-defender-for-endpoint---advanced-hunting"></a>끝점용 Microsoft Defender - 고급 헌팅

끝점용 Microsoft Defender의 가장 강력한 기능 중 하나는 고급 헌팅입니다. 고급 헌팅에 익숙하지 않은 경우 고급 헌팅을 통해 위협에 대한 사전 예방적 헌팅을 [참조합니다.](advanced-hunting-overview.md)

고급 헌팅은 끝점용 Defender가 장치에서 수집하는 캡처된(원시) 데이터의 최대 30일을 탐색할 수 있는 쿼리 기반(Kusto 쿼리 언어) 위협 헌팅 도구입니다. 고급 헌팅을 통해 이벤트를 사전적으로 검사하여 흥미로운 지표와 엔터티를 찾을 수 있습니다. 데이터에 유연하게 액세스하면 알려진 위협과 잠재적 위협 모두에 대한 제약이 없는 헌팅에 도움이 됩니다.

고급 헌팅을 통해 ASR 규칙 정보를 추출하고, 보고서를 만들고, 특정 ASR 규칙 감사 또는 차단 이벤트의 컨텍스트에 대한 자세한 정보를 얻을 수 있습니다.

ASR 규칙 이벤트는 디바이스의 고급 헌팅 섹션에 있는 DeviceEvents 테이블에서 Microsoft 365 Defender. 예를 들어 아래 쿼리와 같은 간단한 쿼리는 지난 30일 동안 ASR 규칙이 있는 모든 이벤트를 데이터 원본으로 보고하고 ActionType 수로 요약하여 요약할 수 있습니다. 이 경우 ASR 규칙의 실제 코드 이름입니다.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="고급 헌팅 쿼리.":::

:::image type="content" source="images/adv-hunt-sc-2new.png" lightbox="images/adv-hunt-sc-2new.png" alt-text="고급 헌팅 화면":::

고급 헌팅을 사용하면 쿼리를 원하는 내용에 따라 구성할 수 있으므로 개별 컴퓨터의 특정 정보를 파악하거나 전체 환경에서 정보를 추출하려는지 여부에 관계없이 쿼리가 진행될 수 있습니다.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>끝점 컴퓨터 타임라인용 Microsoft Defender

고급 헌팅 대신 더 좁은 범위의 끝점 컴퓨터 타임라인에 대한 Microsoft Defender가 있습니다. 디바이스의 수집된 모든 이벤트를 볼 수 있습니다. 지난 6개월 동안의 Microsoft 365 Defender 컴퓨터 목록으로 이동하여 특정 컴퓨터를 선택한 다음 시간 표시 막대 탭을 클릭합니다.

아래 그림은 주어진 끝점에서 이러한 이벤트의 시간 표시 막대 보기의 스크린샷입니다. 이 보기에서 오른쪽 창의 이벤트 그룹을 기준으로 이벤트 목록을 필터링할 수 있습니다. 경고를 보고 기록 타임라인을 스크롤하는 동안 Flagged 및 Verbose 이벤트를 활성화 또는 비활성화할 수도 있습니다.

:::image type="content" source="images/mic-sec-def-timelinenew.png" lightbox="images/mic-sec-def-timelinenew.png" alt-text="Microsoft 365 Defender 시간 표시 막대를 클릭합니다.":::

## <a name="how-to-troubleshoot-asr-rules"></a>ASR 규칙을 해결하는 방법

첫 번째로 가장 즉각적인 방법은 POWERShell cmdlet을 Windows ASR 규칙이 활성화된 디바이스에서 로컬로 검사하는 것입니다.

다음은 ASR 규칙의 영향 및 작동 문제를 해결하기 위해 Windows 정보를 제공하는 몇 가지 다른 소스입니다.

### <a name="querying-which-rules-are-active"></a>활성 상태인 규칙 쿼리

ASR 규칙이 이미 활성화되어 있는지 확인하는 가장 쉬운 방법 중 하나는 PowerShell cmdlet인 Get-MpPreference를 사용하는 것입니다.

다음은 예입니다.

:::image type="content" source="images/getmpreferencescriptnew.png" lightbox="images/getmpreferencescriptnew.png" alt-text="mppreference 스크립트를 얻습니다.":::

구성된 작업이 서로 다른 여러 ASR 규칙이 활성화됩니다.

ASR 규칙에 대한 위의 정보를 확장하기 위해 및/또는 에 대한 AttackSurfaceReductionRules_Ids **사용할** **AttackSurfaceReductionRules_Actions.**

예:

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids
```

:::image type="content" source="images/getmpref-examplenew.png" alt-text="mpreference 예제를 얻습니다.":::

위에는 0(구성되지 않은)의 설정이 있는 ASR 규칙의 모든 ID가 표시됩니다.

다음 단계에서는 각 규칙이 구성된 실제 작업(차단 또는 감사)을 나열합니다.

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions
```

:::image type="content" source="images/getmpref-example2new.png" alt-text="mppreference 예제2를 얻습니다.":::

### <a name="querying-blocking-and-auditing-events"></a>쿼리 차단 및 감사 이벤트

ASR 규칙 이벤트는 로그 내에서 볼 Windows Defender 있습니다.

액세스하려면 이벤트 뷰어를 Windows 열고 응용  프로그램 및 서비스 로그 Microsoft Windows Windows Defender \>  \>  \>  \> **를 탐색합니다.**

:::image type="content" source="images/eventviewerscrnew.png" lightbox="images/eventviewerscrnew.png" alt-text="이벤트 뷰어 스크러.":::

## <a name="microsoft-defender-antimalware-protection-logs"></a>Microsoft Defender 맬웨어 방지 보호 로그

또한 이라는 전용 명령줄 Microsoft Defender 바이러스 백신 통해 규칙 이벤트를 볼 수도 있습니다. 이 도구를 사용하여 필요한 경우 작업을 관리 및 구성하고 `*mpcmdrun.exe*` 자동화할 수 있습니다.

이 유틸리티는 *%ProgramFiles%\Windows Defender\MpCmdRun.exe.* 관리자 권한 명령 프롬프트(즉, 관리자 권한으로 실행)에서 실행해야 합니다.

지원 정보를 생성하기 위해 *-getfilesMpCmdRun.exe 입력합니다.* 잠시 후 여러 로그가 보관함(MpSupportFiles.cab)에 패키지되어 *C:\ProgramData\Microsoft\Windows Defender\Support 에서* 사용할 수 있습니다.

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="맬웨어 보호 로그.":::

해당 보관 파일을 추출하면 문제 해결을 위해 여러 파일을 사용할 수 있습니다.

가장 관련성이 높은 파일은 다음과 같습니다.

- **MPOperationalEvents.txt**: 이 파일에는 이벤트 뷰어에서 찾은 동일한 수준의 정보가 Windows Defender 로그에 포함되어 있습니다.
- **MPRegistry.txt:** 이 파일에서 지원 로그가 캡처된 Windows Defender 모든 현재 구성을 분석할 수 있습니다.
- **MPLog.txt**: 이 로그에는 로그의 모든 작업/작업에 대한 자세한 정보가 Windows Defender.
