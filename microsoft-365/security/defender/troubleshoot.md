---
title: Microsoft 365 Defender 서비스 문제 해결
description: 해결 방법 찾기 및 알려진 Microsoft 365 Defender 문제 해결
keywords: Microsoft 위협 방지 문제 해결, 문제 해결, Azure ATP, 문제, 추가 기능, 설정 페이지
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
ms.openlocfilehash: 8d8083cbba3582c41ca91c57978675987822d0d9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073935"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Microsoft 365 Defender 서비스 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

이 섹션에서는 Microsoft 365 Defender 서비스를 사용할 때 발생할 수 있는 문제를 설명합니다.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Microsoft 365 Defender 콘텐츠가 표시되지 않습니다.

포털에서 인시던트, 관리 센터 또는 헌팅과 같은 탐색 창에 기능이 없는 경우 테넌트에 적절한 라이선스가 있는지 확인해야 합니다.

자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Id에 대한 Microsoft Defender 알림이 Microsoft 365 Defender 인시던트에 표시 되지 않습니다.

환경에 배포된 ID용 Microsoft Defender가 있지만 Microsoft 365 Defender 인시던트의 일부로 ID에 대한 Defender 경고가 없는 경우 Microsoft Cloud App Security 및 Id용 Defender 통합이 사용하도록 설정되어 있는지 확인해야 합니다.

자세한 내용은 [Id 통합에 대한 Microsoft Defender를 참조하세요.](/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>서비스를 켜기 위한 설정 페이지는 어디에 있나요?

Microsoft 365 Defender를 켜기 위해 Microsoft 365 보안 센터의 탐색 창에서 설정에 액세스합니다.  이 탐색 항목은 선행 권한 및 라이선스가 있는 [경우만 표시됩니다.](m365d-enable.md#check-license-eligibility-and-required-permissions)
