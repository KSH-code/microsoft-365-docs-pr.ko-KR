---
title: Microsoft SharePoint Syntex에 대한 시나리오 및 사용 사례
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: laurieellis
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: 조직에서 응용 SharePoint Syntex 시나리오를 찾아 봤습니다.
ms.openlocfilehash: 619acd5d71bc6f3ab1aa99d3b7fd068faa51d696
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59183948"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex에 대한 시나리오 및 사용 사례

다음 예제 시나리오를 사용하여 조직에서 사용자 SharePoint Syntex 방법을 묻습니다.

- [시나리오: 양식 처리를 사용하여 송장에서 데이터 추적](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [시나리오: 문서 이해를 통해 계약에서 정보 추적](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [시나리오: 레코드 관리, 문서 거버넌스 및 규정 준수 프로세스를 기반으로 하는 위험 SharePoint Syntex](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [시나리오: 이전에는 이 문서에 없는 문서에서 정보 캡처](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [시나리오: 데이터 처리를 개선하여 인사이트 및 분석 제공](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [시나리오: 주문 처리 자동화](adoption-scenarios.md#scenario-automate-order-processing)
- [시나리오: Visa 갱신 프로세스 간소화](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a>시나리오: 양식 처리를 사용하여 송장에서 데이터 추적

예를 들어 송장 추적 및 모니터링을 위해 SharePoint Syntex Power Automate 프로세스를 설정할 수 있습니다.

1. 송장 문서를 저장할 라이브러리를 설치합니다.
1. 문서의 필드를 인식하는 모델을 학습합니다.
1. 추적할 필드를 목록으로 추출합니다.
1. 흐름을 설정하여 다음을 통해 특정 이벤트를 알릴 수 있습니다.
    - 새 송장이 추가됩니다.
    - 송장 기한이 지난 경우
    - 송장은 자동 승인 금액보다 큰 금액에 대한 것입니다.

![송장을 추적하고 SharePoint Syntex 및 Power Automate.](../media/content-understanding/process-invoices-flow.png)

이 시나리오를 자동화할 때 다음을 할 수 있습니다.

- 송장에서 데이터를 수동으로 추출하는 대신 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.
- 워크플로를 사용하여 송장을 확인하고 문제를 알려 잠재적인 오류를 줄이고 규정 준수를 향상합니다.

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a>시나리오: 문서 이해를 통해 계약에서 정보 추적

또 다른 예로, 회사의 다른 회사 또는 개인과의 계약을 식별하는 프로세스를 설정할 수 있습니다. 클라이언트 이름, 수수료, 날짜 또는 기타 중요한 정보와 같은 주요 정보를 해당 계약에서 추출하고 정보를 빠르게 볼 수 있는 필드로 라이브러리에 추가하는 모델을 설정하세요. 문서 라이브러리에 보존 레이블을 적용하여 비즈니스 규정을 적절하게 준수하기 위해 특정 기간 전에 계약을 삭제할 수 없습니다.

1. 콘텐츠 센터에서 시작하여 계약에 대한 새 문서 이해 모델을 만들 수 있습니다.
1. 업로드 예제 문서를 확인한 다음 교육을 실행하여 계약 문서를 식별하고 결과를 검토합니다.
1. 추출기에서 클라이언트 이름, 수수료 및 날짜와 같은 계약 필드를 식별하는 교육을 한 다음 추출기 테스트를 합니다.
1. 모델이 완료되면 계약을 업로드할 수 있는 라이브러리에 모델을 적용합니다.
1. 날짜 필드에 보존 레이블을 적용하여 계약이 필요한 기간 동안 라이브러리에 보존됩니다.

![레이블 및 보존 레이블과 SharePoint Syntex 추적하고 모니터링합니다.](../media/content-understanding/process-contracts-flow.png)

이 시나리오를 자동화할 때 다음을 할 수 있습니다.

- 수동으로 수행하지 않고 계약에서 데이터를 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.
- 보존 레이블을 사용하여 계약이 적절하게 보존되도록 하여 규정 준수를 향상합니다.

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>시나리오: 레코드 관리, 문서 거버넌스 및 규정 준수 프로세스를 기반으로 하는 위험 SharePoint Syntex

대부분의 회사에서 위험을 줄이는 것이 일반적인 목표입니다. 다음이 필요할 수 있습니다.

- 테넌트 전체에서 정보 거버넌스를 제공/적용하는 더 나은 방법
- 문서, 전자 메일 및 프로젝트의 '레코드'로 간주되는 기타 통신 형식의 분류 시스템을 개선하기 위해
- 회사 정책을 준수하기 위해 영수증, 계약 등 감사
- 프로젝트에 규정 준수에 필요한 모든 설명서가 프로젝트에 있도록 합니다.

보다 나은 거버넌스가 필요한 문서 및 양식을 SharePoint Syntex 적절히 분류하고, 감사하고, 플래그를 지정하기 위해 규정 준수를 위한 일부 프로세스를 설정하십시오. 최종 사용자가 수동으로 태그를 SharePoint Syntex 대신 콘텐츠를 자동 분류하거나 준수 팀에서 거버넌스 규칙 및 보관을 수동으로 적용할 수 있습니다. 또한 간소화된 검색 환경을 사용하도록 설정하고, 데이터 볼륨을 관리하고, 레코드 관리 및 보존 정책을 적용하고, 규정 준수를 보장하고, 모범 사례 보관 및 삭제 방법을 사용할 수 있습니다.

이 시나리오를 자동화하면 다음의 안전을 느낄 수 있습니다.

- 규정 준수를 준수하고 위험을 줄입니다.
- 세분화 및 레코드 관리는 일관되고 정확하게 적용됩니다.
- 콘텐츠 볼륨이 제어됩니다.
- 직원은 올바른 컨텍스트에서 올바른 정보를 쉽게 검색할 수 있습니다.

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>시나리오: 이전에는 이 문서에 없는 문서에서 정보 캡처

대부분의 조직에는 법률 문서, 정책, 계약, HR 문서 및 거버넌스 지침이 큰 저장소가 있습니다. 프로젝트, 섹터, 테마, 사람, 지리적 영역 등의 중요한 정보를 추출하기 위해 이러한 데이터 저장소를 마이인드합니다.

예를 들어 HR 감독은 이력서, HR 정책 및 기타 양식을 포함하여 모든 HR 문서에 빠르게 액세스해야 합니다. 또한 문서를 수동으로 제거하지 않고도 이력서 및 기타 HR 관련 문서에서 필요한 정보를 빠르게 식별할 수 있습니다. 수천 개의 이력서, HR 정책 및 여러 사이트에 분산될 수 있는 기타 설명서를 수동으로 살펴보지 않고도 필요한 정보를 빠르게 찾을 수 있는 솔루션을 찾고 있습니다.

이 시나리오를 자동화할 때 다음을 할 수 있습니다.

- 디지털 콘텐츠에서 지식의 잠금을 해제합니다.
- HR 정책, 이력서, 판매 문서, 기술 청사진, 계정 계획 및 정보 추출을 분류합니다.
- 원하는 올바른 정보나 문서를 빠르게 찾을 수 있습니다.
- 최신 정보에 즉시 액세스합니다.
- 검색 시간을 줄입니다.

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a>시나리오: 데이터 처리를 개선하여 인사이트 및 분석 제공

예를 들어 제약 회사에서 FDA SharePoint Syntex 정보를 추출하여 리더의 질문에 답변할 수 있습니다. 답변에 보다 쉽게 액세스할 수 있도록 하면 이러한 답변을 생성하는 데 필요한 시간을 줄이고 데이터의 가용성을 높이어 리더십 질문에 대한 보다 정확한 답변을 생성할 수 있습니다.

예를 들어 프로젝트 관리자는 리더십 팀의 제품 관련 질문에 대한 답변을 신속하게 제공해야 합니다. 하나의 통합 대시보드에서 쿼리와 관련된 정보 및 메트릭을 찾아야 합니다. 제품 레이블, 제품 팜플릿 및 기타 자료에서 필요한 정보를 추출하고 리더십 팀에 다시 보고할 때 사용할 수 있는 통합 보고서를 생성하는 솔루션을 찾고 있습니다.

이 시나리오를 자동화할 때 다음을 할 수 있습니다.

- 답변을 생성하는 데 필요한 시간을 줄입니다.
- 데이터의 가용성을 향상합니다.
- 보다 정확한 답변을 제공합니다.

## <a name="scenario-automate-order-processing"></a>시나리오: 주문 처리 자동화

이 SharePoint Syntex 통해 고객 주문의 수동 처리 시간을 줄일 수 있습니다. 예를 들어 OCR 처리를 사용하여 팩스, 전자 메일 또는 용지의 주문을 SharePoint 자동화된 프로세스를 사용하여 주문을 이행할 수 있도록 해당 주문에서 메타데이터를 추출할 수 있습니다.

예를 들어 공급망 관리자는 수동 데이터 입력으로 인한 오류를 줄이고자 합니다. 비즈니스 시스템으로 들어오는 오류를 줄이기 위해 인바운드 고객 주문(용지, 팩스 또는 전자 메일)의 수동 검토 및 데이터 입력을 방지하려는 경우 AI 및 기계 학습 기술을 적용하여 들어오는 주문 정보의 유효성을 검사하고 핵심 데이터를 추출한 다음 ERP 시스템에 자동으로 푸시하여 주문 이행 및 조정을 위해 솔루션을 원합니다.

이 시나리오를 자동화할 때 다음을 보장할 수 있습니다.

- 주문 및 배송 정확도가 증가합니다.
- 주문 또는 배송 오류와 관련된 수수료 또는 페널티가 감소합니다.
- 송장 송장 또는 지급이 감소하는 경우의 지연
- 직원 비용 절감

## <a name="scenario-simplify-visa-renewal-process"></a>시나리오: Visa 갱신 프로세스 간소화

SharePoint Syntex 주요 계약 정보에 대한 미리 알림 및 갱신을 자동화하는 데 도움이 될 수 있습니다. 예를 들어 HR 감독은 직원의 Visas를 최신으로 유지 및/또는 정시에 갱신해야 합니다. 사람들이 Visas를 업데이트하는 간단하고 직관적인 프로세스를 제공하려는 경우 계약에서 갱신 날짜를 추출하고 갱신 날짜가 다가오면 직원에게 미리 알림을 자동으로 보내는 솔루션이 필요합니다.

이 시나리오를 자동화할 때 다음을 보장할 수 있습니다.

- 비준수 수준이 감소합니다.
- 수동 미리 알림 수가 감소합니다.
- 비준수에 대한 벌금 수가 감소합니다.

## <a name="see-also"></a>참고 항목

[Microsoft SharePoint Syntex 도입: 시작](adoption-getstarted.md)