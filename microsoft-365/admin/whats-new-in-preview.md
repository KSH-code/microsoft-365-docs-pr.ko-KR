---
title: Microsoft 365 관리 센터의 새로운 기능
f1.keywords:
- CSH
ms.author: anfowler
author: adefowler
manager: shohara
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
- FRP150
description: Microsoft 365 관리 센터-이 달에 추가 된 기능에 대해 알아봅니다.
ms.custom:
- MACDashWhatsNew
- AdminSurgePortfolio
ms.openlocfilehash: 64c9939f7dd6c4370b80e74987263942dad0e62f
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208936"
---
# <a name="whats-new-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터의 새로운 기능

::: moniker range="o365-21vianet"

> [!NOTE]
> 이 문서의 일부 정보는 21Vianet에서 운영 하는 Office 365에 적용 되지 않을 수 있습니다.

::: moniker-end

[Microsoft 365 관리 센터](microsoft-365-admin-center-preview.md)에 지속적으로 새로운 기능을 추가 하 고, 문제를 해결 하 고, 사용자 의견을 바탕으로 변경 내용을 적용 하 고 있습니다. 현재 사용 가능한 기능을 확인 하려면 아래를 확인 하세요. 일부 기능은 고객에 게 다양 한 속도로 롤아웃 됩니다. 아직 기능을 볼 수 없는 경우 대상 지정 된 [릴리스에 자신을 추가 해 보세요](manage/release-options-in-office-365.md).

다른 Microsoft 클라우드 서비스의 새로운 기능을 확인 하려면 다음을 수행 하세요.

- [Azure Active Directory의 새로운 기능](https://docs.microsoft.com/azure/active-directory/fundamentals/whats-new)
- [Exchange 관리 센터의 새로운 기능](https://docs.microsoft.com/Exchange/whats-new)
- [Microsoft Intune의 새로운 기능](https://docs.microsoft.com/mem/intune/fundamentals/whats-new)
- [Microsoft 365 준수 센터의 새로운 기능](https://docs.microsoft.com/Office365/SecurityCompliance/whats-new)
- [Microsoft Threat Protection의 새로운 기능](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)
- [SharePoint 관리 센터의 새로운 기능](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)
- [Office 업데이트](https://docs.microsoft.com/OfficeUpdates/)

## <a name="ignite-2020-august--september"></a>Ignite 2020 (9 월 & 일)

Microsoft Ignite-첫 번째 온라인 전용 Ignite에 오신 것을 환영 합니다. [Microsoft Ignite 2020 세션 카탈로그](https://myignite.microsoft.com/sessions)세션 중 하나에 사용자가 표시 되기를 바랍니다. 여기에는 Ignite에서 설명 하는 몇 가지 것이 나와 있습니다. 
> [!NOTE]
> 모든 기능이 즉시 모든 사용자에 게 제공 되는 것은 아닙니다. 새 기능이 표시 되지 않으면 대상 지정 된 [릴리스를 조인](manage/release-options-in-office-365.md)합니다.

### <a name="multi-tenant-management"></a>다중 테 넌 트 관리

Microsoft는 더 빠르고 효율적으로 작업을 수행할 수 있도록 다중 테 넌 트 관리자를 위한 기능 집합을 개발 했습니다.

- **테 넌 트**: 관리 하는 테 넌 트 간을 빠르게 전환 합니다.
- **모든 테 넌 트**: 모든 테 넌 트 서비스의 상태를 빠르게 확인할 수 있는 새 페이지, 미해결 서비스 요청, 제품 및 청구, 권장 설정 작업 및 해당 테 넌 트의 사용자 수
- **설정**: 다중 테 넌 트 설정 페이지에서 설정 페이지의 목록 보기를 제공 하지만 여러 테 넌 트에 맞게 구성 됩니다. 사용 하지 않는 기능, 즉, 테 넌 트에 대해 완료 된 작업이 완료 되어야 하는 작업을 확인할 수 있습니다. 이 보기를 통해 기능 도입을 추적 하 고, 권장 되는 보안 설정 작업이 항상 완료 되도록 할 수 있습니다.
- **서비스 상태**: 서비스 상태 보기에는 모든 사건이 나 권고에 영향을 주는 테 넌 트가 표시 됩니다. 영향을 받는 테 넌 트의 수를 알리는 것도 여기에 해당 합니다. 문제 해결 탭에 대 한 자세한 내용을 보려면 인시던트를 선택한 다음 영향을 받은 테 넌 트 탭으로 전환 하 여 해당 테 넌 트를 드릴 다운 하 고 지원 하기만 하면 됩니다.
- **테 넌 트 사서함 마이그레이션은** 현재 공개 미리 보기의 새로운 서비스로, 테 넌 트 간에 사서함을 이동 하 고, 온보드 사서함을 사용할 수 없습니다. 
- **교차 테 넌 트 도메인 공유**: 여러 테 넌 트 간에 도메인을 공유할 수 있도록 하는 기능에 대 한 비공개 미리 보기에 참가할 수 있습니다. 예를 들어 Contoso가 정문 장난감을 취득 하면 Contoso는 정문 장난감과 도메인을 공유 하 여 두 테 넌 트의 사용자가 자신의 전자 메일 주소로 "contoso.com"을 사용할 수 있도록 합니다.

![문제가 선택 되 고 테 넌 트 탭이 열려 있는 다중 테 넌 트에 대 한 서비스 상태 페이지입니다. 탐색 메뉴에는 모든 테 넌 트, 설정 및 서비스 상태가 유일한 옵션으로 포함 됩니다.](../media/MAC-WN-MTinServiceHealth.png)

### <a name="monitor-your-most-important-accounts"></a>가장 중요 한 계정 모니터링

CEO와 같이 비즈니스에 큰 영향을 주는 사용자에 게 전송 되는 실패 또는 지연 된 전자 메일 메시지를 모니터링 하 고 추적할 수 있습니다. Microsoft 365 관리 센터의 우선 순위 계정 목록에 사용자를 추가 하 여 우선 순위 계정을 추적 합니다. 중요 하거나 높은 우선 순위 정보에 액세스할 수 있는 임원, 리더, 관리자 또는 기타 사용자를 추가 합니다.

우선 순위 계정은 다음 요구 사항을 모두 충족 하는 조직 에서만 사용할 수 있습니다.

- Office 365 E3 또는 Microsoft 365 E3, 또는 Office 365 E5 또는 Microsoft 365 E5
- 최소 1만의 라이선스 및 최소 50의 월간 활성 Exchange Online 사용자

![기능에 대 한 설정 페이지: 가장 중요 한 계정 모니터링](../media/MAC-WN-PriorityAccounts.png)

다음 두 가지 방법으로 시작할 수 있습니다.

- **사용자**로 이동한 다음 "기타 작업" 메뉴에서 **우선 순위 계정 관리** 를 선택 하 여 사용자를 목록에 추가 합니다.
- **설정**으로 이동 하 여 **가장 중요 한 계정을 모니터링**하는 설정 작업을 찾은 다음 **시작**을 선택 합니다.

우선 순위 계정에 대 한 자세한 내용은 우선 순위 계정에 대 한 [우선 순위 계정](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 및 [전자 메일 문제](https://docs.microsoft.com/Exchange/mail-flow-best-practices/mail-flow-insights/mfi-email-issues-for-priority-accounts)모니터링를 참조 하세요.

### <a name="search-faster-and-get-better-results-from-any-page"></a>페이지에서 더 빠르게 검색 및 더 나은 결과 얻기

관리 센터에 대 한 새로운 검색 환경을 구축 하기 시작 했으며, 사용자가 시도를 기다릴 수 없습니다. ![검색 상자가 배너 영역으로 이동 되었습니다. 모든 페이지에서 검색 하려면 Alt + S를 누르십시오.](../media/MAC-WN-GlobalSearch.png)

- 검색 상자가 "Microsoft 365 관리 센터" 라고 표시 되는 머리글 영역으로 이동 되었으므로 홈 페이지 뿐 아니라 모든 페이지에서 검색을 수행할 수 있습니다. 바로 가기 **키 (Alt + S)** 도 제공 됩니다.
- 검색은 더욱 지능적 이며 더 빠른 결과를 제공 합니다. 시작 하려면 "2fa"를 입력 해 보세요.
- 검색 결과는 수행할 수 있는 항목 또는 작업 유형에 따라 구성 됩니다.
  - **사용자**: 사용자의 이름을 선택 하 고 해당 사용자에 게 직접 편집할 수 있습니다. 이름 옆에 있는 "추가 작업" 메뉴를 선택 하는 경우에는 암호를 다시 설정할 수 있습니다. 표시 이름, 성, 이름, 사용자 이름, 기본 전자 메일 주소 및 전자 메일 별칭을 기준으로 검색할 수 있습니다. 하지만 정확히 일치 하는 항목을 가져오려면 기본 전자 메일 주소 또는 사용자 이름으로 검색 합니다.
  - **그룹**: 모든 페이지에서 그룹을 편집 하 고 구성원을 추가 하 고 소유자를 할당 합니다.
  - **작업**: 사용자를 검색 한 다음 암호를 다시 설정 하는 방법과 마찬가지로 페이지에서 "암호 다시 설정"을 검색 한 다음 사용자에 대해 하나 이상의 암호를 다시 설정할 수 있습니다.
  - **탐색**: 탐색 아래의 결과를 통해 관리 센터의 페이지를 빠르게 쉽게 가져올 수 있습니다. 예를 들어 "역할"을 검색 하면 Azure AD 역할에 대 한 역할 페이지로 이동 됩니다.
  - **설정**: 조직, 구독 하는 서비스, 보안 및 개인 정보 설정에 관련 된 모든 설정을 검색 합니다. 
  - **도메인**: 도메인에 대 한 빠른 연결을 찾은 다음 링크를 클릭 하 여 해당 도메인의 개요 및 상태 페이지로 이동할 수 있습니다.
  - **설명서**: 사용자가 결과를 찾을 수 없는 경우 도움이 되는 몇 가지 설명서를 찾으려고 시도 합니다. 맞게 조정 된 문서의 목록에서 일치 하는 항목을 찾는 데는 약간 시간이 더 오래 걸리므로, 두 번째를 수행 하 여 검색 결과를 찾을 수 있도록 합니다. 
  - **사용자 의견**: 원하는 정보를 찾을 수 없습니까? 검색에서 의견을 보내 주세요. 관리 센터에서 더 많은 페이지 및 기타 기능을 검색 하는 기능이 추가 될 예정입니다.

### <a name="microsoft-365-admin-mobile-app"></a>Microsoft 365 관리 모바일 앱

구독에 포함 되어 있는 [microsoft 365 관리 모바일 앱](https://www.microsoft.com/microsoft-365/business/manage-office-365-admin-app)을 사용 하면 모바일 장치에서 microsoft 365를 관리 하 여 매일 작업을 수행할 수 있습니다. 실제로 앱에는 90 기능이 많이 있으며 다음과 같이 몇 가지 추가 되었습니다.

- **Microsoft intune의 모바일 응용 프로그램 관리 및 조건부 액세스 정책 지원**: 조직에서 Intune의 모바일 응용 프로그램 관리 및 조건부 액세스 정책을 설정한 경우에도 이제 개인 장치를 사용 하 여 Microsoft 365를 관리할 수 있습니다.
- **메시지 센터 알림**: **Settings**  >  새 메시지 센터 게시물에 대 한 알림을 받을 수 있도록 설정**알림에서** 메시지 센터 알림을 설정 합니다. 알림을 통해 테 넌 트에서 중요 한 정보와 이벤트에 대 한 정보를 계속 받을 수 있도록 합니다.
- **대금 청구 알림**: **Settings**  >  구독이 만료 되는 경우 장치에 대금 청구 알림을 받으려는 경우에는 설정**알림에서** 대금 청구 알림을 설정할 수도 있습니다.
- **어둡게 모드**: 모바일 앱의 어두운 쪽에 오신 것을 환영 합니다. 이는 가장 많이 요청 되는 기능 중 하나입니다. **설정**  >  **테마로** 이동 하 여 설정을 켭니다.
- **문제 보고**: 이제 앱의 문제를 보고 하거나 다른 관리자가 보고 한 문제를 확인할 수 있습니다. **서비스 상태** 를 방문 하 여 체크 아웃 합니다.

![메시지 센터에 대 한 알림, 서비스 상태, 대금 청구 경고를 포함 하는 Microsoft 365 관리 앱의 상태 페이지](../media/MAC-WN-AdminMobileApp.png)

### <a name="usage-recommendations-for-small-and-medium-businesses"></a>중소 기업에 대 한 사용 권장 사항

중소 기업에서는 조직에 있는 일부 사용자가 팀, OneDrive 또는 Office 앱을 실제로 사용 하지 않는 경우 **홈** 페이지에 대 한 권장 사항을 얻을 수 있습니다. 추천 항목을 보면 앱을 시작 하 고 구독에서 전체 값을 가져올 수 있도록 Microsoft 교육을 비활성 사용자에 게 빠르게 전자 메일로 보낼 수도 있습니다.

### <a name="remote-work-collection"></a>원격 작업 컬렉션

10 월에는 원격 작업 모음을 추가 하 여 small business 소유자와 해당 직원이 온라인으로 작동 하 고 원격으로 작업할 수 있도록 지원 합니다.  **원격 작업 essentials** setup은 모든 기능의 맞게 조정 된 목록으로, 원격 작업을 안전 하 게 사용 하도록 설정 하 고 효과적으로 공동 작업 하는 것이 좋습니다. 몇 주 후에는 **Setup**  >  **원격 작업**설정에서 테스트해 볼 수 있습니다.

![7 개의 작업이 포함 된 설치 프로그램의 원격 작업 기초 페이지가 시작 되지 않았습니다.](../media/MAC-WN-RemoteWork.png)

원격 작업 및 쉽게 저장 하 고 공유할 수 있는 편리한 웹 주소를 안전 하 게 허용 하는 방법에 대 한 자세한 내용은 [aka.ms/remote-business](https://aka.ms/remote-business)로 이동 하세요.

### <a name="need-help-moving-to-more-admin-centers"></a>도움이 필요 하세요? 더 많은 관리 센터로 이동

제품의 변경 내용을 유지 하기 위해 콘텐츠 및 도구를 지속적으로 보고 업데이트 하 고 있습니다. 이제 문제를 신속 하 고 효율적으로 해결 하는 데 도움이 되는 다양 한 셀프 서비스 진단 도구가 제공 됩니다. 최근에 추가 된 몇 가지는 다음과 같습니다.

- Exchange 웹 서비스 제한 정책 변경
- 팀 프로비저닝 및 특정 사용자에 대 한 유효성 검사 상태 확인
- DKIM 설정 문제 해결
- Intune 사용자 등록 오류 진단

이번에는 Microsoft 365 관리 센터에서 이미 제공 하 고 있는 새로운 지원 환경을 다른 관리 센터에 배포 하 고 있습니다. 팀 관리 센터 및 보안 및 규정 준수 관리 센터는 이미 이러한 새로운 환경을 제공 합니다. 또한 **Exchange 관리 센터**, **SharePoint 관리**센터 및 **Office.com** 는 관리자를 위한이 새로운 도움말 환경과 함께 업데이트 될 예정입니다.

### <a name="manage-changes-with-microsoft-planner"></a>Microsoft Planner에서 변경 내용 관리

고객은 곧 메시지 센터 게시물을 Microsoft Planner로 동기화 하 고 모든 사용자가 사용할 수 있도록 할 수 있음을 알게 되었습니다.  이제 메시지에서 작업을 만들고 할당 하 고 완료 되도록 추적할 수 있습니다. 처음에는 **Planner 동기화** 를 선택 하 고 적절 한 요금제에 연결 해야 합니다.

![명령 모음에서 기본 설정 단추 옆에 강조 표시 된 ' planner 동기화 '를 사용 하는 메시지 센터 페이지](../media/MAC-WN-MCPlannerSync.png)

이에 대 한 자세한 내용은이 문서 및 비디오에서 해당 작동 방식을 확인 하세요. [Planner에서 메시지 센터 게시물 추적](https://docs.microsoft.com/Office365/Planner/track-message-center-tasks-planner)

### <a name="documentation-training-and-videos"></a>설명서, 교육 및 비디오

- Microsoft Ignite ([가상 허브](https://adoption.microsoft.com/virtual-hub/))에 대 한 신규 및 just-in-time 시간 IT 전문가 및 개발자를 위한 기술 교육에 대해 자세히 살펴보겠습니다. #SIDETRACKED의 일부로 신속 하 게 20 개의 새 비디오를 확인 하 고 이번 연도를 추적 하는 Ignite admin의 이름입니다.
- [Microsoft 365](https://www.youtube.com/watch?v=OVjb2lGJ4GU&t=2s) 비디오 시리즈의 새로운 기능: 이번 달에는 팀에 대 한 화이트 보드 및 웹에서 사용할 수 있는 새로운 기능과 Azure AD에 대 한 사용자 프로 비전을 자동화 하는 방법, 팀의 새 전원 자동화 트리거 및 작업 등에 대해 설명 합니다. 그리고 다음 달에는 Ignite에서 모든 커다란 문제를 파악할 수 있습니다.
- 먼저 솔루션에 중점을 둔 [Microsoft 365 설명서](https://docs.microsoft.com/microsoft-365) 페이지를 다시 디자인 했습니다. 이 페이지에서는 새 솔루션을 사용할 수 있는 것 처럼 강조 표시 되므로 눈에 잘 들어 두세요.

!["원격 작업자의 역량 강화"와 같은 솔루션을 포함 하는 Microsoft 365 솔루션 설명서의 새 랜딩 페이지](../media/MAC-WN-M365Docspage.png)

## <a name="july-2020"></a>2020년 7월

### <a name="getting-ready-for-ignite-2020"></a>Ignite 2020 준비

Microsoft에서 Ignite 계절으로 이동 하는 동안에는 세션 중에 의견을 많이 제공 하도록 많은 기능을 출시할 예정입니다.

이 문서에 대 한 다음 업데이트는 첫 번째 온라인 전용 Ignite 개시 된 날에 예정 되어 있습니다. 이번 연도에서는 참석이 가능 합니다. 파일을 체크 아웃 하 고 등록 하려면: [Microsoft Ignite 2020](https://www.microsoft.com/ignite)를 참조 하세요.

### <a name="your-products"></a>제품

구독 관리에서 페이지를 보다 빠르게 로드 하 고, 원하는 항목을 보다 신속 하 게 찾고, 웹 접근성 표준 ([WCAG 2.1 지침](http://www.w3.org/TR/WCAG21/))을 충족 하기 위해 많은 작업을 수행 해야 합니다.

- **표 재설계**: 비슷한 구독을 그룹화 할 수 있도록 테이블이 다시 디자인 되었습니다. 제품 **대금 청구**로 이동  >  **Your products**합니다.
- **제품 정보**: 목록에서 제품을 선택 하 여 구독에 대 한 보다 자세한 정보를 제공 합니다.
- **여기에서 모든 작업을 수행**해야 하며, 한 제품을 관리 하기 위해 여러 페이지로 이동 하지 않아도 됩니다. 예를 들어 구독을 취소 해야 하는 경우이 패널은 바로 작업을 수행 하기 위해 열립니다.

![구독 취소 패널이 열려 있는 제품 페이지입니다.](../media/MAC-WN-SubscrDetails.png)

### <a name="domains"></a>도메인

도메인 관리 작업은 복잡할 수 있으며,이를 위해 새로운 기능을 출시 했습니다. 설정 > 도메인으로 이동한 다음 도메인을 선택 하 여 도메인 및 도메인의 상태에 대 한 자세한 정보를 확인 합니다.

:::image type="content" source="../media/MAC-WN-DomainDNS.PNG" alt-text="Contoso.com의 도메인 세부 정보 페이지":::

### <a name="docs-training-and-videos-july-2020"></a>문서, 교육 및 비디오 (2020 년 7 월)

[Microsoft 365](https://youtu.be/m1Nu8WJgCDY) 비디오 시리즈의 새로운 기능: 이번 달에는 웹 및 모바일에 새로운 yammer 환경을 제공 하 고, Microsoft 팀을 위해 Yammer 커뮤니티 앱을 통합 하는 방법, 그리고 Firstline worker 및 관리자를 지원 하기 위한 새로운 정책 패키지 등을 소개 합니다.

## <a name="june-2020"></a>2020년 6월

### <a name="keeping-up-with-office-whats-new-management"></a>Office의 새로운 기능 관리

몇 달 전에 [사용자의 Office 앱에 표시 되는 새 메시지](#office-whats-new-management)를 관리 하는 데 사용할 수 있는 설정을 추가 했습니다. 이번 달에는 신속 하 게 작업 하 고 조직의 사용자에 게 표시할 **새** 메시지를 추적 하는 데 도움이 되는 새 홈 페이지 카드를 출시 했습니다.

### <a name="docs-training-and-videos-june"></a>문서, 교육 및 비디오 (6 월)

- [팀 시작](https://support.microsoft.com/office/184f1aba-2f91-43f0-86e1-9fae607e24f6)

## <a name="may-2020"></a>2020년 5월

### <a name="new-update-channel-for-office"></a>Office의 새 업데이트 채널

5 월 12 일에는 새로운 Office 용 업데이트 채널: 월별 엔터프라이즈 채널을 사용할 수 있습니다. 이 업데이트 채널은 매달 두 번째 화요일에 새로운 Office 기능을 사용자에 게 제공 합니다.

사용자가 포털에서 Office를 자동으로 설치할 수 있도록 허용한 경우에는 월별 엔터프라이즈 채널을 선택할 수 있습니다. 이렇게 하려면 Microsoft 365 관리 센터에 로그인 하 고 **모든**  > **설정**표시  >  **조직 설정**  >  **서비스**  >  **Office 소프트웨어 다운로드 설정**으로 이동 합니다. **한 달에 한 번 선택 하면 (월별 엔터프라이즈 채널)** Office의 새 자동 설치는 월별 엔터프라이즈 채널을 사용 하도록 구성 됩니다.

월별 엔터프라이즈 채널 릴리스와 함께 기존 업데이트 채널의 이름도 수정 됩니다. 예를 들어 월별 채널의 이름은 현재 채널로 바뀝니다. 새 이름은 2020 년 6 월 9 일에 적용 됩니다.

자세한 내용은 [업데이트 채널의 Microsoft 365 앱 변경 사항을](https://docs.microsoft.com/DeployOffice/update-channels-changes)참조 하세요.

### <a name="new-admin-roles"></a>새 관리자 역할

Microsoft 365 관리 센터에 몇 가지 새로운 Azure Active Directory 관리자 역할을 추가 했습니다.

- 하이브리드 id 관리자 역할은 사용자에 게 클라우드 프로 비전 및 인증 서비스를 관리할 수 있는 권한을 부여 합니다.
- 네트워크 관리자 역할을 통해 사용자는 네트워크 위치를 관리 하 고 Microsoft 365 소프트웨어에 대 한 네트워크 insights를 서비스 앱으로 검토할 수 있습니다.
- 프린터 관리자 역할은 프린터 및 프린터 연결의 모든 측면을 관리할 수 있는 사용 권한을 부여 합니다.
- Printer 엔지니어가 프린터 관리자 역할의 하위 집합으로, 프린터를 등록 하 고 등록을 취소 하 고 프린터 상태를 업데이트할 수 있습니다.
이러한 역할에 대 한 자세한 내용은 [관리 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조 하십시오.

### <a name="export-groups-list"></a>그룹 내보내기 목록

관리자 센터에 대 한 액세스 권한이 없는 사용자에 게 그룹 및 사용에 대 한 정보를 공유 해야 하는 관리자가 많았습니다. 이제 감사 목적으로 그룹 목록을 CSV 파일로 내보낼 수 있는데,이는 이전 PowerShell 스크립트를 throw 할 수 있다는 것을 의미 합니다. 실행 하려면 **그룹**  >  **그룹**으로 이동한 후 명령 모음에서 **그룹 내보내기를** 선택 합니다.

### <a name="microsoft-365-solution-and-architecture-center"></a>Microsoft 365 솔루션 및 아키텍처 센터

이번 달에는 [https://docs.microsoft.com](https://docs.microsoft.com) [microsoft 365 솔루션 및 아키텍처 센터](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center)라는 새로운 사이트를 출시 했으며, 보안 및 준수 공동 작업용 통합 microsoft 365 솔루션을 이해 하 고 계획 하 고 구현 하는 데 필요한 기술 지침을 함께 제공 합니다. 이 센터에서는 다음을 확인할 수 있습니다.

- 기본 솔루션 지침
- 작업 솔루션 및 시나리오 지침
- 솔루션 및 아키텍처 그림 (포스터!!!)
- 업계 관련 지침
- 엔터프라이즈 아키텍처 디자인 보안 주체

### <a name="docs-training-and-videos-may"></a>문서, 교육 및 비디오 (있을 수 있음)

- **Microsoft 365 비디오 시리즈의 새로운 기능**: 이번 달에는 팀 관리자 및 보안 및 준수 센터의 새로운 지원 환경, 메시지 센터와의 Planner 통합 및 Microsoft 팀의 새로운 3 중 비디오 레이아웃에 대해 다룹니다. 
- 보다 빠르게 필요한 정보를 찾을 수 있도록 [Microsoft 365 관리 센터 도움말](https://docs.microsoft.com/microsoft-365/admin/) 허브 페이지가 업데이트 되었습니다. 그리고 해당 페이지를 바로 살펴보면 중요 업데이트 및 변경 사항을 알리는 카드를 추가 했습니다.

## <a name="april-2020"></a>2020년 4월

### <a name="intune-roles-management"></a>Intune 역할 관리

[2020년 4월](#april-2020)

잘 하셨습니다. 두 번째 단계를 통합 된 역할 환경으로 이동 했으며 이제 Microsoft 365 관리 센터에서 Intune 역할을 관리할 수 있습니다. 역할을 검색 하 고 역할 권한을 보기 위한 기능과 같은 기능을 활용할 수도 있습니다. 즉, Microsoft 365 및 Intune에 대 한 역할을 관리 하는 두 가지 별도의 도구가 필요 하지 않습니다. Microsoft 365 관리 센터에 로그인 할 때 역할 페이지에는 Azure AD에 대해 하나씩, Intune 용으로는 두 개의 피벗이 표시 됩니다.

![Intune 피벗이 선택 된 역할 페이지](../media/MAC-WN-IntuneRoles.png)

### <a name="sync-message-center-posts-to-planner"></a>Planner에 메시지 센터 게시물 동기화

5 월에 시작 하는 경우 대상 지정 된 릴리스의 관리자는 메시지 센터에서 "Planner 동기화" 단추를 시작 합니다. 이제 작업이 필요한 메시지를 추적 하 고, 추적 하려는 메시지 유형을 선택 하 고, 작업으로 추적할 메시지를 지정 하 고, 나중에 주의 하기 위해 메시지에 태그를 지정할 수 있습니다.

시작 하기 위해 대상 지정 된 [릴리스를 조인](manage/release-options-in-office-365.md) 합니다.

### <a name="need-help-launched-in-teams-admin-center--security-and-compliance-centers"></a>"도움이 필요 하세요?" 보안 및 준수 센터 & 팀 관리 센터에서 시작

팀 관리 센터, 보안 센터 및 준수 센터에서 현재 같은 "도움이 필요 하세요?"를 사용 하 고 있습니다. Microsoft 365 관리 센터에서 도움말을 찾고 지원 서비스에 연락 하는 데 사용 하는 기능입니다. Microsoft는 관리자 로부터 사용자 의견을 많이 받았으며, 동일한 수준의 지원 및 지원을 제공 했으며이를 위해 최선을 다 해 드립니다. 사용해 보고 의견을 보내 주세요.

#### <a name="need-chat"></a>채팅 필요 여부

Microsoft 지원 에이전트는 집에서 작업 하는 동안 고객의 사례와 인터넷 대역폭에 대 한 제한 사항을 유지 하면서도 고객의 통화 품질에 영향을 줄 수 있습니다. 지원을 계속 하기 위해 Microsoft 365 관리 센터에서 상업용 고객에 게 live 채팅 지원 옵션을 시작 했습니다.

이제 서비스 요청을 만들 때 전화 및 전자 메일 외에 옵션으로 채팅을 볼 수 있습니다. 원하는 통신 채널로 채팅을 선택 하 고 요청을 만듭니다. 요청을 만든 후에는 Microsoft 에이전트와 채팅할 준비가 되 면 채팅을 시작할 수 있습니다.

### <a name="teams-updates"></a>팀 업데이트

팀의 사용이 증가 함에 따라서 이러한 기능을 관리 하는 데 도움이 되는 몇 가지 기능이 추가 되었습니다.

- 관리 센터 홈 페이지의 새 권장 사항 카드에는 30 일간 팀이 적극적으로 사용 되지 않은 사용자가 표시 됩니다. 해당 사용자에 게 교육 전자 메일을 보내 팀을 시작 하는 방법을 확인할 수 있습니다.
- **팀과 함께 사용자 가져오기**: **설치 프로그램** 으로 이동 하 여 라이선스 사용자에 대 한 팀을 설정 하 고 게스트 액세스를 허용 하 여 팀에서 외부 고객을 사용할 수 있도록 하는 데 도움이 되는 새 페이지를 확인 합니다.
- Microsoft 팀 카드는 이제 기본적으로 홈 페이지에 고정 되어 있습니다. 이 도구는 팀이 켜져 있는지 여부 및 게스트 액세스를 허용 하는 경우를 표시 합니다. 또한 새로 사용이 허가 된 팀 사용자의 설치 상태를 확인 하 고 네트워크 문제가 팀 사용자에 게 영향을 줄 수 있는지를 확인할 수 있습니다.
- 마지막으로 팀이 포함 된 라이선스를 구매한 경우 팀은 초기 설정 흐름의 단계로 진행 됩니다.

### <a name="productivity-score"></a>생산성 점수

생산성 점수는 사용자가 Microsoft 클라우드 서비스를 사용 하는 방법 및이를 지 원하는 기술 환경에 대 한 정보를 제공 합니다. 점수는 직원 및 기술 경험 측정과 조직의 성과를 반영 하 고 사용자와 같은 조직과 점수를 비교 합니다. 이번 달에는 미리 보기 환경에 다음과 같은 새로운 개념을 소개 합니다.

- 홈 페이지 및 범주 세부 정보 페이지에 대 한 기본 통찰력 보기-기술 환경에 추가 된 끝점 분석 및 네트워크 연결 범주
- 직원 경험 범주에 표시 된 관련 기술 환경 통찰력
- 직원 환경의 일부로 새 통신 범주
- 직원 환경 범주의 조직 메타 데이터를 사용 하는 사용자 세부 정보

자세한 내용은 블로그: 측정값을 확인 [하 고 Microsoft 생산성 점수가 microsoft 365 환경을 향상 시키는](https://techcommunity.microsoft.com/t5/microsoft-365-blog/measure-and-improve-the-microsoft-365-experience-with-microsoft/ba-p/1348618)것이 좋습니다. 생산성 점수가 현재 비공개 미리 보기 상태입니다. 시작 하려면 [생산성 점수 비공개 미리 보기에 참가](https://aka.ms/productivityscorepreview) 합니다.

### <a name="groups-updates"></a>그룹 업데이트

이번 달에는 다음과 같은 두 개의 그룹 용 업데이트가 있습니다.

- 이제 Outlook에서 그룹이 라고도 하는 Office 365 그룹의 전자 메일 주소를 편집할 수 있으며 곧 Microsoft 365 그룹으로 알려져 있습니다.
- 사용자 의견을 받은 후 그룹을 Microsoft 팀으로 변환할 수 없는 이유에 대 한 오류 메시지를 명확 하 게 추가 했습니다.

### <a name="docs-videos-and-training-april"></a>문서, 비디오 및 교육 (4 월)

**Microsoft 365 비디오 시리즈의 새로운 기능**: 이번 달에는 microsoft 팀을 배포 하는 방법, 클라이언트 및 파트너와의 연결을 유지 하기 위해 원격 작업 교육 리소스 및 새로운 Microsoft 365 비즈니스 음성 요금제를 포함 하 여 원격 작업으로 소규모 비즈니스를 전환 하는 데 도움이 되는 팁과 리소스에 대해 알아봅니다. [Microsoft 365의 새로운 기능](https://go.microsoft.com/fwlink/p/?linkid=2118096)

#### <a name="for-your-users"></a>사용자의 경우

- [모임 예약](https://support.microsoft.com/office/c61b4f61-ee62-4a06-8bf7-0a1cd302700a)
- [팀 모임 참가](https://support.microsoft.com/office/078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [조직 전체 팀 만들기](https://support.microsoft.com/office/037bb27a-bcc9-48fe-8d72-44d9482420a3)
- [게스트와 함께 팀 만들기](https://support.microsoft.com/office/11fbb083-52ee-434d-8c6e-63711fdafac7)
- [팀에 게스트로 참가](https://support.microsoft.com/office/928d1eef-61e2-49ec-b754-c2fe86b34824)
- [그룹 전자 메일 주소 만들기](https://support.microsoft.com/office/ded875f9-a9de-437f-b559-2ae4f235bb2b)

#### <a name="for-admins-and-business-owners"></a>관리자 및 비즈니스 소유자의 경우

- [소규모 기업에 원격 작업 강화](https://support.microsoft.com/office/9b91a85a-39b4-40a6-a590-0f9bea0ba8e6)
- [원격 중소 기업 실행](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Microsoft Business Basic 등록](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [2 단계 로그인 설정](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)

## <a name="march-2020"></a>2020년 3월

### <a name="featured-feedback-fix-improve-add-user-reliability-for-licensing"></a>추천 피드백 수정: 라이선스에 대 한 "추가 사용자" 안정성 향상

사용자를 추가할 때 라이선스를 할당 하는 것이 얼마나 어려운 지 관리자 로부터 많은 의견이 수신 되었습니다. 이 수정 프로그램에 대 한 첫 번째 업데이트를 수행 했으며, 이러한 요청을 처리 하기 위해 보다 신뢰할 수 있는 백그라운드 서비스를 마이그레이션 했습니다. 문제가 발생 하면 나중에 다시 시도할 수 있는 오류 메시지가 표시 됩니다.

![오류가 있는 사용자 확인 페이지를 추가 합니다.](../media/MAC-WN-ImprovedLicensing.png)

### <a name="microsoft-teams-home-page-card"></a>Microsoft 팀 홈 페이지 카드

팀 사용에서의 uptick을 사용 하는 경우 일부 조직을에서 고정 된 대시보드 카드를 가져와 더 쉽게 검색할 수 있도록 설정 합니다. 또한이 카드에는 조직에서 원격 작업으로 전환 하는 데 도움이 되는 교육 및 문서에 대 한 링크도 포함 되어 있습니다. **홈** 페이지로 이동 하 여 새 카드를 확인 하세요.

![Microsoft 팀 홈 페이지 카드](../media/MAC-WN-TeamsCard.PNG)

### <a name="customize-your-organizations-sharepoint-mobile-app-theme"></a>조직의 SharePoint 모바일 앱 테마 사용자 지정

Microsoft 365 관리 센터를 사용 하 여 이제 SharePoint 모바일 앱 for iOS 및 SharePoint 모바일 앱 for Android에서 조직의 테마를 사용자 지정할 수 있습니다. 이 기능은 이동 중에 직원 들에 게 SharePoint Online을 일치 시킬 수 있는 모바일 인트라넷 앱 환경을 간편 하 게 제공 합니다. 테마 사용자 지정에는 로고 이미지, 탐색 모음 색, 텍스트 및 아이콘 색, 강조 색 등이 포함 되어 쉽게 인식할 수 있습니다.

![관리 센터 설정을 모바일 앱에 매핑하는 다이어그램입니다.](../media/MAC-WN-CustThemeSP.png)

### <a name="improvements-to-the-add-a-group-wizard"></a>"그룹 추가" 마법사의 향상 된 기능

관리자가 새 그룹을 만들어 동시에 팀으로 만든 경우 팀을 포함 하는 라이선스가 없는 소유자를 할당할 수 있습니다. 그리고 몇 가지 골치 아픈 것을 본 것입니다. 마법사 흐름을 업데이트 하 여 소유자에 게 팀 라이선스가 있는지 확인 하 고 그룹을 팀으로 전환 하는 옵션을 사용 하지 않도록 설정 했습니다.

### <a name="microsoft-365-offerings-for-small-and-medium-businesses"></a>중소 규모 기업을 위한 Microsoft 365 제공

이는 다음 달에 대 한 알림 이지만 준비 되어 있는지 확인 하려고 합니다.

4 월 21 일에 시작 하 여 중소 기업 및 Office 365 ProPlus에 대 한 Office 365 구독과 관련 된 변경 작업을 수행 하 고 있습니다. 이러한 제품은 이제 Microsoft 365 브랜드를 사용 합니다.

새 제품 이름은 2020 년 4 월 21 일에 적용 됩니다. 이는 제품 이름만 변경 되었으며 지금은 가격 또는 기능을 변경할 수 없습니다.

|현재 이름 |새 이름  |
|---------|---------|
|Office 365 Business Essentials     |   Microsoft 365 Business Basic      |
|Office 365 Business Premium     |    Microsoft 365 Business Standard     |
|Microsoft 365 Business     |    Microsoft 365 Business Premium     |
|Office 365 Business     |    비즈니스용 Microsoft 365 앱       |
|Office 365 ProPlus    |   Microsoft 365 enterprise 용 앱      |

### <a name="videos-training-and-docs"></a>동영상, 교육 및 문서

[Microsoft 365 웹 시리즈의 새로운](https://go.microsoft.com/fwlink/p/?linkid=2118096)기능: 이번 달에는 microsoft 팀의 3 년 전 기념일을 강조 하 고, 온라인 모임에서 향상 된 오디오 품질, 이동 앱, 팀 및 Skype 소비자 상호 운용성 등의 firstline 관리자를 대상으로 하는 새로운 기능을 소개 합니다.

## <a name="february-2020"></a>2020년 2월

### <a name="featured-feedback-fix-multi-organization-switcher"></a>주요 피드백 수정 사항: 다중 조직 전환기

여러 Microsoft 클라우드 orgs를 관리 하는 문제에 대 한 파트너 및 관리자의 의견이 많이 수신 되었습니다. 첫 번째로 제공 되는 다중 조직 관리 기능 중 하나는 두 번의 클릭으로 관리 하는 조직을를 변경할 수 있는 **조직 전환기**입니다.
> [!TIP]
> 하나 이상의 조직에 대 한 레코드 파트너가 되는 한, 조직 전환기가 표시 되도록 하기 위해 별도의 작업을 수행할 필요가 없습니다.

1. Microsoft 365 관리 센터에서 조직 이름을 선택 합니다.
![화면 캡처: 조직 프로필 이름이 전환기 아이콘과 함께 표시 되는 홈 페이지의 위쪽입니다.](../media/MAC-Organization-switcher.png)

2. 조직 전환기에서 관리 하려는 조직을 선택 합니다.
![화면 캡처: 통합 메신저 테 넌 트가 강조 표시 된 내 조직 테 넌 트 전환기](../media/MAC-OrgSwitcherSelected.png)

그대로!!!

### <a name="groups"></a>그룹

이번 달에는 그룹 영역에서 다음과 같은 몇 가지 사항을 변경 합니다.

- **그룹 이름순으로 정렬**: **그룹 이름** 열을 선택 하 여 그룹 목록을 사전순으로 정렬할 수 있습니다.
- **삭제 된 microsoft 365 그룹 복원**: 더 이상 Exchange 관리 센터로 이동 하 여 삭제 한 microsoft 365 그룹을 복원할 필요가 없습니다. **Microsoft 365 관리 센터** \> **그룹** \> **삭제** \> 된 그룹 (목록에서 그룹 선택) \> **복원 그룹**으로 이동 합니다. **그룹을 그룹 목록으로** 다시 복원 하 고 그룹의 전자 메일, 대화, 전자 필기장, 파일 및 일정을 복원 합니다.

### <a name="videos-training-and-docs-february"></a>비디오, 교육 및 문서 (2 월)

- **Microsoft 365 비디오 시리즈의 새로운 기능**: 이번 달에는 SharePoint Online에 대 한 사용자 지정 검색 기능을 중점적으로 다루며, Office "What 's new" 관리 기능을 사용 하 여 앱 내 도움말 창, Yammer의 최신 보안 및 준수 업데이트를 통해 최종 사용자의 특정 기능을 표시 하거나 숨길 수 있습니다. 최신 에피소드: [Microsoft 365의 새로운 기능](https://go.microsoft.com/fwlink/p/?linkid=2118096)

- **문서 이동**: Office 365 관리 웹 문서를 Microsoft 365 콘텐츠와 결합 했으며, 새 URL을 알고 있을 수 있습니다. 예를 들어이 문서는 **docs.microsoft.com/Office365/Admin/whats-new-in-preview**에서 호스트 되는 데 사용 되었지만 URL은 현재 **docs.microsoft.com/microsoft-365/admin/whats-new-in-preview**입니다. 페이지를 책갈피로 지정한 경우 링크를 업데이트 해야 합니다. 그러나 콘텐츠 링크는 새 콘텐츠 리포지토리로 리디렉션됩니다.

## <a name="january-2020---happy-new-year"></a>1 월 2020 일, 신규 해 아침

> [!NOTE]
> YouTube의 [Microsoft 365 비디오 시리즈에 새로](https://go.microsoft.com/fwlink/p/?linkid=2118096) 제공 되는 기능을 알고 계십니까? 사용자에 게 롤업되는 최신 기능을 강조 표시 합니다. 매달 [비디오, 교육 및 docs](#videos-training-and-docs) 섹션에서 최신 에피소드 연결을 시작 합니다. <br> <br> 최신 에피소드: [Microsoft 365의 새로운 기능](https://go.microsoft.com/fwlink/p/?linkid=2118096)

### <a name="dark-mode"></a>어둡게 모드

처음 롤아웃 모드는 홈 페이지 에서만 사용할 수 있었습니다. 어두운 모드는 이제 미리 보기 상태를 벗어나 관리 센터의 대부분의 페이지에서 대상으로 지정 된 릴리스로 제공 됩니다.

1. 먼저, 대상 지정 릴리스를 켜야 **설정** \> **설정** \> **조직 프로필** \> **릴리스 기본**설정으로 이동 합니다.
1. 누른 다음 어둡게 모드를 켜려면 **홈** 페이지로 이동한 다음 **어둡게 모드** 단추를 선택 합니다. ( **검색** 필드 옆에이 문서의 새 링크에 대 한 **설명** 입니다.)
1. 어두운 모드를 사용할 수 있는 모든 페이지의 경우 단추는 페이지 맨 위에 있으며 **새 관리 센터** 전환 옆에 있습니다.

### <a name="office-whats-new-management"></a>Office의 새로운 기능 관리

관리자는 Microsoft가 Office 앱의 사용자에 게 "새로운 기능"을 전달 하는 방법을 제어 하 고 이제 해당 컨트롤을 사용 하 게 됩니다. **Settings** \> **Office의 새로운 관리 미리 보기**설정으로 이동 합니다. 사용자가 특정 "새로운 소식" 메시지를 표시 하지 않도록 하려면 기능을 선택 하 고 세부 정보를 보려면 **사용자 로부터 숨기기** 단추를 선택 합니다. 예를 들어 조직에서 조직의 모든 사용자에 게 교육을 보낼 때까지 기능에 대 한 정보를 알려 줄 수 있습니다.

![화면 캡처 기능 세부 정보 창이 열려 있는 새 preview Office](../media/whatsnew-officemgmt-preview.png)

이 기능은 11 월에 미리 볼 수 있도록 처음 출시 되었지만 몇 가지 기능 업데이트를 확인 해야 합니다. [이제 제공 되는 Office의 새로운 관리 미리 보기 업데이트](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-preview/ba-p/1020438) 를 확인할 수 있습니다.

### <a name="partners"></a>파트너

Howdy, 파트너! (도움을 받을 수 없습니다.) 이번 달에도 업데이트가 제공 되었습니다. 파트너는 CSP 고객에 게 관리 센터의 **청구 계정** 섹션에서 Microsoft 고객 계약 (MCA)을 받을 수 있는 옵션을 제공 하는 새로운 기능이 있습니다. 이러한 새로운 환경에서는 다음을 수행 합니다.

1. 고객은 파트너 관계 및 MCA를 수락 하기 위한 링크가 포함 된 초대 전자 메일을 받습니다.
2. 사용자가 로그인 한 후에는 관리 센터에서 바로 MCA 및 파트너 권한을 보고 수락할 수 있습니다.

### <a name="resource-mailboxes"></a>리소스 사서함

리소스 사서함 목록이 새 스타일로 업데이트 되었습니다. Microsoft 365 관리 센터에서 **리소스** \> **대화방 & 장비로**이동 합니다.

### <a name="videos-training-and-docs-january"></a>비디오, 교육 및 문서 (1 월)

1 월에 릴리스된 중소 기업 관리 교육을 확인 하세요.

- [비즈니스 웹 사이트 만들기](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9)
- [답변 및 도움말 찾기](https://support.microsoft.com/office/7f681212-c649-4a3e-a43b-32b1d1e58988)
- [도움말 또는 지원 받기](https://support.microsoft.com/office/18948a4c-3eb1-4b30-b1bc-a4cc29eb7655)
- [사용자 삭제](https://support.microsoft.com/office/6bcdad7b-732a-4260-997a-8c176bc3d9d6)
- [Microsoft 구독 선택](https://support.microsoft.com/office/b9f7c78e-430f-4117-89ec-2eeb1dced2ca)
- [Microsoft 365 for business security 개요](https://support.microsoft.com/office/3274b159-a825-46d7-9421-7d6e209389d1)

## <a name="november-and-december-2019"></a>11 월과 12 월 2019

Ignite 이후에는 알림을 거의 적게 가지 므로 11 월과 12 월의 뉴스를 결합 하 고 있습니다. 새 해를 볼 수 있습니다.

### <a name="change-from-credit-card-to-invoice-payment"></a>신용 카드에서 송장 지불로 변경

신용 카드에서 송장으로 결제 방법을 변경 하는 기능을 롤아웃하는 중입니다. 제품 **대금 청구** 로 이동 하 고 \> **Your products**구독을 선택한 다음 신용 카드 결제 옆의 **편집** 링크를 선택 합니다.

![화면 캡처: 신용 카드를 지불 방법으로 사용 하 여 구독 카드의 청구 구역입니다.](../media/MAC-BillingEditCreditCard.png)

자세한 내용을 보 시겠습니까? [신용 카드 또는 은행 계좌에서 송장으로 변경](../commerce/billing-and-payments/change-payment-method.md)

### <a name="global-reader"></a>전역 읽기 권한자

Microsoft는 [Ignite Edition 2019](#october-2019---ignite-edition)의 전역 독자 역할에 대해 설명 했지만, 더욱 광범위 하 게 작업을 진행 하는 동안 몇 가지 세부 정보를 살펴보겠습니다.

- 전역 독자 역할은 전역 관리자 역할과 함께 읽기 전용입니다. 전역 읽기 권한자는 전역 관리자가 사용 권한을 갖는 모든 내용을 볼 수 있습니다.
- 일부 일치 및 보안 기능과 같은 몇 가지 예외를 제외 하면 전역 독자는 조직에서 사용이 허가 된 모든 Microsoft 클라우드 관리 센터를 볼 수 있습니다.
- 계획, 감사 및 조사를 위해 필요한 사용자에 게 전역 독자 역할을 할당 합니다.
- 또한 사용 권한이 더 작은 다른 역할과 전역 읽기 권한자 역할을 결합할 수 있습니다. 예를 들어 소규모 비즈니스 소유자에 게 **대금 청구 관리자**  +  **전역 독자** 역할을 할당 하 여 요금을 지불 하 고 클라우드 조직에 대 한 변경 내용을 유지할 수 있습니다.
- 전역 독자는 Microsoft 365 관리 센터의 모든 페이지로 이동할 수 있습니다. 편집 가능한 페이지를 열면 위쪽에 변경 내용을 저장할 수 있는 권한이 없음을 알리는 경고가 표시 되며 저장 단추를 사용할 수 없게 됩니다.

여기에서는 앞으로 보려는 전역 독자 역할 및 모든 역할 기반 권한에 대 한 의견을 얻을 수 있습니다. [역할 기반 권한에 대 한 의견 제공](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/10115430-have-a-consistent-experience-when-assigning-admin)

### <a name="new-settings-page"></a>새 설정 페이지

**조직 프로필**, **보안 & 개인 정보**및 **서비스 & 추가 기능** 페이지는 모두 3 개의 세로 탭이 있는 한 페이지로 결합 됩니다. 그리고 가장 적합 한 부분은 모든 설정을 검색할 수 있는 단일 위치입니다.
![화면 캡처: 페이지 맨 위에 강조 표시 된 "모든 설정 검색" 필드가 있는 설정 페이지입니다.](../media/MAC-SettingsMultiPivotSearch.png)

### <a name="training--docs"></a>문서 & 교육

이 섹션에서는이 문서의 새로운 기능을 소개 하 고, 여기서 흥미로운 정보를 제공 하는 새로운 교육 및 문서에 대 한 링크를 시작 합니다.

11 월 부터는 IT 전문가가 Microsoft 365에 대 한 정보를 습득 하 고 교육을 받을 수 있도록 [microsoft에 대해 설명](https://docs.microsoft.com/learn/) 하는 몇 가지 학습 경로를 발표 했습니다. 체크 아웃 합니다.

- [Microsoft 365 기본 사항](https://docs.microsoft.com/learn/paths/m365-fundamentals/)
- [Office 기본 사항 확장](https://docs.microsoft.com/learn/paths/extend-office-fundamentals/)
- [Microsoft 365-엔터프라이즈 배포에서 Windows 10 및 Microsoft 365 앱 for enterprise Modernize](https://docs.microsoft.com/learn/paths/m365-getmodern/)
- [Microsoft 365를 사용하여 엔터프라이즈 배포 관리](https://docs.microsoft.com/learn/paths/manage-enterprise-deployment-m365/)
- [IT용 Microsoft Office 대규모 업그레이드](https://docs.microsoft.com/learn/paths/m365-office-for-it/)
- [Azure에서 Windows 가상 데스크톱을 사용 하 여 원격 데스크톱 및 앱 제공 ](https://docs.microsoft.com/learn/paths/m365-wvd/)
- [비즈니스용 Microsoft 365 및 Surface를 사용하여 최신 작업 공간 만들기](https://docs.microsoft.com/learn/paths/modernize-workplace-with-m365-and-surface/)
- [Microsoft 365로 ID와 액세스 보호](https://docs.microsoft.com/learn/paths/m365-identity/)
- [Microsoft 365를 사용하여 엔터프라이즈 정보 보호](https://docs.microsoft.com/learn/paths/m365-information-protection/)
- [Microsoft 365를 사용하여 보안 관리하기](https://docs.microsoft.com/learn/paths/m365-security-management/)
- [Microsoft 365와 Microsoft Threat Protection으로 위협으로부터 보호하세요.](https://docs.microsoft.com/learn/paths/m365-security-threat-protection/)
- [Microsoft 팀과 팀 공동 작업 관리](https://docs.microsoft.com/learn/paths/m365-manage-team-collaboration/)
- [Microsoft 365에서 SharePoint를 이용한 공동 작업](https://docs.microsoft.com/learn/paths/m365-teams-sharepoint/)

## <a name="october-2019---ignite-edition"></a>10 월 2019 일-Ignite Edition

Microsoft 365 관리 센터의 새로운 기능 Ignite Edition에 오신 것을 환영 합니다. 물론이는 전체 공지 사항 목록이 아니며 몇 가지 강조 사항이 있습니다. 또한 릴리스에 대 한 보다 유용한 정보를 보려면 Ignite 블로그를 확인 하세요.

- [관리-Microsoft 365에 대 한 보안, 생산성 및 네트워크 향상](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/ADMIN-Security-Productivity-and-Network-Enhancements-for/ba-p/964019)
- [Microsoft 팀의 새로운 기능-Ignite 2020](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-New-in-Microsoft-Teams-Ignite-2019/ba-p/937025).

### <a name="role-based-access-control"></a>역할 기반 액세스 제어

6 월에 롤아웃 작업을 시작한 이후로 관리 센터에 역할이 많이 변경 되었습니다.

- **역할 비교** -각 역할에 대해 사용 권한을 비교 하려면 최대 3 개를 선택 합니다. 이렇게 하면 사용자에 게 할당할 최소 허용 역할을 찾는 데 도움이 됩니다. **역할로**이동 하 여 첫 번째 열에 다중 선택 확인란을 사용 하 여 최대 3 개의 역할을 선택한 다음 **역할 비교**를 선택 합니다.

    ![Exchange 관리, 헬프데스크 관리자 및 사용자 관리자 역할 비교](../media/RBAC-CompareRoles.png)

- **즐겨찾기** -즐겨찾기 또는 가장 많이 사용 하는 역할에 별을 추가 하 여 열을 정렬 하거나 필터를 만들어 쉽게 찾을 수 있습니다.
- **활성 사용자**  >  **역할 관리** -역할이 변경 내용에 맞게 업데이트 되었습니다. 역할 목록과 마찬가지로 기본 역할 목록의 범위를 가장 유용 하 게 지정 했지만 **범주별로 모두 표시**를 확장 하 여 모든 역할을 볼 수 있습니다.
- **전역 독자 역할** -사용자에 게 요청 되었습니다. 바로 그거야! [전역 독자](add-users/about-admin-roles.md) 역할!

### <a name="report-an-issue"></a>문제 보고

서비스 상태가 새 스타일로 업데이트 되었으며 서비스 상태 대시보드에 표시 되지 않는 문제의 영향을 받는 경우 Microsoft에 알리는 **문제를 보고할** 수 있습니다. **상태**  >  **서비스 상태**를 이동 합니다.

### <a name="viral-subscriptions"></a>"Viral" 구독

알고 있듯이 사용자는 Power BI 및 앱 연결과 같은 수많은 제품에 무료 구독을 설정할 수 있습니다. 이제 사용자가 시도 했던 "viral 구독"을 볼 수 있습니다. 제품 **대금 청구**로 이동  >  **Your products**합니다. 구독 탭에서 **계정 유형** 필터를 선택 하 여 사용자가 구매한 구독을 확인 합니다. 필요한 경우 이제 계정에서 이러한 구독을 제거할 수 있습니다.

### <a name="user-templates"></a>사용자 서식 파일

서식 파일을 사용 하면 이러한 사용자에 대 한 공유 설정을 저장 했다가 다시 사용 하 여 많은 사용자를 쉽게 추가할 수 있습니다. 역할, 할당 된 라이선스, 연락처 정보, 위치 등의 값을 저장할 수 있습니다. 서식 파일을 사용 하 여 새 사용자를 만들면 이러한 설정에 대해 저장 된 값이 자동으로 만들어집니다. **사용자**  >  **활성 사용자**로 이동한 다음 **사용자 서식 파일** 을 선택 하 여 다시 시도 합니다.

### <a name="office-whats-new-management-preview"></a>Office "새로운 기능" 관리 (미리 보기)

Office 앱에 중요 한 Office 기능을 출시할 때 사용자는 새 기능에 대해 자세히 알아볼 수 있도록 "What 's new" 라는 카드를 받게 됩니다. 사용자에 게 카드를 표시 하지 않으려면 숨길 수 있습니다. 또한 사용자가 카드를 표시 하는 방법을 선택할 수 있습니다. **설정**  >  **Office의 새로운 기능** 으로 이동 하 여 체크 아웃 합니다.

### <a name="sharepoint-url-change"></a>SharePoint URL 변경

기술적으로,이는 Microsoft 365 관리 센터의 news가 아니므로이 소식을 확인 하기 위해 여러분의 의견을 요 합니다.
> [!IMPORTANT]
> 이제 일반 URL을 사용 하 여 SharePoint 관리 센터에 액세스할 수 있습니다. [https://admin.microsoft.com/SharePoint](https://admin.microsoft.com/SharePoint)

자세한 내용은 [SharePoint 관리 센터의 새로운 기능](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)을 참조 하세요.

## <a name="september-2019"></a>2019년 9월

Ignite 2019의 몇 가지 흥미로운 기능 릴리스에 대 한 램프는 몇 년 9 월에 출시 된 몇 가지 새로운 기능만 발표 하 고 있습니다. 하지만 다음 달의 문서에 대해서는 Ignite의 첫 번째 날에 게시 될 예정입니다.

### <a name="featured-feedback-fix--the-option-to-convert-the-deleted-users-mailbox-to-a-shared-mailbox-is-back"></a>중요 한 피드백 수정 – 삭제 된 사용자 사서함을 공유 사서함으로 변환 하는 옵션이 반환 됩니다.

사용자 의견을 크게 주고 지우고, 사용자가 삭제 된 사용자의 사서함에 액세스할 수 있는 권한을 **공유 사서함**으로 변환 하 여 다시 제공 합니다. 사용자 삭제 마법사에 다시 추가 하면 데이터를 사용 하 여 수행할 작업을 결정할 수 있습니다.

- 전자 메일: 다른 사용자에 게 삭제 된 사용자의 사서함을 공유 사서함으로 변환 하 여 액세스할 수 있는 권한을 부여 합니다.
- 파일: OneDrive 파일을 저장 하 고 다른 사용자에 게 액세스 권한을 부여 합니다.
- 사용 권한: 다른 사용자에 게이 사서함에 대 한 액세스 권한이 있는 경우 사용 권한을 제거 합니다.
- 별칭: 다른 사용자에 게 즉시 사용할 수 있도록 전자 메일 별칭을 제거 합니다.
![화면 캡처: 전자 메일 별칭, 사용 권한, OneDrive 및 전자 메일 옵션이 표시 된 사용자 삭제 마법사](../media/WhatsNew-DeleteUserWiz.png)

### <a name="initial-setup"></a>초기 설치

다른 초기 설치 마법사에 대 한 업데이트는 다음과 같습니다 (Microsoft 365 for business). 이 단계는 간소화 되었으며 두 가지 설정 작업을 설정 페이지로 이동 했습니다.

- **보안 windows 10 컴퓨터** -해커의 바이러스, 맬웨어 및 공격 으로부터 windows 10 장치를 보다 효율적으로 보호 하기 위한 정책을 설정 합니다.
- **Office를 자동으로 설치** -이 옵션을 켜면 사용자가 Pc를 Microsoft 365 Business에 연결 하면 컴퓨터가 최신 Office 앱으로 자동 업데이트 되 고 최신 상태로 유지 됩니다.

## <a name="august-2019"></a>2019년 8월

### <a name="billing"></a>청구

이번 달에는 다음과 같은 청구 및 구독 업데이트가 있습니다.

- 장치 기반 구독: Microsoft 365 관리 센터의 장치에 **대해 교육 (장치) 라이선스에 대 한 Microsoft 365 앱** 을 할당 하거나 할당 해제할 수 있습니다. **Microsoft 365 교육용 앱 (장치)** 은 장치에 라이선스를 할당 하는 데 사용할 수 있는 추가 기능 라이선스입니다. 제품 **대금 청구**로 이동 하 여  >  **Your products** 라이선스를 찾고 구입 합니다.
- 사용자 기반 라이선스 관리: **사용자**  >  **활성 사용자** 의 라이선스를 새 스타일에 할당 하는 방법을 업데이트 했습니다. 자세한 내용은 다음을 참조하세요.
  - [사용자에게 라이선스 할당](manage/assign-licenses-to-users.md)
  - [사용자의 라이선스 할당 취소](manage/remove-licenses-from-users.md)

### <a name="setup-page-updates"></a>페이지 업데이트 설정

이제 기능 설정 및 조직 설정에서 다음 단계를 지능적으로 제안 하는 섹션 **에 대 한 권장** 사항을 비롯 하 여 설치 프로그램에 범주 및 섹션이 포함 되어 있습니다. 또한 설정할 새 기능을 추가 했습니다.

- **Office Advanced Threat Protection** -조직에서 Office ATP를 사용 하도록 라이선스가 부여 되었으며이를 아직 구성 하지 않았거나 설정 하지 않은 경우이 페이지가 표시 됩니다. **설정** 으로 이동 하 여 다시 시도 합니다.

### <a name="report-an-issue-august"></a>문제 보고 (8 월)

서비스 상태 대시보드에 표시 되지 않는 문제의 영향을 받는 경우 **문제 보고서** 를 통해 신속 하 고 간편 하 게 알 수 있습니다. **상태**  >  **서비스 상태**를 이동 합니다.

## <a name="july-2019"></a>2019년 7월

### <a name="message-center"></a>메시지 센터

메시지 센터가 새 디자인으로 업데이트 되었으며 놀라운 모양입니다.

![화면 캡처: ' 모든 활성 메시지 ' 탭을 선택 하 고 필터 메뉴를 연 상태에서 메시지 센터를 업데이트 했습니다.](../media/MAC-MessageCenterUpdated.png)

- 이제 **상태별로 메시지**를 볼 수 있습니다. 탭 중 하나를 선택 합니다 ( **모든 활성 메시지**, **중요도 높음**, **읽지 않은 메시지**, 해제 된 **메시지**).
- 범주 **데이터 개인 정보**를 기준으로 필터링 하거나, **변경**, **문제를 방지 하거나 수정할**수 있으며, 정보를 제공 하는 메시지 범주를 **유지할** 수도 있습니다.
- 목록에서 메시지를 선택 하면 명령 모음 **해제**, 읽기 또는 **읽지**않음으로 **표시** 또는 **공유**중 몇 가지 옵션을 사용할 수 있습니다.
- 또한 메시지를 열 때 다음과 같은 추가 옵션을 사용할 수 있습니다.
  - 메시지 링크를 클립보드로 복사 하 여 나중에 저장 하거나 동료와 공유 합니다.
  - 메시지를 **읽음** 또는 **읽지 않음으로**표시 합니다.
  - 메시지에 대 한 의견을 제공 하려면 **like** 또는 **Dislike**를 선택 하면이 메시지와 상관 없는 사용자 의견에 대 한 특정 피드백을 제공 하 라는 의견 창이 열립니다.

### <a name="navigation-pane-intelligence"></a>탐색 창 인텔리전스

 이제 탐색 창에서 마지막 작업을 기억 하 고 사용자가 마지막으로 이전 상태에 창을 표시 합니다. 또한 기본적으로 자주 사용 되는 항목도 표시 되도록 합니다.

### <a name="initial-setup--the-setup-page"></a>설치 페이지 & 초기 설정

조직을 설정 하는 데 도움이 되는 몇 가지 흥미로운 변경 사항이 있습니다. 먼저, **설치** 및 **설정 페이지**간의 차이점을 살펴보겠습니다. **설치 프로그램** 은 Microsoft의 온라인 서비스에 등록 하는 데 사용한 초기 설치 마법사를 참조 합니다. 여기에는 대개 **도메인 연결**, **사용자 추가**및 **Office 앱 다운로드**의 세 가지 특정 단계가 포함 됩니다. **설치 페이지** 는 라이선스를 구매한 기능을 켜면 구독을 최대한 활용 하기 위해 권장 설정 작업을 수행 하는 관리 센터의 페이지입니다.

- **설치** -초기 설치 마법사가 **비즈니스용 Microsoft 365** 구독에 맞게 업데이트 되었습니다. 이 새로운 디자인을 통해 새 조직이 마법사를 보다 빠르게 진행 하 고 성공을 높일 수 있습니다.
- **설정 페이지** **-설정 페이지에서는 구독과** 함께 제공 되는 서비스의 설정 및 보안을 완료 하는 데 도움이 됩니다. 또한 **설정** 페이지에서 해제 된 권장 사항을 볼 수 있습니다. 아직 구독에 사용할 수 있는지 여부를 확인 하려면 **Microsoft 365 관리 센터**  >  **설정**으로 이동 합니다.

### <a name="billing--subscriptions"></a>대금 청구 & 구독

- **소프트웨어** 제품 유형-이제 CSP (클라우드 서비스 공급자)를 통해 구매한 소프트웨어 제품을 볼 수 있습니다. 다운로드 및 키를 보려면 제품 소프트웨어에 대 한 **청구**탭으로 이동  >  **Your products**  >  **Software** 합니다.
- Microsoft 또는 타사 공급자 로부터 구매한 경우에 든 Microsoft 365 관리 센터에서 최신 Azure 제품 및 서비스를 볼 수 있습니다. 다음은 포함 된 최신 Azure 제품의 예입니다.
  - Azure 예약 가상 인스턴스
  - Azure 지원 계획
  - Azure 하이브리드 사용 혜택 (AHUB)
  - 응용 프로그램 관리
  - 장치 서비스
  - Azure 구독

### <a name="simplify-multi-factor-authentication"></a>다단계 인증 간소화

관리자는 조직의 중요 한 정보에 액세스할 수 있습니다. 로그인 할 때 모든 관리자에 게 multi-factor authentication을 사용 하도록 요청 합니다. 새 마법사를 사용 하면 한 단계 만으로 작업을 수행할 수 있습니다. 이를 수행 하려면 **설치**  >  **보안 강화**로 이동 합니다.

### <a name="users"></a>사용자

**삭제 된 사용자** 및 **게스트 사용자** 페이지가 새 스타일로 업데이트 됩니다.

- **게스트 사용자**: SharePoint 또는 OneDrive에서 파일을 보거나 공유 하도록 초대 하 여 게스트 사용자를 추가 합니다. **사용자**  >  **게스트 사용자**로부터 게스트 사용자를 볼 수 있습니다.
- **Deleted users**: 업데이트 된 **삭제 한 사용자** 페이지에서 이전 관리 센터에서 사용할 수 있는 모든 작업을 수행할 수 있지만 이제는 열을 추가 및 제거 합니다. 다양 한 열 옵션을 선택할 수 있습니다. 실제로는 **활성 사용자** 페이지에서 선택할 수 있는 열과 동일 합니다.

## <a name="june-2019"></a>2019년 6월

### <a name="featured-feedback-request---dark-mode"></a>주요 피드백 요청-어둡게 모드

어둡게 모드에서 관리 센터를 보는 것은 미리 보기에 있습니다. 지금은 **홈** 페이지에서 바로 테스트할 수 있습니다. **홈** 페이지의 **새** 소식 링크 옆에 있는 명령 모음에 **어두운 모드** 단추가 표시 됩니다.

### <a name="roles-management"></a>역할 관리

6 월 말에 관리자 역할을 관리 하는 새로운 방법을 구축 하기 시작 했습니다. 사용자가이 기능을 사용할 수 있는 경우 **역할**  >  **역할로**이동 합니다. 그때 까지는 awesome을 살펴보겠습니다.
<br> ![화면 캡처: 사용자 관리자 역할 세부 정보 창이 강조 표시 된 관리 역할 목록입니다.](../media/MAC-AdminRoles-Featured.png) <br>

이러한 새로운 환경에서는 관리자 권한을 가진 사용자를 보다 쉽게 확인 하 고 관리자에 게 적절 한 수준의 액세스 권한을 부여 하는 역할을 할당할 수 있습니다. 또한 여러 관리 센터로 갈 시간을 낭비 하지 않도록 Azure AD에서 역할을 추가 했습니다.
그 밖에 어떤 작업을 할 수 있나요?

- Microsoft 365에서 Azure Active Directory 역할이 할당 된 조직의 모든 관리자 목록을 내보냅니다.  
- 특정 역할에 할당 된 관리자를 확인 하 고, 특정 역할에서 관리자를 추가 또는 제거 하 고, 이름 및 키워드로 역할을 검색 하 고, 각 역할에 대해 사용자가 수행할 수 있는 작업에 대해 자세히 알아보세요.
- 특정 역할을 빠르게 검색 하 고 필터를 만듭니다.

### <a name="payment-method"></a>결제 방법

구독 비용을 지불 하는 방법을 업데이트 했습니다. **대금 청구**요금  >  **& 지불**  >  **결제 방법**으로 이동 합니다. 목록 보기에서 결제 방법을 볼 수 있습니다. 목록에서 항목을 선택 하 여 제거 하 고 편집 하 고 결제 방법이 연결 된 구독을 쉽게 확인할 수 있습니다.

## <a name="may-2019"></a>2019년 5월

### <a name="mays-featured-fix---case-sensitivity"></a>주요 수정 사항 (대/소문자 구분)

이제 공유 사서함, 연락처, 리소스 및 사서함 사용 권한을 검색할 때 검색 용어는 대/소문자를 구분 하지 않아도 됩니다.

**사용자 및 그룹 관리** 이번 달에는 **사용자 차단**, **암호 다시 설정**, **연락처** 목록 보기, **그룹** 목록 보기 및 **그룹** 세부 정보 페이지를 새 관리 센터 스타일로 업데이트 했습니다.

- 새 **그룹** 목록 보기를 사용 하 여 그룹에 대 한 보다 다양 한 데이터를 얻고, 데이터 표시 방식을 사용자 지정할 수 있으며, 그룹 목록에서 데이터를 표시 하는 방법을 기억 합니다. 예를 들어 팀의 그룹을 필터링 **하 여** 그룹이 팀의 일부 인지 확인 하 고 **팀 상태** 열을 추가할 수 있습니다.
- 또한 groups list는 빠른 작업 및 상황별 명령 모음을 비롯 하 여 사용자 관리의 목록 환경에 대 한 향상 된 기능을 제공 합니다.

**추천**<br>
관리 센터에 새 추천 팝업이 표시 될 수 있습니다. 물론 조직에 이익이 있다고 생각 되는 경우에만 추천을 볼 수 있습니다. 하지만 권장 사항을 확인할 때까지 기다리지 않으면 카드 라이브러리에서이를 추가할 수 있습니다.

- **암호 만료** -암호가 **만료 되지**않도록 설정 하는 것이 좋습니다. 또한 조직에 다른 설정이 있는 경우에는이 권장 사항이 표시 될 수 있습니다.
- 전역 **관리자** 가 너무 많습니다. 전역 관리자가 너무 많기 때문에 전역 관리자가 4 명 이상인 경우이 권장 사항이 표시 됩니다. 사용자에 게 작업을 완료 하는 데 필요한 액세스만 제공 하는 것이 좋습니다.
- **Intune 장치 보호** -라이선스에 intune이 포함 되어 있고 intune 설정이 완료 되지 않았거나 장치를 등록 하지 않은 것을 감지 하면 사용자가 모바일 장치에서 액세스할 때 조직의 파일을 보호 하는 intune 정책을 만드는 것이 좋습니다.
- **월간 office 기능 업데이트** -사용자가 월별 office 기능 업데이트를 받을 때 그에 대 한 만족도가 매우 작은 고객 으로부터 피드백을 제공 합니다. 따라서 사용자가 매우 작은 비즈니스이 고 6 개월 마다 Office 기능을 업데이트 하는 경우에는이 권장 사항이 표시 됩니다.

**설정** <br>
설정의 경우에는 몇 가지 사항이 크게 변경 되었습니다. 대부분의 경우 기존 설정을 새 관리 센터 스타일로 업데이트 하기만 하면 됩니다. 앞에서 살펴본 것 처럼 새로운 설정을 추가 하 고 앞에서 본 적이 없는 경우에는 여기에서 설명 하기 시작 합니다. 여기에는 **최신 인증**을 알리는 한 가지 전체 설정이 있습니다. 예, **최신 인증**을 설정 하기 위한 새로운 설정이 있습니다. 체크 아웃 하려면 **Settings**  >  **Services & 추가 기능**  >  **최신 인증**으로 이동 합니다.

## <a name="april-2019"></a>2019년 4월

관리 센터에 대 한 유용한 정보 의견 및 제안을 읽은 후 대부분의 사용자에 게 응답 하 고 실제로 모든 작업을 수행 해야 합니다. 물론 이전 관리 센터를 사용 하 여 모든 항목을 패리티가 있는지 확인 하는 작업을 진행 하 고 있습니다. 그리고 새로운 기능을 롤아웃할 때 당장 당장 하지 못할 수 있습니다.

### <a name="featured-feature---add-users"></a>주요 기능 사용자 추가

4 월의 경우 다음을 안내 하는 **사용자 추가** 마법사가 제공 됩니다. 대기 시간 사용자 추가 전자 메일 및 표시 이름 같은 사용자의 기본 정보를 추가 하 고, 라이선스와 역할을 할당 하 고, 연락처 정보를 추가한 다음, 사용자 계정을 커밋 하기 전에 검토 하는 단계별 방법입니다. **변경 되는 이유는 무엇 인가요?** 이전 환경에서 사용자를 추가 하기 위해 거의 무한정 스크롤하지 않았던 의견이 들립니다.
<br> ![사용자 추가 마법사의 화면 캡처](../media/MAC-AddUserWizard.png) <br>

다음 두 가지 방법으로이를 확인할 수 있습니다. <br>

1. **홈** 페이지의 **사용자 관리** 카드에서 **사용자 추가** 를 선택 합니다. 마법사가 제대로 열리므로 **홈** 페이지에서 수행 중인 작업을 탐색 하지 않아도 됩니다.
2. **사용자**  >  **활성 사용자**로 이동한 후 명령 모음에서 **사용자 추가** 를 선택 합니다.
<br><br>

여기서는 **사용자 관리**를 몇 가지 더 변경 했으며, 다음은 간단한 목록입니다.

- **역할 관리** 창이 새 스타일로 업데이트 되었으며 액세스 가능 합니다. **사용자 차단** 및 **사용자 삭제** 창도 새 스타일로 업데이트 했습니다.
- **제품 라이선스 관리** 명령 모음에서 변경 된 위치입니다.
- 이제 사용자의 사진을 변경 하기가 더 쉽습니다. **활성 사용자** 에서 사용자를 선택 하 고 사진 아래의 **사진을 변경** 합니다.

### <a name="but-wait-theres-more"></a>하지만 기다려! 거기 더 있어

- **홈** 페이지에는 도메인을 추가 하 고, 사용자를 추가 하 고, Office 앱을 다운로드 하는 것과 같은 설정 단계를 완료 하지 않은 경우를 볼 수 있는 새로운 설정 배너가 있습니다.
- **그룹** 목록 및 세부 정보 창이 새 스타일로 업데이트 되었습니다. **그룹**  >  **그룹** 으로 이동 하 여 변경 내용을 확인 합니다.
  - 그룹에 대 한 이야기에는 microsoft 365 그룹을 팀으로 바꿀 수 있는 그룹 세부 정보 창에 **Microsoft 팀** 탭도 추가 되었습니다. 그룹을 "teamify" 하려면 목록에서 Microsoft 365 그룹을 선택 하 고 **Microsoft 팀** 탭을 선택한 다음 팀을 **만듭니다**. 그룹이 이미 팀 인 경우 **팀 관리 센터**에서 해당 그룹을 관리 하기 위한 링크를 받게 됩니다.
  - 마지막으로 **팀 상태** 를 **그룹** 목록에 추가할 수 있습니다. 열 머리글에서 **Choose columns**  >  **팀 상태**  >  **저장**열을 선택 합니다.
- **제한 된 새 관리 역할** -사용자에 게 필요한 액세스 권한만 제공할 수 있도록 몇 가지 새 관리 역할을 릴리스 했습니다.
  - **Kaizala admin**:이 역할의 사용자에 게는 Kaizala 디렉터리에서 사용자 만들기 및 관리, Kaizala 그룹 관리, 작업 카드 및 커넥터 관리, 서비스 요청 만들기 등 Microsoft Kaizala 내의 모든 관리 작업을 수행할 수 있는 권한이 있습니다.
  - **검색 관리**:이 역할의 사용자는 microsoft 365 관리 센터의 모든 microsoft 검색 관리 기능에 대 한 모든 권한을 갖습니다. 검색 관리자는 검색 관리자 및 검색 편집기 역할을 사용자에 게 위임 하 고 책갈피, Q&항목 및 위치와 같은 콘텐츠를 만들고 관리할 수 있습니다. 또한 이러한 사용자는 메시지 센터를 확인 하 고 서비스 상태를 모니터링 하 고 서비스 요청을 만들 수 있습니다.
  - **검색 편집기**:이 역할의 사용자는 책갈피, Q&항목 및 위치를 포함 하 여 Microsoft 365 Search에 대 한 콘텐츠를 만들고 관리 하 고 삭제할 수 있습니다.
- 이번 달에는 bonanza에 대 한 **청구** 변경 내용이 있습니다.
  - 이제 CVV를 삭제 하 고 다시 추가할 필요 없이 기존 신용 카드에 대 한 업데이트를 업데이트할 수 있습니다. **자재 명세서**  >  **지불 방법**으로 이동 하 여 CVV를 업데이트할 수 있습니다.
    - 이를 통해 더 쉽게 **송장을** 찾고 계정에 있는 청구 문제를 파악할 수 있습니다. 이제 PDF를 다운로드 하는 대신 웹 브라우저에서 청구서를 볼 수 있습니다. **자재 명세서**  >  **송장**으로 이동 합니다.
    - 같은 유형의 구독이 여러 개 있는 경우 **제품** 페이지에서 이제 구독 정보를 집계 합니다.

## <a name="march-2019---weve-officially-released-the-admin-center"></a>3 월 2019-관리 센터를 공식적으로 릴리스 했습니다.

화려한 소식에 대 한 자세한 내용은 Microsoft 365 관리 센터의 새로운 기능과 향상 된 기능을 공식적으로 릴리스 했습니다. 여기에 발표 된 블로그 게시물은 [현재 사용할 수 있는 새로운 Microsoft 365 관리 센터](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/The-new-Microsoft-365-admin-center-available-today/ba-p/377870)입니다. 3 월의 경우 블로그 게시물에 의존 하 여 출시 된 기능을 확인 하 고, 앞으로 출시 되는 기능에 대 한 게시물을 읽고 핵심 콘텐츠를 사용할 수 없습니다.
<br> ![Microsoft 365 관리 센터 홈 페이지의 화면 캡처](../media/M365AC-HomePage.png) <br>
여기서는 **대금 청구 & 구독** 영역에 대 한 변경 내용을 한 가지 제공 합니다. Y'all를 개선 하 여 작업을 완료 했다고 생각 하지 않습니까? 지금은 진행 되지 않습니다. 실제로 이번 달에는 파트너 관계를 관리 하는 기능을 **대금 청구**계정에 추가 하는 기능이 추가 되었습니다  >  **Billing accounts**. 여기에서 관리자, CSP 및 간접 대리점에서 파트너 관계를 검토할 수 있습니다. 위임 된 관리 권한을 포함 하 여 새 파트너 관계 요청을 수락할 수도 있습니다.

사용자 의견은 언제나 여러분에 게 중요 하므로 계속 해 서 제공 하세요. 관리 센터의 모든 페이지에서 오른쪽 아래에 있는 **의견 제공** 을 선택한 다음 **도움말 보기** 를 선택 하 여 피드백을 제공할 수 있습니다.

## <a name="february-2019---billing--subscriptions-edition"></a>2019 년 2 월 & 구독 에디션

이번 달에는 "청구 및 구독" 이라고 하는 affectionately 영역에 적용 된 모든 기능에 대해 중점적으로 살펴보겠습니다. 이 경우에는 이러한 항목을 affectionately는 것은 아니지만 이제는 지금까지 생각 합니다.

- **결제 방법** -결제 방법을 업데이트 하는 것이 어려운 의견이 발생 했으며,이를 통해 많은 변화가 있었습니다. **대금 청구**  >  **지불 방법**으로 이동 합니다. 귀하의 결제 방법, 사용자의 지불 방법, 연결 된 구독 등을 쉽게 확인할 수 있습니다. 결제 방법 목록에서 기타 메뉴 (만료 날짜 옆에 3 **개** 작은 점)를 선택한 다음 **구독 보기**를 선택 합니다. **기타** 메뉴를 사용 하 여 결제 방법을 편집 하 고 삭제할 수도 있습니다.
- **청구 계정** -대상 지정 된 릴리스 고객에 게는 새 대금 청구 계정 페이지가 먼저 표시 되 고,이 페이지를 세계 전체에 롤아웃할 예정입니다. 사용할 수 있게 되 면 **대금 청구**  >  **계정**으로 이동 합니다. 새 대금 청구 계정 페이지에서 수행할 수 있는 작업 질문을 하 고 싶습니다.
  - 조직 프로필의 주소 및 기타 연락처 정보를이 페이지에서 직접 업데이트 합니다. **Settings**  >  원하는 경우가 아니면 설정**조직 프로필로**이동할 필요가 없습니다.
  - 또한 직접 또는 볼륨 라이선스 고객을 위해 더 쉽게 작업을 수행할 수 있으므로 **대금 청구 계정의**고객 계약을 수락 하 고 검토 하는 것이 좋습니다. 또한 다른 조직을와 연결 하 여 조직을를 연결 하 여 라이선스 및 리소스를 공유할 수도 있습니다.
- 또한 몇 가지 더 작은 향상 된 기능과 버그 수정도 수행 했습니다.
  - 송장 지불로 구독 다시 활성화
  - 구독에 대 한 서비스 사용 주소 편집
  - 또한 인벤터리 세부 정보 페이지에 몇 가지 알림 기능이 추가 되었으며, 작업을 수행할 수 있는 실제 페이지로 연결 되 고 재고 정보 카드에 더 많은 작업이 포함 됩니다. **청구**금액으로 이동 하 여  >  **Bills**  >  모든 송장에 대 한**세부 정보 보기**

## <a name="january-2019---happy-new-year"></a>1 월 2019 일, 신규 해 아침

- 여전히 **& 서비스** 에 추가 기능을 추가 하는 경우 추가 기능 페이지를 **& > 서비스** 에 대 한 설정이 더 많이 업데이트 되었습니다. 통합 된 앱 이나 보고서에서 최신 항목을 확인 해 보세요.
- **향상 된 기능 검색** 명령 모음의 **검색** 상자 보다 더 보기 작업을 검색할 수 있도록 업데이트 되었습니다. 예를 들어 "암호 다시 설정" 또는 "사용자 추가"를 시도 합니다.

### <a name="featured-feedback-fix---licenses-and-apps"></a>주요 피드백 수정-라이선스 및 앱

의견에 따라 사용자 세부 정보 창에 **라이선스 및 앱** 이 다시 결합 됩니다. 처음에는 모든 라이선스에 대 한 세부 정보 및 모든 앱 가능성을 위한 공간을 제공 하도록 두 기능을 분리 했습니다. 사용권 및 앱을 두 개의 창으로 구분 하는 것은 혼동을 추가한 사용자 로부터 들었습니다. 또한 라이선스 및 앱을 하나의 탭으로 다시 수신 대기 하 고 제공 합니다. 이제 한 창에서 사용자에 게 할당 된 모든 라이선스에 대해 앱이 해제 되도록 할 수 있습니다. Milk 및 cookies 라이선스 및 앱. 지금 다운로드 합니다.

체크 아웃: 사용자 **> 활성 사용자 >** **사용자 > 라이선스 및 앱을** 편집 하거나 추가할 수 있습니다.
