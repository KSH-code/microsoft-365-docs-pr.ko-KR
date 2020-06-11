---
title: 고급 eDiscovery 사례에 비 custodial 데이터 원본 추가
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
ROBOTS: NOINDEX, NOFOLLOW
description: 고급 eDiscovery 사례에 custodial 되지 않은 데이터 원본을 추가 하 고 데이터 원본을 유지할 수 있습니다. Custodial가 아닌 데이터 원본은 다시 인덱싱되 며 부분적으로 인덱싱된 콘텐츠가 완전히 처리 되 고 신속 하 게 검색 가능 하도록 하기 위해 다시 처리할 수 있습니다.
ms.openlocfilehash: 618d39bfb7be6cd260c88cdf4c57501747f440f1
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695507"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>고급 eDiscovery 사례에 비 custodial 데이터 원본 추가

고급 eDiscovery 사례에서는 경우에 따라 Microsoft 365 데이터 원본을 custodian에 연결 하는 사용자의 요구 사항을 충족 하지 않는 것이 좋습니다. 그러나 데이터를 검색 하 고, 검토 집합에 추가한 다음 검토할 수 있도록 반드시 사례와 연결 해야 할 수도 있습니다. *Custodial이 아닌 데이터 원본을* 호출 하는 새로운 기능을 사용 하면 데이터를 custodian에 연결 하지 않고도 사례에 데이터를 추가할 수 있습니다. 또한 custodian와 연결 된 데이터에 사용할 수 있는 custodial 데이터에 동일한 고급 eDiscovery 기능이 적용 됩니다. Custodial 되지 않은 데이터에 적용할 수 있는 가장 유용한 두 가지 기능은 보류 상태로 설정 하 고 [고급 인덱싱을](indexing-custodian-data.md)사용 하 여 처리 하는 것입니다.

## <a name="add-a-non-custodial-data-source"></a>비 custodial 데이터 원본 추가

고급 eDiscovery 사례에서 custodial가 아닌 데이터 원본을 추가 하 고 관리 하려면 다음 단계를 수행 합니다.

1. **고급 eDiscovery** 홈 페이지에서 데이터를 추가 하려는 사례를 클릭 합니다.

2. **원본** 페이지에서 **데이터 위치** 탭을 클릭 한 다음 **데이터 위치 추가**를 클릭 합니다.

3. **데이터 위치 추가** 를 클릭 하 고 사례에 추가할 데이터 원본을 선택 합니다. 사서함과 사이트를 여러 개 추가할 수 있습니다.

4. 마법사의 **위치 선택** 페이지에서 사서함 이나 사이트 (또는 둘 다)를 사례에 custodial 하지 않는 데이터 원본으로 추가 합니다.

5. 데이터 원본을 추가한 후 **다음**을 클릭 합니다.

6. **위치 유지** 페이지에서 관련 확인란을 선택 하거나 선택을 취소 하 여 보류 상태로 설정할 데이터 원본을 선택 합니다.

7. 보류 선택을 확인 한 후 **제출을**클릭 합니다.

   추가한 각 custodial 데이터 원본이 **데이터 원본** 페이지에 나열 됩니다.

   또한 대/소문자를 구분 **하는 작업 탭에** *custodial 되지 않은 데이터 다시 인덱싱* 작업을 만들고 표시 합니다. 작업을 만든 후에는 초기화 된 고급 인덱싱 프로세스와 데이터 원본을 다시 인덱싱합니다.

## <a name="managing-the-hold-on-non-custodial-data-sources"></a>비 custodial 데이터 원본에 대 한 보류 관리

Custodial이 아닌 데이터 원본에 대 한 보류를 설정 하면 사례에 대 한 custodial 데이터 원본이 모두 포함 된 보류 정책이 자동으로 만들어집니다. Custodial 되지 않은 추가 데이터 원본을 보존 하면이 보류 정책에 추가 됩니다.

1. 사례 **홈** 페이지에서 **보류** 탭을 클릭 합니다.

2. **보류** 페이지에서 **Ncdshold- \<GUID\> **를 클릭 하 고 GUID 값은 사례에 대해 고유 합니다.

3. 플라이 아웃 페이지에서 **보류 편집** 을 클릭 하 여 보류 중인 custodial 않은 모든 데이터 원본을 확인 합니다.

Custodial이 아닌 데이터 원본에 대해 수행할 수 있는 관리 작업은 다음과 같습니다.

- 이 보류를 편집 하 여 사례에서 모든 비 custodial 데이터 원본에 적용 되는 쿼리 기반 보존을 만들 수 있습니다.

- 보류에서 custodial가 아닌 데이터 원본을 해제할 수 있습니다. 데이터 원본을 해제 해도 비 custodial 데이터 원본이 사례에서 제거 되지는 않습니다. 데이터 원본에 있던 보류만 제거 합니다.
