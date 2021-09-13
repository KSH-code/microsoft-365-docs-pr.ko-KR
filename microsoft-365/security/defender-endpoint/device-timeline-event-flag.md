---
title: 끝점용 Microsoft Defender 장치 타임라인 이벤트 플래그
description: Microsoft Defender for Endpoint 장치 타임라인 이벤트 플래그를 사용하여
keywords: Endpoint 장치 타임라인에 대한 Defender, 이벤트 플래그
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 92d9a6dabc2d8f6251b46d58207170d0c460aa90
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222783"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a>끝점용 Microsoft Defender 장치 타임라인 이벤트 플래그

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Endpoint 장치 타임라인에 대한 Defender의 이벤트 플래그는 잠재적인 공격을 조사할 때 특정 이벤트를 필터링하고 구성하는 데 도움이 됩니다.

Endpoint 장치 타임라인에 대한 Defender는 장치에서 관찰된 이벤트 및 관련 경고를 시간 표시 막대로 제공합니다. 이 이벤트 목록은 디바이스에서 관찰된 모든 이벤트, 파일 및 IP 주소를 전체 표시하는 기능을 제공합니다. 목록이 긴 경우도 있습니다. 디바이스 타임라인 이벤트 플래그는 관련이 있을 수 있는 이벤트를 추적하는 데 도움이 됩니다.

장치 타임라인을 거치고 나면 플래그가 지정한 특정 이벤트를 정렬, 필터링 및 내보낼 수 있습니다.

디바이스 타임라인을 탐색하는 동안 특정 이벤트를 검색하고 필터링할 수 있습니다. 다음을 통해 이벤트 플래그를 설정할 수 있습니다.

- 가장 중요한 이벤트 강조 표시
- 심층적으로 진행해야 하는 이벤트 표시
- 위반 일정을 깔끔하게 구축

## <a name="flag-an-event"></a>이벤트 플래그 지정

1. 플래그를 지정하려는 이벤트 찾기
2. 플래그 열에서 플래그 아이콘을 클릭합니다. 
![장치 타임라인 플래그의 이미지입니다.](images/device-flags.png)
2. 플래그 열에서 플래그 아이콘을 클릭합니다.

   ![장치 타임라인 플래그의 이미지](images/device-flags.png)

## <a name="view-flagged-events"></a>플래그가 지정한 이벤트 보기

1. 시간 표시 막대 필터 **섹션에서** **Flagged 이벤트를 사용하도록 설정합니다.**
2. **적용** 을 클릭합니다. 플래그가 지정한 이벤트만 표시됩니다.
시간 표시줄을 클릭하여 추가 필터를 적용할 수 있습니다. 이 이벤트는 플래그가 지정된 이벤트 이전의 이벤트만 보여 주게 됩니다.  
![필터가 설정되어 있는 장치 타임라인 플래그의 이미지입니다.](images/device-flag-filter.png)
2. **적용** 을 클릭합니다. 플래그가 지정한 이벤트만 표시됩니다. 시간 표시줄을 클릭하여 추가 필터를 적용할 수 있습니다. 이 이벤트는 플래그가 지정된 이벤트 이전의 이벤트만 보여 주게 됩니다.

   ![필터가 설정되어 있는 장치 타임라인 플래그의 이미지](images/device-flag-filter.png)
