---
title: Microsoft 365 사용자 계정 관리
ms.author: josephd
author: JoeDavies-MSFT
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
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 사용자 계정을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327762"
---
# <a name="manage-microsoft-365-user-accounts"></a>Microsoft 365 사용자 계정 관리

구성에 따라 다양 한 방식으로 Microsoft 365 사용자 계정을 관리할 수 있습니다. [Microsoft 365 관리 센터](https://docs.microsoft.com/microsoft-365/admin/add-users/), [POWERSHELL](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), AD DS (active directory 도메인 서비스) 또는 Azure ad (active directory) 관리 포털에서 사용자 계정을 관리할 수 있습니다. 

Microsoft 365을 구입 하는 즉시 Microsoft 365 관리 센터 및 PowerShell을 사용 하 여 계정을 관리할 수 있습니다. 클라우드 id를 관리할 때 조직의 모든 사용자에 게는 별도의 사용자 계정 이름과 암호가 있습니다. 온-프레미스 인프라와 통합 하 고 사용자 계정을 Microsoft 365와 동기화 하려면 Azure AD Connect를 사용 하 여 SSO (single sign-on) 기능에 대 한 id와 암호를 동기화 할 수 있습니다.
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>사용자 계정을 관리 하는 위치 및 방법 계획

사용자 계정을 관리할 수 있는 위치와 방법은 Microsoft 365에 사용할 id 모델에 따라 달라 집니다. 전체 모델은 클라우드 전용 모델과 하이브리드입니다.
  
### <a name="cloud-only"></a>클라우드 전용

Microsoft 365 관리 센터에서 사용자를 만들고 관리 합니다. PowerShell 또는 Azure AD 관리 센터를 사용할 수도 있습니다. 
    
### <a name="hybrid"></a>하이브리드

사용자 계정은 AD DS에서 Microsoft 365와 동기화 되므로, 온-프레미스 AD DS 도구를 사용 하 여 사용자 계정을 관리 해야 합니다. 
    
## <a name="managing-accounts"></a>계정 관리

조직에서 계정을 만들고 관리 하는 방법을 결정할 때는 다음 요구 사항을 고려 하세요.
  
- Microsoft 365와 AD DS 간에 id를 연결 하려면 온-프레미스 환경 내의 서버에 디렉터리 동기화 소프트웨어를 설치 해야 합니다.
    
- SSO 옵션을 비롯 한 디렉터리 동기화 옵션을 사용 하려면 AD DS 특성이 표준을 충족 해야 합니다. 디렉터리에서 사용 되는 특성 및 필요한 정리 (있는 경우)에 대 한 [자세한 내용은 Prepare to directory synchronization To Microsoft 365을](prepare-for-directory-synchronization.md)참조 하십시오. 
    
- Microsoft 365 계정을 만드는 방법을 계획 합니다.
    
다음 표에서는 다양 한 계정 관리 도구를 보여 줍니다.
    
|도구|Notes|
|:-----|:-----|
|Microsoft 365 관리 센터  <br/> |[개별적으로 또는 대량으로 사용자 추가](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  사용자 계정을 추가 및 변경할 수 있는 간단한 웹 인터페이스를 제공 합니다.  <br/>  디렉터리 동기화가 사용 하도록 설정 된 경우 (위치 및 라이선스 할당을 설정할 수 있음) 사용자를 변경 하는 데 사용할 수 없습니다.  <br/>  SSO 옵션과 함께 사용할 수 없습니다.  <br/> |
|Windows PowerShell  <br/> |[Windows PowerShell을 사용 하 여 Microsoft 365 관리](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Windows PowerShell 스크립트를 사용 하 여 사용자를 대량 사용자에 게 추가할 수 있습니다.  <br/>  계정을 만드는 방법에 관계 없이 계정에 위치 및 라이선스를 할당 하는 데 사용할 수 있습니다.  <br/> |
|대량 가져오기  <br/> |[동시에 여러 사용자 추가](add-several-users-at-the-same-time.md) <br/>  CSV 파일을 가져와서 Microsoft 365에 사용자 그룹을 추가할 수 있도록 허용 합니다.  <br/>  SSO 옵션과 함께 사용할 수 없습니다.  <br/> |
|Azure AD  <br/> |Microsoft 365 구독을 사용 하 여 무료 버전의 Azure AD를 가져올 수 있습니다. 클라우드 사용자에 대해 셀프 서비스 암호 재설정 및 무료 버전을 사용 하 여 로그인 및 액세스 패널 페이지의 사용자 지정과 같은 기능을 수행할 수 있습니다. 향상 된 기능을 얻으려면 기본 에디션, Azure AD Premium P1 또는 Azure AD Premium P2로 업그레이드 하면 됩니다. 지원 되는 기능 목록은 [AZURE AD edition](https://go.microsoft.com/fwlink/p/?LinkId=698465) 를 참조 하세요.  <br/> |
|디렉터리 동기화  <br/> |[Azure AD와 온-프레미스 id 통합](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  암호 동기화 여부와 관계 없이 디렉터리 동기화의 경우 [빠른 설정으로 AZURE AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698537)를 사용 합니다.  <br/>  여러 포리스트와 SSO 옵션에 대해 [AZURE AD Connect의 사용자 지정 설치](https://go.microsoft.com/fwlink/p/?LinkId=698430)를 사용 합니다.  <br/>  SSO를 사용 하도록 설정 하는 데 필요한 인프라를 제공 합니다.  <br/>  미리 구성 된 마이그레이션 및 하이브리드 Exchange와 같은 다양 한 하이브리드 시나리오에 필요  <br/>  AD DS에서 보안 및 메일 사용이 가능한 그룹을 동기화 합니다.  <br/> |
|||
   
- 사용자 계정을 Microsoft 365에 추가 하려는 방법에 관계 없이 라이선스 할당, 위치 지정 등 여러 가지 계정 기능을 관리 해야 합니다. 이러한 기능은 Microsoft 365 관리 센터에서 장기간 관리할 수 있거나 [PowerShell을 사용 하 여 사용자 계정을 만들](https://go.microsoft.com/fwlink/p/?LinkId=717083)수도 있습니다.
    
    관리 센터를 통해 모든 사용자를 추가 하 고 관리 하는 경우 Microsoft 365 계정을 만드는 것과 동시에 위치를 지정 하 고 라이선스를 할당 합니다. 따라서 계획은 그다지 많지 않아도 됩니다.
    
    > [!IMPORTANT]
    > 라이선스 (예: SharePoint Online에)를 할당 하지 않고 Microsoft 365에서 계정을 만드는 것은 계정 소유자가 Microsoft 365 center를 볼 수 있지만 회사 구독 내의 어떤 서비스에도 액세스 하지 못하는 것을 의미 합니다. 위치 및 라이선스를 할당 한 후에는 할당 한 서비스에 계정이 복제 됩니다. 사용자는 자신의 계정에 로그인 하 고 할당 한 서비스를 사용할 수 있습니다. 
  
## <a name="see-also"></a>참고 항목

[Microsoft 365 관리 센터](https://docs.microsoft.com/microsoft-365/admin/add-users)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
