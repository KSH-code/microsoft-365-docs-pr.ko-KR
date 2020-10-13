---
title: Office 365 Security, Office 365 ATP, EOP, ATP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Office 365의 보안, EOP부터 ATP 요금제 1 및 2, 표준 및 고급 보안 구성 등이 추가 됩니다. 사용자의 정의 및 속성을 보호 하는 방법을 이해 합니다.
ms.openlocfilehash: 94fce99d029d21524bc60af4622fda7ee38980e7
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430695"
---
# <a name="office-365-security-overview"></a>Office 365 보안 개요

이 문서에서는 클라우드의 새 보안 속성을 소개 합니다. 보안 작업 센터의 일부 인지에 관계 없이 해당 공간에 대 한 보안 관리자 이거나, 리프레셔를 사용 하 여 시작 해 보세요.

> [!CAUTION]
> **Outlook.com**, **microsoft 365 제품군**또는 **Microsoft 365 Personal**을 사용 하 고 있고 *안전한 링크* 또는 *안전한 첨부 파일* 정보가 필요한 경우 ***이 링크***: [Microsoft 365 구독자에 대 한 고급 Outlook.com 보안](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)을 클릭 합니다.

## <a name="office-365-security-spelled-out"></a>Office 365 보안에 대 한 자세한 표기

모든 Office 365 구독에는 보안 기능이 제공 됩니다. 수행할 수 있는 목표와 작업은 이러한 서로 다른 구독의 초점에 따라 달라 집니다. Office 365 보안에서는 다음과 같은 세 가지 주요 보안 서비스 (또는 제품)가 구독 유형에 연결 됩니다.

1. EOP (Exchange Online Protection)
1. Advanced Threat Protection, 요금제 1 (ATP P1)
1. Advanced Threat Protection, 계획 2 (ATP P2)

> [!NOTE]
> 구독을 구매한 경우 *지금*보안 기능을 롤아웃 해야 하는 경우 [위협 으로부터 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 문서의 단계를 건너뛰십시오. 구독을 처음 사용 하는 경우 시작 하기 전에 라이선스를 확인 하려는 경우 [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/#/homepage)에서 제품 > 대금 청구를 검색 하세요.

Office 365 보안은 EOP에서 제공 하는 핵심 보호를 기반으로 작성 되었습니다. Exchange Online 사서함을 찾을 수 있는 모든 구독에는 EOP이 제공 됩니다 (여기서 설명 하는 모든 보안 제품은 클라우드 기반).

이러한 세 가지 구성 요소는 다음과 같은 방식으로 설명 됩니다.

|EOP  | ATP P1 | ATP P2  |
|---------|---------|---------|
|광범위 한 볼륨 기반 알려진 공격을 방지 합니다.    |  제로 일 맬웨어, 피싱 및 비즈니스 전자 메일 손상 으로부터 전자 메일 및 공동 작업을 보호 합니다.       | 사후 위반 조사, 사냥 및 대응, 자동화 및 시뮬레이션 (교육)을 추가 합니다.         |

그러나 아키텍처 측면에서 각 요소를 보안에 대 한 누적 계층으로 생각 하면 보안이 강조 됩니다. 다음과 같습니다.

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="Placeholder graphic":::

이러한 각 서비스는 보호, 감지, 조사 및 대응 중에서 목표를 강조 하지만 모든 서비스는 보호, 감지, 조사 및 ***대응의*** ***모든*** 목표를 수행할 수 있습니다.

Office 365 보안의 핵심은 EOP 보호입니다. ATP P1에는 EOP이 포함 되어 있습니다. ATP P2에는 P1 및 EOP가 포함 됩니다. 누적 된 구조입니다. 따라서이 제품을 구성 하는 경우 EOP로 시작 하 고 ATP에 대 한 작업을 수행 해야 합니다.

전자 메일 인증 구성은 공용 DNS에서 발생 하지만 스푸핑 으로부터 보호 하려면이 기능을 구성 하는 것이 중요 합니다. *EOP가 있는 경우* *** [전자 메일 인증을 구성](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)해야***합니다.

Office 365 E3 또는 그 아래에는 EOP 있지만 독립 실행형 ATP P1을 업그레이드를 통해 구매할 수 있는 옵션이 있습니다. Office 365 E5가 있는 경우 이미 ATP P2를가지고 있습니다.

> [!TIP]
> 구독이 Office 365 E3 또는 E5가 아닌 경우 ATP P1으로 업그레이드할 수 있는 옵션이 있는지 계속 해 서 확인 합니다. 관심이 있는 경우 [이 웹 페이지](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) 에는 ATP P1 업그레이드를 위한 구독 목록이 표시 됩니다 (자세한 내용은 페이지 끝까지 확인).

## <a name="the-office-365-security-ladder-from-eop-to-atp"></a>EOP에서 ATP로의 Office 365 보안 사다리

<br/>

![EOP 및 ATP 및 보안에 중점을 두어 보호 하 고 검색에서 조사 하 고 응답 합니다.전자 메일 인증 구성 (최소 DKIM 및 DMARC 이상)을 EOP 이상으로 설정 해야 합니다.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)


> [!IMPORTANT]
> 자세한 내용은 [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview)및 [Advanced Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)페이지를 참조 하세요.

ATP 계획을 추가 하는 것이 순수한 EOP threat management에 대 한 이점은 처음부터 쉽게 알 수 있습니다. 조직에서 업그레이드 경로가 적합 한지를 쉽게 확인할 수 있도록 다음 작업을 수행 하는 경우 각 제품의 기능을 살펴보겠습니다.

 - 위협 방지 및 감지
 - 조사
 - 멈추게

**Exchange Online Protection**을 사용 하 여 시작:
<p>

|방지/감지  |조사  |응답  |
|---------|---------|---------|
| 기술에는 다음이 포함 됩니다.<ul><li>스팸</li><li>피싱</li><li>맬웨어</li><li>대량 메일</li><li>스푸핑 인텔리전스</li><li>가장 검색</li><li>관리자 격리</li><li>가양성 및 거짓 네거티브를 관리 하 고 사용자 제출</li><li>Url 및 파일에 대 한 허용/차단</li><li>보고서</li></u1>|<li>감사 로그 검색</li><li>메시지 추적</li>|<li>제로 시간 자동 제거 (ZAP)</li><li>허용 및 차단 목록의 구체화 및 테스트</li>|

EOP를 자세히 검토 하려면 **[이 문서를 참조](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-21vianet&branch=tp_EOPOverview)** 하세요.

이러한 제품은 누적 되는 것 이므로 ATP P1을 평가 하 여 구독 하기로 결정 하면 이러한 기능을 추가 합니다.

**Advanced Threat Protection의 향상 된 기능, 계획 1** (날짜):
<p>

|방지/감지  |조사  |응답  |
|---------|---------|---------|
| 기술에는 EOP plus의 모든 것이 포함 됩니다.<u1><li>안전한 첨부 파일</li><li>안전한 링크<li>작업에 대 한 ATP 보호 (예: SharePoint Online, 팀, 비즈니스용 OneDrive)</li><li>전자 메일, Office 클라이언트 및 팀의 클릭 시간 보호</li><li>ATP 피싱 방지</li><li>사용자 및 도메인 가장 보호</li><li>경고에 대 한 알림 및 SIEM 통합 API</li>|<li>검색에 대 한 SIEM 통합 API</li><li>**실시간 검색 도구**</li><li>URL 추적</li>|<li>동일</li></u1>

따라서 ATP P1은 집을 ***방지*** 하는 쪽을 확장 하 고 추가 ***검색***형식을 추가 합니다.

ATP P1은 조사를 위해 **실시간** 검색도 추가 합니다. 이 위협 인식 도구의 이름은 ATP P1을 알고 있다는 것을 명확 하 게 *알* 수 있으므로 굵게 표시 됩니다. ATP P2에는 나타나지 않습니다.

**Advanced Threat Protection에서 향상 된 기능, 계획 2** (날짜):
<p>

|방지/감지  |조사  |응답  |
|---------|---------|---------|
| 기술에는 EOP의 모든 것과 ATP P1 plus가 포함 됩니다.<u1><li>동일</li>|<li>**위협 탐색기**</li><li>위협 트래커</li><li>캠페인 보기</li>|<li>자동 조사 및 대응 (AIR)</li><li>위협 탐색기의 AIR</li><li>손상 된 사용자를 위한 AIR</li><li>자동 조사를 위한 SIEM 통합 API</li>

따라서 ATP P2는 집의 ***조사 및 응답*** 쪽을 확장 하 고 새 사냥 강도를 추가 합니다. 자동화.

ATP P2에서는 기본 구하기 도구를 실시간 검색 대신 **위협 탐색기** 라고 합니다. 보안 센터로 이동할 때 Threat Explorer가 표시 되 면 ATP P2에 있는 것입니다.

ATP P1 및 P2의 세부 정보를 보려면 **[이 문서로 이동](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** 합니다.

> [!TIP]
> EOP 및 ATP는 최종 사용자에 게 제공 되는 경우에도 서로 다릅니다. EOP 및 ATP P1에서는 포커스를 *인식*하므로 이러한 두 서비스에는 사용자가 의심 스러운 전자 메일을 보고 하 여 추가 분석을 수행할 수 있도록 *보고서 메시지 Outlook 추가 기능이* 포함 되어 있습니다. <p> ATP P2 (EOP 및 P1의 모든 것이 포함 됨)에서는 최종 사용자에 대 한 *추가 교육* 으로 포커스가 이동 되므로 보안 작업 센터에는 강력한 *위협 시뮬레이터* 도구에 대 한 액세스 권한 및 최종 사용자 메트릭이 제공 됩니다.

## <a name="office-365-atp-plan-1-vs-plan-2-cheat-sheet"></a>Office 365 ATP 계획 1 및 계획 2 요약 정보 시트

이 빠른 참조는 각 ATP 구독에 제공 되는 기능을 이해 하는 데 도움이 됩니다. 비즈니스 의사 결정자는 EOP 기능에 대 한 지식과 함께 사용 하 여 사용자의 요구에 가장 적합 한 ATP를 결정 하는 데 도움이 될 수 있습니다.

|Office 365 ATP 계획 1|Office 365 ATP 계획 2|
|---|---|
|<br/>구성, 보호 및 검색 기능: <ul><li>[안전한 첨부 파일](atp-safe-attachments.md)</li><li>[안전한 링크](atp-safe-links.md)</li><li>[SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP](atp-for-spo-odb-and-teams.md)</li><li>[ATP 피싱 방지 보호 기능](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[실시간 탐지](threat-explorer.md)</li></ul>|Office 365 ATP 계획 1 기능<br/>--- 추가 ---<br/>자동화, 조사, 수정 및 교육 기능:</li><li>[위협 트래커](threat-trackers.md)</li><li>[위협 탐색기](threat-explorer.md)</li><li>[자동화된 조사 및 응답](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[공격 시뮬레이터](attack-simulator.md)</li></ul>|
|

- Office 365 ATP 계획 2는 Office 365 E5, Office 365 A5 및 Microsoft 365 E5에 포함되어 있습니다.

- Office 365 ATP 계획 1은 Microsoft 365 Business Premium에 포함되어 있습니다.

- Office 365 ATP 계획 1과 Office 365 ATP 계획 2는 특정 구독의 추가 기능으로 사용할 수 있습니다. 자세한 내용은 [ATP 계획에서](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)사용할 수 있는 다른 링크 기능을 참고 하십시오.

- [안전한 문서](safe-docs.md) 기능은 Microsoft 365 E5 또는 Microsoft 365 E5 보안 라이선스가 있는 사용자만 사용할 수 있습니다(Office 365 ATP 계획에는 미포함).

- 현재 구독에 Office 365 ATP가 포함 되어 있지 않은 경우에는 [영업에 연락 하 여 평가판을 시작 하](https://go.microsoft.com/fwlink/p/?LinkId=518644)고 조직에서 ATP가 작동 하는 방식을 알아봅니다.

> [!TIP]
> ***참가자 팁*** Docs.microsoft.com 목차를 사용 하 여 EOP 및 ATP에 대해 알아볼 수 있습니다. 이 페이지로 돌아가 [Office 365 보안 개요](https://docs.microsoft.com/microsoft-365/security/office-365-security/?view=o365-worldwide)를 탐색 하면 측면 표시줄에 목차 조직이 있음을 확인할 수 있습니다. 배포 (마이그레이션 포함)로 시작 된 다음 방지, 검색, 조사 및 응답을 계속 합니다. <p> 이 구조는 보안 **관리** 항목 다음에 **보안 작업** 항목이 오도록 구분 됩니다. 작업 역할의 새 구성원 인 경우이 팁의 링크와 목차를 사용 하 여 공간을 파악 하는 데 도움이 됩니다. *사용자 의견 링크* 를 사용 하 고 *문서를 평가해* 보십시오. 피드백을 통해 사용자에 게 제공 되는 정보를 개선할 수 있습니다.

## <a name="where-to-go-next"></a>다음으로 이동 위치

보안 관리자 인 경우에는 메일에 대해 DKIM 또는 DMARC를 구성 해야 할 수 있습니다. 우선 순위 사용자에 대해 ' 고급 ' 보안 미리 설정을 롤아웃할 수도 있고 제품의 새로운 기능을 찾을 수 있습니다. 또는 보안 Ops를 사용 중인 경우 실시간 검색 또는 위협 탐색기를 활용 하 여 최종 사용자에 게 공격 시뮬레이터를 조사 및 대응 하거나 교육을 받을 수 있습니다. 어느 쪽이 든 다음에는 확인할 사항에 대 한 몇 가지 추가 권장 사항을 제공 합니다.

[SPF, DKIM 및 DMARC (세 가지 설정에 대 한 링크 포함)를 포함 하는 전자 메일 인증](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)

[권장 되는 특정 ' 골든 ' configs를 참조](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 하 고 [권장 사전 설정을 사용 하 여 보안 정책을 빠르게 구성](https://docs.microsoft.com/microsoft-365/security/office-365-security/preset-security-policies)

[Office 365 ATP의 새로운 기능 (EOP 개발 포함)](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp) 에 대해 설명 합니다.

[위협 탐색기 또는 실시간 검색 사용](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)

[Office 365 ATP에서 공격 시뮬레이터](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator) 사용