---
title: 엔드포인트용 Microsoft Defender API에 액세스
ms.reviewer: ''
description: API를 사용하여 워크플로우를 자동화하고 엔드포인트 기능에 대한 Microsoft Defender를 기반으로 혁신하는 방법을 알아보십시오.
keywords: apis, api, wdatp, 오픈 API, 엔드 포인트 API용 마이크로 소프트 수비수, 마이크로 소프트 수비수 ATP, 공개 API, 지원 api, 경고, 장치, 사용자, 도메인, IP, 파일, 고급 사냥, 쿼리
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
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571832"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>엔드포인트용 Microsoft Defender API에 액세스 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**적용 대상:** 
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 엔드포인트에 대한 마이크로 소프트 디펜더를 경험하고 싶으십니까? [무료 평가판에 가입하십시오.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



엔드포인트의 수비수는 프로그래밍 방식API 집합을 통해 많은 데이터와 작업을 노출합니다. 이러한 API를 사용하면 워크플로우를 자동화하고 엔드포인트 용 Defender 기능을 기반으로 혁신할 수 있습니다. API 액세스에는 OAuth2.0 인증이 필요합니다. 자세한 내용은 [OAuth 2.0 권한 부여 코드 Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)참조하십시오.

엔드포인트의 API에 대한 수비수에 대한 간략한 개요를 보려면 이 비디오를 시청하십시오. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.
- [AAD 응용 프로그램](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp) 만들기
- 이 응용 프로그램을 사용하여 액세스 토큰 받기
- 토큰을 사용하여 끝점 API에 대한 Defender에 액세스


응용 프로그램 컨텍스트 또는 사용자 **컨텍스트가** 있는 끝점 API에 대한 Defender에 액세스할 수 **있습니다.**

- **응용 프로그램 컨텍스트: (권장)** <br>
    로그인한 사용자 없이 실행되는 앱에서 사용됩니다. 예를 들어 백그라운드 서비스 또는 데몬으로 실행되는 앱입니다.

    응용 프로그램 컨텍스트를 사용하여 끝점 API에 대한 Defender에 액세스하려면 수행해야 하는 단계:

  1. AAD 웹 응용 프로그램을 만듭니다.
  2. 응용 프로그램에 원하는 권한을 할당합니다(예: '경고 읽기', '컴퓨터 격리'). 
  3. 이 응용 프로그램에 대한 키를 만듭니다.
  4. 키가 있는 응용 프로그램을 사용하여 토큰을 가져옵니다.
  5. 토큰을 사용하여 엔드포인트 API에 대한 Microsoft Defender에 액세스

     자세한 내용은 [응용 프로그램 컨텍스트를 통해 액세스 하기 를](exposed-apis-create-app-webapp.md)참조하십시오.


- **사용자 컨텍스트:** <br>
    사용자를 대신하여 API에서 작업을 수행하는 데 사용됩니다.

    응용 프로그램 컨텍스트를 사용하여 끝점 API에 대한 Defender에 액세스하는 단계:

  1. AAD 네이티브 응용 프로그램을 만듭니다.
  2. 응용 프로그램에 원하는 권한을 할당합니다(예: '경고 읽기', '컴퓨터 격리' 등) 
  3. 사용자 자격 증명이 있는 응용 프로그램을 사용하여 토큰을 가져옵니다.
  4. 토큰을 사용하여 엔드포인트 API에 대한 Microsoft Defender에 액세스

     자세한 내용은 [사용자 컨텍스트를 통해 액세스 하기 를](exposed-apis-create-app-nativeapp.md)참조하십시오.


## <a name="related-topics"></a>관련 항목
- [엔드포인트 API용 마이크로소프트 수비수](exposed-apis-list.md)
- [응용 프로그램 컨텍스트와 끝점에 대 한 마이크로소프트 수비수 액세스](exposed-apis-create-app-webapp.md)
- [사용자 컨텍스트를 통해 엔드포인트에 대한 Microsoft Defender 액세스](exposed-apis-create-app-nativeapp.md)
