---
title: 'Microsoft SharePoint Syntex 도입: 시작'
description: 조직에서 비즈니스 문제를 SharePoint Syntex 사용하여 구현하는 방법을 배워야 합니다.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
ms.localizationpriority: medium
ms.openlocfilehash: 172c0a681bc8e7c7867e4bcba1c75f94cfc12e60
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193162"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint Syntex 도입: 시작

다음 세 부분으로 구성되는 것으로 SharePoint Syntex 지능형 콘텐츠 서비스를 사용할 수 있습니다.

- **콘텐츠 이해:** 코드 없는 AI 모델을 만들어 콘텐츠에서 정보를 분류하고 추출하여 지식 검색 및 재사용을 위한 메타데이터를 자동으로 적용합니다. 콘텐츠 [이해에 대해 자세히 알아보겠습니다.](document-understanding-overview.md)
- **콘텐츠 처리:** 콘텐츠 캡처, 수집 및 분류를 자동화하고 콘텐츠를 사용하여 콘텐츠 중심 프로세스를 Power Automate. 콘텐츠 처리에 [대해 자세히 알아보겠습니다.](form-processing-overview.md)
- **콘텐츠 준수:** 콘텐츠를 제어하고 관리하여 보안 및 거버넌스를 사용자와 통합하여 Microsoft Information Protection.

새로운 AI 서비스 및 기능을 사용하여 콘텐츠 이해 및 분류 앱을 콘텐츠 관리 흐름에 직접 빌드할 수 SharePoint Syntex. 콘텐츠를 이해하는 방법에는 두 가지가 있습니다. 사용하는 모델 형식은 파일 형식 및 사용 사례를 기반으로 합니다.

| 양식 처리 | 문서 이해 |
|:-------|:-------|
| 문서 라이브러리에서 만들어집니다. | 콘텐츠 센터의 일부인 콘텐츠 센터에서 SharePoint Syntex. |
| AI 작성기에서 만든 모델입니다. | 네이티브 인터페이스에서 만든 모델입니다. |
| 반구조적 파일 형식에 사용됩니다. | 구조화되지 않은 파일 형식에 사용됩니다. |
| Settable 분류자입니다. | 선택적 추출기를 사용할 수 있는 학습 가능한 분류자입니다. |
| 단일 라이브러리로 제한됩니다. | 여러 라이브러리에 적용할 수 있습니다. |
| PDF, JPG, PNG 형식 교육 총 50MB/500 pp. | 5~10개의 PDF, Office 또는 전자 메일 파일(부정 예제 포함)에 대해 학습 가능합니다. |

기능을 보다 완전한 비교는 문서 이해 모델과 양식 처리 모델 간의 [차이를 참조하세요.](difference-between-document-understanding-and-form-processing-model.md)

## <a name="identify-pilot-business-scenarios-to-optimize"></a>최적화할 파일럿 비즈니스 시나리오 확인

조직에서 SharePoint Syntex 사용할 수 있도록 준비하려면 먼저 유용한 시나리오를 이해해야 합니다. "이유"는 필요한 모델과 모델이 적용되는 위치를 기준으로 조직을 구성하는 방법을 결정하는 데 도움이 됩니다. 다음은 문서 이해가 조직에 도움이 될 수 있는 몇 가지 시나리오입니다.

- **콘텐츠 처리:** 계약서, 작업 설명 및 기타 양식과 같은 문서를 처리합니다. 양식을 조정하고 필드를 이해하고 매핑하기 위해 모델을 교육한 다음 양식을 실행하여 데이터를 자동으로 수집합니다. 자세한 내용은 양식 처리 [개요를 참조하세요.](form-processing-overview.md)
- **송장 분석:** 송장에서 관련 세부 정보를 끌어오고 정책이 준수되고 있는지 또는 적절하게 처리되고 있는지 확인

조직에 도움이 되는 SharePoint Syntex 방법을 생각해 보아야 합니다.

- 비즈니스 프로세스 자동화
- 검색 정확도 향상
- 규정 준수 위험 관리

고려할 비즈니스 시나리오를 고려할 때 다음과 같은 질문을 합니다.

- 실제 문제를 해결하나요?
- 광범위하게 사용되거나 광범위한 영향을 미치나요?
- 얻을 수 있나요?
- 성공을 측정할 수 있나요?

영향 및 구현 용이성을 기반으로 시나리오 우선 순위를 지정합니다. 초기 포커스 영역을 쉽게 구현할 수 있는 더 큰 영향 시나리오로 만들어야 합니다. 구현하기 어려운 낮은 영향 시나리오의 우선 순위를 낮게 지정합니다.

예제 시나리오 및 사용 [사례를](adoption-scenarios.md) 사용하여 조직에서 시나리오를 사용하는 방법에 대한 SharePoint Syntex 합니다.

## <a name="identify-roles--responsibilities"></a>역할 및 & 식별

조직에서 모델을 빌드하고 관리할 사용자 결정 다음 역할이 관련될 수 있습니다.

| SharePoint/지식 관리자 | 파워 플랫폼 관리자 | 지식 관리자 | 모델 소유자 |
|:-------|:-------|:-------|:-------|
| AAD 역할| AAD 역할 | AAD 역할 | 챔피언 |
| 양식 처리 구성 | 양식 처리를 위한 Dataverse 환경 구성 | 사용 사례 수집 | 비즈니스 사용 사례 수집 |
| 콘텐츠 센터 및 사용 권한 관리| AIB 크레딧 구매 및 할당 | 모범 사례 설정 및 모델 분석 검토 | 모델 만들기 및 적용 |

지식 관리자, 비즈니스 프로세스 소유자 및 콘텐츠 모델 소유자는 조직에서 샘플 모델 및 챔피언 채택을 생성합니다.
관련이 있을 수 있는 기타: 규정 준수 관리자, 세분화 관리자.

어디에서 모델을 빌드하고 적용할 것인가? 개선할 수 있는 기존 프로세스 또는 리포지토리가 있나요?

- 양식 처리: 양식 처리 작업을 받을 사이트를 결정할 수 있습니다.
- 문서 이해: 서로 다른 비즈니스 영역에 대해 여러 콘텐츠 센터를 만들 수 있습니다.

## <a name="strategic-positioning"></a>전략적 위치

이해 관계자와 협의하여 이해 관계자가 비즈니스용 전략에 부합하는지 SharePoint Syntex. 이 위치 관리에 도움이 되는 다음 리소스를 조사하고 제공합니다.

- 비즈니스 결과:
  - 잠재적 회계 결과
  - 잠재적인 민첩성 결과
  - 비즈니스 결과 서식 파일
- 이해 관계자/Exec 스폰서 구입/조정
  - 비즈니스 사례 데크
  - 재무 모델
  - 회사 준비 - 문화

## <a name="identify-stakeholders"></a>관련자 파악

프로젝트에 대한 관련자를 파악합니다.

|역할 |책무 |부서 |
|:-------|:-------|:--------|
| Executive sponsor(s)   | 회사에 높은 수준의 비전과 가치 전달   |  경영진 대표   |
| Project 선행 | 전체 실행 및 배포 과정 감독 | 프로젝트 관리 |
| 지식 관리자| 콘텐츠 센터 만들기 및 관리 | IT 또는 기타 부서|
| 콘텐츠 관리자 및 모델 소유자| 사용 사례 수집 및 모델 만들기 및 적용 | 모든 부서|
| 챔피언 | 이의 처리 독려 및 관리 | 모든 부서(직원) |
| 테넌트 관리자 | 테넌트 수준 설정 구성 | IT 부서|
| 파워 플랫폼 관리자| Dataverse 환경 구성 | IT 부서|

> [!NOTE]
> 이러한 각 역할을 롤아웃 전체에서 이행하는 것이 까다로우면 식별된 솔루션을 시작하는 데 이러한 역할이 모두 필요하지 않을 수도 있습니다.

## <a name="readiness-checklist"></a>준비 검사 목록

사용자에 대한 구현을 준비하려면 SharePoint Syntex 다음을 해야 합니다.

![콘텐츠 이해를 위한 준비](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. 종료 상태 계획
    - 문서 이해 모델은 끝이 아니라 수단입니다.
    - 다음을 사용하여 추출된 메타데이터의 값을 사용 계획합니다.
      - 검색
      - 필터링 및 보기 서식
      - 규정 준수
      - 자동화
2. 식별
    - 기존 정보 아키텍처 및 콘텐츠 관리 기능 사용을 이해합니다.
    - 기존 콘텐츠 형식이 모델에 대해 좋은 후보인가요?
    - 메타데이터를 통해 개선할 기존 프로세스는 무엇입니까?
3. 디자인
    - 정보 아키텍처, 관리되는 메타데이터 및 콘텐츠 형식에 대한 접근 방식을 디자인합니다.
    - 정의, 만들기, 관리 프로세스를 디자인합니다.

## <a name="engage-your-organization"></a>조직 참여

1. 지주를 식별하고 시나리오를 확인하고 프로젝트 계획을 개발합니다.
1. 설정을 구성하고 라이선스를 적용합니다.
1. 인식과 교육 시작 - 챔피언을 모집합니다.
1. 단계적 롤아웃  
1. 피드백을 수집하고 이행합니다.
1. 사용량이 증가함에 따라 필요한 경우 AI 작성기 크레딧에 대한 계획이 커지고 있습니다.

## <a name="see-also"></a>참고 항목

[SharePoint Syntex에 대한 시나리오 및 사용 사례](adoption-scenarios.md)

[Microsoft 365 솔루션을 사용하여 계약 관리](solution-manage-contracts-in-microsoft-365.md)
