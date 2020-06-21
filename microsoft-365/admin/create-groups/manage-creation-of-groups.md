---
title: 그룹을 만들 수 있는 사용자 관리
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Microsoft 365 그룹을 만들 수 있는 사용자를 제어 하는 방법을 알아봅니다.
ms.openlocfilehash: b64e7ac96c5a0e38583d00f8a61bd47c5304cf45
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761677"
---
# <a name="manage-who-can-create-groups"></a>그룹을 만들 수 있는 사용자 관리

  
사용자가 Microsoft 365 그룹을 쉽게 만들 수 있으므로 다른 사람을 대신 하 여이를 만드는 요청을 많이 받게 하지 못합니다. 그러나 비즈니스에 따라 그룹을 만들 수 있는 사용자를 제어하고자 할 수 있습니다.
  
이 문서에서는 다음과 같은 그룹을 사용 하는 모든 Microsoft 365 서비스에서 그룹을 만드는 기능을 사용 하지 않도록 설정 하는 방법을 설명 합니다.
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream

- Planner
    
- PowerBI

- 웹 및 로드맵 용 프로젝트
    
Microsoft 365 그룹 만들기를 특정 보안 그룹의 구성원으로 제한할 수 있습니다. 이를 구성 하기 위해 Windows PowerShell을 사용 합니다. 이 문서에서는 필요한 단계를 안내 합니다.
  
이 문서에서 설명 하는 단계에서는 특정 역할의 구성원이 그룹을 만들 수 없습니다. 전역 관리자는 Microsoft 365 관리 센터, Planner, 팀, Exchange, SharePoint Online 등의 모든 방법을 통해 그룹을 만들 수 있습니다. 다른 역할은 제한 된 방법 (아래 참조)을 통해 그룹을 만들 수 있습니다.
        
  - Exchange 관리자: Exchange 관리 센터, Azure AD
    
  - 파트너 계층 1 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD
    
  - 파트너 계층 2 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD
    
  - 디렉터리 작성자: Azure AD

  - SharePoint 관리자: SharePoint 관리 센터, Azure AD
  
  - 팀 서비스 관리자: 팀 관리 센터, Azure AD
  
  - 사용자 관리 관리자: Microsoft 365 관리 센터, Yammer, Azure AD
     
이러한 역할 중 하나의 구성원 인 경우 제한 된 사용자에 대 한 Microsoft 365 그룹을 만든 다음 사용자를 그룹 소유자로 할당할 수 있습니다. 이 역할이 있는 사용자는 생성을 방해할 수 있는 PowerShell 설정에 관계 없이 Yammer에서 연결 된 그룹을 만들 수 있습니다.

## <a name="licensing-requirements"></a>라이선스 요구 사항

그룹을 만드는 사용자를 관리 하기 위해 다음 사용자에 게 할당 된 Azure AD Premium 라이선스 또는 Azure AD Basic .EDU 라이선스가 필요 합니다.

- 이러한 그룹 만들기 설정을 구성 하는 관리자
- 그룹을 만들 수 있는 보안 그룹의 구성원

> [!NOTE]
> Azure 라이선스를 할당 하는 방법에 대 한 자세한 내용은 [Azure Active Directory 포털에서 라이선스 할당 또는 제거](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) 를 참조 하세요.

다음 사용자는 Azure AD Premium 또는 Azure AD Basic .EDU 라이선스를 할당할 필요가 없습니다.

- Microsoft 365 그룹의 구성원이 고 다른 그룹을 만들 수 없는 사용자입니다.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>1 단계: Microsoft 365 그룹을 만들어야 하는 사용자에 대 한 보안 그룹 만들기

조직의 보안 그룹을 하나만 사용 하 여 그룹을 만들 수 있는 사용자를 제어할 수 있습니다. 그러나 다른 보안 그룹을 이 그룹의 구성원으로 중첩할 수 있습니다. 예를 들어 그룹 만들기 허용이라는 그룹이 지정된 보안 그룹이고, Microsoft 플래너 사용자 및 Exchange Online 사용자라는 그룹이 해당 그룹의 구성원입니다.

위에 나열 된 역할의 관리자는 그룹을 만들 수 있는 기능을 유지 하므로이 그룹의 구성원 일 필요는 없습니다.

> [!IMPORTANT]
> **보안 그룹** 을 사용 하 여 그룹을 만들 수 있는 사용자를 제한 해야 합니다. Microsoft 365 그룹을 사용 하려고 하면 구성원이 보안 그룹을 확인 하므로 SharePoint에서 그룹을 만들 수 없습니다. 
    
1. 관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.

2. **그룹 추가**를 클릭 합니다.

3. 그룹 유형으로 **보안** 을 선택 합니다. 그룹의 이름을 기억하세요! 나중에 필요합니다.
  
4. 조직에서 그룹을 만들 수 있도록 하려는 사용자 또는 다른 보안 그룹을 추가 하 여 보안 그룹 설정을 완료 합니다.
    
자세한 내용은 [Microsoft 365 관리 센터에서 보안 그룹 만들기, 편집 또는 삭제](../email/create-edit-or-delete-a-security-group.md)를 참조 하세요.
 
## <a name="step-2-run-powershell-commands"></a>2단계: PowerShell 명령 실행

그룹 수준 게스트 액세스 설정을 변경 하려면 AzureAD (module name **AzureADPreview**)의 [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 의 preview 버전을 사용 해야 합니다.

- 이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.

- AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.

- 미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.



아래 스크립트를 메모장과 같은 텍스트 편집기 또는 [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)에 복사 합니다.

*\<SecurityGroupName\>* 만든 보안 그룹의 이름으로 대체 합니다. 예시:

`$GroupName = "Group Creators"`

GroupCreators.ps1으로 파일을 저장 합니다. 

PowerShell 창에서 파일을 저장 한 위치로 이동 합니다 ("CD <FileLocation> " 형식).

다음 명령을 입력 하 여 스크립트를 실행 합니다.

`.\GroupCreators.ps1`

메시지가 표시 되 면 [관리자 계정으로 로그인](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) 합니다.

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

스크립트의 마지막 줄에 업데이트 된 설정이 표시 됩니다.

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

나중에 사용 되는 보안 그룹을 변경 하려는 경우 새 보안 그룹의 이름으로 스크립트를 다시 실행할 수 있습니다.

그룹 만들기 제한을 해제 하 고 모든 사용자가 그룹을 만들 수 있도록 하려면 $GroupName를 ""로 설정 하 고 $AllowGroupCreation "True"로 설정한 후 스크립트를 다시 실행 합니다.
    
## <a name="step-3-verify-that-it-works"></a>3단계: 작동하는지 확인

변경 내용이 적용 되려면 30 분 이상이 소요 될 수 있습니다. 다음을 수행 하 여 새 설정을 확인할 수 있습니다.

1. 그룹을 만들 수 없는 사용자 계정을 사용 하 여 로그인 합니다. 즉, 사용자가 만들었거나 관리자가 만든 보안 그룹의 구성원이 아닙니다.
    
2. **Planner** 타일을 선택 합니다. 
    
3. Planner의 왼쪽 탐색 창에서 **새 계획** 을 선택 하 여 계획을 만듭니다. 
  
4. 계획 및 그룹 만들기가 사용 하지 않도록 설정 된다는 메시지가 표시 됩니다.

보안 그룹의 구성원을 사용 하 여 동일한 절차를 다시 시도 합니다.

> [!NOTE]
> 보안 그룹의 구성원이 그룹을 만들 수 없는 경우 해당 구성원은 해당 [OWA 사서함 정책을](https://go.microsoft.com/fwlink/?linkid=852135)통해 차단 되지 않아야 합니다.
    
## <a name="related-articles"></a>관련 문서

[Office 365 PowerShell 시작](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Azure Active Directory에서 셀프 서비스 그룹 관리 설정](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[그룹 설정 구성을 위한 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
