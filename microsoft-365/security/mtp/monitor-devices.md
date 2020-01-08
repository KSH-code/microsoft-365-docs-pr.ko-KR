---
title: Microsoft 365 보안 센터의 장치 모니터링 및 보고
description: 장치를 안전 하 고 최신 상태로 유지 하 고 조직에서 잠재적인 위협을 발견할 수 있는 방법에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터, 보고서, 장치
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 37e273a3e01177dec23b668ecb8a6301011ab88d
ms.sourcegitcommit: 72d0280c2481250cf9114d32317ad2be59ab6789
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40966906"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Microsoft 365 보안 센터의 장치 모니터링 및 보고

Microsoft 365 보안 센터에서 장치를 안전 하 고 최신 상태로 유지 하 고 잠재적인 위협을 발견할 수 있습니다.

## <a name="view-device-alerts"></a>장치 알림 보기

Microsoft Defender ATP에서 장치에 대 한 위반 활동 및 기타 위협에 대 한 최신 알림을 받을 수 있습니다 (E5 라이선스 사용 가능). Microsoft 365 보안 센터는 기본 워크플로를 사용 하 여 높은 수준에서 이러한 경고를 효과적으로 모니터링 합니다.

### <a name="monitor-high-impact-alerts"></a>높은 영향을 주는 알림 모니터링

각 Microsoft Defender ATP 경고에는 네트워크가 무인 모드로 유지 되는 경우 네트워크에 대 한 잠재적 영향을 나타내는 해당 심각도 높음, 중간, 낮음 또는 정보가 포함 되어 있습니다.  

**장치 경고 심각도** 카드를 사용 하 여 특히 더 심각 하 고 즉각적인 응답이 필요할 수 있는 경고에 초점을 집중 합니다. 이 카드에서 Microsoft Defender 보안 센터 포털에 대 한 추가 정보를 볼 수 있습니다.

![장치 경고 심각도 카드](../images/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>경고 원본 이해

Microsoft Defender ATP는 광범위 한 보안 센서 및 인텔리전스 원본의 데이터를 활용 하 여 알림을 생성 합니다. 예를 들어 Windows Defender 바이러스 백신 및 타사 맬웨어 방지의 검색 정보 뿐 아니라 웹 서비스 API를 통해 제공 되는 사용자 지정 위협 인텔리전스를 사용할 수 있습니다.

**장치 경고 검색** 원본 카드에는 원본에의 한 알림 배포가 표시 됩니다. 이 카드는 특정 원본, 특히 사용자 지정 원본에 관련 된 작업을 추적 하는 데 도움이 됩니다. 이를 사용 하 여 악성 활동 또는 구성 요소를 자동으로 차단 하도록 구성 되지 않은 센서에서 들어오는 경고에 집중할 수도 있습니다.

![장치 경고 검색 원본 카드](../images/device-alert-detection-sources.png)

이 카드에서 Microsoft Defender 보안 센터 포털에 대 한 추가 정보를 볼 수 있습니다.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>알림을 트리거하는 위협의 유형 이해

Microsoft Defender ATP는 공격 체인의 특정 단계 또는 위협 구성 요소 유형을 나타내는 범주로 각 경고를 정렬 합니다. 예를 들어 검색 된 위협 활동은 동작이 네트워크의 다른 장치에 연결 시도와 관련 되어 있으며 공격자가 초기 foothold를 얻은 후에 발생 했을 것임을 나타내는 이동으로 분류 될 수 있습니다. 감지 되 면 위협 구성 요소는 맬웨어 또는 보다 구체적으로 랜 섬 웨어, 자격 증명 가로채기 또는 기타 악성 또는 원치 않는 소프트웨어로 분류 될 수 있습니다.

**장치 위협 범주** 카드에는 이러한 범주에 대 한 경고 배포가 표시 됩니다. 이 정보를 사용 하 여 자격 증명 도용 시도와 같은 위협 활동을 식별 하 고, 예를 들어 사회 공학적에서의 시도에 비해 더 중요 한 영향을 줄 수 있습니다. 이를 사용 하 여 랜 섬 웨어와 같은 잠재적인 파괴적인 위협을 모니터할 수도 있습니다.

![장치 위협 범주 카드](../images/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>활성 경고 모니터링

**장치 경고 상태** 카드에는 해결 되지 않아 주의가 필요할 수 있는 경고의 수가 표시 됩니다. 이 카드에서 Microsoft Defender 보안 센터 포털에 대 한 추가 정보를 볼 수 있습니다.

![장치 경고 상태 카드](../images/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>확인 된 알림의 분류 모니터링

Microsoft Defender ATP 알림을 확인할 때 보안 담당자는 다음과 같이 확인 된 경고를 지정할 수 있습니다.

* 실제 위반 활동 또는 위협 구성 요소를 식별 하는 진정한 경고
* 정상적인 활동이 잘못 검색 된 거짓 경고

**장치 경고 분류** 카드에는 해결 된 경고가 참 또는 거짓 알림으로 분류 되어 있는지 여부가 표시 됩니다. 이 카드에서 Microsoft Defender 보안 센터 포털에 대 한 추가 정보를 볼 수 있습니다.

참고: 일부 경우에는 특정 알림에 대해 분류 정보를 사용할 수 없습니다.

![장치 경고 분류 카드](../images/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>해결 된 경고 확인 모니터링

확인 중에 경고가 참 인지 거짓이 든 관계 없이 보안 담당자는 알림을 확인 하는 동안 발견 된 일반 또는 악의적인 활동의 유형을 나타내는 결정을 제공할 수 있습니다.

**장치 경고 결정** 카드에는 다음과 같이 각 경고에 대해 제공 되는 결정이 표시 됩니다.

* **APT** 고급 영구 위협 (검색 된 활동 또는 위협 구성 요소가 영향을 받는 네트워크에서 foothold를 획득 하도록 설계 된 복잡 한 위반의 일부임을 나타냄)  
* **악성 파일** 또는 코드
* **보안** 직원 보안 직원이 수행 하는 정규 활동
* 실제 위협을 시뮬레이트하고 보안 센서를 트리거하고 알림을 생성할 것으로 예상 되는 **보안 테스트** 활동 또는 구성 요소
* **원치 않는 소프트웨어** 앱 및 악성으로 간주 되지 않는 기타 소프트웨어 및 정책 또는 적절 한 사용 표준을 위반 하는 경우
* **기타 기타** 제공 된 형식에 포함 되지 않는 기타 모든 결정

이 카드에서 Microsoft Defender 보안 센터의 추가 정보를 확인할 수 있습니다.

![장치 경고 결정 카드](../images/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>위험에 처 한 장치 이해

**장치 보호** 장치에 대 한 위험 수준을 표시 합니다. 위험 수준은 장치에 대 한 알림 유형 및 심각도와 같은 요소를 기반으로 합니다.

![장치 보호 카드](../images/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Intune 관리 장치에 대 한 상태 모니터링 및 보고

다음 보고서에는 Intune의 장치에 등록 된 데이터가 포함 되어 있습니다. Unenrolled 장치의 데이터는 포함 되지 않습니다. 전역 관리자만 이러한 카드를 볼 수 있습니다.

Intune에서 등록 된 장치 데이터에는 다음이 포함 됩니다.

* 장치 준수
* 활성 맬웨어가 있는 장치
* 장치에 있는 맬웨어 유형
* 장치에 대 한 맬웨어
* 맬웨어 검색이 포함 된 장치
* 맬웨어 검색이 포함 된 사용자

### <a name="monitor-device-compliance"></a>장치 준수 모니터링

**장치 준수** 는 구성 정책을 준수 하는 Intune의 장치 수를 보여 줍니다.

![장치 준수 카드](../images/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>맬웨어 감지 장치 검색

**장치 맬웨어 감지** 는 보류 중인 작업 (전체 검색 또는 수동 사용자 작업) 또는 재구성 작업이 성공적으로 완료 되지 않아 완전히 해결 되지 않은 맬웨어를 포함 하는 Intune 등록 장치 수를 제공 합니다.

![장치 맬웨어 감지 카드](../images/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>검색 된 맬웨어 유형 이해

**장치에 있는 맬웨어 유형은** Intune에서 등록 된 장치에서 감지 되는 다양 한 유형의 맬웨어를 보여 줍니다. Microsoft 365 보안 센터에서 각 유형을 조사할 수 있습니다.

![장치 카드의 맬웨어 유형](../images/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>장치에서 검색 되는 특정 맬웨어 이해

**장치의 맬웨어** 장치에서 검색 되는 특정 맬웨어 목록을 제공 합니다.

![장치 카드의 맬웨어](../images/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>맬웨어가 가장 많은 장치 이해

**맬웨어 감지 장치** 는 맬웨어가 검색 된 장치를 보여 줍니다. Microsoft 365 보안 센터에서는 맬웨어가 활성 상태 인지 여부, 해당 장치를 사용 하는 사람 및 Intune의 관리 상태를 조사할 수 있습니다.

![맬웨어 감지 카드가 포함 된 장치](../images/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>맬웨어가 가장 많은 장치를 보유 하는 사용자 이해

**맬웨어 검색을 사용** 하는 사용자에 게는 맬웨어가 탐지 된 장치를 사용한 사용자가 표시 됩니다. Microsoft 365 보안 센터에서는 각 사용자에 게 할당 된 장치의 수와 각 장치에 대 한 추가 정보와 맬웨어 유형에 대 한 자세한 정보를 확인할 수 있습니다.

![맬웨어 검색 카드를 사용 하는 사용자](../images/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a>ASR 규칙 배포 및 검색 모니터링 및 관리

[ASR (Attack Surface Reduction) 규칙](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) 을 사용 하면 일반적으로 익스플로잇 맬웨어를 검색 하는 장치를 감염 시키는 작업과 앱을 방지할 수 있습니다. 이러한 규칙은 실행 파일을 실행하는 시기와 방법을 제어합니다. 예를 들어 JavaScript나 VBScript가 다운로드 한 실행 파일을 시작하는 것을 방지하거나 Office 매크로에서 Win32 API 호출을 차단하거나 USB 드라이브에서 실행되는 프로세스를 차단할 수 있습니다.

![공격 노출 카드](../images/attack-surface-reduction-rules.png)

**공격 표면 감소 규칙** 카드는 장치 전체의 규칙 배포 개요를 제공합니다.

카드의 맨 위에 있는 막대에는 다음의 배포 모드에 있는 총 장치 수가 표시됩니다.

* 검색 된 활동을 차단 하도록 하나 이상의 규칙을 구성 하는 **차단 모드** 장치
* 검색 된 활동을 차단 하도록 규칙이 설정 되어 있지 않지만 검색 작업을 감사 하도록 하나 이상의 규칙 집합이 있는 **감사 모드** 장치  
* 모든 ASR 규칙을 끈 상태에서 장치 **해제**

이 카드의 아래쪽 부분에는 장치 전체의 규칙 설정이 표시됩니다. 각 막대는 차단 또는 감사 검색으로 설정되어 있거나 규칙이 완전히 해제되어 있는 장치의 수를 표시합니다.

### <a name="view-asr-detections"></a>ASR 검색 보기

네트워크에서 ASR 규칙 감지에 대 한 자세한 정보를 보려면 **Attack surface reduction** 카드에서 검색 **보기** 를 선택 합니다. 자세한 보고서 **페이지의 검색 탭이** 열립니다.

![탐지 탭](../images/detections-tab.png)

페이지 맨 위에 있는 차트에는 차단 되거나 감사 된 시간 단위 누적 검색에 따른 검색 내용이 표시 됩니다. 하단의 표에는 최근 검색이 나열되어 있습니다. 표에서 다음의 정보를 사용하여 검색 특성을 이해할 수 있습니다.

* **탐지 됨** 파일은 해당 내용이 의심 스러운 공격 활동을 트리거한 파일 (대개 스크립트나 문서)입니다.
* 규칙에서 catch 하도록 설계 된 공격 활동을 설명 하는 **규칙** 이름입니다. 기존 ASR 규칙에 대 한 정보 검토
* **원본 앱** 콘텐츠를 로드 하거나 실행 하 여 의심 스러운 공격 활동을 트리거한 응용 프로그램입니다. 웹 브라우저, Office 응용 프로그램 또는 PowerShell과 같은 시스템 도구와 같은 합법적인 응용 프로그램이 될 수 있습니다.
* **게시자** 원본 앱을 출시 한 공급 업체입니다.

### <a name="review-device-asr-rule-settings"></a>장치 ASR 규칙 설정 검토

**Attack surface reduction 규칙** 보고서 페이지에서 **구성** 탭으로 이동 하 여 개별 장치에 대 한 규칙 설정을 검토 합니다. 각 규칙이 차단 모드, 감사 모드 또는 전체 해제에 대 한 세부 정보를 가져올 장치를 선택 합니다.

![구성 탭](../images/configuration-tab.png)

Microsoft Intune은 ASR 규칙에 대 한 관리 기능을 제공 합니다. 설정을 업데이트 하려면 탭의 **장치 구성** 아래에서 **시작** 을 선택 하 여 Intune에서 장치 관리를 엽니다.

### <a name="exclude-files-from-asr-rules"></a>ASR 규칙에서 파일 제외

Microsoft 365 보안 센터는 공격 노출 범위 규칙에 따라 검색에서 [제외 하려는 파일](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) 의 이름을 수집 합니다. 파일을 제외 하면 가양성 검색을 줄이고 차단 모드에서 더 안전 하 게 공격 표면 축소 규칙을 배포할 수 있습니다.

제외는 Microsoft Intune에서 관리 되지만 Microsoft 365 보안 센터에서는 파일을 이해 하는 데 도움이 되는 분석 도구를 제공 합니다. 제외할 파일 수집을 시작 하려면 **Attack surface reduction 규칙** 보고서 페이지의 **제외 항목 추가** 탭으로 이동 합니다.

>[!NOTE]  
>이 도구는 모든 attack surface reduction 규칙에 따라 검색을 분석 하지만 [일부 규칙만 제외를 지원](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)합니다.

![제외 항목 추가 탭](../images/add-exclusions-tab.png)

이 표에서는 공격 노출 범위 규칙에 의해 검색 된 모든 파일 이름을 보여 줍니다. 파일을 선택 하 여 제외로 인 한 영향을 검토할 수 있습니다.

* 검색의 수 감소
* 검색을 보고 하는 장치 수는 얼마나 적습니다.

제외할 전체 경로를 사용 하 여 선택한 파일 목록을 가져오려면 **제외 경로 가져오기를**선택 합니다.

**Windows 로컬 보안 기관 하위 시스템 (lsass.exe)에서 ASR 규칙 차단 자격 증명 가로채기** 에 대 한 로그는 검색 된 파일로 일반 시스템 파일을 원본 응용 프로그램 **lsass.exe**에 캡처합니다. 따라서이 파일은 제외 경로의 생성 된 목록에 포함 됩니다. **Lsass.exe**대신이 규칙을 트리거한 파일을 제외 하려면 검색 된 파일 대신 원본 앱 경로를 사용 합니다.

원본 앱을 찾으려면이 특정 규칙에 대해 다음 [고급 구하기 쿼리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) 를 실행 합니다 (규칙 ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2으로 식별 됨).

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>파일 제외 확인
ASR에서 파일을 제외 하기 전에 해당 파일을 검사 하 여 실제로 악성 프로그램 인지 여부를 확인 하는 것이 좋습니다.

파일을 검토 하려면 Microsoft Defender 보안 센터의 [파일 정보 페이지](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) 를 사용 합니다. 이 페이지에서는 VirusTotal 바이러스 검사 비율 뿐만 아니라 전파 정보를 제공 합니다. 페이지를 사용 하 여 심층 분석을 위해 파일을 전송할 수도 있습니다.

Microsoft Defender 보안 센터에서 검색 된 파일을 찾으려면 다음 고급 검색 쿼리를 사용 하 여 모든 ASR 검색을 찾습니다.

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Microsoft Defender 보안 센터의 유니버설 검색 표시줄을 사용 하 여 파일을 검색 하려면 결과에서 **SHA1** 또는 **InitiatingProcessSHA1** 를 사용 합니다.