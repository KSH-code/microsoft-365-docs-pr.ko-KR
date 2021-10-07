---
title: PowerShell을 Microsoft 365 그룹 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: 이 문서에서는 PowerShell에서 Microsoft 365 관리 작업을 수행하는 방법을 설명합니다.
ms.openlocfilehash: 603d28ce04515d70633894cab7baab62a5f1581e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150789"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>PowerShell을 Microsoft 365 그룹 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

이 문서에서는 Microsoft PowerShell에서 그룹에 대한 일반적인 관리 작업을 수행하는 단계를 제공합니다. 또한 그룹에 대한 PowerShell cmdlet을 나열합니다. 사이트 관리에 대한 자세한 SharePoint [PowerShell을](/sharepoint/manage-team-and-communication-sites-in-powershell)사용하여 SharePoint 온라인 사이트 관리를 참조하세요.

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>사용자 그룹 Microsoft 365 지침 링크
<a name="BK_LinkToGuideLines"> </a>

사용자가 [조직에서 그룹을 만들거나 편집할 Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)조직의 사용 지침에 대한 링크를 표시하면 됩니다. 예를 들어 그룹 이름에 특정 접두사나 접미사 추가가 필요한 경우

Azure AD(Azure Active Directory) PowerShell을 사용하여 사용자에게 조직의 조직 사용 지침을 Microsoft 365 있습니다. 그룹 [Azure Active Directory 구성하기 위한 cmdlet을](/azure/active-directory/enterprise-users/groups-settings-cmdlets) 확인하고 디렉터리 수준에서 설정  만들기의 단계에 따라 사용 지침 하이퍼링크를 정의합니다. AAD cmdlet을 실행하고 나면 사용자가 그룹에서 그룹을 만들거나 편집할 때 지침에 대한 링크가 Outlook.

![사용 지침 링크를 사용하여 새 그룹을 만드세요.](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![그룹 사용 지침을 클릭하여 조직에서 그룹 Office 365 확인합니다.](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>사용자가 그룹으로 보내기 허용 Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

그룹에서 "다른 Microsoft 365 보내기"를 사용하도록 설정하려면 [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) 및 [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlet을 사용하여 이를 구성합니다. 이 설정을 사용하도록 설정하면 Microsoft 365 그룹 사용자가 Outlook 웹용 Outlook 전자 메일을 보내고 회신할 수 Microsoft 365 있습니다. 사용자는 그룹으로 이동하여 새 전자 메일을 만들고 "다른 사람으로 보내기" 필드를 그룹의 전자 메일 주소로 변경할 수 있습니다.

(관리 센터에서 이 작업을 Exchange[있습니다.](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)

다음 스크립트를 사용하여 업데이트할 그룹의 별칭과 사용 권한을 부여할 사용자의 별칭으로 바랜 다음 스크립트를 *\<GroupAlias\>* *\<UserAlias\>* 사용하십시오. [커넥트 실행하기 위해 Exchange Online PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell) 실행해야 합니다.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

cmdlet이 실행되면 사용자는 그룹 전자 메일 Outlook 웹용 Outlook 보낸 사람 필드에 그룹 전자 메일 주소를 추가하여 그룹으로 보낼 수 **있습니다.**

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>조직에서 Microsoft 365 그룹에 대한 분류 만들기

조직의 사용자가 그룹을 만들 때 설정할 수 있는 민감도 레이블을 Microsoft 365 있습니다. 그룹을 분류하려는 경우 이전 그룹 분류 기능 대신 민감도 레이블을 사용하는 것이 좋습니다. 민감도 레이블 사용에 대한 자세한 내용은 민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint [사이트를 참조하세요.](../compliance/sensitivity-labels-teams-groups-sites.md)

> [!IMPORTANT]
> 현재 분류 레이블을 사용하는 경우 민감도 레이블을 사용하도록 설정하면 그룹을 만드는 사용자가 더 이상 해당 레이블을 사용할 수 없습니다.

이전 그룹 분류 기능을 계속 사용할 수 있습니다. 조직의 사용자가 그룹을 만들 때 설정할 수 있는 분류를 Microsoft 365 있습니다. 예를 들어 사용자가 만든 그룹에 대해 "표준", "비밀" 및 "최고 비밀"을 설정하도록 허용할 수 있습니다. 그룹 분류는 기본적으로 설정되지 않습니다. 사용자가 그룹 분류를 설정하려면 그룹 분류를 만들어야 합니다. PowerShell을 Azure Active Directory 사용하여 사용자가 Microsoft 365 그룹에 대한 조직의 사용 지침을 안내합니다.

그룹 [Azure Active Directory 구성하기 위한 Azure Active Directory cmdlet을](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) 확인하고 디렉터리 수준에서  설정 만들기의 단계에 따라 Microsoft 365 그룹에 대한 분류를 정의합니다.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

각 분류에 설명을 연결하려면 Settings 특성  *ClassificationDescriptions를* 사용하여 정의할 수 있습니다.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

여기서 Classification은 ClassificationList의 문자열과 일치합니다.

예제:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

위의 Azure Active Directory cmdlet을 실행하여 분류를 설정한 후 특정 그룹에 대한 분류를 설정하려는 경우 [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet을 실행합니다.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

또는 분류를 사용하여 새 그룹을 만들 수 있습니다.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

PowerShell 사용에 대한 자세한 내용은 [PowerShell을](/powershell/exchange/exchange-online-powershell) Exchange Online 커넥트 [Exchange Online PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell) 사용하여 Exchange Online 참조합니다.

이러한 설정을 사용하도록 설정하면 그룹 소유자는 웹 및 웹 페이지의 Outlook 드롭다운 메뉴에서 분류를 선택하고 Outlook 편집 페이지에서 저장할 **수** 있습니다.

![그룹 Microsoft 365 선택](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>전체 Microsoft 365 그룹 숨기기
<a name="BKMK_CreateClassification"> </a>

GAL(전체 주소 Microsoft 365) 및 조직의 기타 목록에 그룹이 나타나는지 여부를 지정할 수 있습니다. 예를 들어 주소 목록에 표시하지 않는 법률 부서 그룹이 있는 경우 해당 그룹이 GAL에 나타나지 못하게 할 수 있습니다. 다음 Set-Unified 그룹 cmdlet을 실행하여 주소 목록에서 그룹을 숨길 수 있습니다.

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>내부 사용자만 그룹으로 메시지를 Microsoft 365 허용
<a name="BKMK_CreateClassification"> </a>

다른 조직의 사용자가 Microsoft 365 그룹으로 전자 메일을 보내지 못하게 하려는 경우 해당 그룹의 설정을 변경할 수 있습니다. 내부 사용자만 그룹에 전자 메일을 보낼 수 있습니다. 외부 사용자가 해당 그룹에 메시지를 보내면 거부됩니다.

Set-UnifiedGroup cmdlet을 실행하여 이 설정을 업데이트합니다.

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>메일 그룹에 메일 Microsoft 365 추가
<a name="BKMK_CreateClassification"> </a>

보낸 사람이 Microsoft 365 그룹으로 전자 메일을 보내면 메일Tip을 볼 수 있습니다.

그룹 Set-Unified 실행하여 그룹에 메일Tip을 추가합니다.

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

메일Tip과 함께 메일Tip에 대한 추가 언어를 지정하는 MailTipTranslations를 설정할 수도 있습니다. 스페인어 번역을 사용하려는 경우 다음 명령을 실행합니다.

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>그룹의 표시 이름 Microsoft 365 변경

표시 이름은 그룹의 이름을 Microsoft 365 지정합니다. Exchange 관리 센터 또는 에서 이 이름을 볼 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터.</a> 다음 명령을 실행하여 그룹의 표시 이름을 편집하거나 기존 Microsoft 365 그룹에 표시 이름을 할당할 Set-UnifiedGroup 있습니다.

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>사용자에 대한 Microsoft 365 그룹의 기본 Outlook 또는 비공개로 변경
<a name="BKMK_CreateClassification"> </a>

Microsoft 365 그룹의 Outlook 기본적으로 비공개로 만들어집니다. 조직에서 기본적으로 Microsoft 365 그룹을 공개로 만들거나 다시 비공개로 만들 수 있도록 하려는 경우 다음 PowerShell cmdlet 구문을 사용 합니다.

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

비공개로 설정하는 경우:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

설정을 확인하면 다음을 입력합니다.

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

자세한 내용은 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) 및 [Get-OrganizationConfig를 참조합니다.](/powershell/module/exchange/get-organizationconfig)

## <a name="microsoft-365-groups-cmdlets"></a>Microsoft 365 그룹 cmdlet

다음 cmdlet은 그룹에서 사용할 Microsoft 365 있습니다.

|**cmdlet 이름**|**설명**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |이 cmdlet을 사용하여 기존 Microsoft 365 그룹을 조회하고 그룹 개체의 속성을 볼 수 있습니다.  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |Group에서 특정 속성 Microsoft 365 업데이트  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |새 그룹 Microsoft 365 만들 수 있습니다. 이 cmdlet은 최소한의 매개 변수 집합을 제공합니다. 확장 속성의 값을 설정하기 위해 새 Set-UnifiedGroup 다음에 값을 사용합니다.  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |기존 그룹 Microsoft 365 삭제  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |그룹 구성원 자격 및 소유자 정보 Microsoft 365 검색  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |기존 그룹의 구성원, 소유자 및 구독자 Microsoft 365 추가 <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |기존 그룹에서 소유자 및 Microsoft 365 제거  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |계정과 연결된 사용자 사진에 대한 정보를 보는 데 사용됩니다. 사용자 사진이 Active Directory에 저장됩니다.  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |사용자 사진을 계정과 연결하는 데 사용됩니다. 사용자 사진이 Active Directory에 저장됩니다.  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |그룹에서 사진 Microsoft 365 제거  <br/> |

## <a name="related-topics"></a>관련 항목

[메일 그룹을 Microsoft 365 업그레이드](/office365/admin/manage/upgrade-distribution-lists)

[Microsoft 365 그룹을 만들 수 있는 사용자 관리](/office365/admin/create-groups/manage-creation-of-groups)

[그룹에 대한 게스트 Microsoft 365 관리](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[정적 그룹 구성원을 동적 인으로 변경](/azure/active-directory/users-groups-roles/groups-change-type)
