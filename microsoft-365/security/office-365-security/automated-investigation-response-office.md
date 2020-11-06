---
title: Microsoft Defender for Office 365에서 자동화 된 조사 및 응답 (AIR) 작동 방식
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
ms.date: 11/05/2020
description: Office 용 Microsoft Defender 365에서 자동화 된 조사 및 응답 기능이 작동 하는지 확인
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 6923e283e4ec62de9e4a9c1d9196eb032724798d
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931961"
---
# <a name="how-automated-investigation-and-response-air-works-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365에서 자동화 된 조사 및 응답 (AIR) 작동 방식

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

보안 알림이 트리거되면 해당 경고를 확인 하 고 조직을 보호 하기 위한 단계를 수행 하는 보안 운영 팀이 진행 됩니다. 경우에 따라 보안 운영 팀에서 트리거된 경고 량이 지나치게 느껴질 수 있습니다. Microsoft Defender for Office 365의 자동 조사 및 응답 (AIR) 기능은 도움이 될 수 있습니다.

AIR을 사용 하면 보안 운영 팀이 보다 효율적이 고 효율적으로 작업할 수 있습니다. AIR 기능에는 현재 존재 하는 잘 알려진 위협에 대응 하 여 자동화 된 조사 프로세스가 포함 되어 있습니다. 적절 한 교정 작업을 통해 승인을 받고, 보안 운영 팀이 검색 된 위협에 대처할 수 있도록 합니다.

이 문서에서는 AIR이 몇 가지 예를 통해 작동 하는 방식에 대해 설명 합니다. AIR 사용을 시작할 준비가 되 면 [자동으로 위협에 대 한 조사 및 응답](office-365-air.md)을 참조 하세요.

- [예 1: 사용자가 보고 한 피싱 메시지가 조사 playbook를 시작 하는 경우](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [예 2: 보안 관리자가 위협 탐색기에서 조사를 트리거합니다.](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [예제 3: Office 365 관리 활동 API를 사용 하 여 AIR과의 보안 운영 팀 통합](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)


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

- [Microsoft 365 Defender의 자동화 된 조사 및 응답 기능에 대해 알아보기](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
