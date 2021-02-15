---
title: 데이터 개인 정보 규정이 적용된 정보 관리
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Microsoft 365 보존 레이블 및 정책을 사용하여 Microsoft 365 환경에서 개인 데이터를 관리합니다.
ms.openlocfilehash: c2a933e556213ae4b78db9dc5f903885df969b27
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377048"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>데이터 개인 정보 규정이 적용된 정보 관리

GDPR(일반 데이터 보호 규정), HIPAA-HITECH(미국 의료 개인 정보 보호법), 캘리포니아 소비자 보호법(CCPA) 및 브라질 데이터 보호법(LGPD)과 같은 데이터 개인 정보 보호 규정 준수 요구 사항을 해결하기 위해 사용자 환경에 정보 거버넌스 컨트롤을 사용할 수 있습니다. 

이러한 컨트롤은 주로 다음 솔루션 영역에 해당합니다.

- 보존 정책
- 보존 레이블
- 레코드 관리

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>정보 거버넌스 제어에 영향을 미치는 데이터 개인 정보 보호 규정

다음은 정보 거버넌스 제어와 관련이 있을 수 있는 데이터 개인 정보 규정의 샘플 목록입니다.

- GDPR 문서(13)(2)(a)
- GDPR 문서(5)(1)(f)
- HIPAA-HITECH(45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH(45 CFR 164.316(b)(1)(ii))
- LGPD 문서 46

이러한 규정에 대한 자세한 내용은 데이터 개인 정보 보호 위험 평가를 참조하고 [중요한 정보 문서를 식별합니다.](information-protection-deploy-assess.md)

정보 거버넌스에서 데이터 개인 정보 규정은 일반적으로 다음을 요구합니다.

- Microsoft 365에 저장된 개인 데이터의 보존 및 삭제를 위한 기술 체계를 사용해야 합니다.
- 개인 데이터를 저장하는 경우 데이터 저장 기간(현재 프런트 엔드 웹 시스템에서 표준 사례)을 주제에 알릴 수 있습니다.
- 확인 가능한 방법을 사용하여 실수로 처리, 손실 또는 변경되지 않도록 개인 데이터를 보호해야 합니다.
- 개인 데이터에 대해 실행되는 모든 작업은 문서화되고 해당 문서는 지정된 기간 동안 보존해야 합니다.

데이터 개인 정보 규정은 데이터 보존 및 삭제와 관련되어 매우 구체적인 것이 아니기 때문에 Microsoft 365 구독에 저장된 개인 정보에 대한 정보 거버넌스 지침을 규정할 수 있는 다른 요인을 고려해야 합니다. 다음은 몇 가지 예입니다.

- 5년 동안 비활성한 후 소비자 계정이 사용되지 않고, 해당 시점 이후에 계정 데이터를 삭제 또는 비유해야 하여 알림 및 기타 자동화와 관련된 데이터와 워크플로를 저장하는 시스템 간의 오케스트레이션이 필요합니다.
- GDPR과 관련된 정책 및 절차를 3년 동안 유지하도록 규칙을 구성하여 정책 및 절차에 대한 조직의 보존 일정에 부합합니다.
- 지원 조직을 통해 소비자와 통신하기 위한 별도의 구독 유지 관리 모든 전자 메일 통신은 시스템의 개인 정보 부채 빌드를 줄이기 위해 2주 후에 보존 및 삭제되었습니다.

답변할 주요 질문은 다음입니다. 

- 개인 데이터를 포함하는 정보는 "계속 보관" 관행을 피하기 위해 유효한 비즈니스상의 이유로 유지해야 하는 기간은 얼마나 하나요? 이는 비즈니스 연속성을 위한 보존 요구와 균형을 맞출 수 있어야 합니다.

개인 정보를 보관하거나 삭제하는 법적 및 비즈니스 이유에 관계없이 Microsoft는 Microsoft 365에서 데이터 거버넌스 체계를 구현하는 다양한 기능을 제공합니다.

## <a name="managing-information-governance-in-microsoft-365"></a>Microsoft 365에서 정보 거버넌스 관리

시작은 Microsoft [](../compliance/manage-information-governance.md) [365에서](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)정보 거버넌스 및 데이터 보존, 삭제 및 폐기 관리를 참조하세요.

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>컨테이너, 전자 메일 및 콘텐츠에 대한 데이터 보존 일정 개발

다음 사항에 유의해야 합니다.

- 정의된 정보 유형에 대한 데이터 보존 일정을 설정하는 것이 보존 또는 삭제 체계를 구현하기 위한 선행 요구 사항은 고려되어야 합니다.

- 대부분의 조직에서 중요하게 고려하는 정보 유형과 그와 함께 수행되는 해당 큰 레코드 보존 일정의 수를 고려할 때 데이터 보존 및 레코드 관리 전략을 구현하려면 계획이 필요합니다. 

- 이 유형의 효과적인 데이터 거버넌스 전략을 설정하는 핵심은 보다 공식적인 관리가 필요한 가장 우선 순위가 높은 비즈니스 기능 및 정보 유형에 중점을 두는 것입니다. 법적 계약서, 재무 제표 및 규정 준수 설명서를 예로 들 수 있습니다. 모든 단일 정보 유형에 대해 별도의 보존 일정을 설정하지 않도록 합니다. 예를 들어 일반 비즈니스 콘텐츠에 대한 보존 일정을 7년으로 설정하는 등 일반적인 범주를 최대한 활용해 보아야 합니다.

- 사용자 환경의 개인 정보 유형을 더 잘 알 수 있는 경우 이러한 유형의 콘텐츠에 대한 보존 및 삭제 일정을 설정하고 정보 아키텍처를 조정하여 이러한 종류의 정보를 보다 쉽게 관리합니다. 예를 들어 제어된 액세스로 개별 사이트, 라이브러리 또는 폴더에서 개인 정보를 격리합니다.

### <a name="retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블

보존 [정책 및 보존](../compliance/retention.md) 레이블을 사용하여 개인 데이터를 포함하거나 포함할 것으로 예상되는 Microsoft 365의 콘텐츠를 보존하거나 삭제합니다.

### <a name="records-management"></a>레코드 관리

Microsoft 365에서 데이터에 대한 레코드 [](../compliance/records-management.md) 관리 솔루션을 구현하기 위해 레코드를 선언하는 보존 레이블을 사용하세요.

데이터 개인 정보 보호를 위해 법률 부서에서 받은 DSRS(데이터 주체 요청)는 기록으로 선언되고 규정 활동 보존 사양을 준수하기 위해 무기한 또는 증명으로 삭제될 수 있습니다.

