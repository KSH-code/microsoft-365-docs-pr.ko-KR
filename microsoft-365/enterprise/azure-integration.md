---
title: Azure와 통합된 Microsoft 365
ms.author: kvice
author: kelleyvice-msft
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
description: 암호 Microsoft 365 Single Sign-On을 원하는 경우 Azure AD와 통합합니다.
ms.openlocfilehash: de971ee857e955fc4ddb8a059da23974965e81e3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192869"
---
# <a name="azure-integration-with-microsoft-365"></a>Azure와 통합된 Microsoft 365

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 Azure AD(Azure Active Directory)를 사용하여 뒤에서 사용자 ID를 관리합니다. Microsoft 365 구독에는 무료 Azure AD 구독이 포함되어 있으므로 사용자 계정과 암호를 동기화하거나 Single Sign-On을 설정할 수 있도록 AD DS(Active Directory 도메인 서비스)를 통합할 수 있습니다. 고급 기능을 구입하여 계정을 더 효율적으로 관리할 수도 있습니다.
  
Azure AD는 통합 앱 관리와 같은 다른 기능도 제공합니다. 이러한 기능은 통합 앱 구독을 확장하고 사용자 지정하는 Microsoft 365 있습니다.
  
Azure AD 배포 어드바이저를 사용하여 Azure AD 배포 Microsoft 365 관리 센터 설치 및 구성 환경을 만들 수 있습니다(다음을 위해 로그인해야 Microsoft 365.

 - [Azure AD 커넥트 고문](https://aka.ms/aadconnectpwsync)
 - [AD FS 배포 어드바이저](https://aka.ms/adfsguidance)
 - [Azure AD 설정 가이드](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD 버전 및 Microsoft 365 관리

유료 구독이 있는 Microsoft 365 Azure AD 구독도 무료로 사용할 수 있습니다. Azure AD를 사용하여 사용자 및 그룹 계정을 만들고 관리할 수 있습니다. 이 구독을 활성화하려면 일회성 등록을 완료해야 합니다. 이후에 사용자 서비스에서 Azure AD에 액세스할 수 Microsoft 365 관리 센터. 

무료 Azure AD 구독을 등록하는 방법에 대한 지침은 무료 [Azure AD 구독 사용을 참조하세요.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) 등록하기 위해 azure.microsoft.com 직접 이동하지 말고 무료 Azure AD 구독과는 별개인 Microsoft Azure 평가판 또는 유료 구독이 Microsoft 365. 
  
무료 구독을 사용하면 사내의 로렉터와 동기화하고, Single Sign-On을 설정하고, Salesforce, DropBox 등의 서비스 응용 프로그램으로 많은 소프트웨어와 동기화할 수 있습니다.
  
향상된 AD DS 기능, 양방향 동기화 및 기타 관리 기능을 원하는 경우 무료 구독을 유료 프리미엄 구독으로 업그레이드할 수 있습니다. 자세한 내용은 에디션 [Azure Active Directory 참조합니다.](https://azure.microsoft.com/pricing/details/active-directory/)
  
Azure AD 및 Microsoft 365 대한 자세한 내용은 id [Microsoft 365 참조하세요.](about-microsoft-365-identity.md)
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>테넌트의 기능 Microsoft 365 확장

|**기능**|**설명**|
|:-----|:-----|
|통합 앱  <br/> |메일, 일정, 연락처, 사용자, 그룹, 파일 및 폴더와 같은 Microsoft 365 데이터에 대한 액세스 권한을 개별 앱에 부여할 수 있습니다. Azure AD DC 관리자 또는 전역 관리자  수준에서 이러한 앱을 승인하고 **Azure AD에** 앱을 등록하여 전체 회사에서 사용할 수 있도록 할 수도 있습니다. 자세한 내용은 관리자용 통합 앱 [및 Azure AD를 Microsoft 365 참조하세요.](integrated-apps-and-azure-ads.md)<br/> 자세한 내용은 [관리자 역할 정보](/microsoft-365/admin/add-users/about-admin-roles?)를 참조하세요. <br/> Single [Sign-On도 참조합니다.](/azure/active-directory/manage-apps/what-is-single-sign-on)  <br/> |
|Power Apps  <br/> | Power Apps 및 기타 데이터 앱과 같은 기존 데이터 원본에 연결할 수 있는 모바일 SharePoint 앱입니다. 자세한 [내용은 SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) 및 Power Apps 페이지에 대한 Power App 만들기를 참조하세요. [](https://powerapps.microsoft.com/)  <br/> |
   
## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 개요](microsoft-365-overview.md)
