---
title: 준수 관리자를 사용하여 개선 작업 관리
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: admindeeplinkCOMPLIANCE
description: 준수 점수 및 준수 관리자를 사용하여 개인 데이터에 대한 보호 수준을 개선하는 방법을 학습합니다.
ms.openlocfilehash: 5a655d504551e42398cdabbcf7a3f651d788c0ad
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786017"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>준수 관리자를 사용하여 개선 작업 관리

Microsoft 준수 관리자는 유럽 연합 [GDPR(일반](/compliance/regulatory/gdpr)데이터 보호 규정), 캘리포니아 소비자 보호법 [CCPA,](/compliance/regulatory/ccpa-faq)HIPAA-HITECH(미국 의료 개인 정보 보호법) 및 브라질 데이터 보호법(LGPD)과 같은 데이터 개인 정보 보호 규정과 관련된 개선된 기능을 관리하는 데 도움을 줄 수 있습니다.

이 문서에서는 데이터 개인 정보 보호를 위해 이 도구를 사용하는 방법에 대한 지침을 제공합니다.

> [!NOTE]
> 준수 관리자의 권장 사항을 준수 보장으로 해석하면 안 됩니다. 규제 환경당 고객 제어의 효율성을 평가하고 유효성을 검사하는 것은 귀하의 의 의의입니다. 이러한 서비스는 온라인 서비스 약관의 사용 [약관을 따라야 합니다.](https://go.microsoft.com/fwlink/?linkid=2108910) 보안 및 Microsoft 365 대한 [라이선스 지침도 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="getting-started-with-compliance-manager"></a>준수 관리자 시작

#### <a name="what-is-compliance-manager"></a>준수 관리자

[준수 관리자는](../compliance/compliance-manager.md) Microsoft 클라우드 서비스와 관련된 규정 Microsoft 365 규정 준수 센터 관리하기 위한 워크플로 기반 위험 평가 도구입니다. Azure AD(Microsoft 365 또는 Azure Active Directory) 구독의 일부로 준수 관리자는 Microsoft 클라우드 서비스에 대한 공유 책임 모델 내에서 규정 준수를 관리하는 데 도움이 됩니다.

**평가 사용 준비**

준수 관리자는 GDPR 및 [](../compliance/compliance-manager-assessments.md) HIPAA/HITECH와 같은 데이터 개인 정보 관련 규정에 맞춰진 평가를 작성하기 위한 미리 작성된 템플릿을 제공합니다. 템플릿에는 규정 요구 사항을 충족하기 위한 개선 조치를 취할 수 있도록 기본 제공 컨트롤 매핑이 있습니다. 각 평가는 Microsoft에서 관리하는 컨트롤로 나타난 대상 서비스에 대한 각 규정 호출 컨트롤에 대한 정보를 제공합니다.

미리 작성된 템플릿을 사용하면 위험 평가를 빠르게 시작할 수 있습니다. 준수 관리자를 사용하는 데 더 많은 습관적이면 자체 컨트롤 및 개선 작업을 추가하여 미리 작성된 템플릿을 사용자 지정하거나 조직의 요구에 맞게 사용자 지정 평가를 직접 만들 수 있습니다.

준수 [관리자가 제공하는 전체 평가 템플릿](../compliance/compliance-manager-templates-list.md) 목록을 시청하세요.

**실시간 준수 점수**

또한 준수 관리자는 컨트롤 내에서 권장 개선 작업을 완료하는 진행 상황을 측정하는 준수 점수를 제공합니다. 이 점수를 사용하여 진행 상황을 모니터링하고 위험을 줄이는 잠재력에 따라 작업의 우선 순위를 지정할 수 있습니다.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>준수 관리자 빠른 시작 가이드 사용

준수 [관리자 빠른 시작](../compliance/compliance-manager-quickstart.md) 가이드는 준수 관리자를 사용할 수 있도록 주요 리소스에 대한 단계와 링크를 제공합니다.

- [첫 방문: 준수 관리자에 익숙해지기](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - 준수 관리자 대시보드 작업
    - 준수 점수 이해
    - Learning 개선 작업에 대한 자세한 정보를
    - 평가 및 템플릿 이해
- [Ramping up: Configure Compliance Manager to manage your compliance activities](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - 첫 번째 평가 구축 및 관리
    - 평가의 컨트롤을 완료하기 위해 개선 작업에 대한 구현 및 테스트 작업 수행
    - 다양한 작업이 준수 점수에 미치는 영향 이해
- [확장: 고급 기능을 사용하여 사용자 지정 요구 사항 충족](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - 비영리 제품을 추적하기 위한 사용자 지정 Microsoft 365 만들기
    - 기존 템플릿을 수정하여 컨트롤 추가 또는 제거
    - 개선 작업의 자동화된 테스트 설정

## <a name="how-your-compliance-score-is-calculated"></a>규정 준수 점수 계산 방법

준수 점수는 Microsoft와 고객 관리 컨트롤 구현의 조합에 따라 계산됩니다. 자세한 [설명은](../compliance/compliance-score-calculation.md) 준수 점수 계산을 참조합니다.

컨트롤은 필수인지 또는 사용자 지정인지 여부와 예방용, 감지용 또는 시정용인지에 따라 점수 값이 할당됩니다. 이러한 컨트롤은 다른 컨트롤을 상대로 구현하지 않을 위험을 총체적으로 나타 내포합니다.

준수 점수 계산 문서에 설명된 것 처럼 예방용 컨트롤은 감지용 컨트롤 및 수정 컨트롤보다 높은 점수를 얻게 되고 필수 컨트롤은 재량에 비해 높은 점수를 얻습니다.

준수 점수 관리 UI는 이러한 매개 변수를 나열하지 않으며 이러한 매개 변수를 필터링하는 기능을 제공하지 않습니다. 그러나 준수 관리자에서 연결된 템플릿을 다운로드하면 결과 데이터 집합에 대부분의 규정에 대한 이러한 매개 변수가 나열됩니다.

기술 컨트롤의 경우 준수 관리자는 작업이 성공적으로 구현 및 테스트된 후 개선 작업 점수를 자동으로 업데이트합니다. 작업 또는 설명서와 관련된 작업과 같은 기타 비기술적인 제어 작업은 점수가 점수에 계산되기 전에 구현된 것으로 수동으로 &mdash; &mdash; 기록해야 합니다.

또한 많은 사용자가 데이터 개인 정보 규정 준수가 아닌 다른 이유로 보존 레이블을 사용하는 등의 다른 목적에 대해 특정 개선 작업을 구현하고 있으므로 의도적인 준수 작업의 일부가 아닌 다른 목적으로 사용되어도 이러한 기능을 사용할 때의 크레딧을 얻게 &mdash; &mdash; 됩니다.

준수 점수는 광범위한 규모의 개선을 추적하기 위한 상대적인 측정값으로 간주해야 합니다. 완벽한 점수를 따라야 하는 것은 아니며,

## <a name="additional-guidance"></a>추가 안내

다음은 규정 준수 관리자를 사용하여 데이터 개인 정보 규정 준수를 달성하는 데 도움이 되는 몇 가지 중요한 팁입니다.

- 각 데이터 개인 정보 규정에는 기술 제어, 문서 사양 및 운영, 프로세스 및 보고 요구 사항이 조합되어 있습니다. 이러한 모든 작업은 개선 작업에 표시 됩니다.

- 개선 작업의 보기를 관심 영역에 집중하려면 준수 관리자 관리자의  솔루션 탭에서 작업 유형별로 필터링할 수 있습니다. 준수 관리자 대시보드 보기 필터링에 대해 자세히 [알아보하세요.](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)

- 준수 관리자에서 식별된 개선 작업의 상대적 중요도와 우선 순위는 조직에서 관리해야 한다고 결정한 데이터 개인 정보 보호 위험과 함께 더 광범위한 위험 검토의 일부로 간주해야 합니다.

- 여러 규제 요구 사항에 대한 개선 작업 집계에서도 GDPR, LGPD, CCPA 및 HIPAA-HITECH에 대한 규정 평가 템플릿을 선택하면 준수 관리자에 약 400개 개선 작업이 나열됩니다. 이 긴 목록을 보다 효율적으로 활용하기 위해 개선 작업 필터를 사용하여 결과 집합을 보다 관리 가능한 목록으로 줄입니다.

- 범주 필터는 논리적 그룹화로 개선 작업을 필터링하는 수단을 제공합니다. 이 전체 솔루션의 문서 추적, 방지, 보호, 보존 및 조사가 이 전체 솔루션에 맞게 조정됩니다.

- 개선 작업에 나열된 일부 컨트롤은 특정 규제 문서와 더 직접적으로 연결된 것으로 간주될 수 있으며, 다른 컨트롤은 규정의 준수와 더 간접적으로 연결될 수 있으며 단순히 권장 활동 또는 모범 사례인 경우도 많을 수 있습니다.