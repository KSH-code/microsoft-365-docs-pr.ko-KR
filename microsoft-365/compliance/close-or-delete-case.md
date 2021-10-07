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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery 사례에서 지원되는 조사 또는 법률 사례가 닫히거나 삭제될 때 발생하는 일에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 88e0892bec3f220d9c405f3886c37fa89ad2c647
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158349"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>사례 닫기 또는 Advanced eDiscovery 삭제

Advanced eDiscovery 지원되는 법률 사례 또는 조사가 완료되면 사례를 닫거나 삭제할 수 있습니다. 닫힌 사례를 다시 열 수 있습니다.

## <a name="close-a-case"></a>케이스 종료

다음은 사례를 닫을 때 Advanced eDiscovery 다음과 같습니다.

- 케이스에 보류된 콘텐츠 위치가 포함되어 있는 경우 해당 보류는 해제됩니다. 보류가 해제된 후 30일의 유예 기간(지연 보류)이 보류된 콘텐츠 위치에 적용됩니다. 이렇게 하면 콘텐츠가 즉시 삭제되는 것을 방지할 수 있으며, 관리자는 지연 보류 기간이 만료된 후 영구적으로 삭제되는 콘텐츠를 검색하거나 복구할 수 있습니다. 자세한 내용은 [eDiscovery 보류에서](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)콘텐츠 위치 제거를 참조하세요.

- 케이스를 닫으면 케이스와 연결된 보류 항목만 꺼집니다. 다른 보류가 콘텐츠 위치(예: 소송 보류, Core eDiscovery 보류 또는 다른 Advanced eDiscovery 사례의 보류)에 있는 경우에도 해당 보류는 계속 유지 관리됩니다.

- 사례는 여전히 해당 페이지의 eDiscovery 페이지에 Microsoft 365 규정 준수 센터. 닫힌 케이스의 세부 정보, 보류, 검색 및 구성원은 유지됩니다.

- 사례를 닫은 후 편집할 수 있습니다. 예를 들어 구성원을 추가 또는 제거하고, 검색을 만들고, 검색 결과를 내보내고, 검색 결과에서 분석을 위해 검색 결과를 준비할 Advanced eDiscovery. 활성 케이스와 닫힌 케이스의 주요 차이점은 케이스를 닫을 때 보류가 해제된다는 것입니다.

케이스를 닫으려면

1. **Advanced eDiscovery** 페이지에서 닫을 케이스를 선택합니다.

2. **설정** 탭의 **케이스 정보** 에서 **선택** 을 클릭합니다.

   ![사례 정보 플라이아웃 페이지에 액세스하여 사례 Advanced eDiscovery 액세스합니다.](..\media\AeDSelectCaseInformation.png) 

3. 사례 정보 플라이아웃 페이지의 아래쪽에서 동작 **을** 클릭한 다음 사례 **닫기 를 클릭합니다.** 

   닫기 프로세스를 완료하는 데 최대 60분 정도 걸릴 수 있습니다.

## <a name="reopen-a-closed-case"></a>닫힌 사례 다시 열기

Advanced eDiscovery 사례를 다시 열면 사례를 닫을 때 수행되던 보류가 자동으로 다시 설정되지 않습니다. 사례가 다시 열리면 보류 탭으로 이동하여  이전 보류를 켜야 합니다. 보류를 설정하려면 해당 보류를 선택해 플라이아웃 페이지를 표시한 다음 **상태** 토글을 **켜기** 로 설정합니다.

닫힌 사례를 다시 열기 위해

1. **Advanced eDiscovery** 페이지에서 다시 열 케이스를 선택합니다.

2. **설정** 탭의 **케이스 정보** 에서 **선택** 을 클릭합니다.

3. 사례 정보 플라이아웃 페이지의 아래쪽에서 작업 을 **클릭한** 다음 사례 다시 **열기 를 클릭합니다.** 

   다시 열기 프로세스를 완료하는 데 최대 60분이 걸릴 수 있습니다.

## <a name="delete-a-case"></a>케이스 삭제

활성 및 닫힌 사례를 모두 삭제할 Advanced eDiscovery 있습니다. 케이스를 삭제하면 보유자, 통신, 검색, 검토 집합 및 내보내기 작업의 목록과 같은 케이스와 연결된 모든 구성 요소가 삭제됩니다. 사례는 목록의 Advanced eDiscovery **목록에서** Microsoft 365 규정 준수 센터. 삭제된 사례는 복구하거나 다시 열 수 없습니다.

> [!NOTE]
> 데이터 유출 시나리오에서 검토 집합의 항목을 제거하는 유일한 방법은 사례를 삭제하는 Advanced eDiscovery 것입니다. 다른 "검색 및 삭제" 메서드는 검토 집합에서 항목을 제거하지 않습니다.

사례를 삭제하려면 먼저 사례와 연결된 모든 보류를  삭제해야 합니다. 여기에는 끄기 상태의 보류 삭제가 **포함됩니다.**

사례와 연결된 보류를 삭제하려면

1. 삭제할 **Advanced eDiscovery** 보류 탭으로 이동하십시오.

2. 삭제할 보류를 클릭합니다.

3. 플라이아웃 페이지에서 보류 **삭제를 클릭합니다.**

케이스를 삭제하려면

1. **Advanced eDiscovery** 페이지에서 삭제할 케이스를 선택합니다.

2. **설정** 탭의 **케이스 정보** 에서 **선택** 을 클릭합니다.

3. 사례 정보 플라이아웃 페이지의 아래쪽에서 작업 을 **클릭한** 다음 사례 삭제 **를 클릭합니다.** 

