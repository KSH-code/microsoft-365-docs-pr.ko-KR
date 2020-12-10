---
title: 메일 흐름 대시보드의 큐 정보
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
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 큐 위젯을 사용하여 아웃바운드 커넥터를 통해 해당 & 또는 파트너 조직으로의 메일 흐름의 실패를 모니터링하는 방법을 배울 수 있습니다.
ms.openlocfilehash: c582a7f459d89fa1515713c4f55dea14b619a6ec
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616395"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>보안 및 준수 센터에서 & 정보를 큐에 들이기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


커넥터를 사용하여 조직에서 사용자 조직 또는 파트너 전자 메일 서버로 메시지를 보낼 수 없는 경우 메시지는 Microsoft 365에서 대기됩니다. 이 조건을 발생하게 하는 일반적인 예는 다음과 같습니다.

- 커넥터가 잘못 구성되었습니다.
- On-premises 환경에서 네트워킹 또는 방화벽이 변경되었습니다.

Microsoft 365는 24시간 동안 배달을 계속 다시 시도합니다. 24시간이 지난 후 메시지는 만료되고 배달되지 않은 보고서(NDRs 또는 반송 메시지라고도 알려지음)에서 보낸 사람에 반환됩니다.

대기 중인 전자 메일 볼륨이 미리 정의된 임계값(기본값은 200개 메시지)을 초과하면 다음 위치에서 정보를 사용할 수 있습니다.

- 보안 **및** 준수 [](mail-flow-insights-v2.md) 센터의 메일 흐름 대시보드에서 [& 정보를 제공합니다.](https://protection.office.com) 자세한 내용은 이 항목의 메일 흐름 대시보드 [섹션에서 큐](#queues-insight-in-the-mail-flow-dashboard) 정보를 참조하십시오.

- 경고는 보안  및 준수 센터(경고 대시보드 또는 &)의 경고 [대시보드에](https://protection.office.com) 최근 \> **경고에** <https://protection.office.com/alertsdashboard> 표시됩니다.

  ![보안 및 준수 센터의 경고 대시보드에서 & 최근 경고](../../media/mfi-queued-messages-alert.png)

- 관리자는 **Messages라는** 기본 경고 정책의 구성에 따라 전자 메일 알림을 받게 됩니다. 이 경고에 대한 알림 설정을 구성하려면 다음 섹션을 참조하세요.

  경고 정책에 대한 자세한 내용은 보안 및 준수 센터의 [경고 & 참조하세요.](../../compliance/alert-policies.md)

## <a name="customize-queue-alerts"></a>큐 경고 사용자 지정

1. 보안 & 규정 준수 [센터에서](https://protection.office.com)경고  경고 정책으로 이동하거나 \>  를 열 수 <https://protection.office.com/alertpolicies> 있습니다.

2. 경고 정책 **페이지에서** **Messages라는** 정책이 지연된 경우를 찾아 선택합니다.

3. 메시지가 **지연된** 플라이아웃이 열리면 알림을 켜거나 끄고 알림 설정을 구성할 수 있습니다.

   ![메시지가 지연된 경고 정책 세부 정보 보안 및 & 센터](../../media/mfi-queued-messages-alert-policy.png)

   - **상태:** 경고를 설정 또는 해제할 수 있습니다.

   - **전자 메일 받는 사람** 및 **일별 알림 제한:** **편집을** 클릭하여 다음 설정을 구성합니다.

4. 알림 설정을 구성하려면 편집을 **클릭합니다.** 나타나는 **정책** 플라이아웃 편집에서 다음 설정을 구성합니다.

   - **전자 메일 알림 보내기:** 기본값이 설정되어 있습니다.
   - **전자 메일 받는 사람:** 기본값은 **TenantAdmins입니다.**
   - **일별 알림 제한:** 기본값은 **No limit입니다.**
   - **임계값:** 기본값은 200입니다.

   ![메시지의 알림 설정이 지연된 경고 정책 세부 정보 보안 & 준수 센터](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. 완료되면 저장 및 닫기 **를** **클릭합니다.**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>메일 흐름 대시보드의 큐 정보

대기 중인 메시지 볼륨이 임계값을 초과하고 경고를 생성하지 않은 경우에도 메일 흐름 대시보드의 **큐** 정보를 사용하여 1시간 넘게 대기된 메시지를 보고 대기 중인 메시지 수가 너무 커지기 전에 조치를 취할 수 있습니다. [](mail-flow-insights-v2.md)

![보안 및 준수 센터의 메일 흐름 대시보드에서 & 위젯](../../media/mfi-queues-widget.png)

위젯에서 메시지 수를 클릭하면 메시지 대기  플라이아웃이 다음 정보와 함께 표시됩니다.

- **대기 중인 메시지 수**
- **커넥터 이름:** 커넥터 이름을 클릭하여 EAC(Exchange 관리 센터)에서 커넥터를 관리합니다.
- **큐 시작 시간**
- **만료된 가장 오래된 메시지**
- **대상 서버**
- **마지막 IP 주소**
- **마지막 오류**
- **해결 방법**: 일반적인 문제 및 해결 방법을 사용할 수 있습니다. If is a **Fix it now** link is available, click it to fix the problem. 그렇지 않은 경우 사용 가능한 링크를 클릭하여 오류 및 가능한 해결 방법과 관련한 자세한 정보를 제공합니다.

![메일 흐름 대시보드에서 큐 정보를 클릭한 후의 세부 정보](../../media/mfi-queues-details.png)

경고가 지연된 메시지의  세부 정보에서 큐 보기를 클릭하면 동일한 플라이아웃이 **표시됩니다.**

![보안 및 준수 센터에서 메시지가 지연된 & 있습니다.](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)
