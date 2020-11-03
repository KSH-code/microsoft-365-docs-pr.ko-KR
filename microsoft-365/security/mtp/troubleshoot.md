---
title: Microsoft 365 Defender 서비스 문제 해결
description: 알려진 Microsoft 365 Defender 문제에 대 한 해결 방법 및 해결 방법 찾기
keywords: Microsoft Threat Protection, 문제 해결, Azure ATP, 문제, 추가 기능, 설정 페이지 문제 해결
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
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844671"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Microsoft 365 Defender 서비스 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

이 섹션에서는 Microsoft 365 Defender 서비스를 사용할 때 발생할 수 있는 문제에 대해 설명 합니다.


## <a name="i-dont-see-microsoft-365-defender-content"></a>Microsoft 365 Defender 콘텐츠가 표시 되지 않음
포털의 인시던트, 작업 센터 또는 검색 등의 기능이 탐색 창에 표시 되지 않는 경우에는 테 넌 트에 적절 한 라이선스가 있는지 확인 해야 합니다. 

자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender for Identity alerts for Id 365 알림
사용자 환경에 Microsoft Defender for Identity가 배포 되어 있지만 Microsoft 365 Defender 인시던트의의 일환으로 Id 알림을 위한 Defender가 표시 되지 않는 경우 Microsoft Cloud App Security 및 Defender for Identity 통합을 사용 하도록 설정 했는지 확인 해야 합니다. 

자세한 내용은 [id 통합용 Microsoft Defender](https://docs.microsoft.com/cloud-app-security/aatp-integration)를 참조 하세요.

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>서비스를 켜는 설정 페이지는 어디에 있나요?
Microsoft 365 Defender를 켜려면 Microsoft 365 보안 센터의 탐색 창에서 **설정** 에 액세스 합니다. 이 탐색 항목은 [필수 사용 권한 및 라이선스가](mtp-enable.md#check-license-eligibility-and-required-permissions)있는 경우에만 표시 됩니다.
 

