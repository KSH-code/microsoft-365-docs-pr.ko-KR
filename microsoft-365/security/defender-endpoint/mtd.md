---
title: Endpoint용 Microsoft Defender - Mobile Threat Defense
ms.reviewer: ''
description: 끝점용 Microsoft Defender의 모바일 위협 방어 개요
keywords: mobile, defender, Endpoint용 Microsoft Defender, ios, mtd, android, security
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8de50b9f06f05c012cc2b4c789838612d98abe62
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557308"
---
# <a name="microsoft-defender-for-endpoint---mobile-threat-defense"></a>Endpoint용 Microsoft Defender - Mobile Threat Defense

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Android 및 iOS의 끝점용 Microsoft Defender는 **MTD(모바일 위협 방어 솔루션)입니다.** 일반적으로 회사에서는 모바일 장치가 자주 비위정화되어 보호되지 않는 반면, PC를 취약성 및 공격으로부터 보호하는 데 주력하고 있습니다. 모바일 플랫폼에 앱 차단 및 소비자 앱 스토어를 정한 등의 기본 제공 보호가 있는 경우 이러한 플랫폼은 웹 기반 또는 기타 정교한 공격에 취약합니다. 더 많은 직원이 업무에 장치를 사용하며 중요한 정보에 액세스하는 경우 회사에서 모바일에 대한 점점 더 정교한 공격으로부터 장치와 리소스를 보호하기 위해 MTD 솔루션을 배포해야 합니다.

## <a name="key-capabilities"></a>주요 기능

Android 및 iOS의 끝점용 Microsoft Defender는 아래의 주요 기능을 제공합니다. 최신 기능 및 이점에 대한 자세한 내용은 공지 [사항을 읽어 보세요.](https://aka.ms/mdeblog)

<br>

|기능|설명|
|---|---|
|웹 보호|피싱 방지, 안전하지 않은 네트워크 연결 차단 및 사용자 지정 표시기 지원|
|맬웨어 보호(Android 전용)|악성 앱 검색.|
|탈옥 검색(iOS 전용)|무단으로 보호된 장치 검색.|
|통합 알림|통합 M365 보안 콘솔의 모든 플랫폼에서 알림|
|조건부 액세스, 조건부 실행|위험한 장치가 회사 리소스에 액세스하지 않습니다. 끝점 위험 신호에 대한 Defender를 MAM(앱 보호 정책)에 추가할 수도 있습니다.|
|통합 Microsoft Tunnel|VPN 게이트웨이 솔루션인 Microsoft Tunnel 통합하여 단일 앱에서 보안 및 연결을 사용할 수 있습니다. 현재 Android에서만 사용 가능|

이러한 모든 기능은 끝점용 Microsoft Defender 라이선스 보유자가 사용할 수 있습니다. 자세한 내용은 라이선스 요구 [사항을 참조하세요.](minimum-requirements.md#licensing-requirements)

## <a name="overview-and-deploy"></a>개요 및 배포

모바일에서 끝점용 Microsoft Defender 배포는 MEM(Microsoft Endpoint Manager)을 통해 수행될 수 있습니다. MTD 기능 및 배포에 대한 간략한 개요는 이 비디오를 시청하세요.

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMpiC]

자세한 내용은 아래 링크를 참조하세요.

**Android:** [Android용 끝점용 Microsoft Defender](microsoft-defender-endpoint-android.md)

**iOS:** [iOS의 끝점용 Microsoft Defender](microsoft-defender-endpoint-ios.md)

### <a name="pilot-evaluation"></a>파일럿 평가

끝점용 Microsoft Defender를 사용하여 모바일 위협 방어를 평가하는 동안 더 큰 장치 집합에 서비스를 배포하기 전에 특정 기준이 충족되는지 확인할 수 있습니다. 종료 조건을 정의하고 광범위하게 배포하기 전에 충족되도록 할 수 있습니다.

이렇게 하면 서비스를 롤아웃하는 동안 발생할 수 있는 잠재적인 문제를 줄일 수 있습니다. 다음은 도움이 될 수 있는 몇 가지 테스트 및 종료 조건입니다.

- 장치 인벤토리 목록에 장치 표시: 모바일 장치에서 끝점용 Defender를 성공적으로 온보딩한 후 장치가 보안 콘솔의 장치 인벤토리에 [나열되어 있는지 확인합니다.](https://security.microsoft.com)

- Android 장치에서 맬웨어 감지 테스트 실행: Google Play 스토어에서 테스트 바이러스 앱을 설치하고 끝점용 Microsoft Defender에서 검색하는지 확인합니다. 다음은 이 테스트에 사용할 수 있는 예제 앱입니다. [바이러스 테스트](https://play.google.com/store/apps/details?id=com.androidantivirus.testvirus). Android Enterprise 프로필이 있는 경우 작업 프로필만 지원됩니다.

- 피싱 테스트 실행: 끝점용 Microsoft Defender에서 차단하는지 https://smartscreentestratings2.net 찾아보고 확인을 합니다. Android Enterprise 프로필이 있는 경우 작업 프로필만 지원됩니다.

- 경고는 대시보드에 나타납니다. 위의 검색 테스트에 대한 알림이 보안 콘솔에 [나타나는지 확인합니다.](https://security.microsoft.com)

## <a name="deployment-best-practices"></a>배포 모범 사례

### <a name="end-user-onboarding"></a>최종 사용자 온보드

- [사용자 온보딩을](android-configure.md#conditional-access-with-defender-for-endpoint-on-android)적용하도록 조건부 액세스 구성: 이 설정을 적용하여 최종 사용자가 배포 후 끝점용 Microsoft Defender 앱에 온보딩하도록 할 수 있습니다. 끝점 위험 신호에 대한 Defender로 조건부 액세스 구성에 대한 빠른 데모를 위해 이 비디오를 시청합니다. 

  <br/>

  > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMwR1]

### <a name="simplify-onboarding"></a>온보더링 간소화

- [Android Enterprise - Always-on VPN을 설치합니다.](android-intune.md#auto-setup-of-always-on-vpn)
- [iOS - VPN 프로필 자동 설정](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)

## <a name="configure"></a>구성하기

- [Android 기능 구성](android-configure.md)
- [iOS 기능 구성](ios-configure-features.md)
- [감독되는 iOS 장치에 대한 감독 모드 구성](ios-install.md#configure-microsoft-defender-for-endpoint-for-supervised-mode)

## <a name="resources"></a>리소스

- [Microsoft Defender for Endpoint(Android용)](microsoft-defender-endpoint-android.md)
- [Microsoft Defender for Endpoint(iOS용)](microsoft-defender-endpoint-ios.md)
- 공지 사항을 읽어 예정된 릴리스에 대한 정보를 [계속 읽습니다.](https://aka.ms/mdeblog)

