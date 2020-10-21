---
title: 고급 eDiscovery에 대 한 CJK/더블 바이트 지원
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365의 고급 eDiscovery에서 더블 바이트 문자 집합을 사용 하는 중국어, 일본어 및 한국어 (CJK) 언어를 지 원하는 방법에 대해 알아봅니다.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626942"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>고급 eDiscovery에 대 한 CJK 언어 지원

고급 eDiscovery에서는 검토 집합의 다음 고급 시나리오에 대해 더블 바이트 문자 집합 언어 (예: *CJK* 언어로 통칭 되는 중국어 간체, 중국어 번체, 일본어 및 한국어 포함)를 지원 합니다.

- [검토 집합에서 데이터를 쿼리할](review-set-search.md)때

- [검토 집합의 문서에 태그](tagging-documents.md)를 추가할 때

- 근접 중복 검색, 전자 메일 스레딩 및 테마 분석을 사용 하 여 [검토 집합의 사례 데이터를 분석 하는](analyzing-data-in-review-set.md) 경우

## <a name="frequently-asked-questions"></a>자주하는 질문

**CJK 문자가 포함 된 항목을 수집 하기 위해 검색을 만드는 방법은 무엇 인가요?**

고급 eDiscovery에서 콘텐츠를 검색할 때 [키워드 검색](building-search-queries.md#keyword-searches), [키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md) 에 CJK 문자를 사용할 수 있습니다. 중요 eDiscovery 및 콘텐츠 검색에서 콘텐츠를 검색할 때 CJK 문자 검색도 지원 됩니다.

Microsoft **는 부울 연산자,** **OR**, **NOT**및 **NEAR**을 비롯 하 여 모든 [검색 운영자](keyword-queries-and-search-conditions.md#search-operators) 및 [검색 조건](keyword-queries-and-search-conditions.md#search-conditions)에 대해 CJK 지원을 제공 합니다.

콘텐츠 위치 또는 항목에 CJK 문자가 포함 되어 있지만 검색 결과에 결과가 반환 되지 않으면 쿼리 언어-국가/지역 아이콘을 클릭 합니다. ![콘텐츠 검색의 쿼리 언어-국가/지역 아이콘](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) 해당 검색에 해당 하는 언어-국가 문화권 코드 값을 선택 합니다. 기본 언어/지역은 중립입니다.

**한 번에 여러 언어를 검색할 수 있나요?**

검색 시나리오에 따라 다릅니다.

- 고급 eDiscovery의 [검토 집합에서 데이터를 쿼리할](review-set-search.md) 때 여러 언어를 검색할 수 있습니다.

- [검색을 만들어 데이터를 수집](create-search-to-collect-data.md)하는 경우에는 대상으로 지정 하는 각 언어에 대해 별도의 검색을 만듭니다. 예를 들어, 중국어와 한국어가 모두 포함 된 문서를 검색 하는 경우 첫 번째 쿼리에 대해 중국어를 선택 하 고 두 번째 쿼리에 대해 한국어를 선택 합니다.

**검토 집합에서 쿼리에 사용할 언어를 선택 하는 쿼리 언어-국가/지역 아이콘이 표시 되지 않습니다. 검토 집합 검색에서 쿼리 언어를 지정 하려면 어떻게 해야 합니까?**

검토 집합 쿼리의 경우 문서 언어를 지정할 필요가 없습니다. 검토 집합에 콘텐츠를 추가 하는 경우 고급 eDiscovery에서는 문서 언어를 자동으로 검색 합니다. 이렇게 하면 검토 집합에서 쿼리 결과를 최적화 하는 데 도움이 됩니다.

**[파일 메타 데이터](view-documents-in-review-set.md#file-metadata)에서 검색 된 언어를 확인할 수 있나요?**

아니요, 파일 메타 데이터에 검색 된 언어가 표시 되지 않습니다.

**검토 집합에서 문서 언어를 기준으로 필터링 할 수**있습니까?

아니요, 검토 집합에서 문서 언어를 필터링, 정렬 또는 검색할 수 없습니다.

**검토 설정 시나리오에 대해이 CJK 릴리스가 기존 검색 및 검토 집합에 영향을 줍니까?**

아니요, 기존 검색 및 검토 집합이 모두 변경 되지 않습니다. 기존 데이터를 다시 인덱싱할 필요는 없으며 영어 텍스트에 대 한 검색 결과는 동일 합니다.

**표시 언어를 중국어, 일본어 또는 한국어로 변경 하려면 어떻게 해야 합니까?**

표시 언어 및 표준 시간대를 변경 하는 방법에 대 한 자세한 내용은 [how to set language and region settings For Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)을 참조 하십시오.

## <a name="known-issues"></a>알려진 문제

- OCR은 이미지 파일에서 CJK 문자를 지원 하지 않습니다.

- [주석 보기](view-documents-in-review-set.md#annotate-view) 의 전자 메일 파일 (예: * .eml 및 * .msg)은 CJK 언어에서 지원 되지 않습니다.

- [텍스트 보기](view-documents-in-review-set.md#text-view) 의 검색 방문 횟수 강조 표시는 CJK 언어에서 지원 되지 않습니다.

- 데이터를 분석 하는 데 사용 되는 [관련성 모듈](using-relevance.md) 은 CJK 언어를 지원 하지 않습니다.

- [쿼리 기반 보류](managing-holds.md#manage-non-custodial-holds) 는 CJK 언어에서 지원 되지 않습니다. 
