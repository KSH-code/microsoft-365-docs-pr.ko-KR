---
title: Microsoft 365 그룹에서 게스트 액세스 관리
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Microsoft 365 그룹에 게스트를 추가 하 고, 게스트 사용자를 보고, PowerShell을 사용 하 여 게스트 액세스를 제어 하는 방법을 알아봅니다.
ms.openlocfilehash: 48f3339968040eeb82a93d6540c70f0bbea0754a
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140546"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Microsoft 365 그룹에서 게스트 액세스 관리

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경 되는 중입니다. 환경이 여기에 나와 있는 세부 정보와 일치 하지 않으면 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조 하세요.

::: moniker-end

기본적으로 Microsoft 365 그룹에 대 한 게스트 액세스는 조직에서 사용 하도록 설정 되어 있습니다. 관리자는 전체 조직에 대 한 그룹 또는 개별 그룹에 대 한 게스트 액세스를 허용할지 여부를 제어할 수 있습니다.

이 옵션이 설정 되 면 그룹 구성원은 웹에서 Outlook을 통해 게스트 사용자를 Microsoft 365 그룹에 초대할 수 있습니다. 초대는 승인을 위해 그룹 소유자에 게 전송 됩니다.

> [!Note]
> 기본 모드 또는 [EU 지역](https://go.microsoft.com/fwlink/?linkid=2107357) 에 있는 Yammer Enterprise 네트워크는 네트워크 게스트를 지원 하지 않습니다.
> Microsoft 365 연결 된 Yammer 그룹은 현재 게스트 액세스를 지원 하지 않지만, Yammer 네트워크에 연결 되지 않은 외부 그룹을 만들 수 있습니다. 지침은 [Yammer에서 외부 그룹 만들기 및 관리](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) 를 참조 하세요.

### <a name="edit-guest-information"></a>게스트 정보 편집

승인 된 게스트 사용자는 디렉터리와 그룹에 추가 됩니다.

그룹의 게스트 액세스는 SharePoint 또는 팀이 포함 된 보다 광범위 한 시나리오의 일부로 사용 되는 경우가 많습니다. 이러한 서비스에는 자체 게스트 공유 설정이 있습니다. 그룹, SharePoint 및 팀에서 게스트 공유를 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.

- [게스트와 현장에서 공동 작업하기](../../solutions/collaborate-in-site.md)
- [게스트와 팀으로 공동 작업하기](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>그룹 관리 게스트 액세스

그룹에서 게스트 액세스를 사용 하도록 설정 하거나 사용 하지 않도록 설정 하려면 Microsoft 365 관리 센터에서이 작업을 수행 하면 됩니다.

1. 관리 센터에서 **설정** \> **설정** 으로 이동 하 여 **Microsoft 365 그룹**을 선택 합니다.
  
2. **Microsoft 365 그룹** 페이지에서 조직 외부의 사용자에 게 그룹 리소스에 대 한 액세스를 허용할지, 아니면 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 할지 여부를 선택 합니다.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>관리 센터에서 Microsoft 365 그룹에 게스트 추가

게스트가 디렉터리에 이미 있는 경우 Microsoft 365 관리 센터에서 사용자를 그룹에 추가할 수 있습니다.
  
1. 관리 센터에서 **그룹** > **그룹** 페이지로 이동 합니다.
  
2. 게스트를 추가할 그룹을 클릭 하 고 **구성원** 탭에서 **모두 보기 및 구성원 관리** 를 선택 합니다. 
  
4. **구성원 추가**를 선택 하 고 추가 하려는 게스트의 이름을 선택 합니다.
    
5. **저장**을 선택합니다.

게스트를 디렉터리에 직접 추가 하려는 경우 [azure portal에서 Azure Active DIRECTORY B2B 공동 작업 사용자를 추가할](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)수 있습니다.

게스트 정보를 편집 하려는 경우 [Azure Active Directory를 사용 하 여 사용자의 프로필 정보를 추가 하거나 업데이트할](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)수 있습니다.
  
## <a name="block-guest-users-from-a-specific-group"></a>특정 그룹의 게스트 사용자 차단

대부분의 그룹에 대 한 게스트 액세스를 허용 하지만 게스트 액세스를 차단 하려는 경우에는 Microsoft PowerShell을 사용 하 여 개별 그룹에 대 한 게스트 액세스를 차단할 수 있습니다.

그룹 수준 게스트 액세스 설정을 변경 하려면 [Graph에 대 한 Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 의 preview 버전 (모듈 이름 **AzureADPreview**)을 사용 해야 합니다.

- 이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.

- AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.

- 미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.

> [!NOTE]
> 이러한 명령을 실행 하려면 전역 관리자 권한이 있어야 합니다. 

게스트 액세스를 차단 하려는 그룹 * / * 의 이름으로 변경 되는 다음 스크립트를 실행 합니다.

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
    
![게스트 그룹 액세스가 false로 설정 되었음을 보여 주는 PowerShell 창의 스크린샷](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
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

[Microsoft 365 관리 센터에서 그룹 멤버 자격 관리](add-or-remove-members-from-groups.md)
  
[Azure Active Directory 액세스 검토](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
