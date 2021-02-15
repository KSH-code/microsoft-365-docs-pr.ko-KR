---
title: 엔터프라이즈용 Microsoft 365 테스트 환경에 iOS/iPadOS 및 Android 장치 등록
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 이 테스트 랩 가이드를 사용하여 Microsoft 365 테스트 환경에 장치를 등록하고 원격으로 관리합니다.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367086"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈용 Microsoft 365 테스트 환경에 iOS 및 Android 장치 등록

*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*

이 문서에서는 엔터프라이즈용 Microsoft 365 테스트 환경에서 iOS/iPadOS 및 Android 장치에 대한 기본 모바일 장치 관리 기능을 등록하고 테스트하는 방법을 설명합니다.

테스트 환경에 iOS/iPadOS 및 Android 장치를 등록하는 데는 다음 세 단계가 있습니다.
- [1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2단계: iOS/iPadOS 및 Android 장치 등록](#phase-2-enroll-your-ios-and-android-devices)
- [3단계: 원격으로 iOS/iPadOS 및 Android 장치 관리](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)테스트 랩 가이드 스택으로 이동하세요.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축

최소 요구 사항과 경량 방식으로 iOS/iPadOS 및 Android 장치를 등록하려는 경우 Lightweight 기본 구성의 지침을 [따릅니다.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
시뮬레이트된 엔터프라이즈에 iOS/iPadOS 및 Android 장치를 등록하려는 경우 통과 인증의 지침을 [따릅니다.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> 자동화된 라이선스 및 그룹 멤버 자격을 테스트하는 데는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다. 여기에서는 자동화된 라이선스 및 그룹 멤버십을 테스트할 수 있는 옵션으로 제공되고, 일반적인 조직을 나타내는 환경에서 실험해 볼 수 있습니다.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>2단계: iOS 및 Android 장치 등록

장치를 관리하기 위해 MDM(모바일 장치 관리) 솔루션을 고려하는 경우 Microsoft Intune을 사용할 수 있습니다. Intune을 포함하여 MDM 공급자와 함께 작업하는 경우 장치는 "등록"됩니다. 등록하면 사용자가 구성한 기능과 설정이 수신됩니다. 

Intune에는 몇 가지 방법으로 iOS/iPadOS 및 Android 장치를 등록할 수 있습니다. 조직에 가장 적합한 등록 옵션을 선택할 수 있습니다. 자세한 내용과 지침은 다음 문서를 참조하세요.

- [배포 가이드: Microsoft Intune에서 iOS 및 iPadOS 장치 등록](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [배포 가이드: Microsoft Intune에서 Android 장치 등록](/mem/intune/fundamentals/deployment-guide-enrollment-android)

장치 관리를 위해 Intune을 사용할 준비가 됐고 몇 가지 지침을 원하는 경우 다음 정보가 도움이 될 수 있습니다.

- [장치 관리 개요](/mem/intune/fundamentals/what-is-device-management)
- [자습서: Microsoft Endpoint Manager의 Intune Walkthrough Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [배포 가이드: Microsoft Intune 설치 또는 이동](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>3단계: 원격으로 iOS 및 Android 장치 관리

Microsoft Intune은 원격 잠금 및 암호 재설정 기능을 제공 합니다. 누군가가 장치를 분실한 경우 원격으로 디바이스를 잠글 수 있습니다. 누군가가 암호를 잊어버렸다면 원격으로 다시 설정할 수 있습니다.

- iOS/iPadOS 또는 Android 장치를 원격으로 잠그기 위해 Intune을 사용하여 원격으로 디바이스를 [잠그십시오.](/mem/intune/remote-actions/device-remote-lock)
- 원격으로 암호를 다시 설정하려면 Intune에서 장치 암호 재설정 또는 [제거를 참조하세요.](/mem/intune/remote-actions/device-passcode-reset)

원격으로 실행할 수 있는 추가 작업에 대한 자세한 내용은 사용 가능한 장치 [작업을 참조하세요.](/mem/intune/remote-actions/device-management#available-device-actions)
    
## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [모바일](m365-enterprise-test-lab-guides.md#mobile-device-management) 장치 관리 기능을 살펴보아야 합니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
  
[엔터프라이즈용 Microsoft 365 테스트 환경에 대한 장치 준수 정책](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)
