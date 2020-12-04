---
title: Microsoft 365 그룹을 만들 수 있는 사용자 관리
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Microsoft 365 그룹을 만들 수 있는 사용자를 제어하는 방법을 배워야 합니다.
ms.openlocfilehash: e3424a9cc916c9464478fbe4411bbbf7b971d989
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572624"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Microsoft 365 그룹을 만들 수 있는 사용자 관리

기본적으로 모든 사용자는 Microsoft 365 그룹을 만들 수 있습니다. 이는 사용자가 IT의 지원을 요청하지 않고도 공동 작업을 시작할 수 있도록 하여 권장되는 접근 방식입니다.

비즈니스에서 그룹을 만들 수 있는 사용자만 제한해야 하는 경우 이 문서의 절차에 따라 작업을 수행하면 됩니다. 그룹을 만들 수 있는 사용자가 제한될 경우 다음을 포함하여 액세스에 대한 그룹을 사용 하는 모든 서비스에 영향을 미치게 됩니다.

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- PowerBI(클래식)
- 웹용 프로젝트/로드맵

Microsoft 365 그룹 만들기를 특정 보안 그룹의 구성원으로 제한할 수 있습니다. 이를 구성하기 위해 다음을 Windows PowerShell. 이 문서에서는 필요한 단계를 단계로 진행합니다.

이 문서의 단계에서는 특정 역할의 구성원이 그룹을 만들 수 없습니다. Office 365 전역 관리자는 Microsoft 365 관리 센터, Planner, Teams, Exchange 및 SharePoint Online과 같은 모든 수단을 통해 그룹을 만들 수 있습니다. 다른 역할은 아래에 나열된 제한된 수단을 통해 그룹을 만들 수 있습니다.

- Exchange 관리자: Exchange 관리 센터, Azure AD
- 파트너 계층 1 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD
- 파트너 계층 2 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD
- 디렉터리 작성자: Azure AD
- SharePoint 관리자: SharePoint 관리 센터, Azure AD
- Teams 서비스 관리자: Teams 관리 센터, Azure AD
- 사용자 관리 관리자: Microsoft 365 관리 센터, Yammer, Azure AD

이러한 역할 중 하나의 구성원인 경우 제한된 사용자에 대해 Microsoft 365 그룹을 만든 다음 해당 사용자를 그룹의 소유자로 할당할 수 있습니다.

## <a name="licensing-requirements"></a>라이선스 요구 사항

그룹을 만드는 사용자 관리하려면 다음 사용자에게 할당된 Azure AD Premium 라이선스 또는 Azure AD Basic EDU 라이선스가 필요합니다.

- 이러한 그룹 만들기 설정을 구성하는 관리자
- 그룹을 만들 수 있는 보안 그룹의 구성원

> [!NOTE]
> Azure [라이선스를](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) 할당하는 방법에 대한 자세한 내용은 Azure Active Directory 포털에서 라이선스 할당 또는 제거를 참조하세요.

다음 사용자에게 할당된 Azure AD Premium 또는 Azure AD Basic EDU 라이선스가 필요하지 않습니다.

- Microsoft 365 그룹의 구성원이자 다른 그룹을 만들 수 없는 사용자입니다.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>1단계: Microsoft 365 그룹을 만들어야 하는 사용자에 대한 보안 그룹 만들기

조직에서 하나의 보안 그룹만 사용하여 그룹을 만들 수 있는 사용자만 제어할 수 있습니다. 그러나 다른 보안 그룹을 이 그룹의 구성원으로 중첩할 수 있습니다.

위에 나열된 역할의 관리자는 이 그룹의 구성원이 아니어도 그룹을 만들 수 있습니다.

> [!IMPORTANT]
> 보안 그룹을 사용하여 **security group** 그룹을 만들 수 있는 사용자만 제한해야 합니다. Microsoft 365 그룹 사용은 지원되지 않습니다.

1. 관리 센터에서 그룹 [페이지로 이동합니다.](https://admin.microsoft.com/adminportal/home#/groups)

2. 그룹 **추가를 클릭합니다.**

3. 그룹 **유형으로 보안을** 선택 합니다. 그룹의 이름을 기억하세요! 나중에 필요합니다.

4. 보안 그룹 설정을 완료하고, 해당 그룹에 그룹을 만들 수 있도록 하려는 사용자 또는 기타 보안 그룹을 추가합니다.

자세한 내용은 Microsoft [365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)관리 센터에서 보안 그룹 만들기, 편집 또는 삭제를 참조하세요.

## <a name="step-2-run-powershell-commands"></a>2단계: PowerShell 명령 실행

그룹 수준 게스트 액세스 설정을 변경하려면 [AzureAD(AzureAD(Azure Active Directory PowerShell for Graph)(모듈](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 이름 **AzureADPreview)의** 미리 보기 버전을 사용해야 합니다.

- 이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.

- AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.

- 미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.

아래 스크립트를 메모장 같은 텍스트 편집기나 [ISE의 텍스트 Windows PowerShell 복사합니다.](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)

만든 보안 그룹의 *\<SecurityGroupName\>* 이름으로 바 대체합니다. 예시:

`$GroupName = "Group Creators"`

파일을 다른 파일로 GroupCreators.ps1.

PowerShell 창에서 파일을 저장한 위치("CD"를 입력)로 <FileLocation> 이동합니다.

다음을 입력하여 스크립트를 실행합니다.

`.\GroupCreators.ps1`

메시지가 [표시될 때 관리자 계정으로](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) 로그인합니다.

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = $False"

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
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

스크립트의 마지막 줄에 업데이트된 설정이 표시됩니다.

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

앞으로 사용되는 보안 그룹을 변경하려는 경우 새 보안 그룹의 이름으로 스크립트를 다시 실행하면 됩니다.

그룹 만들기 제한을 해제하고 모든 사용자가 그룹을 만들 수 있도록 다시 허용하려는 경우 $GroupName ""로 설정하고 $AllowGroupCreation "True"로 설정하고 스크립트를 다시 실행합니다.

## <a name="step-3-verify-that-it-works"></a>3단계: 작동하는지 확인

변경 내용을 적용하는 데 30분 이상 걸릴 수 있습니다. 다음을 수행하여 새 설정을 확인할 수 있습니다.

1. 그룹을 만들 수 있는 능력이 없는 사용자의 사용자 계정으로 Microsoft 365에 로그인합니다. 즉, 사용자가 만든 보안 그룹의 구성원이나 관리자가 아닌 것입니다.

2. **Planner 타일을** 선택합니다.

3. Planner의 왼쪽 **탐색에서** 새 계획을 선택하여 계획을 만들 수 있습니다.

4. 계획 및 그룹 만들기를 사용하지 않도록 설정했다는 메시지가 표시됩니다.

보안 그룹의 구성원과 동일한 절차를 다시 시도하십시오.

> [!NOTE]
> 보안 그룹의 구성원이 그룹을 만들 수 없는 경우 해당 OWA 사서함 정책을 통해 차단되지 [않는지 검사합니다.](https://go.microsoft.com/fwlink/?linkid=852135)

## <a name="related-articles"></a>관련 문서

[Office 365 PowerShell 시작](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Azure Active Directory에서 셀프 서비스 그룹 관리 설정](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[그룹 설정 구성을 위한 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
