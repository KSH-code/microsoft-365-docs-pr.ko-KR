---
title: Microsoft Teams, Office 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용
ms.author: krowley
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 레이블을 적용할 수 있습니다.
ms.openlocfilehash: 4a8cf810ba29c2bb025b50e1529081a1a9ba6843
ms.sourcegitcommit: 72d0280c2481250cf9114d32317ad2be59ab6789
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40966896"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Microsoft Teams, Office 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용

[Microsoft 365 준수 센터](https://protection.office.com/)에서 민감도 레이블을 만들 때 이제 레이블을 Microsoft Teams, Office 365 그룹 그리고 SharePoint 사이트에 적용할 수 있습니다. 사용자는 정책을 레이블과 연결하여 다음을 제어할 수 있습니다.

- 공개/비공개 설정
- 게스트 액세스
- 관리되지 않는 장치에서 액세스

팀 또는 그룹에 레이블을 적용하는 경우 레이블은 자동으로 연결된 SharePoint 팀 사이트로 적용되고 그 반대로 적용되기도 합니다.

사용자는 이제 또한 SharePoint 및 OneDrive에서 Office 파일에 민감도 레이블을 사용할 수 있습니다. 자세한 내용은 [SharePoint 및 OneDrive에서 Office 파일에 민감도 레이블 사용(공개 미리 보기)](sensitivity-labels-sharepoint-onedrive-files.md)을 참조하세요.

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Microsoft Teams, Office 365 그룹 및 SharePoint 사이트의 공개 미리 보기에 대한 정보

Microsoft Teams, Office 365 그룹 및 SharePoint 사이트의 민감도 레이블은 테넌트에 점진적으로 배포되고 있으며 최종 출시 전에 변경될 수 있습니다.

이 공개 미리 보기는 Office 365 Content Delivery Network(CDNs)에서는 작동하지 않습니다.

## <a name="overview"></a>개요

민감도 레이블을 게시할 때 Office 365의 사용자는 같은 레이블 목록에 액세스할 수 있습니다.

이 이미지들은 다음을 표시합니다.

- SharePoint에서 새 팀 사이트를 만들 때 목록이 표시되는 방식

- Word에서 목록을 볼 때

예를 들어:

![SharePoint에서 팀 사이트를 만들 때의 민감도 레이블](media/sensitivity-label-new-team-site.png)

![Word 데스크톱 앱에 표시되는 민감도 레이블](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a>이 미리 보기를 사용

사용자는 Microsoft Teams, Office 365 그룹 및 SharePoint 사이트를 사용하여 이 민감도 레이블의 미리 보기를 사용하도록 설정하려면 [그래프용 Azure Directory PowerShell(AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)(모듈 이름 **AzureADPreview**)의 미리 보기 버전을 사용해야 합니다.

- 이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.

- AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.

- 미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.

이제 Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에서 민감도 레이블의 미리 보기를 사용할 준비가 되었습니다.

1. PowerShell 세션에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용하여 Azure Active Directory에 연결합니다. 예를 들어 다음을 실행합니다.
    
    ```powershell
    Connect-AzureAD
    ````
    
    자세한 지침은 [Azure AD에 연결](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad)을 참조하세요.

2. 다음의 명령을 실행합니다.
    
    ```powershell
    $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
    if ($setting -eq $null)
    {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
    }
    else
    {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
    }
    ```
    
    > [!NOTE]
    > 이 미리 보기를 사용하도록 설정하면 Office 365에서 새 그룹 및 SharePoint 사이트에 대해 이전의 분류를 더 이상 사용하지 않습니다. [Azure AD 사이트 분류](/sharepoint/dev/solution-guidance/modern-experience-site-classification)($setting ["ClassificationList"])를 사용한 경우 기존 그룹과 사이트에서는 여전히 이전의 분류를 표시합니다. 새 분류를 표시하려면 전환을 합니다. 전환하는 방법에 대한 내용은 [클래식 Azure AD 사이트 분류를 사용한 경우](#if-you-used-classic-azure-ad-site-classification)를 참조하세요. 

3. 동일한 PowerShell 세션에서 이제 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용하여 보안 & 준수 센터에 연결합니다. 지침은 [Office 365 보안 및 규정 준수 센터 PowerShell에 연결](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)을 참조합니다.

4. 다음 명령을 실행하여 레이블을 Azure AD에 동기화하여 Office 365 그룹에서 사용할 수 있습니다.
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>민감도 레이블을 만들거나 편집할 때 사이트 및 그룹 설정을 지정

미리 보기를 사용하도록 설정한 후 다음 단계를 사용하여 민감도 레이블을 만들거나 편집합니다. 레이블이 이미 정의되어 있는 경우에도 새 민감도 레이블이 사이트 및 그룹과 작동하려면 다음의 단계를 완료해야 합니다. 이러한 설정에 대한 변경은 동기화하는 데 최대 24시간이 걸릴 수 있습니다.

1. Microsoft 365 규정 준수 센터에서 **분류** > **민감도 레이블**을 선택합니다.

2. **레이블 만들기**를 선택합니다. 이미 레이블이 있으면 다음 단계로 건너뜁니다.

3. 원하는 옵션을 선택한 다음 **사이트 및 그룹 설정** 탭에서 다음을 선택합니다.
    
    - 개인 정보(공개/비공개): 비공개는 조직에서 승인된 구성원만 그룹 내부의 내용을 볼 수 있음을 의미합니다. 조직의 그 외의 사람은 그룹 내부의 내용을 볼 수 없습니다. [자세한 정보](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - 게스트 액세스: 사용자는 그룹에 게스트를 추가할 수 있는지를 제어할 수 있습니다. [Office 365 그룹에서의 게스트 액세스 관리에 대해 알아보세요](/office365/admin/create-groups/manage-guest-access-in-groups)
    - 관리되지 않는 장치: 이 설정을 사용하면 Intune에서 하이브리드 AD에 참가하지 않았거나 비규격인 장치에서의 SharePoint 콘텐츠로의 액세스를 차단하거나 제한할 수 있습니다. 관리되지 않는 장치를 선택하는 경우 Azure AD로 이동하여 정책 설정을 완료해야 합니다. 관련 정보는 [관리되지 않는 장치에서 액세스 제어](/sharepoint/control-access-from-unmanaged-devices)를 참조합니다.
    
    ![사이트 및 그룹 설정 탭](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> 팀, 그룹 또는 사이트에 레이블을 적용하는 경우에는 사이트 및 그룹 설정만 적용이 됩니다. 암호화 및 콘텐츠 표시와 같은 다른 설정은 팀, 그룹 또는 사이트 내의 모든 콘텐츠에 적용되지 않습니다.
> 
> 마찬가지로, 레이블을 만들고 사이트 및 그룹 설정을 켜지 않는 경우에는 사용자가 팀, 그룹 및 사이트를 만들 때 해당 레이블을 계속 사용할 수 있지만 설정을 적용하지 않고 분류를 하게 됩니다.

[민감도 레이블 게시에 대해 자세히 알아보기](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a>민감도 레이블 관리

> [!WARNING]
> Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에 사용하는 민감도 레이블 만들기, 수정 그리고 삭제는 사용자에게 레이블 정책을 게시하는데 케어 코디네이션을 필요로 합니다. 

다음의 지침을 사용하여 모든 사용자에게 영향을 줄 수 있는 사이트 및 그룹에 대한 만들기 오류를 방지합니다.

**레이블 만들기 및 게시:**

민감도 레이블이 만들어지고 게시된 후 레이블이 팀, 그룹 및 사이트의 사용자에게 표시될 때까지는 최대 24시간이 걸릴 수 있습니다. 다음의 단계를 사용하여 테넌트의 모든 사용자에 대한 레이블을 게시합니다.

1. 민감도 레이블을 만들고 테넌트의 일부 사용자 계정에만 게시합니다.

2. 24시간을 기다립니다.

3. 24시간을 기다린 후에 1단계에서 지정한 사용자 계정 중 하나를 사용하여 1단계에서 만든 레이블이 있는 팀, Office 365 그룹 또는 SharePoint 사이트를 만듭니다.

4. 3단계의 만들기 작업 중에 오류가 없으면 테넌트의 모든 사용자에게 레이블을 게시합니다. 오류가 있으면 Microsoft 지원 센터에 문의하세요.

**게시된 레이블 수정 및 삭제:**

하나 이상의 레이블 정책에 포함된 민감도 레이블을 수정하거나 삭제하는 경우, 이러한 작업의 수행은 모든 팀, 그룹 및 사이트에 대한 만들기 오류로 이어질 수 있습니다. 이러한 상황을 방지하려면 다음의 지침을 사용 하세요.

1. 레이블이 포함된 모든 레이블 정책에서 민감도 레이블을 제거합니다.

2. 48시간을 기다립니다.

3. 48시간을 기다린 후에 팀, 그룹 또는 사이트 만들기를 시도해보고 해당 레이블이 더 이상 보이지 않는지 확인합니다.

4. 민감도 레이블이 보이지 않는 경우에는 안전하게 레이블을 수정하거나 삭제할 수 있습니다. 레이블이 계속 표시되면 Microsoft 지원 센터에 문의하세요.

## <a name="troubleshoot-sensitivity-label-deployment"></a>민감도 레이블 배포 문제 해결

### <a name="labels-not-visible-after-publishing"></a>게시 후 레이블이 보이지 않음
이 설정을 사용하도록 설정하거나 민감도 레이블의 설명을 수정한 후 팀 또는 Office 365 그룹을 만들 때 문제가 발생하는 경우 레이블을 저장하고 몇 시간을 기다린 후에 팀 또는 그룹을 다시 만들어 봅니다. 이에 대한 내용은 [민감도 레이블을 만들거나 변경한 후의 롤아웃 일정 예약](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)을 참조하세요.

아직 SharePoint Online에서 새 민감도 레이블을 표시할 수 없는 경우 Microsoft 지원 센터에 문의하세요.

### <a name="team-group-or-sharepoint-site-creation-errors"></a>팀, 그룹 또는 SharePoint 사이트 만들기 오류
공개 미리 보기를 진행하는 동안 만들기 오류가 발생하는 경우 다음과 같은 두 가지 옵션이 있습니다.

- 모든 사용자에 대해 민감도 레이블이 필수가 아닌지 확인합니다.

- 이 페이지의 [이 미리 보기를 사용](#enable-this-preview) 섹션에서와 동일한 지침을 사용하여 Microsoft Teams, Office 365 그룹 및 SharePoint 사이트의 민감도 레이블을 해제할 수 있습니다. 그러나 미리 보기를 사용하지 않도록 설정하려면 회선 `$setting["EnableMIPLabels"] = "True"`을 검색하고 **True**값을 **False**로 변경합니다.

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>새 팀에 민감도 레이블을 적용

사용자는 Microsoft Teams에서 새 팀을 만들 때 민감도 레이블을 선택할 수 있습니다. 사용자가 민감도 레이블을 선택할 때 개인 정보 설정이 필요에 따라 변경됩니다. 사용자가 레이블에 대해 선택한 게스트 액세스 설정에 따라 조직 외부의 사용자를 팀에 추가할 수 있는지의 여부가 결정됩니다.

[Teams용 민감도 레이블에 대해 자세히 알아보기](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![새 팀을 만드는 경우 개인 정보 설정](media/privacy-setting-new-team.png)

팀을 만든 후에는 모든 채널의 우측 상단 모서리에 민감도 레이블이 표시됩니다.

![민감도 레이블이 팀에 표시됩니다.](media/privacy-setting-teams.png)

이 서비스는 Office 365 그룹 및 연결된 SharePoint 팀 사이트에 자동으로 동일한 민감도 레이블을 적용합니다.

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>새 그룹에 민감도 레이블을 적용

웹용 Outlook에서 새 **민감도** 상자에는 게시된 레이블이 포함되어 있습니다. 사용자가 추가 정보를 원하는 경우 도움말 아이콘을 클릭하여 사용 가능한 레이블과 관련 정책에 대한 세부 정보를 읽을 수 있습니다.

![그룹 만들기 및 민감도 아래의 옵션 선택](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>새 사이트에 민감도 레이블을 적용

관리자 및 최종 사용자는 최신 팀 사이트 및 커뮤니케이션 사이트를 만들 때 민감도 레이블을 선택할 수 있습니다.

[새 SharePoint 관리 센터에서 사이트 만드는 방법 알아보기](/sharepoint/create-site-collection)

사용자가 최신 팀 및 커뮤니케이션 사이트를 만들 때 기본적으로 민감도 레이블이 이미 선택되어 있습니다. 사용자는 도움말 아이콘을 선택하여 레이블에 대한 더욱 자세한 정보를 확인할 수 있습니다.

![사이트 만들기 및 민감도 아래의 옵션 선택](media/sensitivity-label-new-communication-site.png)

사용자가 사이트로 이동할 때 레이블의 이름과 적용된 정책을 볼 수 있습니다.

![민감도 레이블이 적용된 사이트](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>SharePoint 관리 센터에서 민감도 레이블 관리

레이블을 보고 편집하려면 새 SharePoint 관리 센터의 활성 사이트 페이지를 사용합니다.

![활성 사이트 페이지의 민감도 열](media/manage-site-sensitivity-labels.png)

[새 SharePoint 관리 센터에서의 사이트 관리에 대해 자세히 알아보기](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>레이블의 사이트 및 그룹 설정 변경

레이블의 사이트 및 그룹 설정을 변경할 때마다 팀, 사이트, 그룹에서 새 설정을 사용할 수 있도록 다음 PowerShell 명령을 실행해야 합니다. 최상의 방법은 여러 팀, 그룹 또는 사이트에 레이블을 적용한 후 레이블의 사이트와 그룹 설정을 변경하지 않는 것입니다.

1. 다음 명령을 실행하여 Office 365 보안 & 규정 준수 센터 PowerShell에 연결한 후 민감도 레이블과 해당 Guid 목록을 가져옵니다.
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. 사용자가 변경한 레이블의 GUID를 기록해 둡니다.

3. 이제 Exchange Online PowerShell에 연결하여 Get-UnifiedGroup cmdlet을 실행하고 예제 GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" 대신에 레이블 GUID를 지정합니다. 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. 각 그룹에 대해 민감도 레이블을 다시 적용하고 예제 GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" 대신에 레이블 GUID를 지정합니다.
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-new-sensitivity-labels"></a>새 민감도 레이블에 대한 지원

다음의 앱과 서비스는 이 미리 보기에서 민감도 레이블을 지원합니다.

- Microsoft 365 규정 준수 센터
- SharePoint
- 웹용 Outlook
- Teams
- SharePoint 관리 센터
- Azure AD 관리 센터

다음과 같은 앱과 서비스를 사용하여 새 민감도 레이블이 있는 Office 365 그룹을 만들 수 없습니다.

- Mac용 Outlook
- Outlook 모바일  
- Windows용 Outlook 데스크톱
- 양식  
- Dynamics 365  
- Yammer  
- Stream  
- Planner  
- Project  
- PowerBI  
- Teams 관리 센터  
- Microsoft 365 관리 센터  
- Exchange 관리 센터

## <a name="if-you-used-classic-azure-ad-site-classification"></a>클래식 Azure AD 사이트 분류를 사용한 경우

이 미리 보기를 사용하도록 설정하면 Office 365에서 새 그룹 및 SharePoint 사이트에 대해 이전의 분류를 더 이상 지원하지 않습니다. 그러나 기존의 그룹과 사이트는 이전 분류를 변환하지 않는 한 계속 표시를 합니다. 이전 분류에는 `ClassificationList` 설정에 대한 값을 정의한 Azure AD PowerShell 또는 PnP Core 라이브러리를 통해 설정하는 "최신" 사이트 분류가 포함 됩니다.

예를 들어 PowerShell에서:

```powershell
   ($setting["ClassificationList"])
```

이전 분류 방법에 대한 자세한 내용은 [SharePoint "최신" 사이트 분류](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)를 참조하세요.

현재의 배포에 따라 이전의 분류를 새 분류로 변환하기 위한 두 가지 옵션이 있습니다.

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>파일 및 전자 메일에 대해 민감도 레이블(통합 Microsoft 정보 보호 레이블)을 전혀 사용하지 않은 경우

다음의 작업을 권장합니다.

1. Microsoft 365 준수 센터에서 기존의 분류와 이름이 같은 새 민감도 레이블을 만듭니다.
2. PowerShell을 사용하여 새 레이블을 이름 매핑을 사용하여 기존의 Office 365 그룹 및 SharePoint 사이트에 적용합니다.
3. 이전의 분류를 삭제합니다.

새 민감도 레이블을 지원하는 앱 및 서비스에서 해당 항목을 표시합니다. 새 레이블과 같이 새 팀, 그룹 및 사이트를 만듭니다. 사용자는 새 레이블을 지원하지 않는 앱 및 서비스에서 계속해서 그룹을 만들 수 있습니다. 그러나 사용자는 이 그룹에 레이블을 적용할 수 없습니다. PowerShell을 사용하여 이 그룹에 새 민감도 레이블을 적용합니다.

사용자는 이전의 분류를 유지할 수 있지만 PowerShell을 사용하여 이러한 그룹에 새 민감도 레이블을 적용할 것을 권장합니다.

새 민감도 레이블을 지원하는 앱 및 서비스가 새 레이블과 함께 만들어집니다. 사용자는 새 레이블을 지원하지 않는 앱 및 서비스에서 그룹을 만들 때 분류를 선택할 수 있습니다.

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>파일 및 전자 메일에 대해 민감도 레이블(통합 Microsoft 정보 보호 레이블)을 사용하는 경우

이 미리 보기를 사용하도록 설정하는 즉시 Microsoft 365 준수 센터의 각 레이블로 이동하여 사이트 및 그룹에 원하는 정책을 적용합니다. 사용자는 사이트 및 그룹에 대해 사용할 수 있는 기존 레이블을 보게 됩니다.

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Office 365 그룹의 레이블을 변경하기 전에 SharePoint Online 관리 셸을 준비합니다.

새 레이블을 적용하기 전에 최신 SharePoint Online 관리 셸을 실행하고 있는지 확인합니다. 이미 최신 버전을 사용하고 있는 경우 [새 민감도 레이블로 Office 365 그룹의 레이블 변경 ](#relabel-office-365-groups-with-new-sensitivity-labels)을 계속 진행할 수 있습니다.

미리 보기를 위한 SharePoint Online 관리 셸을 준비하려면 다음을 수행합니다.

1. 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 **프로그램 추가/제거**로 이동하여 "SharePoint Online 관리 셸"을 제거합니다.

2. 웹 브라우저에서 다운로드 센터 페이지로 이동한 다음 [최신 SharePoint Online 관리 셸을 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)합니다.

3. 언어를 선택한 다음 **다운로드**를 클릭합니다.

4. X64 및 x86 .msi 파일 중에서 선택합니다. 64비트 버전의 Windows를 실행하는 경우 x64 파일을 혹은 32비트 버전을 실행하는 경우 x86 파일을 다운로드합니다. 버전을 모르는 경우에는 [어떠한 Windows 운영 체제 버전을 실행 중인가요?](https://support.microsoft.com/help/13443/windows-which-operating-system)를 참조하세요.

5. 파일을 다운로드한 후 실행을 하고 설정 마법사의 단계를 따릅니다.

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>새 민감도 레이블로 Office 365 그룹의 레이블을 변경합니다.

1. 최신 버전의 SharePoint Online 관리 셸을 사용 하고 있는지 확인합니다. 이에 대한 지침은 [Office 365 그룹의 레이블을 변경하기 전에 SharePoint Online 관리 셸을 준비](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)를 참조합니다.

2. Office 365에서 전역 관리자 또는 SharePoint 관리자 권한을 보유하는 회사 또는 학교 계정을 사용하여 SharePoint Online 관리 셸에 연결합니다. 자세한 방법은 [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.

3. 다음의 명령을 실행하여 민감도 레이블과 해당 GUID 목록을 가져옵니다.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. 덮어쓸 레이블의 GUID를 기록합니다. 예를 들면 "일반" 레이블입니다.

5. 다음의 명령을 사용하여 "일반" 분류를 포함하는 그룹의 목록을 가져옵니다. 이 명령을 실행하는 경우 Exchange Online PowerShell에 연결하고 Get-unifiedGroup cmdlet을 실행합니다.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. 각 그룹에 새 민감도 레이블 GUID를 추가합니다.

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
