---
title: 검색 및 분석 설정 구성 - Advanced eDiscovery
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
description: 모든 Advanced eDiscovery 적용하는 모든 검토 설정을 구성합니다. 여기에는 분석 및 광학 문자 인식에 대한 설정이 포함됩니다.
ms.openlocfilehash: 4d46ca4dfb5897c7b262858ab7c955221016e3c7
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184251"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>검색 및 분석 설정 구성 Advanced eDiscovery

각 사례에 대한 설정을 구성하여 Advanced eDiscovery 기능을 제어할 수 있습니다.

- 근사 중복 및 전자 메일 스레드

- 테마

- 자동 재생 검토 설정 쿼리

- 텍스트 무시

- 광학 문자 인식

사례에 대한 검색 및 분석 설정을 구성

1. **고급 eDiscovery** 페이지에서 사례를 선택합니다.

2. **검색 및 분석** 의 **설정** 탭에서 **선택** 을 클릭합니다.

   사례 설정 페이지가 표시됩니다. 이러한 설정은 사례의 모든 검토 집합에 적용됩니다.

   ![사례에 대한 분석 및 Advanced eDiscovery 구성합니다.](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>근사 중복 및 전자 메일 스레드

이 섹션에서는 중복 검색, 중복에 가까운 검색 및 전자 메일 스레딩에 대한 매개 변수를 설정할 수 있습니다. 자세한 내용은 중복에 [가까운](near-duplicate-detection-in-advanced-ediscovery.md) 검색 및 [전자 메일 스레딩을 참조하세요.](email-threading-in-advanced-ediscovery.md)

- **가까운 중복/전자 메일 스레딩:** 이 기능을 설정하면 검토 집합의 데이터에 대한 분석을 실행할 때 중복 검색, 중복에 가까운 검색 및 전자 메일 스레딩이 워크플로의 일부로 포함됩니다.

- **문서 및 전자 메일 유사성 임계값:** 두 문서의 유사성 수준이 임계값을 초과하면 두 문서가 동일한 중복 집합에 저장됩니다.

- **최소/최대 단어 수:** 이러한 설정은 최소한 최소한의 단어와 최대 단어 수가 있는 문서에서만 거의 중복 및 전자 메일 스레딩 분석을 수행하게 지정합니다.

## <a name="themes"></a>테마

이 섹션에서는 테마에 대한 매개 변수를 설정할 수 있습니다. 자세한 내용은 [테마를 참조하세요.](themes-in-advanced-ediscovery.md)

- **테마:** 이 기능을 설정하면 검토 집합의 데이터에 대한 분석을 실행할 때 테마 클러스터링이 워크플로의 일부로 수행됩니다.

- **최대 테마 수:** 검토 집합의 데이터에 대한 분석을 실행할 때 생성될 수 있는 최대 테마 수를 지정합니다.

- **테마에 숫자 포함:** 켜져 있는 경우 테마를 생성하는 경우 테마를 식별하는 숫자가 포함됩니다. 

- **최대 테마 수를 동적으로 조정합니다.** 특정 상황에서는 검토 집합에 원하는 수의 테마를 생성하기에 충분한 문서가 없는 경우도 있습니다. 이 설정을 사용하도록 설정하면 고급 eDiscovery에서 최대 테마 수를 적용하려고 시도하지 않고 최대 테마 수를 동적으로 조정합니다.

## <a name="review-set-query"></a>쿼리 집합 검토

분석 후  저장된 검토용 검색 자동 만들기 확인란을 선택하면 Advanced eDiscovery 검토용 집합 쿼리를 자동으로 **생성합니다.** 

![For Review 자동 작성된 쿼리입니다.](../media/AeDForReviewQuery.png)

이 쿼리는 기본적으로 검토 집합에서 중복 항목을 검색합니다. 이렇게 하면 검토 집합의 고유한 항목을 검토할 수 있습니다. 이 쿼리는 사례에 있는 검토 집합에 대한 분석을 실행할 때만 만들어집니다. 검토 집합 쿼리에 대한 자세한 내용은 검토 집합의 데이터 [쿼리를 참조하세요.](review-set-search.md)

## <a name="ignore-text"></a>텍스트 무시

전자 메일의 콘텐츠에 관계없이 전자 메일 메시지에 추가되는 긴 고지와 같이 특정 텍스트가 분석 품질을 하할 수 있는 상황이 있습니다. 무시해야 하는 텍스트에 대해 알고 있는 경우, 텍스트 문자열과 텍스트에서 제외해야 하는 분석 기능(근사 중복, 전자 메일 스레드, 테마 및 관련성)을 지정하여 분석에서 제외할 수 있습니다. 정규식(RegEx)을 무시된 텍스트로 사용할 수도 있습니다.

## <a name="optical-character-recognition-ocr"></a>광학 문자 인식(OCR)

이 설정을 설정하면 이미지 파일에서 OCR 처리가 실행됩니다. OCR 처리는 다음과 같은 상황에서 실행됩니다.

- 보호자 및 비보조 [](non-custodial-data-sources.md) 데이터 원본이 사례에 추가되는 경우 이미지 파일에 OCR을 적용하면 컬렉션 중에 해당 파일의 텍스트를 검색할 수 있습니다. OCR 처리는 고급 인덱싱 [프로세스 중에 수행됩니다.](indexing-custodian-data.md) OCR은 고급 인덱싱 중에 처리된 항목에만 실행됩니다. 예를 들어 고급 인덱싱 중에 부분적으로 인덱싱되거나 다른 인덱싱 오류가 있는 큰 PDF 파일을 처리하면 파일에 OCR도 적용됩니다. 즉, OCR 처리는 고급 인덱싱 프로세스 중에 다시 인덱싱되는 파일에만 발생합니다. 즉, 보안 주관이 사례에 추가되지만 일부 전자 메일 첨부 파일은 고급 인덱싱 중에 처리되지 않는 OCR에 대해 처리되지 않는 상황이 있을 수 있습니다.

- 다른 데이터 원본의 콘텐츠(양도인과 연결되지 않은 데이터 원본의 경우 사례에 추가)가 검토 집합에 추가되는 경우.

데이터가 검토 집합에 추가된 후 이미지 텍스트를 검토, 검색, 태그 지정 및 분석할 수 있습니다. 선택된 이미지 파일의 텍스트 뷰어에서 추출된 텍스트를 검토 집합에서 볼 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [보유자 데이터의 고급 인덱싱](indexing-custodian-data.md)

- [검색 결과를 검토 집합에 추가](add-data-to-review-set.md#optical-character-recognition)

- [지원되는 이미지 파일 형식](supported-filetypes-ediscovery20.md#image)
