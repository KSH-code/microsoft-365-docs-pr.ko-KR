---
title: Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 테스트 환경에서 장치를 등록 하 고 원격으로 관리 합니다.
ms.openlocfilehash: b98e184d3216a779fc495cf65b73d3a2b212e257
ms.sourcegitcommit: ea48c86c727dcd9d4b3b970b14a4260337f158f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38694075"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록

*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*

이 문서에 나와 있는 지침을 수행 하 여 Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치에 대 한 기본 모바일 장치 관리 기능을 등록 하 고 테스트할 수 있습니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> [여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항에 따라 간단한 방식으로 iOS 및 Android 장치를 등록 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 iOS 및 Android 장치를 등록 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> 자동 라이선싱 및 그룹 구성원을 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>2 단계: iOS 및 Android 장치 등록

먼저 Install (설치)의 지침을 사용 하 여 테스트 환경에 대 한 Microsoft Intune 회사 포털 앱을 사용자 지정 하 [고 회사 포털 앱에 로그인](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) 합니다.

그런 다음 [회사 리소스에 대 한 액세스 설정](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 의 지침을 사용 하 여 iOS 장치를 등록 합니다.

다음으로, [Intune에서 android 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) 의 지침을 사용 하 여 android 장치를 등록 합니다.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>3 단계: 원격으로 iOS 및 Android 장치 관리

Microsoft Intune에서는 원격 잠금 및 암호 초기화 기능을 모두 제공합니다. 장치를 분실한 경우 원격으로 장치를 잠글 수 있습니다. 다른 사용자가 암호를 잊어버린 경우 원격으로 다시 설정할 수 있습니다.
  
원격으로 iOS 또는 Android 장치를 잠그려면:

1. 전역 관리자 계정의 자격 증명을 [https://portal.azure.com](https://portal.azure.com) 사용 하 여 Azure portal에 로그인 합니다.
2. **모든 서비스**를 클릭 하 고 **intune**을 입력 한 다음 **intune**을 클릭 합니다.
3. **모든 장치 > 장치**를 클릭 합니다.
4. 장치 목록에서 iOS 또는 Android 장치를 클릭 한 다음 **원격 잠금** 작업을 클릭 합니다.

    
원격으로 암호를 초기화하려면:

1. 필요한 경우 전역 관리자 계정의 자격 증명을 [https://portal.azure.com](https://portal.azure.com) 사용 하 여 Azure portal에 로그인 합니다.
2. **모든 서비스**를 클릭 하 고 **intune**을 입력 한 다음 **intune**을 클릭 합니다.
3. **모든 장치 > 장치**를 클릭 합니다.
4. 관리 하는 장치 목록에서 iOS 또는 Android 장치를 클릭 하 고 ...를 선택 **합니다. 자세히** 그런 다음 암호 장치 원격 작업 **제거** 를 선택 합니다.

자세한 내용은 [사용 가능한 장치 작업](https://docs.microsoft.com/intune/device-management#available-device-actions)을 참조 하십시오.

    
## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 기능을 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
  
[Microsoft 365 Enterprise 테스트 환경에 대 한 장치 준수 정책](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

