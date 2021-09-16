---
title: 그룹 Microsoft Defender 바이러스 백신 구성
description: 그룹 정책을 사용하여 끝점용 Microsoft Defender에서 끝점에서 Microsoft Defender 바이러스 백신 정책을 구성하고 관리하는 방법을 학습합니다.
keywords: 그룹 정책, GPO, 구성, 설정
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/08/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 881db58dc6658c7ed73201e48e7e2079dbf6aa97
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59401017"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>그룹 정책 설정을 사용하여 그룹 정책 Microsoft Defender 바이러스 백신

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

그룹 정책을 [사용하여](/windows/win32/srvnodes/group-policy) 끝점에서 Microsoft Defender 바이러스 백신 관리할 수 있습니다.

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>그룹 Microsoft Defender 바이러스 백신 사용하여 구성

일반적으로 다음 절차에 따라 그룹 정책 설정을 구성하거나 Microsoft Defender 바이러스 백신 수 있습니다.

1. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 GPO(그룹 정책 개체)를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**

3. 관리 **템플릿 을 클릭합니다.**

4. 트리를 확장하여 **Windows 구성 요소를 Microsoft Defender 바이러스 백신.**  >  

5. 구성할 설정이 포함된  섹션(이 항목의 표에서 위치)을 확장하고 설정을 두 번 클릭하여 열고 구성을 변경합니다.

6. [평소처럼 업데이트된 GPO를 배포합니다.](/windows/win32/srvnodes/group-policy) 

## <a name="group-policy-settings-and-resources"></a>그룹 정책 설정 및 리소스

이 항목의 다음 표에서는 Windows 10 버전 1703에서 사용할 수 있는 그룹 정책 설정을 나열하고 이 설명서 라이브러리(해당하는 경우)의 해당 항목에 대한 링크를 제공합니다. 

> [!TIP]
> [2020년 5월 업데이트(2004년 설정](https://www.microsoft.com/download/101451)대한 그룹 정책 Windows 10 참조 스프레드시트를 다운로드합니다. 이 스프레드시트에는 Windows 10 2020년 5월 업데이트(2004년)에 대해 제공된 관리 템플릿 파일에 포함된 컴퓨터 및 사용자 구성에 대한 정책 설정이 나열되어 있습니다. 그룹 정책 개체를 편집할 때 스프레드시트를 참조하도록 구성할 수 있습니다.<br/><br/>

| 위치 | 설정 | 문서 |
|:---|:---|:---|
| 클라이언트 인터페이스 | 헤드리스 UI 모드 사용 | [사용자가 사용자 인터페이스를 보거나 상호 작용하지 Microsoft Defender 바이러스 백신 방지](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| 클라이언트 인터페이스 | 작업을 수행해야 하는 경우 클라이언트에 추가 텍스트 표시 | [엔드포인트에 표시되는 알림 구성](configure-notifications-microsoft-defender-antivirus.md) |
| 클라이언트 인터페이스 | 모든 알림 표시 안 | [엔드포인트에 표시되는 알림 구성](configure-notifications-microsoft-defender-antivirus.md) |
| 클라이언트 인터페이스 | 재부팅 알림을 표시하지 않습니다. | [엔드포인트에 표시되는 알림 구성](configure-notifications-microsoft-defender-antivirus.md) |
| 제외 | 확장 제외 | [검사에서 제외 구성 Microsoft Defender 바이러스 백신 유효성 검사](configure-exclusions-microsoft-defender-antivirus.md) |
| 제외 | 경로 제외 | [검사에서 제외 구성 Microsoft Defender 바이러스 백신 유효성 검사](configure-exclusions-microsoft-defender-antivirus.md) |
| 제외 | 프로세스 제외 | [검사에서 제외 구성 Microsoft Defender 바이러스 백신 유효성 검사](configure-exclusions-microsoft-defender-antivirus.md) | 
| 제외 | 자동 제외 끄기 | [검사에서 제외 구성 Microsoft Defender 바이러스 백신 유효성 검사](configure-exclusions-microsoft-defender-antivirus.md) |
| MAPS | '모든 시 차단' 기능 구성 | [모든 시 차단 사용](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| MAPS | Microsoft MAPS에 가입 | [클라우드 제공 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | 추가 분석이 필요한 경우 파일 샘플 보내기 | [클라우드 제공 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | Microsoft MAPS에 보고하기 위한 로컬 설정 오버라이드 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | 확장된 클라우드 검사 구성 | [클라우드 차단 제한 시간 구성](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | 클라우드 보호 수준 선택 | [클라우드 제공 보호 수준 지정](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| 네트워크 검사 시스템 | 네트워크 트래픽 검사에 대한 추가 정의 집합 지정 | [네트워크 트래픽 검사에 대한 추가 정의 집합 지정](specify-additional-definitions-network-traffic-inspection-mdav.md) |
| 네트워크 검사 시스템 | 정의 사용 중지 켜기 | [정의 사용 중지 구성](turn-on-definition-retirement.md)  |
| 네트워크 검사 시스템 | 프로토콜 인식 켜기 | [프로토콜 인식 켜기](turn-on-protocol-recognition.md)  |
| 격리 | Quarantine 폴더에서 항목 제거를 위한 로컬 설정 오버라이드 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 격리 | Quarantine 폴더에서 항목 제거 구성 | [검사에 대한 Microsoft Defender 바이러스 백신 구성](configure-remediation-microsoft-defender-antivirus.md) |
| 실시간 보호 | 컴퓨터의 파일 및 프로그램 활동 모니터링에 대한 로컬 설정 다시 설정 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 실시간 보호 | 들어오는 파일 및 나올 파일 활동에 대한 모니터링을 위한 로컬 설정 오버라이드 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 실시간 보호 | 다운로드한 모든 파일 및 첨부 파일을 검사하기 위한 로컬 설정 다시 설정 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 실시간 보호 | 동작 모니터링 켜기에 대한 로컬 설정 다시 설정 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 실시간 보호 | 실시간 보호를 켜도록 로컬 설정 다시 설정 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 실시간 보호 | 검사할 다운로드한 파일 및 첨부 파일의 최대 크기 정의 | [항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호 | 컴퓨터에서 파일 및 프로그램 활동 모니터링 | [항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호 | 다운로드한 모든 파일 및 첨부 파일 검색 | [항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호 | 실시간 보호 끄기 | [항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호 | 동작 모니터링 켜기 | [항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호 | 실시간 보호를 사용할 때마다 프로세스 검색 켜기 | [항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호 | 원시 볼륨 쓰기 알림 켜기 | [항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호 | 수신 및 전송 파일 및 프로그램 활동에 대한 모니터링 구성 | [항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 수정 | 재구성 완료를 위해 예약된 전체 검색을 실행하도록 하루 중 시간의 로컬 설정 재지정 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 수정 | 재구성 완료를 위해 예약된 전체 검사 실행을 위해 주중 날짜 지정 | [예약된 Microsoft Defender 바이러스 백신 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 수정 | 재구성 완료를 위해 예약된 전체 검사 실행 시간을 지정합니다. | [예약된 Microsoft Defender 바이러스 백신 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 보고 | 향상된 알림 끄기 | [엔드포인트에 표시되는 알림 구성](configure-notifications-microsoft-defender-antivirus.md)
| 루트 | 끄기 Microsoft Defender 바이러스 백신 | 사용되지 않습니다(설치된 타사  바이러스 백신 앱이 올바르게 작동하도록 이 설정을 구성되지 않도록 설정해야 합니다.
| 루트 | 프록시 서버를 무시할 주소 정의 | [디바이스 프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus) |
| 루트 | 네트워크에 연결하기 위한 프록시 자동 구성(.pac) 정의 | [디바이스 프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus) |
| 루트 | 네트워크에 연결하기 위한 프록시 서버 정의 | [디바이스 프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus) |
| 루트 | 목록에 대한 로컬 관리자 병합 동작 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 루트 | 맬웨어 방지 서비스가 정상 우선 순위로 시작하도록 허용 | [검사에 대한 Microsoft Defender 바이러스 백신 구성](configure-remediation-microsoft-defender-antivirus.md) |
| 루트 | 맬웨어 방지 서비스가 항상 실행되는 상태로 유지하도록 허용 | [검사에 대한 Microsoft Defender 바이러스 백신 구성](configure-remediation-microsoft-defender-antivirus.md) |
| 루트 | 루틴 수정 끄기 | [검사에 대한 Microsoft Defender 바이러스 백신 구성](configure-remediation-microsoft-defender-antivirus.md) |
| 루트 | 예약된 작업 시간 임의로 | [사용자에 대해 예약된 검사 Microsoft Defender 바이러스 백신](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 검사 | 사용자가 스캔을 일시 중지하도록 허용 | 사용자가 사용자 인터페이스를 [보거나](prevent-end-user-interaction-microsoft-defender-antivirus.md) 상호 작용하지 못하도록 Microsoft Defender 바이러스 백신(사용자 인터페이스에서 지원되지 Windows 10) |
| 검사 | 예약된 검사를 실행하기 전에 최신 바이러스 및 스파이웨어 정의 확인 | [이벤트 기반 강제 업데이트 관리](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 검사 | catch-up 검사가 강제로 실행된 후의 일 수 정의 | [최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 검사 | 전체 검사 켜기 | [최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 검사 | 빠른 검사 실행 켜기 | [최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 검사 | 최대 CPU 사용률에 대한 로컬 설정 오버라이드 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 검사 | 일정 검사 일에 대한 로컬 설정 오버라이드 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 검사 | 예약된 빠른 검사 시간을 위한 로컬 설정 재지정 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 검사 | 예약된 검사 시간의 로컬 설정 오버라이드 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 검사 | 예약된 검사에 사용할 검사 유형에 대한 로컬 설정 오버라이드 구성 | [사용자가 정책 설정을 로컬로 수정하지 못하도록 차단 또는 허용](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 검사 | 시스템 복원 지점 만들기 | [검사에 대한 Microsoft Defender 바이러스 백신 구성](configure-remediation-microsoft-defender-antivirus.md) |
| 검사 | 검사 기록 폴더에서 항목 제거 설정 | [검사에 대한 Microsoft Defender 바이러스 백신 구성](configure-remediation-microsoft-defender-antivirus.md) |
| 검사 | 추론 켜기 | [항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 검사 | 전자 메일 검사 켜기 | [2016에서 검사 옵션 Microsoft Defender 바이러스 백신](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 검사 | 재분석 지점 검사 켜기 | [2016에서 검사 옵션 Microsoft Defender 바이러스 백신](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 검사 | 매핑된 네트워크 드라이브에서 전체 검사 실행 | [2016에서 검사 옵션 Microsoft Defender 바이러스 백신](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 검사 | 보관 파일 검사 | [2016에서 검사 옵션 Microsoft Defender 바이러스 백신](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 검사 | 네트워크 파일 검사 | [2016에서 검사 옵션 Microsoft Defender 바이러스 백신](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 검사 | 압축된 실행 실행기 검사 | [2016에서 검사 옵션 Microsoft Defender 바이러스 백신](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 검사 | 이동식 드라이브 검사 | [2016에서 검사 옵션 Microsoft Defender 바이러스 백신](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 검사 | 보관 파일을 검색할 최대 깊이 지정 | [2016에서 검사 옵션 Microsoft Defender 바이러스 백신](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 검사 | 검사 중 CPU 사용률의 최대 백분율 지정 | [2016에서 검사 옵션 Microsoft Defender 바이러스 백신](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 검사 | 검사할 보관 파일의 최대 크기 지정 | [2016에서 검사 옵션 Microsoft Defender 바이러스 백신](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 검사 | 예약된 검색을 실행할 날짜 지정 | [사용자에 대해 예약된 검사 Microsoft Defender 바이러스 백신](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 검사 | 매일 빠른 검색을 실행할 간격 지정 | [사용자에 대해 예약된 검사 Microsoft Defender 바이러스 백신](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 검사 | 예약된 검사에 사용할 검사 유형 지정 | [사용자에 대해 예약된 검사 Microsoft Defender 바이러스 백신](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 검사 | 매일 빠른 검사에 대한 시간 지정 | [사용자에 대해 예약된 검사 Microsoft Defender 바이러스 백신](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 검사 | 예약된 검색을 실행할 시간 지정 | [사용자에 대해 예약된 검사 Microsoft Defender 바이러스 백신](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 검사 | 컴퓨터가 사용 중이지만 사용 중이 아닌 경우만 예약된 검사 시작 | [사용자에 대해 예약된 검사 Microsoft Defender 바이러스 백신](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | Microsoft 업데이트의 보안 인텔리전스 업데이트 허용 | [모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 배터리 전원으로 실행 시 보안 인텔리전스 업데이트 허용 | [모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | Microsoft MAPS에 대한 정의 기반 보고서를 사용하지 않도록 설정하도록 알림 허용 | [이벤트 기반 강제 업데이트 관리](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | Microsoft MAPS에 대한 보고서를 기반으로 실시간 보안 인텔리전스 업데이트 허용 | [이벤트 기반 강제 업데이트 관리](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 시작 시 최신 바이러스 및 스파이웨어 정의 확인 | [이벤트 기반 강제 업데이트 관리](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 보안 인텔리전스 업데이트 다운로드를 위한 파일 공유 정의 | [보안 Microsoft Defender 바이러스 백신 및 보안 인텔리전스 업데이트 관리](manage-protection-updates-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 보안 인텔리전스 업데이트가 필요한 날짜 수 정의 | [최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 스파이웨어 정의가 기한이 지난 것으로 간주될 날짜 수 정의 | [최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 바이러스 정의가 기한이 지난 것으로 간주될 날짜 수 정의 | [최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 보안 인텔리전스 업데이트 다운로드를 위한 원본 순서 정의 | [보안 Microsoft Defender 바이러스 백신 및 보안 인텔리전스 업데이트 관리](manage-protection-updates-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 시작 시 보안 인텔리전스 업데이트 시작 | [이벤트 기반 강제 업데이트 관리](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 보안 인텔리전스 업데이트를 확인할 날짜 지정 | [보호 업데이트를 다운로드하고 적용해야 하는 경우 관리](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 보안 인텔리전스 업데이트를 확인할 간격 지정 | [보호 업데이트를 다운로드하고 적용해야 하는 경우 관리](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 보안 인텔리전스 업데이트를 확인할 시간 지정 | [보호 업데이트를 다운로드하고 적용해야 하는 경우 관리](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| 보안 인텔리전스 업데이트 | 보안 인텔리전스 업데이트 후 검사 켜기 | [사용자에 대해 예약된 검사 Microsoft Defender 바이러스 백신](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 위협 | 감지 시 기본 작업을 수행하지 않을 위협 경고 수준 지정 | [검사에 대한 Microsoft Defender 바이러스 백신 구성](configure-remediation-microsoft-defender-antivirus.md) |
| 위협 | 검색 시 기본 작업을 수행하지 않을 위협 지정 | [검사에 대한 Microsoft Defender 바이러스 백신 구성](configure-remediation-microsoft-defender-antivirus.md) |

## <a name="see-also"></a>참고 항목

- [관리 및 구성 도구에 대한 참조 항목](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
