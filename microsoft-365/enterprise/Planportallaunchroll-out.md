---
title: SharePoint Online에서 포털 시작 롤아웃 계획
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: 이 문서에서는 SharePoint Online에서 포털 시작을 계획하는 방법과 성공적인 실행을 위해 취할 단계에 대해 설명
ms.openlocfilehash: d77baac6209a4002bb1c27513d5ccfdf5c4ac28a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905695"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>SharePoint Online에서 포털 시작 롤아웃 계획

포털은 사이트에서 콘텐츠를 사용하는 다수의 사이트 방문자를 보유하는 인트라넷 상의 SharePoint 사이트입니다. 대규모 조직에서는 이들을 다수 보유할 수도 있습니다. 예를 들어 회사 포털과 HR 포털이 있습니다. 일반적으로 포털에서는 사이트와 해당 콘텐츠를 만들고 저술하는 사용자가 비교적 적습니다. 포털을 사용하는 대부분의 방문자는 콘텐츠를 읽고 사용하기만 합니다.

이 문서에서는 SharePoint Online에 대한 배포 및 롤아웃 계획을 계획하는 방법을 설명합니다. 또한 기존 부하 테스트가 SharePoint Online에서 허용되지 않는 방식도 제공합니다. SharePoint Online은 클라우드 서비스로, 서비스의 부하 기능, 상태 및 전체 부하 잔액은 Microsoft에서 관리합니다.

성공적인 포털 만들기를 지원하기 위해 정상 포털 만들기, 시작 및 유지 관리에 자세히 설명된 기본 원칙, 사례 및 권장 사항을 [따르하세요.](/sharepoint/portal-health) 

배포 방법은 아래에서 강조 표시됩니다.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>SharePoint Online의 용량 계획 개요
모든 팜에서 용량을 효율적으로 활용하고 예기치 않은 증가를 처리하기 위해 특정 사용 시나리오를 추적하는 자동화 기능을 제공합니다. 한 팜에 있는 테넌트 하나에 대해 정확한 증가를 예측할 수 없는 반면, 집계된 요청 합계는 시간이 경과하면서 예측할 수 있습니다. SharePoint Online의 증가 추세를 파악하여 향후 확장을 계획할 수 있습니다. 용량 계획 및 부하 테스트 [SharePoint Online에 대한 자세한 내용은 을 참조하십시오.](capacity-planning-and-load-testing-sharepoint-online.md)

성공적인 실행의 핵심 부분은 아래에 자세히 설명된 "웨이브" 또는 "단계적 롤아웃" 접근 방식입니다. 

## <a name="can-i-load-test-sharepoint-online"></a>테스트 SharePoint Online을 로드할 수 있나요?
SharePoint Online은 팜 전체에서 균형이 조정되는 공유 다중 테넌트 환경으로, 계속 조정됩니다. SharePoint Online과 같은 환경을 부하 테스트합니다. 이러한 확장이 지속적으로 변경되어 예기치 않은 결과가 발생할 뿐 아니라 허용되지도 않습니다. 

자세한 내용은  [다음을 수행하세요. 용량 계획 및 부하 테스트 SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>권장 지침에 따라 페이지 최적화
SharePoint Online에 대한 권장 지침에 대해 검토하지 않고는 단순히 SharePoint Online으로 페이지를 이동하면 안 됩니다. 가장 좋은 방법은 조직의 대부분의 사용자가 사이트의 시작점으로 액세스할 수 있는 위치인 SharePoint의 모든 사이트 또는 포털에 대해 항상 모든 홈 페이지를 최적화하는 것입니다.

몇 가지 기본 요인을 고려해야 합니다.
- 사내 배포는 개체 캐시, 출력 캐시 및 Blob 캐시와 같은 기존 서버 쪽 캐시를 활용할 수 있습니다. 클라우드의 토폴로지 차이로 희미한 배율 차이로 접근 방식이 줄어들기 때문에 이러한 옵션을 반드시 사용할 수 있는 것은 아니어도 됩니다.
- 클라우드 사용에 사용되는 모든 페이지/기능/사용자 지정은 다른 영역 또는 지역의 사용자가 보다 일관된 환경을 제공하도록 사용자의 분산된 위치뿐만 아니라 더 높은 대기 시간으로 최적화해야 합니다. 클라우드는 최신 SharePoint뿐만 아니라 분산된 사용자 기반에 최적화하기 위해 CDN(콘텐츠 배달 네트워크)과 같은 최적화를 제공합니다. 마지막으로 알려진 LKG(Good)는 OOTB(기본 제공) 웹 파트에서 활용됩니다.

### <a name="what-to-do"></a>할 일:
 - SharePoint Online의 모든 사이트 [](./page-diagnostics-for-spo.md)페이지에 대해 분석 및 지침을 제공하는 Chromium 확장인 페이지 진단 도구를 사용합니다. 사이트 소유자, 편집자, 관리자 및 개발자가 분석 및 최적화의 시작점으로 사용할 수 있습니다.
 - 개발자는 최신 페이지의 브라우저에서 Ctrl-F12뿐만 아니라 F12 브라우저 개발자 도구와 같은 개발 도구도 사용해야 합니다. [Fiddler를](https://www.telerik.com/download/fiddler) 사용하여 페이지의 크기 가중치(페이지 크기가 메가바이트)와 전체 페이지 로드에 영향을 미치는 호출 및 요소 수를 검토할 수도 있습니다. 

이 섹션에서는 페이지를 최적화하기 위한 간략한 요약을 제공합니다.  자세한 내용은 다음을 참조하고, 정상 포털을 [만들고, 시작하고, 유지 관리합니다.](/sharepoint/portal-health)

## <a name="follow-a-wave--phased-roll-out-approach"></a>웨이브/단계적 롤아웃 방식 따르기
사이트 실행을 위한 기존의 Big bang 접근 방식에서는 사용자 지정, 외부 원본, 서비스 또는 프로세스가 올바른 규모로 테스트된 것이 확인되지 않습니다. 이는 시작되는 데 몇 개월이 걸릴 수 있는 것은 아니며 조직 규모에 따라 적어도 며칠 동안 권장됩니다. 따라서 웨이브 롤아웃 계획에 따라 다음 단계를 진행하기 전에 문제를 일시 중지하고 해결할 수 있는 옵션을 제공하므로 문제가 발생할 수 있는 사용자 수가 줄어든다. SharePoint as a Service는 사용 현황 및 예측된 사용 현황을 기반으로 용량을 확장하며, 시작 사실을 알려드릴 필요가 없는 경우에는 지침에 따라 성공을 보장해야 합니다.
  
다음 이미지와 같이 초대된 사용자 수가 실제로 사이트를 사용하는 사용자보다 훨씬 많은 경우가 종종 있습니다. 이 이미지는 릴리스를 롤아웃하는 방법에 대한 전략을 보여줍니다. 이 방법은 대부분의 사용자에게 SharePoint 사이트를 표시하기 전에 SharePoint 사이트를 개선하는 방법을 식별하는 데 도움이 됩니다.
  
![초대받은 사용자 및 활성 사용자를 보여 주는 그래프](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
파일럿 단계에서는 조직이 신뢰하고 참여할 것으로 알고 있는 사용자로부터 피드백을 받을 수 있습니다. 이렇게 하면 시스템 사용 방법과 시스템 수행 방법을 측정할 수 있습니다.
  
각 단계 동안 배포의 각 단계 동안 성능뿐만 아니라 기능에 대한 사용자 피드백을 수집합니다. 이는 시스템이 느리게 도입되고 시스템이 더 많이 사용될 때 개선할 수 있는 이점이 있습니다. 또한 사이트가 더 많은 사용자에게 롤아웃될 때 증가하는 부하에 대응하고 페이지 최적화 지침에 따라 사용자에 대한 긍정적인 환경을 보장할 수 있습니다.

### <a name="what-to-do"></a>할 일:
- 각 단계의 타이밍을 결정하고, 계속하기 전에 조정해야 하는 경우 대치/일시 중지 기회가 있는지 확인
- 사용하도록 설정할 첫 번째 사용자 그룹을 계획하여 앞으로 이동해야 하는 피드백을 받을 수 있도록 합니다. 즉, 가능한 경우 적시에 피드백을 제공할 활성 사용자 그룹을 선택합니다.
- 각 웨이브를 계획할 때 작은 사용자 기반(5,000명 미만)으로 시작한 다음 각 웨이브를 진행할 때 그룹 크기를 늘려야 합니다. 이렇게 하면 시차가 있는 접근 방식을 만들 수 있으며 필요한 일시 중지 기회를 쉽게 일시 중지할 수 있습니다.