---
title: iOS 기능에 대한 끝점용 Microsoft Defender 구성
description: iOS 기능에 끝점용 Microsoft Defender를 배포하는 방법을 설명
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, ios, 구성, 기능, ios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d32d40ac8ce086caedd53e0a69aac2a3025dc702
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842257"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>iOS 기능에 대한 끝점용 Microsoft Defender 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> iOS의 끝점용 Defender는 VPN을 사용하여 웹 보호 기능을 제공합니다. 이는 일반 VPN이 아니며 장치 외부에서 트래픽을 취하지 않는 로컬/자체 루프 VPN입니다.

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>iOS의 끝점용 Defender를 통해 조건부 액세스  
iOS의 끝점용 Microsoft Defender 및 Microsoft Intune Azure Active Directory 장치 위험 점수를 기반으로 장치 준수 및 조건부 액세스 정책을 시행할 수 있습니다. Endpoint용 Defender는 Intune을 통해 이 기능을 활용하기 위해 배포할 수 있는 MTD(Mobile Threat Defense) 솔루션입니다.

iOS에서 끝점용 Defender를 통해 조건부 액세스를 설정하는 방법에 대한 자세한 내용은 Endpoint 및 [Intune용 Defender를 참조하세요.](/mem/intune/protect/advanced-threat-protection)

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Endpoint용 Microsoft Defender의 탈옥 감지
끝점용 Microsoft Defender에는 무단으로 보호된 관리되지 않는 장치를 검색하는 기능이 있습니다. 장치가 무단으로 보호된 것으로 감지되면 보안 센터에 높은 **위험** 경고가 보고되고, 조건부 액세스가 장치 위험 점수를 기반으로 설정되어 있는 경우 장치가 회사 데이터에 액세스하지 못하게 차단됩니다.

## <a name="web-protection-and-vpn"></a>웹 보호 및 VPN

기본적으로 iOS의 Endpoint용 Defender에는 웹 보호 기능이 포함 및 사용됩니다. [웹 보호는](web-protection-overview.md) 웹 위협으로부터 장치를 보호하고 피싱 공격으로부터 사용자를 보호하는 데 도움이 됩니다. iOS의 끝점용 Defender는 VPN을 사용하여 이 보호를 제공합니다. 이는 로컬 VPN으로, 기존 VPN과 달리 네트워크 트래픽은 장치 외부로 전송되지 않습니다.

기본적으로 사용하도록 설정되어 있는 동안 VPN을 사용하지 않도록 설정해야 하는 경우도 있습니다. 예를 들어 VPN을 구성할 때 작동하지 않는 일부 앱을 실행하려는 경우를 예로 들 수 있습니다. 이러한 경우 아래 단계에 따라 디바이스의 앱에서 VPN을 사용하지 않도록 선택할 수 있습니다.

1. iOS 장치에서 설정 열고 **일반을 클릭하거나** **탭한** 다음 **VPN 을 클릭합니다.**
1. 끝점용 Microsoft Defender의 "i" 단추를 클릭하거나 탭합니다.
1. VPN을 사용하지 **커넥트 On Demand를** 해제합니다.

    > [!div class="mx-imgBorder"]
    > ![VPN 구성 필요 시 연결](images/ios-vpn-config.png)

> [!NOTE]
> VPN을 사용하지 않도록 설정하면 웹 보호를 사용할 수 없습니다. 웹 보호를 다시 사용하도록 설정하려면 장치에서 끝점용 Microsoft Defender 앱을 열고 VPN 시작 을 클릭하거나 **탭합니다.**

## <a name="co-existence-of-multiple-vpn-profiles"></a>여러 VPN 프로필의 동시 사용

Apple iOS는 동시에 활성화하기 위해 여러 장치 전체의 VPN을 지원하지 않습니다. 디바이스에 여러 VPN 프로필이 존재할 수 있는 반면 한 번의 VPN만 활성화할 수 있습니다.


## <a name="configure-compliance-policy-against-jailbroken-devices"></a>무단으로 보호된 장치에 대한 규정 준수 정책 구성

무단으로 보호된 iOS 장치에서 회사 데이터에 액세스하지 못하도록 보호하기 위해 Intune에서 다음 규정 준수 정책을 설정하는 것이 좋습니다.

> [!NOTE]
> 탈옥 검색은 iOS의 끝점에 대해 Microsoft Defender에서 제공하는 기능입니다. 그러나 이 정책을 탈옥 시나리오에 대한 추가 방어 계층으로 설정하는 것이 좋습니다.

다음 단계에 따라 무단으로 보호된 장치에 대한 규정 준수 정책을 만들 수 있습니다.

1. Microsoft Endpoint Manager [관리 센터에서](https://go.microsoft.com/fwlink/?linkid=2109431)장치 **준수** 정책 정책  ->    ->  **만들기로 이동하세요.** 플랫폼으로 "iOS/iPadOS"를 선택하고 만들기를 **클릭합니다.**

    > [!div class="mx-imgBorder"]
    > ![정책 만들기](images/ios-jb-policy.png)

2. 정책의 이름(예: "탈옥에 대한 규정 준수 정책")을 지정합니다.
3. 준수 설정 페이지에서 장치 상태 **섹션을** 클릭하여 확장하고 **무단으로** 차단된 장치 차단 **필드를** 클릭합니다.

    > [!div class="mx-imgBorder"]
    > ![정책 설정](images/ios-jb-settings.png)

4. 준수하지 *않는* 작업에 대한 작업 섹션에서 요구 사항에 따라 작업을 선택하고 다음 을 **선택합니다.**

    > [!div class="mx-imgBorder"]
    > ![정책 작업](images/ios-jb-actions.png)

5. 할당 *섹션에서* 이 정책에 포함할 사용자 그룹을 선택하고 다음 을 **선택합니다.**
6. **검토+만들기 섹션에서** 입력한 정보가 모두 올바른지 확인한 다음 만들기를 **선택합니다.**

## <a name="configure-custom-indicators"></a>사용자 지정 표시기 구성

iOS의 끝점용 Defender를 사용하면 관리자가 iOS 장치에서도 사용자 지정 표시기를 구성할 수 있습니다. 사용자 지정 표시기를 구성하는 방법에 대한 자세한 내용은 [지표 관리를 참조하세요.](/microsoft-365/security/defender-endpoint/manage-indicators)

> [!NOTE]
> iOS의 끝점용 Defender는 IP 주소 및 URL/도메인에 대한 사용자 지정 표시기만 만들 수 있습니다.

## <a name="report-unsafe-site"></a>안전하지 않은 사이트 보고

피싱 웹 사이트는 개인 또는 재무 정보를 얻기 위해 신뢰할 수 있는 웹 사이트를 가장합니다. 피싱 [](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 사이트일 수 있는 웹 사이트를 보고하려는 경우 네트워크 보호에 대한 피드백 제공 페이지를 방문하세요.

