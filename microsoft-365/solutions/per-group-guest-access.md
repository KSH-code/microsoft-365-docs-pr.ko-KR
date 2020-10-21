---
title: 게스트 사용자가 특정 그룹에 추가 되지 않도록 설정
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 게스트 사용자가 특정 그룹에 추가 되지 않도록 하는 방법을 알아봅니다.
ms.openlocfilehash: 91c7560186fb0b954075e9ff9c997b34121951cd
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651353"
---
# <a name="prevent-guest-users-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>게스트 사용자가 특정 Microsoft 365 그룹 또는 Microsoft 팀 팀에 추가 되지 않도록 합니다.

대부분의 그룹과 팀에 대 한 게스트 액세스를 허용 하지만 게스트 액세스를 차단 하려는 경우에는 개별 그룹 및 팀에 대 한 게스트 액세스를 차단할 수 있습니다. (팀에 대 한 게스트 액세스 차단은 연결 된 그룹에 대 한 게스트 액세스를 차단 하 여 수행 됩니다.) 이렇게 하면 새 게스트가 추가 되는 것을 방지할 수 있지만 그룹 또는 팀에 이미 있는 게스트는 제거 되지 않습니다.

조직에서 민감도 레이블을 사용 하는 경우에는 그룹 단위로 게스트 액세스를 제어 하는 데 사용 하는 것이 좋습니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 [민감도 레이블을 사용 하 여 Microsoft 팀, microsoft 365 그룹 및 SharePoint 사이트의 콘텐츠를 보호](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)합니다. 가능한 한 이 방법을 사용하는 것이 좋습니다.

## <a name="change-group-settings-using-microsoft-powershell"></a>Microsoft PowerShell을 사용 하 여 그룹 설정 변경

PowerShell을 사용 하 여 개별 그룹에 새 게스트를 추가 하지 못하게 할 수도 있습니다.

그룹 수준 게스트 액세스 설정을 변경 하려면 [Graph에 대 한 Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 의 preview 버전 (모듈 이름 **AzureADPreview**)을 사용 해야 합니다.

- 이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.

- AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.

- 미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.

> [!NOTE]
> 이러한 명령을 실행 하려면 전역 관리자 권한이 있어야 합니다. 

*/<GroupName/>* 게스트 액세스를 차단 하려는 그룹의 이름으로 변경 되는 다음 스크립트를 실행 합니다.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

설정을 확인 하려면 다음 명령을 실행 합니다.

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

확인은 다음과 같습니다.
    
![게스트 그룹 액세스가 false로 설정 되었음을 보여 주는 PowerShell 창의 스크린샷](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>도메인을 기반으로 게스트 액세스 허용 또는 차단

특정 도메인을 사용 하는 게스트 사용자를 허용 하거나 차단할 수 있습니다. 예를 들어 회사 (Contoso)에 다른 회사 (Fabrikam)와의 협력 관계가 있으면 사용자가 자신의 그룹에 해당 게스트를 추가할 수 있도록 허용 목록에 Fabrikam을 추가할 수 있습니다.

자세한 내용은 [특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)를 참조 하세요.

## <a name="add-guests-to-the-global-address-list"></a>전체 주소 목록에 게스트 추가

기본적으로 게스트는 Exchange 전체 주소 목록에 표시 되지 않습니다. 아래에 나와 있는 단계를 사용 하 여 게스트가 전체 주소 목록에 표시 되도록 합니다.

다음을 실행 하 여 게스트 사용자의 ObjectID를 찾습니다.

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

그런 후에는 ObjectID, GivenName, 성, DisplayName 및 TelephoneNumber에 적절 한 값을 사용 하 여 다음을 실행 합니다.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>관련 문서

[Microsoft 365 관리 센터에서 그룹 멤버 자격 관리](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Azure Active Directory 액세스 검토](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
