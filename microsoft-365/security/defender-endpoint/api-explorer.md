---
title: 끝점용 Microsoft Defender의 API 탐색기
ms.reviewer: ''
description: API 탐색기를 사용하여 API 쿼리를 생성하고, 테스트하고, 사용 가능한 모든 API에 대한 요청을 전송합니다.
keywords: api, 탐색기, 보내기, 요청, get, post,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 3235ed9e3b4f51b9156267e324573f04443eccc6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210044"
---
# <a name="api-explorer"></a>API 탐색기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

끝점 API 탐색기용 Microsoft Defender는 대화형으로 끝점 API용 다양한 Defender를 탐색하는 데 도움이 되는 도구입니다.

API 탐색기를 사용하면 끝점 API 끝점에 대해 사용 가능한 모든 Defender에 대한 API 쿼리를 쉽게 생성하고, 테스트하고, 요청을 보낼 수 있습니다. API 탐색기를 사용하여 작업을 수행하거나 사용자 인터페이스를 통해 아직 사용할 수 없는 데이터를 찾을 수 있습니다.

이 도구는 앱 개발 중에 유용합니다. 이를 통해 사용자 액세스 설정을 사용하는 API 쿼리를 수행하여 액세스 토큰 생성 필요성을 줄일 수 있습니다.

이 도구를 사용하여 샘플 쿼리 갤러리를 탐색하고 결과 코드 샘플을 복사하고 디버그 정보를 생성할 수 있습니다.

API 탐색기를 사용하여 다음을 할 수 있습니다.

- 모든 메서드에 대한 요청을 실행하고 실시간으로 응답을 볼 수 있습니다.
- API 샘플을 빠르게 탐색하고 지원되는 매개 변수에 대해 자세히 알아보기
- API 호출을 쉽게 만들 수 있습니다. 관리 포털 로그인 이상으로 인증할 필요가 없습니다.

## <a name="access-api-explorer"></a>Access API 탐색기

왼쪽 탐색 메뉴에서 Api **API &** \> **파트너를 선택합니다.**

## <a name="supported-apis"></a>지원되는 API

API 탐색기는 끝점용 Defender에서 제공하는 모든 API를 지원합니다.

지원되는 API 목록은 API 설명서에서 사용할 [수 있습니다.](apis-intro.md)

## <a name="get-started-with-the-api-explorer"></a>API 탐색기 시작

1. 왼쪽 창에는 사용할 수 있는 샘플 요청 목록이 있습니다.
2. 링크를 따라가고 쿼리 **실행을 클릭합니다.**

일부 샘플에서는 URL에 매개 변수를 지정해야 할 수 있습니다(예: {machine- ID}).

## <a name="faq"></a>FAQ

**API 탐색기를 사용하려면 API 토큰이 필요한가요?** <br>
API에 액세스하기 위한 자격 증명은 필요하지 않습니다. API 탐색기는 요청을 할 때마다 Endpoint용 Defender 관리 포털 토큰을 사용합니다.

로그인한 사용자 인증 자격 증명은 API 탐색기가 사용자를 대신하여 데이터에 액세스할 수 있는 권한이 있는지 확인하는 데 사용됩니다.

특정 API 요청은 RBAC 권한에 따라 제한됩니다. 예를 들어 "제출 표시기"에 대한 요청은 보안 관리자 역할로 제한됩니다.
