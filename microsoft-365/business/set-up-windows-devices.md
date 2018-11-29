---
title: Microsoft 365 Business 사용자를 위한 Windows 장치 설정
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Microsoft 365 비즈니스 사용자를 위한 Windows 10 Pro을 실행 하는 Windows 장치를 설정 하는 방법에 알아봅니다. '
ms.openlocfilehash: 482199b175c568bfae420619aa02024303894789
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869932"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a>Microsoft 365 Business 사용자를 위한 Windows 장치 설정

## <a name="prerequisites"></a>필수 구성 요소

Microsoft 365 Business 사용자를 위해 Windows 장치를 설정하기 전에 모든 Windows 장치가 Windows 10 Pro 버전 1703(크리에이터 업데이트)을 사용하고 있는지 확인하세요. Windows 10 Pro를 보완하고 중앙 집중식 관리와 Microsoft 365 Business의 보안 제어를 사용할 수 있는 클라우드 서비스이자 장치 관리 기능인 Windows 10 Business를 배포하려면 Windows 10 Pro가 설치되어 있어야 합니다.
  
Windows 장치에서 Windows 7 Pro, Windows 8 Pro 또는 Windows 8.1 Pro를 실행하는 경우 Microsoft 365 Business 구독을 통해 Windows 10으로 업그레이드할 수 있습니다.
  
Windows 장치를 Windows 10 Pro 크리에이터 업데이트로 업그레이드하는 방법에 대한 자세한 내용은 [Windows Pro 크리에이터 업데이트로 Windows 장치 업그레이드](upgrade-to-windows-pro-creators-update.md)의 단계를 따르세요.
  
[장치가 Windows 10 Business로 업그레이드되었는지 확인](set-up-windows-devices.md#bkmk_verifywin10)을 참조하여 업그레이드가 완료되고 올바르게 작동하는지 확인하세요. 
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Windows 10 장치를 조직의 Azure AD에 연결

조직의 모든 Windows 장치가 Windows 10 Pro 크리에이터 업데이트로 업그레이드되었거나 이미 Windows 10 Pro 크리에이터 업데이트를 실행하고 있는 경우 장치를 조직의 Azure Active Directory에 연결할 수 있습니다. 장치가 연결되면 자동으로 Microsoft 365 Business 구독의 일부인 Windows 10 Business로 장치가 업그레이드됩니다.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>새로운 Windows 10 Pro 장치 또는 새로 업그레이드된 장치

Windows 10 Pro 크리에이터 업데이트를 실행하는 새로운 장치 또는 Windows 10 Pro 크리에이터 업데이트로 업그레이드했지만 Windows 10 장치 설정을 완료하지 않은 장치의 경우 다음 단계를 따르세요.
  
1. **어떻게 설정하시겠어요?** 페이지에 도달할 때까지 Windows 10 장치 설정을 진행합니다. 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. 해당 페이지에서 **조직용 설정**을 선택한 다음 Microsoft 365 Business 사용자 이름과 암호를 입력합니다. 
    
3. Windows 10 장치 설정을 완료합니다.
    
   설정을 완료하면 사용자가 조직의 Azure AD에 연결됩니다. [장치가 Azure AD에 연결되었는지 확인](set-up-windows-devices.md#bkmk_verifyaad)을 참조하여 연결을 확인하세요. 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>이미 설정되었으며 Windows 10 Pro를 실행하는 장치

 **Azure AD에 사용자 연결:**
  
1. 사용자의 Windows PC에서 Windows 10 Pro 버전 1703(크리에이터 업데이트)([필수 조건](pre-requisites-for-data-protection.md) 확인)을 사용하는 경우 Windows 로고와 설정 아이콘을 차례로 클릭합니다.
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. **설정**에서 **계정**으로 이동합니다.
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. **사용자 정보** 페이지에서 **회사 또는 학교 액세스** \> **연결**을 차례로 클릭합니다.
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. **회사 또는 학교 계정 설정** 대화 상자의 **대체 작업**에서 **Azure Active Directory에 이 장치 가입**을 선택합니다.
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. **로그인 하면 하기** 페이지에서 작업이 나 교육용 계정 입력 \> **다음**합니다.
  
   **암호 입력** 페이지에서 암호를 입력 \> **에 로그인**합니다.
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. 에 * *이 조직 있는지 확인 * * 페이지 정보가 올바른지 확인 하 고 **참가**클릭 합니다.
  
   **완료되었습니다!** 페이지에서 **완료**를 클릭합니다.
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
비즈니스용 OneDrive에 파일을 업로드한 경우 파일을 다시 동기화하세요. 타사 도구를 사용하여 프로필 및 파일을 마이그레이션한 경우 새 프로필과도 동기화합니다.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>장치가 Azure AD에 연결되었는지 확인

**설정** **대 한 액세스 작업 또는 학교** 페이지에서 사용자의 동기화 상태를 확인 하려면 클릭 **에 연결 됨** _에서 \<조직 이름\> **정보** 및 **연결 해제**단추를 공개 하려면 _ 영역입니다. 동기화 상태를 가져오려면 **정보** 클릭 합니다. 
  
동기화 상태 페이지에서 동기화를 클릭하여 PC에 최신 모바일 장치 관리 정책을 받습니다.
  
Microsoft 365 Business 계정을 사용하려면 Windows **시작** 단추로 이동하여 현재 계정 사진을 마우스 오른쪽 단추로 클릭한 다음 **계정 전환**을 클릭합니다. 조직 전자 메일 및 암호를 사용하여 로그인합니다.
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>장치가 Windows 10 Business로 업그레이드되었는지 확인

Azure AD에 연결된 Windows 10 장치가 Microsoft 365 Business 구독의 일부인 Windows 10 Business로 업그레이드되었는지 확인하세요.
  
1. **설정** \> **시스템** \> **정보**로 이동합니다.
    
2. **버전**이 **Windows 10 Business**인지 확인합니다.
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>다음 단계

모바일 장치를 설정하려면 [Microsoft 365 Business 사용자를 위한 모바일 장치 설정](set-up-mobile-devices.md)을 참조하고 장치 보호 또는 앱 보호를 설정하려면 [Microsoft 365 Business 관리](manage.md)를 참조하세요.
  
