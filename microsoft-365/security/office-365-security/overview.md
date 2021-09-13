---
title: Office 365 Microsoft Defender for Office 365 및 Exchange Online Protection
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 07/21/2021
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Office 365의 보안, EOP에서 Office 365 플랜 1 및 2로 변경, 표준(Standard) 및 엄격한(Strict) 보안 구성 등. 현재 보유 중인 항목이 무엇이고 이러한 항목을 어떻게 보호할 수 있는지 알아보세요.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b9db76654e19309816b29e5cfe607c064b8d364
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192292"
---
# <a name="microsoft-defender-for-office-365-security-overview"></a>Microsoft Defender for Office 365 보안 개요

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)

이 문서에서는 클라우드의 보안 속성을 Office 365 새로운 Microsoft Defender를 소개합니다. 보안 운영 센터의 일원인지, 해당 공간에 새로 온 보안 관리자인지, 또는 분위기 전환을 원하는지와 관계 없이, 이제 시작하겠습니다.

> [!CAUTION]
> **Outlook.com**, **Microsoft 365 Family** 또는 **Microsoft 365 Personal** 을 사용 중이고 *안전한 링크* 또는 *안전한 첨부 파일 정보* 가 필요한 경우 이 [Microsoft 365 구독자를위한 고급 Outlook.com 보안](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2) ***링크를 클릭*** 합니다.

## <a name="what-is-defender-for-office-365-security"></a>보안에 대한 Defender Office 365

모든 Office 365 구독에는 보안 기능이 함께 제공됩니다. 수행할 수 있는 목표와 작업은 이러한 여러 구독의 포커스에 따라 다릅니다. Office 365 보안에는 구독 유형과 연계된 세 가지 주요 보안 서비스(또는 제품)가 있습니다.

1. EOP(Exchange Online Protection)
1. Office 365용 Microsoft Defender 플랜 1(Office P1용 Defender)
1. Office 365용 Microsoft Defender 플랜 2(Office P2용 Defender)

> [!NOTE]
> 구독을 구입했고 *지금 바로* 보안 기능을 출시해야 한다면 [위협](protect-against-threats.md)으로부터 보호 문서의 단계로 건너 뛰세요. 구독을 처음 사용하고 시작하기 전에 라이선스를 알고 싶다면 [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/#/homepage)에서 청구> 내 제품을 찾아보세요.

EOP에서 제공하는 핵심 보호를 위한 Office 365 보안 빌드입니다. EOP는 Exchange Online 사서함을 찾을 수 있는 모든 구독에 있습니다(여기서 설명하는 모든 보안 제품은 클라우드 기반임).

이러한 방식으로 설명된 세 가지 구성 요소를 보는 것이 익숙할 수 있습니다.

|EOP|Office 365용 Microsoft Defender P1|Office 365용 Microsoft Defender P2|
|---|---|---|
|광범위한 볼륨 기반의 알려진 공격을 방지합니다.|제로 데이 맬웨어, 피싱 메일 및 비즈니스 전자 메일 손상으로부터 전자 메일 및 공동 작업을 보호합니다.|위반 후 조사, 사냥 및 대응, 자동화 및 시뮬레이션 (교육용)을 추가하세요.|
|

그러나 아키텍처 측면에서 각 부분을 보안에 중점을 둔 누적 보안 계층으로 생각하여 시작해 봅시다. 다음과 더 비슷합니다.

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP 및 Office 365용 Microsoft Defender와 전자 메일 인증에 대한 참고 사항을 포함하여 서비스에 중점을 둔 상호 관계 ":::

이러한 각 서비스는 보호, 감지, 조사 및 대응 중 목표를 강조하지만 * **모든** _서비스는 보호, 탐지, 조사 및 대응 중_ *_모든_* 목표를 수행할 수 있습니다.

Office 365 보안의 핵심은 EOP 보호입니다. Office 365용 Microsoft Defender P1에는 EOP가 포함되어 있습니다. Defender for Office 365 P2에는 P1 및 EOP가 포함되어 있습니다. 이러한 구조는 누적적입니다. 따라서 이 제품을 구성할 때에는 EOP로 시작하여 Office 365용 Defender로 작업해야 합니다.

전자 메일 인증 구성은 공개 DNS에서 실행하지만, 스푸핑을 차단하는 데 도움이 하도록 이 기능을 구성하는 것이 중요합니다. *EOP가 있는 경우* ***[전자 메일 인증을 구성](email-validation-and-authentication.md)*** 해야 합니다.

Office 365 E3 이상이 있는 경우 EOP가 있지만 업그레이드를 통해 독립 실행형 Defender for Office 365 P1을 구입하는 옵션이 제공됩니다. Office 365 E5가 있다면 Office 365용 Defender P2가 이미 있는 것입니다.

> [!TIP]
> 구독이 Office 365 E3 또는 E5가 아닌 경우에도 Office 365용 Microsoft Defender P1로 업그레이드 할 수 있는 옵션이 있는지 확인할 수 있습니다. 관심이 있다면 [이 웹 페이지 ](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids)에 Office 365용 Defender P1 업그레이드에 적합한 구독 목록이 나와 있습니다(자세한 내용은 페이지 끝 부분을 확인하세요).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>EOP에서 Office 365용 Microsoft Defender로의 Office 365 보안 사다리

> [!IMPORTANT]
> [Exchange Online Protection ](exchange-online-protection-overview.md) 및 [Office 365용 Defender](defender-for-office-365.md)에서 자세한 내용을 알아보세요.

Office 365용 Defender 플랜을 추가하는 것이 완벽한 EOP 위협 관리에 유리한 이유는 한 번에 파악하기 어려울 수 있습니다. 업그레이드 경로가 조직에 적합한 지 분류하는 데 도움이 되도록 다음과 같은 경우 각 제품의 기능을 살펴 보겠습니다.

- 위협 방지 및 감지
- 조사 중
- 응답

**Exchange Online Protection** 시작
<p>

|방지/감지|조사|응답|
|---|---|---|
|기술에 포함되는 사항은 다음과 같습니다.<ul><li>스팸</li><li>phish</li><li>맬웨어</li><li>대량 메일</li><li>스푸핑 인텔리전스</li><li>가장 검색</li><li>관리자 격리</li><li>가양성 및 가음성의 관리자 및 사용자 전송</li><li>URL 및 파일에 대한 허용/차단</li><li>보고서</li></u1>|<li>감사 로그 검색</li><li>메시지 추적</li>|<li>ZAP(제로 아워 자동 제거)</li><li>허용 및 차단 목록 수정 및 테스트</li>|
|

EOP에 대해 자세히 알아보려면 **[이 도움말로 이동](exchange-online-protection-overview.md)** 하세요.

이러한 제품은 누적되므로 Office 365용 Microsoft Defender P1을 평가하고 구독하기로 결정한다면, 이러한 기능을 추가하게 됩니다.

**Office 365용 Defender, 플랜 1**(최신)의 이점:
<p>

|방지/감지|조사|응답|
|---|---|---|
|기술에는 EOP에 포함된 모든 사항과 다음 항목이 포함됩니다.<u1><li>안전한 첨부 파일</li><li>안전한 링크<li>워크로드에 대한 Office 365용 Microsoft Defender 보호 기능(예: SharePoint Online, Teams, 비즈니스용 OneDrive)</li><li>전자 메일, Office 클라이언트 및 Teams의 클릭 시간 보호</li><li>Office 365용 Defender의 피싱 방지</li><li>사용자 및 도메인 가장 보호</li><li>알림 및 알림에 대한 SIEM 통합 API</li>|<li>검색을 위한 SIEM 통합 API</li><li>**실시간 검색 도구**</li><li>URL 추적</li>|<li>같음</li></u1>

따라서 Office 365용 Microsoft Defender P1는 집의 **방지** _측면을 확장하고_ 또 다른 형식의 _감지_**를 추가합니다.

Office 365용 Microsoft Defender P1은 조사를 위해 **실시간 감지** 기능도 추가합니다. 이 위협 검색 도구의 이름은 Office 365용 Defender P1이 있다는 것을 분명히 *알 수* 있기 때문에 굵게 표시됩니다. Office 365용 Microsoft Defender P2에는 표시되지 않습니다.

**Office 365용 Defender, 플랜 2**(최신)의 이점:
<p>

|방지/감지|조사|응답|
|---|---|---|
|기술에는 EOP의 모든 기능과 Office 365용 Microsoft Defender P1 및 다음 항목이 포함됩니다. <u1><li>같음</li>|<li>**위협 탐색기**</li><li>위협 추적기</li><li>캠페인 보기</li>|<li>자동 조사 및 대응(AIR)</li><li>위협 탐색기의 AIR</li><li>손상된 사용자를 위한 AIR</li><li>자동화된 조사를 위한 SIEM 통합 API</li>

따라서 Office 365용 Microsoft Defender P2는 ***조사 및 대응*** 측면을 확장하고 새로운 검색 능력을 추가합니다. 자동화

Office 365용 Microsoft Defender P2에서는 기본 검색 도구를 실시간 감지가 아닌 **위협 탐색기** 이라고 합니다. Microsoft 365 Defender 포털로 이동할 때 위협 탐색기가 표시될 경우 P2용 Microsoft Defender에 Office 365 있습니다.

Office 365용 Microsoft Defender P1 및 P2에 대해 자세히 알아보려면 **[이 문서로 이동](defender-for-office-365.md)** 하세요.

> [!TIP]
> EOP 및 Office 365용 Microsoft Defender는 최종 사용자 측면에서도 차이가 있습니다. EOP 및 Office 365용 Defender P1의 포커스는 *인식* 이므로이 두 서비스에는 *보고 메시지 Outlook 추가 기능* 이 포함되어있어 사용자가 분석 목적으로 의심스러운 전자 메일을 보고할 수 있습니다. <p> Office 365용 Microsoft Defender P2(EOP 및 P1의 모든 내용을 포함)에서는 포커스가 최종 사용자를 위한 *추가 교육* 으로 전환되므로 보안 작업 센터는 제공하는 강력한 *위협 시뮬레이터* 툴과 최종 사용자 메트릭에 액세스할 수 있습니다.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Office 365용 Microsoft Defender 플랜 1 대 플랜 2 치트 시트

이 빠른 참조는 각 Office 365용 Defender 구독과 함께 제공되는 기능을 이해하는 데 도움이 됩니다. 이 빠른 참조가 EOP 기능에 대한 지식과 결합될 경우, 비즈니스 의사 결정자가 자신의 요구에 가장 적합한 Office 365용 Microsoft Defender를 결정하는 데 도움이 될 수 있습니다.

|Office 365용 Defender 플랜 1|Office 365용 Defender 플랜 2|
|---|---|
|구성, 보호 및 검색 기능: <ul><li>[안전한 첨부 파일](safe-attachments.md)</li><li>[안전한 링크](safe-links.md)</li><li>[SharePoint, OneDrive 및 Microsoft Teams용 안전한 첨부 파일](mdo-for-spo-odb-and-teams.md)</li><li>[Office 365용 Defender의 피싱 방지 보호 기능](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[실시간 감지](threat-explorer.md)</li></ul>|Office 365용 Defender 플랜 1 기능 <p> --- 추가 --- <p> 자동화, 조사, 수정 및 교육 기능: <ul><li>[위협 트래커](threat-trackers.md)</li><li>[위협 탐색기](threat-explorer.md)</li><li>[자동화된 조사 및 응답](office-365-air.md)</li><li>[공격 시뮬레이션 교육](attack-simulation-training.md)</li></ul>|
|

- Office 365용 Microsoft Defender 플랜 2는 Office 365 E5, Office 365 A5 및 Microsoft 365 E5에 포함되어 있습니다.

- Office 365용 Microsoft Defender 플랜 1은 Microsoft 365 Business Premium에 포함되어 있습니다.

- Office 365용 Microsoft Defender 플랜 1과 Office365용 Defender 플랜 2를 각각 특정 구독의 추가 기능으로 사용할 수 있습니다. 자세한 내용은 여기 제시된 또 다른 링크 [Office 365용 Microsoft Defender 플랜의 기능 가용성](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)을 참조하세요.

- [안전한 문서](safe-docs.md) 기능은 Microsoft 365 E5 또는 Microsoft 365 E5 보안 라이선스가 있는 사용자만 사용할 수 있습니다. (Office 365용 Microsoft Defender 플랜에는 미포함)

- 현재 구독에 Office 365용 Microsoft Defender가 포함되는 것을 원하지 않는 경우 [영업 팀에 문의하여 평가판을 시작하고](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)조직에서 Microsoft Office 365용 Defender를 사용할 수 있는 방법을 찾아보세요.

> [!TIP]
> ***내부자 팁** _. docs.microsoft.com 목차를 사용하여 EOP 및 Office 365용 Microsoft Defender에 대해 알아볼 수 있습니다. [Office 365 보안 개요](index.yml) 페이지로 돌아가면 사이드 바에 목차 구성이 표시됩니다. 이 목차는 배포(마이그레이션 포함)로 시작하여 방지, 검색, 조사 및 응답으로 이어집니다. <p> 이 구조는 여러 항목으로 나누어져 있으며_ *보안 관리** 항목 뒤에 **보안 작업** 항목이 나옵니다. 두 가지 업무 역할 중 하나에 대한 새로운 구성원 인 경우 이 팁의 링크와 목차에 대한 지식을 사용하여 공간에 대해 배우는 데 도움을 얻으세요. 이동하면서 *의견 링크* 를 사용하고 *문서를 평가* 하는 것을 잊지 마세요. 피드백은 제공 서비스를 개선하는 데 도움이 됩니다.

## <a name="where-to-go-next"></a>관련 내용 확인 위치

보안 관리자인 경우 메일에 대해 DKIM 또는 DMARC를 구성해야 할 수 있습니다. 우선 순위 사용자를 위해 '엄격한'보안 사전 설정을 배포하거나 제품의 새로운 기능을 찾으려고 할 수 있습니다. 또는 보안 작업을 사용하는 경우 실시간 감지 또는 위협 탐색기를 활용하여 조사 및 대응하거나 공격 시뮬레이터로 최종 사용자 감지 기능을 교육할 수 있습니다. 어느 쪽이든 다음에 살펴볼 사항에 대해 몇 가지 추가 권장 사항이 있습니다.

[SPF, DKIM 및 DMARC를 포함한 전자 메일 인증(세 가지 설정 링크 포함)](email-validation-and-authentication.md)

[특정한 권장 '골든' 구성을 확인](recommended-settings-for-eop-and-office365.md) 및 [권장 사전 설정 기능을 사용하여 보안 정책을 신속하게 구성](preset-security-policies.md)

[Office 365용 Microsoft Defender의 새로운 기능(EOP 개발 포함)](whats-new-in-defender-for-office-365.md)확인

[위협 탐색기 또는 실시간 감지 기능 사용](threat-explorer.md)

공격 [시뮬레이션 교육 사용](attack-simulation-training.md)
