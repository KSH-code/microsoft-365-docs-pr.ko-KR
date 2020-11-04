---
title: 메일 흐름 대시보드의 큐 통찰력
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 큐 위젯을 사용 하 여 아웃 바운드 커넥터를 통해 온-프레미스 또는 파트너 조직으로의 실패 한 메일 흐름을 모니터링 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e6935793cd04c6072784cd20b55649126864c369
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877576"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>보안 & 준수 센터의 큐 통찰력

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


커넥터를 사용 하 여 조직에서 온-프레미스 또는 파트너 전자 메일 서버로 메시지를 보낼 수 없는 경우 해당 메시지는 Microsoft 365에서 대기 됩니다. 이러한 상황을 일으키는 일반적인 예는 다음과 같습니다.

- 커넥터가 올바르게 구성 되지 않았습니다.
- 온-프레미스 환경에 네트워킹이 나 방화벽이 변경 되었습니다.

Microsoft 365는 24 시간 동안 배달을 계속 해 서 다시 시도 합니다. 24 시간 후에는 메시지가 만료 되어 배달 못 함 보고서 (Ndr 또는 바운스 메시지로도 알려짐)의 보낸 사람에 게 반환 됩니다.

대기 중인 전자 메일 볼륨이 미리 정의 된 임계값을 초과 하는 경우 (기본값은 200 메시지), 다음 위치에서 정보를 사용할 수 있습니다.

- **큐** 는 [보안 & 준수 센터](https://protection.office.com)의 [메일 흐름 대시보드에](mail-flow-insights-v2.md) 있습니다. 자세한 내용은이 항목의 [메일 흐름 대시보드 섹션에 있는 큐 통찰력](#queues-insight-in-the-mail-flow-dashboard) 를 참조 하세요.
  
- 경고가 **최근 경고** 에 표시 됨 [보안 & 준수 센터](https://protection.office.com) ( **경고** \> **대시보드** 또는)의 알림 대시보드 <https://protection.office.com/alertsdashboard>

  ![보안 & 준수 센터의 알림 대시보드의 최근 경고](../../media/mfi-queued-messages-alert.png)

- 관리자는 **메시지가 지연** 된 기본 경고 정책의 구성에 따라 전자 메일 알림을 받습니다. 이 경고에 대 한 알림 설정을 구성 하려면 다음 섹션을 참조 하십시오.

  경고 정책에 대 한 자세한 내용은 [Security & 준수 센터의 경고 정책](../../compliance/alert-policies.md)를 참조 하십시오.

## <a name="customize-queue-alerts"></a>큐 알림 사용자 지정

1. [보안 & 준수 센터](https://protection.office.com)에서 **알림** \> **경고 정책** 으로 이동 하거나 엽니다 <https://protection.office.com/alertpolicies> .

2. **경고 정책** 페이지에서 **메시지가 지연** 된 정책을 찾아서 선택 합니다.

3. 메시지의 플라이 아웃이 **지연 된** 경우 알림을 켜거나 끄고 알림 설정을 구성할 수 있습니다.

   ![메시지가 지연 됨 경고 정책 세부 정보 보안 & 준수 센터](../../media/mfi-queued-messages-alert-policy.png)

   - **상태** : 알림을 설정 하거나 해제할 수 있습니다.

   - **전자 메일 받는 사람** 및 **일별 알림 제한** : **편집** 을 클릭 하 여 다음 설정을 구성 합니다.

4. 알림 설정을 구성 하려면 **편집** 을 클릭 합니다. 표시 되는 정책 플라이 아웃 **편집** 에서 다음 설정을 구성 합니다.

   - **전자 메일 알림 보내기** : 기본값은 on입니다.
   - **전자 메일 받는 사람** : 기본값은 **tenantadmins** 입니다.
   - **일별 알림 제한** : 기본값은 **제한이 없습니다**.
   - **임계값** : 기본값은 200입니다.

   ![메시지의 알림 설정이 지연 됨 경고 정책 세부 정보 보안 & 준수 센터](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. 작업이 완료 되 면 **저장** 후 **닫기를** 클릭 합니다.

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>메일 흐름 대시보드의 큐 통찰력

대기 중인 메시지 볼륨이 임계값을 초과 하지 않고 경고가 생성 된 경우에도 [메일 흐름 대시보드에](mail-flow-insights-v2.md) **큐** 통찰력을 사용 하 여 1 시간 이상 대기 된 메시지를 확인 하 고 대기 중인 메시지 수가 너무 커지지 않으면 조치를 취할 수 있습니다.

![보안 & 준수 센터의 메일 흐름 대시보드의 큐 위젯](../../media/mfi-queues-widget.png)

위젯의 메시지 수를 클릭 하면 다음 정보와 함께 **대기 중인 메시지** 플라이 아웃이 나타납니다.

- **대기 중인 메시지 수**
- **커넥터 이름** : Exchange 관리 센터 (EAC)에서 커넥터를 관리 하려면 커넥터 이름을 클릭 합니다.
- **큐 시작 시간**
- **가장 오래 된 메시지가 만료 됨**
- **대상 서버**
- **마지막 IP 주소**
- **마지막 오류**
- **해결 방법** : 일반적인 문제 및 해결 방법을 사용할 수 있습니다. **지금 해결** 방법을 사용할 수 있는 경우에는이 링크를 클릭 하 여 문제를 해결 합니다. 그렇지 않으면 사용 가능한 링크를 클릭 하 여 오류 및 가능한 해결 방법에 대 한 자세한 내용을 확인할 수 있습니다.

![메일 흐름 대시보드에서 큐 통찰력을 클릭 한 후의 세부 정보](../../media/mfi-queues-details.png)

메시지 세부 정보에서 **큐 보기** 를 클릭 하 여 경고를 **지연** 한 후에 동일한 플라이 아웃이 표시 됩니다.

![보안 & 준수 센터에서 메시지의 알림 세부 정보가 지연 되었습니다.](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.
