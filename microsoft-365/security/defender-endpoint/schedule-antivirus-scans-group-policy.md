---
title: 그룹 정책을 사용하여 바이러스 백신 검사 예약
description: 그룹 정책을 사용하여 바이러스 백신 검사 설정
keywords: 빠른 검사, 전체 검사, 일정, 그룹 정책, 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6ca4616cd1c2818e0a1eb0b5c286142e9f65f32b
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59353589"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>그룹 정책을 사용하여 바이러스 백신 검사 예약

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

이 문서에서는 그룹 정책을 사용하여 예약된 검색을 구성하는 방법을 설명합니다. 검사 예약 및 검사 유형에 대한 자세한 내용은 [Configure scheduled quick or full Microsoft Defender 바이러스 백신 scan을 참조합니다.](schedule-antivirus-scans.md) 

## <a name="configure-antivirus-scans-using-group-policy"></a>그룹 정책을 사용하여 바이러스 백신 검사 구성

1. 그룹 정책 관리 컴퓨터의 그룹 정책 편집기에서 컴퓨터 구성 관리 템플릿 및 구성 요소 Windows  \>  \>  \> **검사로** \> **Microsoft Defender 바이러스 백신 합니다.**

2. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**

3. 그룹 정책 개체에 대한 설정을 지정하고 확인 을 **선택합니다.** 

4. 구성할 각 설정에 대해 1-4단계를 반복합니다.

5. 일반적으로와 같은 그룹 정책 개체를 배포합니다. 그룹 정책 개체에 대한 도움이 필요한 경우 그룹 정책 개체 [만들기를 참조합니다.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

> [!TIP]
> 보호 업데이트를 다운로드 [및](manage-protection-update-schedule-microsoft-defender-antivirus.md) 적용해야 하는 경우 관리 및 사용자가 정책 설정을 로컬로 수정할 수 있도록 허용 안 하도록 허용 항목을 [참조하세요.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="group-policy-settings-for-scheduling-scans"></a>검사의 그룹 정책 설정

| 위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우) |
|:---|:---|:---|:---|
| 검사 | 예약된 검사에 사용할 검사 유형 지정 | 빠른 검사 |
| 검사 | 예약된 검색을 실행할 날짜 지정 | 검색을 실행할 날짜를 지정하거나 지정하지 않습니다. | 없음 |
| 검사 | 예약된 검색을 실행할 시간 지정 | 자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.). | 2:a.m. |
| 루트 | 예약된 작업 시간 임의로 |이 Microsoft Defender 바이러스 백신 검사 시작 시간을 0시간에서 4시간 사이의 간격으로 임의로 임의로 변경합니다. <p>[SCEP에서](/mem/intune/protect/certificates-scep-configure)임의로 스캔을 30분을 더하거나 30분을 더한 간격으로 임의로 변경합니다. 이는 가상 컴퓨터 또는 VDI 배포에서 유용할 수 있습니다. | 사용 |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>끝점이 사용되지 않는 경우 검색을 위한 그룹 정책 설정

| 위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우) |
|:---|:---|:---|:---|
| 검사 | 컴퓨터가 사용 중이지만 사용 중이 아닌 경우만 예약된 검사 시작 | 컴퓨터가 설정되지만 사용되지 않는 한 예약된 검사는 실행되지 않습니다. | 사용 |

> [!NOTE]
> 끝점이 사용되지 않는 시간을 위해 검색을 예약하는 경우 검색은 CPU 스로틀 구성을 적용하지 못하며 가능한 한 빨리 검색을 완료하기 위해 사용 가능한 리소스를 최대한 활용합니다.

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>재구성 필요 검사 예약을 위한 그룹 정책 설정

| 위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우) |
|---|---|---|---|
| 수정 | 재구성 완료를 위해 예약된 전체 검사 실행을 위해 주중 날짜 지정 | 검색을 실행할 날짜를 지정하거나 지정하지 않습니다. | 없음 |
| 수정 | 재구성 완료를 위해 예약된 전체 검사 실행 시간을 지정합니다. | 자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.) | 2:a.m. |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>매일 검색을 위한 그룹 정책 설정

| 위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우) |
|:---|:---|:---|:---|
| 검사 | 매일 빠른 검색을 실행할 간격 지정 | 다음 빠른 검사 전에 경과해야 하는 시간을 지정합니다. 예를 들어 2시간마다 실행을 위해 **2를** 입력하고, 하루 한 번씩 **24를 입력합니다.** **0을 입력하여** 매일 빠른 검색을 실행하지 않습니다. | 없음 |
| 검사 | 매일 빠른 검사에 대한 시간 지정 | 자정 이후의 시간(분)을 지정합니다(예: **60** :a.m.) | 2:a.m. |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>보호 업데이트 후 검색을 위한 그룹 정책 설정

| 위치 | 설정 | 설명 | 기본 설정(구성되지 않은 경우)|
|:---|:---|:---|:---|
| 서명 업데이트 | 보안 인텔리전스 업데이트 후 검사 켜기 | 검사는 새 보호 업데이트가 다운로드된 직후에 발생합니다. | 사용 |

