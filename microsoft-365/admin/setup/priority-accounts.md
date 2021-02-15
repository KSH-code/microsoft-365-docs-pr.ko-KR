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
description: 비즈니스에 큰 영향을 미치는 계정으로 보내거나 보낸 실패 및 지연된 전자 메일 메시지를 모니터링합니다.
ms.openlocfilehash: dbdd692a41d341564376960788054e70623daf5a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233365"
---
# <a name="manage-and-monitor-priority-accounts"></a>우선 순위 계정 관리 및 모니터링

모든 Microsoft 365 조직에는 중요, 소유 정보 또는 높은 우선 순위 정보에 액세스할 수 있는 임원, 리더, 관리자 또는 기타 사용자와 같이 필수인 사람이 있습니다.

조직에서 이러한 계정을 보호하도록 지원하기 위해 이제 특정 사용자를 우선 순위 계정으로 지정하고 추가 보호를 제공하는 앱별 기능을 활용할 수 있습니다. 앞으로 더 많은 앱 및 기능이 우선 순위 계정을 지원할 예정으로, 우선  순위 계정 보호 및 프리미엄 메일 흐름 모니터링의 두 가지 기능을 **발표했습니다.**

- **우선 순위** 계정 보호 - Office 365용 Microsoft Defender(이전의 Office 365 Advanced Threat Protection)는 경고, 보고서 및 조사에서 필터에 사용할 수 있는 태그로 우선 순위 계정을 지원합니다. 자세한 내용은 Microsoft [Defender for Office 365에서 사용자 태그를 확인하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags)
- **고급 메일 흐름 모니터링** - 정상 메일 흐름은 비즈니스 성공에 중요할 수 있으며 배달 지연 또는 오류는 비즈니스에 부정적인 영향을 미칠 수 있습니다. 실패 또는 지연된 전자 메일에 대한 임계값을 선택하고, 임계값을 초과하면 경고를 수신하고, 우선 순위 계정에 대한 전자 메일 문제 보고서를 볼 수 있습니다. 자세한 내용은 최신 [EAC의](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) 우선 순위 계정 보고서에 대한 전자 메일 문제 확인

우선 순위 계정에 대한 보안 모범 사례는 우선 순위 계정에 [대한 보안 권장 사항을 참조하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts)

## <a name="before-you-begin"></a>시작하기 전에

이 **항목에 설명된** 우선 순위 계정 보호 기능은 다음 요구 사항을 충족하는 조직에서만 사용할 수 있습니다.

- Office 365 E3, Office 365 E5, Microsoft 365 E5 또는 Microsoft 365 E5 보안이 있는 Microsoft Defender를 포함하여 Office 365 계획 2용 Microsoft Defender

이 **항목에 설명된** 고급 메일 흐름 모니터링 기능은 다음 요구 사항을 충족하는 조직에서만 사용할 수 있습니다.

- 조직은 Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5 중 하나 또는 제품의 조합에서 최소 10,000개 이상의 라이선스 수가 필요합니다. 예를 들어 조직에서는 Office 365 E3 라이선스 3,000개와 Microsoft 365 E5 8500을 사용할 수 있으며 적격 제품의 라이선스는 총 11,500개입니다.
- 조직에는 매월 최소 50명의 활성 Exchange Online 사용자가 있어야 합니다.

> [!NOTE]
> 우선 순위 계정을 250개까지 모니터링할 수 있습니다.

### <a name="add-priority-accounts-from-the-setup-page"></a>설치 페이지에서 우선 순위 계정 추가

설치 페이지에서 우선 순위 계정을 **추가합니다.**

1. Go to the Microsoft 365 admin center <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> at.

2. 조직 지식 **설정으로** 이동한 후 가장 중요한 계정 모니터링에서  >   **보기를 선택하십시오.** 

3. 시작 **또는** **관리** 선택 .

4. 우선 **순위** 계정 추가 페이지의 검색 필드에 우선 순위 계정 목록에 추가할 사람의 이름 또는 전자 메일 주소를 입력합니다. 실패 또는 지연된 전자 메일에 대한 전자 메일 임계값을 설정하고 우선 순위 계정에 대한 문제에 대한 주간 보고서를 받을 수도 있습니다.

5. 사용자를 선택하고 저장을 **선택합니다.**

활성 사용자 페이지에서 우선 순위 계정을 추가할 수 있습니다.

### <a name="add-priority-accounts-from-active-users-page"></a>활성 사용자 페이지에서 우선 순위 계정 추가

활성 사용자 페이지에서 우선 순위 계정을 추가합니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

2. 사용자 활성 **사용자로** 이동하여 페이지 맨 위에 있는  >   **...를** 선택합니다. 우선 **순위 계정 관리를 선택합니다.**

3. 계정 **추가를** 선택하고  우선 순위 계정 추가 페이지의 검색 필드에 우선 순위 계정 목록에 추가할 사람의 이름을 입력합니다.

4. 사용자를 선택하고 저장을 **선택합니다.**

## <a name="remove-a-user-from-the-priority-accounts-list"></a>우선 순위 계정 목록에서 사용자 제거

1. Go to the Microsoft 365 admin center <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> at.

2. 조직 지식 **설정으로** 이동한 후 가장 중요한 계정 모니터링에서  >   **보기를 선택하십시오.** 

3. On the **Monitor your most accounts** page, choose Priority **accounts** under Manage **this feature.**

4. 우선 **순위 계정** 페이지에서 목록에서 제거할 사용자를 선택하고 계정을 **제거합니다.**

## <a name="related-topics"></a>관련 항목

[Microsoft 365에서 우선 순위 계정 사용](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)