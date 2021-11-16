---
title: 다음의 검토 집합에서 데이터 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 사례를 분석할 때 문서 집합을 구성하는 데 사용할 수 있는 Advanced eDiscovery 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e1a8f2986c31cdf710d65532eb64394bc34d7a0b
ms.sourcegitcommit: d40b8c506c34a661a275f756081a27ef9ad5bf4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2021
ms.locfileid: "60971982"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>다음의 검토 집합에서 데이터 Advanced eDiscovery

수집된 문서의 수가 크면 모두 검토하기 어려울 수 있습니다. Advanced eDiscovery 정보를 손실하지 않고도 검토할 문서의 양을 줄이고 문서를 공동으로 구성하는 데 도움이 되는 다양한 도구를 제공합니다. 이러한 기능에 대한 자세한 내용은 다음을 참조합니다.

- [중복에 가까운 검색](near-duplicate-detection-in-advanced-ediscovery.md)

- [전자 메일 스레드](email-threading-in-advanced-ediscovery.md)

- [테마](themes-in-advanced-ediscovery.md)

## <a name="run-analytics-for-a-review-set"></a>검토 집합에 대한 분석 실행

검토 집합의 데이터를 분석하는 경우:

1. 사례에 대한 분석 설정을 구성합니다. 자세한 내용은 검색 및 분석 [설정 구성을 참조하세요.](configure-search-and-analytics-settings-in-advanced-ediscovery.md)

2. 분석할 리뷰 집합을 열 수 있습니다.

3. 분석 **실행**  >  **문서 & 클릭합니다.**

   ![분석 드롭다운 목록에서 & 분석 실행을 선택합니다.](..\media\RunAnalytics1.png)

사례의 작업 탭에서 분석  진행률을 확인할 수 있습니다.

 분석이 완료되면 분석 보고서를 보고, 분석 출력에 대한 검토 집합 내에서 쿼리를 실행하고(검토 집합 내의 쿼리 [참조)](review-set-search.md)특정 문서의 관련 문서를 볼 수 있습니다(검토 집합의 데이터 검토 [참조).](reviewing-data-in-review-set.md)

## <a name="using-the-for-review-filter-query"></a>검토용 필터 쿼리 사용

검토 집합에 대한 분석을 실행한 후 검토를 필터링하는 자동으로 생성된 필터 쿼리(검토용)를 사용하여 불필요하거나 중복되거나 포함되지 않은 항목을 제외할 수 있습니다.  이렇게 하여 검토 집합에 대표적이고 고유하며 포괄적인 항목만 남게 됩니다.

검토용  필터 쿼리를 검토 집합에 적용하려면 저장된 필터 쿼리 드롭다운 목록을 선택한 다음 검토용 **\[ 자동 작성]을 선택합니다.** 

![저장된 필터 쿼리 드롭다운 목록에서 검토를 선택합니다.](..\media\ForReviewFilterQuery1.png)

검토용 필터 쿼리 구문은 **다음과** 같습니다.

`(((FileClass="Email") AND (InclusiveType="InclusiveMinus" OR InclusiveType="Inclusive")) OR ((FileClass="Attachment") AND (UniqueInEmailSet="true")) OR ((FileClass="Document") AND (MarkAsRepresentative="Unique")) OR (FileClass="Conversations"))`

다음 목록에서는 필터 쿼리의 결과를 검토 집합에 적용한 후 표시되는 콘텐츠에 대해 설명합니다.

- **전자 메일.** 포함 또는 포함Minus로 표시된 **항목을 표시됩니다.**  포괄 항목은 전자 메일 스레드의 최종 메시지입니다. 전자 메일 스레드의 모든 이전 콘텐츠가 포함되어 있습니다. 전자 메일 스레드의 특정 메시지와 연결된 하나 이상의 첨부 파일이 포함된 포괄 제외. 검토자는 포괄 제외 값을 사용하여 첨부 파일이 연결된 전자 메일 스레드의 특정 메시지를 확인할 수 있습니다.

- **첨부 파일.** 동일한 전자 메일 집합에서 중복된 첨부 파일을 필터합니다. 전자 메일 스레드에서 고유한 첨부 파일만 표시됩니다.

- **문서 및 기타**. 중복 문서를 필터로 작성합니다. 검토 집합에서 고유한 문서만 표시됩니다.

- **Teams 대화 .** 검토 Teams (및 Yammer) 대화가 표시됩니다.

포괄 형식 및 문서 고유성에 대한 자세한 내용은 에서 전자 메일 [스레딩을 Advanced eDiscovery.](email-threading-in-advanced-ediscovery.md)

> [!NOTE]
> 2021년 [11월](advanced-ediscovery-large-cases.md)4일  Advanced eDiscovery 형식의 공개 미리 보기에서 검토용 필터 쿼리는 2021년 11월 4일 Teams 만들어진 검토 집합에 대한 Teams 대화를 반환하지 않습니다. 이 문제가 해결되었습니다. 즉, 검토용 쿼리를  검토 집합에 다시 적용하면 모든 검토 대화가 포함되어 있기 때문에 필터 쿼리와 일치하는 더 Teams 수 있습니다.

## <a name="analytics-report"></a>분석 보고서

검토 집합에 대한 분석 보고서를 보는 방법:

1. 검토 집합을 열 수 있습니다.

2. 분석 **보고서**  >  **표시를 클릭합니다.**

분석 **보고서에는** 분석의 7개 구성 요소가 있습니다.

- **대상 인구:** 검토 집합에 있는 전자 메일 메시지, 첨부 파일 및 느슨한 문서의 수입니다.

- **문서(첨부** 파일 제외): 피벗인 느슨한 문서 수, 피벗의 거의 중복에 가까운 고유 문서 또는 다른 문서의 정확한 복제본 수입니다.

- **전자 메일:** 포괄, 포괄 복사본, 포괄 마이너스 또는 위 없음으로 표시된 전자 메일 메시지 수입니다.

- **첨부 파일:** 검토 집합에 있는 다른 전자 메일 첨부 파일과 고유하거나 중복되는 전자 메일 첨부 파일 수입니다.

- **파일 형식별로 문서 번호를 매기기:** 파일 확장명으로 식별되는 파일 수입니다.

- **원본을 통해 문서 수:** 원본 데이터 원본의 콘텐츠 요약입니다.

- **프로세스별로 집계된 문서:** 검토 집합 프로세스의 콘텐츠 요약입니다. 
