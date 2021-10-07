---
title: 공격 시뮬레이션 교육 배포 고려 사항 및 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 관리자는 계획 2 조직용 Microsoft Defender 또는 Microsoft 365 E5 시뮬레이션 및 교육과 관련하여 배포 고려 사항과 Office 365 정보를 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 19b8997a5f2d1f8df40c740fb996432b13a21d3b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196600"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>공격 시뮬레이션 교육 배포 고려 사항 및 FAQ

공격 시뮬레이션 교육은 이제 일반적으로 [사용할 수 있습니다.](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291) 공격 시뮬레이션 교육은 Microsoft 365 E5 또는 Microsoft Defender for Office 365 계획 2 조직이 실제 피싱 페이로드를 통해 강화된 피싱 시뮬레이션을 생성 및 관리할 수 있도록 하여 소셜 엔지니어링 위험을 측정하고 관리할 수 있도록 합니다. Terranova 보안과 협력하여 제공된 하이퍼 대상 교육은 지식을 개선하고 직원의 행동을 변경하는 데 도움이 됩니다.

공격 시뮬레이션 교육을 시작하는 데 대한 자세한 내용은 공격 시뮬레이션 교육 사용 [시작을 참조하세요.](attack-simulation-training-get-started.md)

전체 시뮬레이션 만들기 및 예약 환경은 자유 흐름과 마찰 없이 설계된 반면, 엔터프라이즈 규모에서 시뮬레이션을 실행하려면 계획이 필요한 경우가 종종 있습니다. 이 문서는 고객이 자체 환경에서 시뮬레이션을 실행할 때 직면하는 특정 문제를 해결할 수 있도록 지원합니다.

## <a name="issues-with-end-user-experiences"></a>최종 사용자 환경의 문제

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>Google 금고 차단된 피싱 시뮬레이션 URL

URL 신뢰도 서비스는 공격 시뮬레이션 교육에 사용되는 하나 이상의 URL을 안전하지 않은 것으로 식별할 수 있습니다. Google 금고 검색을 통해 시뮬레이션된 피싱 URL 중 일부를 기만 사이트 미리 **메시지로 차단합니다.** 항상 시뮬레이션 URL을 허용하기 위해 많은 URL 신뢰도 공급업체와 협력하고 있습니다. 그러나 항상 전체 범위가 있는 것은 아니며,

![Google Chrome에서 기만적인 사이트 경고.](../../media/attack-sim-chrome-deceptive-site-message.png)

이 문제는 이 문제의 영향을 Microsoft Edge.

계획 단계의 일부로 피싱 캠페인에서 URL을 사용하기 전에 지원되는 웹 브라우저에서 URL의 가용성을 확인하십시오. Google 금고 검색에서 URL을 차단하는 경우 Google의 [](https://support.google.com/chrome/a/answer/7532419) 이 지침을 따라 URL에 대한 액세스를 허용합니다.

공격 [시뮬레이션](attack-simulation-training-get-started.md) 교육에서 현재 사용되는 URL 목록에 대한 공격 시뮬레이션 교육 사용 시작을 참조하세요.

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>네트워크 프록시 솔루션 및 필터 드라이버에 의해 차단되는 피싱 시뮬레이션 및 관리자 URL

피싱 시뮬레이션 URL과 관리자 URL은 모두 중간 보안 장치 또는 필터에 의해 차단되거나 삭제될 수 있습니다. 예제:

- 방화벽
- WAF(웹 응용 프로그램 방화벽) 솔루션
- 타사 필터 드라이버(예: 커널 모드 필터)

이 계층에서 차단되는 고객은 거의 없는 반면에 이 문제가 발생했습니다. 문제가 발생하는 경우 필요한 경우 보안 장치 또는 필터의 검색을 무시하기 위해 다음 URL을 구성하는 것이 있습니다.

- 공격 시뮬레이션 교육 시작에 설명된 시뮬레이션된 피싱 [URL입니다.](attack-simulation-training-get-started.md)
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>모든 대상 사용자에게 배달되지 않는 시뮬레이션 메시지

실제로 시뮬레이션 전자 메일 메시지를 받는 사용자 수가 시뮬레이션 대상 사용자 수보다 적을 수 있습니다. 대상 유효성 검사의 일부로 제외되는 사용자 유형은 다음과 같습니다.

- 받는 사람 전자 메일 주소가 잘못되었습니다.
- 게스트 사용자.
- Azure AD(Azure Ad)에서 더 이상 Azure Active Directory 사용자입니다.

유효한 사서함이 있는 게스트가 아닌 유효한 사용자만 시뮬레이션에 포함됩니다. 메일 그룹 또는 메일 사용이 가능한 보안 그룹을 사용하여 사용자를 대상으로 지정하는 경우 Exchange Online [PowerShell에서](/powershell/exchange/connect-to-exchange-online-powershell) [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) cmdlet을 사용하여 메일 그룹 구성원을 보고 유효성을 검사할 수 있습니다.

## <a name="issues-with-attack-simulation-training-reporting"></a>공격 시뮬레이션 교육 보고 관련 문제

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>공격 시뮬레이션 교육 보고서에는 활동 세부 정보가 포함되지 않습니다.

공격 시뮬레이션 교육에는 직원의 위협 준비 진행 상황을 알려주는 풍부한 실행 가능한 인사이트가 함께 제공될 수 있습니다. 공격 시뮬레이션 교육 보고서에 데이터가 채워지지 않은 경우 조직에서 감사 로그 검색이 켜져 있는지(기본적으로 켜져 있는지) 확인해야 합니다.

감사 로그 검색은 이벤트를 캡처, 기록 및 다시 읽을 수 있도록 공격 시뮬레이션 교육에 필요합니다. 감사 로그 검색을 끄면 공격 시뮬레이션 교육에 다음과 같은 결과가 표시됩니다.

- 일부 보고서에서는 보고 데이터를 사용할 수 없습니다. 보고서가 비어 있는 것으로 표시됩니다.
- 데이터를 사용할 수 없는 경우 교육 배정이 차단됩니다.

감사 로그 검색을 설정하려면 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)

> [!NOTE]
> 또한 사용자에게 E5 라이선스가 할당되지 않은 경우 빈 활동 세부 정보가 발생할 수도 있습니다. 보고 이벤트가 캡처 및 기록되도록 활성 사용자에게 하나 이상의 E5 라이선스가 할당되어 있는지 확인

### <a name="simulation-reports-are-not-updated-immediately"></a>시뮬레이션 보고서가 즉시 업데이트되지 않습니다.

자세한 시뮬레이션 보고서는 캠페인을 시작한 직후에 업데이트되지 않습니다. 걱정하지 마세요. 이 동작은 예상됩니다.

모든 시뮬레이션 캠페인에는 수명 주기가 있습니다. 처음 만들 때 시뮬레이션은 **예약된 상태입니다.** 시뮬레이션이 시작되면 진행 중 **상태로 전환됩니다.** 완료되면 시뮬레이션이 **완료된 상태로 전환됩니다.**

시뮬레이션이 예약된  상태일 때 시뮬레이션 보고서는 대부분 비어 있습니다. 이 단계에서 시뮬레이션 엔진은 대상 사용자 전자 메일 주소를 확인하거나, 메일 그룹을 확장하고, 목록에서 게스트 사용자를 제거하는 등입니다.

![예약된 상태의 보고](../../media/attack-sim-empty-reporting.png)

시뮬레이션이 진행 중 **단계에 들어오면** 보고에 들어가기 시작하는 정보를 알 수 있습니다.

![진행 중 상태의 보고](../../media/attack-sim-in-progress.png)

진행 중 상태로 전환한 후 개별 시뮬레이션 보고서가 업데이트되는 데 최대 30분이 걸릴 **수** 있습니다. 시뮬레이션이 **Completed** 상태가 될 때까지 보고서 데이터가 계속 빌드됩니다. 보고 업데이트는 다음과 같은 간격으로 발생합니다.

- 처음 60분마다 10분마다.
- 60분 후 2일까지 15분마다
- 2일 후 7일까지 30분마다
- 7일 후 60분마다

개요 페이지의  위젯은 시간 경과에 따라 조직의 시뮬레이션 기반 보안 자세에 대한 빠른 스냅숏을 제공합니다. 이러한 위젯은 시간 경과에 따라 전반적인 보안 자세와 여정을 반영하기 때문에 각 시뮬레이션 캠페인이 완료된 후 업데이트됩니다.

> [!NOTE]
> 다양한 보고 페이지에서 **내보내기** 옵션을 사용하여 데이터를 추출할 수 있습니다.

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>사용자가 피싱으로 보고한 메시지가 시뮬레이션 보고서에 나타나지 않습니다.

공격 시뮬레이터 교육의 시뮬레이션 보고서는 사용자 활동에 대한 세부 정보를 제공합니다. 예제:

- 메시지의 링크를 클릭한 사용자입니다.
- 자격 증명을 포기한 사용자입니다.
- 메시지를 피싱으로 보고한 사용자입니다.

피싱으로 보고된 메시지가 공격 시뮬레이션 교육 시뮬레이션 보고서에 캡처되지 않은 경우 보고된 메시지의 Microsoft로의 배달을 차단하는 Exchange 메일 흐름 규칙(전송 규칙)이 있을 수 있습니다. 메일 흐름 규칙이 다음 전자 메일 주소로의 배달을 차단하지 않는지 확인

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- junk@office365.microsoft.com \_

## <a name="other-frequently-asked-questions"></a>기타 질문과 대답

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>Q: 시뮬레이션 캠페인을 대상으로 지정하는 데 권장되는 방법은 무엇입니까?

A: 대상 사용자에게 다음과 같은 몇 가지 옵션을 사용할 수 있습니다.

- 모든 사용자를 포함합니다(현재 사용자가 40,000명 미만인 조직에서 사용 가능).
- 특정 사용자를 선택 합니다.
- CSV 파일(줄당 하나의 전자 메일 주소)에서 사용자를 선택합니다.
- Azure AD 그룹 기반 대상 지정.

Azure AD 그룹에서 대상 사용자를 식별하는 캠페인을 일반적으로 더 쉽게 관리할 수 있습니다.

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>Q: CSV에서 가져오거나 사용자를 추가하는 동안 사용자를 대상으로 지정하는 데 제한이 있습니까?

A: CSV 파일에서 받는 사람을 가져오거나 시뮬레이션에 개별 받는 사람을 추가하는 제한은 40,000개입니다.

받는 사람은 개별 사용자 또는 그룹일 수 있습니다. 그룹에는 수백 또는 수천 명의 받는 사람이 포함될 수 있으므로 개별 사용자 수에 대한 실제 제한이 설정되지 않습니다.

큰 CSV 파일을 관리하거나 개별 받는 사람을 여러 개 추가하는 것이 번거로우면 됩니다. Azure AD 그룹을 사용하여 시뮬레이션의 전체 관리를 간소화합니다.

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>Q: Microsoft에서 다른 언어로 페이로드를 제공합니까?

A: 현재 사용할 수 있는 지역화된 페이로드는 5개입니다. 기존 페이로드를 다른 언어로 직접 또는 기계 번역하면 부정확성 및 줄어든다는 사실이 발견했습니다.

즉, 사용자 지정 페이로드 제작 환경을 사용하여 원하는 언어로 직접 페이로드를 만들 수 있습니다. 또한 특정 지리에서 사용자를 대상으로 지정하는 데 사용된 기존 페이로드를 수집하는 것이 좋습니다. 즉, 공격자가 콘텐츠를 지역화할 수 있습니다.

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>Q: 관리자 포털 및 교육 환경을 위해 다른 언어로 전환하려면 어떻게 하나요?

A: Microsoft 365 Office 365 사용자 계정에 대해 언어 구성이 구체화되어 중앙 집중화됩니다. 언어 설정을 변경하는 방법에 대한 지침은 비즈니스용 Microsoft 365 표시 언어 및 표준 [시간대 변경을 참조하세요.](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)

구성 변경 내용이 모든 서비스에서 동기화하는 데 최대 30분이 걸릴 수 있습니다.

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>Q: 본격적인 캠페인을 시작하기 전에 테스트 시뮬레이션을 트리거하여 어떻게 보이는지 이해할 수 있나요?

A: 예! 마법사의 **마지막** 시뮬레이션 검토 페이지에서 새 시뮬레이션을 만들 수 있습니다. 테스트 보내기 옵션이 **있습니다.** 이 옵션은 현재 로그인한 사용자에게 샘플 피싱 시뮬레이션 메시지를 전송합니다. 받은 편지함에서 피싱 메시지의 유효성을 검사한 후 시뮬레이션을 제출할 수 있습니다.

![시뮬레이션 검토 페이지에서 테스트 단추를 보내십시오.](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>Q: 동일한 시뮬레이션 캠페인의 일부로 다른 테넌트에 속한 사용자를 대상으로 할 수 있나요?

대답: 아니요. 현재 테넌트 간 시뮬레이션은 지원되지 않습니다. 모든 대상 사용자가 동일한 테넌트에 있는지 확인 테넌트 간 사용자 또는 게스트 사용자는 시뮬레이션 캠페인에서 제외됩니다.

### <a name="q-how-does-region-aware-delivery-work"></a>Q: 지역 인식 배달은 어떻게 작동하나요?

A: 지역 인식 배달은 대상 사용자 사서함의 TimeZone 특성과 '이전' 논리를 사용하여 메시지를 배달할 시기를 지정합니다. 예를 들어 다음 시나리오를 고려합니다.

- 태평양 표준 시간대(UTC-8)의 오전 7:00에 관리자는 캠페인을 만들고 같은 날 오전 9시에 시작을 예약합니다.
- UserA는 동부 표준 시간대(UTC-5)에 있습니다.
- UserB는 태평양 표준 시간대에도 있습니다.

같은 날 오전 9시에 시뮬레이션 메시지가 UserB로 전송됩니다. 태평양 표준시(태평양 표준시)는 동부 표준시 오후 12시이기 때문에 지역 인식 배달을 사용할 경우 메시지는 같은 날에 UserA로 전송되지 않습니다. 대신 메시지는 다음 날 동부 시간으로 오전 9시에 UserA로 전송됩니다.

따라서 지역 인식 배달이 설정된 캠페인의 초기 실행 시 시뮬레이션 메시지가 특정 표준 시간대의 사용자에게만 전송된 것으로 표시될 수 있습니다. 그러나 시간이 지나고 더 많은 사용자가 범위로 들어오면 대상 사용자가 늘어나게 됩니다.