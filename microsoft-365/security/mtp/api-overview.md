---
title: Microsoft 365 Defender API 개요
description: Microsoft 365 Defender에서 사용 가능한 API에 대해 자세히 알아보기
keywords: api, api, 개요, 인시던트, 인시던트, 위협 헌팅, Microsoft 365 defender
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
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719193"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Microsoft 365 Defender API 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender는 통합 준비가 완료된 플랫폼을 토대로 구축되었습니다.

Microsoft 365 Defender API를 사용하여 공유 인시던트 및 고급 헌팅 테이블을 기반으로 워크플로를 자동화합니다.

- **[결합된 인시던트 큐](api-incident.md)** - 인시던트 API에서 전체 공격 범위와 영향을 미치는 모든 자산을 함께 그룹화하여 중요한 일에 집중합니다.

- **[제품](api-advanced-hunting.md)** 간 위협 헌팅 - 보안 팀의 조직 지식을 활용하여 사용자 지정 쿼리를 만들어 여러 보호 제품에서 수집된 원시 데이터를 시차를 두어 손상 징후를 찾습니다.

이러한 Microsoft 365 Defender 관련 API와 함께 다른 각 보안 제품은 고유한 기능을 활용하는 데 도움이 되는 추가 [API를](api-articles.md) 노출합니다.

## <a name="learn-more"></a>자세한 정보

| **API 액세스 방법 이해** |
|-|
| [API 할당량 및 라이선싱에 대해 자세히](api-terms.md) |
| [Microsoft 365 Defender API 액세스](api-access.md) |
| **앱 빌드** |
| ['Hello world' 앱 만들기](api-hello-world.md) |
| [사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기](api-create-app-user-context.md) |
| [사용자 없이 Microsoft 365 Defender에 액세스하는 앱 만들기](api-create-app-web.md) |
| [Microsoft 365 Defender API에 대한 다중 테넌트 파트너 액세스가 있는 앱 만들기](api-partner-access.md) |
| **앱 문제 해결 및 유지 관리** |
| [API 오류 코드 이해](api-error-codes.md) |
| [Azure Key Vault를 사용하여 앱에서 비밀 관리](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [사용자 로그인에 대한 OAuth 2.0 권한 부여 구현](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
