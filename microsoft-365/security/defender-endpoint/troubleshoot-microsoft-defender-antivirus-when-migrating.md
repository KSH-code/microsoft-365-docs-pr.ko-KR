---
title: 타사 솔루션에서 마이그레이션하는 동안 Microsoft Defender 바이러스 백신 문제 해결
description: 마이그레이션할 때 발생하는 일반적인 오류 Microsoft Defender 바이러스 백신
keywords: 이벤트, 오류 코드, 로깅, 문제 해결, Microsoft Defender 바이러스 백신, Windows Defender 바이러스 백신, 마이그레이션
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 337f034dced0cad5d483b55fa279a7b220fb8e72
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59401581"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>타사 솔루션에서 마이그레이션하는 동안 Microsoft Defender 바이러스 백신 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)


타사 보안 솔루션에서 타사 보안 솔루션으로 마이그레이션하는 동안 문제가 발생하는 경우 여기에서 도움말을 Microsoft Defender 바이러스 백신.

## <a name="review-event-logs"></a>이벤트 로그 검토

작업 표시줄에서 검색 아이콘을  선택하고 이벤트 뷰어를 검색하여 이벤트 뷰어 *앱을 열 수 있습니다.*

응용 프로그램에 Microsoft Defender 바이러스 백신 응용 프로그램  및 서비스 로그 Microsoft Windows \>  \> **Windows Defender.** \> 

이 위치에서 작동 **아래의 열기** 를 **선택합니다.**

세부 정보 창에서 이벤트를 선택하면 아래쪽 창의 일반 및 세부 정보 탭에서  이벤트에 대한 자세한 정보가 표시됩니다. 

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender 바이러스 백신 시작되지 않습니다.

이 문제는 여러 가지 이벤트 ID의 형태로 매니페스트될 수 있습니다. 이 모든 이벤트는 모두 동일한 원인이 있습니다.

### <a name="associated-event-ids"></a>연결된 이벤트 ID

이벤트 ID|로그 이름|설명|원본
---|---|---|---
15 |응용 프로그램|업데이트된 Windows Defender 상태가 SECURITY_PRODUCT_STATE_OFF.|보안 센터
5007|Microsoft-Windows-Windows Defender/Operational|Windows Defender 바이러스 백신 구성이 변경되었습니다. 이 이벤트가 예기치 않은 이벤트인 경우 맬웨어의 결과일 수 있는 설정을 검토해야 합니다. <p> **이전 값:** Default\IsServiceRunning = 0x0 <p> **새 값:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1|Windows Defender
5010|Microsoft-Windows-Windows Defender/Operational|Windows Defender 바이러스 백신 소프트웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 검사가 사용되지 않도록 설정됩니다.|Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>타사 바이러스 백신이 Microsoft Defender 바이러스 백신 프로그램 업데이트가 시작되지 않는지 어떻게 알 수 있습니다.

Windows 10 장치에서 끝점용 Microsoft Defender를 사용하지 않는 경우 타사 바이러스 백신이 설치되어 있는 경우 Microsoft Defender 바이러스 백신 자동으로 꺼집니다. 타사 바이러스 백신이 설치된 끝점용 Microsoft Defender를 사용하는 경우 Microsoft Defender 바이러스 백신 기능이 축소되어 수동 모드로 시작됩니다.

> [!TIP]
> 방금 설명한 시나리오는 해당 시나리오에만 Windows 10. 다른 버전의 Windows [타사](microsoft-defender-antivirus-compatibility.md) 보안 소프트웨어와 함께 실행되는 Microsoft Defender 바이러스 백신 응답이 다릅니다.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>서비스 앱을 사용하여 서비스 Microsoft Defender 바이러스 백신 해제되어 있는지 확인

서비스 앱을 열하려면 작업  표시줄에서 검색 아이콘을 선택하고 서비스를 *검색합니다.* services.msc 를 입력하여 명령줄에서 앱을 열 *수도 있습니다.*

서비스 Microsoft Defender 바이러스 백신 대한 정보는 운영 에서 서비스 앱 **Windows Defender** \> **나열됩니다.** 바이러스 백신 서비스 이름은 Windows Defender 바이러스 백신 *입니다.*

앱을 검사하는 동안 Windows Defender 바이러스 백신 *서비스가* 수동으로 설정되어 있는 것을 볼 수 있지만 이 서비스를 수동으로 시작하려고 시도하면 로컬 컴퓨터의 Windows Defender 바이러스 백신 서비스 서비스가 시작된 다음 중지됨을 표시하는 *경고가 표시됩니다. 일부 서비스는 다른* 서비스 또는 프로그램에서 사용하지 않는 경우 자동으로 중지됩니다.

이는 타사 Microsoft Defender 바이러스 백신 호환성을 유지하기 위해 자동으로 꺼져 있습니다.

#### <a name="generate-a-detailed-report"></a>자세한 보고서 생성

관리자 모드로 실행 모드에서 명령 프롬프트를 열고  다음 명령을 입력하여 현재 활성 그룹 정책에 대한 자세한 보고서를 생성할 수 있습니다.

```powershell
GPresult.exe /h gpresult.html
```

그러면 *./gpresult.html.* 이 파일을 열면 끄는 방법에 따라 다음과 같은 Microsoft Defender 바이러스 백신 수 있습니다.

##### <a name="group-policy-results"></a>그룹 정책 결과

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>도메인 또는 로컬 수준에서 또는 SCCM(System Center Configuration Manager)을 통해 GPO(그룹 정책)를 통해 보안 설정을 구현하는 경우

GPResults 보고서의 제목 아래에 Windows *Components/Windows Defender 바이러스 백신*, 다음과 같은 항목이 표시될 수 있습니다. 이 항목은 Microsoft Defender 바이러스 백신 끄는 것입니다.

정책|설정|더하기 GPO
---|---|---
끄기 Windows Defender 바이러스 백신|사용|Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>GPP(그룹 정책 기본 설정)를 통해 보안 설정을 구현하는 경우

레지스트리 항목(키 *경로: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, 값 이름: DisableAntiSpyware)* 아래에 다음과 같은 항목이 표시되어 Microsoft Defender 바이러스 백신 표시됩니다.

DisableAntiSpyware|-
---|---
더하기 GPO|Win10-Workstations
결과: 성공|
**일반**|
작업|업데이트
**속성**|
Hive|HKEY_LOCAL_MACHINE
키 경로|SOFTWARE\Policies\Microsoft\Windows Defender
값 이름|DisableAntiSpyware
값 유형|REG_DWORD
값 데이터|0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>레지스트리 키를 통해 보안 설정이 구현된 경우

보고서에 다음 텍스트가 포함될 수 있습니다. 이 텍스트는 Microsoft Defender 바이러스 백신 해제되어 있습니다.

> 레지스트리(regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware(dword) 1(16진수)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>보안 설정이 Windows 서버 Windows 경우

이미징 관리자가 보안 정책 **[DisableAntiSpyware를](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** 설정하거나,GPEdit.exe *,* LGPO.exe ** 또는 작업 순서에서 레지스트리를 수정하여 로컬로 설정할 수 있습니다. 신뢰할 수 [있는 이미지](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) 식별자를 구성할 수 Microsoft Defender 바이러스 백신.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>다시 Microsoft Defender 바이러스 백신 켜기

Microsoft Defender 바이러스 백신 활성 상태인 다른 바이러스 백신이 없는 경우 자동으로 켜집니다. 모든 기능을 사용하여 실행할 수 있도록 타사 바이러스 Microsoft Defender 바이러스 백신 완전히 꺼야 합니다.

> [!WARNING]
> *wdboot,* *wdfilter,* wdnisdrv, *wdnissvc* 및 *windefend에* 대한 Windows Defender 시작 값을 편집하는 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services 지원되지 않을 수 있으며 강제로 시스템을 다시 이미지화해야 할 수 있습니다.  

수동 모드는 끝점용 Microsoft Defender 및 타사 바이러스 백신과 함께 사용 가능한 Microsoft Defender 바이러스 백신. 수동 모드를 사용하면 Microsoft Defender가 파일을 검색하고 자체적으로 업데이트할 수 있지만 위협을 해결하지는 않습니다. 또한 끝점 [DLP(데이터](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) 손실 방지)가 배포되지 않는 한 실시간 보호를 통한 동작 모니터링은 수동 모드에서 사용할 수 없습니다. [](configure-real-time-protection-microsoft-defender-antivirus.md)

제한된 주기적 [](limited-periodic-scanning-microsoft-defender-antivirus.md)검사라고 하는 또 다른 기능은 최종 사용자가 자동으로 끄기 Microsoft Defender 바이러스 백신 사용할 수 있습니다. 이 기능을 Microsoft Defender 바이러스 백신 검색을 통해 타사 바이러스 백신과 함께 파일을 주기적으로 검색할 수 있습니다.

> [!IMPORTANT]
> 엔터프라이즈 환경에서는 제한된 주기적 검색을 권장하지 않습니다. 이 모드에서 실행 시 사용할 수 있는 검색, 관리 및 보고 Microsoft Defender 바이러스 백신 활성 모드에 비해 감소합니다.

### <a name="see-also"></a>참고 항목

- [Microsoft Defender 바이러스 백신 호환성](microsoft-defender-antivirus-compatibility.md)
- [Microsoft Defender 바이러스 백신 앱의 Windows 보안](microsoft-defender-security-center-antivirus.md)
