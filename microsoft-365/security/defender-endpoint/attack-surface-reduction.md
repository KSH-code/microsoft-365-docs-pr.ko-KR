---
title: 공격 표면 감소 규칙을 사용하여 맬웨어 감염 방지
description: 공격 표면 감소 규칙은 악용이 앱 및 스크립트를 사용하여 장치를 맬웨어에 감염하는 것을 방지하는 데 도움이 될 수 있습니다.
keywords: 공격 표면 감소 규칙, asr, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 끝점용 Microsoft Defender
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 5392cf40a0d37e332d7b3bec260ab34e9a3a083e
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882444"
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
- Windows 11
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
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

  >[!NOTE]
  >Windows Server 2016 및 Windows Server 2012 R2는 이 기능이 작동하려면 Windows 서버의 [](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) 지침을 사용하여 온보드해야 합니다. 


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

이벤트 로그의 공격 표면 축소 이벤트에 대해 나열된 "엔진 버전"은 운영 체제가 아니라 Endpoint용 Defender에 의해 생성됩니다. Endpoint용 Defender는 Windows 10 및 Windows 11 통합되어 있으므로 이 Windows 10 또는 Windows 11 작동합니다.

## <a name="attack-surface-reduction-rules"></a>공격 노출 영역 축소 규칙

다음 표 및 하위 섹션에서는 16개 공격 표면 감소 규칙 각각에 대해 설명하고 있습니다. 공격 표면 감소 규칙은 규칙 이름에 따라 사전순으로 나열됩니다.

그룹 정책 또는 PowerShell을 사용하여 공격 표면 감소 규칙을 구성하는 경우 GUID가 필요합니다. 반면에 사용자 또는 Microsoft Endpoint Manager Microsoft Intune GUID가 필요하지 않습니다.

|규칙 이름|GUID|파일 & 제외|지원되는 최소 OS|
|---|:---:|---|---|
|[악용된 취약한 서명된 드라이버의 남용 차단](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11|
|[Adobe Reader에서 하위 프로세스를 만들지 차단](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11 <br>  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) <br> [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2) |
|[모든 Office 응용 프로그램에서 자식 프로세스를 만들지 차단](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11 <br> Windows Server 2016|
|[로컬 보안 기관 하위 Windows(lsass.exe)에서 자격 증명 도용 차단](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11 <br><br>  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) <br> [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)|
|[전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11 <br> Windows Server 2016 <br> Windows Server 2012 R2|
|[실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11|
|[잠재적으로 난치될 수 있는 스크립트의 실행 차단](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11 <br>  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) <br> [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2) |
|[JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11 <br> Windows Server 2016|
|[응용 Office 콘텐츠 만들기 차단](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11 <br> Windows Server 2016 <br> Windows Server 2012 R2 |
|[응용 Office 코드 삽입 차단](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11|
|[통신 Office 응용 프로그램에서 자식 프로세스를 만들지 차단](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11|
|[WMI 이벤트 구독을 통한 지속성 차단](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|지원되지 않음|[Windows 10 버전 1903(빌드](/windows/whats-new/whats-new-windows-10-version-1903) 18362) 이상 또는 Windows 11|
|[PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11 <br> <br>  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) <br> [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)
|
|[USB에서 실행된 무단 및 사인되지 않은 프로세스 차단](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11|
|[매크로에서 Win32 API Office 차단](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11|
|[랜섬웨어에 대한 고급 보호 사용](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|지원|[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상 또는 Windows 11 <br> <br>  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) <br> [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2) |
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>악용된 취약한 서명된 드라이버의 남용 차단

이 규칙은 응용 프로그램이 디스크에 취약한 서명된 드라이버를 작성하지 못하게 합니다. 와일드에서 취약한 서명된 드라이버는 커널에 액세스하기에 충분한 권한이 있는 로컬 응용 프로그램에 \-  \- 의해 악용될 수 있습니다. 취약한 서명된 드라이버를 사용하면 공격자가 보안 솔루션을 사용하지 않도록 설정하거나 우회할 수 있습니다. 결과적으로 시스템 손상이 일어날 수 있습니다.

**악용된** 취약한 드라이버 남용 차단 규칙은 시스템에 이미 있는 드라이버가 로드되는 것을 차단하지 않습니다.

>[!NOTE]
>
> MEM OMA-URI 사용자 지정 규칙의 프로시저 정보에 대해 [MEM OMA-URI를](enable-attack-surface-reduction.md#mem) 사용하여 이 규칙을 구성할 수 있습니다.
>
> PowerShell을 사용하여 이 규칙을 [구성할 수 있습니다.](enable-attack-surface-reduction.md#powershell)
>
> 드라이버를 검사하기 위해 이 웹 사이트를 사용하여 분석을 위해 [드라이버를 제출합니다.](https://www.microsoft.com/en-us/wdsi/driversubmission)

지원되는 운영 체제:

- [Windows 10 Pro 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- [Windows 10 Enterprise 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- [Windows Server, 버전 1803(반기 채널)](/windows-server/get-started/whats-new-in-windows-server-1803) 이상
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune 이름: `Block abuse of exploited vulnerable signed drivers`

GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

### <a name="block-adobe-reader-from-creating-child-processes"></a>Adobe Reader에서 하위 프로세스를 만들지 차단

이 규칙은 Adobe Reader가 프로세스를 만들지 못하게 차단하여 공격을 방지합니다.

소셜 엔지니어링 또는 악용을 통해 맬웨어는 페이로드를 다운로드 및 시작하고 Adobe Reader를 중단할 수 있습니다. Adobe Reader에서 자식 프로세스가 생성되지 않도록 차단하면 벡터로 사용하려는 맬웨어가 확산되지 않습니다.

지원되는 운영 체제:

- [Windows 10, 버전 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 이름: `Process creation from Adobe Reader (beta)`

Configuration Manager 이름: 아직 사용할 수 없습니다.

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>모든 Office 응용 프로그램에서 자식 프로세스를 만들지 차단

이 규칙은 Office 프로세스 만들기를 차단합니다. Office 앱에는 Word, Excel, PowerPoint, OneNote 및 Access가 포함됩니다.

악의적인 자식 프로세스를 만드는 것은 일반적인 맬웨어 전략입니다. 벡터로 Office 악용하는 맬웨어는 VBA 매크로를 실행하고 코드를 악용하여 더 많은 페이로드를 다운로드하고 실행하려고 합니다. 그러나 일부 합법적인 업무(LINE-OF-BUSINESS) 응용 프로그램에서는 자식 프로세스를 무해한 용도로 생성할 수도 있습니다. 명령 프롬프트를 만들거나 PowerShell을 사용하여 레지스트리 설정을 구성하는 등의 경우

지원되는 운영 체제:

- [Windows 10 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 이름: `Office apps launching child processes`

Configuration Manager 이름: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>로컬 보안 기관 하위 Windows 자격 증명 도용 차단

이 규칙은 LSASS(Local Security Authority Subsystem Service)를 잠가 자격 증명 도용을 방지하는 데 도움이 됩니다.

LSASS는 Windows 인증합니다. Microsoft Defender Credential Guard는 Windows 10 LSASS에서 자격 증명을 추출하려고 시도하지 않습니다. 그러나 일부 조직에서는 사용자 지정 스마트 카드 드라이버 또는 LSA(Local Security Authority)로 로드되는 다른 프로그램과의 호환성 문제로 인하여 모든 컴퓨터에서 Credential Guard를 사용하도록 설정할 수 없습니다. 이러한 경우 공격자는 Mimikatz와 같은 해킹 도구를 사용하여 LSASS에서 지우기 암호 및 NTLM 해시를 스크랩할 수 있습니다.

> [!NOTE]
> 일부 앱에서는 코드가 실행 중인 모든 프로세스를 열기하고 모든 사용 권한으로 열려고 시도합니다. 이 규칙은 앱의 프로세스 열기 작업을 거부하고 보안 이벤트 로그에 세부 정보를 기록합니다. 이 규칙은 노이즈를 많이 생성할 수 있습니다. LSASS를 열기만 하지만 기능에는 실질적인 영향을 미치는 앱이 있는 경우 제외 목록에 앱을 추가할 필요가 없습니다. 이 이벤트 로그 항목 자체는 악의적인 위협을 나타낼 필요는 없습니다.

지원되는 운영 체제:

- [Windows 10 버전 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 이름: `Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager 이름: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단

이 규칙은 Microsoft Outlook 응용 프로그램 또는 Outlook.com 및 기타 인기 있는 웹 메일 공급자에서 연 전자 메일에서 다음 파일 형식이 시작되지 Outlook 차단합니다.

- 실행 파일(예: .exe, .dll 또는 .scr)
- 스크립트 파일(예: PowerShell .ps, Visual Basic .vbs 또는 JavaScript .js 파일)

지원되는 운영 체제:

- [Windows 10 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 이름: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager 이름:`Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> 전자 **메일 클라이언트 및 웹** 메일에서 실행 가능한 콘텐츠 차단 규칙에는 사용하는 응용 프로그램에 따라 다음과 같은 대체 설명이 있습니다.
>
> - Intune(구성 프로필): 전자 메일(webmail/mail client)에서 삭제된 실행 가능한 콘텐츠(예: dll, ps, js, vbs 등)의 실행입니다(예외 없음).
> - Endpoint Manager: 전자 메일 및 웹 메일 클라이언트에서 실행 가능한 콘텐츠 다운로드를 차단합니다.
> - 그룹 정책: 전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠를 차단합니다.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단

이 규칙은 다음 조건이 충족되지 않는 한 .exe, .dll 또는 .scr과 같은 실행 파일이 시작되지 못하게 차단합니다.

- Prevalence: The executable files are found on more than 1,000 endpoints
- 사용 시간: 실행 파일이 24시간 이상 전에 릴리스되었습니다.
- 위치: 실행 파일이 신뢰할 수 있는 목록 또는 제외 목록에 포함됩니다.

파일이 악의적인 경우 처음에 명확하지 않을 수 있는 것으로 보아서, 트러블되지 않았거나 알 수 없는 실행 파일을 실행하는 것은 위험할 수 있습니다.

> [!IMPORTANT]
> 이 규칙을 [사용하려면](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 클라우드 제공 보호를 사용하도록 설정해야 합니다.
>
> GUID로 **보전,** 보존 기간 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단 규칙은 Microsoft가 소유하며 관리자가 `01443614-cd74-433a-b99e-2ecdc07bfc25` 지정하지 않습니다. 이 규칙은 클라우드 제공 보호를 사용하여 신뢰할 수 있는 목록을 정기적으로 업데이트합니다.
>
> 개별 파일 또는 폴더(폴더 경로 또는 정식 리소스 이름을 사용하여)를 지정할 수 있지만 적용할 규칙이나 제외를 지정할 수 없습니다.

지원되는 운영 체제:

- [Windows 10 버전 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune 이름: `Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager 이름: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>잠재적으로 난치될 수 있는 스크립트의 실행 차단

이 규칙은 난처한 스크립트 내에서 의심스러운 속성을 검색합니다.

스크립트 난동은 맬웨어 작성자와 합법적인 응용 프로그램이 지적 재산을 숨기거나 스크립트 로드 시간을 줄이는 데 사용하는 일반적인 기술입니다. 또한 맬웨어 작성자는 난독을 사용하여 악의적인 코드를 읽기 어렵게 하여 사람 및 보안 소프트웨어에 의해 가려질 수 없습니다.

지원되는 운영 체제:

- [Windows 10 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 이름: `Obfuscated js/vbs/ps/macro code`

Configuration Manager 이름: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단

이 규칙은 스크립트가 잠재적으로 악의적인 다운로드 콘텐츠를 시작하지 못하게 합니다. JavaScript 또는 VBScript로 작성된 맬웨어는 종종 다운로드자 역할을 하여 인터넷에서 다른 맬웨어를 페치하고 실행합니다.

일반적인 것은 아니며, 업무용 응용 프로그램에서는 스크립트를 사용하여 설치 관리자를 다운로드하고 실행하기도 합니다.

지원되는 운영 체제:

- [Windows 10 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)

Intune 이름: `js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager 이름: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>응용 Office 콘텐츠 만들기 차단

이 규칙은 word, Excel 및 PowerPoint 등의 Office 앱이 악성 코드가 디스크에 기록되지 않도록 차단하여 잠재적으로 악의적인 실행 콘텐츠를 만들지 못하게 합니다.

벡터로 Office 악용하는 맬웨어는 악의적인 구성 요소를 Office 디스크에 저장하려고 할 수 있습니다. 이러한 악성 구성 요소는 컴퓨터 재부팅에서 유지되고 시스템에서 지속됩니다. 따라서 이 규칙은 일반적인 지속성 기술에 대해 방어합니다.

지원되는 운영 체제:

- [Windows 10 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [](/configmgr/core/servers/manage/updates) System Center Configuration Manager(SCCM) CB 1710(SCCM이 현재 Microsoft Endpoint Configuration Manager)

Intune 이름: `Office apps/macros creating executable content`

SCCM 이름: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>응용 Office 코드 삽입 차단

이 규칙은 앱을 다른 프로세스로 Office 코드 삽입 시도를 차단합니다.

공격자는 앱의 Office 사용하여 코드 삽입을 통해 악성 코드를 다른 프로세스로 마이그레이션하려고 시도할 수 있으므로 코드가 깔끔한 프로세스로 악의적으로 처리될 수 있습니다.

코드 삽입을 사용하는 데 알려진 합법적인 비즈니스 목적이 없습니다.

이 규칙은 Word, Excel 및 PowerPoint.

지원되는 운영 체제:

- [Windows 10 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 이름: `Office apps injecting code into other processes (no exceptions)`

Configuration Manager 이름: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>통신 Office 응용 프로그램에서 자식 프로세스를 만들지 차단

이 규칙은 Outlook 자식 프로세스를 만들지 못하게 하지만 합법적인 Outlook 합니다.

이 규칙은 사회 엔지니어링 공격으로부터 보호하고 코드 악용을 통해 보안상 취약성을 악용하지 Outlook. 또한 사용자의 자격 [Outlook](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) 공격자가 사용할 수 있는 규칙 및 양식 악용으로부터 보호합니다.

> [!NOTE]
> 이 규칙은 규칙에 따라 DLP 정책 팁과 도구 Outlook. 이 규칙은 Outlook Outlook.com에만 적용됩니다.

지원되는 운영 체제:

- [Windows 10, 버전 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune 이름: `Process creation from Office communication products (beta)`

Configuration Manager 이름: 사용할 수 없습니다.

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>WMI 이벤트 구독을 통한 지속성 차단

이 규칙은 맬웨어가 WMI를 부인하여 디바이스에서 지속성에 이를 수 없습니다.

> [!IMPORTANT]
> 파일 및 폴더 제외는 이 공격 표면 축소 규칙에 적용되지 않습니다.

파일 없는 위협은 다양한 방법을 사용하여 숨김을 유지하여 파일 시스템에서 볼 수 없는 것을 방지하고 주기적인 실행 제어를 얻습니다. 일부 위협은 WMI 리포지토리 및 이벤트 모델을 남용하여 숨길 수 있습니다.

지원되는 운영 체제:

- [Windows 10 버전 1903](/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Server 1903](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Intune 이름: 사용할 수 없습니다.

Configuration Manager 이름: 사용할 수 없습니다.

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단

이 규칙은 [PsExec](/sysinternals/downloads/psexec) 및 [WMI를](/windows/win32/wmisdk/about-wmi) 통해 만든 프로세스의 실행을 차단합니다. PsExec과 WMI 모두 코드를 원격으로 실행할 수 있으므로 맬웨어가 명령 및 제어 목적으로 이 기능을 남용하거나 조직의 네트워크 전체에 감염을 전파할 위험이 있습니다.

> [!WARNING]
> [Intune](/intune) 또는 다른 MDM 솔루션으로 장치를 관리하는 경우 이 규칙만 사용 이 규칙은 Configuration Manager 클라이언트가 올바르게 Microsoft Endpoint Configuration Manager WMI 명령을 차단하기 때문에 이 규칙은 관리자를 [통해](/configmgr) 관리와 비호환합니다.

지원되는 운영 체제:

- [Windows 10 버전 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 이름: `Process creation from PSExec and WMI commands`

Configuration Manager 이름: 해당되지 않습니다.

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>USB에서 실행된 무단 및 사인되지 않은 프로세스 차단

이 규칙을 사용하여 관리자는 SD 카드를 포함하여 USB 이동식 드라이브에서 사인되지 않은 실행 파일 또는 트러블된 실행 파일을 실행하지 못하게 할 수 있습니다. 차단된 파일 형식에는 실행 파일(예: .exe, .dll 또는 .scr)이 포함됩니다.

지원되는 운영 체제:

- [Windows 10 버전 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune 이름: `Untrusted and unsigned processes that run from USB`

Configuration Manager 이름: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>매크로에서 Win32 API Office 차단

이 규칙은 VBA 매크로가 Win32 API를 호출하지 못하게 합니다.

Office VBA는 Win32 API 호출을 가능하게 합니다. 맬웨어는 [Win32 API를](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) 호출하여 디스크에 직접 아무것도 쓰지 않고 악성 셸 코드를 시작하는 등 이 기능을 남용할 수 있습니다. 대부분의 조직에서는 다른 방법으로 매크로를 사용하는 경우에도 매일 작동할 때 Win32 API를 호출하는 기능을 사용하지 않습니다.

지원되는 운영 체제:

- [Windows 10 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 이름: `Win32 imports from Office macro code`

Configuration Manager 이름: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>랜섬웨어에 대한 고급 보호 사용

이 규칙은 랜섬웨어에 대한 추가 보호 계층을 제공합니다. 클라이언트와 클라우드추론을 모두 사용하여 파일이 랜섬웨어와 같은지 여부를 판단합니다. 이 규칙은 다음 특성 중 하나 이상이 있는 파일을 차단하지 않습니다.

- 파일이 Microsoft 클라우드에서 이미 손상되지 않은 것으로 발견된 경우
- 파일이 유효한 서명된 파일입니다.
- 이 파일은 랜섬웨어로 간주되지 않을 정도로 보전됩니다.

규칙은 랜섬웨어를 방지하기 위해 신중하게 진행되는 경향이 있습니다.

> [!NOTE]
> 이 규칙을 [사용하려면](enable-cloud-protection-microsoft-defender-antivirus.md) 클라우드 제공 보호를 사용하도록 설정해야 합니다.

지원되는 운영 체제:

- [Windows 10 버전 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 이름: `Advanced ransomware protection`

Configuration Manager 이름: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`
