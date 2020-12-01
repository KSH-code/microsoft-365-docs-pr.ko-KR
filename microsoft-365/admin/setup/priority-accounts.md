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
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477616"
---
# <a name="manage-and-monitor-priority-accounts"></a>우선 순위 계정 관리 및 모니터링

모든 Microsoft 365 조직에는 임원, 리더, 관리자 또는 중요, 독점 또는 높은 우선 순위 정보에 대 한 액세스 권한이 있는 다른 사용자와 같은 필수 사용자가 있습니다.

조직에서 이러한 계정을 보호 하기 위해 이제 특정 사용자를 우선 순위 계정으로 지정 하 고 추가 보호 기능을 제공 하는 앱 관련 기능은 활용할 수 있습니다. 나중에 더 많은 앱과 기능에서 우선 순위 계정을 지원 하 고 시작 하기 위해 **우선 순위 계정 보호** 및 **프리미엄 메일 흐름 모니터링** 이라는 두 가지 기능을 발표 했습니다.

- **우선 순위 계정 보호** -Microsoft Defender for office 365 (이전의 Office 365 Advanced Threat protection)에서는 알림, 보고서 및 조사의 필터에 사용할 수 있는 태그로 우선 순위 계정을 지원 합니다. 자세한 내용은 [Microsoft Defender For Office 365에서 사용자 태그](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)를 참조 하세요.
- **프리미엄 메일 흐름 모니터링** -정상 메일 흐름은 비즈니스 성공을 위해 중요할 수 있으며 배달 지연 또는 실패는 비즈니스에 부정적인 영향을 줄 수 있습니다. 실패 하거나 지연 된 전자 메일에 대 한 임계값을 선택 하 고 해당 임계값이 초과 되 면 알림을 수신 하 고 우선 순위 계정의 전자 메일 문제에 대 한 보고서를 볼 수 있습니다. 자세한 내용은 [최신 EAC에서 우선 순위 계정의 전자 메일 문제](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)를 확인 하세요.

## <a name="before-you-begin"></a>시작하기 전에

이 항목에서 설명 하는 **우선 순위 계정 보호** 기능은 조직에서 다음 요구 사항을 충족 하는 경우에만 사용할 수 있습니다.

- Office 365 E3, Office 365 E5, Microsoft 365 E5 또는 Microsoft 365 E5 Security를 포함 하는 microsoft Defender for Office 365 계획 2

이 항목에서 설명 하는 **프리미엄 메일 흐름 모니터링** 기능은 조직에서 다음 요구 사항을 충족 하는 경우에만 사용할 수 있습니다.

- 조직에는 Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5와 같은 제품의 라이선스 수가 최소 1만이 하 이거나,이 중 하나 또는 그 조합으로 되어 있어야 합니다. 예를 들어 조직에서 3000 Office 365 E3 라이선스 및 8500 Microsoft 365 E5를 보유 하 여 해당 제품의 총 11500 라이선스를 확인할 수 있습니다.
- 조직에는 적어도 50 개의 월간 활성 Exchange Online 사용자가 있어야 합니다.

> [!NOTE]
> 최대 250 개의 우선 순위 계정을 모니터링할 수 있습니다.

### <a name="add-priority-accounts-from-the-setup-page"></a>설정 페이지에서 우선 순위 계정 추가

**설정 페이지** 에서 우선 순위 계정을 추가 합니다.

1. Microsoft 365 관리 센터 ()로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 합니다.

2. **설정**  >  **조직 지식** 으로 이동 하 고 **가장 중요 한 계정 모니터링** 에서 **보기** 를 선택 합니다.

3. **시작** 또는 **관리** 를 선택 합니다.

4. **우선 순위 계정 추가** 페이지의 검색 필드에 우선 순위 계정 목록에 추가할 사용자의 이름이 나 전자 메일 주소를 입력 합니다. 또한 실패 하거나 지연 된 전자 메일에 대 한 전자 메일 임계값을 설정 하 고 우선 순위 계정에 대 한 주간 문제 보고서를 받을 수 있습니다.

5. 사용자를 선택 하 고 **저장** 을 선택 합니다.

활성 사용자 페이지에서 우선 순위 계정을 추가할 수도 있습니다.

### <a name="add-priority-accounts-from-active-users-page"></a>활성 사용자의 우선 순위 계정 추가 페이지

활성 사용자 페이지에서 우선 순위 계정을 추가 합니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

2. **사용자**  >  **활성 사용자** 로 이동 하 여 페이지 맨 위에 있는 **...** 를 선택 합니다. **우선 순위 계정 관리** 를 선택 합니다.

3. **계정 추가** 를 선택 하 고 **우선 순위 계정 추가** 페이지의 검색 필드에 우선 순위 계정 목록에 추가할 사용자의 이름을 입력 합니다.

4. 사용자를 선택 하 고 **저장** 을 선택 합니다.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>우선 순위 계정 목록에서 사용자 제거

1. Microsoft 365 관리 센터 ()로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 합니다.

2. **설정**  >  **조직 지식** 으로 이동 하 고 **가장 중요 한 계정 모니터링** 에서 **보기** 를 선택 합니다.

3. **가장 많은 계정 모니터링** 페이지의 **이 기능 관리** 에서 **우선 순위 계정을** 선택 합니다.

4. **우선 순위 계정** 페이지에서 목록에서 제거할 사용자를 하나 이상 선택 하 고 **계정 제거** 를 선택 합니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365에서 우선 순위 계정 사용](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)