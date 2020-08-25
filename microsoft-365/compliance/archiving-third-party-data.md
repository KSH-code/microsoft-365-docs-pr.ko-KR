---
title: 타사 데이터 보관
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 Microsoft 365 사서함으로 타사 데이터를 가져오는 방법을 알아봅니다.
ms.openlocfilehash: 6b75d2857fd95d24a90f9245cb299b7558aa3cec
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860713"
---
# <a name="archive-third-party-data"></a>타사 데이터 보관

Microsoft 365를 사용하면 관리자가 데이터 커넥터를 사용하여 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 Microsoft 365 조직의 사서함으로 타사 데이터를 가져와 보관할 수 있습니다. Microsoft 365에서 데이터 커넥터를 사용하여 타사 데이터를 가져와 보관할 경우의 주요 이점은 데이터가 가져온 후에 다양한 Microsoft 365 규정 준수 솔루션을 적용할 수 있다는 점입니다. 이를 통해 조직의 비 Microsoft 데이터가 조직에 영향을 주는 규정 및 표준을 준수하도록 할 수 있습니다.

## <a name="third-party-data-connectors"></a>타사 데이터 커넥터

다음 표에서는 Microsoft 365 준수 센터에서 사용할 수 있는 타사 데이터 커넥터를 열 수 있습니다. 또한 Microsoft 365에서 가져온 후 타사 데이터에 적용할 수 있는 규정 준수 솔루션이 요약되어 있습니다. 각 규정 [준수 솔루션과](#overview-of-compliance-solutions-that-support-third-party-data) 이 솔루션이 제3자 데이터를 이용하는 방법에 대한 자세한 내용은 다음 섹션을 참조하세요.

> [!TIP]
> 타사 데이터 **열의 링크를** 클릭하여 해당 데이터 형식에 대한 커넥터를 만드는 단계별 지침을 참조합니다.

|타사 데이터  |소송 보존|eDiscovery  |보존 정책  |레코드 관리  |커뮤니케이션 규정 준수  |내부자 위험 관리  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[블룸버그 메시지](archive-bloomberg-message-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[HR 데이터](import-hr-data.md) ||||||![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[ICE 채팅](archive-icechat-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[LinkedIn](archive-linkedin-data.md)   |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
||||||||

이전 테이블에 나열된 타사 데이터(HR 데이터 제외)는 사용자 사서함으로 가져옵니다. 타사 데이터를 지원하는 해당하는 준수 솔루션이 데이터가 저장된 사용자 사서함에 적용됩니다.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>타사 데이터를 지원하는 규정 준수 솔루션 개요

다음 섹션에서는 Microsoft 365 규정 준수 솔루션이 이전 표에 나열된 타사 데이터를 관리하는 데 도움이 되는 몇 가지 사항을 설명합니다.

### <a name="litigation-hold"></a>소송 보존

타사 [데이터를 보존하려면 사용자](create-a-litigation-hold.md) 사서함에 소송 보존을 적용합니다. 보류를 만들 때는 보존 기간(시간 기반 *보존이라고도*함)을 지정하여 삭제 및 수정한 타사 데이터가 지정된 기간 동안 보존되다가 사서함에서 영구적으로 삭제되도록 할 수 있습니다. 또는 콘텐츠를 무한기간 보존(무한 *보존이라고*하는)하거나 소송 보존이 제거될 때까지 보존할 수 있습니다.

### <a name="ediscovery"></a>eDiscovery

Microsoft 365의 세 가지 기본 eDiscovery 도구는 콘텐츠 검색, Core eDiscovery 및 Advanced eDiscovery입니다.

- **[콘텐츠 검색](content-search.md).** 콘텐츠 검색 도구를 사용하여 사서함에서 가져온 타사 데이터를 검색할 수 있습니다. 검색 쿼리 및 조건을 사용하여 검색 결과 범위를 좁히고 검색 결과를 내보낼 수 있습니다.

- **[핵심 eDiscovery](get-started-core-ediscovery.md).** 이 도구는 기본 검색 및 내보내기 기능을 구현하므로 사례 데이터에 액세스할 수 있는 사람을 제어하고 검색 조건과 일치하는 사용자 사서함 또는 사서함 콘텐츠를 보류 상태로 할 수 있는 사례를 만들 수 있습니다. 즉, 사용자 사서함으로 가져온 타사 데이터에 eDiscovery 보류를 배치할 수 있습니다.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** 이 강력한 도구는 사례에 보유자를 추가하고, 보류자의 데이터를 대기시키고, 보유자의 타사 데이터를 검토하여 테마 및 중복 검색 같은 향후 분석을 위해 핵심 eDiscovery의 사례 기능을 확장합니다. 타사 데이터를 검토 집합에 로드한 후 쿼리를 실행하고 좁은 결과 집합으로 필터링할 수 있습니다.

   핵심 eDiscovery와 고급 eDiscovery를 통해 조직의 법적 또는 내부 조사와 관련이 있을 수 있는 타사 데이터를 관리할 수 있습니다.

### <a name="retention-policies"></a>보존 정책

보존 기간이 [만료되면 보존할](retention.md) 보존 정책을 적용한 다음 타사 데이터(및 기타 사서함 콘텐츠)를 삭제할 수 있습니다. 특정 보존 기간의 타사 데이터를 삭제하거나 보존 기간이 만료되면 게시 검토를 트리거하는 보존 정책을 사용할 수도 있습니다.

### <a name="records-management"></a>레코드 관리

Microsoft [records management](records-management.md) 365의 레코드 관리 기능을 사용하여 타사 데이터를 레코드로 선언할 수 있습니다. 사서함의 타사 데이터를 기록으로 표시하는 보존 레이블을 적용하는 사용자가 수동으로 이 작업을 할 수 있습니다. 타사 데이터에서 중요한 정보, 키워드 또는 콘텐츠 유형을 식별하여 보존 레이블을 자동 적용할 수도 있습니다.

### <a name="communication-compliance"></a>커뮤니케이션 규정 준수

[커뮤니케이션](communication-compliance.md) 규정 준수를 통해 제3자 데이터를 검사하여 조직의 데이터 표준을 준수하는지도 확인합니다. 이렇게 하려면 조직에서 적절하지 않은 메시지에 대한 수정 작업을 검색하고 캡처하고 수행합니다. 예를 들어 가져온 타사 데이터가 중요하지 않은 언어, 중요 정보 및 규정 준수를 모니터링할 수 있습니다.

### <a name="insider-risk-management"></a>내부자 위험 관리

참가자 위험 관리 솔루션에서는 선택적인 HR 데이터 [Insider risk management](insider-risk-management.md) 같은 타사 데이터의 신호를 사용하여 조직의 위험 활동을 감지 및 조사하고 이에 대한 작업을 수행하도록 함으로서 내부 위험을 최소화할 수 있습니다. 예를 들어 HR 데이터 커넥터에서 가져온 데이터는 위험 지표로 직원 데이터 도용을 감지하는 데 도움이 됩니다.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Microsoft 파트너와 함께 타사 데이터 보관

조직에서 Microsoft 파트너와 함께 사용할 수 있는 타사 데이터 가져오고 보관하는 또 다른 옵션이 있습니다. Microsoft 준수 센터에서 사용할 수 있는 데이터 커넥터가 타사 데이터 형식을 지원하지 않는 경우 타사 데이터 원본에서 정기적으로 항목을 추출하도록 구성할 사용자 지정 커넥터를 제공한 다음 타사 API를 통해 Microsoft 클라우드에 연결하여 해당 항목을 Microsoft 365로 가져올 수 있는 파트너와 작업할 수 있습니다. 파트너 커넥터는 타사 데이터 원본의 항목 콘텐츠를 전자 메일 메시지로 변환한 다음 Microsoft 365의 사서함으로 가져올 수도 있습니다.

함께 작업할 수 있는 파트너 목록과 이 방법의 단계별 프로세스는 파트너와 함께 Microsoft 365에 타사 데이터를 [보관하는 방법을 참조하세요.](work-with-partner-to-archive-third-party-data.md)
