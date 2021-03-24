---
title: Office 365용 Microsoft Defender 평가
description: 평가 모드의 Office 365용 Defender는 맬웨어와 같은 판정을 기록하지만 메시지에 대해 행동하지 않는 Office 365 전자 메일 정책에 대한 Defender를 만듭니다.
keywords: Office 365, Office 365용 Microsoft Defender 평가, Office 365 평가, office 365, Microsoft Defender, ATP 평가
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2e97e510cbc3188f8cc6117c5d7bd1e1d23897eb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073247"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender 평가

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365 평가판이 공개 미리 보기에 있습니다. 이 미리 보기 버전은 서비스 수준 계약 없이 제공됩니다. 일부 기능은 지원되지 않을 수도, 기능이 제한될 수도 있습니다.

포괄적인 보안 제품 평가를 수행하면 업그레이드 및 구매에 대한 정보를 제공한 결정을 내리는 데 도움이 될 수 있습니다. 보안 제품의 기능을 사용해 보아 보안 운영 팀이 일상적인 작업에서 어떻게 도움을 줄 수 있는지 평가하는 데 도움이 됩니다.

[Microsoft Defender for Office 365](defender-for-office-365.md) 평가 환경은 장치 및 환경 구성의 복잡하지 않습니다. 따라서 Office 365용 Microsoft Defender의 기능을 평가하는 데 집중할 수 있습니다. 평가 모드에서는 MX 레코드를 Microsoft를 설정하지 않고 Exchange Online 사서함으로 전송된 모든 메시지를 평가할 수 있습니다. 이 기능은 Word, SharePoint 또는 Teams와 같은 Office 클라이언트에는 적용되지 않는 전자 메일 보호에만 적용됩니다.

Office 365용 Microsoft Defender를 지원하는 라이선스가 아직 없는 경우 [무료 30일](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) 평가를 시작하고 Office 365 보안 및 준수 센터( & 테스트할 수 https://protection.office.com/homepage) 있습니다. 빠른 설치를 즐길 수 있으며 필요한 경우 쉽게 해제할 수 있습니다.

## <a name="how-the-evaluation-works"></a>평가 작동 방식

평가 모드의 Office 365용 Defender는 맬웨어와 같은 판정을 기록하지만 메시지에 대해 행동하지 않는 Office 365 전자 메일 정책에 대한 Defender를 만듭니다. MX 레코드 구성을 변경할 필요는 없습니다.

평가 모드에서는 [안전](safe-attachments.md)첨부 파일, [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)  [안전한](safe-links.md)링크 및 사서함 인텔리전스 기반 가장 정책이 사용자 대신 설정됩니다. 모든 Defender for Office 365 정책은 백그라운드에서 적용되지 않은 모드로 만들어지며 표시되지 않습니다.

설치의 일부로 평가 모드는 커넥터에 대한 향상된 [필터링도 구성합니다.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) IP 주소 및 보낸 사람 정보를 보존하여 필터링 정확도를 향상시킵니다. 그렇지 않으면 메일이 Office 365용 Defender 앞에 있는 ESG(전자 메일 보안 게이트웨이)를 통과할 때 손실됩니다. 커넥터에 대한 향상된 필터링은 기존 EOP(Exchange Online Protection) 스팸 방지 및 피싱 방지 정책에 대한 필터링 정확도도 향상시킵니다.

사용 커넥터에 대해 향상된 필터링을 사용하면 필터링 정확도가 향상되지만 Office 365용 Defender 앞에 ESG가 있으며 현재 EOP 필터링을 무시하지 않는 경우 특정 메시지의 결과물이 변경될 수 있습니다. 영향은 EOP 정책으로 제한됩니다. 평가의 일부로 MDO 정책 설정은 적용되지 않은 모드로 만들어집니다. 잠재적인 프로덕션 영향을 최소화하기 위해 SCL(스팸 지수)을 -1로 설정하는 전송 규칙을 만들어 모든 EOP 필터링을 무시할 수 있습니다. 자세한 [내용은 EAC를 사용하여 메시지의 SCL을](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)설정하는 메일 흐름 규칙   만들기를 참조합니다.

평가 모드를 설정하면 정책이 구현된 경우 차단될 메시지를 수량화하는 최대 90일의 데이터로 매일 보고서가 업데이트됩니다(예: 삭제, 정크 메일 보내기, 검지). Office 365 및 EOP 검색에 대한 모든 Defender에 대한 보고서가 생성됩니다. 검색 기술(예: 가장)별로 집계되어 시간 범위별로 필터링할 수 있습니다. 또한 주문형 메시지 보고서를 만들어 사용자 지정 피벗을 만들거나 위협 탐색기를 사용하여 심층 분석 메시지를 만들 수 있습니다.

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

Office 365용 Microsoft Defender에 대한 평가판 라이선스를  획득하려면 청구 관리자 역할 또는 전역 관리자 **역할이 필요합니다.** 전역 관리자 역할이 있는 사람에게 권한을 요청합니다. [구독 및 라이선스에 대한 자세한 내용은](../../commerce/licenses/subscriptions-and-licenses.md)

적절한 역할이 있는 경우 청구 서비스 구매로 > Microsoft 365 관리 센터에서 Microsoft Defender for Office 365용 Microsoft Defender(계획 2)에 대한 평가판 라이선스를 얻는 것이 좋습니다. 평가판에는 25개 라이선스에 대한 30일 무료 평가판이 포함되어 있습니다. [Office 365용 Microsoft Defender 평가판(계획 2)을 다운로드합니다.](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

고급 위협을 모니터링하고 보고하는 평가가 있는 30일 기간이 있습니다. Office 365용 전체 Defender 기능을 원하는 경우 유료 구독을 구입할 수도 있습니다.

### <a name="roles"></a>역할

**평가 모드에서** Office 365용 Defender를 설정하려면 Exchange Online 역할이 필요합니다. Microsoft 365 규정 준수 또는 보안 관리자 역할 할당은 작동하지 않습니다.

- [Exchange Online의 사용 권한에 대해 자세히 알아보기](/exchange/permissions-exo/permissions-exo)
- [관리자 역할 할당에 대해 자세히](../../admin/add-users/assign-admin-roles.md)

다음 역할이 필요합니다.

|작업 |역할(Exchange Online)|
|---|---|
|무료 평가판 다운로드 또는 Office 365용 Microsoft Defender 구입(계획 2)|청구 관리자 역할 또는 전역 관리자 역할|
|평가 정책 만들기|원격 및 허용 도메인 역할 보안 관리자 역할|
|평가 정책 편집|원격 및 허용 도메인 역할 보안 관리자 역할|
|평가 정책 삭제|원격 및 허용 도메인 역할 보안 관리자 역할 |
|평가 보고서 보기|보안 관리자 역할 또는 보안 읽기 관리자 역할|
|

### <a name="enhanced-filtering"></a>향상된 필터링

대량 및 스팸 방지와 같은 Exchange Online Protection 정책은 동일하게 유지됩니다. 그러나 이 평가에서는 커넥터에 대한 향상된 필터링이 설정되어 우회하지 않는 한 메일 흐름 및 Exchange Online Protection 정책에 영향을 줄 수 있습니다.

커넥터에 대한 향상된 필터링을 통해 테넌트는 스푸핑 방지 보호 기능을 사용할 수 있습니다. ESG(전자 메일 보안 게이트웨이)를 사용하는 경우 커넥터에 대한 향상된 필터링을 설정하지 않은 경우 스푸핑 방지가 지원되지 않습니다.

### <a name="urls"></a>URL

메일 흐름 중에 URL이 확인됩니다. 특정 URL을 검색하지 못하게 하려는 경우 허용된 URL 목록을 적절하게 관리합니다. 자세한 [내용은 테넌트 허용/차단 목록](tenant-allow-block-list.md) 관리를 참조하세요.

전자 메일 메시지 본문의 URL 링크는 고객 영향을 줄이지 않습니다.

### <a name="email-routing"></a>전자 메일 라우팅

메일을 라우팅하는 인바운드 커넥터의 이름을 포함하여 전자 메일이 현재 라우팅되는 방법을 설정하는 데 필요한 해당 세부 정보를 준비합니다. Exchange Online Protection만 사용하는 경우 커넥터가 없습니다.  [메일 흐름 및 전자 메일 라우팅에 대해 자세히](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

지원되는 전자 메일 라우팅 시나리오는 다음과 같습니다.

- **타사 파트너 및/또는** 사내 서비스 공급자: 평가하려는 인바운드 커넥터는 타사 공급자를 사용하고/ 또는 전자 메일 보안에 대한 솔루션을 사용 중입니다.
- **Microsoft Exchange Online 보호만:** 평가하려는 테넌트는 전자 메일 보안에 Office 365를 사용하며 MX(메일 교환) 레코드는 Microsoft를 지점으로 합니다.

### <a name="email-security-gateway"></a>전자 메일 보안 게이트웨이

타사 ESG(전자 메일 보안 게이트웨이)를 사용하는 경우 공급자의 이름을 알아야 합니다. ESG를 사용하는 경우 ESG를 사용하는 경우 장치의 공용 IP 주소(es)를 알아야 합니다.

지원되는 타사 파트너는 다음과 같습니다.

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- 소포스
- Symantec
- Trend Micro

### <a name="scoping"></a>겹치기

평가 범위를 인바운드 커넥터로 제한할 수 있습니다. 커넥터가 구성되지 않은 경우 관리자는 평가 범위를 통해 테넌트의 모든 사용자로부터 데이터를 수집하여 Office 365용 Defender를 평가할 수 있습니다.

## <a name="get-started-with-the-evaluation"></a>평가 시작

Office 365 보안 및 준수 센터에서 Microsoft Defender for Office 365 평가판 &(3개의 액세스 https://protection.office.com/homepage) 지점에서 찾을 수 있습니다.

- 대시보드에서 > 관리
- 위협 관리 > 정책
- 보고서 > 대시보드

## <a name="setting-up-the-evaluation"></a>평가 설정

평가에 대한 설정 흐름을 시작하면 두 가지 라우팅 옵션이 제공됩니다. 조직의 메일 라우팅 설정 및 평가 요구에 따라 타사 및/또는 사내 서비스 공급자를 사용할지 아니면 서비스 공급자만 사용할지 Microsoft Exchange Online.

- 타사 파트너 및/또는 사내 서비스 공급자를 사용하는 경우 드롭다운 메뉴에서 공급업체 이름을 선택해야 합니다. 다른 커넥터 관련 세부 정보를 제공합니다.

- MX 레코드가 Microsoft를 Microsoft Exchange Online Exchange Online 사서함이 있는 경우 이 옵션을 선택합니다.

설정을 검토하고 필요한 경우 편집합니다. 그런 다음 평가 **만들기를 선택합니다.** 설정이 완료된 것을 나타내는 확인 메시지가 표시됩니다.

Office 365용 Microsoft Defender 평가 보고서는 매일 한 번 생성됩니다. 데이터가 채워지는 데 최대 24시간이 걸릴 수 있습니다.

### <a name="exchange-rules-optional"></a>Exchange 규칙(선택 사항)

기존 게이트웨이가 있는 경우 평가 모드를 사용하도록 설정하면 커넥터에 대한 향상된 필터링이 활성화됩니다. 그러면 수신되는 보낸 사람 IP 주소를 변경하여 필터링 정확도가 향상됩니다. 이 경우 필터 판정이 변경될 수 있으며 Exchange Online Protection을 무시하지 않는 경우 특정 메시지에 대한 배달성이 변경될 수 있습니다. 이 경우 필터링을 일시적으로 무시하여 영향을 분석할 수 있습니다. 우회하려면 Exchange 관리 센터로 이동하여 SCL -1의 정책을 생성합니다(아직 없는 경우). 규칙 구성 요소 및 규칙의 작동 방식에 대한 자세한 내용은 Exchange Online의 메일 흐름 규칙(전송 규칙)을 참조하세요.

## <a name="evaluate-capabilities"></a>기능 평가

평가 보고서가 생성된 후 조직의 전자 메일 및 공동 작업 작업 공간에서 식별된 고급 위협 링크, 고급 위협 첨부 파일 및 잠재적인 가장 수를 참조하세요.

평가판이 만료되면 90일 동안 보고서에 계속 액세스할 수 있습니다. 그러나 더 이상 정보를 수집하지 않습니다. 평가판이 만료된 후 Office 365용 Microsoft Defender를 계속 사용하려면 [Office 365용 Microsoft Defender 유료 구독(계획 2)을](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)구입해야 합니다.

설정으로 **이동하여** 라우팅을 업데이트하거나 평가를 해제할 수 있습니다. 그러나 끄고 나서 평가를 계속하기로 결정한 경우 동일한 설정 프로세스를 다시 진행해야 합니다.

## <a name="provide-feedback"></a>피드백 제공

사용자 의견은 고급 공격으로부터 환경을 보호하는 데 도움이 됩니다. 제품 기능 및 평가 결과에 대한 경험과 노출을 공유합니다.

의견을  보내주세요.를 선택하여 의견을 보내주세요.