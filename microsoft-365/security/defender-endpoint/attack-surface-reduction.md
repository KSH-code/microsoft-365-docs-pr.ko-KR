---
title: 공격 표면 감소 규칙을 사용하여 맬웨어 감염 방지
description: 공격 표면 감소 규칙은 악용이 앱 및 스크립트를 사용하여 장치를 맬웨어에 감염하는 것을 방지하는 데 도움이 될 수 있습니다.
keywords: 공격 표면 감소 규칙, asr, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 402ae897717e935b59f0f63a48f7307a2ff522e4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222043"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>공격 표면 감소 규칙을 사용하여 맬웨어 감염 방지

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>공격 표면 감소 규칙이 중요한 이유

조직의 공격 표면에는 공격자가 조직의 장치 또는 네트워크를 손상시킬 수 있는 모든 위치가 포함됩니다. 공격 표면을 줄이는 것은 조직의 장치와 네트워크를 보호하는 것을 의미하며, 공격자는 공격을 더 적은 방법으로 수행할 수 있습니다. 끝점용 Microsoft Defender에서 공격 표면 감소 규칙을 구성하면 도움이 될 수 있습니다!

공격 표면 감소 규칙은 다음과 같은 특정 소프트웨어 동작을 대상으로 합니다.

- 파일 다운로드 또는 실행을 시도하는 실행 파일 및 스크립트 실행
- 난동 또는 기타 의심스러운 스크립트 실행
- 앱이 일반적인 일과의 작업 중에 일반적으로 시작되지 않는 동작 수행

이러한 소프트웨어 동작은 경우에 따라 합법적인 응용 프로그램에서 볼 수 있습니다. 그러나 이러한 동작은 일반적으로 맬웨어를 통해 공격자에 의해 악용되는 위험한 동작으로 간주됩니다. 공격 표면 감소 규칙은 소프트웨어 기반의 위험한 동작을 제한하고 조직을 안전하게 유지하는 데 도움이 될 수 있습니다.

공격 표면 감소 규칙을 구성하는 방법에 대한 자세한 내용은 공격 표면 감소 규칙 사용 [을 참조하세요.](enable-attack-surface-reduction.md)

## <a name="assess-rule-impact-before-deployment"></a>배포 전에 규칙 영향 평가

에서 해당 규칙에 대한 보안 권장을 열면 공격 표면 감소 규칙이 네트워크에 어떤 [영향을 줄 수](/windows/security/threat-protection/#tvm)위협 및 취약성 관리.

:::image type="content" source="images/asrrecommendation.png" alt-text="공격 표면 감소 규칙에 대한 보안 재코입니다.":::

권장 사항 세부 정보 창에서 사용자 영향을 확인하여 생산성에 부정적인 영향을 주지 않으면서 차단 모드에서 규칙을 사용하도록 설정하는 새 정책을 허용할 수 있는 장치의 비율을 결정할 수 있습니다.

[지원되는](enable-attack-surface-reduction.md#requirements) 운영 체제 및 추가 요구 사항에 대한 자세한 내용은 "공격 표면 감소 규칙 사용" 문서의 요구 사항을 참조하세요.

## <a name="audit-mode-for-evaluation"></a>평가를 위한 감사 모드

감사 [모드를 사용하여](audit-windows-defender.md) 공격 표면 감소 규칙이 사용하도록 설정된 경우 조직에 어떤 영향을 주는지 평가합니다. 모든 규칙을 먼저 감사 모드에서 실행하여 해당 규칙이 업무(LINE-OF-BUSINESS) 응용 프로그램에 미치는 영향을 이해할 수 있습니다. 많은 기간 업무(기간 업무) 응용 프로그램은 제한된 보안 문제로 작성되어 맬웨어와 유사한 방식으로 작업을 수행할 수 있습니다. 감사 데이터를 모니터링하고 [](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 필요한 응용 프로그램에 대한 제외를 추가하면 생산성을 줄이지 않고 공격 표면 감소 규칙을 배포할 수 있습니다.

## <a name="warn-mode-for-users"></a>사용자에 대한 경고 모드

(**NEW**!) 경고 모드 기능 이전에 사용하도록 설정된 공격 표면 감소 규칙을 감사 모드 또는 차단 모드로 설정할 수 있습니다. 새 경고 모드를 사용하면 콘텐츠가 공격 표면 축소 규칙에 의해 차단되면 콘텐츠가 차단된 것 을 나타내는 대화 상자가 표시됩니다. 또한 이 대화 상자에서는 콘텐츠 차단을 해제할 수 있는 옵션도 제공합니다. 그러면 사용자가 작업을 다시 시도할 수 있으며 작업이 완료됩니다. 사용자가 콘텐츠 차단을 해제하면 콘텐츠가 24시간 동안 차단되지 않은 상태로 유지된 다음 다시 시작을 차단합니다.

경고 모드는 사용자가 작업을 수행하는 데 필요한 콘텐츠에 액세스하지 못하게 하여 조직이 공격 표면 감소 규칙을 적용하는 데 도움이 됩니다.

### <a name="requirements-for-warn-mode-to-work"></a>작동 경고 모드에 대한 요구 사항

경고 모드는 다음 버전의 경고를 실행하는 장치에서 Windows.

- [Windows 10, 버전 1809](/windows/whats-new/whats-new-windows-10-version-1809) 이상
- [Windows Server, 버전 1809 이상](/windows-server/get-started/whats-new-in-windows-server-1809)

Microsoft Defender 바이러스 백신 활성 모드에서 실시간 보호를 통해 [실행해야 합니다.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)

또한 맬웨어 [방지 Microsoft Defender 바이러스 백신 설치해야](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) 합니다.

- 최소 플랫폼 릴리스 요구 사항: `4.18.2008.9`
- 최소 엔진 릴리스 요구 사항: `1.1.17400.5`

자세한 내용은 Microsoft Defender 맬웨어 방지 플랫폼에 대한 업데이트를 [참조하세요.](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)

### <a name="cases-where-warn-mode-is-not-supported"></a>경고 모드가 지원되지 않는 경우

경고 모드는 3가지 공격 표면 감소 규칙에서 구성할 때 지원되지 Microsoft Endpoint Manager. (그룹 정책을 사용하여 공격 표면 축소 규칙을 구성하는 경우 경고 모드가 지원됩니다.) 경고 모드에서 구성할 때 경고 모드를 지원하지 않는 세 가지 규칙은 Microsoft Endpoint Manager 같습니다.

- [JavaScript 또는 VBScript에서 다운로드한](attack-surface-reduction-rules.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content) 실행 콘텐츠(GUID)를 시작하지 차단 `d3e037e1-3eb8-44c8-a917-57927947596d`
- [WMI 이벤트 구독(GUID)을 통한](attack-surface-reduction-rules.md#block-persistence-through-wmi-event-subscription) 지속성 `e6db77e5-3df2-4cf1-b95a-636979351e5b` 차단
- [랜섬웨어에 대한](attack-surface-reduction-rules.md#use-advanced-protection-against-ransomware) 고급 보호 사용(GUID) `c1db55ab-c21a-4637-bb3f-a12568109d35`

또한 이전 버전의 에지 버전을 실행하는 장치에서는 경고 모드가 지원되지 Windows. 이러한 경우 경고 모드에서 실행하도록 구성된 공격 표면 감소 규칙은 차단 모드에서 실행됩니다.

## <a name="notifications-and-alerts"></a>알림 및 경고

공격 표면 감소 규칙이 트리거될 때마다 알림이 장치에 표시됩니다. 회사 세부 정보 및 연락처 정보로 [알림을 사용자 지정](customize-attack-surface-reduction.md#customize-the-notification)할 수 있습니다.

또한 특정 공격 표면 감소 규칙이 트리거되면 경고가 생성됩니다.

알림 및 생성된 경고는 Microsoft 365 Defender 포털()(이전의 Microsoft 365 Defender)에서 볼 [https://security.microsoft.com](https://security.microsoft.com) [수 있습니다.](microsoft-defender-security-center.md)

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>고급 헌팅 및 공격 표면 축소 이벤트

고급 헌팅을 사용하여 공격 표면 감소 이벤트를 볼 수 있습니다. 들어오는 데이터의 양을 간소화하기 위해 고급 헌팅을 통해 각 시간의 고유한 프로세스만 볼 수 있습니다. 공격 범위 축소 이벤트의 시간은 이벤트가 시간 내에 처음으로 나타났습니다.

예를 들어 오후 2시 동안 10대의 장치에서 공격 표면 감소 이벤트가 발생했다고 가정해 보겠습니다. 첫 번째 이벤트가 2:15에 발생하고 마지막 2:45에 발생했다고 가정합니다. 고급 헌팅을 사용하면 실제로 10대의 장치에서 발생한 경우에도 해당 이벤트의 인스턴스가 하나씩 표시될 수 있으며 타임스탬프는 오후 2시 15분입니다.

고급 헌팅에 대한 자세한 내용은 고급 헌팅으로 위협을 사전 [대응적으로 헌팅을 참조하세요.](advanced-hunting-overview.md)

## <a name="attack-surface-reduction-features-across-windows-versions"></a>여러 버전에서 공격 Windows 기능

다음 버전 및 버전의 디바이스를 실행하는 장치에 대해 공격 표면 감소 규칙을 설정할 수 Windows.

- Windows 10 Pro 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- Windows 10 Enterprise 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- Windows 서버, [버전 1803(반기 채널)](/windows-server/get-started/whats-new-in-windows-server-1803) 이상
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

공격 표면 감소 규칙에는 Windows E5 라이선스가 필요하지 않습니다. [E5를](/windows/deployment/deploy-enterprise-licenses)Windows 고급 관리 기능을 사용할 수 있습니다. E5에서만 사용할 수 있는 고급 Windows 포함:

- [Endpoint용 Defender에서](microsoft-defender-endpoint.md) 사용할 수 있는 모니터링, 분석 및 워크플로
- 의 보고 및 구성 [Microsoft 365 Defender.](/microsoft-365/security/defender/overview-security-center)

이러한 고급 기능은 E3 라이선스 또는 Windows Professional Windows 없습니다. 그러나 해당 라이선스가 있는 경우 이벤트 뷰어 및 로그를 사용하여 Microsoft Defender 바이러스 백신 축소 규칙 이벤트를 검토할 수 있습니다.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>포털에서 공격 표면 감소 Microsoft 365 Defender 검토

Endpoint용 Defender는 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 차단합니다.

고급 헌팅을 사용하여 에서 Defender에서 [끝점 Microsoft 365 Defender](microsoft-defender-security-center.md) [쿼리할 수 있습니다.](advanced-hunting-query-language.md) 감사 모드를 실행하는 [](audit-windows-defender.md)경우 고급 헌팅을 사용하여 공격 표면 감소 규칙이 환경에 미칠 수 있는 영향을 이해할 수 있습니다.

다음은 예제 쿼리입니다.

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>이벤트 뷰어에서 공격 Windows 검토

다음과 같은 Windows 로그를 검토하여 공격 표면 감소 규칙에 의해 생성된 이벤트를 볼 수 있습니다.

1. 평가 [패키지를](https://aka.ms/mp7z2w) 다운로드하고  디바이스에서cfa-events.xml쉽게 액세스할 수 있는 위치에 파일을 추출합니다.

2. 이벤트 뷰어를 시작 메뉴 이벤트 뷰어에 Windows 입력합니다. 

3. **작업에서** 사용자 지정 보기 **가져오기... 를 선택합니다.**

4. 추출된 *cfa-events.xml* 파일을 선택합니다. 또는 [XML을 직접 복사합니다.](event-views.md)

5. **확인** 을 선택합니다.

이벤트를 필터로 지정하여 제어된 폴더 액세스와 관련된 다음 이벤트만 표시하는 사용자 지정 보기를 만들 수 있습니다.

|이벤트 ID|설명|
|---|---|
|5007|설정이 변경될 때의 이벤트|
|1121|차단 모드에서 규칙이 발생하면 이벤트|
|1122|감사 모드에서 규칙이 발생하면 이벤트|

이벤트 로그의 공격 표면 축소 이벤트에 대해 나열된 "엔진 버전"은 운영 체제가 아니라 Endpoint용 Defender에 의해 생성됩니다. Endpoint용 Defender는 Windows 10 통합되어 있으므로 이 Windows 10 설치된 모든 장치에서 작동합니다.
