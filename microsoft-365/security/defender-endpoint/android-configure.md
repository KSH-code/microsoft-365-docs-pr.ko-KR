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
ms.openlocfilehash: 441e7a598e0487759dc5e48dab3e74a7b3b1ead6
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187571"
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

## <a name="related-topics"></a>관련 항목

- [Microsoft Defender for Endpoint(iOS용) 개요](microsoft-defender-endpoint-android.md)
- [Microsoft Intune으로 Microsoft Defender for Endpoint(Android용) 배포](android-intune.md)
