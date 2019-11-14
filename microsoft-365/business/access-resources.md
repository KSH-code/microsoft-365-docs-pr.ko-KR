---
title: Microsoft 365 Business의 Azure AD에 가입 된 장치에서 온-프레미스 리소스에 액세스
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Azure Active Directory에 가입 된 Windows 10 장치에서 비즈니스 앱, 파일 공유 및 프린터와 같은 온-프레미스 리소스에 액세스 하는 방법을 알아봅니다.
ms.openlocfilehash: fdc1eca6913ba6af4f6b65691fdee2165e7c827e
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323398"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Microsoft 365 Business의 Azure AD에 가입 된 장치에서 온-프레미스 리소스에 액세스

Azure Active Directory에 가입 된 모든 Windows 10 장치에는 Office 365 앱과 같은 모든 클라우드 기반 리소스에 대 한 액세스 권한이 있으며 Microsoft 365 Business를 통해 보호할 수 있습니다. LOB (기간 업무) 앱, 파일 공유 및 프린터와 같은 온-프레미스 리소스에 대 한 액세스를 허용할 수도 있습니다. 액세스를 허용 하려면 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) 를 사용 하 여 온-프레미스 Active Directory를 Azure Active directory와 동기화 합니다. 

자세한 내용은 [Azure Active Directory의 장치 관리 소개](https://docs.microsoft.com/azure/active-directory/device-management-introduction)를 참조 하세요.
이 단계는 다음 섹션에도 요약 되어 있습니다.

## <a name="run-azure-ad-connect"></a>Azure AD Connect 실행

조직의 Azure AD 조인 장치에서 온-프레미스 리소스에 액세스 하도록 설정 하려면 다음 단계를 완료 합니다.
  
1. 사용자, 그룹 및 연락처를 로컬 Active Directory에서 Azure Active Directory로 동기화 하려면 [Set up directory synchronization For Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)에 설명 된 대로 디렉터리 동기화 마법사 및 Azure AD Connect를 실행 합니다.
    
2. 디렉터리 동기화가 완료 되 면 조직의 Windows 10 장치가 Azure AD에 가입 되어 있는지 확인 합니다. 이 단계는 각 Windows 10 장치에서 개별적으로 수행 됩니다. 자세한 내용은 [Microsoft 365 비즈니스 사용자를 위한 Windows 장치 설정을](set-up-windows-devices.md) 참조 하세요. 
    
3. Windows 10 장치가 Azure AD에 가입 되 면 각 사용자는 자신의 장치를 다시 부팅 하 고 Microsoft 365 Business 자격 증명으로 로그인 해야 합니다. 이제 모든 장치에 온-프레미스 리소스에 대 한 액세스 권한이 있습니다.
    
Azure AD에 가입 된 장치에 대 한 온-프레미스 리소스에 액세스 하기 위해 추가 단계를 수행할 필요는 없습니다. 이 기능은 Windows 10에서 기본 제공 됩니다. 
  
조직이 앞에서 설명한 Azure AD 조인한 장치 구성에 배포할 준비가 되지 않은 경우 [하이브리드 AZURE AD 조인한 장치 구성을](manage-windows-devices.md)설정 하는 것이 좋습니다.
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Azure AD에 Windows 장치를 연결할 때의 고려 사항

Azure AD에서 가입한 Windows 장치가 이전에 도메인에 가입 되어 있거나 작업 그룹에 있는 경우 다음 제한 사항을 고려 하십시오.
  
- 장치 Azure AD가 조인 되 면 기존 프로필을 참조 하지 않고 새 사용자를 만듭니다. 프로필을 수동으로 마이그레이션해야 합니다. 사용자 프로필에는 즐겨찾기, 로컬 파일, 브라우저 설정 및 시작 메뉴 설정과 같은 정보가 포함 됩니다. 기존 파일 및 설정을 새 프로필에 매핑하는 타사 도구를 찾는 것이 가장 좋습니다.

- 장치에서 GPO (그룹 정책 개체)를 사용 하는 경우 일부 Gpo에는 Intune의 CSP ( [구성 서비스 공급자](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) )가 제공 되지 않을 수 있습니다. [Mmat 도구](https://www.microsoft.com/download/details.aspx?id=45520) 를 실행 하 여 기존 gpo에 대해 비교 가능한 csp를 찾습니다.

- 사용자는 Active Directory 인증을 통해 작동 하는 응용 프로그램을 인증할 수 없습니다. 레거시 앱을 평가 하 고 가능한 경우 최신 인증을 사용 하는 앱으로 업데이트 하는 것이 좋습니다.

- Active Directory 프린터 검색이 작동 하지 않습니다. 모든 사용자에 대해 직접 프린터 경로를 제공 하거나 [하이브리드 클라우드 인쇄](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)를 사용할 수 있습니다.
