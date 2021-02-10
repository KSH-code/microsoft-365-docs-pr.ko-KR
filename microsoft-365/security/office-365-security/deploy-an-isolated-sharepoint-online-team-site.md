---
title: 격리된 SharePoint Online 팀 사이트 배포
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 이 단계별 배포 가이드를 사용하여 365에서 격리된 SharePoint Online 팀 사이트를 Microsoft Office 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b1f0342afc92b4540330417ad0fc9cabe1dc8a8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165502"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>격리된 SharePoint Online 팀 사이트 배포

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Microsoft Defender for Office 365 요금제 1 및 계획 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

 **요약:** 이러한 단계별 지침에 따라 격리된 새 SharePoint Online 팀 사이트를 배포합니다.

이 문서는 365에서 격리된 SharePoint Online 팀 사이트를 만들고 구성하기 위한 단계별 Microsoft Office 가이드입니다. 이러한 단계에서는 세 가지 기본 SharePoint 그룹 및 해당 권한 수준을 각 액세스 수준에 대해 단일 Azure AD(Active Directory) 기반 액세스 그룹과 함께 사용하는 것으로 가정합니다.

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>1단계: 팀 사이트 액세스 그룹 만들기 및 채우기

이 단계에서는 세 가지 기본 SharePoint 그룹에 대해 세 개의 Azure AD 기반 액세스 그룹을 만들고 적절한 사용자 계정으로 채우습니다.

> [!NOTE]
> 다음 단계에서는 필요한 모든 사용자 계정이 이미 있으며 적절한 라이선스가 할당되어 있는 것으로 가정합니다. 그렇지 않은 경우 1단계를 진행하기 전에 라이선스를 추가하고 라이선스를 할당하십시오.

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>1단계: 사이트의 SharePoint Online 관리자 나열

격리된 팀 사이트의 SharePoint Online 관리자에 해당하는 사용자 계정 집합을 결정하십시오.

Microsoft 365를 통해 사용자 계정 및 그룹을 관리하고 Windows PowerShell 사용하려는 경우 UPN(사용자 계정 이름)(예: UPN: belindan@contoso.com) 목록을 만들어야 합니다.

### <a name="step-2-list-the-members-for-the-site"></a>2단계: 사이트의 구성원 나열

격리된 팀 사이트의 구성원, 사이트 내에 저장된 리소스에 대해 공동 작업할 구성원에 해당하는 사용자 계정 집합을 결정하십시오.

Microsoft 365를 통해 사용자 계정 및 그룹을 관리하고 PowerShell을 사용하려는 경우 해당 UPNS 목록을 만들어야 합니다. 사이트 구성원이 많은 경우 텍스트 파일에 UPNS 목록을 저장하고 모두 단일 PowerShell 명령으로 추가할 수 있습니다.

### <a name="step-3-list-the-viewers-for-the-site"></a>3단계: 사이트의 뷰어 나열

격리된 팀 사이트의 뷰어에 해당하는 사용자 계정 집합, 사이트에 저장된 리소스를 볼 수 있지만 해당 리소스를 수정하거나 콘텐츠에 대해 직접 공동 작업할 수 없는 사용자 계정 집합을 결정하십시오.

Microsoft 365를 통해 사용자 계정 및 그룹을 관리하고 PowerShell을 사용하려는 경우 해당 UPNS 목록을 만들어야 합니다. 사이트 구성원이 많은 경우 텍스트 파일에 UPNS 목록을 저장하고 모두 단일 PowerShell 명령으로 추가할 수 있습니다.

사이트의 뷰어에는 임원 관리, 법률 자문가 또는 부서 간 이해 관계자가 포함됩니다.

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>4단계: Azure AD에서 사이트에 대한 세 가지 액세스 그룹 만들기

Azure AD에서 다음 액세스 그룹을 만들어야 합니다.

- 사이트 관리자(1단계의 목록 포함)
- 사이트 구성원(2단계의 목록 포함)
- 사이트 뷰어(3단계의 목록 포함)

1. 브라우저에서 Azure Portal로 이동하여 사용자 관리 관리자 또는 회사 관리자 역할로 할당된 계정의 자격 증명으로 <https://portal.azure.com> 로그인합니다.

2. Azure Portal에서 **Azure Active Directory > 그룹** 을 차례로 클릭합니다.

3. **그룹 - 모든 그룹** 블레이드에서 **+ 새 그룹** 을 클릭합니다.

4. 새 **그룹 블레이드에서** 다음을 합니다.

   - **그룹 유형** 에서 **보안** 을 선택합니다.

   - 이름에 그룹 이름을 **입력합니다.**

   - 그룹 설명에 그룹에 대한 **설명을 입력합니다.**

   - **멤버 유형** 에서 **할당됨** 을 선택합니다.

5. **만들기** 를 클릭한 다음 **그룹** 블레이드를 닫습니다.

6. 추가 그룹에 대해 3-5단계를 반복합니다.

> [!NOTE]
> Office 기능을 사용하도록 설정하려면 Azure Portal을 사용하여 그룹을 만들어야 합니다. 격리된 SharePoint Online 사이트가 나중에 파일을 암호화하고 특정 그룹에 권한을 할당하기 위해 Azure Information Protection 레이블이 있는 기밀 사이트로 구성되는 경우 허용된 그룹은 Office 기능을 사용하도록 설정하여 만들어야 합니다. Azure AD 그룹이 만들어진 후 Office 기능 설정을 변경할 수 없습니다.

다음은 세 개의 사이트 액세스 그룹을 구성한 결과입니다.

![격리된 SharePoint Online 사이트 배포를 위한 세 가지 액세스 그룹](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>5단계. 액세스 그룹에 사용자 계정 추가

이 단계에서 다음을 합니다.

1. 1단계의 사용자 목록을 사이트 관리자 액세스 그룹에 추가합니다.
2. 2단계의 사용자 목록을 사이트 구성원 액세스 그룹에 추가합니다.
3. 3단계의 사용자 목록을 사이트 뷰어 액세스 그룹에 추가합니다.

AD DS(Active Directory 도메인 서비스)를 통해 사용자 계정 및 그룹을 관리하는 경우 일반 AD DS 사용자 및 그룹 관리 절차를 사용하여 적절한 액세스 그룹에 사용자를 추가하고 Microsoft 365 구독과의 동기화를 기다릴 수 있습니다.

Office 365를 통해 사용자 계정 및 그룹을 관리하는 경우 Microsoft 365 관리 센터 또는 PowerShell을 사용할 수 있습니다. 액세스 그룹에 대해 그룹 이름이 중복된 경우 Microsoft 365 관리 센터를 사용해야 합니다.

Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당된 사용자 계정으로 로그인하고 그룹을 사용하여 적절한 액세스 그룹에 적절한 사용자 계정 및 그룹을 추가합니다.

PowerShell의 경우 먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결합니다.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

다음으로, 다음 명령 블록을 사용하여 액세스 그룹에 개별 사용자 계정을 추가합니다.

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

액세스 그룹의 UPNS를 텍스트 파일에 저장한 경우 다음 PowerShell 명령 블록을 사용하여 모두 한 번씩 추가할 수 있습니다.

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

PowerShell의 경우 다음 명령 블록을 사용하여 액세스 그룹에 개별 그룹을 추가합니다.

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

결과는 다음과 같습니다.

- 사이트 관리자 Azure AD 그룹에 사이트 관리자 사용자 계정 또는 그룹이 포함되어 있습니다.
- 사이트 구성원 Azure AD 그룹에는 사이트 구성원 사용자 계정 또는 그룹이 포함되어 있습니다.
- 사이트 뷰어 Azure AD 그룹에는 사이트 콘텐츠만 볼 수 있는 사용자 계정 또는 그룹이 포함되어 있습니다.

Microsoft 365 관리 센터 또는 다음 PowerShell 명령 블록을 사용하여 각 액세스 그룹에 대한 그룹 구성원 목록의 유효성을 검사합니다.

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

다음은 사용자 계정 또는 그룹으로 채워진 세 개의 사이트 액세스 그룹을 구성한 결과입니다.

![사용자 계정으로 채워진 세 개의 액세스 그룹](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>2단계: 격리된 팀 사이트 만들기 및 구성

이 단계에서는 격리된 SharePoint Online 사이트를 만들고 새 Azure AD 기반 액세스 그룹을 사용하도록 기본 SharePoint Online 권한 수준에 대한 사용 권한을 구성합니다. 기본적으로 새 팀 사이트에는 Microsoft 365 그룹 및 기타 관련 리소스가 포함되어 있지만, 이 경우 Microsoft 365 그룹 없이 팀 사이트를 만들게 됩니다. 따라서 SharePoint를 통해 사용 권한을 전적으로 유지할 수 있습니다.

먼저 다음 단계를 사용하여 SharePoint Online 팀 사이트를 만들어야 합니다.

1. SharePoint Online 팀 사이트(SharePoint Online 관리자)를 관리하는 데 사용할 계정으로 Microsoft 365 관리 센터에 로그인합니다. 도움을 받으려면 [Office 365에 로그인하는 위치](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.

2. Microsoft 365 관리 센터의 **관리** 센터에서 **SharePoint를 클릭합니다.**

3. SharePoint 관리 센터에서 사이트를 **확장하고** 활성 **사이트를 클릭합니다.**

4. 만들기를 클릭한 다음 다른 **옵션을 선택합니다.** 

5. 서식 **파일 선택 목록에서** 팀 **사이트를 선택합니다.**

6. 사이트 **이름에** 팀 사이트의 이름을 입력합니다.

7. 기본 **관리자에서** 로그인한 계정을 입력합니다.

8. **마침** 을 클릭합니다.

그런 다음 새 SharePoint Online 팀 사이트에서 사용 권한을 구성합니다.

1. 도구 모음에서 설정 아이콘을 클릭한 다음, **사이트 사용 권한** 을 클릭합니다.

2. 사이트 **공유에서** 구성원이 공유할 **수 있는 방법 변경을 클릭합니다.**

3. 사이트 **소유자만 파일,** 폴더 및 사이트를 공유할 수 있습니다.

4. 액세스 **허용 요청을 해제로** **설정**

5. **저장** 을 클릭합니다.

6. 사용 권한 **창에서** 고급 사용 **권한 설정을 클릭합니다.**

7. 브라우저의 **사용** 권한 탭에서 **\<site name> 목록의 구성원을** 클릭합니다.

8. **사용자 및 그룹** 에서 **새로 만들기** 를 클릭합니다.

9. 공유 **대화** 상자에서 사이트 구성원 액세스 그룹의 이름을 입력하고 선택한 다음 공유를 **클릭합니다.**

10. 브라우저에서 뒤로 단추를 클릭합니다.

11. 목록에서 **\<site name> 소유자를** 클릭합니다.

12. **사용자 및 그룹** 에서 **새로 만들기** 를 클릭합니다.

13. 공유 **대화** 상자에 사이트 관리자 액세스 그룹의 이름을 입력하고 해당 이름을 선택한 다음 공유를 **클릭합니다.**

14. 브라우저에서 뒤로 단추를 클릭합니다.

15. 목록에서 **\<site name> 방문자를** 클릭합니다.

16. **사용자 및 그룹** 에서 **새로 만들기** 를 클릭합니다.

17. 공유 **대화** 상자에 사이트 뷰어 액세스 그룹의 이름을 입력하고 선택한 다음 공유를 **클릭합니다.**

18. 브라우저의 **권한** 탭을 닫습니다.

이러한 권한 설정의 결과는 다음과 같습니다.

- **\<site name> Owners** SharePoint 그룹에는 모든 구성원이 모든 권한 수준을 가지는 사이트 관리자 액세스 **그룹이** 포함되어 있습니다.
- Members **\<site name>** SharePoint 그룹에는 모든 구성원이 편집 권한 수준을 가지는 사이트 구성원 액세스 **그룹이** 포함되어 있습니다.
- **\<site name> Visitors** SharePoint 그룹에는 모든 구성원이 읽기 권한 수준을 가지는 사이트 뷰어 액세스 **그룹이** 포함되어 있습니다.
- 구성원이 다른 구성원을 초대하거나 구성원이 아닌 구성원이 액세스를 요청하는 기능을 사용할 수 없습니다.

사용자 계정 또는 Azure AD 그룹으로 채워지는 세 가지 액세스 그룹을 사용하도록 구성된 사이트에 대한 세 개의 SharePoint 그룹이 있는 결과 구성은 다음과 같습니다.

![액세스 그룹 및 사용자 계정을 통해 격리된 SharePoint Online 사이트의 최종 구성](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

이제 사용자와 사이트 구성원은 액세스 그룹 중 하나의 그룹 구성원 자격을 통해 사이트의 리소스를 사용하여 공동 작업을 할 수 있습니다.

## <a name="next-step"></a>다음 단계

사이트 액세스 그룹 구성원을 변경하거나 사용자 지정 권한이 있는 문서 폴더를 만들어야 하는 경우 격리된 SharePoint Online 팀 사이트 관리를 [참조하세요.](manage-an-isolated-sharepoint-online-team-site.md)

## <a name="see-also"></a>참고 항목

[격리된 SharePoint Online 팀 사이트](isolated-sharepoint-online-team-sites.md)

[격리된 SharePoint Online 팀 사이트 디자인](design-an-isolated-sharepoint-online-team-site.md)

[격리된 SharePoint Online 팀 사이트 관리](manage-an-isolated-sharepoint-online-team-site.md)
