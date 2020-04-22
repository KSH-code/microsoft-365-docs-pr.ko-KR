---
title: Microsoft 365 배포에 대 한 다단계 인증 계획
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365의 다단계 인증 및이를 설정 하기 위해 수행 해야 하는 단계에 대해 알아봅니다.
ms.openlocfilehash: 035a79c9db44990dbce09de540e3e483b3cea8df
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665671"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a>Microsoft 365 배포에 대 한 다단계 인증 계획

다단계 인증(MFA)은 두 가지 이상의 확인 방법을 사용해야 하고 사용자 로그인 및 트랜잭션에 두 번째 보안 레이어를 추가하는 인증 방법입니다. 이는 다음과 같이 사용자 계정 암호를 초과 하는 정보와 함께 추가 확인 단계를 요구 하는 방식으로 작동 합니다.
  
- 사용자의 smart 전화로 전송 되는 임의로 생성 되는 확인 코드
    
- 전화 통화
    
- 스마트 카드(가상 또는 실제) 
    
- 생체 인식 장치 
    
## <a name="mfa-in-microsoft-365"></a>Microsoft 365의 MFA

Microsoft 365에서는 MFA를 사용 하 여 추가 보안을 제공 하 고 Microsoft 365 관리 센터에서 관리 합니다. Microsoft 365에서는 구독의 일부로 [Azure Multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) 기능의 다음과 같은 하위 집합을 제공 합니다. 
  
- 최종 사용자에 대해 MFA를 사용 하도록 설정 하 고 적용 하는 기능
    
- 모바일 앱(온라인 및 일회용 암호[OTP])을 두 번째 인증 요소로 사용
    
- 전화 통화를 두 번째 인증 요소로 사용
    
- SMS (Short Message Service) 텍스트 메시지를 두 번째 인증 요소로 사용
    
- 비 브라우저 클라이언트용 응용 프로그램 암호 (예: Microsoft Lync 2013 communications software)
    
- 인증 전화 통화 중의 기본 Microsoft 인사말
    
추가 된 기능의 전체 목록은 [Azure Multi-factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927)을 참조 하세요. [Azure Multi-factor Authentication 라이선스](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing)를 구입 하 여 언제 든 지 모든 기능을 이용할 수 있습니다. 
  
Microsoft 365에서 사용자 계정이 있는 경우 클라우드 전용 id를 사용 하는지 또는 single sign-on 및 AD FS (Active Directory Federation Services)로 하이브리드를 설정 했는지에 따라 다른 기능 하위 집합을 사용할 수 있습니다. 
  
|**어디에서 Microsoft 365를 관리 하나요?**|**MFA 두 번째 요소 옵션**|
|:-----|:-----|
|클라우드만  <br/> | Azure Multi-factor Authentication (텍스트 또는 전화 통화)  <br/> |
|하이브리드 설치, 관리되는 온-프레미스  <br/> | 사용자 ID 온-프레미스를 관리하는 경우 다음과 같은 옵션이 있습니다.  <br/> -실제 또는 가상 스마트 카드 (AD FS)  <br/> -Azure Multi-factor Authentication (AD FS 용 모듈)  <br/>  -Azure Multi-factor Authentication  <br/> |
   
Office 2013 장치 앱은 [ADAL (Active Directory 인증 라이브러리)](https://go.microsoft.com/fwlink/p/?LinkId=526684)사용을 통해 MFA를 지원 합니다. Azure AD (Active Directory)는 사용자가 로그인 할 수 있는 웹 페이지를 호스팅합니다. ID 공급자는 Azure AD이거나 AD FS와 같은 페더레이션 ID 공급자일 수 있습니다. 페더레이션 사용자에 대한 인증은 다음 단계를 따릅니다.
  
1. Azure AD는 사용자를 조직의 레코드 id 공급자가 호스팅하는 로그인 웹 페이지로 리디렉션합니다. ID 공급자는 사용자의 로그인 이름에 지정된 도메인에 의해 결정됩니다.
    
2. 사용자는 자신의 장치에 표시된 로그인 웹 페이지에서 로그인합니다. 
    
3. 사용자가 성공적으로 로그인하면 ID 공급자는 Azure AD에 토큰을 반환합니다.
    
4. Azure AD는 Office 장치 앱에 대 한 JWT (JSON Web Token)를 반환 하며, 장치 앱은 Microsoft 365에서 JWT를 사용 하 여 인증 됩니다. 
    
  
## <a name="requirements-for-office-2013-client-apps"></a>Office 2013 클라이언트 앱에 대 한 요구 사항

Office 2013 클라이언트 앱용 MFA를 활성화하려면 [간편 실행 기반 설치](#click-to-run-based-installations) 또는 [MSI 기반 설치](#msi-based-installations)가 있는지에 따라 다음 소프트웨어(아래 나열한 버전 이상)를 설치해야 합니다.
  
Office 설치가 간편 실행 기반인지 MSI 기반인지 확인하려면:
  
1. Outlook 2013을 시작합니다.
    
2. **파일** 메뉴에서 **Office 계정을**선택 합니다.
    
3. Outlook 2013 간편 실행 설치의 경우 **업데이트 옵션** 항목이 표시됩니다. MSI 기반 설치의 경우 **업데이트 옵션** 항목이 표시되지 않습니다. 
    
    ![Office 2013 설치가 간편 실행 또는 MSI 기반 인지를 알리는 방법](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

Sor [에 대 한 자세한 내용은 최신 인증 wiki 문서에 대 한 FAQ](https://go.microsoft.com/fwlink/p/?LinkId=530064)를 참조 하세요.
  
### <a name="click-to-run-based-installations"></a>간편 실행 기반 설치

간편 실행 기반 설치의 경우 아래 나열 된 파일 버전 또는 이후 버전의 파일을 사용 하 여 다음 소프트웨어가 설치 되어 있어야 합니다. 나열된 파일 버전과 같거나 높지 않은 파일 버전인 경우 아래 단계에 따라 업데이트합니다.
  
|**파일 이름**|**컴퓨터의 설치 경로**|**파일 버전**|
|:-----|:-----|:-----|
|MSO. DLL  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |15.0.4753.1001  <br/> |
|CSI. DLL  <br/> |CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll  <br/> |15.0.4753.1000  <br/> |
|Groove  <br/> |C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe  <br/> |15.0.4763.1000  <br/> |
|Outlook.exe  <br/> |C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe  <br/> |15.0.4753.1002  <br/> |
|ADAL. DLL  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |일정하지 않음  <br/> |
   
### <a name="msi-based-installations"></a>MSI 기반 설치

MSI 기반 설치의 경우 아래 나열한 파일 버전 이상으로 다음 소프트웨어를 설치해야 합니다. 나열된 파일 버전과 같거나 높지 않은 파일 버전인 경우 업데이트 KB 문서 열에 있는 링크를 사용하여 업데이트합니다.
  
|**파일 이름**|**컴퓨터의 설치 경로**|**업데이트를 다운로드할 위치**|**버전**|
|:-----|:-----|:-----|:-----|
|MSO. DLL  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |[KB3085480](https://support.microsoft.com/kb/3085480) <br/> |15.0.4753.1001  <br/> |
|CSI. DLL  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll  <br/> |[KB3085504](https://support.microsoft.com/kb/3085504) <br/> |15.0.4753.1000  <br/> |
|Groove  <br/> |C:\Program Files\Microsoft Office\Office15\GROOVE.EXE  <br/> |[KB3085509](https://support.microsoft.com/kb/3085509) <br/> |15.0.4763.1000  <br/> |
|Outlook.exe  <br/> |C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE  <br/> |[KB3085495](https://support.microsoft.com/kb/3085495) <br/> |15.0.4753.1002  <br/> |
|ADAL. DLL  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |[KB3055000](https://support.microsoft.com/kb/3055000) <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |[MS14-052](https://support.microsoft.com/kb/2977629) <br/> |해당 사항 없음  <br/> |
   
## <a name="enable-mfa"></a>MFA 설정

구독에 대해 MFA를 사용 하도록 설정 하려면 다음 단계를 수행 합니다.
  
1. 필요한 경우 다음을 수행 합니다. 

  - [Windows 장치에서 Office 2013에 대 한 최신 인증을 사용 하도록 설정](enable-modern-authentication.md)합니다.
    
  - 타사 디렉터리 서비스를 사용 하 여 Azure Multi-factor Authentication을 설정 합니다.
    
    이 프로그램에 수락 된 특정 id 공급자에 대 한 정보를 보려면 [Azure Multi-factor Authentication 및 타사 VPN 솔루션을 포함 하는 고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) 를 참조 하세요. 
    
2. [Microsoft 365에 대해 MFA를 설정](set-up-multi-factor-authentication.md)합니다.
    
3. 개별 사용자에 게 MFA로 로그인 하는 방법을 설명 합니다. [MFA를 사용 하 여 Microsoft 365에 로그인을](https://support.office.com/en-us/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb)참조 하세요.

> [!IMPORTANT]
> 사용자가 Azure Multi-factor Authentication을 사용 하도록 설정한 상태에서 최신 인증을 사용 하도록 설정 되지 않은 모든 장치를 Office 2013를 실행 하는 경우 해당 장치에서 AppPasswords를 사용 해야 합니다. AppPasswords에 대 한 자세한 내용은 [Azure 다단계 인증을 사용 하는 앱 암호](https://go.microsoft.com/fwlink/p/?LinkId=528178)를 참조 하세요.
  
## <a name="faq"></a>FAQ

[최신 인증 Wiki 문서에 대한 FAQ](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a>알려진 문제

[엔터프라이즈 최신 인증용 Office 2013 및 Microsoft 365 앱: 온 보 딩 하기 전에 알아야 할 사항](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Azure 다단계 인증 문제 해결:**
  
[Azure Multi-factor Authentication 문제 해결](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)을 참조 하세요.
  
[AD FS를 사용하는 경우 Office 2013 최신 인증의 로그인 문제를 해결하는 방법](https://support.microsoft.com/kb/3052203/)
  
 **대체 ID가 작동하지 않는 경우:**
  
[PowerShell을 사용하여 중복된 UPN을 수정하는 방법](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)(중복된 사용자 계정 이름을 수정하기 위한 스크립트)
  
 **클라이언트 액세스 필터링:**
  
[엔터프라이즈 최신 인증 및 클라이언트 액세스 필터링 정책에 대 한 Office 2013 및 Microsoft 365 앱: 온 보 딩 하기 전에 알아야 할 사항](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **어떤 앱이 MFA를 지원하나요?**
  
|**Windows**|**Mac**|**iOS**|**Android 휴대폰**|**Android 태블릿**|
|:-----|:-----|:-----|:-----|:-----|
|이 릴리스에서는 Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 및 비즈니스용 Skype에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 Mac용 Word 2016, Mac용 Excel 2016 및 Mac용 PowerPoint 2016에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 iPad용 Word, iPad용 Excel 및 iPad용 PowerPoint에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 Android용 Word, Android용 Excel 및 Android용 PowerPoint에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 Android용 Word, Android용 Excel 및 Android용 PowerPoint에 대한 최신 인증이 지원됩니다.  <br/> |
|이 릴리스에서는 Outlook 2013 및 Outlook 2016에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 Mac용 Outlook 2016에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 iPad용 Outlook에 대한 최신 인증이 지원됩니다.  <br/> |||
   

