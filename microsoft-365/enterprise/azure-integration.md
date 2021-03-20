---
title: Microsoft 365와 Azure 통합
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: 암호 동기화 또는 Single Sign-On을 원하는 경우 Azure AD와 Microsoft 365를 통합합니다.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905335"
---
# <a name="azure-integration-with-microsoft-365"></a>Microsoft 365와 Azure 통합

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365는 Azure AD(Azure Active Directory)를 사용하여 뒤에서 사용자 ID를 관리합니다. Microsoft 365 구독에는 무료 Azure AD 구독이 포함되어 있으므로 사용자 계정 및 암호를 동기화하거나 Single Sign-On을 설정할 수 있도록 AD DS(Active Directory 도메인 서비스)를 통합할 수 있습니다. 고급 기능을 구입하여 계정을 더 효율적으로 관리할 수도 있습니다.
  
Azure AD는 Microsoft 365 구독을 확장하고 사용자 지정하는 데 사용할 수 있는 통합 앱 관리와 같은 다른 기능도 제공합니다.
  
Microsoft 365 관리 센터에서 Azure AD 배포 관리자를 사용하여 안내 설치 및 구성 환경을 사용할 수 있습니다(Microsoft 365에 로그인해야 합니다).

 - [Azure AD Connect 어드바이저](https://aka.ms/aadconnectpwsync)
 - [AD FS 배포 어드바이저](https://aka.ms/adfsguidance)
 - [Azure AD 설정 가이드](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD 버전 및 Microsoft 365 ID 관리

Microsoft 365에 대한 유료 구독이 있는 경우 Azure AD 구독도 무료로 사용할 수 있습니다. Azure AD를 사용하여 사용자 및 그룹 계정을 만들고 관리할 수 있습니다. 이 구독을 활성화하려면 일회성 등록을 완료해야 합니다. 이후에 Microsoft 365 관리 센터에서 Azure AD에 액세스할 수 있습니다. 

무료 Azure AD 구독을 등록하는 방법에 대한 지침은 무료 [Azure AD 구독 사용을 참조하세요.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) 등록하기 위해 직접 이동하지 azure.microsoft.com Microsoft 365를 사용하여 무료 Azure AD 구독과는 별개인 Microsoft Azure에 대한 평가판 또는 유료 구독이 됩니다. 
  
무료 구독을 사용하면 사내의 로렉터와 동기화하고, Single Sign-On을 설정하고, Salesforce, DropBox 등의 서비스 응용 프로그램으로 많은 소프트웨어와 동기화할 수 있습니다.
  
향상된 AD DS 기능, 양방향 동기화 및 기타 관리 기능을 원하는 경우 무료 구독을 유료 프리미엄 구독으로 업그레이드할 수 있습니다. 자세한 내용은 Azure [Active Directory 버전 을 참조하세요.](https://azure.microsoft.com/pricing/details/active-directory/)
  
Microsoft 365 및 Azure AD에 대한 자세한 내용은 [Microsoft 365 ID 모델을 참조하세요.](about-microsoft-365-identity.md)
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Microsoft 365 테넌트의 기능 확장

|**기능**|**설명**|
|:-----|:-----|
|통합 앱  <br/> |메일, 일정, 연락처, 사용자, 그룹, 파일 및 폴더와 같은 Microsoft 365 데이터에 대한 액세스 권한을 개별 앱에 부여할 수 있습니다. 또한 전역 관리자 수준에서 이러한 앱을 승인하고 Azure AD에 앱을 등록하여 전체 회사에서 사용할 수 있도록 할 수 있습니다. Formore 정보는 [Microsoft 365](integrated-apps-and-azure-ads.md)관리자를 위한 통합 앱 및 Azure AD를 참조하세요.  <br/> Single [Sign-On도 참조합니다.](/azure/active-directory/manage-apps/what-is-single-sign-on)  <br/> |
|PowerApps  <br/> | Power Apps는 SharePoint 목록 및 기타 데이터 앱과 같은 기존 데이터 원본에 연결할 수 있는 모바일 장치에 초점을 맞추는 앱입니다. 자세한 [내용은 Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) 및 [PowerApps 페이지를](https://powerapps.microsoft.com/) 참조하세요.  <br/> |
   
## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 개요](microsoft-365-overview.md)