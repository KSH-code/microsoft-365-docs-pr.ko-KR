---
title: Microsoft Teams, Office 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 레이블을 적용할 수 있습니다.
ms.openlocfilehash: a6c187227703395ed5fe3d926dabe30e6203fca5
ms.sourcegitcommit: 909f18d6c497086899fa239b5b5e0bb91f1e7804
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39819134"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Microsoft Teams, Office 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용

[Microsoft 365 준수 센터](https://protection.office.com/)에서 민감도 레이블을 만들 때는 이제 microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 해당 우편물을 적용할 수 있습니다. 다음과 같이 레이블에 정책을 연결 하 여 제어할 수 있습니다.

- 공용/개인 설정
- 게스트 액세스
- 관리 되지 않는 장치에서 액세스

팀 또는 그룹에 레이블을 적용 하면 연결 된 SharePoint 팀 사이트 및 기타 방식으로 레이블이 자동으로 적용 됩니다.

이제 SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용 하도록 설정할 수도 있습니다. [자세한 정보](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 대 한 공개 미리 보기

Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 대 한 민감도 레이블은 테 넌 트에 점진적으로 롤아웃 되며 최종 릴리스 전에 변경 될 수 있습니다.

Office 365 Content Delivery Networks (CDNs)에서는 공개 미리 보기가 작동 하지 않습니다.

## <a name="overview"></a>개요

민감도 레이블을 게시할 때 Office 365의 사용자에 게 동일한 레이블 목록에 대 한 액세스 권한이 있습니다.

표시 되는 이미지는 다음과 같습니다.

- SharePoint에서 새 팀 사이트를 만들 때 목록이 표시 되는 방식

- Word에서 목록을 볼 때

![SharePoint에서 팀 사이트를 만들 때의 민감도 레이블](media/sensitivity-label-new-team-site.png)

![Word 데스크톱 앱에 표시 되는 민감도 레이블](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a>Azure PowerShell을 사용 하 여이 미리 보기 사용

1. Azure PowerShell을 사용 하 여 Azure에 전역 관리자로 로그인 합니다. 자세한 내용은 [Azure PowerShell을 사용 하 여 로그인](/powershell/azure/authenticate-azureps)을 참조 하십시오.

2. 다음 명령을 실행합니다.

```powershell
  Connect-AzureAD
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

이 미리 보기를 사용 하도록 설정 하면 Office 365에서 새 그룹 및 SharePoint 사이트에 대 한 이전 분류를 더 이상 사용 하지 않습니다. [AZURE AD 사이트 분류](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting ["ClassificationList"])를 사용 하는 경우 기존 그룹 및 사이트에서 이전 분류를 계속 표시 합니다. 새 분류를 표시 하려면 변환 합니다. 이를 변환 하는 방법에 대 한 자세한 내용은 [클래식 AZURE AD 사이트 분류를 사용 하는지](#if-you-used-classic-azure-ad-site-classification)확인 하세요. 

## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>민감도 레이블을 만들거나 편집할 때 사이트 및 그룹 설정 설정

미리 보기를 사용 하도록 설정한 후에는 다음 단계를 수행 하 여 민감도 레이블을 만들거나 편집 합니다. 새 민감도 레이블이 이미 정의 된 레이블이 있더라도 사이트 및 그룹과 함께 작업 하려면이 단계를 완료 해야 합니다. 이러한 설정에 대 한 변경 내용은 동기화를 최대 24 시간까지 걸릴 수 있습니다.

1. Microsoft 365 준수 센터에서 **분류** > **민감도 레이블을**선택 합니다.

2. **레이블 만들기를**선택 합니다. 레이블이 이미 있는 경우 다음 단계로 건너뜁니다.

3. 원하는 옵션을 선택 하 고 **사이트 및 그룹 설정** 탭에서 다음을 선택 합니다.

    - 개인 정보 보호 (공개/개인): 비공개 란 조직에서 승인 된 구성원만이 그룹 내의 내용을 볼 수 있음을 의미 합니다. 조직의 다른 사용자가 그룹의 내용을 볼 수 없습니다. [자세한 정보](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - 게스트 액세스: 게스트를 그룹에 추가할 수 있는지 여부를 제어할 수 있습니다. [Office 365 그룹에서 게스트 액세스 관리에 대해 자세히 알아보기](/office365/admin/create-groups/manage-guest-access-in-groups)
    - 관리 되지 않는 장치:이 설정을 사용 하면 Intune에서 하이브리드 AD가 연결 되어 있지 않거나 호환 되지 않는 장치에서 SharePoint 콘텐츠에 대 한 액세스를 차단 하거나 제한할 수 있습니다. 관리 되지 않는 장치를 선택 하는 경우에는 Azure AD로 이동 하 여 정책 설정을 완료 해야 합니다. 자세한 내용은 [관리 되지 않는 장치에서의 액세스 제어](/sharepoint/control-access-from-unmanaged-devices)를 참조 하십시오.

![사이트 및 그룹 설정 탭](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> 팀, 그룹 또는 사이트에 레이블을 적용 하는 경우에만 사이트 및 그룹 설정만 적용 됩니다. 암호화 및 콘텐츠 표시와 같은 다른 설정은 팀, 그룹 또는 사이트 내의 모든 콘텐츠에 적용 되지 않습니다. 마찬가지로 레이블을 만들고 사이트 및 그룹 설정을 사용 하지 않는 경우에도 사용자가 팀, 그룹 및 사이트를 만들 때도 레이블을 사용할 수 있지만 사용자가이를 적용할 때 어떤 작업을 수행 하지 않아도 됩니다.

[민감도 레이블을 게시 하는 방법 알아보기](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="troubleshoot-sensitivity-label-deployment"></a>민감도 레이블 배포 문제 해결

이러한 설정을 사용 하도록 설정 하거나 레이블의 설명을 변경한 후에 팀 또는 Office 365 그룹을 만들 때 문제가 발생 하면 레이블을 저장 하 고 몇 시간 기다린 후 팀 또는 Office 365 그룹을 다시 만듭니다.

아직 SharePoint Online의 새 민감도 레이블을 볼 수 없으면 Microsoft Support에 즉시 문의 하세요.

[민감도 레이블을 게시 하는 방법 알아보기](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>새 팀에 민감도 레이블 적용

사용자는 Microsoft 팀에서 새 팀을 만들 때 민감도 레이블을 선택할 수 있습니다. 민감도 수준을 선택 하면 개인 정보 설정이 필요에 따라 변경 됩니다. 레이블에 대해 선택한 게스트 액세스 설정에 따라 사용자가 조직 외부의 사용자를 팀에 추가할 수 있거나 추가 하지 못할 수도 있습니다.

![새 팀을 만들 때의 개인 정보 설정](media/privacy-setting-new-team.png)

팀을 만든 후에는 민감도 레이블이 모든 채널의 오른쪽 위 모서리에 표시 됩니다.

![팀에 민감도 레이블이 표시 됩니다.](media/privacy-setting-teams.png)

이 서비스는 Office 365 그룹 및 연결 된 SharePoint 팀 사이트에 동일한 민감도 레이블을 자동으로 적용 합니다.

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>새 그룹에 민감도 레이블 적용

웹용 Outlook에서 새 **우편물 종류** 상자에는 게시 된 레이블이 포함 됩니다. 사용자가 추가 정보를 원하는 경우 도움말 아이콘을 클릭 하 여 사용 가능한 레이블과 연결 된 정책에 대 한 세부 정보를 읽을 수 있습니다.

![그룹 만들기 및 민감도에서 옵션 선택](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>새 사이트에 민감도 레이블 적용

관리자 및 최종 사용자가 최신 팀 사이트 및 통신 사이트를 만들 때 민감도 레이블을 선택할 수 있습니다.

[새 SharePoint 관리 센터에서 사이트를 만드는 방법을 알아봅니다.](/sharepoint/create-site-collection)

사용자가 최신 팀 및 커뮤니케이션 사이트를 만들 때 우편물 종류 레이블은 기본적으로 이미 선택 되어 있습니다. 사용자가 도움말 아이콘을 선택 하 여 레이블에 대 한 자세한 내용을 확인할 수 있습니다.

![사이트 만들기 및 민감도에서 옵션 선택](media/sensitivity-label-new-communication-site.png)

사용자가 사이트를 탐색할 때 레이블 이름 및 적용 된 정책을 볼 수 있습니다.

![민감도 레이블이 적용 된 사이트](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>SharePoint 관리 센터에서 민감도 레이블 관리

레이블을 보고 편집 하려면 새 SharePoint 관리 센터에서 활성 사이트 페이지를 사용 합니다.

![활성 사이트 페이지의 민감도 열](media/manage-site-sensitivity-labels.png)

[새 SharePoint 관리 센터에서 사이트를 관리 하는 방법에 대해 자세히 알아보세요](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>레이블에 대 한 사이트 및 그룹 설정 변경

여러 팀, 그룹 또는 사이트에 레이블을 적용 한 후에는 설정을 변경 하지 않는 것이 좋습니다. 변경을 수행 해야 하는 경우 Azure AD PowerShell 스크립트를 사용 하 여 업데이트를 수동으로 적용 해야 합니다. 이 메서드를 사용 하면 모든 기존 팀, 사이트 및 그룹이 새 설정을 적용 합니다.

## <a name="support-for-the-new-sensitivity-labels"></a>새 민감도 레이블 지원

다음 앱 및 서비스는이 미리 보기에서 민감도 레이블을 지원 합니다.

- Microsoft 365 규정 준수 센터
- SharePoint
- 웹용 Outlook
- Teams
- SharePoint 관리 센터
- Azure AD 관리 센터

다음 앱 및 서비스를 사용 하 여 새 민감도 레이블로 Office 365 그룹을 만들 수는 없습니다.

- Mac 용 Outlook
- Outlook 모바일  
- Windows 용 Outlook 데스크톱
- Forms  
- Dynamics 365  
- Yammer  
- Stream  
- Planner  
- Project  
- PowerBI  
- 팀 관리 센터  
- Microsoft 365 관리 센터  
- Exchange 관리 센터

## <a name="if-you-used-classic-azure-ad-site-classification"></a>클래식 Azure AD 사이트 분류를 사용한 경우

이 미리 보기를 사용 하도록 설정 하면 Office 365에서 새 그룹 및 SharePoint 사이트에 대 한 이전 분류를 더 이상 지원 하지 않습니다. 그러나 기존 그룹과 사이트는 변환 하지 않는 한 이전 분류를 계속 표시 합니다. 이전 분류에는 설정 값 `ClassificationList` 을 정의 하는 Azure AD PowerShell 또는 PnP 핵심 라이브러리를 통해 설정한 "최신" 사이트 분류가 포함 됩니다.

예를 들어 PowerShell:

```powershell
   ($setting["ClassificationList"])
```

이전 분류 방법에 대 한 자세한 내용은 [SharePoint "최신" 사이트 분류](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)를 참조 하세요.

현재 배포에 따라 이전 분류를 새 분류로 변환 하는 두 가지 옵션이 있습니다.

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>파일 및 전자 메일에 대해 민감도 레이블 (통합 Microsoft Information Protection 레이블)을 사용 하지 않은 경우

따라서 다음 작업이 권장됩니다.

1. Microsoft 365 준수 센터에서 기존 분류와 이름이 같은 새 민감도 레이블을 만듭니다.
2. PowerShell을 사용 하 여 새 레이블을 이름 매핑을 사용 하 여 기존 Office 365 그룹 및 SharePoint 사이트에 적용 합니다.
3. 이전 분류를 삭제 합니다.

새 민감도 레이블을 지 원하는 앱 및 서비스에서 해당 항목을 표시 합니다. 새 레이블을 사용 하 여 팀, 그룹 및 사이트를 새로 만듭니다. 사용자는 새 레이블을 지원 하지 않는 앱 및 서비스에서 그룹을 만들 수 있습니다. 그러나 사용자는 이러한 그룹에 레이블을 적용할 수 없습니다. PowerShell을 사용 하 여 이러한 그룹에 새 민감도 레이블을 적용 합니다.

이전 분류를 유지할 수 있습니다. 그러나 PowerShell을 사용 하 여 이러한 그룹에 새 민감도 레이블을 적용 하는 것이 좋습니다.

새 민감도 레이블을 지 원하는 앱 및 서비스가 새 레이블로 작성 됩니다. 사용자가 새 레이블을 지원 하지 않는 앱 및 서비스에서 그룹을 만들 때는 분류를 선택할 수 있습니다.

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>파일 및 전자 메일에 민감도 레이블 (통합 Microsoft Information Protection labels)을 사용 하는 경우

이 미리 보기를 사용 하도록 설정 하는 즉시 Microsoft 365 준수 센터의 각 레이블로 이동 하 여 사이트 및 그룹에 대해 원하는 정책을 적용 합니다. 사용자는 사이트 및 그룹에 사용할 수 있는 기존 레이블을 확인 하기 시작 합니다.

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Office 365 그룹을 relabel 하기 전에 SharePoint Online 관리 셸 준비

새 레이블을 적용 하기 전에 최신 SharePoint Online 관리 셸을 실행 중인지 확인 합니다. 최신 버전을 이미 사용 하 고 있는 경우 [Relabel Office 365 그룹을 새 민감도 레이블로](#relabel-office-365-groups-with-new-sensitivity-labels)이동 하 여 확인할 수 있습니다.

미리 보기에 대해 SharePoint Online 관리 셸을 준비 하려면 다음을 수행 합니다.

1. 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 **프로그램 추가/제거** 로 이동 하 여 "SharePoint Online 관리 셸"을 제거 합니다.

2. 웹 브라우저에서 다운로드 센터 페이지로 이동 하 [여 최신 SharePoint Online 관리 셸을 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)합니다.

3. 언어를 선택 하 고 **다운로드**를 클릭 합니다.

4. X64 파일과 x86 .msi 파일 중에서 선택 합니다. 64 비트 버전의 Windows 또는 x86 파일 (32 비트 버전을 실행 하는 경우)을 실행 하는 경우 x64 파일을 다운로드 합니다. 알 수 없는 경우 [실행 중인 Windows 운영 체제 버전](https://support.microsoft.com/help/13443/windows-which-operating-system)을 확인 하세요.

5. 파일을 다운로드 한 후에는 파일을 실행 하 고 설치 마법사의 단계를 따릅니다.

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>새 민감도 레이블이 있는 Relabel Office 365 그룹

1. 최신 버전의 SharePoint Online 관리 셸을 사용 하 고 있는지 확인 합니다. 자세한 내용은 [Office 365 그룹을 relabel 하기 전에 SharePoint Online 관리 셸 준비](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)를 참조 하세요.

2. Office 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint Online 관리 셸에 연결 합니다. 자세한 방법은 [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.

3. 다음 명령을 실행 하 여 민감도 레이블 및 해당 Guid의 목록을 가져옵니다.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. 덮어쓸 레이블의 GUID를 기록해 둡니다. 예를 들면 "일반" 레이블입니다.

5. 다음 명령을 사용 하 여 "General" 분류를 포함 하는 그룹 목록을 가져옵니다. 이 명령을 실행 하면 Exchange Online PowerShell에 연결 하 여 Remove-unifiedgroup cmdlet을 실행 합니다.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. 각 그룹에 대해 새 민감도 레이블 GUID를 추가 합니다.

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
