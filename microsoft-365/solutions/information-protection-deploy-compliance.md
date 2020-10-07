---
title: 준수 관리자를 사용 하 여 개선 작업 관리
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
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
description: 준수 점수 및 준수 관리자를 사용 하 여 개인 데이터에 대 한 보호 수준을 향상 시키는 방법을 알아봅니다.
ms.openlocfilehash: 5b41fa9fc52253d415a22aaa3422a87c4f1bda7c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377102"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>준수 관리자를 사용 하 여 개선 작업 관리

Microsoft 준수 관리자는 유럽 연합 [일반 데이터 보호 규정 (GDPR)](../compliance/gdpr.md), [캘리포니아 소비자 보호 Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (미국 의료 보험 개인 정보 취급 방침), LGPD (브라질 data Protection act)와 같은 데이터 개인 정보 규정에 관련 된 개선 사항을 관리 하는 데 도움이 될 수 있습니다.

이 문서에서는 데이터 개인 정보 보호를 위해이 도구를 사용 하는 방법에 대 한 지침을 제공 합니다.

>[!Note]
>준수 관리자의 권장 사항을 준수 보장으로 해석하면 안 됩니다. 규정 환경에 따라 고객 컨트롤의 효율성을 평가 하 고 유효성을 검사 하는 작업은 사용자의 결정입니다. 이러한 서비스는 [온라인 서비스 약관](https://go.microsoft.com/fwlink/?linkid=2108910)의 사용 약관에 따라 달라 집니다. [보안 및 규정 준수에 대 한 Microsoft 365 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager) 참조
>

## <a name="getting-started-with-compliance-manager"></a>준수 관리자 시작

#### <a name="what-is-compliance-manager"></a>준수 관리자 란?

[준수 관리자](../compliance/compliance-manager.md) 는 microsoft 클라우드 서비스와 관련 된 규정 준수 활동을 관리 하기 위한 microsoft 365 준수 센터의 워크플로 기반 위험 평가 도구입니다. Microsoft 365 또는 Azure AD (Active Directory) 구독의 일부로, 준수 관리자는 Microsoft 클라우드 서비스에 대 한 공유 책임 모델 내에서 규정 준수를 관리 하는 데 도움이 됩니다.

**평가를 사용할 준비가 되었습니다.**

준수 관리자는 GDPR 및 HIPAA/HITECH와 같은 데이터 개인 정보 관련 규정에 부합 되는 [평가를 빌드하기](../compliance/compliance-manager-assessments.md) 위한 미리 작성 된 템플릿을 제공 합니다. 이 서식 파일에는 규정 요구 사항을 충족 하기 위한 개선 작업을 수행 하는 데 도움이 되는 기본 제공 컨트롤 매핑이 있습니다. 각 평가에서는 특정 대상 서비스에 대 한 각 규정 호출을 제어 하는 컨트롤에 대 한 정보를 제공 하며, Microsoft에서 관리 하 고 제어 하는 컨트롤을 통해 분류 하 여 

미리 작성 된 서식 파일을 사용 하면 위험 평가를 빠르게 시작할 수 있습니다. 규정 준수 관리자를 보다 능숙 하 게 사용할 수 있는 것 처럼, 사용자가 직접 작성 한 서식 파일을 사용자 지정할 수도 있고, 향상 된 작업을 추가 하 여 조직의 요구 사항에 맞게 고유한 사용자 지정 평가를 만들 수도 있습니다.

준수 관리자가 제공한 [평가 템플릿의 전체 목록을](../compliance/compliance-manager-templates-list.md) 확인 합니다.

**실시간 준수 점수**

또한 준수 관리자는 컨트롤 내에서 권장 되는 개선 작업을 완료 하는 과정을 측정 하는 준수 점수를 제공 합니다. 이 점수를 사용 하 여 위험을 줄일 수 있도록 진행 상황을 모니터링 하 고 작업의 우선 순위를 지정할 수도 있습니다.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>준수 관리자의 빠른 시작 가이드 사용

[준수 관리자의 빠른](../compliance/compliance-manager-quickstart.md) 단계 및 준수 관리자와 함께 작업 하는 데 도움이 되는 주요 리소스에 대 한 링크를 제공 합니다.

- [처음 방문: 준수 관리자에 게 익숙해져야 합니다.](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - 준수 관리자 대시보드 작업
    - 준수 점수 이해
    - 개선 작업에 대 한 학습
    - 평가 및 템플릿 이해
- [램프 업: 준수 작업을 관리 하도록 준수 관리자 구성](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - 첫 번째 평가 구성 및 관리
    - 평가에서 제어를 완료 하기 위한 개선 작업에 대 한 구현 및 테스트 작업 수행
    - 다양 한 작업으로 인해 준수 점수가 영향을 미치는 방식 이해
- [수직 확장: 사용자 지정 요구 사항을 충족 하기 위해 고급 기능 사용](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Microsoft 제품이 아닌 365 제품을 추적 하기 위한 사용자 지정 평가 만들기
    - 기존 서식 파일을 수정 하 여 컨트롤 추가 또는 제거
    - 개선 작업에 대 한 자동화 된 테스트 설정

## <a name="how-your-compliance-score-is-calculated"></a>규정 준수 점수 계산 방법

Microsoft 및 고객 관리 제어 구현의 조합에 따라 규정 준수 점수가 계산 됩니다. 자세한 설명은 [준수 점수 계산](../compliance/compliance-score-calculation.md) 을 참조 하세요.

컨트롤이 필수 인지 아니면 임의 인지에 따라 점수 값이 할당 되 고 사용자가 예방적이 든 상관 없이 예방용 인지 인지 여부를 결정 합니다. 이는 다른 컨트롤을 기준으로이를 구현 하지 않을 위험을 나타냅니다.

규정 준수 점수 계산 문서에 나와 있는 것 처럼 예방적 컨트롤은 예방용 인지 보다 더 높은 점수를 얻게 되며, 필수 컨트롤은 임의의 것 보다 더 높은 점수를 얻게 됩니다.

규정 준수 점수 관리자 UI에는 이러한 매개 변수가 나열 되지 않으며 필터링 기능도 제공 되지 않습니다. 그러나 준수 관리자에서 연결 된 서식 파일을 다운로드 하는 경우 결과 데이터 집합에는 대부분의 규정에 해당 하는 매개 변수가 나열 됩니다.

기술 제어의 경우 준수 관리자는 작업을 성공적으로 구현 및 테스트 한 후에 향상 된 개선 작업 점수를 자동으로 업데이트 합니다. &mdash;작동 하거나 설명서와 관련 된 기타 기술 없는 제어 작업을 &mdash; 점수가 점수에 들어가기 전에 구현 됨에 따라 수동으로 기록 해야 합니다.

또한 &mdash; 데이터 개인 정보 규정 준수 이외의 이유로 보존 레이블을 사용 하 여 다른 용도로도 사용 하는 경우에는 해당 기능을 사용 하는 것이 좋지만 &mdash; , 의도적인 규정 준수 작업의 일부가 아닌 경우에는 다른 목적에 대 한 특정 향상 작업을 구현 해야 합니다.

규정 준수 점수는 광범위 한 규모의 개선을 추적 하기 위한 상대 수단으로 간주 해야 합니다. 완벽 한 점수를가지고 서는 안 됩니다.

## <a name="additional-guidance"></a>추가 안내

다음은 준수 관리자를 사용 하 여 데이터 개인 정보 규정 준수를 달성 하는 데 도움이 되는 몇 가지 중요 한 팁입니다.

- 각 데이터 개인 정보 규정에는 기술 컨트롤, 문서 사양, 운영, 프로세스 및 보고 요구 사항의 조합이 포함 되어 있습니다. 이러한 모든 기능을 향상 작업에 표시 합니다.

- 검토 작업을 관심 있는 영역에 집중 하기 위해 준수 관리자 관리자의 **솔루션** 탭에서 작업 유형별로 필터링 할 수 있습니다. [준수 관리자 대시보드 보기 필터링](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)에 대해 더 자세히 알아보세요.

- 준수 관리자에서 식별 된 개선 작업의 상대적 중요도와 우선 순위는 조직에서 관리 해야 하는 데이터 개인 정보 위험과 함께 광범위 한 위험 검토의 일부로 간주 해야 합니다.

- 여러 규정 요구 사항에 대 한 향상 된 작업 집계를 사용 하는 경우에도 GDPR, LGPD, CCPA 및 HIPAA-HITECH에 대 한 규정 평가 템플릿이 선택 된 경우 준수 관리자에 게는 거의 400 개선 작업이 나열 됩니다. 이 긴 목록을 보다 효율적으로 활용 하려면 향상 작업 필터를 사용 하 여 결과 집합을 보다 쉽게 관리할 수 있는 목록으로 줄이십시오.

- Categories filter는이 전체 솔루션의 추적, 방지, 보호, 보존 및 조사를 수행 하는 논리적 그룹화를 통해 향상 작업을 필터링 하는 방법을 제공 합니다.

- 향상 작업에 나열 된 일부 컨트롤은 특정 규제 문서에 직접 연결 되어 있는 것으로 간주 되는 반면, 다른 컨트롤은 규정의 스피릿와 간접적으로 더 많이 연결 될 수 있으며,이는 단순히 권장 되는 작업 또는 모범 사례입니다.