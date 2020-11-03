---
title: Microsoft 365 Defender Api 액세스
description: Microsoft 365 Defender Api에 액세스 하는 방법 알아보기
keywords: 액세스, api, 응용 프로그램 컨텍스트, 사용자 컨텍스트, aad 응용 프로그램, 액세스 토큰
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845023"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Microsoft 365 Defender Api 액세스

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.


 Microsoft 365 Defender는 프로그래밍 Api 집합을 통해 대부분의 데이터와 작업을 제공 합니다. 이러한 Api를 사용 하면 Microsoft 365 Defender 기능을 기반으로 워크플로와 로깅을 자동화할 수 있습니다. API 액세스를 사용 하려면 OAuth 2.0 인증이 필요 합니다. 자세한 내용은 [OAuth 2.0 인증 코드 흐름](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)을 참조 하십시오.


일반적으로 Api를 사용 하려면 다음 단계를 수행 해야 합니다.
- AAD 응용 프로그램 만들기
- 이 응용 프로그램을 사용 하 여 액세스 토큰 가져오기
- 토큰을 사용 하 여 Microsoft 365 Defender API에 액세스


**응용 프로그램 컨텍스트** 또는 **사용자 컨텍스트** 를 사용 하 여 Microsoft 365 Defender API에 액세스할 수 있습니다.

- **응용 프로그램 컨텍스트: (권장)** <br>
    로그인 한 사용자 없이 실행 되는 앱에서 사용 됩니다. 예를 들어 백그라운드 서비스 또는 daemons 실행 되는 앱입니다.

    응용 프로그램 컨텍스트를 사용 하 여 Microsoft 365 Defender API에 액세스 하기 위해 수행 해야 하는 단계는 다음과 같습니다.

  1. AAD 웹 응용 프로그램을 만듭니다.
  2. 해당 하는 경우 applicationFor 원하는 사용 권한 (예: **AdvancedHunting** **, all** )을 할당 합니다. 
  3. 이 응용 프로그램에 대 한 키를 만듭니다.
  4. 해당 키로 응용 프로그램을 사용 하 여 토큰을 가져옵니다.
  5. 토큰을 사용 하 여 Microsoft 365 Defender API에 액세스

     자세한 내용은 [Get access with application context](api-create-app-web.md)를 참조 하세요.


- **사용자 컨텍스트:** <br>
    사용자를 대신 하 여 API에서 작업을 수행 하는 데 사용 됩니다.

    응용 프로그램 컨텍스트를 사용 하 여 Microsoft 365 Defender API에 액세스 하기 위해 수행 해야 하는 단계는 다음과 같습니다.
  1. AAD 네이티브 응용 프로그램을 만듭니다.
  2. 원하는 사용 권한을 응용 프로그램에 할당 합니다. 예를 들어 AdvancedHunting, read, **read** **를 예로** 들 있습니다.
  3. 사용자 자격 증명으로 응용 프로그램을 사용 하 여 토큰을 가져옵니다.
  4. 토큰을 사용 하 여 Microsoft 365 Defender API에 액세스

     자세한 내용은 [사용자 컨텍스트로 액세스 가져오기](api-create-app-user-context.md)를 참조 하세요.


## <a name="related-topics"></a>관련 항목
- [Microsoft 365 Defender Api](api-supported.md)
- [응용 프로그램 컨텍스트를 사용 하 여 Microsoft 365 Defender에 액세스](api-create-app-web.md)
- [사용자 컨텍스트를 사용 하 여 Microsoft 365 Defender 액세스](api-create-app-user-context.md)
