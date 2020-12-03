---
title: Microsoft Defender for Office 365 평가
description: Defender for Office 365 for evaluation mode는 맬웨어 같은 verdicts를 기록 하지만 메시지에는 작동 하지 않는 Office 365 전자 메일 정책에 대 한 Defender를 만듭니다.
keywords: office 365, Microsoft Defender for Office 365, office 365 evaluation, office 365, Microsoft Defender, ATP 체험
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 12b6499822f8ed97ace8468054f219361d925332
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562997"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 평가

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

>[!IMPORTANT]
>Office 2013에 대 한 Microsoft Defender가 곧 공개 될 예정입니다. 365이 미리 보기 버전은 서비스 수준 계약 없이 제공 됩니다. 특정 기능은 지원 되지 않거나 제한 된 기능을 포함할 수 있습니다.

포괄적인 보안 제품 평가를 수행 하면 업그레이드 및 구매에 대 한 의사 결정을 내리는 데 도움이 됩니다. 이를 통해 보안 제품의 기능을 사용해 일상적인 작업을 수행 하는 데 보안 운영 팀이 어떻게 도움이 되는지 평가할 수 있습니다.

[Microsoft Defender For Office 365](office-365-atp.md) 평가 환경은 보안 솔루션의 기능 평가에 집중할 수 있도록 장치 및 환경 구성의 복잡성을 없애기 위해 설계 되었습니다. SharePoint, Office 클라이언트 또는 팀이 아닌 전자 메일 보호에만 적용 됩니다.

Office 365 용 Microsoft Defender를 지 원하는 라이선스가 아직 없는 경우에는 [30 일 무료 평가판](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) 을 시작 하 고 Office 365 보안 & 준수 센터 ()에서 기능을 테스트할 수 있습니다 https://protection.office.com/homepage) . 빠른 설정을 사용 하 고 필요한 경우 쉽게 해제할 수 있습니다.

## <a name="how-the-evaluation-works"></a>평가 작동 방식

Defender for Office 365 for evaluation mode는 맬웨어 같은 verdicts를 기록 하지만 메시지에는 작동 하지 않는 Office 365 전자 메일 정책에 대 한 Defender를 만듭니다. MX 레코드 구성을 변경할 필요는 없습니다.

평가 모드, [안전한 첨부 파일](atp-safe-attachments.md), [안전한 링크](atp-safe-links.md)및 [피싱 방지 가장 정책이](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 사용자 대신 설치 됩니다. 모든 Defender for Office 365 정책은 백그라운드에서 강요 되지 않음 모드로 만들어지고 사용자에 게 표시 되지 않습니다.

설치 과정의 일부로 평가 모드는 [커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)도 구성 합니다. Office 365의 Defender 앞에 있는 ESG (전자 메일 보안 게이트웨이)를 통해 메일이 전달 될 때 손실 되는 IP 주소 및 보낸 사람 정보를 유지 하 여 필터링 정확도를 향상 시킵니다. 또한 EOP (Exchange Online Protection) 스팸 방지 및 피싱 방지 정책에 대 한 필터링 정확성이 향상 됩니다.

일부 지원 되지 않는 시나리오에 대 한 잠재적 프로덕션 영향을 최소화 하기 위해 SCL (스팸 지 수)을-1로 설정 하는 전송 규칙을 만들어 모든 EOP 필터링을 무시할 수 있습니다. 자세한 내용은 [EAC를 사용 하 여 메시지의 SCL을 설정 하는 메일 흐름 규칙 만들기를](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)참조 하십시오   .

평가 모드를 설정 하면 매일 보고서가 업데이트 되 고 (예: 삭제, 정크로 보내기, 격리) 정책이 적용 되어 구현 된 것으로 차단 된 메시지를 수량화 하는 데이터를 최대 90 일까지 정량화 합니다. 모든 Defender for Office 365 및 EOP 검색에 대 한 보고서가 생성 됩니다. 이러한 사용자는 검색 기술에 따라 집계 되며 (예: 가장) 시간 범위를 기준으로 필터링 할 수 있습니다. 또한 메시지 보고서를 주문형으로 만들어 사용자 지정 피벗을 만들거나 위협 탐색기를 사용 하 여 메시지를 자세히 작성할 수 있습니다.

간단한 설정 환경에서는 다음에 집중할 수 있습니다.

- 평가 실행
- 자세한 보고서 가져오기
- 작업에 대 한 보고서 분석
- 평가 결과 발표

## <a name="before-you-begin"></a>시작하기 전에

### <a name="licensing"></a>라이선싱

평가에 액세스 하려면 라이선스 요구 사항을 충족 해야 합니다. 다음 라이선스 중 하나를 사용할 수 있습니다.

- Microsoft Defender for Office 365 계획 1
- Microsoft Defender for Office 365 계획 2
- Microsoft 365 E5, Microsoft 365 E5 보안
- Office 365 E5

이러한 라이선스 중 하나가 없으면 평가판 라이선스를 취득 해야 합니다.

#### <a name="trial"></a>평가판

Microsoft Defender for Office 365에 대 한 평가판 라이선스를 취득 하려면 **청구 관리자 역할** 또는 **전역 관리자 역할이** 있어야 합니다. 전역 관리자 역할이 있는 사용자의 권한을 요청 합니다. [구독 및 라이선스에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

적절 한 역할을 수행한 후에는 Microsoft 365 관리 센터에서 Office 365 (요금제 2)에 대 한 Microsoft Defender에 대 한 평가판 라이선스를 취득 하는 것이 좋습니다 > Purchase service로 이동 하는 것입니다. 평가판에는 25 개 라이선스에 대 한 30 일 무료 평가판이 포함 되어 있습니다. [Microsoft Defender For Office 365 (요금제 2)에 대 한 평가판을 받습니다](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA). 

최종 위협에 대 한 모니터링 및 보고를 위한 평가와 함께 30 일의 기간을 갖게 됩니다. 또한 전체 Defender for Office 365 기능을 원하는 경우 유료 구독을 구입 하는 옵션도 제공 됩니다.

### <a name="roles"></a>역할

Exchange Online 역할은 평가 모드에서 Office 365 용 Defender를 설정 하는 데 필요 합니다. 필요한 역할은 다음과 같습니다.

|작업 | 역할 |
|-----| -----|
| 무료 평가판 받기 또는 Office 365 용 Microsoft Defender 구매 (요금제 2)| 청구 관리자 역할 또는 전역 관리자 역할|
| 평가 정책 만들기| 원격 및 허용 도메인 역할 보안 관리자 역할|
| 평가 정책 편집 | 원격 및 허용 도메인 역할 보안 관리자 역할 |
| 평가 정책 삭제 | 원격 및 허용 도메인 역할 보안 관리자 역할 |
|평가 보고서 보기 | 보안 관리자 역할 또는 보안 독자 역할|

### <a name="enhanced-filtering"></a>향상 된 필터링

대량 및 스팸 보호와 같은 Exchange Online 보호 정책이 동일 하 게 유지 됩니다. 또한 메시지 배달은 동일 하 게 유지 됩니다. 그러나 계산을 통해 커넥터에 대 한 향상 된 필터링이 설정 되므로 무시 되지 않으면 메일 흐름 및 Exchange Online 보호 정책에 영향을 줍니다.

커넥터에 대 한 향상 된 필터링을 통해 테 넌 트에서 스푸핑 방지 보호를 사용할 수 있습니다. 커넥터에 대 한 향상 된 필터링을 설정 하지 않고 ESG (전자 메일 보안 게이트웨이)를 사용 하는 경우에는 스푸핑 방지가 지원 되지 않습니다.

### <a name="urls"></a>URL

메일 흐름 중에 Url이 열 됩니다. 특정 Url을 열 않으려면 허용 되는 Url 목록을 적절 하 게 관리 합니다. 자세한 내용은 [테 넌 트 허용/차단 목록에서 Url 관리](tenant-allow-block-list.md) 를 참조 하세요.

고객의 영향을 줄이기 위해 전자 메일 메시지 본문의 URL 링크가 래핑 되지 않습니다.

### <a name="email-routing"></a>전자 메일 라우팅

메일을 라우팅하는 인바운드 커넥터의 이름을 비롯 하 여 전자 메일이 현재 라우팅되는 방법을 설정 하는 데 필요한 세부 정보를 준비 해야 합니다. Exchange Online Protection을 사용 하는 경우에는 커넥터가 없는 것입니다.  [메일 흐름 및 전자 메일 라우팅에 대 한 자세한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow) 정보

지원 되는 전자 메일 라우팅 시나리오는 다음과 같습니다.

- 타사 **파트너 및/또는 온-프레미스 서비스 공급자**: 평가 하려는 인바운드 커넥터는 타사 공급자를 사용 하거나 전자 메일 보안에 온-프레미스 솔루션을 사용 하 고 있습니다.  
- **Microsoft Exchange Online Protection 전용**: 평가 하려는 테 넌 트는 전자 메일 보안에 Office 365을 사용 하 고 MX (메일 교환) 레코드는 Microsoft를 가리킵니다.

### <a name="email-security-gateway"></a>전자 메일 보안 게이트웨이

타사 전자 메일 보안 게이트웨이 (ESG)를 사용 하는 경우 공급자의 이름을 알고 있어야 합니다. ESG 온-프레미스 또는 지원 되지 않는 공급 업체를 사용 하는 경우에는 장치에 대 한 공용 IP 주소를 알고 있어야 합니다.

지원 되는 타사 파트너는 다음과 같습니다.

- Barracuda
- Ironpor
- Mimecast
- Proofpoint
- Sophos
- Symantec
- 경향 마이크로

### <a name="scoping"></a>범위

인바운드 커넥터에 대 한 평가 범위를 지정할 수 있습니다. 커넥터를 구성 하지 않은 경우에는 평가 범위를 사용 하 여 관리자가 테 넌 트의 모든 사용자 로부터 데이터를 수집 하 여 Defender for Office 365을 평가할 수 있습니다.

## <a name="get-started-with-the-evaluation"></a>평가 시작

https://protection.office.com/homepage)다음 3 개의 액세스 포인트에서 office 365 Security & 준수 센터의 office 365 평가용 설정 카드를 찾습니다.

- 위협 관리 > 대시보드
- 위협 관리 > 정책
- 보고서 > 대시보드

## <a name="setting-up-the-evaluation"></a>평가 설정

평가를 위해 설정 흐름을 시작 하면 두 개의 라우팅 옵션이 제공 됩니다. 조직의 메일 라우팅 설정 및 평가 요구 사항에 따라 타사 및/또는 Microsoft Exchange Online만 사용 하 고 있는지 여부를 선택할 수 있습니다.

- 타사 파트너 및/또는 온-프레미스 서비스 공급자를 사용 하는 경우에는 드롭다운 메뉴에서 공급 업체의 이름을 선택 해야 합니다. 다른 커넥터 관련 정보를 제공 합니다.

- MX 레코드가 Microsoft를 가리키고 Exchange Online 사서함이 있는 경우 Microsoft Exchange Online을 선택 합니다.

설정을 검토 하 고 필요한 경우 편집 합니다. 그런 다음 **평가 만들기** 를 선택 합니다. 설정이 완료 되었음을 나타내는 확인 메시지가 표시 됩니다.

Microsoft Defender for Office 365 평가 보고서는 하루에 한 번 생성 됩니다. 데이터가 채워 차지 하는 데 최대 24 시간이 걸릴 수 있습니다.

### <a name="exchange-rules-optional"></a>Exchange 규칙 (선택 사항)

기존 게이트웨이가 있는 경우에는 커넥터에 대 한 향상 된 필터링을 활성화 하 고 들어오는 보낸 사람 IP 주소를 변경 하기 때문에 필터링을 무시할 수 있습니다. 무시 하려면 Exchange 관리 센터로 이동 하 여 SCL-1 정책 (아직 없는 경우)을 만듭니다. 규칙 구성 요소 및 해당 작동 방식에 대 한 자세한 내용은 Exchange Online의 메일 흐름 규칙 (전송 규칙)을 참조 하세요.

## <a name="evaluate-capabilities"></a>기능 평가

평가 보고서가 생성 된 후 조직의 전자 메일 및 공동 작업 영역에서 식별 된 advanced threat links, advanced threat attachments 및 잠재 impersonations의 수를 확인 합니다.  

평가판이 만료 되 면 계속 해 서 90 일 동안 보고서에 액세스할 수 있습니다. 그러나 더 이상 정보를 수집 하지 않습니다. 평가판이 만료 된 후에 Microsoft Defender for Office 365을 계속 사용 하려면 [Microsoft defender For office 365 (요금제 2)에 대해 유료 구독을 구입](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)해야 합니다.

**설정** 으로 이동 하 여 라우팅을 업데이트 하거나 언제 든 지 평가를 해제할 수 있습니다. 그러나 종료 후에도 평가를 계속 하기로 결정 했을 때와 동일한 설정 프로세스를 다시 진행 해야 합니다.

## <a name="provide-feedback"></a>피드백 제공

사용자 의견을 활용 하면 고급 공격 으로부터 환경을 보호 하는 데 도움이 됩니다. 사용자 환경 및 제품 기능 및 평가 결과의 상대를 공유 합니다.

**의견 제공** 을 선택 하 여 생각 하는 사항을 알려주세요.
