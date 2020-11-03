---
title: 자동화 된 조사 및 응답 (AIR) 개요
f1.keywords:
- NOCSH
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 자동 인시던트 대응, 조사, 재구성, 위협 방지
ms.date: 09/29/2020
description: Microsoft Defender for Office 365의 자동화 된 조사 및 응답 기능에 대 한 개요를 확인 하세요.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 316e2e30e5865e068f20d151cd0b081a96ee853f
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845975"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 자동 조사 및 응답 (AIR)에 대 한 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


보안 알림이 트리거되면 해당 경고를 확인 하 고 조직을 보호 하기 위한 단계를 수행 하는 보안 운영 팀이 진행 됩니다. 경우에 따라 보안 운영 팀에서 트리거된 경고 량이 지나치게 느껴질 수 있습니다. Microsoft Defender for Office 365의 자동 조사 및 응답 (AIR) 기능은 도움이 될 수 있습니다. 

AIR을 사용 하면 보안 운영 팀이 보다 효율적이 고 효율적으로 작업할 수 있습니다. AIR 기능에는 현재 존재 하는 잘 알려진 위협에 대응 하 여 자동화 된 조사 프로세스가 포함 되어 있습니다. 적절 한 교정 작업을 통해 승인을 받고, 보안 운영 팀이 검색 된 위협에 대처할 수 있도록 합니다. 

이 문서에서는 AIR의 개요를 제공 합니다. AIR 사용을 시작할 준비가 되 면 [자동으로 위협에 대 한 조사 및 응답](office-365-air.md)을 참조 하세요.

## <a name="at-a-high-level"></a>높은 수준

알림이 트리거되면 보안 playbook가 적용 됩니다. 상황에 따라 [자동화 된 조사 프로세스](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) 를 시작할 수 있습니다. 자동화 된 조사 중 및 후에는 [업데이트 관리 작업](air-remediation-actions.md) 을 수행 하는 것이 좋습니다. Office 365 용 Microsoft Defender에는 자동으로 작업이 수행 되지 않습니다. 보안 운영 팀에서 검토 한 다음 [각 수정 작업을 승인 하거나 거부](air-review-approve-pending-completed-actions.md)합니다. 조사 후 모든 작업이 승인 되거나 거부 되 면 조사가 완료 됩니다. 이러한 모든 활동은 Microsoft 365 보안 센터 ()에서 추적 되 고 볼 수 있습니다 [https://security.microsoft.com](https://security.microsoft.com) . 자세한 내용은 [조사의 세부 정보 보기](air-view-investigation-results.md#view-details-of-an-investigation)를 참조 하십시오.

다음 섹션에서는 경고, 보안 playbooks 및 작업 중인 AIR의 예에 대 한 자세한 정보를 제공 합니다.

## <a name="alerts"></a>경고

[경고](../../compliance/alert-policies.md#viewing-alerts) 는 보안 운영 팀 워크플로에서 문제를 대응 하기 위한 트리거를 나타냅니다. 확인을 위해 적절 한 경고 집합에 우선 순위를 지정 하는 동시에, 주소가 지정 되지 않은 위협에 대 한 해결 방법은 어렵습니다. 경고에 대 한 조사가 수동으로 수행 되 면 보안 운영 팀은 콘텐츠, 장치 및 사용자와 같은 엔터티를 찾아서 위협 으로부터 연결 해야 합니다. 이러한 작업과 워크플로를 사용 하면 시간이 매우 오래 걸리고 여러 도구 및 시스템을 포함할 수 있습니다. 공기, 조사 및 보안 이벤트에 대 한 응답은 중요 보안 및 위협 관리 알림을 통해 보안 응답 playbook가 자동으로 트리거되도록 하 여 자동화 됩니다. 

현재 AIR의 경우 다음 경고 정책 종류에서 생성 된 경고는 자동으로 조사 됩니다.  

- 잠재적으로 악의적인 URL 클릭이 검색 되었습니다.
- 사용자가 피싱으로 보고 한 전자 메일`*`
- 배달 후 제거 된 맬웨어를 포함 하는 전자 메일 메시지`*`
- 배달 후 제거 된 피싱 Url을 포함 하는 전자 메일 메시지`*`
- 의심 스러운 전자 메일 전송 패턴 감지
- 사용자가 전자 메일을 보내지 못하도록 제한 됨
- 관리자가 전자 메일의 수동 조사를 시작 합니다.`*`

> [!NOTE]
> 별표 ()로 표시 된 경고에는 `*` Microsoft 365 보안 센터 내의 각 경고 정책에 *정보* 심각도가 할당 되며 전자 메일 알림이 해제 됩니다. [알림 정책 구성을](../../compliance/alert-policies.md#alert-policy-settings)통해 전자 메일 알림을 설정할 수 있습니다. 

알림을 보려면 보안 & 준수 센터 **에서 경고**  >  **보기** 를 선택 합니다. 알림을 선택 하 여 세부 정보를 확인 하 고, **보기 조사** 링크를 사용 하 여 해당 [조사](air-view-investigation-results.md#investigation-graph)로 이동 합니다.  

> [!NOTE]
> 정보 알림은 기본적으로 경고 보기에 숨겨집니다. 이러한 항목을 보려면 알림 필터링을 변경 하 여 정보 알림 메시지를 포함 합니다.

조직에서 경고 관리 시스템, 서비스 관리 시스템 또는 SIEM (보안 정보 및 이벤트 관리) 시스템을 통해 보안 경고를 관리 하는 경우 전자 메일 알림을 통해 또는 [Office 365 관리 활동 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)를 통해 해당 시스템에 알림을 보낼 수 있습니다. 전자 메일 또는 API를 통한 조사 경고 알림에는 Microsoft 365 보안 센터의 경고에 액세스 하 여 할당 된 보안 관리자가 조사로 신속 하 게 이동할 수 있도록 하는 링크가 포함 되어 있습니다.

![조사로 연결 되는 경고](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>보안 playbook

Security playbook는 microsoft Defender for Office 365 및 Microsoft 365 Defender의 자동화 중심에 있는 백 엔드 정책입니다. AIR에서 제공 되는 보안 playbook은 일반적인 실제 보안 시나리오를 기반으로 하며, 보안 운영 팀의 의견을 기반으로 개발 되었습니다. 조직 내에서 특정 알림이 트리거될 때 보안 playbook 자동으로 실행 됩니다. 알림이 트리거되 면 연결 된 playbook 자동 조사 및 응답 시스템에 의해 실행 됩니다. 이 조사 단계에서는 특정 경고의 playbook에 따라 경고를 분석 하 여 연결 된 모든 메타 데이터 (전자 메일 메시지, 사용자, 제목, 보낸 사람 등)를 조사 합니다. 조사 playbook의 결과에 따라, AIR에서는 조직의 보안 팀이 위협을 제어 하 고 완화 하기 위해 취할 수 있는 일련의 작업을 권장 합니다. 

AIR에서 제공 하는 보안 playbook은 조직이 현재 전자 메일을 통해 직면 한 가장 흔한 위협에 대 한 해결 방법을 제공 합니다. Microsoft 및 고객의 자산을 보호 하는 데 도움이 되는 사용자를 비롯 하 여 보안 작업 및 사건 대응 팀의 입력을 기반으로 합니다.

- 사용자가 보고 한 피싱 메시지
- URL-결과 change 클릭
- 맬웨어 배달 후 검색 (맬웨어 ZAP)
- 피싱 검색 된 배달 후 ZAP (피싱 ZAP)
- 사용자가 손상 된 것으로 보고 됨 
- 수동 전자 메일 조사 (Explorer 맬웨어, 피싱 또는 모든 전자 메일 보기에서 관리자가 트리거됨)

더 많은 playbook 및 playbook 업데이트가 완료 되 면 릴리스됩니다. [Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap) 방문 하 여 그 밖의 계획 및 출시 예정 사항을 확인 하세요.

### <a name="playbooks-include-investigation-and-recommendations"></a>Playbooks에는 조사 및 권장 사항이 포함 되어 있습니다.

AIR에서는 각 보안 playbook 다음이 포함 됩니다. 

- 전자 메일 엔터티의 루트 조사 (예: 파일, Url, 받는 사람, IP 주소 등)
- 조직에서 받은 유사한 전자 메일에 대 한 추가 구하기 
- 다른 잠재적 위협을 식별 및 상호 연결 하기 위해 수행 되는 단계 
- 권장 되는 위협 재구성 작업

각 상위 단계에는 위협에 대 한 심층적이 고 자세 하며 철저 한 응답을 제공 하기 위해 실행 되는 여러 하위 단계가 포함 되어 있습니다.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>예: 사용자가 보고 한 피싱 메시지가 조사 playbook를 시작 합니다.

조직의 사용자가 피싱 시도 라고 생각 하는 전자 메일을 받는 경우를 가정해 보겠습니다. 이러한 메시지를 보고 하도록 훈련 된 사용자는 [보고서 메시지 추가 기능](enable-the-report-message-add-in.md) 을 사용 하 여 분석을 위해 Microsoft에 보냅니다. 전송도 시스템에 전송 되 고 **제출 보기의** 탐색기 (이전에는 **사용자가 보고** 한 보기 라고 함)에 표시 됩니다. 또한 사용자가 보고 한 메시지는 이제 조사 playbook를 자동으로 실행 하는 시스템 기반 정보 알림을 트리거합니다.

루트 조사 단계에서는 전자 메일의 다양 한 측면을 평가 합니다. 이러한 요소는 다음과 같습니다.

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
- 신호가 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)와 같은 다른 플랫폼과 공유 됩니다.
- 의심 스러운 전자 메일 메시지에서 모든 사용자가 악의적인 링크를 클릭 했는지 여부가 결정 됩니다.
- [EOP](exchange-online-protection-overview.md)(Exchange Online Protection) 및 ([Microsoft Defender for Office 365](office-365-atp.md))에서 확인을 수행 하 여 사용자가 보고 하는 다른 유사한 메시지가 있는지 확인 합니다.
- 사용자가 손상 되었는지 확인 하는 검사를 수행 합니다. 이 검사는 Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)및 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)간의 신호를 활용 하 여 관련 된 사용자 활동에 대 한 예외를 모두 연관 시킵니다.

사냥 단계에서는 위험과 위협이 다양 한 구하기 단계에 할당 됩니다. 

재구성은 playbook의 마지막 단계입니다. 이 단계에서는 조사 및 구하기 단계를 기반으로 재구성 단계가 수행 됩니다. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>예: 보안 관리자가 위협 탐색기에서 조사를 트리거합니다.

알림을 통해 트리거되는 자동화 된 조사 외에 조직의 보안 운영 팀은 [위협 탐색기](threat-explorer.md)의 보기에서 자동화 된 조사를 트리거할 수 있습니다.  또한이 조사에서는 Microsoft Defender 인시던트 및 외부 SIEM 도구에서이 조사가 트리거된 것을 볼 수 있도록 경고가 생성 됩니다. 

예를 들어 Explorer에서 **맬웨어** 보기를 사용 하는 경우를 가정해 보겠습니다. 차트 아래 탭을 사용 하 여 **전자 메일** 탭을 선택 합니다. 목록에서 항목을 하나 이상 선택 하면 **+ Actions** 단추가 활성화 됩니다. 

![선택한 메시지가 있는 탐색기](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

**동작** 메뉴를 사용 하 여 **트리거 조사** 를 선택할 수 있습니다.

![선택한 메시지에 대 한 동작 메뉴](../../media/explorer-malwareview-selectedemails-actions.jpg)

경고로 트리거되는 playbook와 마찬가지로, 탐색기의 보기에서 트리거되는 자동 조사에는 루트 조사, 위협의 식별 및 상관 지정, 위협 완화를 위한 권장 작업 등이 포함 됩니다.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>예: Office 365 관리 활동 API를 사용 하 여 보안 운영 팀에서 AIR을 해당 SIEM에 통합

Microsoft Defender for Office 365의 AIR 기능에는 보안 작업 팀이 위협을 모니터링 하 고 해결 하는 데 사용할 수 있는 [자세한 정보 & 보고서](air-view-investigation-results.md) 가 포함 되어 있습니다. 그러나 AIR 기능을 다른 솔루션과 통합할 수도 있습니다. 예를 들면 SIEM (보안 정보 및 이벤트 관리) 시스템, 사례 관리 시스템 또는 사용자 지정 보고 솔루션 등이 있습니다. 이러한 종류의 통합은 [Office 365 관리 활동 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)를 사용 하 여 수행할 수 있습니다. 

예를 들어 조직에서는 보안 운영 팀이 AIR에서 이미 처리 된 피싱 경고를 볼 수 있는 방법을 설정 했습니다. 솔루션은 관련 경고를 조직의 SIEM 서버와 해당 사례 관리 시스템과 통합 합니다. 이 솔루션은 보안 운영 팀이 실제 위협에 집중 하 고 시간과 노력을 집중할 수 있도록 가양성의 수를 크게 줄여줍니다. 이 사용자 지정 솔루션에 대 한 자세한 내용은 [Tech 커뮤니티 블로그: 365 Office 365 용 Microsoft Defender 및 O365 관리 API를 사용 하 여 SOC의 효율성 향상](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)을 참조 하세요.

## <a name="next-steps"></a>다음 단계

- [AIR 사용 시작](office-365-air.md)

- [Microsoft 365 로드맵를 방문 하 여 곧 계획 되 고 출시 되는 사항을 확인 하세요.](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Microsoft 365 Defender의 추가 자동화 된 조사 및 응답 기능에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
