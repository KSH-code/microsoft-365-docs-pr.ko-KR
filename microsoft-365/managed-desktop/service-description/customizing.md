---
title: 서비스 계획에 대 한 예외
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: aca3bb6413aaab7620b1e1277c821a79dba4bb2f
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302905"
---
# <a name="exceptions-to-the-service-plan"></a>서비스 계획에 대 한 예외

Microsoft Managed Desktop은 맞게 조정 된 장치 목록, [표준 장치 설정](device-policies.md), 응용 프로그램 요구 사항 및 [구성 가능한 특정 설정을](../working-with-managed-desktop/config-setting-overview.md)제공 하 여 최종 사용자에 게 안전 하 고 생산성을 부여 하 고 즐겁게 환경을 제공 하도록 설계 되었습니다. 항상 제공 되는 서비스를 유지 하는 것이 가장 좋습니다. 그러나 서비스의 세부 사항이 조직의 요구 사항에 정확 하 게 맞지 않을 수도 있음을 인식 하 고 있습니다. 서비스를 특정 방식으로 변경 해야 하는 경우 다음 프로세스를 따라 변경 내용을 요청 하는 것이 중요 합니다.
 
## <a name="types-of-exceptions"></a>예외 유형

Microsoft Managed Desktop 기본 구성에 대 한 예외를 추가 하거나 변경할 수는 없습니다. 예를 들면 USB 포트 구성에서 새 장치 드라이버를 배포 하기 위한 범위입니다. 다양 한 예외를 그룹화 하는 방법은 다음과 같습니다.

|형식  |설명  |
|---------|---------|
|생산성 소프트웨어     |  최종 사용자에 게 필요한 포그라운드 소프트웨어 ( [응용 프로그램 요구 사항](mmd-app-requirements.md) 에 의해 제한 됨)       |
|Vpn & 보안 에이전트     |  장치 또는 네트워크의 동작을 보호, 모니터링 또는 변경 하는 데 사용 되는 소프트웨어       |
|디지털 환경 모니터링     |  사용자의 장치에서 데이터를 추적 하는 데 사용 되는 소프트웨어       |
|하드웨어 또는 소프트웨어 드라이버     |   장치 드라이버 ( [응용 프로그램 요구 사항](mmd-app-requirements.md) 에 따라 제한 됨)      |
|정책도     | 관리 되는 장치에 대 한 Windows 10 또는 Office 365 ProPlus 설정        |
|장치     | Microsoft Managed Desktop [장치 목록](device-list.md) 에 없는 장치        |
|기타     |  다른 영역에 포함 되지 않는 모든 사항       |
 
## <a name="request-an-exception"></a>예외 요청

변경 요청을 만들어 Microsoft Managed Desktop Administration portal을 통해 요청을 제출 합니다. 다음 정보를 포함 해야 합니다.

-   면제 유형: 예외 범주는 무엇입니까? (위의 표 참조)
-   요구 사항: 예외에 대 한 특정 비즈니스 요구 사항은 무엇 인가요?
-   제안: 비즈니스에서 요청 하는 솔루션은 무엇입니까?
-   시간 표시 막대:이 예외를 마지막으로 얼마나 오래 하시 겠어요? 

## <a name="how-we-assess-an-exception-request"></a>예외 요청을 평가 하는 방법

예외 요청을 검토할 때는 다음 순서 대로 이러한 요인을 평가 합니다.
 
1.  Microsoft Managed Desktop이 모든 장치에 배포 되는 일부 응용 프로그램 및 정책은 negotiable 되지 않으므로 요청이 해당 사용자에 게 영향을 주지 않도록 해야 합니다. 자세한 내용은 [장치 구성](device-policies.md) 를 참조 하세요.
2.  최종 사용자가 작업을 수행 하는 데 필요한 제한 된 생산성 소프트웨어가 승인 될 수 있습니다. 
3.  Microsoft 기술을 사용 하 여 요구 사항을 충족 하는 경우에는 프로젝트 범위에 따라 3 ~ 12 개월의 예외 마이그레이션 기간에 대 한 요청을 승인할 수 있습니다.
4.  Microsoft 기술을 사용 하 여 요구 사항을 충족할 수 없는 경우에는 다음 조건 중 하나를 위반 하는 경우를 제외 하 고 요청을 승인할 가능성이 높습니다.  

이러한 원칙은 Microsoft Managed Desktop이 표준 서식 파일의 편차를 추적 하는 동안 항상 필요한 사항을 충족할 수 있도록 합니다. 

## <a name="key-conditions"></a>주요 조건

다음 조건에 위반 되지 않도록 예외를 검토 합니다.

-   예외는 시스템 보안에 악영향을 미치지 않아야 합니다. 
-   예외를 유지 관리 하는 경우 Microsoft Managed Desktop 작업 또는 지원에 상당한 비용이 드는 것은 아닙니다.
-   예외는 커널 모드를 중단 시키거나 중단 시키는 등 시스템 안정성에는 영향을 주지 않아야 합니다.
-   서비스를 운영 하거나 핵심 Microsoft Managed Desktop 기술과의 충돌을 허용 하지 않도록 변경 해야 합니다.

이러한 조건은 나중에 변경 될 수 있습니다. 이러한 변경 작업을 수행 하는 경우 해당 조건이 적용 되기 전에 30 일 전에 알림이 제공 됩니다.  Microsoft Managed Desktop이 승인 된 예외를 충족 하는 대체 방법을 제공 하는 경우 Microsoft Managed Desktop은 Microsoft Managed Desktop이 예외를 지 원하는 방식으로 변경 되는 것을 고객에 게 알립니다. 

## <a name="revoking-approval-for-an-exception"></a>예외에 대 한 승인 해지

요청 된 예외를 승인 및 배포한 후에는 변경 내용을 처음으로 승인 했을 때 명확 하지 않은 주요 상황을 위반 하는 문제를 발견할 수 있습니다. 이 상황에서는 예외에 대 한 승인을 취소 해야 할 수 있습니다.
 
이 경우 Microsoft 관리 되는 데스크톱 관리 포털을 사용 하 여 사용자에 게 알림 메시지를 표시 합니다. 사용자에 게 처음 알릴 때 90 일 동안 예외를 제거 해야 예외가 있는 장치가 Microsoft Managed Desktop service 수준 계약에 의해 더 이상 바인딩되지 않습니다. 엄격한 시간 표시 막대에 따라 여러 알림을 전송 하지만, 심각한 사고나 위협으로 인해 시간 표시 막대 또는 예외에 대 한 결정을 변경 해야 할 수 있습니다. 사용자의 동의 없이 예외를 *제거* 하는 것은 아니지만 해지 된 예외가 있는 모든 장치는 더 이상 서비스 수준 계약에 따라 바인딩되지 않습니다. 다음은 사용자에 게 보낼 알림의 시간 표시 막대입니다.

- **첫 번째 알림:** Microsoft는이를 철회 하는 이유에 대 한 정보, 수행 해야 하는 작업, 해당 작업에 대 한 마감일, 의사 결정을 원하는 경우 따라야 하는 단계를 비롯 하 여 승인 취소 결정에 대 한 첫 번째 알림을 제공 합니다. 이는 모든 장치에서 예외를 제거 해야 하기 전까지 90 일 전에 진행 됩니다. 
- **두 번째 알림 (30 일 후):** 첫 번째 주의 사항에 제공 된 것과 동일한 정보를 포함 하 여 두 번째 알림을 제공 합니다. 
- **세 번째 알림 (첫 번째 알림 이후 60 일):** 첫 번째 주의 사항에 제공 된 것과 동일한 정보를 포함 하 여 세 번째 알림을 제공 합니다. 
- **최종 알림 (90 일 마감 날짜 1 주 전):** 여기서는 첫 번째 주의 사항에 제공 된 것과 동일한 정보를 포함 하 여 네 번째 알림을 제공 합니다.
- **첫 번째 알림 이후 90 일:** Microsoft Managed Desktop 서비스 수준 계약은 해당 예외가 해지 된 모든 장치에 더 이상 적용 되지 않습니다. 언제 든 지 의사 결정을 시도 하 고 업그레이드, 구성 변경 또는 소프트웨어 변경을 포함 하 여 고려 사항에 대 한 추가 정보를 제공할 수 있습니다. 


