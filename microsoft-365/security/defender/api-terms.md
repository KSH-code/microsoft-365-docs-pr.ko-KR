---
title: Microsoft 365 Defender API 라이선스 및 사용 약관
description: Microsoft 365 Defender의 API에 대한 라이선스 및 사용 약관에 대한 설명
keywords: api, api, 사용권, 사용 조건, api, 법적, 알림, 행동 강령
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
ms.openlocfilehash: 9b70311726b6c1c5bedf34a18ee1763255c93ba3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070071"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender API 라이선스 및 사용 약관

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

## <a name="official-terms"></a>공식 약관

Microsoft 365 Defender API는 Microsoft API 라이선스 및 사용 [약관에 따라 관리됩니다.](/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>법적 고지

Microsoft 및 모든 참가자는 Creative Commons Attribution 4.0 International Public License에 따라 이 리포지토리의 Microsoft 설명서 및 기타 콘텐츠에 대한 라이선스를 부여합니다. [](https://github.com/MicrosoftDocs/microsoft-365-docs) 자세한 내용은 LICENSE 파일을 [참조하세요.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

설명서에서 참조되는 Microsoft, Windows, Microsoft Azure 및/또는 기타 Microsoft 제품 및 서비스는 미국 및/또는 기타 국가에서 Microsoft의 상표 또는 등록 상표일 수 있습니다.

이 프로젝트의 라이선스는 Microsoft 이름, 로고 또는 상표를 사용할 수 있는 권한을 부여하지 않습니다. Microsoft의 일반 상표 지침은 [Microsoft 상표 에서 찾을 수 있습니다.](https://go.microsoft.com/fwlink/?LinkID=254653)

개인 정보 보호 정보는 Microsoft의 [개인 정보 보호에서 찾을 수 있습니다.](https://privacy.microsoft.com)

Microsoft와 모든 참가자는 해당 저작권, 특허권 또는 상표에 따라 암시적, 금반언 또는 기타로 에스투셀에 의해서든 다른 모든 권리를 보유합니다.

## <a name="other-restrictions"></a>기타 제한 사항

고급 헌팅 API에는 반환되는 결과 수와 검색할 수 있는 데이터에 대한 몇 가지 제한이 있습니다. [](/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations)

1. 지난 30일 동안의 데이터만 쿼리할 수 있습니다.
1. 결과에는 최대 100,000개 행이 포함됩니다.

### <a name="quotas-and-resource-allocation"></a>할당량 및 리소스 할당

Microsoft 365 Defender API에는 스로틀 임계값이 있습니다.

- **인시던트 API:** 분당 최대 50통 또는 시간당 1500개 호출
- **고급 헌팅 API:** 분당 최대 15통, 시간당 10분, 하루 4시간의 실행 시간

스로틀을 나타내는 HTTP 응답 상태 코드는 `429` 입니다.

요청이 스로틀된 경우 응답 본문에 다시 요청을 시작할 수 있는 시간이 표시됩니다.

## <a name="related-articles"></a>관련 문서

- [Microsoft 365 Defender API 개요](api-overview.md)
- [지원되는 Microsoft 365 Defender API](api-supported.md)
- [Microsoft 365 Defender API 액세스](api-access.md)