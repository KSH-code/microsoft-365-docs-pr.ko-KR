---
title: 업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용
description: 보호 및 Microsoft Defender 바이러스 백신 받는 방법을 관리합니다.
keywords: 업데이트, 보안 기준, 보호, 업데이트 예약, 강제 업데이트, 모바일 업데이트, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 09/08/2021
ms.openlocfilehash: e136556bc2749261230e0267355ed68ef811e0a8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212082"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- Windows Defender 바이러스 백신

최신 Microsoft Defender 바이러스 백신 유지하는 것은 장치에 새로운 맬웨어 및 공격 기술로부터 보호하는 데 필요한 최신 기술 및 기능을 유지하는 데 중요합니다. 수동 모드에서 실행 중인 경우에도 바이러스 Microsoft Defender 바이러스 백신 [업데이트해야 합니다.](microsoft-defender-antivirus-compatibility.md) 최신 업데이트와 관련된 두 가지 유형의 업데이트가 Microsoft Defender 바이러스 백신 있습니다.

- 보안 인텔리전스 업데이트
- 제품 업데이트

> [!TIP]
> 최신 엔진, 플랫폼 및 서명 날짜를 확인한 다음 Microsoft Defender 바이러스 백신 Microsoft 맬웨어 방지에 대한 보안 인텔리전스 업데이트를 [방문하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

## <a name="security-intelligence-updates"></a>보안 인텔리전스 업데이트

Microsoft Defender 바이러스 백신 Microsoft Advanced [](cloud-protection-microsoft-defender-antivirus.md) Protection Service 또는 MAPS라고도 하는 클라우드 제공 보호를 사용하며 보안 인텔리전스 업데이트를 주기적으로 다운로드하여 보호 기능을 제공합니다.

> [!NOTE]
> 업데이트는 아래 KB 번호에 따라 릴리스됩니다.
>
> - Microsoft Defender 바이러스 백신: KB2267602
> - System Center Endpoint Protection: KB2461484

클라우드 제공 보호는 항상 설정되어 있으며 인터넷에 대한 활성 연결이 필요합니다. 보안 인텔리전스 업데이트는 예약된 일정에 따라 발생합니다(정책을 통해 구성 가능). 자세한 내용은 에서 Microsoft 클라우드 제공 보호 [Microsoft Defender 바이러스 백신.](cloud-protection-microsoft-defender-antivirus.md)

최신 보안 인텔리전스 업데이트 목록은 보안 인텔리전스 업데이트 및 Microsoft Defender 바이러스 백신 [맬웨어 방지를 참조하세요.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

엔진 업데이트는 보안 인텔리전스 업데이트에 포함되어 있으며 월별 케이던스에 릴리스됩니다.

## <a name="product-updates"></a>제품 업데이트

Microsoft Defender 바이러스 백신 업데이트라고 하는 월별 [업데이트(KB4052623)가](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *필요합니다.*

다음 방법 중 하나를 통해 업데이트 배포를 관리할 수 있습니다.

- [Windows WSUS(서버 업데이트 서비스)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- Microsoft를 배포하고 네트워크의 끝점에 Windows 배포하는 데 사용하는 일반적인 방법입니다.

자세한 내용은 [Manage the sources for Microsoft Defender 바이러스 백신 protection updates를 참조하십시오.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)

> [!NOTE]
>
> - 월별 업데이트는 단계적으로 릴리스되어 Window Server Update Services에 여러 [패키지가 표시됩니다.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
> - 이 문서에는 광범위한 릴리스 채널에 포함된 변경 내용이 나열됩니다. [여기에서 최신 광범위 채널 릴리스를 참조하세요.](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)
> - 단계적 출시 프로세스에 대한 자세한 내용을 알아보고 다음 릴리스에 대한 자세한 내용은 Microsoft Defender 업데이트에 대한 단계적 출시 프로세스 관리를 [참조하세요.](manage-gradual-rollout.md)
> - 보안 인텔리전스 업데이트에 대한 자세한 내용은 보안 인텔리전스 업데이트 및 Microsoft Defender 바이러스 백신 Microsoft 맬웨어 [방지를 참조하세요.](https://www.microsoft.com/wdsi/defenderupdates)

## <a name="monthly-platform-and-engine-versions"></a>월별 플랫폼 및 엔진 버전

플랫폼 업데이트를 업데이트하거나 설치하는 방법에 대한 자세한 내용은 Windows Defender 맬웨어 방지 플랫폼용 업데이트를 [참조하세요.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)

모든 업데이트에 포함

- 성능 개선
- 서비스성 개선 및
- 통합 개선(클라우드, [](/microsoft-365/security/defender/microsoft-365-defender)Microsoft 365 Defender).
<br/>
<details>
<summary> 2021년 8월(플랫폼: 4.18.2108.7 | 엔진: 1.1.18500.10)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.349.22.0**<br/>
&ensp;릴리스: **2021년 9월 2일**<br/>
&ensp;플랫폼: **4.18.2108.7**<br/>
&ensp;엔진: **1.1.18500.10**<br/>
&ensp;지원 단계: **보안 및 중요 업데이트**<br/>

### <a name="whats-new"></a>새로운 기능
- 동작 모니터링 엔진 개선
- 새로운 성능 [분석기 Microsoft Defender 바이러스 백신](tune-performance-defender-antivirus.md)
- Microsoft Defender 바이러스 백신 DLS를 로드할 수 없습니다.
- Microsoft Defender 바이러스 백신 트러스트된 사용자 무시에 대해 더 강해지기
- 규칙당 공격 표면 감소 규칙 제외 구성에 대한 [지원이 추가되었습니다.](customize-attack-surface-reduction.md)
- 랜섬웨어에 대한 추가 데이터를 포함하기 위해 Human-Operated 변경 알림 확장(HumOR)

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details><details>
<summary> 2021년 7월(플랫폼: 4.18.2107.4 | 엔진: 1.1.18400.4)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.345.13.0**<br/>
&ensp;릴리스: **2021년 8월 5일**<br/>
&ensp;플랫폼: **4.18.2107.4**<br/>
&ensp;엔진: **1.1.18400.4**<br/>
&ensp;지원 단계: **보안 및 중요 업데이트**<br/>

### <a name="whats-new"></a>새로운 기능
- 휴대용 장치에 대한 장치 Windows 지원 추가
- 잠재적으로 원치 않는 응용 프로그램(PUA) 보호는 소비자에 대해 기본적으로 켜져 있습니다(잠재적으로 원치 않는 앱이 기본적으로 [차단됩니다 참조).](https://support.microsoft.com/windows/potentially-unwanted-apps-will-be-blocked-by-default-b9f53cb9-7f1e-40bb-8c6b-a17e0ab6289e)
- 그룹 정책 개체 관리 시스템에 대한 예약된 검사는 사용자가 구성한 검사 시간을 준수합니다.
- 동작 모니터링 엔진 개선

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details><details>
<summary> 2021년 6월(플랫폼: 4.18.2106.5 | 엔진: 1.1.18300.4)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.343.17.0**<br/>
&ensp;릴리스: **2021년 6월 28일**<br/>
&ensp;플랫폼: **4.18.2106.5**<br/>
&ensp;엔진: **1.1.18300.4**<br/>
&ensp;지원 단계: **보안 및 중요 업데이트**<br/>

### <a name="whats-new"></a>새로운 기능
- Microsoft Defender 업데이트의점적 출시 프로세스를 관리하기 위한 새로운 컨트롤입니다. Microsoft Defender 업데이트에 대한 서진적 출시 프로세스 [관리를 참조하세요.](manage-gradual-rollout.md)
- 동작 모니터링 엔진 개선
- 맬웨어 방지 정의의 롤아웃 개선
- 확장 에지 네트워크 이벤트 검사

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>이전 버전 업데이트: 기술 업그레이드 지원만

새 패키지 버전이 출시된 후 이전 두 버전에 대한 지원은 기술 지원으로만 축소됩니다. 이 섹션에 나열된 버전보다 오래된 버전은 기술 업그레이드 지원 전용으로 제공됩니다.
<details>
<summary> 2021년 5월(플랫폼: 4.18.2105.4 | 엔진: 1.1.18200.4)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.341.8.0**<br/>
&ensp;릴리스: **2021년 6월 3일**<br/>
&ensp;플랫폼: **4.18.2105.4**<br/>
&ensp;엔진: **1.1.18200.4**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능
- 동작 모니터링 [개선](client-behavioral-blocking.md)
- 고정 [네트워크 보호](network-protection.md) 알림 필터링 기능

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details><details>
<summary> 2021년 4월(플랫폼: 4.18.2104.14 | 엔진: 1.1.18100.5)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.337.2.0**<br/>
&ensp;릴리스: **2021년 4월 26일(엔진:**  1.1.18100.6 릴리스 2021년 5월 5일)<br/>
&ensp;플랫폼: **4.18.2104.14**<br/>
&ensp;엔진: **1.1.18100.5**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능
- 추가 동작 모니터링 논리
- 커널 모드 키 로거 검색 개선
- Microsoft Defender 업데이트의점적 출시 프로세스를 관리하기 위한 새 [컨트롤이 추가되었습니다.](manage-gradual-rollout.md)


### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details><details>
<summary> 2021년 3월(플랫폼: 4.18.2103.7 | 엔진: 1.1.18000.5)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.335.36.0**<br/>
&ensp;릴리스: **2021년 4월 2일**<br/>
&ensp;플랫폼: **4.18.2103.7**<br/>
&ensp;엔진: **1.1.18000.5**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- 동작 모니터링 엔진 개선
- 확장된 네트워크 무차별 공격 완화
- 변조 방지를 사용하도록 설정한 경우 더 많은 실패한 변조 [시도](prevent-changes-to-security-settings-with-tamper-protection.md) 이벤트 생성

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details><details>
<summary> 2021년 2월(플랫폼: 4.18.2102.3 | 엔진: 1.1.17900.7)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.333.7.0**<br/>
&ensp;릴리스: **2021년 3월 9일**<br/>
&ensp;플랫폼: **4.18.2102.3**<br/>
&ensp;엔진: **1.1.17900.7**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- 변조 방지를 통한 [서비스 복구 개선](prevent-changes-to-security-settings-with-tamper-protection.md)
- 변조 보호 범위 확장

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details><details>
<summary> 2021년 1월(플랫폼: 4.18.2101.9 | 엔진: 1.1.17800.5)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.327.1854.0**<br/>
&ensp;릴리스: **2021년 2월 2일**<br/>
&ensp;플랫폼: **4.18.2101.9**<br/>
&ensp;엔진: **1.1.17800.5**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- 셸 코드 악용 감지 개선
- 자격 증명 도용 시도에 대한 가시성 향상
- 서비스에서 향상된 Microsoft Defender 바이러스 백신 기능
- x64 에뮬 ARM 지원 개선
- 해결 방법: EDR 보호가 초기 검색을 수행한 후 위협 기록에 차단 알림이 남아 있습니다.

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details><details>
<summary> 2020년 11월-2020년 11월(플랫폼: 4.18.2011.6 | 엔진: 1.1.17700.4)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.327.1854.0**<br/>
&ensp;릴리스: **2020년 12월 3일**<br/>
&ensp;플랫폼: **4.18.2011.6**<br/>
&ensp;엔진: **1.1.17700.4**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- 향상된 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 상태 지원 로깅

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details><details>
<summary> 2020년 10월(플랫폼: 4.18.2010.7 | 엔진: 1.1.17600.5)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.327.7.0**<br/>
&ensp;릴리스: **2020년 10월 29일**<br/>
&ensp;플랫폼: **4.18.2010.7**<br/>
&ensp;엔진: **1.1.17600.5**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- 특수 위협 범주에 대한 새 설명
- 향상된 에뮬ation 기능
- 향상된 호스트 주소 허용/차단 기능
- Defender CSP의 새 옵션에서 로컬 사용자 제외의 무시

### <a name="known-issues"></a>알려진 문제

알려진 문제 없음
<br/>
</details><details>
<summary> 2020년 9월(플랫폼: 4.18.2009.7 | 엔진: 1.1.17500.4)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.325.10.0**<br/>
&ensp;릴리스: **2020년 10월 1일**<br/>
&ensp;플랫폼: **4.18.2009.7**<br/>
&ensp;엔진: **1.1.17500.4**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- 파일을 Quarantine에서 복원하려면 관리자 권한이 필요합니다.
- 이제 XML 형식 이벤트가 지원됩니다.
- 제외 병합을 외면하기 위한 CSP 지원
- 새 관리 인터페이스:
   - UDP 검사
   - Server 2019의 네트워크 보호
   - 네트워크 보호를 위한 IP 주소 제외
- TPM 측정에 대한 가시성 향상
- VBA 모듈 Office 향상

### <a name="known-issues"></a>알려진 문제

알려진 문제 없음
<br/>
</details>
<details>
<summary> 2020년 8월(플랫폼: 4.18.2008.9 | 엔진: 1.1.17400.5)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.323.9.0**<br/>
&ensp;릴리스: **2020년 8월 27일**<br/>
&ensp;플랫폼: **4.18.2008.9**<br/>
&ensp;엔진: **1.1.17400.5**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- 원격 분석 이벤트 추가
- 향상된 검사 이벤트 원격 분석
- 메모리 검사에 대한 향상된 동작 모니터링
- 향상된 매크로 스트림 검사
- `AMRunningMode`PowerShell cmdlet에 Get-MpComputerStatus 추가
- [DisableAntiSpyware는](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 무시됩니다. Microsoft Defender 바이러스 백신 바이러스 백신 프로그램을 검색하면 자동으로 꺼집니다.


### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details>

<details>
<summary> 2020년 7월(플랫폼: 4.18.2007.8 | 엔진: 1.1.17300.4)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.321.30.0**<br/>
&ensp;릴리스: **2020년 7월 28일**<br/>
&ensp;플랫폼: **4.18.2007.8**<br/>
&ensp;엔진: **1.1.17300.4**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- BITS에 대한 향상된 원격 분석
- Authenticode 코드 서명 인증서 유효성 검사 개선

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details>

<details>
<summary> 2020년 6월(플랫폼: 4.18.2006.10 | 엔진: 1.1.17200.2)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.319.20.0**<br/>
&ensp;릴리스: **2020년 6월 22일**<br/>
&ensp;플랫폼: **4.18.2006.10**<br/>
&ensp;엔진: **1.1.17200.2**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- 지원 [로그의 위치를 지정할 수 있습니다.](./collect-diagnostic-data.md)
- 수동 모드에서 적극적인 catchup 검사 건너뛰기
- 데이터 데이터 연결에서 Defender 업데이트 허용
- 캐싱을 사용하지 않도록 설정한 경우의 고정 성능 조정
- 고정 레지스트리 쿼리
- ADMX의 검사 시간 임의 지정 수정

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details>

<details>
<summary> 2020년 5월(플랫폼: 4.18.2005.4 | 엔진: 1.1.17100.2)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.317.20.0**<br/>
&ensp;릴리스: **2020년 5월 26일**<br/>
&ensp;플랫폼: **4.18.2005.4**<br/>
&ensp;엔진: **1.1.17100.2**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- 검사 이벤트에 대한 로깅 개선
- 향상된 사용자 모드 크래시 처리.
- 변조 방지를 위한 이벤트 추적이 추가되었습니다.
- AMSI 샘플 제출 수정
- AMSI 클라우드 차단 수정
- 고정 보안 업데이트 설치 로그

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details>

<details>
<summary> 2020년 4월(플랫폼: 4.18.2004.6 | 엔진: 1.1.17000.2)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.315.12.0**<br/>
&ensp;릴리스: **2020년 4월 30일**<br/>
&ensp;플랫폼: **4.18.2004.6**<br/>
&ensp;엔진: **1.1.17000.2**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능
- WDfilter 개선
- 더 실행 가능한 이벤트 데이터를 추가하여 표면 감소 감지 이벤트 공격
- 진단 데이터 및 WMI의 고정 버전 정보
- 플랫폼 업데이트 후 UI에서 잘못된 플랫폼 버전 수정
- 파일 없는 위협 방지를 위한 동적 URL intel
- UEFI 검사 기능
- 업데이트 로깅 확장

### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details>

<details>
<summary> 2020년 3월(플랫폼: 4.18.2003.8 | 엔진: 1.1.16900.2)</summary>

&ensp;보안 인텔리전스 업데이트 버전: **1.313.8.0**<br/>
&ensp;릴리스: **2020년 3월 24일**<br/>
&ensp;플랫폼: **4.18.2003.8**<br/>
&ensp;엔진: **1.1.16900.4**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- [MpCmdRun에](./command-line-arguments-microsoft-defender-antivirus.md) 추가된 CPU 스로틀 옵션
- 진단 기능 개선
- 보안 인텔리전스 시간 제한 단축(5분)
- AMSI 엔진 내부 로그 기능 확장
- 프로세스 차단에 대한 알림 개선

### <a name="known-issues"></a>알려진 문제
[**Fixed**] Microsoft Defender 바이러스 백신 실행 시 파일을 건너뛰고 있습니다.

<br/>
</details>

<details>

<summary> 2020년 2월(플랫폼: - | 엔진: 1.1.16800.2)</summary>


&ensp;보안 인텔리전스 업데이트 버전: **1.311.4.0**<br/>
&ensp;릴리스: **2020년 2월 25일**<br/>
&ensp;플랫폼/클라이언트: **-**<br/>
&ensp;엔진: **1.1.16800.2**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능


### <a name="known-issues"></a>알려진 문제
알려진 문제 없음
<br/>
</details>

<details>
<summary> 2020년 1월(플랫폼: 4.18.2001.10 | 엔진: 1.1.16700.2)</summary>


보안 인텔리전스 업데이트 버전: **1.309.32.0**<br/>
릴리스: **2020년 1월 30일**<br/>
플랫폼/클라이언트: **4.18.2001.10**<br/>
엔진: **1.1.16700.2**<br/>
&ensp;지원 단계: **기술 업그레이드 지원(전용)**<br/>

### <a name="whats-new"></a>새로운 기능

- WS2016의 고정 BSOD 및 Exchange
- TMP가 네트워크 경로로 리디렉션될 때 플랫폼 업데이트 지원
- 플랫폼 및 엔진 버전이 [WDSI에 추가됩니다.](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- 긴급 서명 업데이트를 [수동 모드로 확장](./microsoft-defender-antivirus-compatibility.md)
- 4.18.1911.3 중단 수정

### <a name="known-issues"></a>알려진 문제

[**고정**] [](/windows-hardware/design/device-experiences/modern-standby) 최신 대기 모드를 활용하는 장치는 보호의 간격을 Windows Defender 필터 드라이버가 중단될 수 있습니다.  영향을 받는 컴퓨터는 최신 맬웨어 방지 플랫폼으로 업데이트되지 않은 것으로 고객에게 표시됩니다.
<br/>
> [!IMPORTANT]
> 이 업데이트는:
> - SHA2를 지원하기 위해 더 낮은 버전의 플랫폼을 실행하는 RS1 장치에서 필요합니다.
> - 문제가 있는 시스템에 대한 재부팅 플래그가 있습니다.
> - 는 2020년 4월에 다시 출시될 예정으로, 향후 가용성을 유지하기 위해 최신 업데이트로 변경되지 않습니다.
> - 는 재부팅 요구 사항으로 인해 업데이트로 분류됩니다. 및
> - 는 업데이트 [에서만 Windows 있습니다.](https://support.microsoft.com/help/4027667/windows-10-update)
<br/>
</details>

<details>
<summary> 2019년 11월부터 2019년 11월까지(플랫폼: 4.18.1911.3 | 엔진: 1.1.16600.7)</summary>

보안 인텔리전스 업데이트 버전: **1.307.13.0**<br/>
릴리스: **2019년 12월 7일**<br/>
플랫폼: **4.18.1911.3**<br/>
엔진: **1.1.17000.7**<br/>
지원 단계: **지원 없음**<br/>

### <a name="whats-new"></a>새로운 기능

- 고정 MpCmdRun 추적 수준
- WDFilter 버전 정보 수정
- 알림 개선(PUA)
- MRT 로그를 추가하여 파일 지원

### <a name="known-issues"></a>알려진 문제
이 업데이트를 설치하면 디바이스에서 점프 패키지 4.18.2001.10을 최신 플랫폼 버전으로 업데이트해야 합니다.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender 바이러스 백신 플랫폼 지원

플랫폼 및 엔진 업데이트는 월별 케이던스에 제공됩니다. 완전히 지원받기 위해 최신 플랫폼 업데이트를 최신으로 유지하세요. 지원 구조는 동적이며, 최신 플랫폼 버전의 가용성에 따라 다음 두 단계로 진화합니다.

- **보안 및** 중요 업데이트 서비스 단계 - 최신 플랫폼 버전을 실행하는 경우 맬웨어 방지 플랫폼에 대한 보안 및 중요 업데이트를 받을 수 있습니다.

- **기술 지원(전용) 단계** - 새 플랫폼 버전이 출시된 후 이전 버전(N-2)에 대한 지원은 기술 지원으로만 축소됩니다. N-2 이전의 플랫폼 버전은 더 이상 지원되지 않습니다.*

\*기술 지원은 Windows 10 릴리스 버전에서 최신 플랫폼 버전으로의 업그레이드를 위해 계속 [제공됩니다(Windows 10](#platform-version-included-with-windows-10-releases)릴리스에 포함된 플랫폼 버전 참조).

기술 지원(전용) 단계 중에는 상업적으로 합리적인 지원 인시던트가 Microsoft 고객 서비스 & 지원 및 Microsoft의 관리 지원 서비스(예: 프리미어 지원)를 통해 제공됩니다. 지원 인시던트가 추가 지침을 위해 개발로 에스컬레이터해야 하는 경우, 비보안 업데이트가 필요하거나, 보안 업데이트가 필요한 경우 고객에게 최신 플랫폼 버전 또는 중간 업데이트(*)로 업그레이드할지 묻는 요청이 표시됩니다.

### <a name="platform-version-included-with-windows-10-releases"></a>릴리스에 포함된 플랫폼 Windows 10 버전

아래 표에는 최신 Microsoft Defender 바이러스 백신 함께 제공된 플랫폼 및 엔진 버전이 Windows 10 있습니다.

|Windows 10 릴리스  |플랫폼 버전  |엔진 버전 |지원 단계 |
|:---|:---|:---|:---|
|2004(20H1/20H2) |4.18.1909.6 |1.1.17000.2 | 기술 업그레이드 지원(전용) |
|1909(19H2) |4.18.1902.5 |1.1.16700.3 | 기술 업그레이드 지원(전용) |
|1903(19H1) |4.18.1902.5 |1.1.15600.4 | 기술 업그레이드 지원(전용) |
|1809(RS5) |4.18.1807.18075 |1.1.15000.2 | 기술 업그레이드 지원(전용) |
|1803(RS4) |4.13.17134.1 |1.1.14600.4 | 기술 업그레이드 지원(전용) |
|1709(RS3) |4.12.16299.15 |1.1.14104.0 | 기술 업그레이드 지원(전용) |
|1703(RS2) |4.11.15603.2 |1.1.13504.0 | 기술 업그레이드 지원(전용) |
|1607(RS1) |4.10.14393.3683 |1.1.12805.0 | 기술 업그레이드 지원(전용) |

릴리스 Windows 10 자세한 내용은 수명 주기 Windows [시트를 참조하세요.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>DISM(배포 이미지 서비스 및 관리)에 대한 업데이트

최신 바이러스 백신 및 맬웨어 방지 업데이트로 Windows 10(Enterprise, Pro 및 Home edition), Windows Server 2019 및 Windows Server 2016 OS 설치 이미지를 업데이트하는 것이 좋습니다. OS 설치 이미지를 최신으로 유지하면 보호 격차를 방지할 수 있습니다.

자세한 내용은 운영 체제 설치 Windows Microsoft [Defender 업데이트를 참조하세요.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)

<details>
<summary>1.1.2109.01</summary>

&ensp;패키지 버전: **1.1.2109.01**<br/>
&ensp;플랫폼 버전: **4.18.2107.4**<br/>
&ensp;엔진 버전: **1.1.18400.5**<br/>
&ensp;서명 버전: **1.347.891.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2108.01</summary>

&ensp;패키지 버전: **1.1.2108.01**<br/>
&ensp;플랫폼 버전: **4.18.2107.4**<br/>
&ensp;엔진 버전: **1.1.18300.4**<br/>
&ensp;서명 버전: **1.343.2244.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2107.02</summary>

&ensp;패키지 버전: **1.1.2107.02**<br/>
&ensp;플랫폼 버전: **4.18.2105.5**<br/>
&ensp;엔진 버전: **1.1.18300.4**<br/>
&ensp;서명 버전: **1.343.658.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2106.01</summary>

&ensp;패키지 버전: **1.1.2106.01**<br/>
&ensp;플랫폼 버전: **4.18.2104.14**<br/>
&ensp;엔진 버전: **1.1.18100.6**<br/>
&ensp;서명 버전: **1.339.1923.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;패키지 버전: **1.1.2105.01**<br/>
&ensp;플랫폼 버전: **4.18.2103.7**<br/>
&ensp;엔진 버전: **1.1.18100.6**<br/>
&ensp;서명 버전: **1.339.42.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;패키지 버전: **1.1.2104.01**<br/>
&ensp;플랫폼 버전: **4.18.2102.4**<br/>
&ensp;엔진 버전: **1.1.18000.5**<br/>
&ensp;서명 버전: **1.335.232.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;패키지 버전: **1.1.2103.01**<br/>
&ensp;플랫폼 버전: **4.18.2101.9**<br/>
&ensp;엔진 버전: **1.1.17800.5**<br/>
&ensp;서명 버전: **1.331.2302.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;패키지 버전: **1.1.2102.03**<br/>
&ensp;플랫폼 버전: **4.18.2011.6**<br/>
&ensp;엔진 버전: **1.1.17800.5**<br/>
&ensp;서명 버전: **1.331.174.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;패키지 버전: **1.1.2101.02**<br/>
&ensp;플랫폼 버전: **4.18.2011.6**<br/>
&ensp;엔진 버전: **1.1.17700.4**<br/>
&ensp;서명 버전: **1.329.1796.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;패키지 버전: **1.1.2012.01**<br/>
&ensp;플랫폼 버전: **4.18.2010.7**<br/>
&ensp;엔진 버전: **1.1.17600.5**<br/>
&ensp;서명 버전: **1.327.1991.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;패키지 버전: **1.1.2011.02**<br/>
&ensp;플랫폼 버전: **4.18.2010.7**<br/>
&ensp;엔진 버전: **1.1.17600.5**<br/>
&ensp;서명 버전: **1.327.658.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 새로 고쳐진 Microsoft Defender 바이러스 백신 서명
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;패키지 버전: **1.1.2011.01**<br/>
&ensp;플랫폼 버전: **4.18.2009.7**<br/>
&ensp;엔진 버전: **1.1.17600.5**<br/>
&ensp;서명 버전: **1.327.344.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- 없음
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;패키지 버전: **1.1.2011.01**<br/>
&ensp;플랫폼 버전: **4.18.2008.9**<br/>
&ensp;엔진 버전: **1.1.17400.5**<br/>
&ensp;서명 버전: **1.327.2216.0**<br/>

### <a name="fixes"></a>수정
- 없음

### <a name="additional-information"></a>추가 정보
- RS1 Windows 10 OS 설치 이미지에 대한 지원이 추가되었습니다.
<br/>
</details>

## <a name="more-resources"></a>추가 리소스

| 문서 | 설명  |
|:---|:---|
|[운영 체제 설치 Windows 대한 Microsoft Defender 업데이트](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | OS 설치 이미지(WIM 및 VHD 파일)에 대한 맬웨어 방지 업데이트 패키지를 검토합니다. Microsoft Defender 바이러스 백신(Windows 10 Enterprise, Pro 및 Home edition), Windows Server 2019 및 Windows Server 2016 설치 이미지에 대한 Windows Server 2016 다운로드합니다.  |
|[보호 업데이트를 다운로드하고 적용하는 방법 관리](manage-protection-updates-microsoft-defender-antivirus.md) | 보호 업데이트는 여러 소스를 통해 전달할 수 있습니다. |
|[보호 업데이트를 다운로드하고 적용해야 하는 경우 관리](manage-protection-update-schedule-microsoft-defender-antivirus.md) | 보호 업데이트를 다운로드해야 하는 경우를 예약할 수 있습니다. |
|[최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md) | 끝점에서 업데이트 또는 예약된 검사가 누락된 경우 다음에 사용자가 로그인할 때 강제로 업데이트를 실행하거나 검색할 수 있습니다. |
|[이벤트 기반 강제 업데이트 관리](manage-event-based-updates-microsoft-defender-antivirus.md) | 시작 시 또는 특정 클라우드 제공 보호 이벤트 후에 보호 업데이트를 다운로드할 수 있습니다. |
|[모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| 모바일 장치 및 가상 머신에 특히 유용한 배터리 전원에서 업데이트가 발생해야 하는지 여부와 같은 설정을 지정할 수 있습니다. |
