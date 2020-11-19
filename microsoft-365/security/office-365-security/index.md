---
title: Office 365 보안, Office 365 용 Microsoft Defender, EOP, MSDO
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
description: Office 365의 보안, EOP부터 Defender for Office 365 요금제 1 및 2, 표준 및 고급 보안 구성 등이 추가 됩니다. 사용자의 정의 및 속성을 보호 하는 방법을 이해 합니다.
ms.openlocfilehash: 008488149a403fdafef9de0b0f64a9a43616debe
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357758"
---
# <a name="office-365-security-overview"></a>Office 365 보안 개요

이 문서에서는 클라우드의 새 보안 속성을 소개 합니다. 보안 작업 센터의 일부 인지에 관계 없이 해당 공간에 대 한 보안 관리자 이거나, 리프레셔를 사용 하 여 시작 해 보세요.

> [!CAUTION]
> **Outlook.com**, **microsoft 365 제품군** 또는 **Microsoft 365 Personal** 을 사용 하는 경우에는 *안전 링크* 또는 *안전한 첨부 파일* 정보가 필요 합니다. * [Microsoft 365 구독자를 위해](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)**이 링크** _: 고급 Outlook.com 보안을 클릭 합니다.

## <a name="office-365-security-spelled-out"></a>Office 365 보안에 대 한 자세한 표기

모든 Office 365 구독에는 보안 기능이 제공 됩니다. 수행할 수 있는 목표와 작업은 이러한 서로 다른 구독의 초점에 따라 달라 집니다. Office 365 보안에서는 다음과 같은 세 가지 주요 보안 서비스 (또는 제품)가 구독 유형에 연결 됩니다.

1. EOP (Exchange Online Protection)
1. Microsoft Defender for Office 365 계획 1 (Defender for Office P1)
1. Microsoft Defender for Office 365 계획 2 (Defender for Office P2)

> [!NOTE]
> 구독을 구매한 상태에서 _right 보안 기능을 롤아웃 해야 하는 경우에는 [위협 으로부터 보호](protect-against-threats.md) 문서의 단계를 건너뛰십시오. 구독을 처음 사용 하는 경우 시작 하기 전에 라이선스를 확인 하려는 경우 [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/#/homepage)에서 제품 > 대금 청구를 검색 하세요.

Office 365 보안은 EOP에서 제공 하는 핵심 보호를 기반으로 작성 되었습니다. Exchange Online 사서함을 찾을 수 있는 모든 구독에는 EOP이 제공 됩니다 (여기서 설명 하는 모든 보안 제품은 클라우드 기반).

이러한 세 가지 구성 요소는 다음과 같은 방식으로 설명 됩니다.

|EOP|Microsoft Defender for Office 365 P1|Microsoft Defender for Office 365 P2|
|---|---|---|
|광범위 한 볼륨 기반 알려진 공격을 방지 합니다.|제로 일 맬웨어, 피싱 및 비즈니스 전자 메일 손상 으로부터 전자 메일 및 공동 작업을 보호 합니다.|사후 위반 조사, 사냥 및 대응, 자동화 및 시뮬레이션 (교육)을 추가 합니다.|
|

그러나 아키텍처 측면에서 각 요소를 보안에 대 한 누적 계층으로 생각 하면 보안이 강조 됩니다. 다음과 같습니다.

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP 및 Microsoft Defender for Office 365 및 서비스 강조 (전자 메일 인증에 대 한 참고 사항 포함)를 통해 서로 간의 관계":::

이러한 각 서비스는 보호, 감지, 조사 및 응답 중에서 목표를 강조 하지만 서비스는 보호 **all**, 감지, 조사 및 응답의 _*_모든_*_ 목표를 수행할 수 있습니다.

Office 365 보안의 핵심은 EOP 보호입니다. Microsoft Defender for Office 365 P1에는 EOP이 포함 되어 있습니다. Defender for Office 365 P2에는 P1 및 EOP이 포함 되어 있습니다. 누적 된 구조입니다. 따라서이 제품을 구성 하는 경우 EOP로 시작 하 고 Office 365 용 Defender로 작업을 수행 해야 합니다.

전자 메일 인증 구성은 공용 DNS에서 발생 하지만 스푸핑 으로부터 보호 하려면이 기능을 구성 하는 것이 중요 합니다. _EOP가 있는 경우 * ***[전자 메일 인증을 구성](email-validation-and-authentication.md)해야**_ 합니다.

Office 365 E3이 있거나 아래에 EOP 있지만 업그레이드를 통해 Office 365 P1 용 독립 실행형 Defender를 구입 하는 옵션을 사용할 수 없습니다. Office 365 E5가 있는 경우 이미 Office 365 P2 용 Defender가 있는 것입니다.

> [!TIP]
> 구독이 Office 365 E3 또는 E5가 아니면 Office 365 P1 용으로 Microsoft Defender로 업그레이드할 수 있는 옵션이 있는지 계속 해 서 확인 합니다. 관심 있는 경우 [이 웹 페이지](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) 에는 Microsoft Defender for Office 365 P1 업그레이드에 적합 한 구독이 나열 되어 있습니다 (자세한 내용은 페이지 끝까지 확인).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>EOP에서 Microsoft Defender for Office 365의 Office 365 보안 사다리

![EOP 및 Microsoft Defender for Office 365 및 보안에 중점을 두어 보호 하 고 검색에서 조사 하 고 응답 합니다. 전자 메일 인증 구성 (최소 DKIM 및 DMARC 이상)을 EOP 이상으로 설정 해야 합니다.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> 이러한 페이지에 대 한 자세한 내용은 [Exchange Online Protection](exchange-online-protection-overview.md)및 [Defender for Office 365](office-365-atp.md)을 참조 하세요.

Microsoft Defender for Office 365 계획을 추가 하는 것을 이해 하는 것이 순수한 EOP threat management에 대 한 이점은 처음에는 알기 어려울 수 있습니다. 조직에서 업그레이드 경로가 적합 한지를 쉽게 확인할 수 있도록 다음 작업을 수행 하는 경우 각 제품의 기능을 살펴보겠습니다.

- 위협 방지 및 감지
- 조사
- 멈추게

_ * Exchange 온라인 보호 * *로 시작 하는 경우:
<p>

|방지/감지|조사|응답|
|---|---|---|
|기술에는 다음이 포함 됩니다.<ul><li>스팸</li><li>피싱</li><li>맬웨어</li><li>대량 메일</li><li>스푸핑 인텔리전스</li><li>가장 검색</li><li>관리자 격리</li><li>가양성 및 거짓 네거티브를 관리 하 고 사용자 제출</li><li>Url 및 파일에 대 한 허용/차단</li><li>보고서</li></u1>|<li>감사 로그 검색</li><li>메시지 추적</li>|<li>제로 시간 자동 제거 (ZAP)</li><li>허용 및 차단 목록의 구체화 및 테스트</li>|
|

EOP를 자세히 검토 하려면 **[이 문서를 참조](exchange-online-protection-overview.md)** 하세요.

이러한 제품은 누적 되는 것 이므로 Office 365 P1 용 Microsoft Defender를 평가 하 여 구독 하기로 결정 하면 이러한 기능을 추가 합니다.

**Office 365 용 Defender에서 향상 되었으며, 계획 1** (날짜)에 대해 다음을 수행 합니다.
<p>

|방지/감지|조사|응답|
|---|---|---|
|기술에는 EOP plus의 모든 것이 포함 됩니다.<u1><li>안전한 첨부 파일</li><li>안전한 링크<li>Microsoft Defender for Office 365 protection (예: 작업의 경우) SharePoint Online, 팀, 비즈니스용 OneDrive)</li><li>전자 메일, Office 클라이언트 및 팀의 클릭 시간 보호</li><li>Office 365 용 Defender의 피싱 방지</li><li>사용자 및 도메인 가장 보호</li><li>경고에 대 한 알림 및 SIEM 통합 API</li>|<li>검색에 대 한 SIEM 통합 API</li><li>**실시간 검색 도구**</li><li>URL 추적</li>|<li>동일</li></u1>

따라서 Microsoft Defender for Office 365 P1은 집을 확장 하 고 *_prevention_* 추가 _*_검색_*_ 형식을 추가 합니다.

Microsoft Defender for Office 365 P1은 조사를 위해 _ *실시간* 검색 *도 추가 합니다. 이 위협 사냥 도구의 이름은 Office 365 P1에 대 한 Defender가 있다는 것을 명확 하 게 *알* 수 있으므로 굵게 표시 됩니다. Office 365 P2에 대 한 Defender에는 표시 되지 않습니다.

**Office 365 용 Defender에서 향상 되었으며, 계획 2** (날짜)에 대해 다음을 수행 합니다.
<p>

|방지/감지|조사|응답|
|---|---|---|
|기술에는 EOP의 모든 것이 포함 되며, Microsoft Defender for Office 365 P1 plus:<u1><li>동일</li>|<li>**위협 탐색기**</li><li>위협 트래커</li><li>캠페인 보기</li>|<li>자동 조사 및 대응 (AIR)</li><li>위협 탐색기의 AIR</li><li>손상 된 사용자를 위한 AIR</li><li>자동 조사를 위한 SIEM 통합 API</li>

따라서 Microsoft Defender for Office 365 P2는 집의 **_조사 및 응답_* _ 면을 확장 하 고 새 사냥 강도를 추가 합니다. 자동화.

Microsoft Defender for Office 365 P2에서는 기본 구하기 도구를 실시간 검색 대신 ¹*Threat Explorer** 라고 합니다. 보안 센터로 이동할 때 Threat Explorer가 표시 되 면 Microsoft Defender for Office 365 P2가 있는 것입니다.

Microsoft Defender for Office 365 P1 및 P2에 대 한 자세한 내용을 보려면 **[이 문서로 이동](office-365-atp.md)** 하세요.

> [!TIP]
> EOP 및 Microsoft Defender for Office 365는 최종 사용자에 게 제공 되는 경우에도 다릅니다. EOP 및 Defender for Office 365 P1에서는 포커스를 *인식* 하므로, 이러한 두 서비스에는 추가 분석을 위해 사용자가 의심 스러운 전자 메일을 보고할 수 있도록 *보고서 메시지 Outlook 추가 기능이* 포함 되어 있습니다. <p> Defender for Office 365 P2 (EOP 및 P1의 모든 것이 포함 됨)에서는 최종 사용자에 대 한 *추가 교육* 으로 포커스가 이동 되므로 보안 작업 센터에는 강력한 *위협 시뮬레이터* 도구에 대 한 액세스 권한 및 최종 사용자 메트릭이 제공 됩니다.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 계획 1 및 계획 2 요약 정보 시트

이 빠른 참조는 각 Microsoft Defender for Office 365 구독에 제공 되는 기능을 이해 하는 데 도움이 됩니다. EOP 기능에 대 한 지식과 함께 사용 하면 비즈니스 의사 결정권자가 요구 사항에 가장 적합 한 Office 365의 Microsoft Defender를 결정 하는 데 도움이 될 수 있습니다.

|Defender for Office 365 계획 1|Defender for Office 365 계획 2|
|---|---|
|구성, 보호 및 검색 기능: <ul><li>[안전한 첨부 파일](atp-safe-attachments.md)</li><li>[안전한 링크](atp-safe-links.md)</li><li>[SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP](atp-for-spo-odb-and-teams.md)</li><li>[Defender for Office 365의 피싱 방지 보호 기능](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[실시간 탐지](threat-explorer.md)</li></ul>|Defender for Office 365 계획 1 기능<br/>--- 추가 ---<br/>자동화, 조사, 수정 및 교육 기능:</li><li>[위협 트래커](threat-trackers.md)</li><li>[위협 탐색기](threat-explorer.md)</li><li>[자동화된 조사 및 응답](office-365-air.md)</li><li>[공격 시뮬레이터](attack-simulator.md)</li></ul>|
|

- Office 365 E5, Office 365 A5 및 Microsoft 365 E5에는 microsoft Defender for Office 365 계획 2가 포함 되어 있습니다.

- Office 365용 Microsoft Defender 플랜 1은 Microsoft 365 Business Premium에 포함되어 있습니다.

- Microsoft Defender for Office 365 계획 1과 Office 용 Defender 365 계획 2는 각각 특정 구독에 대 한 추가 기능으로 사용할 수 있습니다. 자세한 내용은 [Microsoft Defender For Office 365 계획에서 사용할](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)수 있는 또 다른 링크 기능을 설명 합니다.

- [안전한 문서](safe-docs.md) 기능은 Microsoft 365 E5 또는 Microsoft 365 E5 보안 라이선스가 있는 사용자만 사용할 수 있습니다. (Office 365용 Microsoft Defender 플랜에는 미포함)

- 현재 구독에 Office 365 용 Microsoft Defender가 포함 되어 있지 않은 경우에는 [영업에 연락 하 여 평가판을 시작 하](https://go.microsoft.com/fwlink/p/?LinkId=518644)고 조직에서 microsoft Defender for Office 365가 작동 하는 방식을 확인 하세요.

> [!TIP]
> ***Insider tip** _. Docs.microsoft.com 목차를 사용 하 여 EOP 및 Office 용 Microsoft Defender 365에 대해 알아볼 수 있습니다. 이 페이지로 돌아가 [Office 365 보안 개요](https://docs.microsoft.com/microsoft-365/security/office-365-security)를 탐색 하면 측면 표시줄에 목차 조직이 있음을 확인할 수 있습니다. 배포 (마이그레이션 포함)로 시작 된 다음 방지, 검색, 조사 및 응답을 계속 합니다. <p> 이 구조는 _ *보안 관리** 항목과 **보안 작업** 항목을 차례로 구분 하 여 구성 합니다. 작업 역할의 새 구성원 인 경우이 팁의 링크와 목차를 사용 하 여 공간을 파악 하는 데 도움이 됩니다. *사용자 의견 링크* 를 사용 하 고 *문서를 평가해* 보십시오. 피드백을 통해 사용자에 게 제공 되는 정보를 개선할 수 있습니다.

## <a name="where-to-go-next"></a>다음으로 이동 위치

보안 관리자 인 경우에는 메일에 대해 DKIM 또는 DMARC를 구성 해야 할 수 있습니다. 우선 순위 사용자에 대해 ' 고급 ' 보안 미리 설정을 롤아웃할 수도 있고 제품의 새로운 기능을 찾을 수 있습니다. 또는 보안 Ops를 사용 중인 경우 실시간 검색 또는 위협 탐색기를 활용 하 여 최종 사용자에 게 공격 시뮬레이터를 조사 및 대응 하거나 교육을 받을 수 있습니다. 어느 쪽이 든 다음에는 확인할 사항에 대 한 몇 가지 추가 권장 사항을 제공 합니다.

[SPF, DKIM 및 DMARC (세 가지 설정에 대 한 링크 포함)를 포함 하는 전자 메일 인증](email-validation-and-authentication.md)

[권장 되는 특정 ' 골든 ' configs를 참조](recommended-settings-for-eop-and-office365-atp.md) 하 고 [권장 사전 설정을 사용 하 여 보안 정책을 빠르게 구성](preset-security-policies.md)

[Microsoft Defender For Office 365의 새로운 기능 (EOP 개발 포함)](whats-new-in-office-365-atp.md) 에 대해 설명 합니다.

[위협 탐색기 또는 실시간 검색 사용](threat-explorer.md)

[Microsoft Defender For Office 365의 Attack 시뮬레이터](attack-simulator.md) 사용
