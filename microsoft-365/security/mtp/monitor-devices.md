---
title: 장치 모니터링 & 보고 - 보안 센터
description: 조직에서 장치를 안전하고 최신으로 유지하며 잠재적인 위협을 발견하는 방법에 대해 설명
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, 장치
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930501"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Microsoft 365 보안 센터의 장치 모니터링 및 보고

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 보안 센터에서 장치를 안전하고 최신으로 유지하며 잠재적인 위협을 발견합니다.

## <a name="view-device-alerts"></a>장치 경고 보기

끝점용 Microsoft Defender에서 장치에 대한 위반 활동 및 기타 위협에 대한 최신 경고를 얻습니다(E5 라이선스에서 사용 가능). Microsoft 365 보안 센터는 기본 설정 워크플로를 사용하여 이러한 경고를 높은 수준에서 효과적으로 모니터링합니다.

### <a name="monitor-high-impact-alerts"></a>영향이 큰 경고 모니터링

각 끝점용 Microsoft Defender 경고에는 해당하는 심각도(높음, 중간, 낮음 또는 정보)가 있습니다. 무인으로 남아 있는 경우 네트워크에 잠재적인 영향을 나타냅니다.  

장치 경고 **심각도** 카드를 사용하여 특히 심각하고 즉각적인 응답이 필요할 수 있는 경고에 집중합니다. 이 카드에서 Microsoft Defender 보안 센터 포털에서 자세한 정보를 볼 수 있습니다.

![장치 경고 심각도 카드](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>경고 원본 이해

끝점용 Microsoft Defender는 광범위한 보안 센서 및 인텔리전스 원본의 데이터를 활용하여 경고를 생성합니다. 예를 들어 Microsoft Defender 바이러스 백신 및 타사 맬웨어 방지의 검색 정보를 사용할 수 있습니다. 또한 웹 서비스 API를 통해 제공되는 사용자 지정 위협 인텔리전스를 사용할 수도 있습니다.

장치 **경고 검색** 원본 카드는 소스로 경고 배포를 보여줍니다. 특정 원본, 특히 사용자 지정 원본과 관련된 활동을 추적합니다. 또한 이 카드를 사용하여 악의적인 활동이나 구성 요소를 자동으로 차단하도록 구성되지 않은 센서에서 오는 경고에 집중할 수 있습니다.

![장치 경고 감지 소스 카드](../../media/device-alert-detection-sources.png)

이 카드에서 Microsoft Defender 보안 센터 포털에서 자세한 정보를 볼 수 있습니다.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>경고를 트리거하는 위협 유형 이해

끝점용 Microsoft Defender는 공격 체인의 특정 단계 또는 위협 구성 요소 유형을 나타내는 범주로 각 경고를 정렬합니다. 예를 들어 감지된 위협 활동은 네트워크의 다른 장치에 연결하려고 시도했다는 것을 나타내기 위해 "측면 이동"으로 분류될 수 있습니다. 공격자가 초기 발자국을 얻은 후에 활동이 발생한 것일 수 있습니다. 검색된 위협 구성 요소는 광범위하게 맬웨어로 분류되거나 특정 위협 유형으로 분류될 수 있습니다. 랜섬웨어, 자격 증명 도용 또는 기타 유형의 악성 또는 원치 않는 소프트웨어가 포함됩니다.

Device **threat categories** card shows the distribution of alerts into these categories. 이 정보를 사용하여 일반적으로 소셜 엔지니어링 시도보다 영향을 더 많이 미치는 자격 증명 도난 시도와 같은 위협 활동을 식별할 수 있습니다. 랜섬웨어와 같은 잠재적으로 파괴적인 위협을 모니터링할 수도 있습니다.

![장치 위협 범주 카드](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>활성 경고 모니터링

장치 **경고 상태** 카드는 해결되지 않은 경고 수를 나타내며 주의가 필요할 수 있습니다. 이 카드에서 Microsoft Defender 보안 센터 포털에서 자세한 정보를 볼 수 있습니다.

![장치 경고 상태 카드](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>해결된 경고 분류 모니터링

끝점에 대한 Microsoft Defender 경고를 확인할 때 보안 직원은 경고가 확인된지 여부를 다음으로 지정할 수 있습니다.

* 실제 위반 활동 또는 위협 구성 요소를 식별하는 실제 경고
* 정상적인 활동을 잘못 감지한 거짓 경고

장치 **경고 분류** 카드는 해결된 경고가 참 또는 거짓 경고로 분류된지 여부를 보여줍니다. 이 카드에서 Microsoft Defender 보안 센터 포털에서 자세한 정보를 볼 수 있습니다.

참고: 특정 경고에 대해 분류 정보를 사용할 수 없는 경우도 있습니다.

![장치 경고 분류 카드](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>해결된 경고 결정 모니터링

보안 직원은 해결 중에 경고가 참인지 또는 거짓인지를 분류할 수 있습니다. 결정은 경고 유효성을 검사하는 동안 발견된 일반 또는 악의적인 활동의 유형을 나타냅니다.

장치 **경고 결정 카드에는** 각 경고에 대해 제공된 결정이 표시됩니다.

* **APT**: 검색된 활동 또는 위협 구성 요소가 영향을 받는 네트워크에서 발판을 확보하도록 설계된 정교한 위반의 일부임을 나타내는 고급 영구 위협  
* **맬웨어**: 악성 파일 또는 코드
* **보안 담당자**: 보안 담당자가 수행한 정상적인 활동
* **보안 테스트**: 실제 위협을 시뮬레이션하도록 디자인된 활동 또는 구성 요소로, 보안 센서를 트리거하고 경고를 생성해야 합니다.
* **원치** 않는 소프트웨어 : 악성으로 간주되지 않지만 정책 또는 허용되는 사용 표준을 위반하는 앱 및 기타 소프트웨어
* **기타**: 제공된 형식에 속하지 않는 기타 결정

이 카드에서 Microsoft Defender 보안 센터에서 자세한 정보를 볼 수 있습니다.

![장치 경고 결정 카드](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>위험에 노출된 장치 이해

**장치 보호는** 디바이스의 위험 수준을 보여줍니다. 위험 수준은 장치의 경고 유형 및 심각도와 같은 요인을 기반으로 합니다.

![장치 보호 카드](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Intune 관리 장치의 상태 모니터링 및 보고

다음 보고서에는 Intune에 등록된 장치의 데이터가 포함되어 있습니다. 미가용 장치의 데이터는 포함되지 않습니다. 전역 관리자만 이러한 카드를 볼 수 있습니다.

Intune 등록된 장치 데이터에는 다음이 포함됩니다.

* 장치 준수
* 활성 맬웨어가 있는 장치
* 장치의 맬웨어 유형
* 장치의 맬웨어
* 맬웨어 감지가 있는 장치
* 맬웨어 검색이 있는 사용자

### <a name="monitor-device-compliance"></a>장치 준수 모니터링

**장치 준수는** Intune에 등록된 장치 수가 구성 정책을 준수하는지 보여줍니다.

![장치 준수 카드](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>맬웨어 검색을 통해 장치 검색

**장치 맬웨어 검색은** 완전히 해결되지 않은 맬웨어가 있는 Intune 등록 장치의 수를 제공합니다. 보류 중인 작업, 다시 시작, 전체 검사, 수동 사용자 작업 또는 수정 작업이 성공적으로 완료되지 않은 경우 해결이 부족할 수 있습니다.

![장치 맬웨어 감지 카드](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>검색된 맬웨어 유형 이해

**장치의 맬웨어 유형은** Intune에 등록된 장치에서 감지된 다양한 종류의 맬웨어를 보여 주며, Microsoft 365 보안 센터에서 각 유형을 조사할 수 있습니다.

![장치 카드의 맬웨어 유형](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>장치에서 검색된 특정 맬웨어 이해

**장치의 맬웨어는** 장치에서 감지된 특정 맬웨어 목록을 제공합니다.

![장치 카드의 맬웨어](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>맬웨어가 가장 많은 장치 이해

**맬웨어 검색이 있는 장치는** 맬웨어 검색이 가장 많은 장치를 보여 주며, Microsoft 365 보안 센터에서 맬웨어가 활성 상태인지, 장치를 사용하는 사용자 및 Intune의 관리 상태를 조사할 수 있습니다.

![맬웨어 감지 카드가 있는 장치](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>맬웨어가 가장 많은 장치가 있는 사용자 이해

**맬웨어 검색이 있는 사용자는** 맬웨어 검색이 가장 많은 장치를 사용자에게 보여 주게 됩니다. Microsoft 365 보안 센터에서 각 사용자에게 할당된 장치 수와 각 장치 및 맬웨어 유형에 대한 자세한 정보를 볼 수 있습니다.

![맬웨어 검색 카드가 있는 사용자](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a>공격 표면 감소 규칙 배포 및 검색 모니터링 및 관리

[ASR(공격](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) 취약성 축소) 규칙은 일반적으로 악용 검색 맬웨어가 장치를 감염시킬 때 사용하는 작업 및 앱을 방지하는 데 도움이 됩니다. 이러한 규칙은 실행 파일을 실행하는 시기와 방법을 제어합니다. 예를 들어 JavaScript나 VBScript가 다운로드 한 실행 파일을 시작하는 것을 방지하거나 Office 매크로에서 Win32 API 호출을 차단하거나 USB 드라이브에서 실행되는 프로세스를 차단할 수 있습니다.

![공격 표면 감소 카드](../../media/attack-surface-reduction-rules.png)

**공격 표면 감소 규칙** 카드는 장치 전체의 규칙 배포 개요를 제공합니다.

카드의 맨 위에 있는 막대에는 다음의 배포 모드에 있는 총 장치 수가 표시됩니다.

* **차단 모드:** 검색된 활동을 차단하도록 구성된 규칙이 하나 이상 있는 장치
* **감사 모드:** 검색된 활동을 차단하기 위해 설정된 규칙이 없지만 검색된 활동을 감사하기 위해 하나 이상의 규칙이 설정된 장치  
* **끄기**: 모든 ASR 규칙이 꺼진 장치

이 카드의 아래쪽 부분에는 장치 전체의 규칙 설정이 표시됩니다. 각 막대는 차단, 감사 검색 또는 규칙이 완전히 꺼져 있는 장치 수를 나타냅니다.

### <a name="view-asr-detections"></a>ASR 검색 보기

네트워크에서 ASR 규칙 검색에 대한 자세한 정보를  확인하려면 공격 표면 축소 규칙 카드에서 검색 **보기를** 선택합니다. 자세한 **보고서** 페이지의 검색 탭이 열립니다.

![검색 탭](../../media/detections-tab.png)

페이지 맨 위에 있는 차트에는 차단되거나 감사된 검색을 누적하는 시간의에 대한 검색이 표시됩니다. 하단의 표에는 최근 검색이 나열되어 있습니다. 표에서 다음의 정보를 사용하여 검색 특성을 이해할 수 있습니다.

* **검색된 파일:** 파일, 일반적으로 스크립트 또는 문서로, 해당 콘텐츠가 의심되는 공격 활동을 트리거한 경우
* **규칙:** 규칙이 catch하도록 디자인된 공격 활동을 설명하는 이름입니다. 기존 ASR 규칙에 대한 읽기
* **원본 앱**: 의심되는 공격 활동을 트리거하는 콘텐츠를 로드하거나 실행한 응용 프로그램입니다. 웹 브라우저, Office 응용 프로그램 또는 PowerShell과 같은 시스템 도구와 같은 합법적인 응용 프로그램일 수 있습니다.
* **게시자**: 원본 앱을 릴리스한 공급업체

### <a name="review-device-asr-rule-settings"></a>장치 ASR 규칙 설정 검토

공격 표면 **감소 규칙** 보고서 페이지에서  구성 탭으로 이동하여 개별 장치에 대한 규칙 설정을 검토합니다. 장치를 선택하여 각 규칙이 차단 모드인지, 감사 모드인지 또는 완전히 해제되어 있는지에 대한 자세한 정보를 얻을 수 있습니다.

![구성 탭](../../media/configuration-tab.png)

Microsoft Intune은 ASR 규칙에 대한 관리 기능을 제공합니다. 설정을 업데이트하려면 탭의 장치  구성에서  시작을 선택하여 Intune에서 장치 관리를 하세요.

### <a name="exclude-files-from-asr-rules"></a>ASR 규칙에서 파일 제외

Microsoft 365 보안 센터는 공격 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) 표면 축소 규칙에 의해 검색에서 제외할 수 있는 파일의 이름을 수집합니다. 파일을 제외하면 가중치 검색을 줄이고 차단 모드에서 공격 표면 축소 규칙을 보다 확신 있게 배포할 수 있습니다.

제외는 Microsoft Intune에서 관리되지만 Microsoft 365 보안 센터에서는 파일을 이해하는 데 도움이 되는 분석 도구를 제공합니다. 제외를 위해 파일 수집을 시작하려면 공격  표면 축소 규칙 보고서 페이지의 제외 추가 **탭으로** 이동합니다.

>[!NOTE]  
>이 도구는 모든 공격 표면 축소 규칙의 검색을 분석하지만 일부 규칙만 제외를 [지원합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)

![제외 탭 추가](../../media/add-exclusions-tab.png)

이 표에는 공격 표면 축소 규칙에서 검색된 모든 파일 이름이 나열됩니다. 파일을 선택하여 제외가 미치는 영향을 검토할 수 있습니다.

* 검색 수 감소
* 검색을 보고하는 장치 수

제외에 대한 전체 경로가 있는 선택한 파일 목록을 표시하려면 제외 경로 다운로드를 **선택합니다.**

Windows 로컬 보안 기관 하위 체제(lsass.exe)에서 자격 증명을 도용하지 못하게 하는 ASR 규칙에 대한 로그를 **lsass.exe.**  일반적인 시스템 파일이지만 검색된 파일로 캡처됩니다. 따라서 생성된 제외 경로 목록에 이 파일이 포함됩니다. 검색된 파일 대신 이 규칙을 트리거한 파일을lsass.exe검색된 파일 **대신** 원본 앱의 경로를 사용합니다.

원본 앱을 찾으기 위해 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) 이 특정 규칙에 대해 다음 고급 헌팅 쿼리를 실행합니다(규칙 ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2로 식별됨).

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>파일 제외 확인

ASR에서 파일을 제외하기 전에 파일을 검사하여 악성 파일이 아닌지 확인하는 것이 좋습니다.

파일을 검토하기 위해 Microsoft Defender [보안](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) 센터의 파일 정보 페이지를 사용하세요. 이 페이지에서는 보전 정보와 VirusTotal 바이러스 백신 검색 비율을 제공합니다. 페이지를 사용하여 심층 분석을 위해 파일을 제출할 수 있습니다.

Microsoft Defender 보안 센터에서 검색된 파일을 찾으기 위해 다음 고급 헌팅 쿼리를 사용하여 모든 ASR 검색을 검색합니다.

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

결과에 **SHA1** 또는 **InitiatingProcessSHA1을** 사용하여 Microsoft Defender 보안 센터의 유니버설 검색 창을 사용하여 파일을 검색합니다.
