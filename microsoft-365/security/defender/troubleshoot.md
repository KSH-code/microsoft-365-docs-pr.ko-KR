---
title: Defender Microsoft 365 문제 해결
description: 알려진 Defender 문제에 대한 해결 Microsoft 365 해결 방법 찾기
keywords: 문제 Microsoft 365 Defender, 문제 해결, ID에 대한 Microsoft Defender, 문제, 추가 기능, 설정 페이지
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
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782744"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Defender Microsoft 365 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

이 섹션에서는 Defender 서비스를 사용할 때 Microsoft 365 문제를 해결합니다.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Defender 콘텐츠가 Microsoft 365 없습니다.

포털에서 인시던트, 관리 센터 또는 헌팅과 같은 탐색 창에 기능이 없는 경우 테넌트에 적절한 라이선스가 있는지 확인해야 합니다.

자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Id에 대한 Microsoft Defender 경고가 Microsoft 365 없습니다.

환경에 배포된 ID용 Microsoft Defender가 있지만 Microsoft 365 Defender 인시던트의 일부로 ID 경고에 대한 Defender가 없는 경우 id에 대한 Microsoft Cloud App Security 및 Defender 통합이 사용하도록 설정되어 있도록 해야 합니다.

자세한 내용은 [Id 통합에 대한 Microsoft Defender를 참조하세요.](/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>서비스를 켜기 위한 설정 페이지는 어디에 있나요?

Defender를 Microsoft 365 설정하기 위해  설정 센터의 탐색 창에서 Microsoft 365 액세스합니다. 이 탐색 항목은 선행 권한 및 라이선스가 있는 [경우만 표시됩니다.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>내 파일/URL에 대한 예외를 만드는 방법

가짓 긍정은 악성으로 검색되지만 위협이 아닌 파일 또는 URL입니다. 표시기를 만들고 제외를 정의하여 차단을 해제하고 특정 파일/URL을 허용할 수 있습니다. [끝점에 대한 Defender에서 가짓 긍정/부정 주소를 참조하세요.](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)


