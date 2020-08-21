---
title: 메일 흐름 대시보드의 큐 인사이트
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 큐 위도를 사용하여 아웃바운드 커넥터를 통해 온-프레미스 또는 파트너 조직으로의 실패한 메일 흐름을 모니터링하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 79523533306e847988fa0d4e2dd70eca22f7c76c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826908"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>준수 센터에서 보안 & 큐 정보

조직에서 커넥터를 사용하여 메시지를 온-프레미스 또는 파트너 전자 메일 서버로 보낼 수 않으면 메시지가 Microsoft 365에서 대기하고 대기됩니다. 이 조건이 일어하는 일반적인 예는 다음과 같습니다.

- 커넥터가 잘못 구성되었습니다.
- 온-프레미스 환경에 네트워킹 또는 방화벽이 변경되었습니다.

Microsoft 365에서는 24시간 동안 계속 해서 배달을 다시 시도합니다. 24시간 후 메시지는 만료되어 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)의 보낸 사람에게 반환됩니다.

대기된 전자 메일 볼륨이 미리 정의된 임계값(기본값: 200개 메시지)을 초과하면 다음 위치에서 정보를 사용할 수 있습니다.

- **준수 센터의** 보안 흐름 [대시보드에 있는](mail-flow-insights-v2.md) & 큐 정보 자세한 내용은 이 [항목의 메일 흐름 대시보드 섹션에 있는 큐 정보를](#queues-insight-in-the-mail-flow-dashboard) 참조하십시오.
  
- 준수 센터(경고 **대시보드 또는)를** 사용하여 보안 및 [& 알림](https://protection.office.com) 대시보드의 알림**대시보드에** \> **경고가 표시됩니다.** <https://protection.office.com/alertsdashboard>

  ![보안 그룹 규정 준수 센터의 알림 &](../../media/mfi-queued-messages-alert.png)

- 관리자는 메시지가 지연된 기본 경고 정책의 구성을 기반으로 전자 **메일 알림을 받게 됩니다.** 이 경고에 대한 알림 설정을 구성하려면 다음 섹션을 참조하세요.

  경고 정책에 대한 자세한 내용은 보안 [센터 의 보안 센터에서 & 합니다.](../../compliance/alert-policies.md)

## <a name="customize-queue-alerts"></a>큐 경고 사용자 지정

1. 보안 [그룹 준수 & 이동하여](https://protection.office.com)경고 **정책으로** \> **이동하거나 엽니다.** <https://protection.office.com/alertpolicies>

2. 경고 **정책 페이지에서** Messages라는 **정책을 찾아서 선택합니다.**

3. 메시지가 **지연된 플라이아웃이** 열리면 알림을 설정하거나 해제하고 알림 설정을 구성할 수 있습니다.

   ![메시지가 준수 센터의 보안 정책에 대한 & 있습니다.](../../media/mfi-queued-messages-alert-policy.png)

   - **상태:** 알림을 설정하거나 해제할 수 있습니다.

   - **메일 받는** 사람 **및 일별 알림 제한:** 편집을 **클릭하여 다음** 설정을 구성합니다.

4. 알림 설정을 구성하려면 편집을 **클릭합니다.** 표시되는 **Edit policy** 정책 플라이아웃에서 다음 설정을 구성합니다.

   - **메일 보내기 알림:** 기본값은 On.
   - **메일 받는**사람: 기본값은 **TenantAdmins입니다.**
   - **일별 알림 제한:** 기본값은 **없음 입니다.**
   - **임계값:** 기본값은 200입니다.

   ![메시지의 알림 설정은 준수 센터의 보안 정책 세부 & 줍니다.](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. 작업을 마치면 저장을 클릭하고 **닫습니다.** **Save**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>메일 흐름 대시보드의 큐 인사이트

대기된 메시지 볼륨이 임계값을 초과하지 않고 경고를 생성한 경우에도 계속 메일 흐름 대시보드의 큐 정보를 사용하여 대기 중이어서 큐에 대기된 메시지를 확인하고 대기된 메시지 수가 너무 커지기 전에 작업을 수행할 수 있습니다. **Queues** [Mail flow dashboard](mail-flow-insights-v2.md)

![보안 흐름 대시보드의 큐 & 위내](../../media/mfi-queues-widget.png)

위에서 메시지 수를 클릭하면 대기된 **플라이아웃이** 다음 정보와 함께 표시됩니다.

- **대기된 메시지 수**
- **커넥터 이름:** EAC(Exchange 관리 센터)에서 커넥터 이름을 클릭하여 커넥터를 관리합니다.
- **큐 시작 시간**
- **만료된 가장 오래된 메시지**
- **대상 서버**
- **마지막 IP 주소**
- **마지막 오류**
- **해결 방법: 일반적인**문제 및 해결 방법을 사용할 수 있습니다. 이제 링크를 **사용할 수 있는** 경우 해당 링크를 클릭하여 문제를 해결합니다. 그렇지 않으면 오류 및 가능한 해결 방법에 대한 자세한 내용을 확인하기 위해 사용 가능한 링크를 클릭하세요.

![메일 흐름 대시보드에서 큐 정보를 클릭하면 수행되는 세부 정보](../../media/mfi-queues-details.png)

메시지의 세부 정보에서 큐보기를 **클릭하면** **경고가 지연된 경우 동일한 플라이아웃이 표시됩니다.**

![준수 센터에 메시지가 지연되어 & 있습니다.](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)
