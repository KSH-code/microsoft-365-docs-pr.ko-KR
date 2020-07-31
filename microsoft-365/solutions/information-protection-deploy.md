---
title: Microsoft 365을 사용 하 여 데이터 개인 정보 보호 규정에 대 한 information protection 배포
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: 보안 및 서비스 인프라를 구성 하 여 정보를 보호 하 고 데이터 개인 정보 규정을 준수 합니다.
ms.openlocfilehash: 640ce075515c687c037cb0e4ab3e03e3beda81dc
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522292"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Microsoft 365을 사용 하 여 데이터 개인 정보 보호 규정에 대 한 information protection 배포

조직에서 온-프레미스와 클라우드를 모두 포함 하 여 IT 인프라에 저장 된 개인 정보를 보호, 관리 및 제어 해야 하는 지역별 데이터 개인 정보 규정을 준수할 수 있습니다. 데이터 개인 정보 취급 규정의 가장 좋은 예는 유럽 연합의 GDPR (일반 데이터 보호 규정)입니다. 데이터 개인 정보 규정을 준수 하지 않으면 상당한 벌금과 될 수 있습니다.

Microsoft 365의 데이터 형식에는 Microsoft 팀의 채팅 세션, Exchange의 전자 메일 및 SharePoint 및 OneDrive의 파일 등이 포함 됩니다. 이 솔루션은 데이터 개인 정보 규정을 준수 하는 Microsoft 365 services에 저장 된 개인 데이터에 대 한 데이터 개인 정보 인시던트를 식별, 검색, 보호, 제어 및 대응 하는 방법에 대 한 지침을 제공 합니다.

![데이터 개인 정보 규정을 위한 정보 보호 배포](../media/information-protection-deploy/information-protection-deploy-big-picture.png)

데이터 개인 정보 요구 사항에 대해 Microsoft 365 id, 장치 및 위협 방지 컨트롤을 사용 하는 경우에도 추가 정보가 제공 됩니다. 

데이터 개인 정보 규정 준수를 위해 정보를 보호 하기 위한 기준을 충족 하려면 이러한 Microsoft 365 기능을 사용 합니다.

| 기능 또는 특징 | 설명 | 라이선싱 |
|:-------|:-----|:-------|
| 규정 관리자 | Microsoft 서비스 신뢰 포털에서 이 워크플로우 기반 위험 평가 도구를 사용하여 Microsoft 클라우드 서비스와 관련된 규정 준수 활동을 관리합니다. | Microsoft 365 E3 및 E5 |
| 준수 점수(미리 보기) | Microsoft 365 Compliance Center에서 현재 규정 준수 구성의 전체 점수와 이를 개선하기 위한 권장 사항을 확인합니다. | Microsoft 365 E3 및 E5 |
| Office ATP (Advanced Threat Protection) | 전자 메일 메시지, 사무실 문서 및 협업 도구와 같은 Microsoft 365 앱과 데이터를 공격으로부터 보호합니다. | Microsoft 365 E3 및 E5 | 
| 민감도 레이블 | 전자 메일, 파일 또는 사이트에 다양한 수준의 보호 기능을 갖춘 레이블을 배치하여 사용자의 생산성과 협업 능력을 저해하지 않고 조직의 데이터를 분류하고 보호합니다. | Microsoft 365 E3 및 E5 |
| 데이터 손실 방지(DLP). | 개인 정보가 포함된 데이터 공유와 같은 위험하거나 부주의하거나 부적절한 공유를 내외부적으로 탐지, 경고 및 차단합니다. | Microsoft 365 E3 및 E5 | 
| 데이터 보존 레이블 및 정책. | 조직의 정책 또는 데이터 규정을 준수하기 위해 고객의 개인 데이터 스토리지에 대한 데이터 및 요구사항을 보관하는 기간과 같은 정보 거버넌스 제어를 구현합니다. | Microsoft 365 E3 및 E5 |
| 전자 메일 암호화 | 고객의 개인 데이터와 같이 규제 데이터가 들어 있는 조직 내외부의 사용자 간에 암호화된 전자 메일 메시지를 주고 받습니다. | Microsoft 365 E3 및 E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>이 솔루션의 지침 구성

하나 이상의 개인 정보 관련 규정에 따라 개인 데이터를 식별, 관리, 제어 및 모니터링 하는 데 사용할 수 있는 Microsoft 365 도구를 이해 하는 데 도움이 되도록이 지침은 섹션으로 구성 되어 있습니다.
 
![데이터 개인 정보 규정을 위한 정보 보호 배포](../media/information-protection-deploy/information-protection-deploy-grid.png)

이러한 각 섹션은이 솔루션의 별도 문서에 해당 합니다.

>[!Note]
>데이터 개인 정보 취급 방침을 이미 잘 알고 있고 기존 계획에 대해 실행 중인 경우에는 방지, 보호, 보존 및 조사 지침에 중점을 둘 수 있습니다.

>[!Important]
>이 가이드를 따르면, 특히 기능 컨텍스트 외부에 있는 필요한 단계 수를 고려 하 여 데이터 개인 정보 규정을 준수 하는 것은 아닙니다. 준수 여부를 확인 하 고 법률 및 규정 준수 팀에 문의 하거나, 규정 준수를 전문적으로 진행 하는 제 3 자가 제공 하는 지침 및 조언을 검색 해야 합니다.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>계획: 데이터 개인 정보 위험 평가 및 중요 한 항목 확인 

조직에 적용 되는 데이터 개인 정보 규정 및 위험 요소를 평가 하는 것은 Microsoft 365 구성을 통해 얻을 수 있는 기능을 포함 하 여 개선 된 사항을 구현 하기 전에 먼저 수행 해야 하는 주요 단계입니다. 여기에는 조직에서 준수 해야 하는 규정 통제와 관련 된 특정 중요 한 정보 유형, 그리고 Microsoft 365 환경에서 발생 하는 상황을 식별 하는 전반적인 준비 평가 또는 id가 포함 될 수 있습니다.

자세한 내용은 [데이터 개인 정보 보호 위험 평가 및 중요 한 항목 식별](information-protection-deploy-assess.md)을 참조 하세요.

## <a name="track-use-compliance-score-and-compliance-manager"></a>추적: 준수 점수 및 준수 관리자 사용 

준수 점수 및 준수 관리자는 Microsoft 365 준수 관리 센터 및 서비스 신뢰 포털에서 사용 가능한 통합 도구 집합을 제공 합니다. 이러한 도구를 함께 사용 하면 기본 제공 되는 다양 한 데이터 개인 정보 규정에 따라 전반적인 향상 작업을 추적 하 고 관리할 수 있습니다.

또한이 도구를 사용 하면 각 규제 규정에 따라 기본 제공 되는 평가 템플릿을 활용 하 여 선택한 각 평가 템플릿의 작업 항목을 추적할 수 있을 뿐만 아니라 특정 규정 제어를 확인 하 고 특정 작업에 연결할 수도 있습니다.

자세한 내용은 [준수 점수 및 준수 관리자를 사용 하 여 개선 작업 관리](information-protection-deploy-compliance.md)를 참조 하세요.

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>금지: 데이터 개인 정보 규정에 id, 장치 및 위협 보호 사용

Microsoft 365에서는 데이터 개인 정보 규정 준수를 준수 하는 데 사용할 수 있는 다양 한 id, 장치 및 위협 보호 기능을 제공 합니다. 

자세한 내용은 [데이터 개인 정보 규정에 대 한 id, 장치 및 위협 보호 사용](information-protection-deploy-identity-device-threat.md)을 참조 하세요.

이 문서에서는 이러한 영역에서 일반적으로 호출 되는 데이터 개인 정보 보호 규정을 소개 하 고, 구현 요구 사항을 해결 하는 데 도움이 되는 자세한 정보에 대 한 링크와 함께 관련 Microsoft 365 솔루션 목록을 제공 합니다. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>데이터 개인 정보 규정의 영향을 받는 정보 보호

데이터 프라이버시 규정은 GDPR, 캘리포니아 CCPA), HIPAA-HITECH (미국 의료 보험 개인 정보 보호 act) 및 LGPD (브라질 Data Protection Act)의 예제 집합에 있는 4 가지 데이터 개인 정보 보호 기능을 40 포함 하 여 사용자 환경에서 사용할 수 있는 다양 한 개인 정보 보호 컨트롤을 규정 합니다.

자세한 내용은 [조직의 데이터 개인 정보 규정에 대 한 정보 보호 주체를](information-protection-deploy-protect-information.md)참조 하세요.

이 문서에서는 조직의 데이터 프라이버시에 대 한 정보 보호 요구 사항을 해결 하는 데 사용할 수 있는 기본 컨트롤 구성표를 소개 합니다.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Retain: 데이터 개인 정보 규정의 영향을 받는 정보를 제어 합니다.

데이터 개인 정보 규정 통화 GDPR, CCPA, HIPAA-HITECH 및 LGPD의 예제 집합에 포함 된 4 가지 데이터 개인 정보 규정에 따라 25 개 이상의 컨트롤을 비롯 하 여 사용자 환경에서 사용 될 수 있는 개인 홍보 관리 컨트롤에 대 한 호출입니다.

자세한 내용은 [조직의 데이터 개인 정보 규정에 대 한 제어 정보](information-protection-deploy-govern.md)를 참조 하세요.

고의적 보존, 삭제 및 보관과 같은 정보 거 버 넌 스에 대 한 데이터 개인 정보 규정은 모호 하 게 할 수 있지만, &mdash; &mdash; 이 문서에서는 조직의 데이터 개인 정보 보호를 위해 주소 정보 관리 요구 사항을 사용할 수 있는 기본 컨트롤 스키마를 설명 합니다.

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a>조사: 데이터 개인 정보 규정을 모니터링 하 고 응답 합니다.

관련 기능을 operationalize 때 조직의 데이터 개인 정보 인시던트를 모니터링, 조사 및 대응 하는 데 도움이 되는 Microsoft 365 기능이 있습니다. 

이러한 각 단계에 대 한 프로세스, 절차 및 기타 설명서도 규정 된 본문에 대 한 준수를 시연 하는 것이 중요 합니다.

자세한 내용은 [조직의 데이터 개인 정보 보호 인시던트에 모니터링 및 응답을](information-protection-deploy-monitor-respond.md)참조 하세요.
