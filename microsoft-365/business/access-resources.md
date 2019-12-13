---
title: Microsoft 365 비즈니스의 Azure AD 조인 장치에서 온-프레미스 리소스에 액세스
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
description: Azure Active Directory에 연결된 Windows 10 장치의 LOB(기간 업무) 앱, 파일 공유 및 프린터와 같은 온-프레미스 리소스에 액세스하는 방법을 알아봅니다.
ms.openlocfilehash: 89ac38f3da9cbdd3ff1a5eb33dc129d2e83521c7
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967166"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Microsoft 365 비즈니스의 Azure AD 조인 장치에서 온-프레미스 리소스에 액세스

Azure Active Directory에 연결된 모든 Windows 10 장치에는 Office 365 앱과 같은 모든 클라우드 기반 리소스에 대한 액세스 권한이 있으며 Microsoft 365 Business로 보호할 수 있습니다. LOB(기간 업무) 앱, 파일 공유 및 프린터와 같은 온-프레미스 리소스에 대한 액세스를 허용할 수도 있습니다. 액세스를 허용하려면 [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)를 사용하여 온-프레미스 Active Directory를 Azure Active Directory와 동기화합니다. 

자세한 내용은 [Azure Active Directory에서 장치 관리 소개](https://docs.microsoft.com/azure/active-directory/device-management-introduction)를 참조하세요.
다음 섹션에서도 단계는 요약되어 있습니다.

> [!IMPORTANT]
> 이 절차는 OAuth와 NTLM에만 적용됩니다. Kerberos는 지원되지 않습니다.
 
## <a name="run-azure-ad-connect"></a>Azure AD Connect를 실행합니다.

조직의 Azure AD 조인 장치에서 온-프레미스 리소스에 액세스하도록 설정하려면 다음 단계를 완료하세요.
  
1. 로컬 Active Directory의 사용자, 그룹 및 연락처를 Azure Active Directory와 동기화하려면 [Office 365에 대한 디렉터리 동기화 설정](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)에서 설명한 대로 디렉터리 동기화 마법사 및 Azure AD Connect를 실행합니다.
    
2. 디렉터리 동기화가 완료되면 조직의 Windows 10 장치가 Azure AD에 연결되어 있는지 확인합니다. 이 단계는 각각의 Windows 10 장치에서 개별적으로 수행됩니다. 자세한 내용은 [Microsoft 365 Business 사용자를 위한 Windows 장치 설정](set-up-windows-devices.md)을 참조하세요. 
    
3. Windows 10 장치가 Azure AD에 연결된 후에는 각 사용자가 장치를 다시 부팅하여 Microsoft 365 Business 자격 증명으로 로그인해야 합니다. 이제 모든 장치에서 온-프레미스 리소스에 액세스할 수 있습니다.
    
Azure AD 조인 장치에 대한 온-프레미스 리소스에 액세스하는 데 필요한 추가 단계는 없습니다. 이 기능은 Windows 10에서 기본 제공됩니다. 

WHFB 자격 증명 로그인을 통해 PIN/Bio-metric과 같은 암호 방식 이외에 AADJ 장치에 로그인한 다음 온-프레미스 리소스(공유, 프린터 등)에 액세스하려는 경우 https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base을 수행합니다.
  
조직에서 앞서 설명한 Azure AD 조인 장치 구성에 배포할 준비가 되지 않은 경우 [하이브리드 Azure AD 조인 장치 구성](manage-windows-devices.md)을 설정하는 것이 좋습니다.
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Azure AD에 Windows 장치를 연결할 때의 고려 사항

Azure AD에 연결된 Windows 장치가 이전에 도메인에 가입된 경우 또는 작업 그룹에 있는 경우 다음 제한 사항을 고려하세요.
  
- 장치에 Azure AD가 연결되면 기존 프로필을 참조하지 않고 새 사용자를 만듭니다. 프로필은 수동으로 마이그레이션해야 합니다. 사용자 프로필에는 즐겨찾기, 로컬 파일, 브라우저 설정 및 시작 메뉴 설정과 같은 정보가 포함되어 있습니다. 가장 좋은 방법은 기존 파일 및 설정을 새 프로필로 매핑하는 타사 도구를 찾는 것입니다.

- 장치가 GPO(그룹 정책 개체)를 사용하는 경우 일부 GPO는 Intune에서 유사한 [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)(CSP)를 갖지 않을 수 있습니다. [MMAT 도구](https://www.microsoft.com/download/details.aspx?id=45520)를 실행하여 기존 GPO와 유사한 CSP를 찾습니다.

- 사용자가 Active Directory 인증에 의존하는 응용 프로그램에 인증할 수 없습니다. 레거시 앱을 평가하고 가능한 경우 최신 인증을 사용하는 앱으로 업데이트하는 것이 좋습니다.

- Active Directory 프린터 검색이 작동하지 않습니다. 모든 사용자에 대해 직접 프린터 경로를 제공하거나 [하이브리드 클라우드 인쇄](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)를 사용할 수 있습니다.
