---
title: API Microsoft 365 Defender 개요
description: 2013에서 사용 가능한 API에 대해 Microsoft 365 Defender
keywords: api, api, 개요, 인시던트, 인시던트, 위협 헌팅, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2ca601c3c68df9f9f1cc4fb90bcfbe907850ce91
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214615"
---
# <a name="overview-of-microsoft-365-defender-apis"></a>API Microsoft 365 Defender 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

Microsoft 365 Defender 준비된 플랫폼을 토대하여 구축됩니다.

이 Microsoft 365 Defender API를 사용하여 공유 인시던트 및 고급 헌팅 테이블을 기반으로 워크플로를 자동화합니다.

- **[결합된](api-incident.md)** 인시던트 큐 - 인시던트 API에서 전체 공격 범위 및 영향을 미치는 모든 자산을 그룹화하여 중요한 일에 집중합니다.

- **[제품](api-advanced-hunting.md)** 간 위협 헌팅 - 여러 보호 제품에서 수집된 원시 데이터를 분산하기 위해 사용자 지정 쿼리를 만들어 보안 팀의 조직 지식을 활용하여 손상 징후를 찾습니다.

Streaming [API를](../defender-endpoint/raw-data-export.md) 사용하여 단일 데이터 스트림 내에서 발생하는 실시간 이벤트 및 인스턴스의 경고를 제공합니다.

이러한 Microsoft 365 Defender 특정 API와 함께 다른 각 보안 제품은 고유한 [](api-articles.md) 기능을 활용하는 데 도움이 되는 추가 API를 노출합니다.

> [!NOTE]
> 통합 포털로 전환하면 끝점 API용 Microsoft Defender를 기반으로 하는 PowerBi 대시보드에 영향을 주지 않습니다. 대화형 포털 전환에 관계없이 기존 API를 계속 사용할 수 있습니다.

## <a name="learn-more"></a>자세히 알아보기

| **API 액세스 방법 이해** |
|-|
| [API 할당량 및 라이선싱에 대해 자세히](api-terms.md) |
| [MICROSOFT 365 DEFENDER API에 액세스](api-access.md) |
| **앱 빌드** |
| ['Hello world' 앱 만들기](api-hello-world.md) |
| [사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기](api-create-app-user-context.md) |
| [사용자가 없는 앱에 액세스하는 Microsoft 365 Defender 만들기](api-create-app-web.md) |
| [다중 테넌트 파트너가 액세스하여 테넌트 API에 Microsoft 365 Defender 만들기](api-partner-access.md) |
| **앱 문제 해결 및 유지 관리** |
| [API 오류 코드 이해](api-error-codes.md) |
| [Azure Key Vault를 사용하여 앱에서 비밀 관리](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [사용자 로그인에 대한 OAuth 2.0 권한 부여 구현](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |