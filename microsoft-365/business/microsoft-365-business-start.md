---
title: Microsoft 365 Business 시작
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Microsoft 365 Business를 설정하는 방법 알아보기
ms.openlocfilehash: f269e970cc1ee5ba7455ea799b238db577116f09
ms.sourcegitcommit: 38934a2115d5cdeb44c7484d57be07686c6f7720
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2019
ms.locfileid: "38704118"
---
# <a name="get-started-with-microsoft-365-business"></a>Microsoft 365 Business 시작

## <a name="what-is-microsoft-365-business"></a>Microsoft 365 Business란

Microsoft 365 Business는 항상 최신 상태를 유지 하는 Outlook, Word, Excel 및 기타 Office 제품과 같은 광범위 한 비즈니스 생산성 및 공동 작업 도구입니다. 관리 작업을 간단 하 게 수행할 수 있는 엔터프라이즈급 보안을 사용 하 여 모든 iOS, Android 및 Windows 10 장치에서 회사 파일을 보호 합니다.
  
Microsoft 365 Business는 최대 300의 라이선스를 의미 합니다. 라이선스가 더 필요한 경우 자세한 내용은 [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) 설명서를 참조 하세요. 
  
## <a name="get-microsoft-365-business"></a>Microsoft 365 Business 받기

- 파트너가 있는 경우 microsoft 365 Business: microsoft [파트너 센터에서 microsoft 365 business](get-microsoft-365-business.md)를 받을 수 있습니다.
    
- 파트너가 없는데 Microsoft 365 Business를 받으려면 [여기에서 구매](https://www.microsoft.com/microsoft-365/business)할 수 있습니다.
    
## <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business 설정

 **Microsoft 365 Business 제품군 설정 개요**
  
다음 다이어그램에서는 관리자가 Microsoft 365 Business를 설정 하는 방법을 설명 합니다. 또한 Microsoft 365 Business를 위해 Windows PC를 준비하는 단계를 설명합니다. [Windows AutoPilot](add-autopilot-devices-and-profile.md)를 사용 하 여 Microsoft 365 Business 관리 센터에서 새 장치를 추가할 수도 있습니다. AutoPilot을 사용 하 여 새 장치를 설정 하 고 사전 구성 하 여 사용자가 Microsoft 365 Business 자격 증명으로 로그인 하는 즉시 생산적으로 사용할 준비가 되도록 할 수 있습니다.
  
![관리자 및 사용자의 설정 및 관리 흐름을 보여 주는 다이어그램](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Microsoft 365 Business 설정(관리자)

전역 관리자 자격 증명을 사용 하 여 [microsoft 365 business 관리 센터](https://portal.office.com/adminportal/home) 에 로그인 하 고 다음 단계를 완료 하 여 Microsoft 365 Business를 설정 합니다. 
  
1. [Microsoft 365 Business를 사용 하 여 장치의 데이터를 보호 하기 위한 필수 구성 요소](pre-requisites-for-data-protection.md)
    
    먼저 필수 구성 요소를 읽고 장치가 Microsoft 365 Business를 사용할 준비가 되었는지 확인 합니다.
    
2. [설치 마법사를 사용 하 여 Microsoft 365 Business 설정](set-up.md)
    
    **로컬 Active Directory에서 클라우드로 영구적으로 이동**하는 경우 Microsoft 365 Business 관리 센터로 이동 하 여 설치 마법사를 사용 하 여 사용자를 수동으로 추가 하거나 Azure AD Connect를 사용 하 여 일회성 동기화를 수행할 수 있습니다. 이 작업은 다음 두 가지 방법으로 수행할 수 있습니다. 
    
    - Exchange 2010, Exchange 2013 또는 Exchange 2016 server도 있는 경우 최소 하이브리드를 사용 하 여 [exchange 사서함을 Office 365로 빠르게 마이그레이션할](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef)수 있습니다. 최소 하이브리드 단계에는 Azure AD에 대 한 사용자 동기화 및 온-프레미스에서 클라우드로의 전자 메일 마이그레이션 등이 포함 됩니다. 전자 메일 마이그레이션이 완료 되 면이 방법을 사용할 때 디렉터리 동기화가 자동으로 해제 됩니다.
    
    - Office 365 디렉터리 동기화 마법사를 사용 하 여 사용자를 클라우드와 동기화 합니다. [Office 365에서 디렉터리 동기화 설정](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)의 단계를 따라 이 프로세스를 완료합니다. 사용자를 클라우드에 동기화 한 후 [에는 Office 365에 대 한 디렉터리 동기화를 해제](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d)해야 합니다.
    
    또한이 방식으로 추가 된 각 사용자에 게 Microsoft 365 Business에 대 한 라이선스를 제공 해야 합니다. [설치 마법사](set-up.md) 에서이 작업을 수행 하거나 [비즈니스용 Office 365에서 사용자에 게 라이선스를 할당할](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC)수 있습니다.
    
### <a name="2-prepare-mobile-devices"></a>2: 모바일 장치 준비

[Microsoft 365 business 사용자를 위한 모바일 장치 설정](set-up-mobile-devices.md) 의 단계에 따라 장치에 Office 앱을 설치 하 고 Microsoft 365 Business에 의해 보호 되 고 있는지 확인 합니다. 
  
### <a name="3-prepare-pcs"></a>3: PC 준비

관리자는 [Windows AutoPilot](add-autopilot-devices-and-profile.md)을 사용 하 여 새 Windows 10 pc에 대 한 설정을 미리 선택할 수 있습니다. 사용자는이 항목의 단계를 수행 하 여 기존 또는 새 Windows 10 장치를 설정할 수 있으며 [Microsoft 365 비즈니스 사용자를 위해 Windows pc를 설정](set-up-windows-devices.md)합니다. 기존 장치의 경우 사용자가 **선택적** 으로 [파일을 비즈니스용 OneDrive로 이동할](move-files-to-onedrive.md)수 있습니다. 타사 도구를 사용 하 여 Windows 프로필에 연결 된 파일을 OneDrive로 이동할 수도 있습니다.
  
조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business를 설정 하 여 Windows 10 장치를 보호 하 되, 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다. 이를 설정 하려면 [도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정](manage-windows-devices.md) 의 단계를 수행 합니다. 이 방법을 사용할 수 있으며이 상태에 있는 장치를 **하이브리드 AZURE AD 가입 장치**라고 합니다. 
  
일부 온-프레미스 리소스가 포함 된 로컬 Active Directory (예: 파일 공유 및 프린터)를 유지 하는 경우 **azure ad 조인** 장치에서 [Microsoft 365 BUSINESS의 azure ad 조인 장치 로부터 온-프레미스 리소스에 액세스](access-resources.md)하 여 이러한 리소스에 액세스할 수 있습니다.
  
  
## <a name="contact-support"></a>지원 센터 문의

 **지원 센터에 문의해야 하는 경우:**
  
- 파트너에게 문의합니다.
    
- Microsoft 365 비즈니스 관리자는 고객 지원 팀에 액세스할 수 있습니다. ** [비즈니스 제품에 대 한 지원 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>관련 항목
[Microsoft 365 Business 문서 및 리소스](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
Microsoft[365 business로](migrate-to-microsoft-365-business.md) 의 Microsoft [365 business 마이그레이션 관리](manage.md)
  

