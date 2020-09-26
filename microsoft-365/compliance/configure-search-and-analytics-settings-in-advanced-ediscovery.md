---
title: 검색 및 분석 설정 구성-고급 eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom: seo-marvel-mar2020
description: 사례에서 모든 검토 설정에 적용 되는 고급 eDiscovery 설정을 구성 합니다. 여기에는 분석 및 광학 인식을 위한 설정이 포함 됩니다.
ms.openlocfilehash: dfacab79f635a817b127614f524d00b0297981fb
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277085"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>고급 eDiscovery에서 검색 및 분석 설정 구성

각 고급 eDiscovery 사례에 대 한 설정을 구성 하 여 다음 기능을 제어할 수 있습니다.

- 유사 중복 및 전자 메일 스레딩

- 테마

- 자동 생성 검토 집합 쿼리

- 텍스트 무시

- 광학 인식

사례에 대 한 검색 및 분석 설정을 구성 하려면:

1. **고급 eDiscovery** 페이지에서 사례를 선택 합니다.

2. **설정** 탭의 **검색 & 분석**에서 **선택을**클릭 합니다.

   사례 설정 페이지가 표시 됩니다. 이러한 설정은 사례에서 모든 검토 집합에 적용 됩니다.

   ![고급 eDiscovery 사례에 대 한 분석 및 검색 설정 구성](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>유사 중복 및 전자 메일 스레딩

이 섹션에서는 중복 검색, 중복 검색 및 전자 메일 스레딩에 대 한 매개 변수를 설정할 수 있습니다. 자세한 내용은 [Near 중복 검색](near-duplicates.md) 및 [전자 메일 스레딩](email-threading.md)를 참조 하세요.

- **거의 중복/전자 메일 스레딩:** 검토 집합의 데이터에 대 한 분석을 실행 하는 경우 설정, 중복 검색, 중복 검색 및 전자 메일 스레딩은 워크플로의 일부로 포함 됩니다.

- **문서 및 전자 메일 유사성 임계값:** 두 문서에 대 한 유사성 수준이 임계값 보다 높은 경우 두 문서가 동일한 복제 세트에 저장 됩니다.

- **최소/최대 단어 수:** 이러한 설정은 거의 모든 단어 개수 이상 및 최대 단어 수를 포함 하는 문서 에서만 중복 되는 항목 및 전자 메일 스레딩 분석이 수행 되도록 지정 합니다.

## <a name="themes"></a>테마

이 섹션에서는 테마에 대 한 매개 변수를 설정할 수 있습니다. 자세한 내용은 [테마](themes-in-advanced-ediscovery.md)를 참조 하십시오.

- **테마:** 이 옵션이 설정 되 면 검토 집합의 데이터에 대 한 분석을 실행할 때 테마 클러스터링이 워크플로의 일부로 수행 됩니다.

- **최대 테마 수:** 검토 집합의 데이터에 대 한 분석을 실행할 때 생성 될 수 있는 최대 테마 수를 지정 합니다.

- **테마에 숫자 포함:** 이 옵션이 설정 되 면 테마를 생성할 때 주제를 식별 하는 번호가 포함 됩니다. 

- **최대 테마 수를 동적으로 조정 합니다.** 특정 상황에서는 검토 집합에 문서가 충분히 부족 하 여 원하는 수의 테마를 생성할 수 없습니다. 이 설정을 사용 하도록 설정 하면 고급 eDiscovery에서 최대 테마 수를 적용 하는 대신 최대 테마 수를 동적으로 조정 합니다.

## <a name="review-set-query"></a>집합 쿼리 검토

**분석 후에 저장 된 검색을 검토용으로 자동으로 만들기** 확인란을 선택한 경우 Advanced eDiscovery autogenerates review set Query for review를 선택 **합니다.** 

![자동 생성 된 검토 쿼리](../media/AeDForReviewQuery.png)

이 쿼리는 기본적으로 검토 집합에서 중복 된 항목을 필터링 합니다. 이렇게 하면 검토 집합의 고유한 항목을 검토할 수 있습니다. 이 쿼리는 사례에서 검토 집합에 대 한 분석을 실행 한 경우에만 만들어집니다. 자세한 내용을 보려면 set queries (검토 집합) [에서 데이터 쿼리](review-set-search.md)를 참고 하십시오.

## <a name="ignore-text"></a>텍스트 무시

전자 메일의 내용에 관계 없이 전자 메일 메시지에 추가 되는 긴 고 지 사항 등 특정 텍스트가 분석 품질을 감소 시키는 경우가 있습니다. 무시 해야 하는 텍스트를 알고 있는 경우 텍스트 문자열과 해당 텍스트를 제외 해야 하는 분석 기능 (거의 중복, 전자 메일 스레딩, 테마 및 관련성)을 지정 하 여 분석에서 제외할 수 있습니다. 정규식 (RegEx)을 무시 된 텍스트로 사용 하는 기능도 지원 됩니다. 

## <a name="optical-character-recognition-ocr"></a>OCR (광학 문자 인식)

이 설정을 사용 하도록 설정 하면 이미지 파일에서 OCR 처리가 실행 됩니다. OCR 처리는 다음과 같은 상황에서 실행 됩니다.

- Custodians 및 [비 custodial 데이터 원본이](non-custodial-data-sources.md) 사례에 추가 되는 경우 OCR 처리는 고급 인덱싱 프로세스 중에 수행 됩니다. 즉, 검색 조건과 일치 하는 이미지 파일의 텍스트가 컬렉션 검색에서 반환 됩니다.

- Custodian에 연결 되지 않고 비 custodial 데이터 원본의 사례에 추가 되는 다른 데이터 원본의 콘텐츠가 검토 집합에 추가 되는 경우

데이터를 검토 집합에 추가한 후에는 이미지 텍스트를 검토, 검색, 태그 지정 및 분석할 수 있습니다. 검토 집합에서 선택한 이미지 파일의 텍스트 뷰어에서 추출한 텍스트를 볼 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [보유자 데이터의 고급 인덱싱](indexing-custodian-data.md)

- [검색 결과를 검토 집합에 추가](add-data-to-review-set.md#optical-character-recognition)

- [지원 되는 이미지 파일 형식](supported-filetypes-ediscovery20.md#image)
