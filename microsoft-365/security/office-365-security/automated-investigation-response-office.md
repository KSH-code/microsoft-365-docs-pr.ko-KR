---
title: 자동화된 조사 및 대응 (AIR) 개요
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
ms.collection: M365-security-compliance
ms.date: 08/21/2020
description: Office 365 Advanced Threat Protection Plan 2의 자동화된 조사 및 대응 기능에 대한 개요를 확인하세요.
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: 27a2330d5f1ff339aabf6a0fccb94a15dec30852
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860724"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a>Microsoft 365의 AIR(자동 조사 및 대응) 개요

보안 경고가 트리거되면 보안 운영팀이 해당 경고를 살펴보고 조직 보호 단계를 수행해야 합니다. 경우에 따라 보안 운영 팀이 트리거되는 알림을 통해 과도하게 소모되는 경우도 있습니다. Office 365 ATP(Office 365 Advanced Threat Protection)의 자동화된 조사 및 응답(AIR) 기능을 통해 도와드리게 도움이 될 수 있습니다. 

AIR을 사용하면 보안 운영팀이 보다 효율적이고 효과적으로 운영될 수 있습니다. AIR 기능에는 오늘날 잘 알려진 위협에 대한 응답으로 자동화된 조사 프로세스가 포함됩니다. 적절한 수정 작업은 승인을 기다리며 보안 운영 팀이 감지된 위협에 대응할 수 있도록 지원합니다. 

이 문서에서는 AIR에 대한 개요를 제공합니다. AIR 사용을 시작할 준비가 되면 자동 [조사를 참조하여 위협에 대응합니다.](office-365-air.md)

## <a name="at-a-high-level"></a>상위 수준에서

알림이 트리거되면 보안 플레이북이 효과적입니다. 상황에 따라 자동화된 [조사 프로세스를 시작할 수](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) 있습니다. 자동화 조사를 진행하는 동안 및 이후에 시정 [조치를 권장합니다.](air-remediation-actions.md) Office 365 Advanced Threat Protection에서는 아무 작업도 자동으로 수행되지 않습니다. 보안 운영 팀이 검토를 검토한 다음 [각 수정 작업을 승인하거나 거부합니다.](air-review-approve-pending-completed-actions.md) 조사 후 수행되는 모든 작업이 승인 또는 거부되면 조사가 완료됩니다. 이러한 모든 활동은 보안 및 준수 센터에서 추적및 볼 & [있습니다(조사의 세부 정보 보기).](air-view-investigation-results.md#view-details-of-an-investigation)

다음 섹션에서는 발생하는 경고, 보안 플레이북 및 AIR의 예에 대한 자세한 정보를 제공합니다.

## <a name="alerts"></a>경고

[알림은](../../compliance/alert-policies.md#viewing-alerts) 보안 운영 팀 워크플로에 대한 사고 대응 트리거를 나타냅니다. 조사에 대해 적합한 알림에 우선 순위를 지정하며 주소가 지정되지 않은 위협을 방지하기어가 매력적입니다. 알림에 대해 조사를 수동으로 수행할 때 보안 운영 팀이 위협으로부터 위험에 처한 기관(콘텐츠, 장치 및 사용자)을 헌트하고 상관시이해야 합니다. 이러한 작업 및 워크플로에는 시간이 매우 오후 걸리고 여러 도구 및 시스템이 사용될 수 있습니다. AIR을 사용하여 보안 이벤트에 대한 조사 및 대응이 자동화되면 핵심 보안 및 위협 관리 경고가 자동으로 보안 응답 플레이북을 트리거합니다. 

현재 AIR의 경우 다음과 같은 종류의 경고 정책에서 생성된 경고가 자동조됩니다.  

- 악성 URL 클릭이 검색될 수 있는 경우
- 피싱으로 사용자가 보고하는 전자 메일`*`
- 배달 후 맬웨어가 제거되었다는 전자 메일 메시지`*`
- 피싱 URL이 포함된 전자 메일 메시지를 배달 후 제거`*`
- 감지된 의심스러운 전자 메일 전송 패턴`#`
- 사용자가 전자 메일 을 보내지 지나지 제한한 사용자`#`

> [!NOTE]
> 별표()로 표시된 알림은 보안 & 준수 센터 내에서 전자 메일 심각도를 해제한 상태에서 정보 `*` 심각도를 할당받습니다. *Informational* 전자 메일 알림은 경고 정책 구성을 통해 [설정될 수 있습니다.](../../compliance/alert-policies.md#alert-policy-settings) 해시()로 표시된 알림은 `#` 일반적으로 공개 미리 보기 플레이북과 관련되어 경고입니다.

알림을 확인하려면 규정 준수 & 센터에서 **경고**  >  **보기를 선택합니다.** 경고를 선택하여 세부 정보를 확인하고, 거기에서 조사 **링크를** 사용하여 해당 [조사로 이동합니다.](air-view-investigation-results.md#investigation-graph)  

> [!NOTE]
> 정보 경고는 기본적으로 경고 보기에 숨겨져 있습니다. 이러한 경고를 보려면 정보 경고를 포함하도록 경고 필터링을 변경합니다.

조직에서 경고 관리 시스템, 서비스 관리 시스템 또는 SIEM(보안 정보 및 이벤트 관리) 시스템을 통해 보안 경고를 관리하는 경우 전자 메일 알림 또는 Office 365 관리 작업 API를 통해 [해당 시스템에 알림을 보낼 수 있습니다.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) 전자 메일 또는 API를 통한 조사 알림에는 보안 & 준수 센터에서 경고에 액세스하는 링크가 포함됩니다. 사실상, 할당된 보안 관리자는 신속하게 조사를 탐색할 수 있도록 합니다.

![조사에 연결되는 알림](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>보안 플레이북

보안 플레이북은 Office Advanced Threat Protection 및 Microsoft Threat Protection의 자동화 중 심사 에서의 백 엔드 정책입니다. AIR에서 제공하는 보안 플레이북은 일반적인 실제 보안 시나리오를 기준으로 하며 보안 운영 팀의 피드백을 기반으로 개발됩니다. 조직 내에서 특정 알림이 트리거되면 보안 플레이북이 자동으로 시작됩니다. 경고가 트리거되면 연결된 플레이북이 자동화된 조사 및 응답(AIR) 시스템을 사용하여 실행됩니다. 전자 메일 메시지, 사용자, 제목, 보낸 사람 등의 모든 관련 메타데이터를 확인하여 특정 경고의 플레이북을 기반으로 하는 경고 분석 단계는 다음과 같습니다. AIR은 조사 플레이북의 검색 결과를 기반으로 조직의 보안 팀이 위협 요소를 제어하고 완화하는 데 수행할 수 있는 일을 권장합니다. 

AIR과 함께 받는 보안 플레이 북은 조직이 오늘날 전자 메일을 보내는 가장 자주 위협하는 위협을 수행하도록 고민하고 있습니다. Microsoft 및 당사의 자산을 방어하는 사람들을 포함하여 보안 운영 및 사고 대응 팀의 입력을 기반으로 합니다.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>보안 플레이 북이 단계별로 배포

AIR의 일부로 보안 플레이 북이 단계적으로 배포됩니다. 1단계는 일반적으로 사용할 수 있고 보안 관리자가 검토 및 승인할 수 있는 작업에 대한 권장 사항을 제공하는 여러 개의 플레이북이 포함되어 있습니다.

- 사용자가 보고한 피싱 메시지
- URL 클릭 결과 변경
- 맬웨어 배달 후 탐지(맬웨어 ZAP)
- 피싱 메일 배달 후 ZAP(피싱 ZAP) 감지

1단계에서는 위협 탐색기를 사용한 관리자가 트리거한 전자 메일 조사 지원도 [포함합니다.](threat-explorer.md)

2단계는 이제 공개 미리 보기에서 다음 Playbook과 함께 **진행되고,** 작업에 대한 권장 사항을 제공하고, 보안 관리자를 중심으로 문제를 조사하는 데 문제가 있습니다.

- 위검토된 사용자에 보고된 사용자(공개 미리 보기)

플레이북은 완료되면 해제될 예정입니다. [Microsoft 365 로드맵을 방문하여](https://www.microsoft.com/microsoft-365/roadmap) 다른 계획되고 곧 제공될 예정인 기능을 확인하세요.

### <a name="playbooks-include-investigation-and-recommendations"></a>플레이 북은 조사 및 권장 사항을 포함합니다.

AIR에서 각 보안 플레이 북에는 다음이 포함됩니다. 

- 전자 메일의 신원에 대한 루트 조사(예: 파일, URL, 받는 사람, IP 주소 등)
- 조직에서 받은 유사한 전자 메일에 대한 추가 헌팅 
- 다른 잠재적 위협을 식별하고 상관 관계를 확인하기 위해 수행된 단계 및 
- 권장 위협 수정 작업.

각 고급 단계에는 위협에 대한 깊고 세부적적및 전반적인 대응을 제공하기 위해 실행되는 여러 하위 단계가 포함됩니다.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>예: 사용자가 보고한 피싱 메시지는 조사 플레이북을 실행합니다.

조직의 사용자가 피싱 시도라고 생각되는 전자 메일을 받게 된다고 가정합니다. 해당 메시지를 보고하도록 교육한 사용자는 보고서 [메시지 추가 기능을 사용하여](enable-the-report-message-add-in.md) 분석을 위해 Microsoft에 보냅니다. 제출은 또한 시스템에 전송되며 탐색기(이전에는 사용자가 보고한 **보기)의 탐색기에 표시됩니다.** **Submissions** 또한 사용자가 보고한 메시지는 시스템 기반 정보 알림을 트리거하여 조사 플레이북을 자동으로 시작합니다.

루트 조사 단계에서 전자 메일의 다양한 측면이 평가됩니다. 이러한 측면은 다음과 같습니다.

- 위협 유형을 결정할 때
- 전송한 사람
- 전자 메일이 보내서 전송된 위치(인프라 보내기);
- 전자 메일의 다른 인스턴스가 배달되거나 차단되었는지 여부
- 분석가가의 평가
- 전자 메일이 알려진 캠페인에 연결되어 있는지 여부
- 등을 사용할 수 있습니다.

루트 조사가 완료되면 Playbook은 연결된 원래 전자 메일 및 응용 프로그램에 대해 수행할 권장 작업 목록을 제공합니다.
  
다음으로는 몇 가지 위협 조사 및 헌팅 단계가 실행됩니다.

- 전자 메일 메시지도 전자 메일 클러스터 검색을 통해 식별됩니다.
- 신호는 Microsoft Defender ATP 등 다른 [플랫폼과 공유됩니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- 사용자가 의심스러운 전자 메일 메시지의 악성 링크를 통해 클릭한 것인지 여부에 대해 결정됩니다.
- 확인은 Exchange Online[Protection(EOP) 및](exchange-online-protection-overview.md)Office 365 Advanced Threat Protection[(ATP)에서 수행되어](office-365-atp.md)사용자가 보고하는 다른 유사한 메시지가 있는지 알아봅니다.
- 검사는 사용자가 해지되었는지 확인하기 위해 수행됩니다. 이 확인은 Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)및 Azure Active [Directory에서](https://docs.microsoft.com/azure/active-directory)신호를 사용하여 관련된 모든 관련된 사용자 활동 사실과 연관시됩니다.

헌팅 단계 중에 다양한 헌팅 단계에 위험과 위협이 할당됩니다. 

재구성은 플레이북의 최종 단계입니다. 이 단계에서는 조사 및 헌팅 단계에 따라 수정 단계를 수행합니다. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>예: 보안 관리자가 위협 탐색기에서 조사를 트리거합니다.

조직의 보안 작업 팀은 경고로 트리거되는 자동화된 조사 외에도 위협 탐색기의 보기에서 자동 조사를 트리거할 [수 있습니다.](threat-explorer.md)

예를 들어 위협 탐색기의 맬웨어 보기를 사용한다고 **가정합니다.** 차트 아래의 탭을 사용하여 전자 메일 **탭을** 선택합니다. 목록에서 하나 이상의 항목을 선택하면 **+ 작업 단추가** 활성화됩니다. 

![선택한 메시지를 포함한 탐색기](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

동작 **메뉴를** 사용하면 트리거 **조사를 선택할 수 있습니다.**

![선택한 메시지에 대한 동작 메뉴](../../media/explorer-malwareview-selectedemails-actions.jpg)

알림에 의해 트리거되는 플레이북과 마찬가지로, 탐색기의 보기에서 트리거된 자동 조사, 위협을 식별하고 상관시키는 단계 및 이러한 위협을 완화하기 위한 권장 조치가 포함됩니다.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>예: 보안 작업 팀은 Office 365 관리 작업 API를 사용하여 AIR을 SIEM과 통합

Office 365 ATP의 AIR 기능에는 보안 [운영 팀이 위협을 &](air-view-investigation-results.md) 수 있는 보고서 대시보드 가운데 이를 포함합니다. 그러나 다른 솔루션과 AIR 기능을 통합할 수도 있습니다. 이러한 솔루션으로는 SIEM(보안 정보 및 이벤트 관리) 시스템, 사례 관리 시스템 또는 사용자 지정 보고 솔루션이 있습니다. 이러한 종류의 통합은 Office 365 관리 작업 [API를 사용하여 완료할 수 있습니다.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) 

예를 들어 조직은 보안 운영팀이 AIR에 의해 이미 처리된 사용자가 보고한 피싱 경고를 볼 수 있는 방법을 설정했습니다. 솔루션에 따라 관련 알림이 조직의 SIEM 서버 및 해당 사례 관리 시스템에 통합됩니다. 보안 운영 팀이 실실위의 시간과 노동에 집중할 수 있도록 이 솔루션을 통해 가양성 수를 대략적으로 줄일 수 있습니다. 이 사용자 지정 솔루션에 대한 자세한 내용은 [기술 커뮤니티 블로그를 참조하세요. Office 365 ATP 및 O365 관리 API를 사용하여 SOC의 효과성 개선.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

## <a name="next-step"></a>다음 단계

- [AIR 사용하여 시작](office-365-air.md)

## <a name="see-also"></a>참고 항목

- [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Microsoft Threat Protection의 자동화된 조사 및 대응 기능](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide)