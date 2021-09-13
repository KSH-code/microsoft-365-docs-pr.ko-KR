---
title: iOS 기능에 끝점용 Microsoft Defender 배포
description: 미인인 iOS 디바이스에서 끝점용 Microsoft Defender를 배포하는 방법에 대해 설명
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, ios, 구성, 기능, ios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a5080526fe224d6a8e0a524a1973c6c47dc419bc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212205"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-unenrolled-ios-devices"></a>미인인 iOS 장치에 끝점용 Microsoft Defender 배포

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> iOS의 끝점용 Defender는 VPN을 사용하여 웹 보호 기능을 제공합니다. 이는 일반 VPN이 아니며 장치 외부에서 트래픽을 취하지 않는 로컬/자체 루프 VPN입니다.

## <a name="configure-microsoft-defender-for-endpoint-risk-signals-in-app-protection-policy-mam"></a>MAM(앱 보호 정책)에서 끝점 위험 신호에 대한 Microsoft Defender 구성

iOS/iPadOS에서 MAM(앱 보호 정책)에 사용할 위협 신호를 보내도록 끝점용 Microsoft Defender를 구성할 수 있습니다. 이 기능을 사용하면 끝점용 Microsoft Defender를 사용하여 수집되지 않은 장치에서 회사 데이터에 대한 액세스를 보호할 수 있습니다.

끝점용 Microsoft Defender를 통해 앱 보호 정책을 설정하는 단계는 다음과 같습니다.

1. 테넌트에서 끝점용 Microsoft Defender로의 Microsoft Endpoint Manager 연결을 설정합니다. [Microsoft 끝점](https://go.microsoft.com/fwlink/?linkid=2109431)관리자 관리 센터에서 테넌트 관리 커넥터 및 끝점용 Microsoft Defender(플랫폼 간) 또는 끝점용 Microsoft Defender 보안  \>  \>  Microsoft **Defender(설치** 아래)로 이동한 다음 \>  **iOS용** 앱 보호 정책 설정 에서 토글을 켜야 합니다.
1. **저장** 을 선택합니다. 이제 **연결** 상태가 사용으로 설정되어 **있습니다.**
1. 앱 보호 정책 만들기: 끝점 커넥터에 대한 Microsoft Defender  설정이 완료되면 앱 앱 보호 정책(정책 아래)으로 이동하여 새 정책을 만들거나 기존 정책을 \>  업데이트합니다.
1. 조직에서 정책에 필요한 플랫폼, **앱, 데이터** 보호, 액세스 요구 사항 설정을 선택합니다.
1. 조건부 **시작** \> **장치 조건에서** 허용되는 장치 위협 수준 **최대 설정을 찾을 수 있습니다.** 이는 Low, Medium, High 또는 Secured로 구성해야 합니다. 사용할 수 있는 작업은  액세스 차단 또는 데이터 **지우기 입니다.** 이 설정이 적용하기 전에 커넥터를 설정해야 하는 정보 대화 상자가 표시될 수 있습니다. 커넥터가 이미 설정되어 있는 경우 이 대화 상자를 무시할 수 있습니다.
1. 할당을 완료하고 정책을 저장합니다.

MAM 또는 앱 보호 정책에 대한 자세한 내용은 iOS 앱 보호 정책 설정을 [참조하세요.](/mem/intune/apps/app-protection-policy-settings-ios)

## <a name="deploy-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>MAM 또는 미가용 디바이스에 대한 끝점용 Microsoft Defender 배포

iOS의 끝점용 Microsoft Defender는 앱 보호 정책 시나리오를 사용할 수 있도록 지원하며 Apple 앱 스토어에서 사용할 수 있습니다.

앱 보호 정책이 끝점용 Microsoft Defender의 장치 위험 신호를 포함하도록 앱에 대해 구성된 경우 사용자는 이러한 앱을 사용할 때 끝점용 Microsoft Defender를 설치하도록 리디렉션됩니다. 또는 사용자는 Apple 앱 스토어에서 직접 최신 버전의 앱을 설치할 수도 있습니다.
