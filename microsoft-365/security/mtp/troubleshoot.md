---
title: Microsoft 365 Defender 서비스 문제 해결
description: 알려진 Microsoft 365 Defender 문제 해결 방법 찾기
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925721"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Microsoft 365 Defender 서비스 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

이 섹션에서는 Microsoft 365 Defender 서비스를 사용할 때 발생할 수 있는 문제를 설명합니다.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Microsoft 365 Defender 콘텐츠가 표시되지 않습니다.

포털에서 인시던트, 관리 센터 또는 헌팅과 같은 탐색 창에 기능이 없는 경우 테넌트에 적절한 라이선스가 있는지 확인해야 합니다.

자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft 365 Defender 인시던트에 ID에 대한 Microsoft Defender 경고가 표시되지 않습니다.

사용자 환경에 Microsoft Defender for Identity를 배포했지만 Microsoft 365 Defender 인시던트의 일부로 ID에 대한 Defender 경고가 표시되지 않는 경우 Microsoft Cloud App Security 및 Id용 Defender 통합이 사용하도록 설정되어 있도록 해야 합니다.

자세한 내용은 [Microsoft Defender for Identity 통합을 참조하세요.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>서비스를 켜기 위한 설정 페이지는 어디에 있나요?

Microsoft 365 Defender를 켜기 위해 Microsoft 365 보안 센터의 탐색 창에서 설정에 액세스합니다.  이 탐색 항목은 선행 권한 및 라이선스가 있는 경우만 [표시됩니다.](mtp-enable.md#check-license-eligibility-and-required-permissions)
