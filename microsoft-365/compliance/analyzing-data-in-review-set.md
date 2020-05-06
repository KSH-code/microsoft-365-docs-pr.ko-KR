---
title: 고급 eDiscovery에서 검토 집합의 데이터 분석
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
description: 고급 eDiscovery 사례를 분석할 때 문서 집합을 구성 하는 데 사용할 수 있는 도구에 대해 설명 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 87788e444a5ef671586567510448dab8b9deddcd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033822"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>고급 eDiscovery에서 검토 집합의 데이터 분석

수집 된 문서 수가 크면 검토 하기가 어려울 수 있습니다. 고급 eDiscovery에서는 문서를 분석 하 여 정보 손실 없이 검토할 문서 크기를 줄이고 일관 된 방식으로 문서를 구성 하는 데 도움이 되는 다양 한 도구를 제공 합니다. 이러한 기능에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

- [중복에 가까운 검색](near-duplicates.md)

- [전자 메일 스레드](email-threading.md)

- [테마](themes.md)

검토 집합에서 데이터를 분석 하려면 다음을 수행 합니다.

1. 사례에 대 한 분석 설정을 구성 합니다. 자세한 내용은 [Configure search and analytics settings](configure-search-analytics-settings.md)을 참조 하십시오.

2. 분석 하려는 검토 집합을 엽니다.

3. **검토 설정 관리**를 클릭 합니다.

4. **검토 집합에 대 한 분석 실행을**클릭 합니다.

사례에 대 한 **작업** 탭에서 분석 진행률을 확인할 수 있습니다.

 분석이 완료 되 면 분석 보고서를 보고, 분석 출력에 대 한 검토 집합 내에서 쿼리를 실행 하 고 ( [검토 집합 내의 쿼리](review-set-search.md)참조), 지정 된 문서의 관련 문서를 볼 수 있습니다 ( [검토 설정에서 데이터 검토](reviewing-data-in-review-set.md)참조).

## <a name="analytics-report"></a>분석 보고서

검토 집합에 대 한 분석 보고서를 보려면:

1. 검토 집합을 엽니다.

2. **검토 설정 관리**를 클릭 합니다.

3. **보고서 보기**를 클릭 합니다.

보고서에는 분석을 통해 7 개의 구성 요소가 있습니다.

- **대상 채우기:** 검토 집합에 있는 전자 메일 메시지, 첨부 파일 및 느슨한 문서 수입니다.

- **문서 (첨부 파일 제외):** 피벗, 중복 되는 항목에 거의 고유 하지 않은 문서 또는 다른 문서와 정확히 일치 하는 복제본의 수입니다.

- **전자 메일:** Inclusives, 포함 복사본, 포함 minuses, 또는 없음 중 하나에 해당 하는 전자 메일 메시지의 수입니다.

- **첨부 파일:** 검토 집합에 있는 다른 전자 메일 첨부 파일의 고유 또는 중복 되는 전자 메일 첨부 파일의 수입니다.

- **유형별 파일 수:** 파일 확장명으로 식별 되는 파일 수입니다.

- **출처 별 문서:** 원래 데이터 원본에의 한 콘텐츠 요약입니다.

- **프로세스 별로 집계 된 문서:** 검토 집합 프로세스의 콘텐츠 요약입니다. 
