---
title: Office 365 배포의 다단계 인증 계획
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
description: Office 365의 다단계 인증 및 설정 하기 위해 수행 해야 하는 단계에 대해 알아봅니다.
ms.openlocfilehash: e3886387740fe904b9c9458f7b1abf736c3ef83f
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153571"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a>Office 365 배포의 다단계 인증 계획

다단계 인증(MFA)은 두 가지 이상의 확인 방법을 사용해야 하고 사용자 로그인 및 트랜잭션에 두 번째 보안 레이어를 추가하는 인증 방법입니다. 이 작업에는 다음 확인 방법 중 두 가지 이상이 필요합니다.
  
- 임의로 생성된 암호
    
- 전화 통화
    
- 스마트 카드(가상 또는 실제) 
    
- 생체 인식 장치 
    
## <a name="multi-factor-authentication-in-office-365"></a>Office 365에서의 다단계 인증

Office 365에서는 multi-factor authentication을 사용 하 여 추가 보안을 제공 하 고 Microsoft 365 관리 센터에서 관리 합니다. Office 365에서는 구독의 일부로 Azure Multi-factor Authentication 기능의 다음과 같은 하위 집합을 제공 합니다. 
  
- 최종 사용자에 대한 다단계 인증을 활성화 및 적용하는 기능
    
- 모바일 앱(온라인 및 일회용 암호[OTP])을 두 번째 인증 요소로 사용
    
- 전화 통화를 두 번째 인증 요소로 사용
    
- SMS(문자 서비스) 메시지를 두 번째 인증 요소로 사용
    
- 브라우저 이외의 클라이언트(예: Microsoft Lync 2013 통신 소프트웨어)의 응용 프로그램 암호
    
- 인증 전화 통화 중의 기본 Microsoft 인사말
    
추가 기능의 전체 목록은 [Azure 다단계 인증 버전 비교](https://go.microsoft.com/fwlink/?LinkId=506927)를 참조하세요. Azure 다단계 인증 서비스를 구입하여 언제든지 모든 기능을 이용할 수 있습니다. 
  
Office 365에 대한 클라우드 전용 배포 또는 Single Sign-On 및 AD FS(Active Directory Federation Services)에 대한 하이브리드 설치가 있는지에 따라 다른 기능 하위 집합을 사용할 수 있습니다. 
  
|**Office 365 테넌트를 어디에서 관리하나요?**|**MFA 두 번째 요소 옵션**|
|:-----|:-----|
|클라우드만  <br/> |Azure Multi-factor Authentication (텍스트 또는 전화 통화)  <br/> |
|하이브리드 설치, 관리되는 온-프레미스  <br/> | 사용자 ID 온-프레미스를 관리하는 경우 다음과 같은 옵션이 있습니다.  <br/>  실제 또는 가상 스마트 카드 (AD FS를 사용 하는 경우)  <br/> [Azure Multi-factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=526677) (AD FS 용 모듈)  <br/>  Azure Active Directory (Azure AD) 다단계 인증  <br/> |
   
  
다음 그림에서는 업데이트된 Office 2013 장치 앱(Windows 기반)에서 사용자가 MFA를 사용하여 로그인할 수 있는 방법을 보여줍니다. Office 2013 장치 앱은 [Active Directory 인증 라이브러리(ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684) 사용을 통한 다단계 인증을 지원합니다. Azure AD는 사용자가 로그인할 수 있는 웹 페이지를 호스팅합니다. ID 공급자는 Azure AD이거나 AD FS와 같은 페더레이션 ID 공급자일 수 있습니다. 페더레이션 사용자에 대한 인증은 다음 단계를 따릅니다.
  
1. Azure AD는 Office 365 테넌트에 대한 레코드의 ID 공급자가 호스팅하는 로그인 웹 페이지로 사용자를 리디렉션합니다. ID 공급자는 사용자의 로그인 이름에 지정된 도메인에 의해 결정됩니다.
    
2. 사용자는 자신의 장치에 표시된 로그인 웹 페이지에서 로그인합니다. 
    
3. 사용자가 성공적으로 로그인하면 ID 공급자는 Azure AD에 토큰을 반환합니다.
    
4. Azure AD는 Office 장치 앱에 JSON Web Token(JWT)을 반환하며, 장치 앱은 Office 365에서 JWT를 사용하여 인증됩니다. 
    
다음 그림에서 자세히 설명합니다.
  
![Office 2013 장치 앱용 최신 인증](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a>소프트웨어 요구 사항

Office 2013 클라이언트 앱용 MFA를 활성화하려면 [간편 실행 기반 설치](#click-to-run-based-installations) 또는 [MSI 기반 설치](#msi-based-installations)가 있는지에 따라 다음 소프트웨어(아래 나열한 버전 이상)를 설치해야 합니다.
  
Office 설치가 간편 실행 기반인지 MSI 기반인지 확인하려면:
  
1. Outlook 2013을 시작합니다.
    
2. **파일** 메뉴에서 **Office 계정을**선택 합니다.
    
3. Outlook 2013 간편 실행 설치의 경우 **업데이트 옵션** 항목이 표시됩니다. MSI 기반 설치의 경우 **업데이트 옵션** 항목이 표시되지 않습니다. 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a>간편 실행 기반 설치

간편 실행 기반 설치의 경우 아래 나열한 파일 버전 이상으로 다음 소프트웨어를 설치해야 합니다. 나열된 파일 버전과 같거나 높지 않은 파일 버전인 경우 아래 단계에 따라 업데이트합니다.
  
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

MFA를 설정하려면 다음을 완료해야 합니다.
  
1. 최신 인증을 위해 클라이언트 설정:
    
  - [Windows 장치에서 Office 2013에 대한 최신 인증을 설정합니다](enable-modern-authentication.md) . 
    
  - 타사 디렉터리 서비스를 사용 하 여 Azure Multi-factor Authentication을 설정 합니다.
    
    이 프로그램에 수락 된 특정 id 공급자에 대 한 정보를 보려면 [Azure Multi-factor Authentication 및 타사 VPN 솔루션을 포함 하는 고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) 를 참조 하세요. 
    
2. [Office 365에 대한 다단계 인증 설정](set-up-multi-factor-authentication.md)
    
3. MFA로 로그인하는 방법을 개별 사용자에게 알림: [2단계 확인을 통해 Office 365에 로그인합니다](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).
    
> [!IMPORTANT]
> 사용자가 Azure Multi-factor Authentication을 사용 하도록 설정한 상태에서 최신 인증을 사용 하도록 설정 되지 않은 모든 장치를 Office 2013를 실행 하는 경우 해당 장치에서 AppPasswords를 사용 해야 합니다. AppPasswords에 대 한 자세한 내용 및 사용 방법/위치/방법, [Azure Multi_Factor 인증을 사용 하는 앱 암호](https://go.microsoft.com/fwlink/p/?LinkId=528178)를 참조 하세요. 
  
## <a name="faq"></a>FAQ

[최신 인증 Wiki 문서에 대한 FAQ](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 **알려진 문제점:**
  
[Office 2013 및 Office 365 ProPlus 최신 인증: 온보딩하기 전에 알아야 할 사항](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Azure 다단계 인증 문제 해결:**
  
[Azure Multi-factor Authentication 문제 해결](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)을 참조 하세요.
  
[AD FS를 사용하는 경우 Office 2013 최신 인증의 로그인 문제를 해결하는 방법](https://support.microsoft.com/kb/3052203/)
  
 **대체 ID가 작동하지 않는 경우:**
  
[PowerShell을 사용하여 중복된 UPN을 수정하는 방법](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)(중복된 사용자 계정 이름을 수정하기 위한 스크립트)
  
 **클라이언트 액세스 필터링:**
  
[Office 2013 및 Office 365 ProPlus 최신 인증 및 클라이언트 액세스 필터링 정책: 온보딩하기 전에 알아야 할 사항](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **어떤 앱이 MFA를 지원하나요?**
  
|**Windows**|**Mac**|**iOS**|**Android 휴대폰**|**Android 태블릿**|
|:-----|:-----|:-----|:-----|:-----|
|이 릴리스에서는 Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 및 비즈니스용 Skype에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 Mac용 Word 2016, Mac용 Excel 2016 및 Mac용 PowerPoint 2016에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 iPad용 Word, iPad용 Excel 및 iPad용 PowerPoint에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 Android용 Word, Android용 Excel 및 Android용 PowerPoint에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 Android용 Word, Android용 Excel 및 Android용 PowerPoint에 대한 최신 인증이 지원됩니다.  <br/> |
|이 릴리스에서는 Outlook 2013 및 Outlook 2016에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 Mac용 Outlook 2016에 대한 최신 인증이 지원됩니다.  <br/> |이 릴리스에서는 iPad용 Outlook에 대한 최신 인증이 지원됩니다.  <br/> |||
   

