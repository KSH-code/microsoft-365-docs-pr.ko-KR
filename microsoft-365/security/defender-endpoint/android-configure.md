---
title: Microsoft Defender for Endpoint(Android용) 기능 구성
description: Android에서 끝점용 Microsoft Defender를 구성하는 방법을 설명
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mde, android, 구성
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: afff05ac0e18ac41b1e2ba70b59ed4dfd0c6a22a
ms.sourcegitcommit: e685fafd6dde4901c378685b423883faed7b4fe7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2021
ms.locfileid: "59460319"
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

## <a name="configure-privacy-for-malware-threat-report"></a>맬웨어 위협 보고서에 대한 개인 정보 구성

> [!NOTE]
> Android의 Endpoint용 Defender에 대한 개인 정보 보호 컨트롤은 현재 미리 보기에 있으며 상업적으로 출시되기 전에 상당수 수정될 수 있습니다.

맬웨어 위협 보고서에 대한 개인 정보 제어를 사용하여 맬웨어 위협 보고서에서 앱 세부 정보(이름 및 패키지 정보)의 컬렉션을 사용하지 않도록 설정할 수 있습니다. 이렇게 하면 조직에서 악의적인 앱이 감지될 때 앱 이름을 수집할지 여부를 선택할 수 있습니다. *이 기능은 현재 Android 장치 관리자 모드로 등록된 **디바이스에서만 사용할 수** 있습니다.*

다음 단계에 따라 대상 사용자에 대해 사용하도록 설정할 수 있습니다.

1. Microsoft Endpoint Manager [관리](https://go.microsoft.com/fwlink/?linkid=2109431) 센터에서 장치 **구성** 프로필 프로필 만들기로 이동하여 다음 설정을  >    >   입력합니다.

   - **플랫폼:** Android 장치 관리자 선택
   - **프로필**: "사용자 지정"을 선택하고 만들기를 클릭합니다.

2. 기본 섹션에서 프로필의 이름과 설명을 지정합니다.
3. 구성 설정에서 **OMA-URI 설정 추가를** 선택합니다.

   - **이름:** 나중에 쉽게 찾을 수 있도록 이 OMA-URI 설정에 대한 고유한 이름과 설명을 입력합니다.
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderExcludeAppInReport**
   - 데이터 형식: 드롭다운 목록에서 정수(Integer)를 선택합니다.
   - 값: 개인 정보 설정을 사용하도록 설정하려면 1을 입력합니다(기본값은 0).

4. **다음을** 클릭하고 이 프로필을 대상 장치/사용자에게 할당합니다.

위의 개인 정보 보호 컨트롤을 사용하도록 설정하면 장치 준수 검사 또는 조건부 액세스에 영향을 주지 않습니다. 예를 들어 악의적인 앱이 있는 디바이스는 항상 위험 수준이 "보통"입니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft Defender for Endpoint(iOS용) 개요](microsoft-defender-endpoint-android.md)
- [Microsoft Intune으로 Microsoft Defender for Endpoint(Android용) 배포](android-intune.md)
