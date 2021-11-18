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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
recommendations: false
description: 그룹을 만들 수 있는 사용자를 제어하는 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: cea1529071cce92e2b6fad74d4946d1e4c7f3594
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064322"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Microsoft 365 그룹을 만들 수 있는 사용자 관리

기본적으로 모든 사용자는 그룹을 만들 Microsoft 365 있습니다. 이 방법은 사용자가 IT의 지원 없이 공동 작업을 시작할 수 있도록 하여 권장되는 접근 방식입니다.

회사에서 그룹을 만들 수 있는 사용자만 제한해야 하는 경우 Microsoft 365 그룹 만들기를 특정 Microsoft 365 그룹 또는 보안 그룹의 구성원으로 제한할 수 있습니다.

비즈니스 표준을 준수하지 않는 팀 또는 그룹을 만드는 사용자가 우려되는 경우 사용자에게 교육 과정을 완료한 다음 허용된 사용자 그룹에 추가하도록 요구하는 것이 고려됩니다.

그룹을 만들 수 있는 사용자 수를 제한하면 다음을 비롯한 액세스에 대한 그룹을 사용 하는 모든 서비스에 영향을 미치게 됩니다.

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI(클래식)
- Project/로드맵에 대한 자세한

이 문서의 단계에서는 특정 역할의 구성원이 그룹을 만들 수 없습니다. Office 365 전역 관리자는 온라인에서 Microsoft 365 관리 센터, Planner, Exchange 및 SharePoint 만들 수 있습니다. 다른 역할은 아래에 나열된 제한된 수단을 통해 그룹을 만들 수 있습니다.

- Exchange 관리자: Exchange 관리 센터, Azure AD
- 파트너 계층 1 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD
- 파트너 계층 2 지원: Microsoft 365 관리 센터, Exchange 관리 센터, Azure AD
- 디렉터리 작성자: Azure AD
- SharePoint 관리자: SharePoint 관리 센터, Azure AD
- Teams 서비스 관리자: Teams 관리 센터, Azure AD
- 사용자 관리자: Microsoft 365 관리 센터, Azure AD

이러한 역할 중 하나의 구성원인 경우 제한된 사용자에 대해 Microsoft 365 그룹을 만든 다음 사용자를 그룹의 소유자로 할당할 수 있습니다.

## <a name="licensing-requirements"></a>라이선스 요구사항

그룹을 만드는 사용자 관리를 위해 다음 사용자에게 할당된 Azure AD Premium Azure AD Basic EDU 라이선스가 필요합니다.

- 이러한 그룹 만들기 설정을 구성하는 관리자
- 그룹을 만들 수 있는 그룹의 구성원

> [!NOTE]
> Azure [라이선스를 할당하는 방법에](/azure/active-directory/fundamentals/license-users-groups) 대한 자세한 내용은 Azure Active Directory 포털에서 라이선스 할당 또는 제거를 참조하세요.

다음 사용자에게 할당된 Azure AD Premium Azure AD Basic EDU 라이선스가 필요하지 않습니다.

- Microsoft 365 그룹의 구성원이자 다른 그룹을 만들 수 없는 사용자입니다.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>1단계: 그룹 그룹을 만들어야 하는 사용자를 위한 Microsoft 365 만들기

조직에서 그룹을 만들 수 있는 그룹을 제어하는 데는 하나의 그룹만 사용할 수 있습니다. 그러나 다른 그룹을 이 그룹의 구성원으로 중첩할 수 있습니다.

위에 나열된 역할의 관리자는 이 그룹의 구성원이 아니어도 그룹을 만들 수 있습니다.

1. 관리 센터에서 그룹 [페이지로 이동합니다.](https://admin.microsoft.com/adminportal/home#/groups)

2. 그룹 **추가를 클릭합니다.**

3. 원하는 그룹 유형을 선택 합니다. 그룹의 이름을 기억하세요! 나중에 필요합니다.

4. 그룹 설정을 완료하고, 그룹에서 그룹을 만들 수 있도록 하려는 사용자 또는 다른 그룹을 추가합니다.

자세한 지침은 에서 보안 그룹 만들기, 편집 또는 [삭제를 Microsoft 365 관리 센터.](../admin/email/create-edit-or-delete-a-security-group.md)

## <a name="step-2-run-powershell-commands"></a>2단계: PowerShell 명령 실행

그룹 수준 게스트 액세스 설정을 변경하려면 Azure Active Directory [PowerShell for Graph(모듈](/powershell/azure/active-directory/install-adv2) 이름 **AzureADPreview)를** 사용하여 다음을 변경해야 합니다.

- 이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.

- AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.

- 미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.

아래 스크립트를 텍스트 편집기(예: 메모장 또는 ISE Windows PowerShell [복사합니다.](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)

을 만든 그룹의 *\<GroupName\>* 이름으로 바 대체합니다. 예제:

`$GroupName = "Group Creators"`

파일을 다른 파일로 GroupCreators.ps1.

PowerShell 창에서 파일을 저장한 위치로 이동합니다("CD"를 \<FileLocation\> 입력).

다음을 입력하여 스크립트를 실행합니다.

`.\GroupCreators.ps1`

메시지가 [표시될 때](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) 관리자 계정으로 로그인합니다.

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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
} else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

스크립트의 마지막 줄에 업데이트된 설정이 표시됩니다.

![PowerShell 스크립트 출력 스크린샷.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

앞으로 사용되는 그룹을 변경하려는 경우 새 그룹의 이름으로 스크립트를 다시 실행하면 됩니다.

그룹 만들기 제한을 해제하고 모든 사용자가 그룹을 만들 수 있도록 다시 허용하려는 경우 $GroupName ""로 설정하고 $AllowGroupCreation "True"로 설정하고 스크립트를 다시 실행합니다.

## <a name="step-3-verify-that-it-works"></a>3단계: 작동하는지 확인

변경 내용을 적용하는 데 30분 이상 걸릴 수 있습니다. 다음을 수행하여 새 설정을 확인할 수 있습니다.

1. 그룹을 Microsoft 365 수 없는 사용자의 사용자 계정으로 로그인합니다. 즉, 사용자가 만든 그룹의 구성원이나 관리자가 아닌 것입니다.

2. **Planner 타일을** 선택합니다.

3. Planner의 **왼쪽** 탐색에서 새 계획을 선택하여 계획을 만들 수 있습니다.

4. 계획 및 그룹 만들기를 사용하지 않도록 설정했다는 메시지가 표시됩니다.

그룹의 구성원과 동일한 절차를 다시 시도하십시오.

> [!NOTE]
> 그룹의 구성원이 그룹을 만들 수 없는 경우 해당 OWA 사서함 정책을 통해 차단되지 [않는지 검사합니다.](/powershell/module/exchange/set-owamailboxpolicy)

## <a name="related-topics"></a>관련 주제

[공동 작업 거버넌스 계획 권장 사항](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[공동 작업 거버넌스 계획 만들기](collaboration-governance-first.md)

[Office 365 PowerShell 시작](../enterprise/getting-started-with-microsoft-365-powershell.md)

[셀프 서비스 그룹 관리 Azure Active Directory](/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory 구성하기 위한 cmdlet](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
