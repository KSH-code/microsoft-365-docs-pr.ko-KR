---
title: 2013에서 자동화된 조사 결과를 Microsoft 365
keywords: AIR, autoIR, Endpoint용 Microsoft Defender, 자동화, 조사, 수정, 작업
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 2013에서 자동화된 조사를 Microsoft 365 결과 및 주요 결과를 볼 수 있습니다.
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80c58c0e4c084199537dcfbb9097541a0cba71a0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191422"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>2013에서 자동화된 조사의 세부 정보 및 Microsoft 365

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft [](office-365-air.md) [Defender에서](defender-for-office-365.md)자동화된 조사가 Office 365 자동화된 조사 프로세스가 진행되는 동안 및 이후에 이 조사에 대한 세부 정보를 사용할 수 있습니다. 필요한 권한이 있는 경우 사이트 포털에서 해당 세부 Microsoft 365 Defender 있습니다. 조사 세부 정보는 최신 상태를 제공하고 보류 중인 작업을 승인할 수 있는 기능을 제공합니다.

> [!TIP]
> Microsoft 365 Defender 통합 조사 페이지를 참조하세요. 자세한 내용은 [(NEW!)를 참조하세요. 통합 조사 페이지.](../defender/m365d-autoir-results.md#new-unified-investigation-page)

## <a name="investigation-status"></a>조사 상태

조사 상태는 분석 및 작업의 진행률을 나타냅니다. 조사가 실행되면 위협이 발견된지 여부와 작업이 승인된지 여부를 나타내기 위해 상태가 변경됩니다.

<br>

****

|상태|설명|
|---|---|
|**시작 중**|조사가 트리거되고 실행을 기다리는 중입니다.|
|**실행 중**|조사 프로세스가 시작된 후 진행 중입니다. 이 상태는 보류 중인 작업이 [승인된](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) 경우도 발생합니다.|
|**위협 없음**|조사가 완료된 후 위협(사용자 계정, 전자 메일 메시지, URL 또는 파일)을 식별하지 않았습니다. <p> **팁:** 누락된 것으로 의심되는 경우(예: 거짓 부정) 위협 탐색기를 사용하여 조치를 [취할 수 있습니다.](threat-explorer.md)|
|**위협 발견**|자동화된 조사에서 문제가 발견되지만 이러한 문제를 해결하기 위한 구체적인 수정 작업은 없습니다. <p> 위협 **발견** 상태는 특정 유형의 사용자 활동이 식별되지만 정리 작업을 사용할 수 없는 경우에 발생할 수 있습니다. 예를 들어 다음과 같은 사용자 활동이 있습니다. <ul><li>데이터 [손실 방지](../../compliance/dlp-learn-about-dlp.md) 이벤트</li><li>이상을 보내는 전자 메일</li><li>보낸 맬웨어</li><li>보낸 피싱</li></ul> <p> 조사 결과 수정해야 하는 악의적인 URL, 파일 또는 전자 메일 메시지는 발견되지 않았습니다. 전달 규칙이나 위임 해제와 같은 사서함 활동은 발견되지 않았습니다. <p> **팁:** 누락된 것으로 의심되는 경우(예: 거짓 부정) 위협 탐색기를 사용하여 조사하고 조치를 [취할 수 있습니다.](threat-explorer.md)|
|**시스템에 의해 종료됩니다.**|조사가 중지되었습니다. 조사는 몇 가지 이유로 중지될 수 있습니다. <ul><li>조사 보류 중인 작업이 만료되었습니다. 1주일 동안 승인을 기다린 후 보류 중인 작업 시간이 시간 미정</li><li>작업이 너무 많습니다. 예를 들어 악의적인 URL을 클릭하는 사용자가 너무 많은 경우 모든 분석기를 실행할 수 있는 조사 기능을 초과할 수 있으므로 조사가 중단됩니다.</li></ul> <p> **팁:** 작업이 수행되기 전에 조사가 중단된 경우 [위협](threat-explorer.md) 탐색기를 사용하여 위협을 찾아 해결해 하세요.|
|**보류 중인 작업**|조사 결과 악성 전자 메일, 악의적인 URL 또는 위험한 사서함 설정과 위협이 승인을 대기하고 있는 위협을 수정하기 위한 [조치를 발견했습니다.](air-review-approve-pending-completed-actions.md) <p> 해당 **작업이** 있는 위협이 발견되면 보류 중인 작업 상태가 트리거됩니다. 그러나 조사가 실행될 때 보류 중인 작업 목록이 늘어날 수 있습니다. 조사 세부 정보를 확인하여 다른 항목이 아직 완료 보류 중인지 확인|
|**수정**|조사가 완료된 후 모든 수정 작업이 승인되었습니다(완전히 수정된 것으로 알려됨). <p> **참고:** 승인된 수정 작업에는 작업이 수행되지 않도록 하는 오류가 발생할 수 있습니다. 재구성 작업이 성공적으로 완료된지 여부에 관계없이 조사 상태는 변경되지 않습니다. 조사 세부 정보를 시청합니다.|
|**부분적으로 수정**|조사 결과 수정 작업이 수행된 후 일부는 승인 및 완료되었습니다. 다른 작업은 여전히 [보류 중입니다.](air-review-approve-pending-completed-actions.md)|
|**실패**|하나 이상의 조사 분석기가 제대로 완료되지 않는 문제가 발생했습니다. <p> **참고** 재구성 작업이 승인된 후에도 조사가 실패하면 수정 작업이 성공할 수 있습니다. 조사 세부 정보를 시청합니다.|
|**스로틀에 의해 대기**|조사가 큐에 대기 중입니다. 다른 조사가 완료되면 대기 중인 조사가 시작됩니다. 스로틀은 서비스 성능이 나쁜 것을 방지하는 데 도움이 됩니다.  <p> **팁:** 보류 중인 작업은 새 조사를 실행할 수 있는 수를 제한할 수 있습니다. 보류 중인 [작업을 승인(또는 거부)해야 합니다.](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)|
|**스로틀에 의해 종료됩니다.**|조사가 너무 오래 큐에 있는 경우 중지됩니다. <p> **팁**: 위협 [탐색기에서 조사를 시작할 수 있습니다.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>조사 세부 정보 보기

1. Microsoft 365 Defender 포털()로 <https://security.microsoft.com> 이동하여 로그인합니다.
2. 탐색 창에서 작업 센터 **를 선택합니다.**
3. 보류 중 **또는** 기록 **탭에서** 작업을 선택합니다. 플라이아웃 창이 열립니다.
4. 플라이아웃 창에서 조사 페이지 **열기 를 선택합니다.** 
5. 다양한 탭을 사용하여 조사에 대해 자세히 알아보습니다.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>조사와 관련된 경고에 대한 세부 정보 보기

특정 종류의 경고는 경고에서 자동화된 조사를 Microsoft 365. 자세한 내용은 자동화된 [조사를 트리거하는 경고 정책을 참조합니다.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Microsoft 365 Defender 포털()로 <https://security.microsoft.com> 이동하여 로그인합니다.
2. 탐색 창에서 작업 센터 **를 선택합니다.**
3. 보류 중 **또는** 기록 **탭에서** 작업을 선택합니다. 플라이아웃 창이 열립니다.
4. 플라이아웃 창에서 조사 페이지 **열기 를 선택합니다.**
5. 경고 **탭을 선택하여** 해당 조사와 연결된 모든 경고의 목록을 볼 수 있습니다.
6. 목록에서 항목을 선택하여 플라이아웃 창을 열 수 있습니다. 이 경우 경고에 대한 자세한 정보를 볼 수 있습니다.

## <a name="keep-the-following-points-in-mind"></a>다음에 유의해야 합니다.

- 전자 메일 수는 조사 시에 계산하며, 일부 횟수는 조사 플라이아웃을 열 때(기초 쿼리를 기반으로) 다시 계산됩니다.

- 전자 메일 탭의 전자 메일 클러스터에 대해 표시되는 전자 메일 수와 클러스터 플라이아웃에 표시되는 전자 메일 수량 값은 조사 시에 계산됩니다. 

- 전자 메일 클러스터 플라이아웃의 전자 메일 탭 아래쪽에 표시되는 전자 메일 수와 탐색기에 표시된 전자 메일 메시지 수에는 조사 초기 분석 후 받은 전자 메일 메시지가 반영됩니다. 

  따라서 조사 분석 단계 사이에 5개의 전자 메일 메시지가 도착할 때와 관리자가 조사를 검토할 때 원래 수량인 10개의 전자 메일 메시지를 표시하는 전자 메일 클러스터에는 총 15개의 전자 메일 목록이 표시됩니다. 마찬가지로 이전 조사는 평가판을 위해 7일 후에 그리고 유료 라이선스의 경우 30일 후에 만료되는 Office 365 Plan 2용 Microsoft Defender의 데이터가 만료되어 탐색기 쿼리보다 높은 수를 표시하기 시작할 수 있습니다.

  조사 시 전자 메일에 미치는 영향과 수정이 실행될 때까지 현재의 영향을 나타내기 위해 여러 보기에서 기록 횟수와 현재 수를 모두 표시하는 것이 수행됩니다.

- 전자 메일 컨텍스트에서 조사의 일부로 볼륨 이상 위협 표면이 표시될 수 있습니다. 볼륨 이상은 이전 기간과 비교하여 조사 이벤트 시간 주위의 비슷한 전자 메일 메시지에 대한 스파이크를 나타냅니다. 전자 메일 트래픽이 특정 특성(예: 제목 및 보낸 사람 도메인, 본문 유사성, 보낸 사람 IP)과 함께 증가하는 것이 전자 메일 캠페인 또는 공격의 시작에 일반적인 예입니다. 그러나 대량, 스팸 및 합법적인 전자 메일 캠페인은 일반적으로 이러한 특성을 공유합니다.

- 볼륨 이상은 잠재적인 위협을 나타내며, 그에 따라 바이러스 백신 엔진, 검색 또는 악의적인 신뢰도로 식별되는 맬웨어 또는 피싱 위협에 비해 심각하지 않은 것일 수 있습니다.

- 모든 작업을 승인할 것은 없습니다. 권장 작업에 동의하지 않는 경우 또는 조직에서 특정 유형의 작업을 선택하지  않는 경우 작업을 거부하거나 무시하고 작업을 수행하지 않을 수 있습니다.

- 모든 작업을 수락 및/또는 거부하면 조사가 완전히 닫히고(상태가 수정됩니다), 일부 작업이 불완전한 상태로 두면 조사 상태가 부분적으로 수정된 상태로 변경됩니다.

## <a name="next-steps"></a>다음 단계

- [보류 중인 작업 검토 및 승인](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
