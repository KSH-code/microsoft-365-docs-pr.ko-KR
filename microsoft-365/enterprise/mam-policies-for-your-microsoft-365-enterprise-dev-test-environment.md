---
title: 엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 장치 준수 정책
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
description: 이 테스트 랩 가이드를 사용 하 여 엔터프라이즈 테스트 환경용 Microsoft 365에 Intune 장치 준수 정책을 추가 합니다.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367098"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 장치 준수 정책

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*

이 문서에서는 Windows 10 장치에 대 한 Intune 장치 준수 정책을 추가 하는 방법과 엔터프라이즈 용 Microsoft 365 앱을 Microsoft 365 for 엔터프라이즈 테스트 환경에 대해 설명 합니다.

Intune 장치 준수 정책 추가에는 두 단계가 포함 됩니다.
- [1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2 단계: Windows 10 장치에 대 한 장치 준수 정책 만들기](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축

최소 요구 사항과 함께 간단한 방식 으로만 MAM 정책을 구성 하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 MAM 정책을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> 자동 라이선싱 및 그룹 구성원을 테스트 하려면 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에서 옵션으로 제공 됩니다.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>2 단계: Windows 10 장치에 대 한 장치 준수 정책 만들기

이 단계에서는 Windows 10 장치에 대 한 장치 준수 정책을 만듭니다. 이 단계에서는 Microsoft Intune 및 [Microsoft Endpoint Manager 관리 센터](https://go.microsoft.com/fwlink/?linkid=2109431) 를 사용 하 여 그룹을 추가 하 고 준수 정책을 만듭니다.

1. [Microsoft 365 관리 센터로](https://admin.microsoft.com)이동 하 여 전역 관리자 계정으로 microsoft 365 테스트 랩 구독에 로그인 합니다. **Endpoint Manager** 관리 센터를 선택 합니다. [끝점 관리자 관리 센터](https://go.microsoft.com/fwlink/?linkid=2109431) 가 열립니다.

    **아직 장치 관리를 사용 하도록 설정 하지 않은** 메시지를 표시 한 경우 MDM 기관으로 Intune을 선택 합니다. 특정 단계에 대해서 [는 모바일 장치 관리 기관 설정을](/mem/intune/fundamentals/mdm-authority-set)참조 하십시오.

    Endpoint Manager 관리 센터에서는 장치 관리 및 앱 관리에 대해 중점적으로 설명 합니다. 이 관리 센터에 대 한 자세한 내용은 [Tutorial: 연습용 Intune For Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)를 참조 하십시오.

2. **그룹** 에서 **할당** 된 멤버 자격 유형을 사용 하 여 **관리 되는 Windows 10 장치 사용자** 라는 새 **Microsoft 365** 또는 **보안** 그룹을 추가 합니다. 다음 단계에서는 준수 정책을이 그룹에 할당 합니다. 

    특정 단계와 **Microsoft 365** 또는 **보안** 그룹에 대 한 자세한 내용은 [Add groups to users and devices](/mem/intune/fundamentals/groups-add)를 참조 하십시오.

3. **장치** 에서 Windows 10 준수 정책을 만듭니다. 이 정책을 만든 **관리 되는 Windows 10 장치 사용자** 그룹에 할당 합니다.

    정책에서는 단순 암호를 차단 하 고, 방화벽을 요구 하며, Microsoft Defender 맬웨어 방지 서비스를 실행 해야 할 수 있습니다. 규정 준수 정책에는 일반적으로 기본 설정 또는 모든 장치에 포함 되는 최소 운영이 포함 됩니다.

    특정 단계 및 구성할 수 있는 사용 가능한 준수 설정에 대 한 자세한 내용은 [준수 정책을 사용 하 여 관리 하는 장치에 대 한 규칙 설정](/mem/intune/protect/device-compliance-get-started)를 참조 하세요.

완료 되 면 **관리 되는 Windows 10 장치 사용자** 그룹의 구성원을 테스트 하기 위한 장치 준수 정책이 있습니다.
  
## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 기능을 알아봅니다.

## <a name="see-also"></a>참고 항목

[엔터프라이즈 테스트 랩 가이드에 대 한 Microsoft 365](m365-enterprise-test-lab-guides.md)
  
[Microsoft 365에서 엔터프라이즈 테스트 환경용 iOS 및 Android 장치 등록](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[Enterprise Mobility + Security(EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
