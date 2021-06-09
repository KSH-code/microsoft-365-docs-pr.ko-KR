---
title: Microsoft Defender for Endpoint(Android용)
ms.reviewer: ''
description: Android에서 끝점용 Microsoft Defender를 설치하고 사용하는 방법을 설명
keywords: microsoft, defender, Endpoint용 Microsoft Defender, android, 설치, 배포, 제거, intune
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
ms.openlocfilehash: 499ac9a6ee81bacb79cd83993d510f87e11c62c6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844721"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender for Endpoint(Android용)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

이 항목에서는 Android에서 끝점용 Defender를 설치, 구성, 업데이트 및 사용하는 방법을 설명합니다.

> [!CAUTION]
> Android에서 Endpoint용 Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 시스템 오류가 발생할 수 있습니다.


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Android에 끝점용 Microsoft Defender를 설치하는 방법

### <a name="prerequisites"></a>필수 구성 요소

-   **최종 사용자의 경우**

    -   앱의 최종 사용자에게 할당된 끝점용 Microsoft Defender 라이선스입니다. 끝점 라이선싱 요구 사항에 대한 [Microsoft Defender를 참조하세요.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Intune 회사 포털 [앱은 Google Play에서](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 다운로드할 수 있으며 Android 장치에서 사용할 수 있습니다.

        -   또한 Intune 장치 준수 [](/mem/intune/user-help/enroll-device-android-company-portal) 정책을 적용하기 위해 Intune 회사 포털 앱을 통해 장치를 등록할 수 있습니다. 이렇게 하려면 최종 사용자에게 라이선스를 할당해야 Microsoft Intune 합니다.

    -   라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **관리자용**

    -   사이트 포털에 Microsoft Defender 보안 센터 액세스합니다.

        > [!NOTE]
        > Microsoft Intune Android에서 끝점용 Microsoft Defender를 배포하는 데 지원되는 유일한 MDM(모바일 장치 관리) 솔루션입니다. 현재 등록된 장치만 Intune에서 Android 관련 장치 준수 정책에 끝점용 Defender를 적용하는 데 지원됩니다. 

    -   Microsoft Endpoint Manager [관리 센터에](https://go.microsoft.com/fwlink/?linkid=2109431)액세스하여 조직의 등록된 사용자 그룹에 앱을 배포합니다.
        
### <a name="network-requirements"></a>네트워크 요구 사항

- 네트워크에 연결된 경우 Android의 끝점용 Microsoft Defender가 작동하려면 방화벽/프록시가 끝점 서비스 [URL용 Microsoft Defender에](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)액세스할 수 있도록 구성해야 합니다.

### <a name="system-requirements"></a>시스템 요구 사항

-   Android 6.0 이상을 실행하는 Android 장치.
-   Intune 회사 포털 [Google Play에서](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 다운로드하여 설치합니다. Intune 장치 준수 정책을 적용하려면 장치 등록이 필요합니다.

### <a name="installation-instructions"></a>설치 지침

Android의 끝점용 Microsoft Defender는 레거시 장치 관리자 및 Android 및 Android 모드의 두 모드 모두에 Enterprise 지원합니다.
**현재 회사 프로필이 있는 개인 소유 장치 및 회사 소유의 완전히 관리되는 사용자 장치 등록은 Android 2013에서 지원 Enterprise. 다른 Android Enterprise 모드에 대한 지원이 준비되면 발표됩니다.**

Android에서 끝점용 Microsoft Defender를 배포하는 것은 MDM(Microsoft Intune)을 통해 할 수 있습니다.
자세한 내용은 Deploy [Microsoft Defender for Endpoint on Android with Microsoft Intune.](android-intune.md)


> [!NOTE]
> **Android의 끝점용 Microsoft [Defender는 Google Play에서 지금 사용할 수](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 있습니다.** <br> Intune에서 Google Play에 연결하여 디바이스 관리자 및 Android 관리 모드에 걸쳐 끝점용 Microsoft Defender 앱을 Enterprise 수 있습니다. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Android에서 끝점용 Microsoft Defender를 구성하는 방법

Android 기능에서 끝점용 Microsoft Defender를 구성하는 방법에 대한 지침은 [Configure Microsoft Defender for Endpoint on Android features에서](android-configure.md)사용할 수 있습니다.



## <a name="related-topics"></a>관련 항목
- [Microsoft Intune으로 Microsoft Defender for Endpoint(Android용) 배포](android-intune.md)
- [Microsoft Defender for Endpoint(Android용) 기능 구성](android-configure.md)

