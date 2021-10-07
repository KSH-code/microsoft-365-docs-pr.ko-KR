---
title: 끝점용 Microsoft Defender API 릴리스 정보
description: 끝점 API 집합용 Microsoft Defender에 대한 업데이트에 대한 릴리스 정보입니다.
keywords: Endpoint API 릴리스 정보, mde, API, Endpoint용 Microsoft Defender API, 업데이트, 메모, 릴리스
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 677e23e9071148184f6131910bdc2e7c41c86693
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192007"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>끝점용 Microsoft Defender API 릴리스 정보

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

다음 정보에는 끝점 API용 Microsoft Defender에 대한 업데이트와 업데이트 날짜가 나열됩니다.

> [!TIP]
> RSS 피드: 다음 URL을 복사하여 피드 읽기에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다.
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>릴리스 정보 - 가장 오래된 버전(dd.mm.yyyy)

### <a name="06102021"></a>06.10.2021

- 새로운 평가 API 내보내기 방법 추가 - 델타 내보내기 소프트웨어 취약점 _평가(JSON 응답)_ 장치당 평가 방법 및 [속성 내보내기.](get-assessment-methods-properties.md)

### <a name="05252021"></a>05.25.2021

- 장치당 새 API [내보내기 평가 방법 및 속성이 추가되었습니다.](get-assessment-methods-properties.md)

### <a name="03052021"></a>03.05.2021

- 새로운 API 추가: [재구성 활동 메서드 및 속성](get-remediation-methods-properties.md).

### <a name="10022021"></a>10.02.2021

- 새 API 추가: [일괄 업데이트 경고 .](batch-update-alerts.md)

### <a name="25012021"></a>25.01.2021

- 고급 헌팅 [API에](run-advanced-query-api.md) 대한 속도 제한이 분당 15개에서 45회로 업데이트되었습니다.

### <a name="21012021"></a>21.01.2021

- 새 API 추가: [태그로 장치 찾기.](machine-tags.md)
- 새 API 추가: [가져오기 표시기](import-ti-indicators.md).

### <a name="03012021"></a>03.01.2021

- 업데이트된 경고 증거: ***detectionStatus** _, _*_parentProcessFilePath_*_ 및 _ *_parentProcessFileName_** 속성이 추가되었습니다.
- 경고 엔터티 [업데이트:](alerts.md) ***detectorId 속성이 추가되었습니다.***

### <a name="15122020"></a>15.12.2020

- 업데이트된 [장치](machine.md) 엔터티: ***IpInterfaces 목록이 추가되었습니다.*** 장치 [목록 을 참조하세요.](get-machines.md)

### <a name="04112020"></a>04.11.2020

- 새 API 추가: [장치 값 설정](set-device-value.md).
- 장치 [엔터티](machine.md) 업데이트: ***deviceValue 속성이 추가되었습니다.***

### <a name="01092020"></a>01.09.2020

- 관련 증거를 사용하여 경고 엔터티를 확장하는 옵션이 추가되었습니다. 경고 [목록 을 참조하세요.](get-alerts.md)
