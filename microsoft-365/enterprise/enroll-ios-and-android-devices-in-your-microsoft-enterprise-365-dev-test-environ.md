---
title: Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 이 테스트 랩 가이드를 Microsoft 365 테스트 환경에서 장치를 등록 하 고 원격으로 관리 하기를 사용 합니다.
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869856"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록

이 문서에서 제공 하는 지침을 따르면를 등록 하 고 Microsoft 365 기업 테스트 환경에서 iOS 및 Android 장치에 대 한 기본 모바일 장치 관리 기능을 테스트 하는 작업을 할 수 있습니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다

최소 요구 사항을 경량 방식으로 iOS 및 Android 장치를 등록 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.
  
IOS 및 시뮬레이션 된 엔터프라이즈에서 Android 장치 등록 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.
  
> [!NOTE]
> 라이선스 하는 자동화 된 테스트 하 고 그룹 멤버 자격을 원하지 않는 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>2 단계: iOS 및 Android 장치 등록

먼저,의 지침을 사용 하 여 [설치 회사 포털 응용 프로그램에 로그인 하 고](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) 테스트 환경에 대 한 Microsoft Intune 회사 포털 응용 프로그램을 사용자 지정할 수 있습니다.

다음으로 iOS 장치를 등록 하려면 [회사 리소스에 대 한 액세스를 설정](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 하는의 지침을 따르십시오.

다음으로, Android 장치와 등록 [등록 Intune에서 Android 장치에서](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) 에서 지침을 따르십시오.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>3 단계: iOS 및 Android 장치를 원격으로 관리

Microsoft Intune 원격 잠금 및 암호를 모두 재설정 기능을 제공 합니다. 다른 사용자가 장치를 잃을 하는 경우 원격으로 장치를 잠글 수 있습니다. 다른 사용자가 자신의 암호를 잊어버린를 원격으로 재설정할 수 있습니다.
  
IOS 또는 Android 장치를 원격으로 잠그려면:

1. Azure 포털에 로그인 [https://portal.azure.com](https://portal.azure.com) 전역 관리자 계정의 자격 증명을 사용 합니다.
2. **모든 서비스**를 클릭 하 고 **Intune**입력 다음 **Intune**를 클릭 합니다.
3. 클릭 **장치 > 모든 장치**합니다.
4. 장치 목록에서 iOS 또는 Android 장치를 클릭 하 고 **원격 잠금** 동작을 클릭 합니다.

    
원격으로 암호를 초기화하려면:

1. 필요한 경우에서 Azure 포털에 로그인 [https://portal.azure.com](https://portal.azure.com) 전역 관리자 계정의 자격 증명을 사용 합니다.
2. **모든 서비스**를 클릭 하 고 **Intune**입력 다음 **Intune**를 클릭 합니다.
3. 클릭 **장치 > 모든 장치**합니다.
4. 관리 장치 목록에서는 iOS 또는 Android 장치를 클릭 한 **선택... 더 많은**합니다. 다음 **암호를 제거** 장치 원격 작업을 선택 합니다.

추가 실험 [사용 가능한 장치에 작업](https://docs.microsoft.com/intune/device-management#available-device-actions)을 참조 하십시오.

    
## <a name="next-step"></a>다음 단계

테스트 환경의 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 추가 기능 및 특징을 살펴봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
  
[Microsoft 365 Enterprise 테스트 환경용 MAM 정책](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[엔터프라이즈 이동성 + 보안 (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
