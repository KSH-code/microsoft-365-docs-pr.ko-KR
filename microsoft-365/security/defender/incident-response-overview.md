---
title: 조사 및 응답 Microsoft 365 Defender
description: 인시던트 조사 및 대응 기능을 Microsoft 365 Defender.
keywords: 인시던트, 경고, 조사, 분석, 대응, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365, 인시던트 대응, 사이버 공격
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: abd075ae76eefc4a86d3e99471f092b3f4f03b34
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724821"
---
# <a name="investigate-and-respond-with-microsoft-365-defender"></a>조사 및 응답 Microsoft 365 Defender

다음은 작업의 기본 조사 및 응답 Microsoft 365 Defender.

- [인시던트에 대응](#incident-response)
- [자동 수정 작업 검토 및 승인](#automated-investigation-and-remediation)
- [데이터에서 알려진 위협 검색](#proactive-search-for-threats-with-advanced-hunting)
- [최신 사이버 공격 이해](#get-ahead-of-emerging-threats-with-threat-analytics)
- [도움말 보기](#collaborate-with-microsoft-experts)

## <a name="incident-response"></a>사고 대응

Microsoft 365 및 앱은 의심스러우거나 악의적인 이벤트나 활동을 감지할 때 경고를 생성합니다. 개별 경고는 완료되거나 지속적인 공격에 대한 중요한 단서를 제공합니다. 그러나 공격은 일반적으로 장치, 사용자 및 사서함과 같은 다양한 유형의 엔터티에 대해 다양한 기술을 사용합니다. 그 결과 테넌트의 여러 엔터티에 대한 여러 경고가 생성됩니다. 개별 경고를 함께 하여 공격에 대한 통찰력을 확보하는 것은 까다롭고 시간이 많이 소요될 수 Microsoft 365 Defender 경고 및 관련 정보를 인시던트에 자동으로 집계합니다.

지속적인 기준에 따라 인시던트 큐에서 분석 및 해결을 위해 우선순위가 가장 높은 인시던트를 식별하고 대응을 준비합니다. 이러한 조치는 다음으로 구성됩니다.

- [인시던트](incident-queue.md) 큐 필터링 및 정렬을 통해 우선 순위가 가장 높은 인시던트 결정
- [직위를](manage-incidents.md) 수정하고, 분석가에게 할당하고, 태그와 설명을 추가하여 인시던트 관리

각 인시던트에 대해 인시던트 대응 워크플로를 사용하여 인시던트 및 해당 경고 및 데이터를 분석하여 공격을 포함하고 위협을 제거하고 공격으로부터 복구하고 이를 학습합니다. 자세한 [내용은 다음](incidents-overview.md#example-incident-response-workflow-for-microsoft-365-defender) Microsoft 365 Defender.

## <a name="automated-investigation-and-remediation"></a>자동화된 조사 및 수정

조직에서 Microsoft 365 Defender 경우 악의적 또는 의심스러운 활동이나 아티팩트가 감지될 때마다 보안 운영 팀이 Microsoft 365 Defender 포털 내에서 경고를 수신합니다. 제공될 수 있는 위협의 끝 없는 흐름을 통해 보안 팀은 종종 대량의 경고를 해결해야 하는 과제에 직면합니다. 다행히 Microsoft 365 Defender 팀이 위협을 보다 효율적으로 해결할 수 있도록 도와주는 자동화된 조사 및 대응(AIR) 기능이 포함되어 있습니다.

자동화된 조사가 완료되면 관련된 인시던트에 대한 모든 증거에 대한 판결에 도달합니다. 판정에 따라 수정 작업이 식별됩니다. 경우에 따라 수정 작업이 자동으로 수행됩니다. 다른 경우에는 재구성 작업이 관리 센터를 통해 승인을 Microsoft 365 Defender 있습니다. 

자세한 [내용은 2013의](m365d-autoir.md) 자동화된 조사 Microsoft 365 Defender 응답을 참조하세요.

## <a name="proactive-search-for-threats-with-advanced-hunting"></a>고급 헌팅을 사용하여 위협에 대한 사전 검색

공격이 발생할 때 대응하기에 충분하지 않습니다. 랜섬웨어와 같은 확장된 다단계 공격의 경우 진행 중 공격의 증거를 사전적으로 검색하고 작업이 완료되기 전에 이를 중지해야 합니다.

고급 헌팅은 최대 30일의 원시 데이터를 탐색할 수 있는 Microsoft 365 Defender 기반의 쿼리 기반 위협 헌팅 도구입니다. 네트워크의 이벤트를 사전에 검사하여 위협 지표와 엔터티를 찾을 수 있습니다. 이러한 유연한 데이터 Microsoft 365 Defender 통해 알려진 위협과 잠재적 위협 모두에 대해 제약 없는 헌팅을 할 수 있습니다.

동일한 위협 헌팅 쿼리를 사용하여 사용자 지정 검색 규칙을 만들 수 있습니다. 이러한 규칙은 자동으로 실행되어 의심되는 위반 활동, 잘못 구성된 컴퓨터 및 기타 결과를 확인하고 이에 대응합니다.

자세한 [내용은](advanced-hunting-overview.md) 헌팅에서 고급 헌팅을 Microsoft 365 Defender 사전 헌팅을 참조하세요.

## <a name="get-ahead-of-emerging-threats-with-threat-analytics"></a>위협 분석을 사용하여 새로운 위협 요소 미리 활용

위협 분석은 새로운 위협에 직면하는 동안 Microsoft 365 Defender 팀이 최대한 효율적으로 사용할 수 있도록 설계된 보안 기능의 위협 인텔리전스 기능입니다. 여기에는 다음에 대한 자세한 분석 및 정보가 포함됩니다.

- 활성 위협 요소 및 캠페인
- 인기 있는 새로운 공격 기술
- 중요한 취약성
- 일반적인 공격 표면
- 널리 사용되는 맬웨어

위협 분석에는 식별된 각 위협에 대한 Microsoft 365 테넌트 내의 관련 인시던트 및 영향을 미치는 자산에 대한 정보도 포함됩니다.

식별된 각 위협에는 사이버 보안 탐지 및 분석의 최전방에 있는 Microsoft 보안 연구원이 작성한 종합적인 위협 분석 보고서인 분석가 보고서가 포함되어 있으며, 공격이 보안 보고서에 어떻게 나타나는지 Microsoft 365 Defender.

자세한 내용은 에서 위협 분석을 [Microsoft 365 Defender.](threat-analytics.md)

## <a name="collaborate-with-microsoft-experts"></a>Microsoft 전문가와 공동 작업

Microsoft 위협 전문가 - 대상 공격 알림은 관리되는 위협 헌팅 서비스입니다. 적용하고 수락하면 Microsoft 위협 전문가로부터 대상 공격 알림을 받으며, 환경에 대한 중요한 위협을 놓치지 않습니다. 이러한 알림은 조직의 끝점, 전자 메일 및 ID를 보호하는 데 도움이 됩니다. Microsoft 위협 전문가 – 요구 시 전문가를 통해 조직이 직면한 위협에 대한 전문가 조언을 얻을 수 있으며 조직이 직면한 위협에 대한 도움을 받을 수 있습니다. 추가 구독 서비스로 사용할 수 있습니다.

자세한 내용은 Microsoft 위협 전문가 [개요 Microsoft 365 참조하세요.](/security/mtp/microsoft-threat-experts.md)
