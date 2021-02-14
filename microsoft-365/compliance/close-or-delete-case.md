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
description: Advanced eDiscovery 사례에서 지원되는 조사 또는 법적 사례가 닫히거나 삭제될 때 발생하는 일에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419064"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Advanced eDiscovery 사례 닫기 또는 삭제

Advanced eDiscovery 사례에서 지원되는 법적 사례 또는 조사가 완료되면 사례를 닫거나 삭제할 수 있습니다. 닫힌 사례를 다시 열 수 있습니다.

## <a name="close-a-case"></a>사례 닫기

Advanced eDiscovery 사례를 닫을 때 발생하는 문제는 다음과 같습니다.

- 사례에 보류된 콘텐츠 위치가 포함되어 있는 경우 해당 보류가 해제됩니다. 보류가 해제된 후 30일의 유예 기간(지연 보류)이 보류된 콘텐츠 위치에 적용됩니다. 이렇게 하면 콘텐츠가 즉시 삭제되는 것을 방지하고 관리자는 지연 보류 기간이 만료된 후 영구적으로 삭제되는 콘텐츠를 검색하거나 복구할 수 있습니다. 자세한 내용은 [eDiscovery](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)보류에서 콘텐츠 위치 제거를 참조하세요.

- 사례를 닫을 경우 해당 사례와 연결된 보류만 해제됩니다. 다른 보류가 콘텐츠 위치에 있는 경우(예: 소송 보유, Core eDiscovery 보류 또는 다른 Advanced eDiscovery 사례의 보류) 해당 보류는 계속 유지 관리됩니다.

- 사례는 Microsoft 365 규정 준수 센터의 eDiscovery 페이지에 계속 나열됩니다. 마감된 사례의 세부 정보, 보류, 검색 및 구성원은 유지됩니다.

- 사례를 닫은 후 편집할 수 있습니다. 예를 들어 고급 eDiscovery에서 구성원을 추가 또는 제거하고, 검색을 만들고, 검색 결과를 내보내고, 분석을 위해 검색 결과를 준비할 수 있습니다. 활성 사례와 닫힌 사례의 주요 차이점은 사례가 닫히면 보류가 해제되어 있는 것입니다.

사례를 닫는 경우:

1. Advanced **eDiscovery** 페이지에서 닫을 사례를 선택합니다.

2. 설정 **탭의** **대소문자 정보에서** 선택을 **클릭합니다.**

3. 닫기 **사례를 클릭합니다.**

   닫는 프로세스가 완료될 때 최대 60분이 걸릴 수 있습니다.

## <a name="reopen-a-closed-case"></a>닫힌 사례 다시 열기

Advanced eDiscovery 사례를 다시 열면 사례가 닫혀 있을 때 수행된 보류가 자동으로 다시 설정되지 않습니다. 사례가 다시 열리면 보류 탭으로 이동하여  이전 보류를 켜야 합니다. 보류를 켜고 플라이아웃 페이지를 표시하려면 해당 페이지를  선택한 다음 상태 토글을 **켜기로 설정하십시오.**

닫힌 사례를 다시 열기 위해

1. Advanced **eDiscovery** 페이지에서 다시 열 사례를 선택합니다.

2. 설정 **탭의** **대소문자 정보에서** 선택을 **클릭합니다.**

3. 다시 **열기 사례를 클릭합니다.**

   다시 열기 프로세스를 완료하는 데 최대 60분이 걸릴 수 있습니다.

## <a name="delete-a-case"></a>사례 삭제

활성 및 닫힌 Advanced eDiscovery 사례를 모두 삭제할 수 있습니다. 사례를 삭제하면 정보주 목록, 커뮤니케이션, 검색, 검토 집합 및 내보내기 작업과 같은 사례와 관련된 모든 구성 요소가 삭제됩니다. 사례는 Microsoft 365 규정 준수 센터의 **Advanced eDiscovery** 페이지에 있는 사례 목록에서 제거됩니다. 삭제된 사례는 복구하거나 다시 열 수 없습니다.

> [!NOTE]
> 데이터 유출 시나리오에서 검토 집합의 항목을 제거하는 유일한 방법은 Advanced eDiscovery 사례를 삭제하는 것입니다. 다른 "검색 및 삭제" 메서드는 검토 집합에서 항목을 제거하지 않습니다.

사례를 삭제하려면 먼저 사례와 연결된 모든 보류를  삭제해야 합니다. 여기에는 해제 상태의 보류 삭제가 **포함됩니다.**

사례와 연결된 보류를 삭제하려면

1. 삭제할 **Advanced** eDiscovery 사례의 보류 탭으로 이동하십시오.

2. 삭제할 보류를 클릭합니다.

3. 플라이아웃 페이지에서 보류 **삭제를 클릭합니다.**

사례를 삭제하려면

1. Advanced **eDiscovery** 페이지에서 삭제할 사례를 선택합니다.

2. 설정 **탭의** **대소문자 정보에서** 선택을 **클릭합니다.**

3. 사례 **삭제를 클릭합니다.**
