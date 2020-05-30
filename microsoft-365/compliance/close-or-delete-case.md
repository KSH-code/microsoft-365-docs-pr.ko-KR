---
title: 사례 닫기 또는 삭제
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
description: 고급 eDiscovery 사례에서 지 원하는 조사 또는 법적 사례가 종료 되거나 삭제 된 경우 수행 되는 작업에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419064"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>고급 eDiscovery 사례 닫기 또는 삭제

고급 eDiscovery 사례에서 지 원하는 법적 사례 또는 조사가 완료 되 면 대/소문자를 닫거나 삭제할 수 있습니다. 종료 된 케이스를 다시 열 수도 있습니다.

## <a name="close-a-case"></a>사례 닫기

고급 eDiscovery 사례를 닫을 때 수행 되는 작업은 다음과 같습니다.

- 대/소문자에 보류 중인 콘텐츠 위치가 포함 되어 있으면 해당 보류를 해제 합니다. 보류를 해제 하면 보류 중인 콘텐츠 위치에 30 일 유예 기간 ( *지연 대기*)이 적용 됩니다. 이를 통해 콘텐츠가 즉시 삭제 되는 것을 방지 하 고 관리자에 게 지연 보존 기간이 만료 된 후 영구적으로 삭제 되는 콘텐츠를 검색 하거나 복구할 수 있는 기회를 제공 합니다. 자세한 내용은 [eDiscovery 보류에서 콘텐츠 위치 제거](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)를 참조 하세요.

- 사례를 닫으면 해당 사례와 연결 된 보류만 해제 됩니다. 콘텐츠 위치 (예: 소송 보존, 코어 eDiscovery 보류, 다른 고급 eDiscovery 사례의 보류 등)에 다른 보류가 있는 경우 해당 보류는 계속 유지 됩니다.

- 이 사례는 여전히 Microsoft 365 준수 센터의 eDiscovery 페이지에 나열 됩니다. 닫힌 사례에 대 한 세부 정보, 보류, 검색 및 구성원은 그대로 유지 됩니다.

- 해당 사례가 닫힌 후에 대/소문자를 편집할 수 있습니다. 예를 들어 고급 eDiscovery에서 구성원을 추가 하거나 제거 하 고, 검색을 만들고, 검색 결과를 내보내고, 검색 결과를 준비할 수 있습니다. 활성 사례와 닫힌 사례의 주요 차이점은 사례를 닫을 때 보류가 해제 된다는 점입니다.

사례를 닫으려면:

1. **고급 eDiscovery** 페이지에서 닫으려는 사례를 선택 합니다.

2. **설정** 탭의 **사례 정보**에서 **선택을**클릭 합니다.

3. **대/소문자 닫기를**클릭 합니다.

   닫기 프로세스를 완료 하는 데 최대 60 분이 걸릴 수 있습니다.

## <a name="reopen-a-closed-case"></a>닫힌 사례 다시 열기

고급 eDiscovery 사례를 다시 열면 서비스 케이스가 종료 될 때 적용 된 모든 보류는 자동으로 복원 되지 않습니다. 사례를 다시 연 후에는 **보류** 탭으로 이동 하 여 이전 보류를 켜야 합니다. 보류를 설정 하려면이 옵션을 선택 하 여 플라이 아웃 페이지를 표시 하 고 **상태** 전환 설정을 **켜기**로 설정 합니다.

닫힌 사례를 다시 열려면:

1. **고급 eDiscovery** 페이지에서 다시 열 사례를 선택 합니다.

2. **설정** 탭의 **사례 정보**에서 **선택을**클릭 합니다.

3. **대/소문자 다시 열기**를 클릭 합니다.

   다시 여는 프로세스를 완료 하는 데 최대 60 분이 걸릴 수 있습니다.

## <a name="delete-a-case"></a>사례 삭제

활성 및 닫힌 Advanced eDiscovery 사례를 모두 삭제할 수 있습니다. 사례를 삭제 하면 해당 사례와 관련 된 모든 구성 요소 (예: custodians, communications, 검색, 검토 집합 및 내보내기 작업)가 삭제 됩니다. Microsoft 365 준수 센터의 **고급 eDiscovery** 페이지에 있는 사례 목록에서 사례를 제거 합니다. 삭제 된 사례는 복구 하거나 다시 열 수 없습니다.

> [!NOTE]
> 데이터 유출 시나리오에서 검토 집합의 항목을 제거 하는 유일한 방법은 Advanced eDiscovery 사례를 삭제 하는 것입니다. 기타 "검색 및 제거" 방법은 검토 집합에서 항목을 제거 하지 않습니다.

사례 (활성 또는 마감 여부)를 삭제 하려면 먼저 사례와 연결 된 *모든* 보류를 삭제 해야 합니다. 이는 상태가 **Off**인 삭제 보류를 포함 합니다.

사례와 연결 된 보류를 삭제 하려면:

1. 삭제 하려는 고급 eDiscovery 사례의 **보류** 탭을 이동 합니다.

2. 삭제할 보류를 클릭 합니다.

3. 플라이 아웃 페이지에서 **보류 삭제**를 클릭 합니다.

사례를 삭제 하려면 다음을 수행 합니다.

1. **고급 eDiscovery** 페이지에서 삭제할 사례를 선택 합니다.

2. **설정** 탭의 **사례 정보**에서 **선택을**클릭 합니다.

3. **대/소문자 삭제**를 클릭 합니다.
