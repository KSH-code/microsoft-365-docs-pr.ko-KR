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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 사례를 분석할 때 문서 집합을 구성하는 데 사용할 수 있는 Advanced eDiscovery 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190162"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>다음의 검토 집합에서 데이터 Advanced eDiscovery

수집된 문서의 수가 크면 모두 검토하기 어려울 수 있습니다. Advanced eDiscovery 정보를 손실하지 않고도 검토할 문서의 양을 줄이고 문서를 공동으로 구성하는 데 도움이 되는 다양한 도구를 제공합니다. 이러한 기능에 대한 자세한 내용은 다음을 참조합니다.

- [중복에 가까운 검색](near-duplicate-detection-in-advanced-ediscovery.md)

- [전자 메일 스레드](email-threading-in-advanced-ediscovery.md)

- [테마](themes-in-advanced-ediscovery.md)

검토 집합의 데이터를 분석하는 경우:

1. 사례에 대한 분석 설정을 구성합니다. 자세한 내용은 검색 및 분석 [설정 구성을 참조하세요.](configure-search-and-analytics-settings-in-advanced-ediscovery.md)

2. 분석할 리뷰 집합을 열 수 있습니다.

3. 검토 **집합 관리를 클릭합니다.**

4. 검토 **집합에 대한 분석 실행을 클릭합니다.**

사례의 작업 탭에서 분석  진행률을 확인할 수 있습니다.

 분석이 완료되면 분석 보고서를 보고, 분석 출력에 대한 검토 집합 내에서 쿼리를 실행하고(검토 집합 내의 쿼리 [참조)](review-set-search.md)특정 문서의 관련 문서를 볼 수 있습니다(검토 집합의 데이터 검토 [참조).](reviewing-data-in-review-set.md)

## <a name="analytics-report"></a>분석 보고서

검토 집합에 대한 분석 보고서를 보는 방법:

1. 검토 집합을 열 수 있습니다.

2. 검토 **집합 관리를 클릭합니다.**

3. 보고서 **보기 를 클릭합니다.**

보고서에는 분석의 7개 구성 요소가 있습니다.

- **대상 인구:** 검토 집합에 있는 전자 메일 메시지, 첨부 파일 및 느슨한 문서의 수입니다.

- **문서(첨부** 파일 제외): 피벗인 느슨한 문서 수, 피벗의 거의 중복에 가까운 고유 문서 또는 다른 문서의 정확한 복제본 수입니다.

- **전자 메일:** 포괄 복사본, 포괄 복사본 또는 그 어느 것도 포함하지 않은 전자 메일 메시지의 수입니다.

- **첨부 파일:** 검토 집합에 있는 다른 전자 메일 첨부 파일과 고유하거나 중복되는 전자 메일 첨부 파일 수입니다.

- **유형별로 파일 수:** 파일 확장명으로 식별되는 파일 수입니다.

- **원본을 통해 문서 수:** 원본 데이터 원본의 콘텐츠 요약입니다.

- **프로세스별로 집계된 문서:** 검토 집합 프로세스의 콘텐츠 요약입니다. 
