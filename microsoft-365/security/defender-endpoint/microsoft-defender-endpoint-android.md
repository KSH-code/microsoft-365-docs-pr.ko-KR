---
title: Android의 Microsoft Defender ATP
ms.reviewer: ''
description: Android용 Microsoft Defender ATP를 설치하고 사용하는 방법을 설명
keywords: microsoft, defender, atp, android, 설치, 배포, 제거, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 32c42691b3a2b43f9740da26084bf45af0ee80f5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687784"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Android의 끝점용 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) 
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

이 항목에서는 Android용 끝점용 Defender를 설치, 구성, 업데이트 및 사용하는 방법을 설명합니다.

> [!CAUTION]
> Android용 Endpoint용 Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 시스템 오류가 발생할 수 있습니다.


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Android에 끝점용 Microsoft Defender를 설치하는 방법

### <a name="prerequisites"></a>필수 구성 요소

-   **최종 사용자의 경우**

    -   앱의 최종 사용자에게 할당된 끝점용 Microsoft Defender 라이선스입니다. 끝점 라이선싱 요구 사항에 대한 [Microsoft Defender를 참조하세요.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Intune 회사 포털 앱은 [Google Play에서](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 다운로드할 수 있으며 Android 장치에서 사용할 수 있습니다.

        -   또한 Intune 회사 포털 [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) 앱을 통해 디바이스를 등록하여 Intune 장치 준수 정책을 적용할 수 있습니다. 이렇게 하려면 최종 사용자에게 Microsoft Intune 라이선스가 할당됩니다.

    -   라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **관리자용**

    -   Microsoft Defender 보안 센터 포털에 액세스합니다.

        > [!NOTE]
        > Microsoft Intune은 Android에서 끝점용 Microsoft Defender를 배포할 수 있는 유일한 MDM(모바일 장치 관리) 솔루션입니다. 현재 등록된 장치만 Intune에서 Android용 끝점용 Defender 관련 장치 준수 정책을 적용하는 데 지원됩니다. 

    -   [Microsoft Endpoint Manager 관리 센터 에](https://go.microsoft.com/fwlink/?linkid=2109431)액세스하여 조직의 등록된 사용자 그룹에 앱을 배포합니다.

### <a name="system-requirements"></a>시스템 요구 사항

-   Android 6.0 이상을 실행하는 Android 장치.
-   Intune 회사 포털 앱은 [Google Play에서](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 다운로드하여 설치됩니다. Intune 장치 준수 정책을 적용하려면 장치 등록이 필요합니다.

### <a name="installation-instructions"></a>설치 지침

Android의 끝점용 Microsoft Defender는 레거시 장치 관리자 및 Android 엔터프라이즈 모드인 등록된 디바이스의 두 모드 모두에서 설치를 지원합니다.
**현재 회사 프로필 및 회사 소유의 완전히 관리되는 사용자 장치 등록이 있는 개인 소유의 디바이스는 Android Enterprise에서 지원됩니다. 다른 Android 엔터프라이즈 모드에 대한 지원이 준비되면 발표됩니다.**

Android에서 끝점용 Microsoft Defender 배포는 MDM(Microsoft Intune)을 통해 배포됩니다.
자세한 내용은 [Microsoft Intune을 통해 Android에서 끝점용 Microsoft Defender 배포를 참조하세요.](android-intune.md)


> [!NOTE]
> **Android의 끝점용 Microsoft [Defender는 Google Play에서 지금 사용할 수](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 있습니다.** <br> Intune에서 Google Play에 연결하여 장치 관리자 및 Android Enterprise 관리 모드로 끝점용 Microsoft Defender 앱을 배포할 수 있습니다. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Android에서 끝점용 Microsoft Defender를 구성하는 방법

Android 기능에서 끝점용 Microsoft Defender를 구성하는 방법에 대한 지침은 [Configure Microsoft Defender for Endpoint on Android features에서](android-configure.md)사용할 수 있습니다.



## <a name="related-topics"></a>관련 항목
- [Microsoft Intune을 통해 Android에서 끝점용 Microsoft Defender 배포](android-intune.md)
- [Android 기능에서 끝점에 대한 Microsoft Defender 구성](android-configure.md)

