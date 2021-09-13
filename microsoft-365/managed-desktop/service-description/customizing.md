---
title: 서비스 계획에 대한 예외
description: 표준 서비스 계획에 대한 예외를 요청하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 59a2b8227eb7e410ecf8506ce288978213537edc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215382"
---
# <a name="exceptions-to-the-service-plan"></a>서비스 계획에 대한 예외

Microsoft Managed Desktop 장치 [목록,](device-policies.md)표준 장치 설정, 응용 프로그램 요구 [](../working-with-managed-desktop/config-setting-overview.md)사항 및 구성 가능한 특정 설정 모두 사용자에게 안전하고 생산적인 환경을 제공하도록 설계된 특정 구성 가능한 설정을 제공합니다. 항상 제공된 서비스를 유지 하는 것이 가장 좋은 것입니다. 그러나 서비스의 일부 세부 정보는 조직의 요구에 정확히 맞지 않을 수 있습니다. 서비스를 변경해야 하는 경우 다음 프로세스에 따라 변경 내용을 요청하는 것이 중요합니다.
 
## <a name="types-of-exceptions"></a>예외 유형

예외는 기본 구성에 대한 추가 Microsoft Managed Desktop 있습니다. 예제에는 USB 포트 구성에서 새 장치 드라이버 배포에 대한 예제가 있습니다. 다음과 같이 다양한 예외를 그룹화합니다.

|유형  |설명  |
|---------|---------|
|생산성 소프트웨어     |  응용 프로그램 요구 사항에 따라 제한되는 사용자가 필요로 하는 포그라운드 [소프트웨어](mmd-app-requirements.md)       |
|VPN을 & 보안 에이전트     |  장치 또는 네트워크의 동작을 보호, 모니터링 또는 변경하는 데 사용되는 소프트웨어       |
|디지털 환경 모니터링     |  IT에 보고하기 위해 사용자의 장치에서 데이터를 추적하는 데 사용되는 소프트웨어       |
|하드웨어 또는 소프트웨어 드라이버     |   응용 프로그램 요구 사항에 따라 제한되는 [장치 드라이버](mmd-app-requirements.md)      |
|정책     | Windows 10 엔터프라이즈용 Microsoft 365 앱 설정 또는 설정 관리        |
|디바이스     | 디바이스 목록에 없는 Microsoft Managed Desktop [장치](device-list.md)        |
|기타     |  다른 영역에서 다루지 않는 모든 것       |
 
## <a name="request-an-exception"></a>예외 요청

변경 요청을 만들어 Microsoft Managed Desktop 관리 포털을 통해 요청을 제출합니다. 다음 세부 정보를 포함해야 합니다.

- 예외 유형: 예외의 범주는 무엇입니까? (이전 표 참조)
- 요구 사항: 예외에 대한 특정 비즈니스 요구 사항은 무엇입니까?
- 제안: 비즈니스에서 요청하는 해결 방법은 무엇입니까?
- 시간 표시 막대: 이 예외를 지속하려면 얼마나 오래 하나요? 

## <a name="how-we-assess-an-exception-request"></a>예외 요청을 평가하는 방법

예외 요청을 검토할 때 다음 순서로 이러한 요소를 평가합니다.
 
1. 일부 응용 프로그램 및 Microsoft Managed Desktop 모든 장치에 배포하는 정책은 반드시 적용될 수 없습니다. 따라서 요청이 이러한 응용 프로그램에 영향을 주지 않습니다. 자세한 [내용은 장치 구성을](device-policies.md) 참조하세요.
2. 사용자가 작업을 하는 데 필요한 제한된 생산성 소프트웨어가 승인될 수 있습니다. 
3. Microsoft 기술을 사용하여 요구 사항을 충족할 수 있는 경우 프로젝트 범위에 따라 3~12개월의 예외 마이그레이션 기간에 대한 요청을 승인할 수 있습니다.
4. Microsoft 기술을 사용하여 요구 사항을 충족할 수 없는 경우 아래 조건 중 하나를 위반하지 않는 한 요청을 승인할 수 있습니다.  

이러한 원칙은 표준 Microsoft Managed Desktop 편차를 추적하면서 항상 요구 사항을 충족할 수 있도록 보장합니다. 

## <a name="key-conditions"></a>주요 조건

예외를 검토하여 이러한 조건을 위반하지 않도록 합니다.

- 예외가 시스템 보안에 부정적인 영향을 주면 안 됩니다. 
- 예외를 유지 관리하면 모든 작업 또는 지원에 Microsoft Managed Desktop 않습니다.
- 예를 들어 커널 모드가 충돌하거나 중단되는 등 시스템 안정성에 영향을 주지 않는 예외가 있습니다.
- 이 변경으로 서비스 운영이 제한되거나 핵심 기술 및 Microsoft Managed Desktop 없습니다.

이러한 조건은 향후 변경될 수 있습니다. 이러한 변경을 하는 경우 해당 조건이 적용될 30일 전에 30일 알림이 제공될 것입니다.  승인된 Microsoft Managed Desktop 충족하는 다른 방법을 제공하는 경우 Microsoft Managed Desktop 예외를 지원하는 Microsoft Managed Desktop 변경해야 한다고 고객에게 알릴 수 있습니다. 

## <a name="revoking-approval-for-an-exception"></a>예외에 대한 승인 취소

요청된 예외가 승인 및 배포된 후 처음에 변경을 승인할 때 발견되지 않은 주요 조건을 위반하는 문제를 발견할 수 있습니다. 이 경우 예외에 대한 승인을 취소해야 할 수 있습니다.
 
이 경우 관리자 포털을 사용하여 Microsoft Managed Desktop 알릴 것입니다. 예외가 있는 디바이스가 더 이상 서비스 수준 계약에 의해 바인딩되지 Microsoft Managed Desktop 90일 전에 예외를 제거할 수 있습니다. 엄격한 타임라인에 따라 몇 가지 알림을 보내드릴 것입니다. 그러나 심각한 인시던트나 위협이 발생하면 타임라인이나 예외에 대한 결정을 변경해야 할 수 있습니다. 동의 없이  예외를 제거하지는 않지만 해지된 예외가 있는 장치는 더 이상 서비스 수준 계약에 의해 바인딩되지 않습니다. 다음은 전송할 알림의 타임라인입니다.

- **첫 번째 알림:** 승인 취소 결정에 대한 첫 번째 공지를 제공합니다. 예를 들어 승인을 취소하는 이유, 취할 것을 권고하는 작업, 해당 작업의 기한, 결정에 이의를 제기하려는 경우 수행할 단계에 대한 정보가 있습니다. 이 알림은 예외를 모든 장치에서 제거해야 하기 전에 90일 전에 발생합니다. 
- **두 번째 알림(30일 이후):** 첫 번째 알림에 제공된 동일한 정보를 포함하여 두 번째 공지를 제공합니다. 
- 세 번째 알림(첫 번째 알림 후 **60일 후):** 첫 번째 알림에 제공된 동일한 정보를 포함하여 세 번째 통지를 제공합니다. 
- **최종 공지(90일 마감일 1주 전):** 첫 번째 알림에 제공된 동일한 정보를 포함하여 네 번째 알림이 제공됩니다.
- 첫 번째 알림 후 **90일:** Microsoft Managed Desktop 서비스 수준 계약은 해지된 예외가 있는 장치에 더 이상 적용되지 않습니다. 업그레이드, 구성 변경 또는 소프트웨어 변경을 포함하여 결정을 내리고 고려할 추가 정보를 제공할 수 있습니다. 


