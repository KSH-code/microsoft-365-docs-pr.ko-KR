---
title: Office 365용 Microsoft Defender 평가
description: 평가 모드에서 Office 365 Defender는 맬웨어와 같은 Office 365 기록하지만 메시지에 대해 행동하지 않는 전자 메일 정책에 대한 Defender를 만듭니다.
keywords: 평가 Office 365 Microsoft Defender for Office 365, office 365 평가, office 365, Microsoft Defender, 끝점용 Microsoft Defender 평가
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ba60d7b9f677c653bb2d57760989aeb18a4a1e6
ms.sourcegitcommit: 6dbf879f769a825ed7039363f3a91d676e355ee0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60940551"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender 평가

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365 평가는 공개 미리 보기에 있습니다. 이 미리 보기 버전은 서비스 수준 계약 없이 제공됩니다. 특정 기능이 지원되지 않거나 기능이 제한될 수 있습니다.

철저한 보안 제품 평가를 수행하면 업그레이드 및 구매에 대한 정보를 제공한 결정을 내리는 데 도움이 될 수 있습니다. 보안 제품의 기능을 사용해 보아 보안 운영 팀이 일상적인 작업에서 어떻게 도움을 줄 수 있는지 평가하는 데 도움이 됩니다.

microsoft Defender for Office 365 평가 환경은 장치 및 환경 구성의 복잡한 문제를 없애기 위해 디자인되어 사용자에 대한 Microsoft [Defender의](defender-for-office-365.md) 기능을 평가하는 데 집중할 수 Office 365. 평가 모드에서는 MX 레코드가 Microsoft를 Exchange Online 사서함으로 전송된 모든 메시지를 평가할 수 있습니다. 이 기능은 전자 메일 보호에만 적용될 뿐Office Word, SharePoint 또는 Teams.

Microsoft Defender for Office 365 지원하는 라이선스가 없는 경우 [무료 30일](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) 평가를 시작하고 의 Microsoft 365 Defender 포털에서 기능을 테스트할 수 <https://security.microsoft.com> 있습니다. 빠른 설치를 즐길 수 있으며 필요한 경우 쉽게 해제할 수 있습니다.

> [!NOTE]
> Microsoft 365 Defender 포털()에 있는 경우 기타 섹션의 전자 메일 & 공동 작업 정책 & 규칙 위협 정책 평가 모드에서 Office 365 평가용 <https://security.microsoft.com> Defender를 시작할  \>  \>  \>  **수** 있습니다.

## <a name="how-the-evaluation-works"></a>평가 작동 방식

평가 모드에서 Office 365 Defender는 맬웨어와 같은 Office 365 기록하지만 메시지에 대해 행동하지 않는 전자 메일 정책에 대한 Defender를 만듭니다. MX 레코드 구성을 변경할 필요는 없습니다.

평가 모드에서는 금고 [첨부](safe-attachments.md) [파일,](safe-links.md)금고 링크 및 [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 사서함 인텔리전스를 대신하여 설정됩니다. 모든 Office 365 정책은 백그라운드에서 적용되지 않은 모드로 만들어지며 표시되지 않습니다.

또한 설치의 일부로 평가 모드는 커넥터에 대한 향상된 필터링(목록 건너뛰기라고도 _알려)을 구성합니다._ [](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) IP 주소 및 보낸 사람 정보를 보존하여 필터링 정확도를 향상시킵니다. 그렇지 않으면 메일이 ESG(전자 메일 보안 게이트웨이)를 통과할 때 전자 메일 주소 및 보낸 사람 정보가 Office 365. 또한 커넥터에 대한 향상된 필터링은 기존 EOP(스팸 방지) Exchange Online Protection 및 피싱 방지 정책에 대한 필터링 정확도를 향상시킵니다.

향상된 커넥터 필터링은 필터링 정확도를 향상시킵니다. 그러나 현재 EOP 필터링을 무시하지 않는 ESG가 Office 365 ESG가 있는 경우 특정 메시지에 대한 배달성이 변경될 수 있습니다. 영향은 EOP 정책으로 제한됩니다. 평가의 일부로 Office 365 정책에 대한 Defender가 적용되지 않은 모드로 만들어집니다. 잠재적인 프로덕션 영향을 최소화하기 위해 메일 흐름 규칙(전송 규칙)을 만들어 메시지의 SCL(스팸 지수)을 -1로 설정하여 대부분의 EOP 필터링을 무시할 수 있습니다. 자세한 [내용은 Use mail flow rules to set the spam confidence level (SCL) in messages in Exchange Online을](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)   참조하세요.

평가 모드를 설정하면 정책이 구현된 경우 차단될 메시지를 수량화하는 최대 90일의 데이터로 매일 보고서가 업데이트됩니다(예: 삭제, 정크 메일 보내기, 검지). 보고서는 모든 Defender 및 EOP Office 365 생성됩니다. 검색 기술(예: 가장)별로 집계되어 시간 범위별로 필터링할 수 있습니다. 또한 주문형 메시지 보고서를 만들어 사용자 지정 피벗을 만들거나 탐색기를 사용하여 심층 검색 메시지를 만들 수 있습니다.

간소화된 설정 환경을 통해 다음에 집중할 수 있습니다.

- 평가 실행
- 자세한 보고서 확인
- 작업 보고서 분석
- 평가 결과 발표

## <a name="before-you-begin"></a>시작하기 전에

### <a name="licensing"></a>라이선싱

평가에 액세스하려면 라이선스 요구 사항을 충족해야 합니다. 다음 라이선스 중 한 개가 작동됩니다.

- Office 365용 Microsoft Defender 플랜 1
- Office 365용 Microsoft Defender 플랜 2
- Microsoft 365 E5, Microsoft 365 E5 보안
- Office 365 E5

이러한 라이선스 중 하나만 있는 경우 평가판 라이선스를 얻어야 합니다.

#### <a name="trial"></a>평가판

Microsoft Defender for Office 365 평가판 라이선스를 얻기 위해  청구 관리자 역할 또는 전역 관리자 역할이 **필요합니다.** 전역 관리자 역할이 있는 사람에게 권한을 요청합니다. [구독 및 라이선스에 대한 자세한 내용은](../../commerce/licenses/subscriptions-and-licenses.md)

적절한 역할이 있는 경우 청구 서비스 구매로 Office 365(계획 2)에 대한 Microsoft Defender 평가판 Microsoft 365 관리 센터 라이선스를 > 것이 좋습니다. 평가판에는 25개 라이선스에 대한 30일 무료 평가판이 포함되어 있습니다. [Microsoft Defender for Office 365 평가판을 다운로드합니다(계획 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

고급 위협을 모니터링하고 보고하는 평가가 있는 30일 기간이 있습니다. 유료 구독의 전체 Defender 기능을 원하는 경우 유료 구독을 구입할 Office 365 있습니다.

### <a name="roles"></a>역할

**Exchange Online 역할은** 평가 모드에서 Office 365 설정하는 데 필요합니다. 규정 Microsoft 365 또는 보안 관리자 역할을 할당할 수 없습니다.

- [2016년 8월의 사용 권한에 Exchange Online](/exchange/permissions-exo/permissions-exo)
- [관리자 역할 할당에 대해 자세히](../../admin/add-users/assign-admin-roles.md)

다음 역할이 필요합니다.

<br>

****

|작업|역할(Exchange Online)|
|---|---|
|무료 평가판을 다운로드하거나 Microsoft Defender for Office 365 구입(계획 2)|청구 관리자 역할 또는 전역 관리자 역할|
|평가 정책 만들기|원격 및 허용 도메인 역할 보안 관리자 역할|
|평가 정책 편집|원격 및 허용 도메인 역할 보안 관리자 역할|
|평가 정책 삭제|원격 및 허용 도메인 역할 보안 관리자 역할 |
|평가 보고서 보기|보안 관리자 역할 또는 보안 읽기 관리자 역할|
|

### <a name="enhanced-filtering-for-connectors"></a>커넥터에 대한 향상된 필터링

대량 Exchange Online Protection 스팸 방지와 같은 정책은 동일하게 유지됩니다. 그러나 이 평가에서는 커넥터에 대한 향상된 필터링이 켜지며, 이 필터링은 무시하지 않는 한 메일 흐름 및 Exchange Online Protection 정책에 영향을 줄 수 있습니다.

커넥터에 대한 향상된 필터링을 통해 테넌트는 스푸핑 방지 보호를 사용할 수 있습니다. ESG(전자 메일 보안 게이트웨이)를 사용하는 경우 커넥터에 대한 향상된 필터링을 설정하지 않은 경우 스푸핑 방지가 지원되지 않습니다.

### <a name="urls"></a>URL

메일 흐름 중에 URL이 확인됩니다. 특정 URL을 검색하지 못하게 하려는 경우 허용된 URL 목록을 적절하게 관리합니다. 자세한 [내용은 테넌트 허용/차단 목록](tenant-allow-block-list.md) 관리를 참조하세요.

전자 메일 메시지 본문의 URL 링크는 고객 영향을 줄이지 않습니다.

### <a name="email-routing"></a>전자 메일 라우팅

메일을 라우팅하는 인바운드 커넥터의 이름을 포함하여 전자 메일이 현재 라우팅되는 방법을 설정하는 데 필요한 해당 세부 정보를 준비합니다. 이 두 가지 Exchange Online Protection 사용하는 경우 커넥터가 없습니다. [ 메일 흐름 및 전자 메일 라우팅에 대해 자세히](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

지원되는 전자 메일 라우팅 시나리오는 다음과 같습니다.

- **타사 파트너 및/또는** 사내 서비스 공급자: 평가하려는 인바운드 커넥터는 타사 공급자를 사용하고/ 또는 전자 메일 보안에 대한 솔루션을 사용 중입니다.
- **Microsoft Exchange Online 보호만:** 평가하려는 테넌트는 전자 메일 보안에 Office 365 사용하며 MX(메일 Exchange) 레코드가 Microsoft를 Exchange 합니다.

### <a name="email-security-gateway"></a>전자 메일 보안 게이트웨이

타사 ESG(전자 메일 보안 게이트웨이)를 사용하는 경우 공급자의 이름을 알아야 합니다. ESG를 사용하는 경우 ESG를 사용하는 경우 장치의 공용 IP 주소(es)를 알아야 합니다.

지원되는 타사 파트너는 다음과 같습니다.

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- 소포스
- Symantec
- 추세 Micro

### <a name="scoping"></a>겹치기

평가 범위를 인바운드 커넥터로 제한할 수 있습니다. 커넥터가 구성되지 않은 경우 평가 범위는 관리자가 테넌트에 있는 모든 사용자의 데이터를 수집하여 Defender에서 해당 커넥터를 평가할 수 Office 365.

## <a name="get-started-with-the-evaluation"></a>평가 시작

Microsoft 365 Defender 포털()에서 Office 365 평가용 Microsoft Defender 셋업 카드를 찾으면 다음 세 가지 <https://security.microsoft.com> 액세스 포인트에서 찾을 수 있습니다.

- **끝점** \> **취약성 관리** \> **대시보드(** <https://security.microsoft.com/tvm_dashboard> )
- **전자 메일 & 공동 작업** \> **정책 & 규칙** \> **위협 정책(** <https://security.microsoft.com/threatpolicy> )
- **보고서** \> **전자 메일 & 공동 작업** \> **전자 & 공동 작업 보고서(** <https://security.microsoft.com/emailandcollabreport> )

## <a name="setting-up-the-evaluation"></a>평가 설정

평가에 대한 설정 흐름을 시작하면 두 가지 라우팅 옵션이 제공됩니다. 조직의 메일 라우팅 설정 및 평가 요구에 따라 타사 및/또는 사내 서비스 공급자를 사용할지 아니면 서비스 공급자만 사용할지 Microsoft Exchange Online.

- 타사 파트너 및/또는 사내 서비스 공급자를 사용하는 경우 드롭다운 메뉴에서 공급업체 이름을 선택해야 합니다. 다른 커넥터 관련 세부 정보를 제공합니다.

- MX 레코드가 Microsoft를 Microsoft Exchange Online 사서함이 있는 경우 Exchange Online 선택합니다.

설정을 검토하고 필요한 경우 편집합니다. 그런 다음 평가 **만들기를 선택합니다.** 설정이 완료된 것을 나타내는 확인 메시지가 표시됩니다.

Microsoft Defender for Office 365 평가 보고서는 매일 한 번 생성됩니다. 데이터가 채워지는 데 최대 24시간이 걸릴 수 있습니다.

### <a name="exchange-mail-flow-rules-optional"></a>Exchange 흐름 규칙(선택 사항)

기존 게이트웨이가 있는 경우 평가 모드를 사용하도록 설정하면 커넥터에 대한 향상된 필터링이 활성화됩니다. 이 기능은 수신되는 보낸 사람 IP 주소를 변경하여 필터링 정확도를 향상시킵니다. 이 기능은 필터 판정을 변경할 수 있으며, 이 기능을 무시하지 않는 Exchange Online Protection 특정 메시지의 결과물이 변경될 수 있습니다. 이 경우 필터링을 일시적으로 무시하여 영향을 분석할 수 있습니다. 필터링을 무시하려면 에서 Exchange 관리 센터(EAC)를 열고 <https://admin.exchange.microsoft.com> 메시지의 SCL을 -1로 설정하는 메일 흐름 규칙을 만들 수 있습니다(아직 메시지 SCL이 없는 경우). 자세한 내용은 [Use mail flow rules to set the spam confidence level (SCL) in messages in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

## <a name="evaluate-capabilities"></a>기능 평가

평가 보고서가 생성된 후 조직의 전자 메일 및 공동 작업 작업 공간에서 식별된 고급 위협 링크, 고급 위협 첨부 파일 및 잠재적인 가장 수를 참조하세요.

평가판이 만료되면 90일 동안 보고서에 계속 액세스할 수 있습니다. 그러나 더 이상 정보를 수집하지 않습니다. 평가판이 만료된 Office 365 Microsoft Defender를 계속 사용하려면 Microsoft Defender for Office 365 유료 구독을 구입해야 [합니다(계획 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

사용자 로 이동하여 **설정** 업데이트하거나 평가를 해제할 수 있습니다. 그러나 끄고 나서 평가를 계속하기로 결정한 경우 동일한 설정 프로세스를 다시 진행해야 합니다.

## <a name="provide-feedback"></a>피드백 제공

사용자 의견은 고급 공격으로부터 환경을 보호하는 데 도움이 됩니다. 제품 기능 및 평가 결과에 대한 경험과 노출을 공유합니다.

의견을  보내주세요.를 선택하여 의견을 보내주세요.
