---
title: Access 온-프레미스 Microsoft 365 비즈니스에서 Azure AD에 가입 된 장치에서 리소스
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
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 업무용 응용 프로그램, 파일 공유 및 Azure Active Directory에서 프린터 가입 Windows 10 장치와 동일 하 게 온-프레미스 리소스에 대 한 액세스를 얻는 방법에 알아봅니다.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869746"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Access 온-프레미스 Microsoft 365 비즈니스에서 Azure AD에 가입 된 장치에서 리소스

Azure Active Directory에 참가 있는 모든 Windows 10 장치 Office 365 앱 같은 모든 클라우드 기반 리소스에 액세스할 수 및 Microsoft 365 비즈니스에 의해 보호 됩니다. 또한 줄의 업무 (LOB) 응용 프로그램, 파일 공유 및 프린터 등의 온-프레미스 리소스에 대 한 액세스를 허용 하려면 온-프레미스 Active Directory [Azure AD 연결](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)을 사용 하 여 Azure Active Directory와 동기화 할 해야 있습니다. 자세한 내용은 [Azure Active Directory에서 장치 관리 소개](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) 참조 하십시오. 
  
## <a name="run-azure-ad-connect"></a>실행 Azure AD 연결

온-프레미스 리소스에 액세스 하려면 조직에 참가 하는 Azure AD 장치를 사용 하도록 설정 하려면 다음 단계를 완료 합니다.
  
1. Azure Active Directory에 사용자, 그룹 및 로컬 Active Directory에서 연락처를 동기화 하려면 디렉터리 동기화 마법사를 실행 하 고 [Office 365에 대 한 디렉터리 동기화를 설정](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)에 설명 된으로 Azure AD 연결 합니다.
    
2. 디렉터리 동기화가 완료 되 면 조직 Windows 10 장치에 참가 하는 Azure AD 없는지 확인 합니다. 이 단계는 각 Windows 10 장치에 개별적으로 수행 됩니다. 자세한 내용은 [Microsoft 365 비즈니스 사용자를 위한 Windows 장치 설정](set-up-windows-devices.md) 을 참조 하십시오. 
    
3. Windows 10 장치가 Azure AD에 참가 한 후 각 사용자가 장치 및 Microsoft 365 비즈니스 자격 증명을 사용 하 여 로그인 다시 부팅 해야 합니다. 모든 장치 지금도 온-프레미스 리소스에 대 한 액세스를 갖게 됩니다.
    
추가 단계가 온-프레미스 Azure AD에 대 한 리소스 가입 장치에 대 한 액세스를 가져올 필요가 없습니다. Windows 10에서 사용할 수 있는 기본 제공 기능입니다. 
  
조직이 Azure AD 가입 장치 위에서 설명한 구성에서 배포를 수행할 준비가 되지 않은, [하이브리드 Azure AD 가입 장치 구성](manage-windows-devices.md)설정을 것이 좋습니다.
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Azure AD를 Windows 장치에 참가할 때의 고려 사항

작업 그룹에서 또는 Azure AD 도메인에 가입 된 이전에 Windows 장치에 참가 하는 경우 다음과 같은 제한 사항이 고려해 야 합니다.
  
- 장치 Azure AD에 참가 하는 경우 기존 프로필을 참조 하지 않고도 새 사용자를 만듭니다. 이 문제를 해결 하는 프로필 수동으로 마이그레이션해야 할 수 있어야 합니다. 사용자 프로필 등 즐겨찾기, 로컬 파일, 브라우저 설정, 시작 메뉴의 설정 등의 정보를 포함합니다. 가장 좋은 방법은 새 프로필에 기존 파일 및 설정에 매핑하는 타사 도구를 찾을 수
    
- 장치 그룹 정책 개체 (GPO)을 사용 하는 경우 일부 Gpo 비교 가능한 [구성 서비스 공급자](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP)에서 Intune에 없을 수도 있습니다. 기존 Gpo에 대 한 비교 가능한 Csp를 찾을 수 [MMAT 도구](https://www.microsoft.com/download/details.aspx?id=45520) 를 실행 합니다. 
    
- 사용자가 Active Directory 인증 서버를 활용 하는 응용 프로그램에서 인증을 받을 수 없습니다. 처리이 레거시 응용 프로그램을 사용 하 여 평가 하 고 가능한 경우 현대 인증을 사용 하는 응용 프로그램을 업데이트 하는 것이 좋습니다.
    
- Active Directory 프린터 검색 작동 하지 않습니다. 이 문제를 해결 하 고, 모든 사용자에 대 한 직접 프린터 경로 제공 하 고 또는 [하이브리드 클라우드 인쇄](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)를 활용 합니다.
    

