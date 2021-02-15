---
title: '디렉터리 동기화를 위해 라우팅할 수 없는 도메인(예: .local 도메인) 준비'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Microsoft 365 테넌트와 동기화하기 전에 라우팅할 수 없는 도메인이 있는 경우, 해당 도메인을 Microsoft 365 테넌트와 동기화하기 전에 어떻게 해야 할지 배워야 합니다.
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780335"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>디렉터리 동기화를 위해 라우팅할 수 없는 도메인(예: .local 도메인) 준비

Microsoft 365와 Microsoft 프레미스 디렉터리를 동기화하는 경우 Azure AD(Azure Active Directory)에 확인된 도메인이 있습니다. ON-프레미스 AD DS(Active Directory 도메인 서비스) 도메인과 연결된 UPNS(사용자 계정 이름)만 동기화됩니다. 그러나 라우팅할 수 없는 도메인(예: billa@contoso.local)을 포함하는 UPN은 .onmicrosoft.com 도메인(예: billa@contoso.onmicrosoft.com)에 동기화됩니다. 

현재 AD DS에서 사용자 계정에 대해 ".local" 도메인을 사용하는 경우 Microsoft 365 도메인과 제대로 동기화하기 위해 확인된 도메인(예: billa@contoso.com)을 사용하여 도메인을 변경하는 것이 좋습니다.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>".local" 도메인만 있는 경우 어떻게 하나요?

Azure AD Connect를 사용하여 AD DS를 Microsoft 365 테넌트의 Azure AD 테넌트와 동기화합니다. 자세한 내용은 Azure AD에 대한 [On-premises ID 통합을 참조하세요.](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad)
  
Azure AD Connect는 사용자의 UPN 및 암호를 동기화하여 사용자가 해당 사용자가 사용하는 동일한 자격 증명을 사용하여 로그인할 수 있도록 합니다. 그러나 Azure AD Connect는 사용자를 Microsoft 365에서 확인된 도메인과만 동기화합니다. 즉, Microsoft 365 ID는 Azure AD에서 관리하기 때문에 Azure AD에서도 도메인이 확인됩니다. 즉, 도메인은 유효한 인터넷 도메인(예: .com, .org, .net, .us)입니다. 내부 AD DS에서 라우팅할 수 없는 도메인(예: ".local")만 사용하는 경우 Microsoft 365 테넌트에 대해 확인된 도메인과 일치할 수 없습니다. 온-프레미스 AD DS에서 기본 도메인을 변경하거나 하나 이상의 UPN 접미사를 추가하여 이 문제를 해결할 수 있습니다.
  
### <a name="change-your-primary-domain"></a>기본 도메인 변경

Microsoft 365에서 확인한 도메인으로 기본 도메인을 변경합니다(예: contoso.com. 그런 다음 contoso.local 도메인이 있는 모든 사용자가 contoso.com. 그러나 이 프로세스는 매우 관련이 있으며, 다음 섹션에서는 보다 쉬운 해결 방법도 설명합니다.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>UPN 접미사 추가 및 사용자 업데이트

AD DS에 새 UPN 접미사 또는 접미어를 Microsoft 365에서 확인한 도메인과 일치하게 등록하면 ".local" 문제를 해결할 수 있습니다. 새 접미사는 등록한 후 사용자 UPNS를 업데이트하여 ".local"을 새 도메인 이름으로 바꾸어 사용자 계정이 새 접미사처럼 billa@contoso.com.
  
확인된 도메인을 사용하기 위해 UPNS를 업데이트한 후 Microsoft 365와의 동기화를 시작할 준비가 된 것입니다.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>1단계: 새 UPN 접미사 추가**
  
1. AD DS 도메인 컨트롤러의 서버 관리자에서  \> **도구 Active Directory 도메인 및 트러스트를 선택하십시오.**
    
    **또는 사용자가 없는 경우 Windows Server 2012**
    
    **Windows 키 + R을 눌러** 실행 대화 상자를 연 다음 Domain.msc에 입력한 다음 확인을 선택 **합니다.** 
    
    ![Active Directory 도메인 및 트러스트 선택](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. Active **Directory 도메인 및** 트러스트 창에서 Active Directory 도메인 및 **트러스트를** 마우스 오른쪽 단추로 클릭한 다음 속성을 **선택합니다.**
    
    ![Active Directory 도메인 및 트러스트 마우스 오른쪽 단추를 클릭하고 속성 선택](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. UPN 접미사 탭의 대체  **UPN** 접미사 상자에 새 UPN 접미사 또는 접미사를 입력한 다음 적용을  \> **선택합니다.**
    
    ![새 UPN 접미사 추가](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    **접미사** 추가가 완료되면 확인을 선택 합니다. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>2단계: 기존 사용자의 UPN 접미사 변경
  
1. AD DS 도메인 컨트롤러의 서버 관리자에서 도구 Active Directory 사용자 및  \> **컴퓨터를 선택 합니다.**
    
    **또는 사용자가 없는 경우 Windows Server 2012**
    
    **Windows 키 + R을 눌러** 실행 대화 상자를 연 다음 Dsa.msc에 입력한 다음  **확인을 클릭합니다.**
    
2. 사용자를 선택하고 마우스 오른쪽 단추를 클릭한 다음 속성을 **선택합니다.**
    
3. 계정 **탭의** UPN 접미사 드롭다운 목록에서 새 UPN 접미사를 선택한 다음 확인을 **선택합니다.**
    
    ![사용자에 대한 새 UPN 접미사 추가](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. 모든 사용자에 대해 다음 단계를 완료합니다.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>PowerShell을 사용하여 모든 사용자의 UPN 접미사 변경

업데이트할 사용자 계정이 많은 경우 PowerShell을 사용하는 것이 더 쉽습니다. 다음 예제에서는 [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) 및 [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) cmdlet을 사용하여 모든 contoso.local 접미사는 AD DS에서 contoso.com 변경합니다. 

예를 들어 다음 PowerShell 명령을 실행하여 모든 contoso.local 접미어를 업데이트하여 contoso.com.
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

AD [DS에서](https://go.microsoft.com/fwlink/p/?LinkId=624314) Windows PowerShell 자세한 내용은 Active Directory Windows PowerShell 모듈을 참조하세요. 

