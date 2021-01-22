---
title: Microsoft 365 Business Premium 사용자를 위한 Windows 장치 설정
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 중앙 집중식 관리 및 보안 제어를 사용하도록 설정하여 Windows 10 Pro for Microsoft 365 Business Premium 사용자를 실행하는 Windows 장치를 설정하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: b1877d83f113a2ba23d0db374967e0afcd7fe067
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928727"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Microsoft 365 Business Premium 사용자를 위한 Windows 장치 설정

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Microsoft 365 Business Premium 사용자를 위한 Windows 장치 설정의 선행 준비

Microsoft 365 Business Premium 사용자를 위해 Windows 장치를 설정하기 전에 모든 Windows 장치가 Windows 10 Pro 버전 1703(크리에이터스 업데이트)을 실행하고 있는지 확인하십시오. Windows 10 Pro는 Windows 10 Pro를 보완하고 Microsoft 365 Business Premium의 중앙 집중식 관리 및 보안 제어를 가능하게 하는 클라우드 서비스 및 장치 관리 기능 집합인 Windows 10 Business를 배포하기 위한 선행 요구입니다.
  
Windows 7 Pro, Windows 8 Pro 또는 Windows 8.1 Pro를 실행하는 Windows 장치가 있는 경우 Microsoft 365 Business Premium 구독을 통해 Windows 10 업그레이드를 받을 수 있습니다.
  
Windows 장치를 Windows 10 Pro 크리에이터 업데이트로 업그레이드하는 방법에 대한 자세한 내용은 [Windows Pro 크리에이터 업데이트로 Windows 장치 업그레이드](upgrade-to-windows-pro-creators-update.md)의 단계를 따르세요.
  
디바이스가 [Azure AD에](#verify-the-device-is-connected-to-azure-ad) 연결되어 있는지 확인하여 업그레이드가 있는지 확인하거나 업그레이드가 올바르게 진행된지 확인합니다.

Windows를 Microsoft 365에 연결하는 방법을 짧은 비디오를 시청합니다.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Windows 10 장치를 조직의 Azure AD에 연결

조직의 모든 Windows 장치가 Windows 10 Pro 크리에이터스 업데이트로 업그레이드되거나 이미 Windows 10 Pro 크리에이터스 업데이트를 실행 중인 경우 이러한 장치를 조직의 Azure Active Directory에 가입할 수 있습니다. 디바이스가 가입된 후 자동으로 Microsoft 365 Business Premium 구독의 일부인 Windows 10 Business로 업그레이드됩니다.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>최신 또는 새로 업그레이드된 Windows 10 Pro 장치의 경우

Windows 10 Pro 크리에이터 업데이트를 실행하는 새로운 장치 또는 Windows 10 Pro 크리에이터 업데이트로 업그레이드했지만 Windows 10 장치 설정을 완료하지 않은 장치의 경우 다음 단계를 따르세요.
  
1. **어떻게 설정하시겠어요?** 페이지에 도달할 때까지 Windows 10 장치 설정을 진행합니다. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. 여기서 **조직에** 대해 설정한 다음 Microsoft 365 Business Premium의 사용자 이름과 암호를 입력합니다. 
    
3. Windows 10 장치 설정을 완료합니다.
    
   설정을 완료하면 사용자가 조직의 Azure AD에 연결됩니다. [장치가 Azure AD에 연결되었는지 확인](#verify-the-device-is-connected-to-azure-ad)을 참조하여 연결을 확인하세요. 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>Windows 10 Pro를 이미 설치하여 운영 중인 장치의 경우

 **Azure AD에 사용자 연결:**
  
1. 사용자의 Windows PC에서 Windows 10 Pro 버전 1703(크리에이터 업데이트)([필수 조건](pre-requisites-for-data-protection.md) 확인)을 사용하는 경우 Windows 로고와 설정 아이콘을 차례로 클릭합니다.
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. **설정** 에서 **계정** 으로 이동합니다.
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. **사용자 정보** 페이지에서 **회사 또는 학교 액세스** \> **연결** 을 차례로 클릭합니다.
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. **회사 또는 학교 계정 설정** 대화 상자의 **대체 작업** 에서 **Azure Active Directory에 이 장치 가입** 을 선택합니다.
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. **로그인 시작** 페이지에 회사 또는 학교 계정을 입력합니다 \> **다음**.
  
   **암호 입력** 페이지에서 암호를 입력합니다 \> **로그인**.
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. 조직 **페이지가 맞는지** 확인하고 정보가 올바른지 확인하고 참가를 **선택합니다.**
  
   모두 **설정되어 있습니다!** page, chosse **Done.**
  
   ![On the Make sure this is your organization screen, choose Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
비즈니스용 OneDrive에 파일을 업로드한 경우 파일을 다시 동기화합니다. 타사 도구를 사용하여 프로필 및 파일을 마이그레이션한 경우 이러한 도구도 새 프로필에 동기화합니다.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>장치가 Azure AD에 연결되었는지 확인

동기화 상태를 확인하려면 설정의 **Access 직장 또는 학교**  페이지에서 _에 연결 영역을 선택하여 단추 정보 및 연결 끊기를  \<organization name\>  **노출합니다.** 정보를 **선택하면** 동기화 상태를 확인할 수 있습니다. 
  
동기화 **상태 페이지에서** 동기화를 **선택하면** PC에 최신 모바일 장치 관리 정책이 적용됩니다.
  
Microsoft 365 Business Premium 계정 사용을 시작하려면 **Windows** 시작 단추로 이동하여 현재 계정 사진을 마우스 오른쪽 단추로 클릭한 다음 계정을 **전환합니다.** 조직 전자 메일 및 암호를 사용하여 로그인합니다.
  
![동기화 상태를 보려면 정보 버튼을 클릭합니다.](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>PC가 Windows 10 Business로 업그레이드된지 확인

Azure AD에 가입된 Windows 10 장치가 Microsoft 365 Business Premium 구독의 일부로 Windows 10 Business로 업그레이드되는지 확인
  
1. **설정** \> **시스템** \> **정보** 로 이동합니다.
    
2. **버전** 이 **Windows 10 Business** 인지 확인합니다.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>다음 단계

모바일 장치를 설정하려면 [Microsoft 365 Business Premium](set-up-mobile-devices.md)사용자에 대한 모바일 장치 설정 , 장치 보호 또는 앱 보호 정책을 설정하려면 [비즈니스용 Microsoft 365](manage.md)관리를 참조하세요.
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Microsoft 365 Business Premium 설정 및 사용에 대한 자세한 내용은

[Microsoft 365 Business 교육 비디오](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
