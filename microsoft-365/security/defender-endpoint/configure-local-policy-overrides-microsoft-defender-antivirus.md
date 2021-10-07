---
title: 설정에 대한 로컬 Microsoft Defender 바이러스 백신 구성
description: 사용자가 Microsoft Defender AV에서 로컬로 설정을 변경하지 못하도록 설정하거나 사용하지 않도록 설정
keywords: 로컬 오버라이드, 로컬 정책, 그룹 정책, gpo, 잠금, 병합, 목록
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 09/14/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: c206d998d1900ef39a0edbfd21c24b2e0cdc0514
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192946"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>사용자가 로컬에서 정책 설정을 수정하지 Microsoft Defender 바이러스 백신 허용


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

기본적으로 Microsoft Defender 바이러스 백신 그룹 정책 개체를 통해 네트워크의 끝점으로 배포되는 설정은 사용자가 로컬로 설정을 변경하지 못하게 합니다. 경우에 따라 변경할 수 있습니다.

예를 들어 특정 사용자 그룹(예: 보안 연구원 및 위협 조사자)이 사용하는 끝점에서 개별 설정을 추가로 제어하도록 허용해야 할 수 있습니다.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>설정에 대한 로컬 Microsoft Defender 바이러스 백신 구성

이러한 정책의 기본 설정은 **사용 안 입니다.**

사용으로 설정된 경우 끝점의 사용자는 Windows 보안, 로컬 그룹 정책 설정 및 PowerShell cmdlet(해당되는 [경우)을](microsoft-defender-security-center-antivirus.md) 사용하여 관련 설정을 변경할 수 있습니다.

다음 표에는 연결된 기능 또는 설정에 대한 각 정책 정책 설정 및 구성 지침이 나열되어 있습니다.

이러한 설정을 구성하려면

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**

3. 트리를 확장하여 구성 **Windows 구성** Microsoft Defender 바이러스 백신 다음 설정 표에 지정된 위치(이  >   문서에 설명)를 확장합니다. 

4. 아래 표에 지정된 정책 **설정을** 두 번 클릭하고 옵션을 원하는 구성으로 설정하십시오. 확인 **을** 클릭하고 다른 설정에 대해 반복합니다.

5. 그룹 정책 개체를 평소와 같이 배포합니다.

## <a name="table-of-settings"></a>설정 표

<br/><br/>

| 위치 | 설정 | 문서 |
|---|---|---|---|
| MAPS |Microsoft MAPS에 보고하기 위한 로컬 설정 오버라이드 구성|[클라우드 제공 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md) |
| 격리|Quarantine 폴더에서 항목 제거를 위한 로컬 설정 오버라이드 구성|[검사에 대한 수정 구성](configure-remediation-microsoft-defender-antivirus.md) |
| 실시간 보호|컴퓨터의 파일 및 프로그램 활동 모니터링에 대한 로컬 설정 다시 설정 구성|[항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호|들어오는 파일 및 나올 파일 활동에 대한 모니터링을 위한 로컬 설정 오버라이드 구성 | [항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호|다운로드한 모든 파일 및 첨부 파일을 검사하기 위한 로컬 설정 다시 설정 구성|[항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호|동작 모니터링 켜기에 대한 로컬 설정 다시 설정 구성|[항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 실시간 보호|실시간 보호를 켜도록 로컬 설정 다시 설정 구성|[항상 보호 Microsoft Defender 바이러스 백신 모니터링을 사용하도록 설정 및 구성](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 수정|재구성 완료를 위해 예약된 전체 검색을 실행하도록 하루 중 시간의 로컬 설정 재지정 구성|[검사에 대한 수정 구성](configure-remediation-microsoft-defender-antivirus.md) |
| 검사|최대 CPU 사용률에 대한 로컬 설정 오버라이드 구성|[검사 구성 및 실행](run-scan-microsoft-defender-antivirus.md) |
| 검사|일정 검사 일에 대한 로컬 설정 오버라이드 구성|[예약된 검사 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 검사|예약된 빠른 검사 시간을 위한 로컬 설정 재지정 구성|[예약된 검사 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 검사|예약된 검사 시간의 로컬 설정 오버라이드 구성|[예약된 검사 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 검사|예약된 검사에 사용할 검사 유형에 대한 로컬 설정 오버라이드 구성|[예약된 검사 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>로컬 및 전역으로 정의된 위협 수정 및 제외 목록 병합 방법 구성

로컬로 정의된 목록을 전역적으로 정의된 목록과 결합하거나 병합하는 방법을 구성할 수도 있습니다. 이 설정은 제외 [목록,](configure-exclusions-microsoft-defender-antivirus.md)지정된 [](configure-remediation-microsoft-defender-antivirus.md)수정 목록 및 공격 표면 감소에 [적용됩니다.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

기본적으로 로컬 그룹 정책 및 Windows 보안 앱에 구성된 목록은 네트워크에 배포한 적절한 그룹 정책 개체에 의해 정의된 목록과 병합됩니다. 충돌이 있는 경우 전역으로 정의된 목록이 우선합니다.

이 설정을 사용하지 않도록 설정하면 전역으로 정의된 목록(예: 배포된 GOS의 목록)만 사용되도록 할 수 있습니다.

### <a name="use-group-policy-to-disable-local-list-merging"></a>그룹 정책을 사용하여 로컬 목록의RG(로컬 목록)를 사용하지 않도록 설정

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**

3. 트리를 확장하여 **Windows 구성 요소를 > Microsoft Defender 바이러스 백신.**

4. 목록에 대해 **로컬 관리자 병합** 동작 구성을 두 번 클릭하고 옵션을 사용 안 **하도록 설정 합니다.** **확인** 을 클릭합니다.

> [!NOTE]
> 로컬 목록의 선택을 해제하면 제어된 폴더 액세스 설정이 다시 설정됩니다. 또한 로컬 관리자가 설정한 보호된 폴더 또는 허용된 앱을 모두 어버합니다. 제어된 폴더 액세스 설정에 대한 자세한 내용은 에서 차단된 앱 [허용을 Windows 보안.](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)

## <a name="related-topics"></a>관련 항목

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [사용자와의 최종 사용자 상호 작용 Microsoft Defender 바이러스 백신](configure-end-user-interaction-microsoft-defender-antivirus.md)
