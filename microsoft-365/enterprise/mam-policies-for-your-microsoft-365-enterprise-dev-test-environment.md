---
title: 엔터프라이즈용 Microsoft 365 테스트 환경에 대한 장치 준수 정책
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용하여 엔터프라이즈용 Microsoft 365 테스트 환경에 Intune 장치 준수 정책을 추가합니다.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367098"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈용 Microsoft 365 테스트 환경에 대한 장치 준수 정책

*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*

이 문서에서는 Windows 10 장치 및 엔터프라이즈용 Microsoft 365 앱에 대한 Intune 장치 준수 정책을 엔터프라이즈용 Microsoft 365 테스트 환경에 추가하는 방법을 설명합니다.

Intune 장치 준수 정책을 추가하는 데는 다음 두 단계가 있습니다.
- [1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2단계: Windows 10 장치에 대한 장치 준수 정책 만들기](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)테스트 랩 가이드 스택으로 이동하세요.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축

최소 요구 사항을 충족하는 간단한 방식으로만 MAM 정책을 구성하려면 Lightweight base configuration의 지침을 [따르세요.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
시뮬레이트된 엔터프라이즈에서 MAM 정책을 구성하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> 자동화된 라이선스 및 그룹 멤버 자격을 테스트하는 데는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다. 여기에서는 자동화된 라이선스 및 그룹 멤버십을 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 옵션으로 제공됩니다.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>2단계: Windows 10 장치에 대한 장치 준수 정책 만들기

이 단계에서는 Windows 10 장치에 대한 장치 준수 정책을 생성합니다. 이 단계에서는 Microsoft Intune 및 [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) 관리 센터를 사용하여 그룹을 추가하고 준수 정책을 생성합니다.

1. [Microsoft 365](https://admin.microsoft.com)관리 센터로 이동한 후 전역 관리자 계정으로 Microsoft 365 테스트 랩 구독에 로그인합니다. **끝점 관리자 관리 센터를** 선택합니다. 끝점 [관리자 관리 센터가](https://go.microsoft.com/fwlink/?linkid=2109431) 열립니다.

    장치 관리를 사용하도록  설정하지 않은 메시지와 유사한 메시지가 표시되면 MDM 기관으로 Intune을 선택합니다. 특정 단계는 모바일 장치 관리 [기관 설정을 참조하세요.](/mem/intune/fundamentals/mdm-authority-set)

    끝점 관리자 관리 센터는 장치 관리 및 앱 관리에 중점을 니다. 이 관리 센터를 둘러보는 방법에 대한 자세한 내용은 [자습서: Microsoft Endpoint Manager의 Intune Walkthrough Intune을 참조하세요.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)

2. 그룹에서 할당된 구성원 유형으로 관리되는 **Windows 10** 장치 사용자라는 새 **Microsoft 365** 또는 보안 **그룹을 추가합니다.**   다음 단계에서는 이 그룹에 규정 준수 정책을 할당합니다. 

    특정 단계 및 **Microsoft 365** 또는  보안 그룹에 대한 자세한 내용은 사용자 및 장치를 구성할 그룹 [추가를 참조하세요.](/mem/intune/fundamentals/groups-add)

3. **디바이스에서** Windows 10 준수 정책을 생성합니다. 이 정책을 만든 **관리되는 Windows 10** 장치 사용자 그룹에 할당합니다.

    정책에서 간단한 암호를 차단하고, 방화벽을 요구하고, Microsoft Defender 맬웨어 방지 서비스를 실행해야 하는 등 다양한 방법을 사용할 수 있습니다. 준수 정책에는 일반적으로 기본 설정 또는 모든 장치에 필요한 최소 설정이 포함됩니다.

    특정 단계 및 구성할 수 있는 사용 가능한 준수 설정에 대한 자세한 내용은 준수 정책을 사용하여 관리하는 장치에 대한 규칙을 [설정하세요.](/mem/intune/protect/device-compliance-get-started)

완료되면 관리되는 **Windows 10** 장치 사용자 그룹에서 구성원을 테스트하기 위한 장치 준수 정책이 있습니다.
  
## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [모바일](m365-enterprise-test-lab-guides.md#mobile-device-management) 장치 관리 기능을 살펴보아야 합니다.

## <a name="see-also"></a>참고 항목

[엔터프라이즈용 Microsoft 365 테스트 랩 가이드.](m365-enterprise-test-lab-guides.md)
  
[엔터프라이즈용 Microsoft 365 테스트 환경에 iOS 및 Android 장치 등록](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[Enterprise Mobility + Security(EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
