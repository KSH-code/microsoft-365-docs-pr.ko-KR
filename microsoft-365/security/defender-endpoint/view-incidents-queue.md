---
title: 인시던트 큐 보기 및 구성
ms.reviewer: ''
description: 인시던트 목록을 보고 필터를 적용하여 목록을 제한하고 보다 집중적인 보기를 얻을 수 있는 방법을 배워야 합니다.
keywords: 보기, 구성, 인시던트, 집계, 조사, 큐, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8bdc8451d3f3885cb9704a954cae8f439cad1abf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189369"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>엔드포인트용 Microsoft Defender 인시던트 큐 보기 및 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

**인시던트 큐에는** 네트워크의 장치에서 플래그가 지정된 인시던트 모음이 표시됩니다. 이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다.

기본적으로 큐에는 지난 30일 동안의 인시던트가 표시되고, 가장 최근 인시던트가 목록 맨 위에 표시되어 가장 최근 인시던트가 먼저 표시됩니다.

인시던트 큐 보기를 사용자 지정하기 위해 선택할 수 있는 몇 가지 옵션이 있습니다. 

위쪽 탐색에서 다음을 할 수 있습니다.
- 열을 추가 또는 제거하기 위해 열 사용자 지정 
- 페이지당 볼 항목 수 수정
- 페이지당 표시할 항목 선택
- 할당할 인시던트 선택 일괄 처리 
- 페이지 간 탐색
- 필터 적용

![인시던트 큐의 이미지입니다.](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a>인시던트 큐 정렬 및 필터링
다음 필터를 적용하여 인시던트 목록을 제한하고 보다 집중적인 보기를 얻을 수 있습니다.

### <a name="severity"></a>심각도

인시던트 심각도 | 설명
:---|:---
높음 </br>(빨강) | APT(고급 영구 위협)와 자주 관련된 위협. 이러한 인시던트는 장치에 노출될 수 있는 손상의 심각도로 인해 높은 위험을 나타냅니다.
보통 </br>(주황색) | 일반적인 레지스트리 변경, 의심스러운 파일 실행, 공격 단계의 일반적인 관찰 동작 등 조직에서 거의 발견되지 않습니다.
낮음 </br>(노란색) | 조직을 대상으로 하는 고급 위협을 나타낼 필요는 없는, 보급된 맬웨어 및 해킹 도구와 관련된 위협.
정보 </br>(회색) | 정보 인시던트는 네트워크에 해로운 것으로 간주되지는 않지만 추적하는 것이 좋습니다.

## <a name="assigned-to"></a>할당된 사용자
필터를 사용하여 특정 담당자에게 할당 된 목록이나 자신에게 할당된 목록을 선택할 수 있습니다. 

### <a name="category"></a>범주
인시던트는 사이버 보안 킬체인이 있는 단계에 대한 설명에 따라 분류됩니다. 이 보기는 위협 분석가가 컨텍스트에 따라 배포할 우선 순위, 긴급성 및 해당 응답 전략을 결정하는 데 도움이 됩니다.

### <a name="status"></a>상태
상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다.

### <a name="data-sensitivity"></a>데이터 민감도
이 필터를 사용하여 민감도 레이블이 포함된 인시던트가 표시됩니다.

## <a name="incident-naming"></a>인시던트 이름

인시던트의 범위를 한눈에 이해하기 위해 인시던트 이름은 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 자동으로 생성됩니다.

예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*

> [!NOTE]
> 자동 인시던트 명명을 출시하기 전에 존재한 인시던트의 이름은 그대로 유지됩니다.


## <a name="see-also"></a>참고 항목
- [인시던트 큐](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [인시던트 관리](manage-incidents.md)
- [인시던트 조사](investigate-incidents.md)

