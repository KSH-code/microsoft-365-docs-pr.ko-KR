---
title: 데이터 개인 정보 규정의 영향을 받는 정보 제어
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
ms.custom: ''
description: Microsoft 365 보존 레이블 및 정책을 사용 하 여 Microsoft 365 환경에서 개인 데이터를 관리 합니다.
ms.openlocfilehash: a7a0d6e00d29d80dfd0cb72ba217177aa6029a2c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522304"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>데이터 개인 정보 규정의 영향을 받는 정보 제어

정보 거 버 넌 스에서 일반 데이터 보호 규정 (GDPR), HIPAA-HITECH (미국 의료 보험 개인 정보 취급 방침), 캘리포니아 주 보호 Act (CCPA) 및 LGPD (브라질 Data Protection Act)와 관련 된 번호를 포함 하 여 데이터 개인 정보 규정 준수 요구 사항을 해결 하는 데 도움이 되도록 사용자 환경에서 사용할 수 있습니다. 

이러한 컨트롤은 주로 다음 솔루션 영역에 속합니다.

- 보존 정책
- 보존 레이블
- 레코드 관리

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>정보 거 버 넌 스 제어에 영향을 주는 데이터 개인 정보 규정

다음은 정보 거 버 넌 스 컨트롤과 관련이 있을 수 있는 데이터 개인 정보 규정의 예입니다.

- GDPR 문서 (13) (a)
- GDPR 문서 (5) (1) (f)
- HIPAA-HITECH (45 CFR 164.312 (2))
- HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))
- HIPAA-HITECH (45 CFR 164.316 (b) (1) (ii))
- LGPD 문서 46

이러한 규정에 대 한 자세한 내용은 [데이터 개인 정보 보호 위험 평가 및 중요 한 정보 식별 문서](information-protection-deploy-assess.md)를 참조 하세요.

정보 관리를 위해 일반적으로 데이터 개인 정보 규정은 다음을 호출 합니다.

- Microsoft 365에 저장 된 개인 데이터에 대 한 보존 및 삭제를 위한 기술 체계를 사용 해야 합니다.
- 개인 데이터를 저장 하려는 경우에는 프런트 엔드 웹 시스템에서의 표준 관행 인 데이터가 저장 되는 기간을 알려 주어 야 합니다.
- 개인 데이터는 안정형 메서드를 사용 하 여 실수로 처리, 손실 또는 변경 으로부터 보호 해야 합니다.
- 개인 데이터에 대해 실행 되는 모든 작업을 문서화 하 고 지정 된 기간 동안 문서를 보존 해야 합니다.

데이터 개인 정보 규정은 데이터 보존 및 삭제와 관련 하 여 특정 하지 않으므로 Microsoft 365 구독에 저장 된 개인 정보에 대 한 정보 거 버 넌 스 지침을 지시할 수 있는 다른 요인을 고려해 야 합니다. 몇 가지 예는 다음과 같습니다.

- 5 년 동안 사용 하지 않으면 소비자 계정을 에이징 아웃 하 고, 해당 시점 이후 계정 데이터를 삭제 하거나 익명화 시스템 간에 오케스트레이션을 필요한 경우에는 알림 및 기타 자동화와 관련 된 데이터와 워크플로를 저장 합니다.
- 정책 및 절차에 대 한 조직의 보존 일정에 맞게 대체 된 3 년 동안 GDPR과 관련 된 정책 및 절차를 유지 하기 위한 규칙을 구성 합니다.
- 지원 조직을 통해 소비자와 통신 하기 위한 별도의 구독 유지 관리 모든 전자 메일 통신은 시스템의 개인 정보 부채 변환 하려면 buildup를 줄이기 위해 2 주 후에 유지 및 삭제 되었습니다.

대답이 다음과 같은 주요 질문입니다. 

- 개인 데이터를 포함 하는 정보를 보관 하는 데 걸리는 시간이 유효한 비즈니스 이유로 "영구적으로 유지" 되지 않도록 해야 하는 경우 이는 비즈니스 연속성에 대 한 보존 요구와 균형을 유지 해야 합니다.

Microsoft는 개인 정보를 유지 하거나 삭제 하는 법적 및 비즈니스 이유에 관계 없이 Microsoft 365에서 데이터 거 버 넌 스 체계를 구현 하기 위한 다양 한 기능을 제공 합니다.

## <a name="managing-information-governance-in-microsoft-365"></a>Microsoft 365에서 정보 거 버 넌 스 관리

시작 하려면 Microsoft 365에서 [정보 거 버 넌 스](../compliance/manage-information-governance.md) 및 [데이터 보존, 삭제 및 소멸](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)관리를 참조 하세요.

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>컨테이너, 전자 메일 및 콘텐츠에 대 한 데이터 보존 일정 개발

다음 사항에 유의해야 합니다.

- 정의 된 정보 유형에 대 한 데이터 보존 일정을 설정 하는 것은 보존 또는 삭제 체계를 구현 하기 위한 필수 구성 요소입니다.

- 대부분의 조직에서 중요 하 게 고려 하 고 해당 하는 대규모 레코드 보존 일정과 함께 이동 하는 정보 유형 수가 제공 되 면 데이터 보존 및 레코드 관리 전략을 구현 하려면 계획이 필요 합니다. 

- 이 유형의 효과적인 데이터 거 버 넌 스 전략을 설정 하는 것은 보다 높은 우선 순위 비즈니스 기능과 공식적인 관리를 요구 하는 정보 유형을 중점적으로 설명 하기 위한 것입니다. 법적 계약, 금융 명세서 및 규정 준수 설명서를 예로 들 수 있습니다. 모든 단일 정보 유형에 별도의 보존 일정을 사용 하지 않도록 합니다. 일반 비즈니스 콘텐츠에 대 한 7 년간의 보존 일정을 사용 하는 등의 방법으로 일반 범주를 가능한 한 많이 활용 하십시오.

- 환경의 개인 정보 유형을 더 잘 알고 있으면 이러한 유형의 콘텐츠에 대 한 보존 및 삭제 일정을 설정 하 고 정보 아키텍처를 조정 하 여 이러한 유형의 정보를 보다 쉽게 관리할 수 있도록 합니다. 예를 들어 개인 정보를 제어 된 액세스 권한이 있는 별도의 사이트, 라이브러리 또는 폴더에 격리 합니다.

### <a name="retention-policies"></a>보존 정책

자동으로 적용 되는 사이트의 콘텐츠에 대 한 [보존 정책을](../compliance/retention-policies.md) 만들고 배포 합니다.

개인 데이터를 포함 하거나 포함할 것으로 예상 되는 사이트에 대 한 데이터 개인 정보 보호의 경우 조직 표준에 맞게 보존 또는 삭제 규칙을 지정 합니다.

### <a name="retention-labels"></a>보존 레이블

콘텐츠 및 전자 메일에 대 한 [보존 레이블을](../compliance/labels.md) 만들고 배포 합니다.

개인 데이터를 포함 하거나 포함할 것으로 예상 되는 사이트, 라이브러리, 폴더 및 전자 메일에 대 한 데이터 개인 정보 보호를 위해 자동 보존 또는 삭제 규칙을 지정 하 여 조직 표준을 해결 합니다.

### <a name="records-management"></a>레코드 관리

레코드 보존 일정과 파일 계획에 따라 레코드 관리를 위한 보존 레이블을 만들고 배포 합니다.

데이터 개인 정보 보호를 위해 법률 부서에서 수신 된 dsr (데이터 주체 요청)은 레코드로 선언 되며 무제한 저장 되어 규정 활동 보존 사양을 준수 합니다.

자세한 내용은 다음 리소스를 참조 하세요. 

- [레코드 관리](../compliance/records-management.md)
- [파일 플랜 관리자](../compliance/file-plan-manager.md)
- [레코드 관리에 대 한 이벤트 기반 보존](../compliance/automate-event-driven-retention.md)
- [콘텐츠 처리](../compliance/disposition-reviews.md)
