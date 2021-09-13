---
title: 사용자 Microsoft 365 관리
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
- admindeeplinkMAC
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 사용자 계정을 관리하는 Microsoft 365 대해 자세히 알아보아야 합니다.
ms.openlocfilehash: 7a21ed12101f3aaa8323c62d2c15ae30860cd041
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221035"
---
# <a name="manage-microsoft-365-user-accounts"></a>사용자 Microsoft 365 관리

구성에 Microsoft 365 여러 가지 방법으로 사용자 계정을 관리할 수 있습니다. AD [DS(Active](../admin/add-users/index.yml)Directory 도메인 서비스) 또는 Azure AD(Active Directory 도메인 서비스) Microsoft 365 관리 센터 또는 Azure AD(Active Directory 도메인 서비스) Azure Active Directory 사용자 계정을 관리할 수 있습니다. [](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md) 

사용자 계정을 구입하는 Microsoft 365 즉시 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a> Microsoft 365 관리 센터 및 PowerShell을 사용하여 계정을 관리할 수 있습니다. 클라우드 ID를 관리할 때 조직의 모든 사용자에게 별도의 사용자 계정 이름과 암호가 있습니다. 사내 인프라와 통합하고 사용자 계정이 Microsoft 365 동기화하려는 경우 Azure AD 커넥트 사용하여 SSO(Single Sign-On) 기능에 대한 ID 및 암호 동기화를 제공할 수 있습니다.
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>사용자 계정을 관리하는 위치 및 방법 계획

사용자 계정을 관리하는 위치 및 방법은 사용자 계정의 ID 모델에 따라 Microsoft 365. 두 가지 전체 모델은 클라우드 전용 및 하이브리드입니다.
  
### <a name="cloud-only"></a>클라우드 전용

에서 사용자를 만들고 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터.</a> PowerShell 또는 Azure AD 관리 센터를 사용할 수도 있습니다. 
    
### <a name="hybrid"></a>하이브리드

사용자 계정은 AD DS의 Microsoft 365 동기화되어 있으므로 사용자 계정을 관리하려면 사내 AD DS 도구를 사용해야 합니다. 
    
## <a name="managing-accounts"></a>계정 관리

조직에서 계정을 만들고 관리하는 방법을 결정하면 다음 요구 사항을 고려하세요.
  
- 디렉터리 동기화 소프트웨어와 AD DS 간에 ID를 연결하기 위해 디렉터리 동기화 Microsoft 365 설치해야 합니다.
    
- SSO 옵션을 비롯한 모든 디렉터리 동기화 옵션을 사용하려면 AD DS 특성이 표준을 충족해야 합니다. 디렉터리에서 사용되는 특성 및 필요한 정리(있는 경우)의 구체적인 설명은 [Prepare for directory synchronization to Microsoft 365.](prepare-for-directory-synchronization.md) 
    
- 계정 만들기 방법을 Microsoft 365.
    
다음 표에는 다양한 계정 관리 도구가 나열됩니다.
    
|도구|참고|
|:-----|:-----|
|Microsoft 365 관리 센터  <br/> |[개별적으로 또는 대량으로 사용자 추가](../admin/add-users/add-users.md) <br/>  사용자 계정을 추가하고 변경할 수 있는 간단한 웹 인터페이스를 제공합니다.  <br/>  디렉터리 동기화를 사용하도록 설정한 경우(위치 및 라이선스 할당을 설정할 수 있는 경우) 사용자를 변경하는 데 사용할 수 없습니다.  <br/>  SSO 옵션과 함께 사용할 수 없습니다.  <br/> |
|Windows PowerShell  <br/> |[사용자 Microsoft 365 관리 Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  사용자 일괄 스크립트를 사용하여 대량 사용자를 추가할 Windows PowerShell 있습니다.  <br/>  계정 생성 방법에 관계없이 계정에 위치 및 라이선스를 할당하는 데 사용할 수 있습니다.  <br/> |
|대량 가져오기  <br/> |[동시에 여러 사용자 추가](add-several-users-at-the-same-time.md) <br/>  CSV 파일을 가져와서 사용자 그룹을 추가할 수 Microsoft 365.  <br/>  SSO 옵션과 함께 사용할 수 없습니다.  <br/> |
|Azure AD  <br/> |Azure AD 무료 버전과 구독을 Microsoft 365 있습니다. 클라우드 사용자를 위한 셀프 서비스 암호 재설정, 무료 에디션을 사용하여 로그인 및 액세스 패널 페이지 사용자 지정과 같은 기능을 수행할 수 있습니다. 향상된 기능을 사용하려면 기본 버전, 기본 버전 또는 Azure AD Premium P1 또는 Azure AD Premium P2. 지원되는 기능 [목록은 Azure AD](/azure/active-directory/fundamentals/active-directory-whatis) 에디션을 참조하세요.  <br/> |
|디렉터리 동기화  <br/> |[Azure AD와 사내 ID 통합](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  암호 동기화를 사용할지 또는 사용하지 않고 디렉터리 동기화를 위해 Azure AD 커넥트 [설정과 함께 사용합니다.](/azure/active-directory/hybrid/how-to-connect-install-express)  <br/>  여러 포리스트 및 SSO 옵션의 경우 Azure AD 2013의 사용자 지정 [설치를 커넥트.](/azure/active-directory/hybrid/how-to-connect-install-custom)  <br/>  SSO를 사용하도록 설정하는 데 필요한 인프라를 제공합니다.  <br/>  단계적 마이그레이션 및 하이브리드 시나리오와 같은 많은 하이브리드 시나리오에 Exchange  <br/>  AD DS에서 보안 및 메일 사용 가능 그룹을 동기화합니다.  <br/> |
|||
   
- 사용자 계정을 추가하려는 방법에 관계없이 Microsoft 365 할당, 위치 지정 등의 여러 계정 기능을 관리해야 합니다. 이러한 기능은 셸에서 장기적으로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a> 관리하거나 Microsoft 365 관리 센터 [PowerShell을](./create-user-accounts-with-microsoft-365-powershell.md)사용하여 사용자 계정을 만들 수도 있습니다.
    
    관리 센터를 통해 모든 사용자를 추가 및 관리하기로 선택한 경우 위치를 지정하고 라이선스를 할당하는 동시에 새 계정을 만드는 Microsoft 365 합니다. 따라서 계획이 많이 필요하지 않습니다.
    
    > [!IMPORTANT]
    > Microsoft 365 라이선스를 할당하지 않고(예: SharePoint Online에) 계정을 만들면 계정 소유자가 Microsoft 365 센터를 볼 수 있지만 회사 구독 내의 서비스에는 액세스할 수 없습니다. 위치와 라이선스를 할당하면 계정이 할당한 서비스 또는 서비스에 복제됩니다. 사용자는 계정에 로그인하여 할당한 서비스를 사용할 수 있습니다. 
  
## <a name="see-also"></a>참고 항목

[Microsoft 365 관리 센터](../admin/add-users/index.yml)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)