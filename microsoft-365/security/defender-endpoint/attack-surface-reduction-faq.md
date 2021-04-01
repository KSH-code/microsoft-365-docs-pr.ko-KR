---
title: 공격 표면 감소 자주 묻는 질문(FAQ)
description: Microsoft Defender ATP의 공격 표면 축소 규칙에 대한 질문과 대답을 찾아보십시오.
keywords: 공격 표면 감소 규칙, asr, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 71c3f89b721039753709d65daa135cad74a81711
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476469"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>공격 표면 감소 자주 묻는 질문(FAQ)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037) 
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>Windows의 ASR(공격 표면 축소) 부분이 있나요?

ASR은 원래 Windows 10 버전 1709에서 Microsoft Defender 바이러스 백신의 주요 업데이트로 도입된 Exploit Guard 기능 제품군의 기능입니다. Microsoft Defender 바이러스 백신은 Windows의 기본 맬웨어 방지 구성 요소입니다. 그러나 전체 ASR 기능 집합은 Windows 엔터프라이즈 라이선스에서만 사용할 수 있습니다. 또한 ASR 규칙 제외는 Microsoft Defender 바이러스 백신 제외와 별도로 관리됩니다.

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>ASR 규칙을 실행하려면 엔터프라이즈 라이선스가 필요한가요?

전체 ASR 규칙 및 기능 집합은 Windows 10용 엔터프라이즈 라이선스가 있는 경우만 지원됩니다. 엔터프라이즈 라이선스 없이 제한된 수의 규칙이 작동할 수 있습니다. Microsoft 365 Business가 있는 경우 Microsoft Defender 바이러스 백신을 기본 보안 솔루션으로 설정하고 PowerShell을 통해 규칙을 사용하도록 설정하십시오. 엔터프라이즈 라이선스 없이 ASR을 사용하는 것은 공식적으로 지원되지 않고 ASR의 모든 기능을 사용할 수 없습니다.

Windows 라이선스에 대한 자세한 내용은 Windows 10 라이선스를 참조하고 Windows [10용](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) 볼륨 라이선스 [가이드를 참조하세요.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>E3 라이선스가 있는 경우 ASR이 지원하나요?

예. ASR은 Windows Enterprise E3 이상에서 지원됩니다. 

## <a name="which-features-are-supported-with-an-e5-license"></a>E5 라이선스에서 지원되는 기능은 무엇입니까?

E3에서 지원되는 모든 규칙은 E5에서도 지원됩니다.

E5는 끝점용 Defender와의 통합을 강화합니다. E5를 사용하면 실시간으로 경고를 보고, 규칙 제외를 미세 조정하고, ASR 규칙을 구성하고, 이벤트 보고서 목록을 볼 수 있습니다.

## <a name="what-are-the-currently-supported-asr-rules"></a>현재 지원되는 ASR 규칙은 무엇입니까?
ASR은 현재 아래의 모든 규칙을 지원하고 있습니다.

## <a name="what-rules-to-enable-all-or-can-i-turn-on-individual-rules"></a>어떤 규칙을 사용하도록 설정해야 하나요? 모두 또는 개별 규칙을 켜도 하나요?
환경에 가장 적합한 기능을 알아내기 위해 감사 모드에서 ASR 규칙을 사용하도록 [설정하는 것이 좋습니다.](audit-windows-defender.md) 이 방법을 사용하면 조직에 미칠 수 있는 영향을 확인할 수 있습니다. 예를 들어 업무용 응용 프로그램을 들 수 있습니다.

## <a name="how-do-asr-rules-exclusions-work"></a>ASR 규칙 제외는 어떻게 작동하나요?
ASR 규칙의 경우 제외를 하나 추가하면 모든 ASR 규칙에 영향을 미치게 됩니다.
다음 두 가지 특정 규칙은 제외를 지원하지 않습니다.

|규칙 이름|GUID|파일 & 제외|
|:--|:--|:--|
|JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단|D3E037E1-3EB8-44C8-A917-57927947596D|지원되지 않음|
|WMI 이벤트 구독을 통한 지속성 차단|e6db77e5-3df2-4cf1-b95a-636979351e5b|지원되지 않음|

ASR 규칙 제외는 와일드카드, 경로 및 환경 변수를 지원합니다. ASR 규칙에서 와일드카드를 사용하는 방법에 대한 자세한 내용은 파일 확장명 및 폴더 위치에 따라 제외 구성 및 유효성 검사를 [참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus)

ASR 규칙 제외(와일드카드 및 env 포함)에 대한 다음 항목을 알고 있어야 합니다. 변수:

- ASR 규칙 제외는 Defender AV 제외와는 독립적입니다.
- 와일드카드를 사용하여 드라이브 문자를 정의할 수 없습니다.
- 여러 폴더를 제외하려는 경우 경로에서 \의 여러 인스턴스를 사용하여 여러 중첩된 폴더를 \* 나타냅니다(예: c:\Folder \* \* \Test).
- Microsoft Endpoint Configuration *Manager는* 와일드카드(* 또는 ?)를 지원하지 않습니다.
- 임의의 문자(자동화된 파일 생성)가 포함된 파일을 제외하려는 경우 '?' 기호(예: C:\Folder\fileversion?)를 사용할 수 있습니다. docx)
- 그룹 정책의 ASR 제외는 따옴표를 지원하지 않습니다. 엔진은 긴 경로, 공백 등을 기본적으로 처리하기 때문에 따옴표를 사용할 필요가 없습니다.
- ASR 규칙은 NT AUTHORITY\SYSTEM 계정으로 실행되어 환경 변수가 컴퓨터 변수로 제한됩니다.



## <a name="how-do-i-know-what-i-need-to-exclude"></a>제외해야 하는 대상을 어떻게 알 수 있나요?
ASR 규칙마다 보호 흐름이 다릅니다. 구성하는 ASR 규칙이 어떤 것을 방지할지와 실제 실행 흐름이 어떻게 이동하는지 항상 생각해 보아야 합니다.

예: LSASS(Local Security Authority Subsystem) 프로세스에서 직접 읽은 **Windows** 로컬 보안 기관 하위 체제에서 자격 증명 도용을 차단하면 회사 자격 증명이 노출될 수 때문에 보안상 위험할 수 있습니다.

이 규칙은 트러버설이 없는 프로세스가 LSASS 메모리에 직접 액세스할 수 없습니다. 프로세스가 OpenProcess() 함수를 사용하여 LSASS에 액세스하는 경우 액세스 권한이 PROCESS_VM_READ 규칙은 해당 액세스 권한을 특별히 차단합니다.

:::image type="content" source="images/asrfaq1.png" alt-text="LSASS를 도용하는 자격 증명 차단":::

위의 예에서 액세스 권한이 차단된 프로세스에 대한 예외를 만들어야 하는 경우 전체 경로와 함께 파일 이름을 추가하면 차단되지 않습니다. 그리고 LSASS 프로세스 메모리에 액세스할 수 있도록 허용된 후에 파일 이름을 추가합니다. 값이 0이면 ASR 규칙이 이 파일/프로세스를 무시하고 이를 차단/감사하지 않습니다.

:::image type="content" source="images/asrfaq2.png" alt-text="파일 asr 제외":::

## <a name="what-are-the-rules-microsoft-recommends-enabling"></a>Microsoft에서 사용하도록 설정하는 데 권장하는 규칙은 무엇입니까?

가능한 모든 규칙을 사용하도록 설정하는 것이 좋습니다. 그러나 규칙을 사용하도록 설정하지 않는 경우도 있습니다. 예를 들어 Microsoft Endpoint Configuration Manager(또는 System Center Configuration Manager - SCCM)를 사용하여 끝점을 관리하는 경우 PSExec 및 WMI 명령 규칙에서 시작된 프로세스 만들기 차단을 사용하도록 설정하지 않는 것이 좋습니다.

공용 설명서에서 사용할 수 있는 각 규칙 관련 정보 및/또는 경고를 읽어보는 [것이 좋습니다.](/microsoft-365/security/defender-endpoint/attack-surface-reduction.md)
Office, 자격 증명, 스크립트, 전자 메일 등 여러 보호 기조에 걸쳐 있습니다. WMI 이벤트 구독을 통한 지속성 차단을 제외한 모든 ASR 규칙은 Windows 1709 이상에서 지원됩니다.

* [전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [모든 Office 응용 프로그램에서 하위 프로세스를 만들지 차단](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [Office 응용 프로그램에서 실행 가능한 콘텐츠를 만들지 차단](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [Office 응용 프로그램에서 다른 프로세스에 코드를 삽입하지 차단](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [잠재적으로 난치될 수 있는 스크립트의 실행 차단](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [Office 매크로에서 Win32 API 호출 차단](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [랜섬웨어에 대한 고급 보호 사용](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [Windows 로컬](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) 보안 기관 하위 체제에서 자격 증명 도용 차단(lsass.exe)
* [PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [USB에서 실행된 무단 및 사인되지 않은 프로세스 차단](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 조건을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [Office 통신 응용 프로그램에서 하위 프로세스를 만들지 차단](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [Adobe Reader에서 하위 프로세스를 만들지 차단](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [WMI 이벤트 구독을 통한 지속성 차단](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>ASR을 시작하기 위한 몇 가지 좋은 권장 사항은 무엇입니까?

잠시 동안 감사 모드에서 ASR 규칙을 실행하여 ASR 규칙이 조직에 미치는 영향을 테스트합니다. 감사 모드에서 규칙을 실행하는 동안 오로지 차단될 수 있는 모든 업무용 응용 프로그램을 식별하고 ASR에서 제외할 수 있습니다.

대규모 조직에서는 점점 더 광범위한 장치의 하위 집합에서 규칙을 감사하고 사용하도록 설정하여 "링"에서 ASR 규칙을 롤아웃하는 것이 고려해야 합니다. Intune 또는 그룹 정책 관리 도구를 사용하여 조직의 장치를 링으로 정렬할 수 있습니다.

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>ASR 규칙을 사용하도록 설정하기 전에 감사 모드에서 테스트해야 하는 기간은 얼마나 하나요?

규칙이 조직 전체에서 작동하면 규칙이 작동하는 방식에 대한 좋은 기준을 얻기 위해 약 30일 동안 감사 모드로 유지하십시오. 감사 기간 동안 규칙에 의해 차단될 수 있는 기간 업무(기간 업무) 응용 프로그램을 식별하고 제외하도록 규칙을 구성할 수 있습니다.

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>타사 보안 솔루션에서 끝점용 Defender로 전환하고 있습니다. 다른 보안 솔루션에서 ASR로 규칙을 내보내는 "쉬운" 방법이 있나요?

대부분의 경우 다른 보안 솔루션에서 규칙을 가져오는 것보다 [Endpoint용 Defender가](https://docs.microsoft.com/windows/security/threat-protection) 제안한 기준 권장 사항부터 시작하는 것이 더 쉽고 좋습니다. 그런 다음 감사 모드, 모니터링 및 분석과 같은 도구를 사용하여 고유한 요구 사항에 맞게 새 솔루션을 구성합니다. 

끝점의 실시간 보호를 위한 Defender와 결합된 대부분의 ASR 규칙에 대한 기본 구성은 많은 악용 및 취약성으로부터 보호합니다.

끝점용 Defender 내에서 사용자 지정 표시기를 사용하여 방어를 업데이트하여 특정 소프트웨어 동작을 허용하고 차단할 수 있습니다. ASR을 사용하면 파일 및 폴더 제외 형식의 규칙을 일부 사용자 지정할 수도 있습니다. 일반적으로는 특정 기간 동안 규칙을 감사하고 차단될 수 있는 기간 업무(LINE-OF-BUSINESS) 응용 프로그램에 대해 제외를 구성하는 것이 가장 좋은 규칙입니다.

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>ASR은 경로에 시스템 변수와 와일드카드를 포함 하는 파일 또는 폴더 제외를 지원 합니까?

예. ASR 규칙에서 파일 또는 폴더를 제외하는 데 대한 자세한 내용은 [ASR](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 규칙에서 파일 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 및 폴더 제외를 참조하고 제외된 파일 경로에서 시스템 변수 및 와일드카드를 사용하는 방법을 자세히 확인하려면 파일 확장명 및 폴더 위치에 따라 제외 구성 및 유효성 검사를 참조하세요.

## <a name="do-asr-rules-cover-all-applications-by-default"></a>ASR 규칙은 기본적으로 모든 응용 프로그램을 지원하나요?

규칙에 따라 다를 수 있습니다. 대부분의 ASR 규칙은 Word Microsoft Office Excel, PowerPoint, OneNote 또는 Outlook과 같은 모든 제품 및 서비스의 동작을 다룰 수 있습니다. 잠재적으로 난치될 수 있는 스크립트의 실행 차단과 같은 특정 ASR 규칙은 범위에서 더 일반적입니다.

## <a name="does-asr-support-third-party-security-solutions"></a>ASR에서 타사 보안 솔루션을 지원하나요?

ASR은 Microsoft Defender 바이러스 백신을 사용하여 응용 프로그램을 차단합니다. 현재 차단을 위해 다른 보안 솔루션을 사용하도록 ASR을 구성할 수 없습니다.

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>E5 라이선스가 있으며 끝점용 Defender와 함께 일부 ASR 규칙을 사용하도록 설정한 경우 끝점의 이벤트 타임라인에 대한 Defender에 ASR 이벤트가 모두 표시되지 않을 수 있나요?

ASR 규칙에 의해 로컬로 알림이 트리거될 때마다 이벤트에 대한 보고서도 끝점용 Defender 포털로 전송됩니다. 이벤트를 찾는 데 문제가 있는 경우 검색 상자를 사용하여 이벤트 타임라인을 필터링할 수 있습니다. 보안 센터 작업 표시줄의 구성 관리 아이콘에서 공격  표면 관리로 이동을 방문하여 ASR 이벤트를 볼 수 있습니다. 공격 표면 관리 페이지에는 끝점용 Defender에 보고된 ASR 규칙 이벤트의 전체 목록을 포함하는 보고서 검색용 탭이 포함되어 있습니다.

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>GPO를 사용하여 규칙을 적용한 경우 이제 Microsoft Outlook에서 규칙의 인덱싱 옵션을 확인하려고 할 때 '액세스 거부'를 표시하는 메시지가 표시됩니다.

Windows 10에서 직접 인덱싱 옵션을 하세요.

1. Windows **작업 표시줄에서** 검색 아이콘을 선택합니다.

1. 검색 **상자에 인덱싱** 옵션을 입력합니다.

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>규칙에서 "실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단" 규칙에서 사용하는 조건이 관리자가 구성할 수 있나요?

아니요. 이 규칙에 사용되는 기준은 Microsoft 클라우드 보호에서 유지 관리하여 신뢰할 수 있는 목록을 전 세계에서 수집된 데이터로 지속적으로 최신으로 유지할 수 있습니다. 로컬 관리자는 이 데이터를 변경할 수 있는 쓰기 권한이 없습니다. 엔터프라이즈에 맞게 이 규칙을 구성하는 경우 규칙이 트리거되지 않도록 제외 목록에 특정 응용 프로그램을 추가할 수 있습니다.

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>보전, 보존 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 ASR 규칙, 실행 파일 실행 차단을 *사용하도록 설정했습니다.* 시간이 지난 후 소프트웨어 일부를 업데이트했지만 규칙은 이전이 아니어도 이를 차단하고 있습니다. 문제가 있나요?

이 규칙은 신뢰할 수 있는 앱 목록에 보전, 연령 또는 포함으로 측정된 알려진 신뢰도의 각 응용 프로그램에 의존합니다. 응용 프로그램을 차단하거나 허용하는 규칙의 결정은 궁극적으로 Microsoft 클라우드 보호의 이러한 기준 평가에 따라 결정됩니다.

일반적으로 클라우드 보호는 새 버전의 응용 프로그램이 이전 버전과 충분히 유사하여 긴 시간으로 다시할 필요가 없다고 결정할 수 있습니다. 그러나 특히 주요 업데이트 후 버전을 전환한 후 앱이 신뢰도 구축에 다소 시간이 걸릴 수 있습니다. 그동안 제외 목록에 응용 프로그램을 추가하여 이 규칙이 중요한 응용 프로그램을 차단하지 못하게 할 수 있습니다. 새 버전의 응용 프로그램을 자주 업데이트하고 사용하는 경우 이 규칙을 감사 모드에서 실행하기로 선택할 수 있습니다.

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>최근에 ASR 규칙인 Windows 로컬 보안 기관 하위 lsass.exe(자격 증명 도용 *차단)를* 사용하도록 설정하고 많은 알림을 받고 있습니다. 무슨 일이 일어나고 있나요?

이 규칙에 의해 생성된 알림이 악의적인 활동을 나타낼 필요는 없습니다. 그러나 이 규칙은 악의적인 활동을 차단하는 데 여전히 유용합니다. 맬웨어는 종종 계정에 대한 lsass.exe 액세스 권한을 얻지 못하게 합니다. 이 lsass.exe 프로세스에서는 사용자가 로그인한 후 메모리에 사용자 자격 증명을 저장합니다. Windows는 이러한 자격 증명을 사용하여 사용자의 유효성을 검사하고 로컬 보안 정책을 적용합니다.

일반적으로 하루 동안 많은 합법적인 프로세스에서 자격 증명을 lsass.exe 호출하기 때문에 이 규칙이 특히 시목일 수 있습니다. 알려진 합법적인 응용 프로그램에서 이 규칙으로 인해 과도한 알림 수가 생성되는 경우 제외 목록에 알림을 추가할 수 있습니다. 대부분의 다른 ASR 규칙은 많은 응용 프로그램의 정상적인 작동에서 일반적으로 lsass.exe 때문에 이 규칙에 비해 비교적 적은 수의 알림을 생성합니다.

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>LSA 보호와 함께 Windows 로컬 보안 기관 하위 lsass.exe(자격 증명 도용 *차단)* 규칙을 사용하도록 설정하는 것이 좋습니다.

LSA 보호 기능도 사용하도록 설정한 경우 이 규칙을 사용하도록 설정하면 추가 [보호가](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) 제공되지 않습니다. 규칙과 LSA 보호는 모두 동일한 방식으로 작동하기 때문에 둘 다 동시에 실행되는 것이 중복됩니다. 그러나 경우에 따라 LSA 보호를 사용하도록 설정하지 않을 수 있습니다. 이러한 경우 이 규칙을 사용하여 해당 규칙을 대상으로 하는 맬웨어에 대해 동등한 보호를 제공할 수 lsass.exe.

## <a name="see-also"></a>참고 항목

* [공격 표면 감소 개요](attack-surface-reduction.md)
* [공격 표면 감소 규칙 평가](evaluate-attack-surface-reduction.md)
* [공격 표면 감소 규칙 사용자 지정](customize-attack-surface-reduction.md)
* [공격 표면 감소 규칙 사용](enable-attack-surface-reduction.md)
* [다른 바이러스 백신/맬웨어 방지와 Microsoft Defender의 호환성](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
