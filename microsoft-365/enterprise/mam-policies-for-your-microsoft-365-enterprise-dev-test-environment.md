---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 장치 준수 정책
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 Enterprise 테스트 환경에 Intune 장치 준수 정책을 추가 합니다.
ms.openlocfilehash: b8c2fbe437362f72effd5ba550817f847ccbbf74
ms.sourcegitcommit: e15cf5d0d8ff3dfdc457b469992d72ac802e6434
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "33467736"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에 대 한 장치 준수 정책

이 문서의 지침을 사용 하 여 Microsoft 365 Enterprise 테스트 환경에 Intune 장치 준수 정책을 추가 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항을 사용 하 여 간단한 방식으로 MAM 정책을 구성 하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 MAM 정책을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> 자동 라이선싱 및 그룹 구성원을 테스트 하는 경우에는 AD DS (Active directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>2 단계: Windows 10 장치에 대 한 장치 준수 정책 만들기

이 단계에서는 Windows 10 장치에 대 한 장치 준수 정책을 만듭니다.
  
1. 에서[https://portal.office.com](https://portal.office.com)office 365 포털로 이동 하 여 전역 관리자 계정을 사용 하 여 office 365 테스트 랩 구독에 로그인 합니다.
    
2. 브라우저의 새 탭에서 Azure portal ()을 엽니다 [https://portal.azure.com](https://portal.azure.com).

3. 브라우저의 Azure portal 탭에 있는 탐색 창에서 **모든 서비스**를 클릭 하 고 **intune**을 입력 한 다음 **intune**을 클릭 합니다.
    
4. **Microsoft Intune** 블레이드에서 **장치 관리 아직 메시지를 사용 하도록 설정 하지 않은** 경우에는 해당 항목을 클릭 합니다. **모바일 장치 관리 기관** 블레이드에서 **Intune MDM 기관을**클릭 한 다음 **선택을**클릭 합니다. 브라우저 탭을 새로 고칩니다.
    
5. 왼쪽 탐색 창에서 **그룹**을 클릭 합니다.
    
6. **그룹-모든 그룹** 블레이드에서 **+ 새 그룹**을 클릭 합니다.
    
7. **그룹** 블레이드에서 **Office 365** 또는 **보안** 을 선택 **하**고 **이름**에 **관리 되는 Windows 10 장치 사용자** 를 입력 한 다음 **멤버 자격 유형에**서 **할당 됨** 을 선택 하 고 **만들기**를 클릭 합니다. 
    
8. **그룹** 블레이드를 닫습니다.
    
11. **그룹-모든 그룹** 블레이드를 닫습니다.
    
12. **Microsoft Intune** 블레이드에서 **빠른 작업** 목록에서 **준수 정책 만들기**를 클릭 합니다.
    
13. **준수 정책 프로필** 블레이드에서 **정책 만들기**를 클릭 합니다.
    
14. **정책 만들기** 블레이드에서 **Name (이름**)에 **Windows 10**을 입력 합니다. **플랫폼**에서 **windows 10 이상**을 선택 하 고 **windows 10 준수 정책** 블레이드에서 **확인** 을 클릭 한 다음 **만들기**를 클릭 합니다. **Windows 10** 블레이드를 닫습니다.
    
15. **준수 정책 프로필** 블레이드에서 **Windows 10** 정책 이름을 클릭 합니다.
    
16. **Windows 10** 블레이드에서 **할당**을 클릭 하 고 **포함할 그룹 선택을**클릭 합니다.
    
17. **포함할 그룹 선택** 블레이드에서 **관리 되는 Windows 10 장치 사용자** 그룹을 클릭 한 다음 **선택을**클릭 합니다.
    
18. **저장**을 클릭 하 고 **Windows 10 할당** 블레이드를 닫습니다.
    
19. **준수 정책 프로필** 블레이드를 닫습니다.
    
20. **Microsoft Intune** 블레이드에서 왼쪽 탐색 창에서 **클라이언트 앱** 을 클릭 합니다.
    
21. **클라이언트 응용 프로그램** 블레이드에서 **앱**을 클릭 하 고 **추가**를 클릭 합니다. 

22. **앱 추가** 블레이드에서 **앱 유형을**선택 하 고 **Office 365 제품군**에서 **Windows 10** 을 선택 합니다.

23. **앱 제품군 구성을**클릭 한 다음 **확인**을 클릭 합니다.

24. **앱 제품군 정보**를 클릭 하 고 제품군 **이름**에 **windows 10 용 office 앱** 을 입력 하 고 **suite 설명**에 **windows 10 용 office 앱** 을 설정한 다음 **확인**을 클릭 합니다.

25. **앱 제품군 설정을**클릭 하 고 **업데이트 채널**에서 **반기** 를 선택한 다음 **확인**을 클릭 합니다.

26. **앱 추가** 블레이드에서 **추가**를 클릭 합니다.

이제 **windows 10** 장치 준수 정책 및 **관리 되는 Windows 10 장치 사용자** 그룹의 구성원에 대해 선택한 앱을 테스트할 수 있는 장치 준수 정책이 만들어졌습니다. 그룹 유형으로 Office 365을 선택 하면 추가 리소스가 만들어집니다. 
  
## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 기능을 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
  
[Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[EMS (Enterprise Mobility + Security)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
