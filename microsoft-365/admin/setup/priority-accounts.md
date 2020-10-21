---
title: 우선 순위 계정 관리 및 모니터링
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: 비즈니스에 큰 영향을 주는 계정에서 보내거나 받은 전자 메일로 인 한 실패 및 지연 된 메시지를 모니터링 합니다.
ms.openlocfilehash: ce78316290f18f06337adc0e78a1b8992be7b425
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644594"
---
# <a name="manage-and-monitor-priority-accounts"></a>우선 순위 계정 관리 및 모니터링

Microsoft 365 조직의 관리자는 이제 CEO와 같이 비즈니스에 큰 영향을 주는 사용자에 게 전송 되는 실패 또는 지연 된 전자 메일 메시지를 모니터링할 수 있습니다. 우선 순위 계정 목록에 사용자를 추가 하 여이 기능을 사용 하도록 설정할 수 있습니다. 우선 순위 계정은 조직을 실행 하는 데 반드시 필요한 계정입니다. 중요 하거나 높은 우선 순위 정보에 대 한 액세스 권한이 있는 임원, 리더, 관리자 또는 기타 사용자를 추가 합니다.

## <a name="access-priority-accounts"></a>액세스 우선 순위 계정

이 항목에서 설명 하는 우선 순위 계정 기능은 조직 에서만 다음 요구 사항을 충족 해야 합니다.

- Office 365 E3 또는 Microsoft 365 E3, 또는 Office 365 E5 또는 Microsoft 365 E5
- 최소 1만의 라이선스 및 최소 50의 월간 활성 Exchange Online 사용자

## <a name="add-priority-accounts-from-the-setup-page"></a>설정 페이지에서 우선 순위 계정 추가

**설정 페이지**에서 우선 순위 계정을 추가 합니다.

1. Microsoft 365 관리 센터 ()로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 합니다.

2. **설정**  >  **조직 지식**으로 이동 하 고 **가장 중요 한 계정 모니터링**에서 **보기** 를 선택 합니다.

3. **시작** 또는 **관리**를 선택 합니다.

4. **우선 순위 계정 추가** 페이지의 검색 필드에 우선 순위 계정 목록에 추가할 사용자의 이름이 나 전자 메일 주소를 입력 합니다. 또한 실패 하거나 지연 된 전자 메일에 대 한 전자 메일 임계값을 설정 하 고 우선 순위 계정에 대 한 주간 문제 보고서를 받을 수 있습니다.

5. 사용자를 선택 하 고 **저장**을 선택 합니다.

활성 사용자 페이지에서 우선 순위 계정을 추가할 수도 있습니다.

### <a name="add-priority-accounts-from-active-users-page"></a>활성 사용자의 우선 순위 계정 추가 페이지

활성 사용자 페이지에서 우선 순위 계정을 추가 합니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

2. **사용자**  >  **활성 사용자**로 이동한 후 페이지 맨 위에 있는 ...를 선택 **합니다** . **우선 순위 계정 관리**를 선택 합니다.

3. **계정 추가**를 선택 하 고 **우선 순위 계정 추가** 페이지의 검색 필드에 우선 순위 계정 목록에 추가할 사용자의 이름을 입력 합니다.

4. 사용자를 선택 하 고 **저장**을 선택 합니다.

## <a name="monitor-your-priority-accounts"></a>우선 순위 계정 모니터링

**설정** 페이지의 Microsoft 365 관리 센터에서 우선 순위 계정의 전자 메일 상태를 모니터링할 수 있습니다. 최대 250 개의 계정을 능동적으로 모니터링할 수 있습니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

2. **설치** 를 선택 하 고 **고급 모니터링** 옆에 있는 **보기** 를 선택 하 여 우선 순위 계정의 상태를 확인 합니다.

## <a name="email-issues-for-priority-accounts"></a>우선 순위 계정에 대 한 전자 메일 문제

Exchange 관리 센터에서 **우선 순위 계정에 대 한 전자 메일 문제** 보고서로 이동 하 여 우선 순위 계정의 전자 메일 문제를 추적할 수 있습니다. 자세한 내용은 [우선 순위 계정의 전자 메일 문제](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)를 확인 하세요.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>우선 순위 계정 목록에서 사용자 제거

1. Microsoft 365 관리 센터 ()로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 합니다.

2. **설정**  >  **조직 지식**으로 이동 하 고 **가장 중요 한 계정 모니터링**에서 **보기** 를 선택 합니다.

3. **가장 많은 계정 모니터링** 페이지의 **이 기능 관리**에서 **우선 순위 계정을** 선택 합니다.

4. **우선 순위 계정** 페이지에서 목록에서 제거할 사용자를 하나 이상 선택 하 고 **계정 제거**를 선택 합니다.