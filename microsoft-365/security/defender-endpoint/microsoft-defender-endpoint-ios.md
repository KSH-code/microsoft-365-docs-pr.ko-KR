---
title: Microsoft Defender for Endpoint(iOS용)
ms.reviewer: ''
description: iOS에서 끝점용 Microsoft Defender를 설치하고 사용하는 방법을 설명
keywords: microsoft, defender, Endpoint용 Microsoft Defender, ios, 개요, 설치, 배포, 제거, intune
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cdf32e6daa26eb369d66a4b6c0ff3991093c67f9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935272"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender for Endpoint(iOS용)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**iOS의 끝점용 Microsoft Defender는** 웹 사이트, 전자 메일 및 앱의 피싱 및 안전하지 않은 네트워크 연결로부터 보호합니다. 모든 경고는 Microsoft Defender 보안 센터의 단일 창을 통해 사용할 수 있습니다. 이 포털은 보안 팀에서 다른 플랫폼과 함께 iOS 장치에 대한 위협을 중앙 집중식으로 볼 수 있습니다.

> [!CAUTION]
> iOS에서 Endpoint용 Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 시스템 오류가 발생할 수 있습니다.

## <a name="pre-requisites"></a>필수 구성 요소

**최종 사용자용**

- 앱의 최종 사용자에게 할당된 끝점용 Microsoft Defender 라이선스입니다. 끝점 [라이선스 요구 사항에 대한 Microsoft Defender를 참조하세요.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

- Intune 장치 [](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) 준수 정책을 적용하기 위해 Intune 회사 포털 앱을 통해 장치가 등록됩니다. 이렇게 하려면 최종 사용자에게 Microsoft Intune 라이선스가 할당됩니다.
    - Intune 회사 포털 앱은 Apple 앱 스토어에서 [다운로드할 수 있습니다.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Apple은 사용자가 앱 스토어에서 다른 앱을 다운로드하도록 리디렉션을 허용하지 않습니다. 따라서 이 단계는 끝점용 Microsoft Defender 앱에 온보딩하기 전에 사용자가 수행해야 합니다.

- 라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

**관리자용**

- Microsoft Defender 보안 센터 포털에 액세스합니다.

    > [!NOTE]
    > Microsoft Intune은 iOS에서 끝점용 Microsoft Defender를 배포하는 데 지원되는 유일한 MDM(모바일 장치 관리) 솔루션입니다. 현재 등록된 장치만 Intune에서 iOS 관련 장치 준수 정책에 끝점용 Defender를 적용하는 데 지원됩니다.

- Microsoft [Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)관리 센터에 액세스하여 조직의 등록된 사용자 그룹에 앱을 배포합니다.

**시스템 요구 사항**

- iOS 11.0 이상을 실행하는 iOS 장치. iPad 장치는 버전 1.1.15010101 이상에서 공식적으로 지원됩니다.

- [장치가 Intune 회사 포털 앱에 등록됩니다.](https://apps.apple.com/us/app/intune-company-portal/id719171358)

> [!NOTE]
> **iOS의 Microsoft Defender ATP(Microsoft Defender for Endpoint)는 [이제 Apple App Store에서 사용할 수 있습니다.](https://aka.ms/mdatpiosappstore)**

## <a name="installation-instructions"></a>설치 지침

iOS에서 끝점용 Microsoft Defender 배포는 Microsoft Intune(MDM)을 통해 배포할 수 있으며 감독되는 디바이스와 관리되지 않는 디바이스가 모두 지원됩니다.
자세한 내용은 [iOS에서 끝점용 Microsoft Defender 배포를 참조하세요.](ios-install.md)

## <a name="resources"></a>리소스

- iOS 또는 블로그의 [끝점용 Microsoft Defender의 새로운](ios-whatsnew.md) 소식을 방문하여 예정된 릴리스에 대한 정보를 계속 [확인하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)

- 앱 내 피드백 시스템 또는 [SecOps](https://securitycenter.microsoft.com) 포털을 통해 피드백 제공

## <a name="next-steps"></a>다음 단계

- [iOS에서 끝점용 Microsoft Defender 배포](ios-install.md)
- [iOS 기능에 대한 끝점용 Microsoft Defender 구성](ios-configure-features.md)
