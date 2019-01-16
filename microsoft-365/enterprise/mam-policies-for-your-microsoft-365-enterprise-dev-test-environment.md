---
title: Microsoft 365 기업에 대 한 규정 준수 정책 장치 테스트 환경
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 기업에 Intune 장치 규정 준수 정책 테스트 환경에 추가 합니다.
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870348"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 기업에 대 한 규정 준수 정책 장치 테스트 환경

이 문서의 지침을과 함께 Microsoft 365 Enterprise 테스트 환경에 Intune 장치 규정 준수 정책을 추가 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다

최소 요구 사항을 경량 방식으로 MAM 정책을 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.
  
시뮬레이션 된 엔터프라이즈에서 MAM 정책을 구성 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지시를 따릅니다.
  
> [!NOTE]
> 라이선스 하는 자동화 된 테스트 하 고 그룹 멤버 자격을 원하지 않는 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>2 단계: Windows 10 장치에 대 한 장치 규정 준수 정책 만들기

이 단계에서는 Windows 10 장치에 대 한 장치 규정 준수 정책을 만듭니다.
  
1. Office 포털으로 이동 ([https://office.com](https://office.com)) 전역 관리자 계정 사용 하 여 Office 365 평가판 구독에 로그인 합니다.
    
2. 브라우저의 새 탭에서 Azure 포털을 엽니다 [https://portal.azure.com](https://portal.azure.com)합니다.

3. 탐색 창에서 브라우저에서 Azure 포털 탭에서 **모든 서비스**를 클릭 하 고 **Intune**입력 **Intune**를 클릭 한 다음 합니다.
    
4. **Microsoft Intune** 블레이드에 **장치 관리 아직 활성화 하지 않은** 메시지를 표시 하는 경우이 클릭 합니다. **모바일 장치 관리 기관** 블레이드에서 **Intune MDM 기관**클릭 한 다음 **선택**을 클릭 합니다. 브라우저 탭을 새로 고칠 합니다.
    
5. 왼쪽 탐색 창에서 **그룹**을 클릭합니다.
    
6. **그룹-모든 그룹** 블레이드에서 **+ 새 그룹을**클릭 합니다.
    
7. **그룹** 블레이드 선택에 대 한 **Office 365** **그룹 종류?**, **Windows 10 관리 되는 장치 사용자** **이름**입력 하 고 **멤버 자격 종류** **할당 됨** 을 선택 하 고 **만들기**를 클릭 합니다. 
    
8. **그룹** 블레이드를 닫습니다.
    
11. **그룹-모든 그룹** 블레이드를 닫습니다.
    
12. **Microsoft Intune** 블레이드 **빠른 작업** 목록에서 **준수 정책 만들기**를 클릭 합니다.
    
13. **준수 정책 프로필** 블레이드에서 **정책 만들기**를 클릭합니다.
    
14. **정책 만들기** 블레이드 **이름** **Windows 10**을 입력 합니다. **플랫폼** **Windows 10 이상**, 선택한 **Windows 10 규정 준수 정책** 블레이드에서 **확인** 을 클릭 한 다음 **만들기**를 클릭 합니다. **Windows 10** 블레이드를 닫습니다.
    
15. **규정 준수 정책 프로필** 블레이드 **Windows 10** 정책 이름을 클릭 합니다.
    
16. **Windows 10** 블레이드에서 **할당**을 클릭 하 고 **그룹을 포함 하도록 선택**를 클릭 합니다.
    
17. **그룹을 포함 하도록 선택** 블레이드 **Windows 10 관리 되는 장치 사용자** 그룹을 클릭 하 고 **선택**을 클릭 합니다.
    
18. **저장**을 클릭 한 다음 **Windows 10-배정** 블레이드를 닫습니다.
    
19. **준수 정책 프로필** 블레이드를 닫습니다.
    
20. **Microsoft Intune** 블레이드에서의 왼쪽된 탐색 영역에서 **클라이언트 응용 프로그램** 을 클릭 합니다.
    
21. **클라이언트 앱** 블레이드에서 **앱**클릭 한 다음 **추가**클릭 합니다. 

22. **추가 app** 블레이드 **App 유형**을 선택 하 고 **Office 365 제품군**에서 **Windows 10** 선택 합니다.

23. **응용 프로그램 제품군 구성**클릭 하 고 **확인**을 클릭 합니다.

24. **응용 프로그램 제품군 정보**를 클릭 하 고 **제품군 이름**, **설명 제품군** **Windows 10에 대 한 Office 응용 프로그램** 에서 **Windows 10에 대 한 Office 응용 프로그램을** 입력 한 다음 **확인**을 클릭 합니다.

25. **응용 프로그램 제품군 설정**을 클릭, **세미콜론 연간 회의** **업데이트 채널**선택한 다음 **확인**을 클릭 합니다.

26. **추가 app** 블레이드에서 **추가**클릭 합니다.

이제 **Windows 10** 장치 규정 준수 정책에서 선택한 앱을 테스트 하 고 **관리 하는 Windows 10 장치 users** 그룹의 구성원에 대 한 장치 규정 준수 정책. 
  
## <a name="next-step"></a>다음 단계

테스트 환경의 [모바일 장치 관리](m365-enterprise-test-lab-guides.md#mobile-device-management) 추가 기능 및 특징을 살펴봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)입니다.
  
[Microsoft 365 Enterprise 테스트 환경에서 iOS 및 Android 장치 등록](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[엔터프라이즈 이동성 + 보안 (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
