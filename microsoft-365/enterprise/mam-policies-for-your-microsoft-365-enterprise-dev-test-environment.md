---
title: Microsoft 365 Enterprise 테스트 환경용 MAM 정책
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 테스트 환경에 Microsoft 365 기업 Intune 모바일 응용 프로그램 관리 (MAM) 정책을 추가 합니다.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870348"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경용 MAM 정책

이 문서의 지침을 테스트 환경에 Microsoft 365 기업 Intune 모바일 응용 프로그램 관리 (MAM) 정책을 추가 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다

최소 요구 사항을 경량 방식으로 MAM 정책을 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.
  
시뮬레이션 된 엔터프라이즈에서 MAM 정책을 구성 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지시를 따릅니다.
  
> [!NOTE]
> 라이선스 하는 자동화 된 테스트 하 고 그룹 멤버 자격을 원하지 않는 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다. 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a>2단계: iOS 및 Android 장치용으로 MAM 정책 만들고 배포하기

이 단계에서는 두 개의 다른 MAM 정책을 만들고 배포할 수 있습니다. 하나는 iOS 장치용이며 하나는 Android 장치용입니다.
  
1. Office 365 포털에서 이동 ([https://portal.office.com](https://portal.office.com)) 전역 관리자 계정 사용 하 여 Office 365 평가판 구독에 로그인 합니다.
    
2. 브라우저의 새 탭에서 Azure 포털을 엽니다 [https://portal.azure.com](https://portal.azure.com)합니다.

3. 탐색 창에서 Internet Explorer에서 포털 Azure 탭에서 **모든 서비스**를 클릭 하 고 **Intune**입력 **Intune**를 클릭 한 다음 합니다.
    
4. **Microsoft Intune** 블레이드에 **장치 관리 아직 활성화 하지 않은** 메시지를 표시 하는 경우이 클릭 합니다. **모바일 장치 관리 기관** 블레이드에서 **Intune MDM 기관**클릭 한 다음 **선택**을 클릭 합니다. 브라우저 탭을 새로 고칠 합니다.
    
5. 왼쪽 탐색 창에서 **그룹**을 클릭합니다.
    
6. **그룹-모든 그룹** 블레이드에서 **+ 새 그룹을**클릭 합니다.
    
7. **그룹** 블레이드 선택에 대 한 **Office 365** **그룹 종류?**, **iOS 장치 사용자를 관리 되는** **이름**입력 **구성원 종류** **할당 됨** 을 선택 하 고 다음 **만들기**를 클릭 합니다. 
    
8. **그룹** 블레이드를 닫습니다.
    
9. **그룹-모든 그룹** 블레이드에서 **추가**클릭 합니다.
    
10. **그룹** 블레이드 선택에 대 한 **Office 365** **그룹 종류?**, **Android 관리 되는 장치 사용자** **이름**입력 **구성원 종류** **할당 됨** 을 선택 하 고 **만들기**를 클릭 합니다.
    
11. **그룹-모든 그룹** 블레이드를 닫습니다.
    
12. **Intune** 블레이드의 **빠른 작업** 목록에서 **준수 정책 만들기**를 클릭합니다.
    
13. **준수 정책 프로필** 블레이드에서 **정책 만들기**를 클릭합니다.
    
14. **정책 만들기** 블레이드에서 **이름**에 **iOS**를 입력합니다. **플랫폼**에서 **iOS**를 선택하고 **iOS 준수 정책** 블레이드에서 **확인**을 클릭한 다음 **만들기**를 클릭합니다.
    
15. **준수 정책 프로필** 블레이드에서 **정책 만들기**를 클릭합니다.
    
16. **정책 만들기** 블레이드에서 **이름**에 **Android**를 입력합니다. **플랫폼**에서 **Android**를 선택하고 **Android 준수 정책** 블레이드에서 **확인**을 클릭한 다음 **만들기**를 클릭합니다.
    
17. **준수 정책 프로필** 블레이드에서 **Android** 정책 이름을 클릭합니다.
    
18. 왼쪽 탐색 창의 **Android - 속성** 블레이드에서 **배정**을 클릭한 다음 **그룹 선택**을 클릭합니다.
    
19. **그룹 선택** 블레이드에서 **관리 Android 장치 사용자** 그룹을 클릭한 다음 **선택**을 클릭합니다.
    
20. **저장**을 클릭 하 고 **Android-배정** 블레이드를 닫습니다.
    
21. **준수 정책 프로필** 블레이드에서 **iOS** 정책 이름을 클릭합니다.
    
22. 왼쪽 탐색 창의 **iOS - 속성** 블레이드에서 **배정**을 클릭한 다음 **그룹 선택**을 클릭합니다.
    
23. **그룹 선택** 블레이드에서 **관리 iOS 장치 사용자** 그룹을 클릭한 다음 **선택**을 클릭합니다.
    
24. **저장**을 클릭 하 고 **iOS-배정** 블레이드를 닫습니다.
    
25. **준수 정책 프로필** 블레이드를 닫습니다.
    
26. **Intune** 블레이드의 왼쪽 탐색 창에서 **앱 관리**를 클릭합니다.
    
27. **모바일 앱** 블레이드에서 **앱**을 클릭합니다.
    
28. 앱 목록에서 **PowerPoint**를 클릭합니다.  
    
29. **PowerPoint 개요** 블레이드에서 **배정 > 그룹 선택 > 관리 iOS 장치 > 선택**을 클릭합니다. **유형**에서 **사용 가능**을 선택한 다음 **저장**을 클릭합니다.
    
30. 다음 응용 프로그램에 대 한 29 단계를 반복 합니다.
    
    - Android용 Outlook
    
    - iOS용 Word
    
    - IOS용 Excel
    
    - iOS용 Outlook
    
    - iOS용 iPad의 Microsoft Dynamics CRM
    
    - iOS용 iPhone의 Microsoft Dynamics CRM
    
    - Android 휴대폰용 Dynamics CRM
    
    - Android 태블릿용 Dynamics CRM
    
    - Android용 Excel
    
    - Android용 Word
    
    - iOS용 OneNote
    
31. **모바일 앱 - 앱** 블레이드를 닫습니다.
    
32. **모바일 앱** 블레이드에서 **앱 보호 정책**을 클릭합니다.
    
33. **앱 보호 정책** 블레이드에서 **정책 추가**를 클릭합니다.
    
34. **정책 추가** 블레이드에서 **iOS**를 입력한 다음 **필요한 앱 선택**을 클릭합니다.
    
35. **앱** 블레이드에서 **PowerPoint**, **iPhone의 Microsoft Dynamics CRM**, **Excel**, **iPhone의 Microsoft Dynamics CRM**, **Word**, **OneNote** 및 **Outlook**을 클릭한 다음 **선택**을 클릭합니다.
    
36. **정책 추가** 블레이드에서 **만들기**를 클릭합니다.
    
37. **앱 보호 정책** 블레이드에서 **정책 추가**를 클릭합니다.
    
38. **정책 추가** 블레이드에서 **Android**를 입력하고 **플랫폼**에서 **Android**를 선택한 다음 **필요한 앱 선택**을 클릭합니다.
    
39. **앱** 블레이드에서 **PowerPoint**, **태블릿용 Dynamics CRM**, **Excel**, **Word**, **Outlook** 및 **휴대폰용 Dynamics CRM**을 클릭한 다음 **선택**을 클릭합니다.
    
40. **정책 추가** 블레이드에서 **만들기**를 클릭합니다.
    
이제 iOS 장치용과 Android 장치용의 두 가지 MAM 정책이 있으며 선택한 앱의 설정 테스트를 실험할 준비가 되었습니다. 
  
## <a name="next-step"></a>다음 단계

테스트 환경의 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 추가 기능 및 특징을 살펴봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)입니다.
  
[Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[엔터프라이즈 이동성 + 보안 (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
