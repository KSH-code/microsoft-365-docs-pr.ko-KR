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
ms.openlocfilehash: 4c744d6a900dba3c11ee51e75602a430268e15bb
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38029107"
---
# <a name="get-started-with-microsoft-365-business"></a>Microsoft 365 Business 시작

## <a name="what-is-microsoft-365-business"></a>Microsoft 365 Business란

Microsoft 365 Business는 항상 최신 상태를 유지하는 Outlook, Word, Excel 등의 Office 제품과 같은 다양한 비즈니스 생산성 및 공동 작업 도구입니다. 간단하게 관리할 수 있는 엔터프라이즈급 보안을 사용하여 모든 iOS, Android 및 Windows 10 장치에서 작업 파일을 보호할 수 있습니다.
  
Microsoft 365 Business는 최대 300개의 라이선스용으로 만들어졌으며, 라이선스가 더 필요한 경우 자세한 내용은 [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) 설명서를 참조하세요. 
  
## <a name="get-microsoft-365-business"></a>Microsoft 365 Business 받기

- 파트너가 있는 경우 파트너가 Microsoft 365 Business를 받습니다([Microsoft 파트너 센터에서 Microsoft 365 Business 받기)](get-microsoft-365-business.md).
    
- 파트너가 없는데 Microsoft 365 Business를 받으려면 [여기에서 구매](https://www.microsoft.com/microsoft-365/business)할 수 있습니다.
    
## <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business 설정

 **Microsoft 365 Business 제품군 설정 개요**
  
다음 다이어그램에서는 관리자가 Microsoft 365 Business를 설정하는 방법을 설명합니다. Microsoft 365 Business용 Windows PC를 준비하는 단계도 설명합니다. [Windows AutoPilot](add-autopilot-devices-and-profile.md)을 사용하여 Microsoft 365 Business 관리 센터에서 새 장치를 추가할 수도 있습니다. AutoPilot을 사용하여 새 장치를 설정하고 사전 구성할 수 있으며, 사용자가 Microsoft 365 Business 자격 증명으로 로그인하는 즉시 생산성 있게 사용할 준비가 됩니다.
  
![관리자 및 사용자의 설정 및 관리 흐름을 보여 주는 다이어그램](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Microsoft 365 Business 설정(관리자)

전역 관리자 자격 증명을 사용하여 [Microsoft 365 Business 관리 센터](https://portal.office.com/adminportal/home)에 로그인하고 아래 단계를 완료하여 Microsoft 365 Business을(를) 설정합니다. 
  
1. [Microsoft 365 Business를 사용하여 장치의 데이터를 보호하기 위한 필수 조건](pre-requisites-for-data-protection.md)
    
    우선 필수 조건을 읽어 장치가 Microsoft 365 Business를 사용할 준비가 되었는지 확인합니다.
    
2. [설정 마법사를 사용하여 Microsoft 365 Business 설정](set-up.md)
    
    **로컬 Active Directory에서 클라우드로 영구적으로 전환**하는 경우 설정 마법사를 사용하여 Microsoft 365 Business 관리 센터에서 수동으로 사용자를 추가하거나 Azure AD Connect와 일회성 동기화를 수행할 수 있습니다. 두 가지 방법으로 이 작업을 수행할 수 있습니다. 
    
  - 또한 Exchange 2010, Exchange 2013 또는 Exchange 2016 서버가 있는 경우 [최소 하이브리드를 사용하여 Exchange 사서함을 Office 365로 빠르게 마이그레이션](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef)할 수 있습니다. 최소 하이브리드 단계에는 온-프레미스에서 클라우드로 전자 메일 마이그레이션뿐만 아니라 Azure AD와 사용자의 일회성 동기화가 포함됩니다. 이 방법을 사용하면 전자 메일 마이그레이션이 완료된 후 디렉터리 동기화가 자동으로 해제됩니다.
    
  - 사용자와 클라우드를 동기화하려면 Office 365 디렉터리 동기화 마법사를 사용하세요. [Office 365에서 디렉터리 동기화 설정](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)의 단계를 따라 이 프로세스를 완료합니다. 사용자를 클라우드에 동기화한 후 [디렉터리 동기화를 해제해야 합니다](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    또한 이 방법으로 추가한 사용자에게 Microsoft 365 Business에 대한 라이선스를 부여해야 합니다. [설정 마법사](set-up.md) 또는 [비즈니스용 Office 365의 사용자에게 라이선스 할당](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC)에서 이 작업을 수행할 수 있습니다.
    
### <a name="2-prepare-mobile-devices"></a>2: 모바일 장치 준비

[Microsoft 365 Business 사용자를 위해 모바일 장치 설정](set-up-mobile-devices.md)의 단계에 따라 장치에 Office 앱을 설치하고 Microsoft 365 Business로 보호되는지 확인합니다. 
  
### <a name="3-prepare-pcs"></a>3: PC 준비

관리자는 [Windows AutoPilot](add-autopilot-devices-and-profile.md)을 사용하여 새 장치 Windows 10 PC의 설정을 미리 선택할 수 있습니다. 사용자는 [Microsoft 365 Business 사용자용 Windows PC 설정](set-up-windows-devices.md) 항목의 단계에 따라 기존 또는 새 Windows 10 장치를 설정할 수 있습니다. 기존 장치의 경우 사용자는 **선택적으로**[ 비즈니스용 OneDrive로 파일을 이동](move-files-to-onedrive.md)할 수도 있습니다. 타사 도구를 사용하여 Windows 프로필과 연결된 파일을 OneDrive로 이동할 수도 있습니다.
  
조직에서 Windows Server Active Directory 온-프레미스를 사용하는 경우 사용자는 로컬 인증이 필요한 온-프레미스 리소스에 대한 액세스를 계속 유지하면서 Microsoft 365 Business를 설정하여 Windows 10 장치를 보호할 수 있습니다.[Microsoft 365 Business로 도메인에 가입한 Windows 10 장치 관리](manage-windows-devices.md)의 단계에 따라 설정합니다. 이 방법은 권장되는 방법이며, 이러한 상태의 장치를 **하이브리드 Azure AD에 조인된 장치**라고 합니다. 
  
파일 공유 및 프린터처럼 일부 온-프레미스 리소스가 포함된 로컬 Active Directory를 유지하는 경우 [Microsoft 365 Business에서 Azure AD에 조인된 장치의 온-프레미스 리소스에 액세스](access-resources.md)의 단계에 따라 이러한 리소스에 대한 액세스 권한을 **Azure AD에 조인된 장치**에 부여할 수 있습니다.
  
Windows 10 PC를 설정한 후 장치에 [Office를 자동으로 설치](auto-install-or-uninstall-office.md)할 수 있습니다. 
  
## <a name="contact-support"></a>지원 센터 문의

 **지원 센터에 문의해야 하는 경우:**
  
- 파트너에게 문의합니다.
    
- Microsoft 365 Business 관리자는 고객 지원 팀, **[비즈니스 제품에 대해 고객 지원 센터 문의 - 관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)** 에 액세스할 수 있습니다.
    
## <a name="related-topics"></a>관련 항목
[Microsoft 365 Business 문서 및 리소스](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
Microsoft[365 business로](migrate-to-microsoft-365-business.md) 의 Microsoft [365 business 마이그레이션 관리](manage.md)
  

