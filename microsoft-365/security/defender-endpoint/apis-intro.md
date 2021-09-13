---
title: 엔드포인트용 Microsoft Defender API에 액세스
ms.reviewer: ''
description: API를 사용하여 워크플로를 자동화하고 끝점용 Microsoft Defender 기능을 기반으로 혁신하는 방법을 배우기
keywords: api, api, wdatp, open api, 끝점 api용 Microsoft Defender, microsoft defender atp, 공개 api, 지원되는 api, 경고, 장치, 사용자, 도메인, ip, 파일, 고급 헌팅, 쿼리
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a49c4993e6d81c90139e043683193f2ee6e532bf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185923"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>엔드포인트용 Microsoft Defender API에 액세스

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Endpoint용 Defender는 프로그래밍 API 집합을 통해 많은 데이터와 작업을 노출합니다. 이러한 API를 통해 워크플로를 자동화하고 끝점용 Defender 기능을 기반으로 혁신할 수 있습니다. API 액세스에는 OAuth2.0 인증이 필요합니다. 자세한 내용은 [OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

끝점 API용 Defender에 대한 간략한 개요는 이 비디오를 시청하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4d73M]

일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.

- [AAD 응용 프로그램 만들기](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- 이 응용 프로그램을 사용하여 액세스 토큰 얻기
- 토큰을 사용하여 Endpoint API용 Defender 액세스

응용 프로그램 컨텍스트 또는 사용자  컨텍스트를 사용하여 Endpoint API용 Defender에 **액세스할 수 있습니다.**

- **응용 프로그램 컨텍스트: (권장)**

  로그인한 사용자가 없는 실행 앱에서 사용됩니다. 예를 들어 백그라운드 서비스 또는 데몬으로 실행된 앱입니다.

  응용 프로그램 컨텍스트를 통해 Endpoint API용 Defender에 액세스하는 데 필요한 단계:

  1. AAD 웹 응용 프로그램을 만들 수 있습니다.
  2. 원하는 사용 권한을 응용 프로그램에 할당합니다(예: '경고 읽기', '컴퓨터 격리').
  3. 이 응용 프로그램에 대한 키를 생성합니다.
  4. 응용 프로그램을 키와 함께 사용하여 토큰을 얻습니다.
  5. 토큰을 사용하여 끝점용 Microsoft Defender API에 액세스

     자세한 내용은 응용 프로그램 [컨텍스트를 통해 액세스 를 참조하세요.](exposed-apis-create-app-webapp.md)

- **사용자 컨텍스트:**

  사용자를 대신하여 API에서 작업을 수행하는 데 사용됩니다.

  응용 프로그램 컨텍스트를 통해 Endpoint API용 Defender에 액세스하기 위해 수행해야 하는 단계:

  1. AAD 네이티브 응용 프로그램을 만들 수 있습니다.
  2. 원하는 사용 권한을 응용 프로그램에 할당합니다(예: '경고 읽기', '컴퓨터 격리' 등).
  3. 사용자 자격 증명과 함께 응용 프로그램을 사용하여 토큰을 얻습니다.
  4. 토큰을 사용하여 끝점용 Microsoft Defender API에 액세스

     자세한 내용은 [사용자 컨텍스트를 통해 액세스 를 참조하세요.](exposed-apis-create-app-nativeapp.md)

## <a name="related-topics"></a>관련 항목

- [끝점 API용 Microsoft Defender](exposed-apis-list.md)
- [응용 프로그램 컨텍스트를 통해 끝점용 Microsoft Defender 액세스](exposed-apis-create-app-webapp.md)
- [사용자 컨텍스트를 통해 끝점용 Microsoft Defender 액세스](exposed-apis-create-app-nativeapp.md)
