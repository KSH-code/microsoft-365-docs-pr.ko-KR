---
title: 격리된 SharePoint Online 팀 사이트 관리
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 격리된 SharePoint Online 팀 사이트를 관리하고, 새 사용자 및 그룹을 추가하고, 사용자 및 그룹을 제거하고, 사용자 지정 권한이 있는 문서 하위 하위폴더를 만들 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289524"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>격리된 SharePoint Online 팀 사이트 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 요금제 1](office-365-atp.md)
- SharePoint Online 

 **요약:** 다음 절차에 따라 격리된 SharePoint Online 팀 사이트를 관리합니다.

이 문서에서는 격리된 SharePoint Online 팀 사이트에 대한 일반적인 관리 작업에 대해 설명합니다.

## <a name="add-a-new-user"></a>새 사용자 추가

새 사용자가 사이트에 참가할 때 사이트의 참가 수준을 결정해야 합니다.

- 관리: 사이트 관리자 액세스 그룹에 새 사용자 계정 추가

- 활성 공동 작업: 사이트 구성원 액세스 그룹에 사용자 계정 추가

- 보기: 사이트 뷰어 액세스 그룹에 사용자 계정 추가

AD DS(Active Directory 도메인 서비스)를 통해 사용자 계정 및 그룹을 관리하는 경우 일반 AD DS 사용자 및 그룹 관리 절차를 사용하여 적절한 액세스 그룹에 적절한 사용자를 추가하고 구독과의 동기화를 기다릴 수 있습니다.

Microsoft 365를 통해 사용자 계정 및 그룹을 관리하는 경우 Microsoft 365 관리 센터 또는 Microsoft PowerShell을 사용할 수 있습니다.

- Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당된 사용자 계정으로 로그인하고 그룹을 사용하여 적절한 액세스 그룹에 적절한 사용자를 추가합니다.

- PowerShell의 경우 먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결합니다.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) UPN(사용자 계정 이름)을 사용하여 액세스 그룹에 사용자 계정을 추가하려면 다음 PowerShell 명령 블록을 사용하세요.

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

표시 이름을 사용하여 액세스 그룹에 사용자 계정을 추가하려면 다음 PowerShell 명령 블록을 사용하세요.

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>새 그룹 추가

전체 그룹에 대한 액세스를 추가하려면 사이트에 있는 그룹의 모든 구성원의 참가 수준을 결정해야 합니다.

- 관리: 사이트 관리자 액세스 그룹에 그룹 추가

- 활성 공동 작업: 사이트 구성원 액세스 그룹에 그룹 추가

- 보기: 사이트 뷰어 액세스 그룹에 그룹 추가

AD DS를 통해 사용자 계정 및 그룹을 관리하는 경우 일반 AD DS 사용자 및 그룹 관리 절차를 사용하여 적절한 그룹에 적절한 그룹을 추가하고 구독과의 동기화를 기다릴 수 있습니다.

Office 365를 통해 사용자 계정 및 그룹을 관리하는 경우 Microsoft 365 관리 센터 또는 PowerShell을 사용할 수 있습니다.

- Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당된 사용자 계정으로 로그인하고 그룹을 사용하여 적절한 액세스 그룹에 적절한 그룹을 추가합니다.

- PowerShell의 경우 먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결합니다.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 그런 다음 다음 PowerShell 명령을 사용 합니다.

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>사용자 제거

사이트에서 다른 사람의 액세스 권한을 제거해야 하는 경우 사이트 참여에 따라 현재 구성원으로 있는 액세스 그룹에서 해당 액세스 권한을 제거합니다.

- 관리: 사이트 관리자 액세스 그룹에서 사용자 계정 제거

- 활성 공동 작업: 사이트 구성원 액세스 그룹에서 사용자 계정 제거

- 보기: 사이트 뷰어 액세스 그룹에서 사용자 계정 제거

AD DS를 통해 사용자 계정 및 그룹을 관리하는 경우 일반 AD DS 사용자 및 그룹 관리 절차를 사용하여 적절한 액세스 그룹에서 해당 사용자를 제거하고 구독과의 동기화를 기다릴 수 있습니다.

Office 365를 통해 사용자 계정 및 그룹을 관리하는 경우 Microsoft 365 관리 센터 또는 PowerShell을 사용할 수 있습니다.

- Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당된 사용자 계정으로 로그인하고 그룹을 사용하여 적절한 액세스 그룹에서 해당 사용자를 제거합니다.

- PowerShell의 경우 먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결합니다.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
UPN이 있는 액세스 그룹에서 사용자 계정을 제거하려면 다음 PowerShell 명령 블록을 사용하세요.

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

표시 이름이 있는 액세스 그룹에서 사용자 계정을 제거하려면 다음 PowerShell 명령 블록을 사용하세요.

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>그룹 제거

전체 그룹에 대한 액세스를 제거하려면 사이트 참가에 따라 현재 구성원으로 있는 액세스 그룹에서 그룹을 제거합니다.

- 관리: 사이트 관리자 액세스 그룹에서 그룹 제거

- 활성 공동 작업: 사이트 구성원 액세스 그룹에서 그룹 제거

- 보기: 사이트 뷰어 액세스 그룹에서 그룹 제거

Windows Server Active Directory를 통해 사용자 계정 및 그룹을 관리하는 경우 일반 AD DS 사용자 및 그룹 관리 절차를 사용하여 적절한 액세스 그룹에서 해당 그룹을 제거하고 구독과의 동기화를 기다릴 수 있습니다.

Office 365를 통해 사용자 계정 및 그룹을 관리하는 경우 Microsoft 365 관리 센터 또는 PowerShell을 사용할 수 있습니다.

- Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당된 사용자 계정으로 로그인하고 그룹을 사용하여 적절한 액세스 그룹에서 해당 그룹을 제거합니다.

- PowerShell의 경우 먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결합니다.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
표시 이름을 사용하여 액세스 그룹에서 그룹을 제거하려면 다음 PowerShell 명령 블록을 사용 합니다.

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>사용자 지정 권한이 있는 문서 하위폴더 만들기

경우에 따라 격리된 사이트 내에서 작업하는 일부 작업자는 공동 작업을 위해 보다 개인 장소가 필요합니다. SharePoint Online 사이트의 경우 사이트의 문서 폴더에 하위 폴더를 만들고 사용자 지정 권한을 할당할 수 있습니다. 사용 권한이 없는 하위에는 하위폴더가 표시되지 않습니다.

사용자 지정 권한이 있는 문서 하위폴더를 만들하려면 다음을 합니다.

1. 사이트에 대한 관리자 액세스 그룹의 구성원인 계정에 로그인합니다. 도움을 받으려면 [Microsoft 365에 로그인하는 위치](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.

2. 격리된 팀 사이트로 이동하여 **문서를 클릭합니다.**

3. 사용자 지정 권한이 있는 하위 폴더가 포함될 문서 폴더로 찾아 폴더를 만든 다음 열어 이동합니다.

4. **공유** 를 클릭합니다.

5. 고급 **사용자와 공유를 > 클릭합니다.**

6. 사용 **권한 상속 중지를 클릭한** 다음 확인을 **클릭합니다.**

7. **공유** 를 클릭합니다.

8. 고급 **사용자와 공유를 > 클릭합니다.**

9. 고급 **사용자와 공유 > 권한 > 클릭합니다.**

10. 사용 권한 페이지에서 목록의 **\<site name> 구성원을 클릭합니다.**

11. 구성원 **\<site name> 페이지에서** 사이트 구성원 액세스 그룹 옆의 확인 표시를 선택하고 작업을 **클릭한** 다음 그룹에서 사용자 **제거를** 클릭한 다음 **확인을 클릭합니다.**

12. 이 하위폴더에 특정 구성원을 추가하려면 새 구성원을 > **클릭합니다.**

13. 공유 **대화** 상자에서 하위 폴더의 파일에 공동 작업을 할 수 있는 사용자 계정의 이름을 입력하고 공유를 **클릭합니다.**

14. 웹 페이지를 새로 고쳐 새 결과를 봐야 합니다.

15. 왼쪽  탐색의 그룹 아래에서 **\<site name> 방문자** 그룹을 클릭하고 11-14단계를 사용하여 하위 폴더의 파일을 볼 수 있는 사용자 계정 집합을 지정합니다(필요한 경우).

16. 왼쪽  탐색의 그룹 아래에서 **\<site name> Owners** 그룹을 클릭하고 11-14단계를 사용하여 하위폴더에서 사용 권한을 관리할 수 있는 사용자 계정 집합을 지정합니다(필요한 경우).

17. 브라우저에서 **사용자 및 그룹** 탭을 닫습니다.

## <a name="see-also"></a>참고 항목

[격리된 SharePoint Online 팀 사이트](isolated-sharepoint-online-team-sites.md)

[격리된 SharePoint Online 팀 사이트 디자인](design-an-isolated-sharepoint-online-team-site.md)

[격리된 SharePoint Online 팀 사이트 배포](deploy-an-isolated-sharepoint-online-team-site.md)
