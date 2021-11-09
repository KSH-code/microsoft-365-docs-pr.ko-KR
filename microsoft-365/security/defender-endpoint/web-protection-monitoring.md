---
title: 끝점용 Microsoft Defender의 웹 검색 보안 모니터링
description: 끝점용 Microsoft Defender의 웹 보호를 사용하여 웹 검색 보안 모니터링
keywords: 웹 보호, 웹 위협 방지, 웹 검색, 모니터링, 보고서, 카드, 도메인 목록, 보안, 피싱, 맬웨어, 악용, 웹 사이트, 네트워크 보호, Edge, Internet Explorer, Chrome, Firefox, 웹 브라우저
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4bbe7fa9bb9db540451c2878806f04b0d31b1165
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881844"
---
# <a name="monitor-web-browsing-security"></a>웹 검색 보안 모니터링

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

웹 보호를 사용하면 웹 포털의 보고서 및  웹 보호에 > 통해 조직의 웹 검색 보안을 Microsoft 365 Defender 있습니다. 이 보고서에는 웹 위협 감지 통계를 제공하는 카드가 포함되어 있습니다.

- **시간 경과에** 대한 웹 위협 방지 감지 - 이 추세 카드는 선택한 기간(지난 30일, 지난 3개월, 지난 6개월) 동안 유형별로 검색된 웹 위협 수를 표시합니다.

  :::image type="content" alt-text="시간이 지날 때 웹 위협 방지 감지를 보여 주며 카드의 이미지입니다." source="images/wtp-blocks-over-time.png" lightbox="images/wtp-blocks-over-time.png":::

- **웹 위협 방지** 요약 - 이 카드는 지난 30일 동안의 총 웹 위협 감지를 표시하여 다양한 유형의 웹 위협에 대한 배포를 표시합니다. 조각을 선택하면 악성 또는 원치 않는 웹 사이트에서 발견된 도메인 목록이 열립니다.

  :::image type="content" alt-text="웹 위협 방지 요약을 보여 주며 카드의 이미지입니다." source="images/wtp-summary.png" lightbox="images/wtp-summary.png":::

> [!NOTE]
> 블록이 카드 또는 도메인 목록에 반영되기까지 최대 12시간이 걸릴 수 있습니다.

## <a name="types-of-web-threats"></a>웹 위협 유형

웹 보호는 악성 및 원치 않는 웹 사이트를 다음과 같은 분류합니다.

- **피싱** - 사용자가 자격 증명 및 기타 중요한 정보를 유출하도록 설계된 스푸핑된 웹 양식 및 기타 피싱 메커니즘을 포함하는 웹 사이트
- **악성** - 맬웨어를 호스트하고 코드를 악용하는 웹 사이트
- **사용자 지정 표시기** - 차단을 위해 사용자 지정 표시기 목록에 추가한 URL 또는 [도메인](manage-indicators.md) 웹 사이트

## <a name="view-the-domain-list"></a>도메인 목록 보기

웹 위협 방지 요약  카드에서 특정 웹 위협 범주를 선택하여 도메인 페이지를 **열** 수 있습니다. 이 페이지에는 해당 위협 범주의 도메인 목록이 표시됩니다. 이 페이지에서는 각 도메인에 대해 다음 정보를 제공합니다.

- **액세스 횟수** - 도메인의 URL에 대한 요청 수
- **블록** - 요청이 차단된 횟수
- **액세스 추세** - 액세스 시도 횟수 변경
- **위협 범주** - 웹 위협 유형
- **장치** - 액세스 시도가 있는 장치 수

해당 도메인의 URL에 액세스하려고 시도한 장치 목록과 URL 목록을 확인하려면 도메인을 선택합니다.

## <a name="related-topics"></a>관련 항목

- [웹 보호 개요](web-protection-overview.md)
- [웹 컨텐츠 필터링](web-content-filtering.md)
- [웹 위협 방지](web-threat-protection.md)
- [웹 위협에 대응](web-protection-response.md)
