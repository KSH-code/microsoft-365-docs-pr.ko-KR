---
title: 2013에서 이전 버전 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 이전 버전은 Advanced eDiscovery 및 문서에 저장된 모든 문서 버전에서 콘텐츠를 SharePoint OneDrive.
ms.openlocfilehash: 8da7b390a982b9be0a4752e167399ad633377854
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60779135"
---
# <a name="set-up-historical-versions-in-advanced-ediscovery-preview"></a>이전 버전 설정(Advanced eDiscovery)(미리 보기)

조직의 eDiscovery 관리자는 Advanced eDiscovery 버전 기능을 사용하여 SharePoint Online 및 비즈니스용 OneDrive. 그런 다음 분석 및 검토를 위해 해당 콘텐츠를 검토 집합에 추가할 수 있습니다. 이렇게 하면 동일한 문서의 최신 버전에 관련 정보가 포함되어 있지 않은 경우에도 사례 또는 조사와 관련이 있을 수 있는 특정 버전의 문서를 찾아서 검토할 수 있습니다.

조직의 이전 버전 기능을 Advanced eDiscovery SharePoint 조직의 사이트에 대해 버전 관리 기능을 사용하도록 설정해야 합니다. 그런 다음 사용자가 SharePoint 또는 OneDrive 문서를 수정하면 문서를 저장(또는 자동 저장)할 때 암시적 일반 버전이 만들어집니다. SharePoint 버전 관리는 문서, 이벤트 및 작업을 포함하여 SharePoint 수행되는 활동을 추적할 수 있습니다. 이 버전 관리 기능은 법적 조사에 증거를 제공할 수 있는 감사 내선으로 남습니다. 이러한 이전 버전의 문서를 조직에서 사용할 수 있습니다. 조직에서는 법률 문제에서 법정 검색 중에 중요한 내용이나 관련 콘텐츠가 있는 해당 버전을 공유해야 할 수 있습니다.

eDiscovery 관리자가 조직의 이전 버전을 설정한 다음 특정 SharePoint 사이트에 대해 해당 버전을 활성화하면 SharePoint 콘텐츠 푸시 서비스는 활성화된 사이트에서 문서의 모든 주 버전 및 부 버전을 크롤링한 다음 인덱싱을 위해 해당 버전을 전송합니다. 크롤링 및 인덱싱 프로세스가 완료되면 문서 및 해당 버전을 eDiscovery 검색에 사용할 수 있습니다. 버전 기록을 통해 특정 버전에 액세스할 수 있는 한 해당 버전은 Advanced eDiscovery 검색할 수 있습니다.

## <a name="set-up-historical-versions"></a>이전 버전 설정

조직에서 이전 Advanced eDiscovery 사용하도록 설정하려면 조직에서 해당 버전을 설정한 다음 특정 사이트를 활성화해야 해당 사이트에 저장된 모든 문서 버전이 검색할 수 있도록 인덱싱됩니다. 이전 버전에 Advanced eDiscovery 버전을 설정하기 전에 이전 버전에서 버전 SharePoint.

### <a name="step-1-turn-on-versioning-in-sharepoint"></a>1단계: 2단계에서 버전 SharePoint

첫 번째 단계는 모든 버전의 문서가 SharePoint 온라인에서 버전이 유지될 수 있도록 설정하는 것입니다. 자세한 내용은 에서 [버전 SharePoint.](/microsoft-365/community/versioning-basics-best-practices)

### <a name="step-2-turn-on-historical-versions"></a>2단계: 이전 버전 켜기

다음 단계는 이전 버전에서 이전 버전을 설정하는 Advanced eDiscovery. 조직의 이전 버전을 설정하려면 전역 관리자 또는 eDiscovery 관리자(eDiscovery 관리자 역할 그룹의 eDiscovery 관리자 하위 그룹 구성원)되어야 합니다. 이전 버전이 켜진 후 전체 조직에 적용됩니다.

> [!IMPORTANT]
> 이전 버전을 켜면 공개 미리 보기 중에 해제할 수 없습니다. 일반 공급을 위해 이전 버전이 릴리스된 후 해제할 수 있습니다.

1. 에서 Microsoft 365 규정 준수 센터 로 이동하여 [Advanced eDiscovery](https://go.microsoft.com/fwlink/p/?linkid=2173764)로 이동한 Advanced eDiscovery **클릭합니다.**

   ![설정 Advanced eDiscovery 선택](..\media\HistoricalVersions1.png)

2. 설정 **페이지에서** 이전 버전(미리 **보기)** 탭을 선택한 다음  이전 버전 테넌트 컨트롤을 켜기 모드로 전환합니다.

   ![토글을 켜서 이전 버전을 사용하도록 설정](..\media\HistoricalVersions2.png)

   이전 버전을 해제할 수 없다고 경고가 표시됩니다. 앞서 설명한 것 처럼 기능이 일반 공급을 위해 릴리스될 때까지 이전 버전을 해제할 수 없습니다.

3. 예를 **클릭하여** 이전 버전을 켜려면 예를 클릭합니다.

### <a name="step-3-activate-sharepoint-sites"></a>3단계: 사이트 SharePoint 활성화

조직의 이전 버전을 설정한 후 마지막 단계는 이전 버전을 지원하기 위해 SharePoint 사이트를 활성화하는 것입니다. 사이트를 활성화하면(이전 버전 탭의 사이트 목록에  사이트를 추가하여) 사이트가 다시 생성되고 해당 사이트에 저장된 모든 문서 버전이 검색을 위해 인덱싱됩니다.

> [!NOTE]
> 이전 버전의 공개 미리 보기에서는 조직당 사이트 활성화가 100개로 제한됩니다. 이전 버전에 대해 사이트를 활성화하거나 사용하지 않도록 설정할 때마다 이 제한에 대해 정품 인증이 계산됩니다. 여러 사이트를 사용하도록 설정하면 각 사이트가 단일 활성화로 계산됩니다. 총 활성화 수는 이전 버전 **탭에** 표시됩니다.

1. 이전 버전 **페이지의** Advanced eDiscovery 설정 **탭에서** 사용 을  클릭하여 이전 버전에 대한 사이트를 활성화합니다.

   ![사용 을 클릭하여 이전 버전에 대한 사이트 활성화](..\media\HistoricalVersions3.png)  

   플라이아웃 아웃 페이지는 조직의 모든 SharePoint 목록이 포함된 페이지가 표시됩니다.

2. 활성화할 사이트를 선택한 다음  사용 을 클릭하여 이전 버전에 대해 활성화합니다. 검색 상자를 사용하여 특정 사이트를 검색할 수 있습니다.

   사이트의 문서 버전이 인덱싱되고 이 인덱싱 프로세스에서 버전을 검색할 준비가 되기까지 시간이 다소 걸릴 것 같다는 경고가 표시됩니다. 또한 이 경고에는 선택한 사이트의 이전 버전을 30일 동안 사용하지 않도록 설정할 수 없습니다.

3. 예를 **클릭하여** 이전 버전에 대해 사이트를 활성화합니다.

   ![활성화된 사이트 및 사이트 활성화 수가 표시됩니다.](..\media\HistoricalVersions4.png)  

   사이트가 활성화된 사이트 목록에 추가됩니다. 사이트 활성화 수를 보여 주며 카운터도 업데이트됩니다.

4. 이전 버전에 대해 활성화하려는 각 사이트에 대해 이전 단계를 반복합니다.

## <a name="frequently-asked-questions"></a>질문과 대답

**초안 컬렉션을 검토 집합에 커밋할 때 "모든 버전 수집" 옵션과 이전 버전은 어떻게 다를 수 있나요?**

현재 최신 버전의 문서만 검색을 위해 인덱싱됩니다. 즉, 초안 컬렉션을 실행하면 최신 버전의 문서만 검색됩니다. 문서가 컬렉션의 키워드 쿼리와 일치하면 컬렉션 결과에 반환됩니다. 그러나 문서의 최신 버전이 검색 쿼리와 일치하지 않는 경우 이전 버전의 문서에 키워드가 포함된 경우 문서가 반환되지 않습니다. 이러한 상황을 완화하기 위해 Advanced eDiscovery 컬렉션을 검토 집합으로 커밋할 때 문서의 모든 버전을 수집할 [수 있습니다.](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set) 즉, 키워드를 포함할 수 있는 모든 이전 버전이 검토 집합에 추가됩니다.

이전 버전은 사이트를 활성화할 때 마지막 버전이 아닌 문서의 모든 버전이 검색을 위해 인덱싱되어 있기 때문에 "모든 버전 수집"보다 효율적입니다. 결과적으로 이전 버전의 문서에 검색 쿼리와 일치하는 키워드가 포함된 경우 컬렉션에서 해당 키워드가 반환됩니다.

**사이트에 대해 이전 버전을 사용할 수 있는 경우 사이트의 성능에 영향을 미치나요?**

아니요. 사이트에 대해 이전 버전을 사용하도록 설정하면 사이트의 성능은 사이트를 사용하도록 설정하기 전과 동일합니다. 사이트가 활성화된 후 사이트에서 수행되는 크롤링 및 인덱싱 프로세스는 속도가 느려지며 사용률이 높은 시간 동안 수행됩니다. 사이트에 대해 이전 버전을 사용하도록 설정하면 백필 프로세스가 시작되어 사이트에서 문서의 모든 버전을 찾은 다음 해당 버전을 인덱스로 전송합니다. 사이트의 문서 버전 수에 따라 이 백필 프로세스가 서비스 상태 영향을 줄 수 있습니다. 다음과 같은 방법으로 이러한 잠재적인 영향을 완화하고 있습니다.

- 이러한 버전은 사용이 많은 시간에 처리하기 위해 최선을 다하고 있습니다.

- 우선 순위가 가장 낮은 큐에서 문서 버전을 처리하여 대부분의 서비스 리소스를 사용자 변경에 위임할 수 있습니다.

**사이트의 모든 이전 버전의 문서가 모두 인덱싱되고 eDiscovery 검색에 사용할 수 있도록 사이트가 활성화될 때까지 얼마나 기다려야 하나요?**

사이트의 문서 수와 문서당 평균 버전 수에 따라 사이트당 총 파일 수를 예측합니다. 이를 기준으로 인덱싱하는 데 걸릴 수 있는 예상 기간은 다음과 같습니다.

`Number of versions / (Processing rate of 100,000 files per day ) + .5 days = Total number of days to process a site`

사이트의 버전 인덱싱은 사용률이 낮을 때 실행하도록 최적화되어 1일이 버퍼로 추가됩니다.

예를 들어 사이트의 전체 문서 수와 모든 버전이 150,000개이면 사이트를 이전 버전으로 처리하는 데 최소 2일이 걸릴 수 있습니다.

`150,000 files/100,000 files per day + .5 days = 2 days`

**이전 버전의 사이트를 자주 활성화하거나 비활성화하지 않는 이유는 무엇입니까?**

이전에 활성화된 사이트를 비활성화하면 정리 프로세스가 트리거됩니다. 이 프로세스를 완료하는 데 시간이 걸립니다. 동일한 사이트가 다시 활성화되면 사이트를 다시 인덱스하는 백필 프로세스를 다시 시작해야 합니다. 정리 프로세스와 백필 프로세스 모두 시간이 많이 들이고 리소스를 많이 사용합니다. 따라서 사이트의 이전 버전을 반복적으로 활성화 및 비활성화하지 않도록 이전 버전에 대해 정품 인증할 사이트를 신중하게 고려하고 계획하는 것이 좋습니다.
