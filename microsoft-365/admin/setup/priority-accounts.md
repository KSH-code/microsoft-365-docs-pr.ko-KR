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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
description: 비즈니스에 큰 영향을 미치는 계정으로 보내거나 보낸 전자 메일로 전송된 실패 및 지연된 전자 메일 메시지를 모니터링합니다.
ms.openlocfilehash: 95d5e703570b3a399335a0c26d7e953a277ccddf
ms.sourcegitcommit: 34259ec9b6cccc8f6e29808dbe4796d9f72b651b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59934206"
---
# <a name="manage-and-monitor-priority-accounts"></a>우선 순위 계정 관리 및 모니터링

모든 Microsoft 365 조직에는 중요한 정보, 소유 정보 또는 높은 우선 순위 정보에 액세스할 수 있는 임원, 리더, 관리자 또는 기타 사용자와 같이 필수적인 사람이 있습니다.

조직에서 이러한 계정을 보호할 수 있도록 이제 특정 사용자를 우선 순위 계정으로 지정하고 추가 보호를 제공하는 앱별 기능을 활용할 수 있습니다. 앞으로 더 많은 앱 및 기능이 우선 순위 계정을 지원할 예정으로, 우선  순위 계정 보호 및 프리미엄 메일 흐름 모니터링의 두 가지 기능을 **발표했습니다.**

- **우선** 순위 계정 보호 - Microsoft Defender for Office 365(Office 365 Advanced Threat Protection)는 경고, 보고서 및 조사에서 필터에 사용할 수 있는 태그로 우선 순위 계정을 지원합니다. 자세한 내용은 에 대한 [Microsoft Defender의 사용자 태그를 Office 365.](../../security/office-365-security/user-tags.md)

  "모든 사용자가 우선 순위가 아닌가요? 모든 사용자를 우선 순위 계정으로 지정하지 않는 이유는 무엇일까요?" 예, 모든 사용자가 우선 순위이지만 우선 순위 계정 보호는 다음과 같은 추가 이점을 제공합니다.

  - **추가추가:** Microsoft 데이터 센터에서 메일 흐름을 분석하면 회사 임원의 메일 흐름 패턴이 평균 직원과 다르다는 것입니다. 우선 순위 계정 보호는 정규 직원에게 도움이되지 않는 회사 임원에게 특별히 조정된 추가적 이론을 제공합니다.
  - **보고의** 추가 표시 여부: 모든 사용자(또는 영향을 받는 모든 사용자)에 대한 정보는 경고, 보고서 및 조사에서 이미 사용할 수 있습니다. 우선 순위 계정 태그를 필터로 사용하면 특별히 조사 대상을 지정하는 데 사용할 수 있습니다.

- **Premium 메일** Flow 모니터링 - 정상 메일 흐름은 비즈니스 성공에 중요할 수 있으며 배달 지연 또는 오류는 비즈니스에 부정적인 영향을 미칠 수 있습니다. 실패 또는 지연된 전자 메일에 대한 임계값을 선택하고, 해당 임계값을 초과하면 경고를 수신하고, 우선 순위 계정에 대한 전자 메일 문제에 대한 보고서를 볼 수 있습니다. 자세한 내용은 최신 [EAC에서](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) 우선 순위 계정 보고서에 대한 전자 메일 문제 확인

우선 순위 계정에 대한 보안 모범 사례는 우선 순위 계정에 [대한 보안 권장 사항을 참조하세요.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)

## <a name="before-you-begin"></a>시작하기 전에

이 **항목에 설명된** 우선 순위 계정 보호 기능은 다음 요구 사항을 충족하는 조직에서만 사용할 수 있습니다.

- Microsoft Defender for Office 365 Plan 2(Office 365 E3, Office 365 E5, Microsoft 365 E5 또는 Microsoft 365 E5 Security.

이 **Premium 메일** Flow 모니터링 기능은 다음 요구 사항을 충족하는 조직에서만 사용할 수 있습니다.

- 조직에서는 라이선스 수가 5,000개 이상(예: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. 예를 들어 조직에서는 적격 제품 총 5,500개의 라이센스에 대해 3,000개의 Office 365 E3 라이선스 및 2,500개의 Microsoft 365 E5 라이선스를 보유할 수 있습니다.
- 조직은 하나 이상의 핵심 워크로드(Teams, 비즈니스용 One Drive, SharePoint Online, Exchange Online 및 Office 앱에 대해 월별 활성 사용자가 50명 이상 Office 합니다.

> [!NOTE]
> 최대 250개 우선 순위 계정을 모니터링할 수 있습니다.

사서함에 우선 순위 계정 보호를 적용할 때 사서함에 액세스할 수 있는 사용자(예: CEO 및 CEO의 일정을 관리하는 CEO의 임원 비서)에도 우선 순위 계정 보호를 적용해야 합니다.

### <a name="add-priority-accounts-from-the-setup-page"></a>설치 페이지에서 우선 순위 계정 추가

설치 페이지에서 우선 순위 **계정을 추가합니다.**

1. 의 Microsoft 365 관리 센터 로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>

2. 조직 정보  >  **설정으로 이동하여** **가장** 중요한 계정 **모니터링에서 보기를 선택하십시오.**

3. 선택 **시작** 또는 **관리 를 선택합니다.**

4. 우선 **순위** 계정 추가 페이지의 검색 필드에 우선 순위 계정 목록에 추가할 사람의 이름 또는 전자 메일 주소를 입력합니다. 실패하거나 지연된 전자 메일에 대한 전자 메일 임계값을 설정하고 우선 순위 계정에 대한 문제에 대한 주간 보고서를 받을 수도 있습니다.

5. 사용자를 선택하고 저장 을 **선택합니다.**

활성 사용자 페이지에서 우선 순위 계정을 추가할 수 있습니다.

### <a name="add-priority-accounts-from-active-users-page"></a>활성 사용자 페이지에서 우선 순위 계정 추가

활성 사용자 페이지에서 우선 순위 계정을 추가합니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

2. 사용자 활성 **사용자로** 이동하여 페이지 맨 위에 있는 세 개의 점(추가 작업)을  >   선택합니다. 우선 **순위 계정 관리를 선택합니다.**

3. 계정 **추가를** 선택하고 우선 순위 계정 추가 **페이지의** 검색 필드에 우선 순위 계정 목록에 추가할 사람의 이름을 입력합니다.

4. 사용자를 선택하고 저장 을 **선택합니다.**

## <a name="remove-a-user-from-the-priority-accounts-list"></a>우선 순위 계정 목록에서 사용자 제거

1. 의 Microsoft 365 관리 센터 로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>

2. 조직 정보  >  **설정으로 이동하여** **가장** 중요한 계정 **모니터링에서 보기를 선택하십시오.**

3. On the **Monitor your most accounts** page, choose Priority **accounts** under Manage **this feature**.

4. 우선 **순위 계정** 페이지에서 목록에서 제거할 사용자를 선택하고 계정 **제거를 선택합니다.**

## <a name="related-topics"></a>관련 항목

[2016에서 우선 순위 계정 Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
