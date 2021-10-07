---
title: CJK/Double Byte for Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 더블 Advanced eDiscovery 집합을 Microsoft 365, 중국어, 일본어 및 한국어(CJK) 언어를 지원하는 방법을 배워야 합니다.
ms.openlocfilehash: 0d6287afb373c6c1c51ea61de3906ce994590e87
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197620"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>CJK 언어 지원 Advanced eDiscovery

Advanced eDiscovery 검토 집합에서 다음과 같은 고급 시나리오에 대해 더블바트 문자 집합 언어(중국어 간체, 중국어 번체, 일본어 및 *한국어(총체적으로 CJK* 언어라고도 합니다))를 지원합니다.

- 검토 [집합의 데이터를 쿼리할 때](review-set-search.md)

- 검토 [집합에서 문서에 태그를 지정하는 경우.](tagging-documents.md)

- 중복에 [가까운 검색,](analyzing-data-in-review-set.md) 전자 메일 스레딩 및 테마 분석을 사용하여 검토 집합의 사례 데이터를 분석할 때

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**검색을 만들어 CJK 문자가 포함된 항목을 수집하는 방법**

콘텐츠 검색 시 키워드 [검색,](building-search-queries.md#keyword-searches)키워드 [](keyword-queries-and-search-conditions.md) 쿼리 및 검색 조건에 CJK 문자를 사용할 수 Advanced eDiscovery. Core eDiscovery 및 콘텐츠 검색에서 콘텐츠를 검색할 때 CJK 문자 검색도 지원됩니다.

부울 연산자 **AND, OR,** [](keyword-queries-and-search-conditions.md#search-operators) **NOT** 및 NEAR를 비롯한 모든 검색 연산자 및 검색 조건에 대해 CJK 지원을 **제공합니다.** [](keyword-queries-and-search-conditions.md#search-conditions)

콘텐츠 위치 또는 항목에 CJK 문자가 포함되어 있지만 검색에서 결과를 반환하지 않는 경우 쿼리 언어-국가/지역 아이콘을 클릭합니다. ![콘텐츠 검색에서 언어-국가/지역 아이콘을 쿼리합니다.](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) 를 선택하고 검색에 해당하는 언어-국가 문화권 코드 값을 선택합니다. 기본 언어/지역은 중립입니다.

**한에 여러 언어를 검색할 수 있나요?**

검색 시나리오에 따라 다릅니다.

- [2013의 검토 집합에서](review-set-search.md) 데이터를 쿼리할 Advanced eDiscovery 여러 언어를 검색할 수 있습니다.

- 데이터를 [수집하는 검색을](create-search-to-collect-data.md)만들 때 대상으로 하는 각 언어에 대해 별도의 검색을 만들 수 있습니다. 예를 들어 중국어와 한국어가 모두 포함된 문서를 검색하는 경우 첫 번째 쿼리에 대해 중국어를 선택하고 두 번째 쿼리에 대해 한국어를 선택합니다.

**리뷰 집합에서 쿼리에 대한 언어를 선택하는 쿼리 언어-국가/지역 아이콘이 없습니다. 검토 집합 검색에서 쿼리 언어를 지정하는 방법**

검토 집합 쿼리의 경우 문서 언어를 지정할 필요가 없습니다. Advanced eDiscovery 집합에 콘텐츠를 추가할 때 문서 언어를 자동으로 검색합니다. 이렇게 하면 검토 집합에서 쿼리 결과를 최적화하는 데 도움이 됩니다.

**파일 메타데이터에서 검색된 언어를 볼 [수 있나요?](view-documents-in-review-set.md#file-metadata)**

아니요. 파일 메타데이터에서 검색된 언어를 볼 수 없습니다.

**검토 집합의 문서 언어를 사용하여 필터링할 수 있나요?**

아니요. 검토 집합의 문서 언어별로 필터링, 정렬 또는 검색할 수 없습니다.

**검토 집합 시나리오에 대한 이 CJK 릴리스가 기존 검색 및 검토 집합에 영향을 미치나요?**

아니요. 기존 검색 및 검토 집합은 변경되지 않습니다. 기존 데이터를 다시 인덱서할 필요가 없습니다. 영어 텍스트의 검색 결과는 동일합니다.

**표시 언어를 중국어, 일본어 또는 한국어로 변경하는 방법**

표시 언어 및 표준 시간대를 변경하는 방법에 대한 자세한 내용은 에 대한 언어 및 지역 설정을 설정하는 [Office 365.](/office365/troubleshoot/access-management/set-language-and-region)

## <a name="known-issues"></a>알려진 문제

- OCR은 이미지 파일의 CJK 문자를 지원하지 않습니다.

- [Annotate](view-documents-in-review-set.md#annotate-view) 보기의 전자 메일 파일(예: *.eml 및 *.msg)은 CJK 언어에 지원되지 않습니다.

- 텍스트 보기의 검색 적중 강조 [표시는](view-documents-in-review-set.md#text-view) CJK 언어에 지원되지 않습니다.

- 데이터를 [분석하는 데](using-relevance.md) 사용되는 중요성 모듈은 CJK 언어를 지원하지 않습니다.

- [CJK](managing-holds.md#manage-non-custodial-holds) 언어에서는 쿼리 기반 보류가 지원되지 않습니다.