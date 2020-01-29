---
title: Office 365의 자동화 된 조사 및 응답 (AIR)
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection 계획 2의 자동화 된 조사 및 응답 기능에 대 한 개요를 확인 하세요.
ms.openlocfilehash: fcb48da4b6f3777fa8c21ef514d5f591e342562e
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "41573045"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Office 365의 자동화 된 조사 및 응답 (AIR)

자동 조사 및 응답 (AIR) 기능을 사용 하면 현재 존재 하는 잘 알려진 위협에 대응 하 여 자동화 된 조사 프로세스를 실행할 수 있습니다. AIR은 보안 운영 팀이 보다 효율적이 고 효과적으로 운영 하는 데 도움이 됩니다.
- AIR의 작동 방식을 확인 하려면이 문서를 사용 하십시오.
- AIR 사용을 시작 하려면 [Office 365의 위협에 대 한 자동 조사 및 응답](office-365-air.md)을 참조 하세요.

> [!TIP]
> ID 및 위협 방지가 지원되는 Microsoft 365 E5 또는 Microsoft 365 E3가 있나요? [Microsoft 위협 방지](../mtp/microsoft-threat-protection.md)를 시도해 보세요.

## <a name="the-overall-flow-of-air"></a>전체 공기 흐름

높은 수준에서 AIR 흐름은 다음과 같은 방식으로 작동 합니다.

|단계  |관련 항목  |
|---------|---------|
|개     |Office 이벤트에 의해 [알림이](#alerts) 트리거되고 [보안 playbook](#security-playbooks) 선택한 경고에 대 한 자동 조사를 시작 합니다. <br/><br/>또한 보안 분석가는 [탐색기](threat-explorer.md)의 전자 메일에서 [자동 조사를 수동으로 시작할](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)수 있습니다.        |
|2     |자동 조사가 실행 되는 동안 전자 메일 및 해당 전자 메일에 관련 된 엔터티에 대 한 추가 데이터 (파일, Url 및 받는 사람)를 수집 합니다.  새 관련 경고가 트리거되면 조사 범위가 증가할 수 있습니다.         |
|3(sp3)     |자동화 된 조사 도중 및 후에 [세부 정보 및 결과](#investigation-graph) 를 볼 수 있습니다. 결과에는 발견 된 모든 위협을 응답 하 고 수정 하기 위해 취할 수 있는 [권장 작업이](#recommended-actions) 포함 됩니다. 또한 모든 조사 활동을 추적 하는 [playbook 로그](#playbook-log) 를 사용할 수 있습니다.<br/><br/>조직에서 사용자 지정 보고 솔루션 또는 타사 솔루션을 사용 하는 경우에는 [Office 365 관리 활동 API를 사용](office-365-air.md#use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions) 하 여 자동화 된 조사 및 위협에 대 한 정보를 볼 수 있습니다.         |
|4      |보안 운영 팀은 조사 결과 및 권장 사항을 검토 하 고 업데이트 관리 작업을 승인 합니다. Office 365에서 수정 작업은 조직의 보안 팀이 승인한 경우에만 적용될 수 있습니다.         |

다음 섹션에서는 경고, 보안 playbooks 및 조사 세부 정보를 비롯 하 여 AIR에 대 한 자세한 정보를 제공 합니다. 또한이 문서에는 AIR works의 두 가지 예제가 포함 되어 있습니다. AIR 사용을 시작 하려면 [Office 365의 위협에 대 한 자동 조사 및 응답](office-365-air.md)을 참조 하세요.

## <a name="alerts"></a>알림

[경고](../../compliance/alert-policies.md#viewing-alerts) 는 보안 운영 팀 워크플로에서 문제를 대응 하기 위한 트리거를 나타냅니다. 확인을 위해 적절 한 경고 집합에 우선 순위를 지정 하는 동시에, 주소가 지정 되지 않은 위협에 대 한 해결 방법은 어렵습니다. 경고에 대 한 조사가 수동으로 수행 되 면 보안 운영 팀은 콘텐츠, 장치 및 사용자와 같은 엔터티를 찾아서 위협 으로부터 연결 해야 합니다. 이러한 작업과 워크플로를 사용 하면 시간이 매우 오래 걸리고 여러 도구 및 시스템을 포함할 수 있습니다. 무선, 조사 및 Office 365에 대 한 응답은 주요 보안 및 위협 관리 경고로 인해 보안 응답 playbook가 자동으로 트리거되어 보안 이벤트가 자동화 됩니다. 

현재 AIR의 경우 다음 경고 정책 종류에서 생성 된 경고는 자동으로 조사 됩니다.  

- 잠재적으로 악의적인 URL 클릭이 검색 되었습니다.
- 사용자가 피싱으로 보고 한 전자 메일
- 배달 후 제거 된 맬웨어를 포함 하는 전자 메일 메시지 *
- 배달 후 제거 된 피싱 Url을 포함 하는 전자 메일 메시지 *
- 의심 스러운 전자 메일 전송 패턴 감지 #
- 사용자가 전자 메일을 보내지 못하도록 제한 됨 #

> [!NOTE]
> 별표 (*)로 표시 된 경고는 전자 메일 알림을 해제 한 상태에서 보안 & 준수 센터 내의 각 경고 정책에 *정보* 심각도를 할당 합니다. [알림 정책 구성을](../../compliance/alert-policies.md#alert-policy-settings)통해 전자 메일 알림을 설정할 수 있습니다. 해시 (#)로 표시 된 경고는 일반적으로 공개 미리 보기 playbooks에 연결 된 사용 가능한 알림입니다.

알림을 보려면 보안 & 준수 센터 **에서 경고** > **보기**를 선택 합니다. 알림을 선택 하 여 세부 정보를 확인 하 고, **보기 조사** 링크를 사용 하 여 해당 [조사](#investigation-graph)로 이동 합니다.  

> [!NOTE]
> 정보 알림은 기본적으로 경고 보기에 숨겨집니다. 이러한 항목을 보려면 알림 필터링을 변경 하 여 정보 알림 메시지를 포함 합니다.

조직에서 경고 관리 시스템, 서비스 관리 시스템 또는 SIEM (보안 정보 및 이벤트 관리) 시스템을 통해 보안 경고를 관리 하는 경우 전자 메일 알림을 통해 또는 [office 365 관리 활동 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)를 통해 해당 시스템에 office 365 알림을 보낼 수 있습니다. 전자 메일 또는 API를 통한 조사 경고 알림에는 보안 & 준수 센터의 경고에 액세스 하 여 할당 된 보안 관리자가 조사로 신속 하 게 이동할 수 있도록 하는 링크가 포함 되어 있습니다.

![조사로 연결 되는 경고](../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>보안 playbook

보안 playbook Office Advanced Threat protection 및 Microsoft Threat protection의 자동화 핵심에 있는 백 엔드 정책입니다. AIR에서 제공 되는 보안 playbook은 일반적인 실제 보안 시나리오를 기반으로 하며, 보안 운영 팀의 의견을 기반으로 개발 되었습니다. 조직 내에서 특정 알림이 트리거될 때 보안 playbook 자동으로 실행 됩니다. 알림이 트리거되 면 연결 된 playbook가 자동 조사 및 응답 (AIR) 시스템에 의해 실행 됩니다. 이 조사 단계에서는 특정 경고의 playbook에 따라 경고를 분석 하 여 연결 된 모든 메타 데이터 (전자 메일 메시지, 사용자, 제목, 보낸 사람 등)를 조사 합니다. 조사 playbook의 결과에 따라, AIR에서는 조직의 보안 팀이 위협을 제어 하 고 완화 하기 위해 취할 수 있는 일련의 작업을 권장 합니다. 

AIR에서 제공 하는 보안 playbook은 조직이 현재 전자 메일을 통해 직면 한 가장 흔한 위협에 대 한 해결 방법을 제공 합니다. Microsoft 및 고객의 자산을 보호 하는 데 도움이 되는 사용자를 비롯 하 여 보안 작업 및 사건 대응 팀의 입력을 기반으로 합니다.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>보안 playbook가 단계별로 롤아웃 됨

AIR의 일환으로 보안 playbook가 단계별로 배포 됩니다. 이제 1 단계를 일반적으로 사용할 수 있으며, 보안 관리자가 검토 하 고 승인할 수 있는 작업에 대 한 권장 사항을 제공 하는 몇 가지 playbook 포함 합니다.
- 사용자가 보고 한 피싱 메시지
- URL 결과 변경 클릭
- 맬웨어 배달 후 검색 (맬웨어 ZAP)
- 피싱 검색 된 배달 후 ZAP (피싱 ZAP)

1 단계에는 [위협 탐색기](threat-explorer.md)를 사용 하 여 관리자가 트리거한 전자 메일 조사에 대 한 지원도 포함 됩니다.

이제 2 단계에서는 **공개 미리 보기**의 다음 playbook을 사용 하 여 작업을 진행 하 고 있으며 문제 조사에 대 한 권장 사항 및 aiding 보안 관리자를 제공 합니다.
- 사용자가 손상 된 것으로 보고 됨 (공개 미리 보기)

추가 playbook 완료 되 면 릴리스됩니다. [Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap) 방문 하 여 그 밖의 계획 및 출시 예정 사항을 확인 하세요.

### <a name="playbooks-include-investigation-and-recommendations"></a>Playbooks에는 조사 및 권장 사항이 포함 되어 있습니다.

AIR에서는 각 보안 playbook 다음이 포함 됩니다. 
- 전자 메일의 엔터티 (파일, Url, 받는 사람, IP 주소 등)에 대 한 루트 조사
- 조직에서 받은 유사한 전자 메일에 대 한 추가 구하기 
- 다른 잠재적 위협을 식별 및 상호 연결 하기 위해 수행 되는 단계 
- 권장 되는 위협 재구성 작업

각 상위 단계에는 위협에 대 한 심층적이 고 자세 하며 철저 한 응답을 제공 하기 위해 실행 되는 여러 하위 단계가 포함 되어 있습니다.

## <a name="automated-investigations"></a>자동화 된 조사

자동화 된 조사 페이지에 조직의 조사 및 현재 상태가 표시 됩니다.

![AIR의 주 조사 페이지](../media/air-maininvestigationpage.png) 
  
다음을 수행할 수 있습니다.
- 조사로 직접 이동 합니다 ( **조사 ID**선택).
- 필터를 적용 합니다. **조사 유형**, **시간 범위**, **상태**또는 이들의 조합 중에서 선택 합니다.
- 데이터를 .csv 파일로 내보냅니다.

조사 상태는 분석 및 작업의 진행률을 나타냅니다. 조사가 실행 되 면 상태가 변경 되어 위협이 발견 되었는지 여부와 작업이 승인 되었는지 여부를 나타냅니다. 


|상태  |의미  |
|---------|---------|
|시작 중 | 조사가 곧 시작 되기 위해 대기 중입니다. |
|부족 | 조사가 시작 되었으며 분석을 수행 하 고 있습니다. |
|발견 된 위협 없음 | 조사가 분석을 완료 했으며 위협이 발견 되지 않음 |
|시스템 종료 | 7 일 후에 조사가 종료 되지 않고 만료 되었습니다. |
|보류 중인 작업 | 조사에서 권장 되는 작업의 위협을 발견 했습니다.  초기 위협과 권장 작업을 찾은 후에도 조사는 계속 실행 되므로 analyzer가 여전히 진행 중인지 확인 하기 위해 작업을 승인 하기 전에 로그를 확인 해야 합니다. |
|발견 된 위협 | 조사에서 위협이 발견 되었지만 해당 위협이 AIR 내에서 사용할 수 있는 작업을 포함 하 고 있지 않습니다.  아직 방향 AIR 동작이 없는 사용자 작업입니다. |
|수정 | 조사가 완료 되어 완전히 재구성 되었습니다 (모든 작업이 승인 됨). |
|부분 재구성 | 조사가 완료 되었으며 일부 권장 작업을 승인 했습니다. |
|사용자가 종료 | 관리자가 조사를 종료 했습니다. |
|Failed | 조사 중에 위협의 결론에 도달 하지 못하도록 차단 하는 동안 오류가 발생 했습니다. |
|제한에 의해 대기 | 조사에서 시스템 처리 제한 (서비스 성능 보호)으로 인해 분석을 기다리는 중입니다. |
|제한에 의해 종료 됨 | 조사 볼륨 및 시스템 처리 제한으로 인해 조사를 충분 한 시간 내에 완료할 수 없습니다. 탐색기에서 전자 메일을 선택 하 고 조사 작업을 선택 하 여 조사를 retrigger 수 있습니다. |

### <a name="investigation-graph"></a>조사 그래프

특정 조사를 열면 조사 그래프 페이지가 표시 됩니다. 이 페이지에는 전자 메일 메시지, 사용자 (및 해당 활동), 트리거된 알림의 일부로 자동 조사 되는 장치 등의 다양 한 엔터티가 모두 표시 됩니다.

![AIR 조사 그래프 페이지](../media/air-investigationgraphpage.png)

다음을 수행할 수 있습니다.
- 현재 조사에 대 한 시각적 개요를 볼 수 있습니다.
- 조사 기간에 대 한 요약을 봅니다.
- 시각화에서 노드를 선택 하 여 해당 노드의 세부 정보를 확인 합니다.
- 위쪽에서 탭을 선택 하 여 해당 탭의 세부 정보를 확인 합니다.

### <a name="alert-investigation"></a>경고 조사

조사에 대 한 **알림** 탭에서 조사와 관련 된 경고를 볼 수 있습니다. 세부 정보에는 조사를 트리거한 경고 및 확인에 상관 된 위험한 로그인, DLP 정책 위반 등의 상호 관련 된 경고가 포함 됩니다. 이 페이지에서는 보안 분석가가 개별 경고에 대 한 추가 세부 정보를 볼 수도 있습니다.

![AIR 알림 페이지](../media/air-investigationalertspage.png)

다음을 수행할 수 있습니다.
- 현재 트리거하는 경고 및 관련 경고에 대 한 시각적 개요를 볼 수 있습니다.
- 목록에서 알림을 선택 하 여 전체 알림 세부 정보를 표시 하는 플라이 아웃 페이지를 엽니다.

### <a name="email-investigation"></a>전자 메일 조사

조사를 위해 **전자 메일** 탭에서 원본 전자 메일과 조사 과정에서 확인 된 유사 전자 메일의 클러스터를 볼 수 있습니다. 

조직의 사용자가 주고 받으며 전자 메일 통신 및 공격의 다중 사용자 특성을 포함 하는 전자 메일 양이 제공 되는 경우 
- 메시지 헤더, 본문, URL 및 첨부 파일의 유사 특성에 따라 전자 메일 메시지를 클러스터링 합니다. 
- 악성 전자 메일과 좋은 전자 메일을 구분 합니다. 한 
- 악성 전자 메일 메시지에 대 한 작업 수행 

시간이 오래 걸릴 수 있습니다. 이제 AIR에서이 프로세스를 자동화 하 여 조직의 보안 팀 시간과 노력을 절약 합니다. 

전자 메일 분석 단계에서 두 가지 유형의 전자 메일 클러스터, 즉 유사성 클러스터와 지표 클러스터를 확인할 수 있습니다. 
- 유사성 클러스터는 유사한 보낸 사람 및 콘텐츠 특성을 가진 전자 메일에 대해 사냥으로 식별 됩니다. 이러한 클러스터는 원래 검색 결과를 기반으로 악의적인 콘텐츠를 평가 합니다. 악의적인 전자 메일 검색이 충분히 포함 된 전자 메일 클러스터가 악성으로 간주 됩니다.
- 지표 클러스터는 원본 전자 메일에서 동일한 지표 엔티티 (파일 해시 또는 URL)에 대해 사냥으로 식별 되는 전자 메일 메시지입니다. 원본 파일/URL 엔터티가 악성으로 식별 되 면이 엔터티가 포함 된 전자 메일 메시지의 전체 클러스터에 결과 표시기가 적용 됩니다. 맬웨어로 식별 된 파일은 해당 파일을 포함 하는 전자 메일 메시지의 클러스터가 맬웨어 전자 메일 메시지로 취급 됨을 의미 합니다.

클러스터링의 목표는 공격이 나 캠페인의 일부로 동일한 보낸 사람이 보낸 다른 관련 전자 메일 메시지를 찾아서 찾는 것입니다.  경우에 따라 합법적인 전자 메일이 조사를 트리거할 수 있습니다 (예: 사용자가 마케팅 전자 메일을 보고 함).  이 시나리오에서 전자 메일 클러스터링은 전자 메일 클러스터가 악성이 아닌 것을 식별 하며 적절 하 게 수행 되 면 위협을 나타내거나 전자 메일을 제거할 것을 권장 **하지** 않습니다.

**전자 메일** 탭에는 사용자가 보고 한 전자 메일 세부 정보, 보고 된 원래 전자 메일, 맬웨어/피싱로 인 한 전자 메일 메시지 등 조사와 관련 된 전자 메일 항목도 표시 됩니다 zapped.

전자 메일 탭에 식별 된 전자 메일 개수는 현재 **전자 메일** 탭에 표시 되는 모든 전자 메일 메시지의 총 합계를 나타냅니다. 전자 메일 메시지는 여러 클러스터에 존재 하기 때문에, 확인 되 고 수정 작업의 영향을 받는 전자 메일 메시지의 실제 총 수는 모든 클러스터 및 원래 받는 사람의 전자 메일 메시지에 있는 고유한 전자 메일 메시지의 수입니다. 

보안 verdicts, 작업 및 배달 위치는 받는 사람 기준 마다 다르므로, 각 받는 사람에 대 한 전자 메일 메시지의 수에는 두 가지가 있습니다. 따라서 세 명의 사용자에 게 전송 되는 원래 전자 메일은 전자 메일 하나가 아닌 총 3 개의 전자 메일 메시지 수로 계산 됩니다. 참고 전자 메일이 여러 작업을 수행할 수 있고 모든 작업이 수행 되 면 전자 메일의 복사본이 여러 개 있을 수도 있으므로 전자 메일이 두 번 이상 계산 되는 경우가 있을 수 있습니다. 예를 들어 배달 시 감지 되는 맬웨어 전자 메일은 차단 된 (격리 된) 전자 메일과 바뀐 전자 메일 (위협 파일을 경고 파일로 교체 하 고 사용자의 사서함으로 전달)이 모두 발생할 수 있습니다. 시스템에 전자 메일의 복사본이 두 개 있으므로 둘 다 클러스터 수로 계산 될 수 있습니다. 

전자 메일 개수는 조사 시 계산 되며, 기본 쿼리를 기반으로 하 여 조사 flyouts를 열 때 몇 가지 개수가 다시 계산 됩니다. 전자 메일 탭의 전자 메일 클러스터에 대해 표시 되는 전자 메일 수와 클러스터 플라이 아웃에 표시 되는 전자 메일 수량 값은 조사 시 계산 되며 변경 되지 않습니다. 전자 메일 클러스터 플라이 아웃의 전자 메일 탭 아래쪽에 표시 되는 전자 메일 수와 탐색기에 표시 되는 전자 메일 메시지의 수에는 조사 초기 분석 후에 받은 전자 메일 메시지가 반영 됩니다. 따라서 조사 분석 단계와 관리자가 조사를 검토할 때 전자 메일 메시지가 5 개 더 도착 하면 전자 메일 목록 총 15가 표시 됩니다.  ATP P2는 평가판을 위해 7 일 후에, 유료 라이선스에 대해 30 일 후에도 이전 조사에서 표시 되는 것 보다 더 큰 수를 통해 탐색기 쿼리가 보다 많이 나오는 것으로 시작  두 가지 보기의 개수 내역 및 현재 횟수를 모두 보여 주는 것은 조사 당시에 전자 메일 영향을 나타내고 수정이 실행 될 때까지 현재 영향을 나타내도록 하기 위해 수행 됩니다.

예를 들어 다음과 같은 시나리오를 가정해 봅니다. 세 개의 전자 메일 메시지 중 첫 번째 클러스터는 피싱 것으로 간주 됩니다. 이러한 항목 중 일부는 초기 검색을 수행 하는 동안 피싱으로 식별 되었기 때문에 같은 IP 및 주체를 포함 하는 비슷한 메시지의 다른 클러스터가 발견 되어 악성으로 간주 되었습니다. 

![AIR 전자 메일 조사 페이지](../media/air-investigationemailpage.png)

다음을 수행할 수 있습니다.
- 현재 클러스터링 결과 및 발견 된 위협에 대 한 시각적 개요를 볼 수 있습니다.
- 클러스터 엔터티 또는 위협 목록을 클릭 하 여 전체 알림 세부 정보를 표시 하는 플라이 아웃 페이지를 엽니다.
- ' 전자 메일 클러스터 세부 정보 ' 탭 맨 위에 있는 ' 탐색기에서 열기 ' 링크를 클릭 하 여 전자 메일 클러스터를 자세히 조사 합니다.

![플라이 아웃 세부 정보를 사용한 AIR 조사 전자 메일](../media/air-investigationemailpageflyoutdetails.png)

> [!NOTE]
> 전자 메일 컨텍스트에서 조사를 진행 하는 동안 볼륨 변칙 위협 표면을 볼 수 있습니다. 볼륨 변칙은 이전 기간에 비해 조사 이벤트에 대 한 유사한 전자 메일 메시지의 스파이크를 나타냅니다. 전자 메일 트래픽 (예: 제목 및 보낸 사람 도메인, 본문 유사성 및 보낸 사람 IP)이 비슷한 방식으로 전자 메일을 사용 하는 것이 일반적입니다. 그러나 일반적으로 대량, 스팸 및 합법적인 전자 메일 캠페인은 이러한 특성을 공유 합니다. 볼륨 예외는 잠재적 위협을 나타내므로, 바이러스 백신 엔진, 샌드 박싱 또는 악의적인 평판을 사용 하 여 식별 된 맬웨어 또는 피싱 위협과 비교 하는 것이 더 심각 하지 않습니다.

### <a name="user-investigation"></a>사용자 조사

**사용자** 탭에서는 조사의 일부로 식별 된 모든 사용자를 볼 수 있습니다. 사용자 계정은 이벤트가 발생 하거나 해당 사용자 계정에 영향을 줄 수도 있고 해당 계정이 손상 되었을 수 있음을 나타내는 경우 조사에 표시 됩니다.

예를 들어 다음 이미지에서 AIR은 생성 된 새 받은 편지함 규칙을 기반으로 하는 손상 및 예외 표시등을 식별 했습니다. 조사에 대 한 자세한 내용은이 탭 내의 자세한 보기를 통해 확인할 수 있습니다. 손상 및 변칙에 대 한 표시기에는 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)의 변칙 검색이 포함 될 수도 있습니다.

![AIR 조사 사용자 페이지](../media/air-investigationuserspage.png)

다음을 수행할 수 있습니다.
- 발견 된 사용자 결과 및 위험에 대 한 시각적 개요를 확인 하세요.
- 전체 알림 세부 정보를 표시 하는 플라이 아웃 페이지를 열 사용자를 선택 합니다.

### <a name="machine-investigation"></a>컴퓨터 조사

**컴퓨터** 탭에서 조사 과정으로 식별 된 모든 컴퓨터를 볼 수 있습니다. 

![AIR 조사 컴퓨터 페이지](../media/air-investigationmachinepage.png)

일부 playbooks 일부로, AIR에서는 전자 메일 위협을 장치 (예: Zapped 맬웨어)와 연관 시킵니다. 예를 들어 조사를 통해 조사를 위해 [Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) 에 게 악성 파일 해시를 전달 합니다. 이렇게 하면 사용자에 대 한 관련 시스템을 자동으로 조사 하 여 위협이 클라우드 및 끝점에서 모두 해결 되도록 할 수 있습니다. 

다음을 수행할 수 있습니다.
- 발견 된 현재 컴퓨터 및 위협에 대 한 시각적 개요를 볼 수 있습니다.
- 컴퓨터를 선택 하 여 Microsoft Defender 보안 센터에서 관련 [Microsoft DEFENDER ATP 조사](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 로 연결 되는 보기를 엽니다.

### <a name="entity-investigation"></a>엔터티 조사

조사 과정의 일부로 확인 및 분석 된 엔터티가 **엔터티** 탭에서 볼 수 있습니다. 

여기서는 전자 메일 메시지, 클러스터, IP 주소, 사용자 등의 엔터티 유형에 대 한 조사 된 엔터티 및 세부 정보를 볼 수 있습니다. 또한 분석 된 엔터티 수와 각 엔터티가 연결 된 위협을 볼 수 있습니다. 

![AIR 조사 엔터티 페이지](../media/air-investigationentitiespage.png)

다음을 수행할 수 있습니다.
- 발견 된 조사 엔터티 및 위협에 대 한 시각적 개요를 확인 하세요.
- 엔터티를 선택 하 여 관련 엔터티 세부 정보를 표시 하는 플라이 아웃 페이지를 엽니다.

![AIR 조사 엔터티 세부 정보](../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Playbook 로그

**로그** 탭에서는 조사 중에 발생 한 모든 playbook 단계를 볼 수 있습니다. 이 로그는 AIR의 일부로 서 Office 365 자동 조사 기능을 통해 완료 된 모든 분석기 및 작업의 전체 인벤토리를 캡처합니다. 작업 자체, 설명, 실제 시작 날짜를 포함 하 여 수행 된 모든 단계를 명확 하 게 확인할 수 있습니다. 

![AIR 조사 로그 페이지](../media/air-investigationlogpage.png)

다음을 수행할 수 있습니다.
- Playbook 수행 된 단계에 대 한 시각적 개요를 참조 하세요.
- 결과를 CSV 파일로 내보냅니다.
- 보기를 필터링 합니다.

|시키기 | 설명 |
|-----|-----|
|DLP 위반 조사 |[Office 365 DLP (데이터 손실 방지](../../compliance/data-loss-prevention-policies.md) )에서 검색 되는 모든 위반 조사 |
|전자 메일 지표 추출 |조사를 위해 전자 메일 메시지의 머리글, 본문 및 내용에서 표시기 추출 |
|파일 해시 신뢰도 |조직의 사용자 및 컴퓨터에 대 한 파일 해시를 기반으로 예외 검색 |
|메일 클러스터 식별 |헤더, 본문, 콘텐츠 및 Url을 기반으로 하는 전자 메일 분석 |
|메일 클러스터 볼륨 분석 |아웃 바운드 메일 흐름 볼륨 패턴을 기반으로 하는 전자 메일 클러스터 분석 |
|메일 위임 조사 |이 조사와 관련 된 사용자 사서함에 대 한 메일 위임 액세스를 조사 합니다. |
|메일 전달 규칙 조사 |이 조사와 관련 된 사용자 사서함에 대 한 메일 전달 규칙을 조사 합니다. |
|누락 된 맬웨어 감지 |조직에서 사용자의 사서함으로 배달 된 누락 된 맬웨어 검색 |
|주문형 샌드 박싱 |전자 메일 메시지, 첨부 파일 및 Url에 대 한 주문형 샌드 박싱 트리거됨 |
|아웃 바운드 메일 변칙 조사 |조직의 사용자에 대 한 기록 메일 흐름 전송 패턴을 기반으로 예외 검색 |
|아웃 바운드 맬웨어 및 스팸 변칙 조사 |조직 내 사용자 로부터 보낸 조직 내 및 아웃 바운드 맬웨어, 피싱 또는 스팸 감지 |
|보낸 사람 도메인 조사 |[Microsoft 지능형 보안 그래프](https://www.microsoft.com/security/operations/intelligence) 및 외부 위협 인텔리전스 원본의 도메인 신뢰도에 대 한 주문형 확인 |
|보낸 사람 IP 조사 | [Microsoft 지능형 보안 그래프](https://www.microsoft.com/security/operations/intelligence) 및 외부 위협 인텔리전스 원본의 IP 신뢰도에 대 한 주문형 확인 |
|URL 클릭 조사 | 조직의 [Office 365 ATP 안전한 링크](atp-safe-links.md) 를 클릭 하 여 사용자에 게 보호 |
|URL 신뢰도 조사 |[Microsoft 지능형 보안 그래프](https://www.microsoft.com/security/operations/intelligence) 및 외부 위협 인텔리전스 원본의 URL 신뢰도에 대 한 주문형 확인 |
|사용자 활동 조사 |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 에서 사용자 활동 예외 분석 |
|사용자가 보고 한 전자 메일 지표 추출 |조사를 위해 사용자에 게 [보고 된 전자 메일](enable-the-report-message-add-in.md) 의 머리글, 본문 및 콘텐츠에서 지표 추출 |


### <a name="recommended-actions"></a>권장 작업

조사가 완료 된 후에 수정이 권장 되는 모든 playbook 작업을 **작업** 탭에서 확인할 수 있습니다. 

작업은 조사 종료 시에 Microsoft에서 권장 하는 단계를 캡처합니다. 하나 이상의 작업을 선택 하 여 여기에서 수정 작업을 수행할 수 있습니다. **승인을** 클릭 하면 재구성을 시작할 수 있습니다. (적절 한 사용 권한이 필요 함-탐색기 및 AIR에서 작업을 실행 하려면 ' 검색 및 제거 ' 역할이 필요 합니다. 예를 들어 보안 독자는 작업을 볼 수 있지만 승인 하지는 않습니다. 참고: 모든 작업을 승인할 필요는 없습니다. 권장 작업에 동의 하지 않거나 조직에서 특정 유형의 작업을 선택 하지 않는 경우에는 작업을 **거부** 하거나 무시 하 고 작업을 수행 하지 않도록 선택할 수 있습니다. 모든 작업을 승인 및/또는 거부 하면 조사 완전히 닫기 (상태가 재구성 됨)를 제외 하 고, 일부 작업을 완료 하지 않고 조사 상태가 부분 재구성 됨 상태로 변경 됩니다.

![AIR 조사 작업 페이지](../media/air-investigationactionspage.png)

다음을 수행할 수 있습니다.
- Playbook 권장 작업에 대 한 시각적 개요를 볼 수 있습니다.
- 단일 작업 또는 여러 작업을 선택 합니다.
- 설명으로 권장 작업을 승인 하거나 거부 합니다.
- 결과를 CSV 파일로 내보냅니다.
- 보기를 필터링 합니다.

## <a name="remediation-actions"></a>수정 작업

자동 조사가 실행 중이거나 완료 되 면 일반적으로 하나 이상의 수정 작업을 표시 합니다. 다음 표에는 Office 365 AIR의 가능한 수정 작업에 대 한 목록이 나와 있습니다.

|동작은 | 설명 |
|-----|-----|
|차단 URL(클릭 시간) |악성 Url이 포함 된 전자 메일 및 문서에 대해 보호 합니다. 이렇게 하면 사용자가 기존 Office 파일 또는 이전 전자 메일 메시지의 링크를 클릭할 때 [안전한 링크](atp-safe-links.md) 를 통해 악성 링크 및 관련 웹 페이지를 차단 하는 데 사용할 수 있습니다. |
|전자 메일 일시 삭제  |사용자 사서함에서 특정 전자 메일 메시지 일시 삭제|
|전자 메일 클러스터 일시 삭제  |모든 사용자의 사서함에서 쿼리와 일치 하는 악성 전자 메일 메시지를 소프트 삭제|
|외부 메일 전달 해제 |특정 최종 사용자의 사서함에서 전달 규칙을 제거 합니다.|

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>예: 사용자가 보고 한 피싱 메시지가 조사 playbook를 시작 합니다.

조직의 사용자가 전자 메일 메시지를 전송 하 고 [outlook 또는 Outlook Web App 용 보고서 메시지 추가 기능](enable-the-report-message-add-in.md)을 사용 하 여 Microsoft에 보고 하는 경우 보고서도 시스템에 전송 되며 사용자가 보고 한 보기의 탐색기에 표시 됩니다. 이 사용자가 보고 한이 메시지는 이제 조사 playbook를 자동으로 시작 하는 시스템 기반 정보 알림을 트리거합니다.

루트 조사 단계에서는 전자 메일의 다양 한 측면을 평가 합니다. 여기에는 다음이 포함됩니다.
- 사용할 수 있는 위협의 유형에 대 한 결정
- 보낸 사람
- 전자 메일이 전송 되는 위치 (보내는 인프라)
- 전자 메일의 다른 인스턴스가 배달 되거나 차단 되었는지 여부
- 분석가의 평가
- 전자 메일이 알려진 캠페인과 연결 되어 있는지 여부
- 등이 있습니다.

루트 조사가 완료 되 면 playbook는 원래 전자 메일 및 해당 항목과 연결 된 엔터티에 대해 수행할 권장 작업 목록을 제공 합니다.
  
다음으로 몇 가지 위협 조사 및 사냥 단계가 실행 됩니다.

- 전자 메일 클러스터 검색을 통해 유사한 전자 메일 메시지가 식별 됩니다.
- 신호가 [Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)와 같은 다른 플랫폼과 공유 됩니다.
- 의심 스러운 전자 메일 메시지에서 모든 사용자가 악의적인 링크를 클릭 했는지 여부가 결정 됩니다.
- 확인은 Office 365 Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) 및 Office 365 Advanced Threat Protection ([ATP](office-365-atp.md))을 통해 사용자가 보고 하는 다른 유사한 메시지가 있는지를 확인 합니다.
- 사용자가 손상 되었는지 확인 하는 검사를 수행 합니다. 이 검사는 Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)및 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)간의 신호를 활용 하 여 관련 된 사용자 활동에 대 한 예외를 모두 연관 시킵니다. 

사냥 단계에서는 위험과 위협이 다양 한 구하기 단계에 할당 됩니다. 

재구성은 playbook의 마지막 단계입니다. 이 단계에서는 조사 및 구하기 단계를 기반으로 재구성 단계가 수행 됩니다. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>예: 보안 관리자가 위협 탐색기에서 조사를 트리거합니다.

알림을 통해 트리거되는 자동 조사 외에 조직의 보안 운영 팀은 [위협 탐색기](threat-explorer.md)의 보기에서 자동 조사를 트리거할 수 있습니다.

예를 들어 Explorer에서 사용자가 보고 한 메시지에 대 한 데이터를 보고 있다고 가정 합니다. 결과 목록에서 항목을 선택 하 고 작업 메뉴에서 **조사** 를 클릭할 수 있습니다 (적절 한 수정 권한이 있는 경우).

![검사 단추를 사용 하 여 탐색기에서 사용자가 보고 한 메시지](../media/Explorer-UserReported-Investigate.png)

또 다른 예로, 맬웨어를 포함 하는 것으로 검색 된 전자 메일 메시지에 대 한 데이터를 보고 있는 경우 맬웨어가 있는 전자 메일 메시지를 여러 개 검색 한다고 가정해 보겠습니다. **전자 메일** 탭을 선택 하 고 전자 메일 메시지를 하나 이상 선택 하 고 **작업** 메뉴에서 **조사**를 선택 합니다. 

![탐색기에서 맬웨어 조사 시작](../media/Explorer-Malware-Email-ActionsInvestigate.png)

경고로 트리거되는 playbook와 마찬가지로, 탐색기의 보기에서 트리거되는 자동 조사에는 루트 조사, 위협의 식별 및 상관 지정, 위협 완화를 위한 권장 작업 등이 포함 됩니다.

## <a name="how-to-get-air"></a>공기를 얻는 방법

Office 365 AIR은 다음의 구독에 포함되어 있습니다.

- Microsoft 365 E5
- Office 365 E5
- Microsoft 위협 방지
- Office 365 Advanced Threat Protection Plan 2

이러한 구독을 사용 하지 않는 경우 [무료 평가판을 시작](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US)합니다.

기능 가용성에 대 한 자세한 내용은 [ATP (Advanced Threat Protection) 계획에서 사용 가능한 기능](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)을 참조 하세요.

## <a name="required-permissions-to-use-air-capabilities"></a>AIR 기능을 사용 하는 데 필요한 사용 권한

사용 권한은 다음 표에 설명 된 것과 같은 특정 역할을 통해 부여 됩니다. 

|작업 |필요한 역할 |
|--|--|
|AIR 기능을 설정 하려면 |다음 역할 중 하나입니다. <br/>- **전역 관리자**<br/>- **보안 관리자** <br/>이러한 역할은 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [Office 365 보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에서 할당 될 수 있습니다. |
|권장 작업을 승인 하거나 거부 하려면|[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [Office 365 보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center))에서 할당 된 다음 역할 중 하나입니다.<br/>- **전역 관리자** <br/>- **보안 관리자**<br/>- **보안 독자** <br/>--- 및 ---<br/>- **검색 및 제거** (이 역할은 [Office 365 보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에만 할당 됩니다. 여기에 새 역할 그룹을 만들고 새 역할 그룹에 검색 및 제거 역할을 추가 해야 할 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [AIR 사용을 시작 하려면 Office 365](office-365-air.md)
- [Microsoft Defender ATP의 AIR에 대해 자세히 알아보기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 
- [Microsoft 365 로드맵를 방문 하 여 곧 제공 되는 항목을 확인 하 고 롤아웃](https://www.microsoft.com/microsoft-365/roadmap?filters=)

## <a name="see-also"></a>참고 항목

- [Microsoft 위협 방지](../mtp/microsoft-threat-protection.md)
- [Microsoft Threat Protection의 자동 조사 및 개선 (AIR)](../mtp/mtp-autoir.md)
