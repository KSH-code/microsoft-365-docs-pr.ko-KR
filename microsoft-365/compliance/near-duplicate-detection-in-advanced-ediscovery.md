---
title: 중복에 가까운 검색 - eDiscovery
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
description: 중복에 가까운 검색을 사용하여 문서에서 사례 데이터를 분석할 때 텍스트적으로 유사한 문서를 그룹화할 Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216762"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>검색된 항목의 중복에 가까운 Advanced eDiscovery

하위 집합이 동일한 템플릿을 기반으로 하여 상용구 언어가 대부분 동일한 문서 집합을 검토할 수 있으며 여기에서 몇 가지 차이점이 있습니다. 검토자에서 이 하위 집합을 식별하고, 해당 하위 집합 중 하나를 철저하게 검토하고 나머지 부분의 차이점을 검토할 수 있는 경우 모든 문서의 내용을 읽는 데 몇 분의 시간만 들이면서 고유한 정보를 놓치지 않을 것입니다. 근사 중복 검색 시 텍스트로 유사한 문서를 그룹화하여 검토 프로세스를 더욱 효율적으로 만드는 데 도움이 됩니다.

## <a name="how-does-it-work"></a>작동 방식

근사 중복 검색이 실행될 경우, 시스템에서 모든 문서를 텍스트로 구문 분석합니다. 그런 다음 각 문서를 서로 비교하여 유사성의 기준이 설정된 임계값보다 큰지 확인할 수 있습니다. 문서가 있는 경우 문서가 함께 그룹화됩니다. 모든 문서를 비교하고 그룹화하고 나면 각 그룹의 문서가 "피벗"으로 표시됩니다. 문서를 검토할 때 피벗을 먼저 검토하고 같은 중복 집합에서 다른 문서를 검토하면서 피벗과 검토할 문서의 차이를 중점적으로 다룰 수 있습니다.
