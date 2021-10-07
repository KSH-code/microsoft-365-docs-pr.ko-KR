---
title: Microsoft Defender에서 자동화된 조사 및 대응이 작동하는 Office 365
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
keywords: 자동화된 인시던트 대응, 조사, 수정, 위협 방지
ms.date: 01/29/2021
description: Microsoft Defender에서 자동화된 조사 및 응답 기능이 어떻게 Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e421f29ec1723ad724c64991e67bd0da31bb35b6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202492"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Microsoft Defender에서 자동화된 조사 및 대응이 작동하는 Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

보안 경고가 트리거되면 보안 운영 팀이 해당 경고를 보고 조직을 보호하기 위한 단계를 수행해야 합니다. 경우에 따라 보안 운영 팀이 트리거되는 경고의 양에 당황할 수 있습니다. Microsoft Defender for Office 365 자동화된 조사 및 대응(AIR) 기능이 도움이 될 수 있습니다.

AIR을 사용하면 보안 운영 팀이 보다 효율적이고 효율적으로 작업할 수 있습니다. AIR 기능에는 현재 존재하는 잘 알려진 위협에 대응하는 자동화된 조사 프로세스가 포함됩니다. 적절한 수정 작업은 승인을 대기하여 보안 운영 팀이 감지된 위협에 대응할 수 있도록 합니다.

이 문서에서는 AIR이 여러 예제를 통해 작동하는 방식에 대해 설명합니다. AIR 사용을 시작할 준비가 되면 위협 자동 조사 및 [대응을 참조합니다.](office-365-air.md)

- [예제 1: 사용자가 보고한 피싱 메시지가 조사 플레이북을 실행합니다.](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [예제 2: 보안 관리자가 위협 탐색기에서 조사를 트리거합니다.](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [예제 3: 보안 운영 팀이 OFFICE 365 관리 활동 API를 사용하여 AIR을 SIEM과 통합합니다.](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>예: 사용자가 보고한 피싱 메시지가 조사 플레이북을 실행합니다.

조직의 사용자가 피싱 시도로 생각할 수 있는 전자 메일을 받는 경우를 가정해 가정합니다. 이러한 메시지를 보고하도록 학습된 사용자는 보고서 [](enable-the-report-message-add-in.md) 메시지 추가 기능 [](enable-the-report-phish-add-in.md) 또는 피싱 보고 추가 기능을 사용하여 분석을 위해 Microsoft로 전송합니다. 제출은 시스템에 보내지며 제출 보기(이전의  사용자 보고 보기)의 탐색기에서 **표시됩니다.** 또한 사용자가 보고한 메시지는 이제 조사 플레이북을 자동으로 시작하는 시스템 기반 정보 경고를 트리거합니다.

루트 조사 단계에서는 전자 메일의 다양한 측면이 평가됩니다. 이러한 측면은 다음과 같습니다.

- 위협 유형에 대한 결정
- Who 전송합니다.
- 전자 메일이 전송된 위치(인프라 전송);
- 전자 메일의 다른 인스턴스가 배달 또는 차단된 경우
- 분석가의 평가
- 전자 메일이 알려진 캠페인과 연결되는지 여부
- 등.

루트 조사가 완료되면 재생북은 원래 전자 메일 및 연결된 엔터티에 대해 수행할 권장 작업 목록을 제공 합니다.

다음으로 몇 가지 위협 조사 및 헌팅 단계가 실행됩니다.

- 유사한 전자 메일 메시지는 전자 메일 클러스터 검색을 통해 식별됩니다.
- 신호는 끝점용 Microsoft Defender와 같은 다른 [플랫폼과 공유됩니다.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- 사용자가 의심스러운 전자 메일 메시지의 악의적인 링크를 클릭하는지 여부를 결정해야 합니다.
- EOP(Exchange Online Protection) 및 (microsoft[](exchange-online-protection-overview.md)[Defender for](defender-for-office-365.md)Office 365)에 대해 확인을 수행하여 사용자가 보고한 다른 유사한 메시지가 없는지 확인할 수 있습니다.
- 사용자가 손상된 경우 확인이 수행됩니다. 이 검사는 모든 관련 사용자 활동 [Office 365,](/cloud-app-security)Microsoft Cloud App Security [](/azure/active-directory)및 Azure Active Directory 신호를 활용합니다.

헌팅 단계에서는 다양한 헌팅 단계에 위험과 위협이 할당됩니다.

수정은 플레이북의 마지막 단계입니다. 이 단계에서는 조사 및 헌팅 단계에 따라 수정 단계를 수행합니다.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>예: 보안 관리자가 위협 탐색기에서 조사를 트리거합니다.

경고에 의해 트리거되는 자동화된 조사 외에도 조직의 보안 운영 팀은 위협 탐색기 의 보기에서 자동화된 조사를 트리거할 [수 있습니다.](threat-explorer.md)  또한 이 조사는 Microsoft Defender 인시던트 및 외부 SIEM 도구에서 이 조사가 트리거된 것으로 볼 수 있도록 경고를 생성합니다.

예를 들어 탐색기에서 맬웨어 **보기를 사용하고 있는** 경우를 가정해 보겠습니다. 차트 아래의 탭을 사용하여 전자 메일 **탭을** 선택합니다. 목록에서 항목을 하나 이상 선택하면 **+ 작업** 단추가 활성화됩니다.

![선택한 메시지가 있는 탐색기입니다.](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

작업 **메뉴를** 사용하여 조사 **트리거를 선택할 수 있습니다.**

![선택한 메시지에 대한 작업 메뉴입니다.](../../media/explorer-malwareview-selectedemails-actions.jpg)

경고에 의해 트리거되는 플레이북과 마찬가지로 탐색기에서 보기에서 트리거되는 자동 조사에는 루트 조사, 위협을 식별 및 상관 관계화하는 단계, 이러한 위협을 완화하기 위한 권장 조치가 포함됩니다.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>예: 보안 운영 팀이 OFFICE 365 관리 활동 API를 사용하여 AIR과 SIEM을 통합합니다.

Microsoft Defender for Office 365 보안 운영 [&](air-view-investigation-results.md) 팀이 위협을 모니터링하고 해결하기 위해 사용할 수 있는 세부 정보 보고서가 포함되어 있습니다. 그러나 AIR 기능을 다른 솔루션과 통합할 수도 있습니다. 예를 들어 SIEM(보안 정보 및 이벤트 관리) 시스템, 사례 관리 시스템 또는 사용자 지정 보고 솔루션이 있습니다. 이러한 종류의 통합은 관리 활동 API 에서 Office 365 [수 있습니다.](/office/office-365-management-api/office-365-management-activity-api-reference)

예를 들어 최근에 조직은 보안 운영 팀이 AIR에서 이미 처리한 사용자가 보고한 피싱 알림을 볼 수 있는 방법을 설정했습니다. 해당 솔루션은 관련 경고를 조직의 SIEM 서버 및 해당 사례 관리 시스템에 통합합니다. 이 솔루션은 보안 운영 팀이 실제 위협에 시간 및 노력을 집중할 수 있도록 가짓 긍정 수를 크게 줄입니다. 이 사용자 지정 솔루션에 대한 자세한 [내용은 Tech Community 블로그: Microsoft Defender for Office 365 O365 관리 API를 사용하여 SOC의](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)효율성 개선을 참조하세요.

## <a name="next-steps"></a>다음 단계

- [AIR 사용 시작](office-365-air.md)
- [보류 중 또는 완료된 수정 작업 보기](air-review-approve-pending-completed-actions.md)