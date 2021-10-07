---
title: Capacity planning and load testing SharePoint Online(용량 계획과 부하 테스트가 가능한 SharePoint Online)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: 이 문서에서는 허용되지 않는 기존 부하 테스트를 수행하지 않고 SharePoint Online에 배포하는 방법을 설명합니다.
ms.openlocfilehash: f9bf4c508e862d9d99bac2935cfea32878a93762
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172026"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Capacity planning and load testing SharePoint Online(용량 계획과 부하 테스트가 가능한 SharePoint Online)
이 문서에서는 기존 부하 테스트 없이 SharePoint Online에 배포할 수 있는 방법에 대해 설명합니다. 이는 SharePoint Online에서 부하 테스트가 허용되지 않습니다. SharePoint 온라인은 클라우드 서비스로, 서비스의 부하 기능, 상태 및 전반적인 부하 잔액은 Microsoft에서 관리합니다.
  
사이트 시작의 성공을 보장하는 가장 좋은 방법은 포털 시작 롤아웃 계획에서 강조 표시된 기본 원칙, 사례 및 권장 사항을 [따르는 것입니다.](planportallaunchroll-out.md)

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>SharePoint Online에서 용량 계획을 수행하는 방법 개요 
SharePoint Online의 주요 이점 중 하나는 클라우드의 탄력성과 분산된 지역의 사용자를 위한 최적화입니다. 대규모 환경은 매일 수백만 사용자에 대한 서비스로 설정되어 있으므로 팜을 균형 조정하고 확장하여 용량을 효과적으로 처리하는 것이 중요합니다.
  
한 팜의 한 테넌트에서 증가를 예측할 수 없는 경우가 종종 있는 반면, 요청의 집계 합은 시간이 지날 때 예측할 수 있습니다. SharePoint Online의 증가 추세를 파악하여 향후 확장을 계획할 수 있습니다.
  
용량을 효율적으로 사용하며 예기치 않은 증가를 처리하기 위해 모든 팜에서 서비스의 다양한 요소를 추적하고 모니터링하는 자동화가 있습니다. 여러 메트릭이 사용되고, 주요 메트릭 중 하나는 CPU 부하로, 프런트 엔드 서버를 확장하기 위해 신호로 사용됩니다. 또한 [단계적/웨이브](planportallaunchroll-out.md)방식도 권장됩니다. SQL 환경은 시간의 따라 부하 및 증가에 따라 확장될 것이고, 단계 및 파도를 따라 해당 부하와 성장을 올바르게 분산할 수 있습니다. 

용량은 지속적으로 하드웨어를 더 추가하는 것 이상으로, 유효한 부하 요청을 처리하도록 해당 용량을 관리 및 제어하는 데도 관련이 있습니다. 고객이 최상의 환경을 경험할 수 있도록 권장 지침을 따르는 것이 좋습니다. 또한 서비스에서 "부적당" 동작을 허용하지 않도록 하는 데 필요한 조절 패턴과 컨트롤이 있습니다. 모든 "나쁜" 동작이 의도적인 것은 아니며 해당 동작의 영향을 제한해야 합니다. 스로틀 및 이를 방지하는 방법에 대한 자세한 내용은 스로틀되지 않도록 하는 방법 문서를 [검토하세요.](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Online에서 테스트 테스트를 로드할 SharePoint 이유
사내 환경에서는 부하 테스트가 확장 가정의 유효성을 검사하고 궁극적으로 팜의 중단점을 찾는 데 사용됩니다. 로드를 채도로 채우는 것입니다. 

온라인 SharePoint 배율이 비교적 유동적이기 때문에 특정추학에 따라 부하를 조정, 제한 및 제어하기 때문에 다르게 작업을 해야 합니다. 이러한 대규모 다중 테넌트 환경인 경우 동일한 팜의 모든 테넌트를 보호해야 하여 부하 테스트를 자동으로 조정합니다. 그러나 테스트를 로드하려고 하면 스로틀링되는 것 외에 배율 및 팜 균형 조정 작업이 계속 수행될 때 현재 테스트한 팜이 테스트 기간 동안 또는 테스트 후 시간 내에 배율이 변경될 수 있기 때문에 잘못된 결과를 얻게 됩니다.

테스트 SharePoint 서비스로 로드하는 대신 권장 사례를 따르고, 정상 포털 [만들기,](/sharepoint/portal-health) 시작 및 유지 관리 지침을 따르는 것이 좋습니다.