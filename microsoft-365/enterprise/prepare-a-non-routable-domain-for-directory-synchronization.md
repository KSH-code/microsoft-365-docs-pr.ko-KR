---
title: '디렉터리 동기화를 위해 라우팅할 수 없는 도메인(예: .local 도메인) 준비'
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: 라우팅할 수 없는 도메인을 사용자 테넌트와 동기화하기 전에 라우팅할 수 없는 도메인이 있는 경우 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: 5b1ae0f11cc024dc4fa216ae67959da82b936e00
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60212800"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>디렉터리 동기화를 위해 라우팅할 수 없는 도메인(예: .local 도메인) 준비

On-premises 디렉터리를 Microsoft 365 Azure AD(Azure AD)에 확인된 도메인이 Azure Active Directory 합니다. 사내 AD DS(Active Directory 도메인 서비스) 도메인과 연결된 UPNS(사용자 계정 이름)만 동기화됩니다. 그러나 ".local"(예: billa@contoso.local)와 같은 라우팅할 수 없는 도메인을 포함하는 UPN은 .onmicrosoft.com 도메인(예: billa@contoso.onmicrosoft.com)에 동기화됩니다. 

현재 AD DS에서 사용자 계정에 대해 ".local" 도메인을 사용하는 경우 확인된 도메인(예: billa@contoso.com)을 사용하여 Microsoft 365 도메인과 올바르게 동기화하도록 변경하는 것이 좋습니다.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>".local" 도메인만 있는 경우 어떻게 하나요?

Ad DS를 커넥트 테넌트의 Azure AD 테넌트와 동기화하는 데 Azure AD Microsoft 365 사용할 수 있습니다. 자세한 내용은 [Azure AD에 On-premises ID 통합을 참조하세요.](/azure/architecture/reference-architectures/identity/azure-ad)
  
Azure AD 커넥트 사용자의 UPN 및 암호를 동기화하여 사용자가 해당 사용자가 사용하는 동일한 자격 증명으로 로그인할 수 있습니다. 그러나 Azure AD 커넥트 사용자가 확인한 도메인에만 사용자를 Microsoft 365. 즉, ID가 Azure AD에서 관리되는 Microsoft 365 Azure AD에서도 도메인이 확인됩니다. 즉, 도메인은 유효한 인터넷 도메인(예: .com, .org, .net, .us)으로 구성해야 합니다. 내부 AD DS에서 라우팅할 수 없는 도메인(예: ".local")만 사용하는 경우 이 도메인이 Microsoft 365 도메인에 대해 확인된 도메인과 일치할 수 없습니다. 온-프레미스 AD DS에서 기본 도메인을 변경하거나 하나 이상의 UPN 접미사를 추가하여 이 문제를 해결할 수 있습니다.
  
### <a name="change-your-primary-domain"></a>기본 도메인 변경

기본 도메인을 기본 도메인에서 확인한 도메인으로 Microsoft 365 예로 contoso.com. 그런 다음 contoso.local 도메인이 있는 모든 사용자가 contoso.com. 그러나 이 프로세스는 매우 관련이 있으며, 다음 섹션에서는 보다 쉬운 해결 방법도 설명합니다.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>UPN 접미사 추가 및 사용자 업데이트

AD DS에 새 UPN 접미사 또는 접미어를 등록하여 확인한 도메인(또는 도메인)과 일치하면 ".local" 문제를 해결할 수 Microsoft 365. 예를 들어 새 접미사 등록 후 사용자 계정이 새 도메인 이름으로 대체하도록 사용자 UPNS를 업데이트하여 사용자 계정이 billa@contoso.com.
  
확인된 도메인을 사용하기 위해 UPNS를 업데이트하고 나면 프레미스 AD DS를 도메인과 동기화할 Microsoft 365.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>1단계: 새 UPN 접미사 추가**
  
1. AD DS 도메인 컨트롤러의 서버 관리자에서 **도구** \> **Active Directory 도메인 및 트러스트 를 선택 합니다.**
    
    **또는 사용자가 없는 경우 Windows Server 2012**
    
    Windows **+ R을** 눌러 실행  대화 상자를 연 다음 Domain.msc에 입력한 다음 확인 을 **선택 합니다.**
    
    ![Active Directory 도메인 및 트러스트를 선택하십시오.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. Active **Directory 도메인 및 트러스트** 창에서 Active Directory 도메인 및 **트러스트** 를 마우스 오른쪽 단추로 클릭한 다음 속성을 **선택합니다.**
    
    ![Active Directory 도메인 및 트러스트를 마우스 오른쪽 단추로 클릭하고 속성을 클릭합니다.](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. **UPN 접미사** 탭의 대체 **UPN** 접미사 상자에 새 UPN 접미사 또는 접미사를  입력한 다음 적용 추가를 \> **선택합니다.**
    
    ![새 UPN 접미사 추가](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    **접미사** 추가가 완료되면 확인을 클릭합니다. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>2단계: 기존 사용자의 UPN 접미사 변경
  
1. AD DS 도메인 컨트롤러의 서버 관리자에서 **도구** Active Directory 사용자 및 \> **컴퓨터를 선택 합니다.**
    
    **또는 사용자가 없는 경우 Windows Server 2012**
    
    Windows **+ R을** 눌러 실행  대화 상자를 연 다음 Dsa.msc에 입력한 다음 확인을 **클릭합니다.**
    
2. 사용자를 선택하고 마우스 오른쪽 단추로 클릭한 다음 속성을 **선택합니다.**
    
3. 계정 **탭의** UPN 접미사 드롭다운 목록에서 새 UPN 접미사, 확인을 **선택합니다.**
    
    ![사용자에 대한 새 UPN 접미사 추가](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. 모든 사용자에 대해 다음 단계를 완료합니다.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>PowerShell을 사용하여 모든 사용자의 UPN 접미사 변경

업데이트할 사용자 계정이 많은 경우 PowerShell을 사용하는 것이 더 쉽습니다. 다음 예제에서는 [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) 및 [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) cmdlet을 사용하여 모든 contoso.local 접미사는 AD DS에서 contoso.com 변경합니다. 

예를 들어 다음 PowerShell 명령을 실행하여 모든 contoso.local 접미사를 업데이트하여 contoso.com.
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

AD [DS에서](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) Windows PowerShell 자세한 내용은 Active Directory Windows PowerShell 모듈을 참조하세요.