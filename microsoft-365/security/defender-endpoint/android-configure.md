---
title: Microsoft Defender for Endpoint(Android용) 기능 구성
description: Android에서 끝점용 Microsoft Defender를 구성하는 방법을 설명
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mde, android, 구성
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 53eed34cfff6d2318b87e781b32a9963c372b279
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60667389"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Android 기능에서 끝점에 대한 Defender 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Android의 끝점용 Defender를 통해 조건부 액세스

Android의 끝점용 Microsoft Defender 및 Microsoft Intune Azure Active Directory 위험 수준에 따라 장치 준수 및 조건부 액세스 정책을 시행할 수 있습니다. Endpoint용 Defender는 Intune을 통해 이 기능을 활용하기 위해 배포할 수 있는 MTD(Mobile Threat Defense) 솔루션입니다.

Android 및 조건부 액세스에서 끝점용 Defender를 설정하는 방법에 대한 자세한 내용은 Endpoint 및 [Intune용 Defender를 참조하세요.](/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>사용자 지정 표시기 구성

> [!NOTE]
> Android의 끝점용 Defender는 IP 주소 및 URL/도메인에 대한 사용자 지정 표시기 만들기만 지원됩니다.

Android의 끝점용 Defender를 사용하면 관리자가 Android 장치도 지원하도록 사용자 지정 표시기를 구성할 수 있습니다. 사용자 지정 표시기를 구성하는 방법에 대한 자세한 내용은 [지표 관리를 참조하세요.](manage-indicators.md)

## <a name="configure-web-protection"></a>웹 보호 구성
Android의 끝점용 Defender를 통해 IT 관리자는 웹 보호 기능을 구성할 수 있습니다. 이 기능은 Microsoft Endpoint Manager 관리 센터에서 사용할 수 있습니다.

> [!NOTE]
> Android의 끝점용 Defender는 웹 보호 기능을 제공하기 위해 VPN을 사용하게 됩니다. 이는 일반 VPN이 아니며 장치 외부에서 트래픽을 취하지 않는 로컬/자체 루프 VPN입니다.
> 자세한 내용은 Android를 실행 하는 장치에서 웹 보호 [구성을 참조하세요.](/mem/intune/protect/advanced-threat-protection-manage-android)


## <a name="configure-vulnerability-assessment-of-apps-for-byod-devices"></a>BYOD 장치에 대한 앱의 취약점 평가 구성

Android의 끝점용 Microsoft Defender 버전 1.0.3425.0303에서 온보딩된 모바일 장치에 설치된 OS 및 앱의 취약점 평가를 실행할 수 있는 기능이 있습니다.

> [!NOTE]
> 취약점 평가는 끝점용 Microsoft Defender의 위협 및 취약성 관리의 일부입니다. [](next-gen-threat-and-vuln-mgt.md) Android에서 이 기능은 현재 미리 보기로, 상업적으로 출시되기 전에 상당수 수정될 수 있습니다.

**BYOD(개인 장치)의 앱과 관련된 개인 정보 보호에 대한 참고 사항:**

- Android Enterprise 프로필이 있는 경우 작업 프로필에 설치된 앱만 지원됩니다.
- 다른 BYOD 모드의 경우 기본적으로 앱의 취약점 평가는 **사용되지** 않습니다. 그러나 디바이스가 관리자 모드인 경우 관리자는 디바이스에 설치된 앱 목록을 Microsoft Endpoint Manager 기능을 통해 이 기능을 명시적으로 사용하도록 설정할 수 있습니다. 자세한 내용은 설명서를 참조하세요.

### <a name="configure-privacy-for-device-administrator-mode"></a>장치 관리자 모드에 대한 개인 정보 구성

다음 단계에  따라 대상 사용자에 대해  장치 관리자 모드에서 장치에서 앱의 취약점 평가를 사용하도록 설정할 수 있습니다. 

> [!NOTE]
> 기본적으로 장치 관리 모드로 등록된 디바이스에서는 이 설정이 해제되어 있습니다.

1. Microsoft Endpoint Manager [관리](https://go.microsoft.com/fwlink/?linkid=2109431) 센터에서 장치 **구성** 프로필 프로필 만들기로 이동하여 다음 설정을  >    >   입력합니다.

   - **플랫폼:** Android 장치 관리자 선택
   - **프로필**: "사용자 지정"을 선택하고 만들기를 클릭합니다.

2. 기본 **섹션에서** 프로필의 이름과 설명을 지정합니다.

3. 구성 **설정에서** **OMA-URI 설정 추가를** 선택합니다.

   - **이름:** 나중에 쉽게 찾을 수 있도록 이 OMA-URI 설정에 대한 고유한 이름과 설명을 입력합니다.
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderTVMPrivacyMode**
   - 데이터 형식: 드롭다운 목록에서 정수(Integer)를 선택합니다.
   - 값: 개인 정보 설정을 사용하지 않도록 설정하기 위해 0을 입력합니다(기본값은 1).

4. **다음을** 클릭하고 이 프로필을 대상 장치/사용자에게 할당합니다.

### <a name="configure-privacy-for-android-enterprise-work-profile"></a>Android 및 작업 프로필에 Enterprise 개인 정보 구성

Endpoint용 Defender는 작업 프로필에서 앱의 취약점 평가를 지원합니다. 그러나 대상 사용자에 대해 이 기능을 해제하려는 경우 다음 단계를 사용할 수 있습니다.

1. Microsoft Endpoint Manager [관리 센터에서](https://go.microsoft.com/fwlink/?linkid=2109431) 앱 **앱** 구성 정책 관리되는 장치  >    >    >  **추가로 이동하세요.**
2. 정책에 이름을 지정합니다. **Platform > Android Enterprise**; 프로필 유형을 선택합니다.
3. 대상 **앱으로 끝점용 Microsoft Defender를** 선택합니다.
4. 설정 페이지에서 구성 디자이너  사용을 선택하고 키 및 값 유형으로 **DefenderTVMPrivacyMode를** **정수로 추가합니다.**
   - 작업 프로필에서 앱의 취약성을 사용하지 않도록 설정하려면 값을 1로 입력하고 이 정책을 사용자에게 할당합니다. 기본적으로 이 값은 0으로 설정됩니다.
   - 키가 '0'으로 설정된 사용자의 경우 Defender는 취약점 평가를 위해 작업 프로필에서 백end 서비스로 앱 목록을 전송합니다.
5. **다음을** 클릭하고 이 프로필을 대상 장치/사용자에게 할당합니다.

위의 개인 정보 컨트롤을 켜거나 끄면 장치 준수 검사 또는 조건부 액세스에 영향을 미치지 않습니다.


## <a name="configure-privacy-for-malware-threat-report"></a>맬웨어 위협 보고서에 대한 개인 정보 구성

> [!NOTE]
> Android의 Endpoint용 Defender에 대한 개인 정보 보호 컨트롤은 현재 미리 보기에 있으며 상업적으로 출시되기 전에 상당수 수정될 수 있습니다.

맬웨어 위협 보고서에 대한 개인 정보 제어를 사용하여 맬웨어 위협 보고서에서 앱 세부 정보(이름 및 패키지 정보)의 컬렉션을 사용하지 않도록 설정할 수 있습니다. 이렇게 하면 조직에서 악의적인 앱이 감지될 때 앱 이름을 수집할지 여부를 선택할 수 있습니다. *이 기능은 현재 Android 장치 관리자 모드로 등록된 **디바이스에서만 사용할 수** 있습니다.*

다음 단계에 따라 대상 사용자에 대해 이 기능을 켜세요.

1. Microsoft Endpoint Manager [관리](https://go.microsoft.com/fwlink/?linkid=2109431) 센터에서 장치 **구성** 프로필 프로필 만들기로 이동하여 다음 설정을  >    >   입력합니다.

   - **플랫폼:** Android 장치 관리자 선택
   - **프로필**: "사용자 지정"을 선택하고 만들기를 클릭합니다.

2. 기본 **섹션에서** 프로필의 이름과 설명을 지정합니다.

3. 구성 **설정에서** **OMA-URI 설정 추가를** 선택합니다.

   - **이름:** 나중에 쉽게 찾을 수 있도록 이 OMA-URI 설정에 대한 고유한 이름과 설명을 입력합니다.
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderExcludeAppInReport**
   - 데이터 형식: 드롭다운 목록에서 정수(Integer)를 선택합니다.
   - 값: 개인 정보 설정을 사용하도록 설정하려면 1을 입력합니다(기본값은 0).

4. **다음을** 클릭하고 이 프로필을 대상 장치/사용자에게 할당합니다.

이 개인 정보 제어를 사용하는 경우 장치 준수 검사 또는 조건부 액세스에는 영향을 주지 않습니다. 예를 들어 악성 앱이 있는 장치는 항상 위험 수준이 "보통"입니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft Defender for Endpoint(iOS용) 개요](microsoft-defender-endpoint-android.md)
- [Microsoft Intune으로 Microsoft Defender for Endpoint(Android용) 배포](android-intune.md)
