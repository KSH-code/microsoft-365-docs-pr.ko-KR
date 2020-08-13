---
title: EOP에서 그룹 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: EOP (독립 실행형 Exchange Online Protection) 조직의 관리자는 EAC (Exchange 관리 센터) 및 EOP (독립 실행형 Exchange Online Protection) PowerShell에서 메일 그룹을 만들고, 수정 하 고, 제거 하는 방법을 알 수 있습니다.
ms.openlocfilehash: 813735d4024c3b8424a6bbac51ebef7b4c53e590
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653656"
---
# <a name="manage-groups-in-eop"></a>EOP에서 그룹 관리

Exchange Online 사서함이 없는 독립 실행형 EOP (Exchange Online Protection) 조직에서는 다음과 같은 유형의 그룹을 만들고, 수정 하 고, 제거할 수 있습니다.

- **메일 그룹**: 메일 사용자 또는 기타 메일 그룹 모음입니다. 예를 들어 일반적인 관심 영역에서 전자 메일을 수신 하거나 보내야 하는 팀 또는 기타 특별 그룹을 들 수 있습니다. 전자 메일 메시지를 배포 하는 데 단독으로 사용 되는 메일 그룹은 보안 주체가 아니라 해당 사용자에 게 할당 권한을 부여할 수 없습니다.

- **메일 사용이 가능한 보안 그룹**: 관리 역할에 대 한 액세스 권한이 필요한 메일 사용자 및 기타 보안 그룹 모음입니다. 예를 들어 특정 사용자 그룹에 게 스팸 방지 및 맬웨어 방지 설정을 구성할 수 있도록 관리자 권한을 부여할 수 있습니다.

    > [!NOTE]
    >
    > - 기본적으로 새로운 메일 사용이 가능한 보안 그룹은 인증 되지 않은 외부 보낸 사람의 메시지를 거부 합니다.
    >
    > - 메일 사용이 가능한 보안 그룹에 메일 그룹을 추가 하지 마세요.

EAC (Exchange 관리 센터) 및 독립 실행형 EOP PowerShell에서 그룹을 관리할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- Exchange 관리 센터를 열려면 [독립 실행형 EOP에서 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.

- 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 독립 실행형 EOP PowerShell에서 그룹을 관리 하는 경우 제한이 발생할 수 있습니다. 이 항목의 PowerShell 절차에서는 일괄 처리 방법을 사용 하 여 명령 결과가 표시 되기까지 몇 분 정도 전파 지연을 발생 시킵니다.

- 이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 특히 OrganizationManagement (전역 관리자) 및 RecipientManagement 역할 그룹에 기본적으로 할당 되는 메일 그룹 역할이 필요 합니다. 자세한 내용은 [권한 독립 실행형 EOP의 사용 권한을](feature-permissions-in-eop.md) 참조 하 고 [EAC를 사용 하 여 역할 그룹의 구성원 목록을 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)합니다.

- 이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.

> [!TIP]
> 문제가 있습니까? [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼에서 도움을 요청 하세요.

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Exchange 관리 센터를 사용 하 여 메일 그룹 관리

### <a name="use-the-eac-to-create-groups"></a>EAC를 사용 하 여 그룹 만들기

1. EAC에서 **받는 사람** \> **그룹**으로 이동 합니다.

2. **새로** ![ 만들기 아이콘 ](../../media/ITPro-EAC-AddIcon.png) 을 클릭 하 고 다음 옵션 중 하나를 선택 합니다.

   - **메일 그룹**

   - **메일 사용 가능 보안 그룹**

3. 새 그룹 페이지가 열리면 다음 설정을 구성 합니다. 로 표시 된 설정은 <sup>\*</sup> 필수입니다.

   - <sup>\*</sup>**표시 이름**:이 이름은 조직의 주소록, 받는 사람: 줄 (이 그룹에 전자 메일을 보낸 경우) 및 EAC의 **그룹** 목록에 표시 됩니다. 표시 이름은 필수 이며 고유 해야 하며, 사용자가 해당 항목을 인식할 수 있도록 해야 합니다.

   - <sup>\*</sup>**별칭**:이 상자에 그룹의 별칭 이름을 입력 합니다. 별칭은 64 자를 초과할 수 없으며 고유 해야 합니다. 사용자가 전자 메일 메시지의 To 줄에 별칭을 입력 하면 그룹의 표시 이름으로 확인 됩니다.

   - <sup>\*</sup>**전자 메일 주소**: 전자 메일 주소는 @ 기호 왼쪽의 별칭 및 오른쪽에 있는 도메인으로 구성 됩니다. **별칭 값** 은 기본적으로 별칭 값에 사용 되지만 변경할 수는 있습니다. 도메인 값의 경우 조직에서 드롭다운 및 선택 및 허용 도메인을 클릭 합니다.

   - **설명**:이 설명은 주소록과 EAC의 세부 정보 창에 나타납니다.

   - <sup>\*</sup>**소유자**: 그룹 소유자는 그룹 구성원을 관리할 수 있습니다. 기본적으로 그룹을 만든 사람이 소유자가 됩니다. 모든 그룹에는 한 명 이상의 소유자가 있어야 합니다.

     소유자를 추가 하려면 추가 아이콘 **추가를 클릭** ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다. 대화 상자가 나타나면 받는 사람 또는 그룹을 찾아 선택한 다음 **추가 >** 를 클릭 합니다. 필요한 만큼 이 단계를 반복합니다. 작업을 마친 후 **확인**을 클릭합니다.

     소유자를 제거 하려면 소유자를 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.

   - **구성원**: 그룹 구성원을 추가 및 제거 합니다.

     구성원을 추가 하려면 추가 아이콘 **추가를 클릭** ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다. 대화 상자가 나타나면 받는 사람 또는 그룹을 찾아 선택한 다음 **추가 >** 를 클릭 합니다. 필요한 만큼 이 단계를 반복합니다. 작업을 마친 후 **확인**을 클릭합니다.

     구성원을 제거 하려면 구성원을 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.

4. 작업이 끝나면 **저장** 을 클릭 하 여 메일 그룹을 만듭니다.

### <a name="use-the-eac-to-modify-distribution-groups"></a>EAC를 사용 하 여 메일 그룹 수정

1. EAC에서 **받는 사람** \> **그룹**으로 이동 합니다.

2. 그룹 목록에서 수정 하려는 메일 그룹을 선택 하 고 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.

3. 메일 그룹 속성 페이지가 열리면 다음 탭 중 하나를 클릭 하 여 속성을 보거나 변경 합니다.

   작업을 마쳤으면 **저장**을 클릭합니다.

#### <a name="general"></a>일반

이 탭을 사용 하 여 그룹에 대 한 기본 정보를 보거나 변경 합니다.

- **표시 이름**:이 이름은 주소록,이 그룹으로 전자 메일을 보내는 경우 받는 사람 줄, **그룹 목록**에 표시 됩니다. 표시 이름은 필수이며 다른 사람들이 알아 볼 수 있도록 친숙한 형태로 지정해야 합니다. 또한 도메인 내에서 고유해야 합니다.

  그룹 명명 규칙을 구현한 경우에는 표시 이름이 정책에 정의된 명명 규칙을 따라야 합니다.

- **별칭**: 전자 메일 주소에서 @ 기호 왼쪽에 표시 되는 부분입니다. 별칭을 변경하면 그룹의 기본 SMTP 주소도 변경되며 새 별칭을 포함하게 됩니다. 또한 이전 별칭을 사용한 전자 메일 주소는 그룹의 프록시 주소로 남아 있습니다.

- **전자 메일 주소**: 전자 메일 주소는 @ 기호 왼쪽의 별칭 및 오른쪽에 있는 도메인으로 구성 됩니다. **별칭 값** 은 기본적으로 별칭 값에 사용 되지만 변경할 수는 있습니다. 도메인 값의 경우 조직에서 드롭다운 및 선택 및 허용 도메인을 클릭 합니다.

- **설명**:이 설명은 주소록과 EAC의 세부 정보 창에 나타납니다.

#### <a name="ownership"></a>소유권

이 탭을 사용 하 여 그룹 소유자를 할당 합니다. 그룹 소유자는 그룹 구성원을 관리할 수 있습니다. 기본적으로 그룹을 만든 사람이 소유자가 됩니다. 모든 그룹에는 한 명 이상의 소유자가 있어야 합니다.

소유자를 추가 하려면 추가 아이콘 **추가를 클릭** ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다. 대화 상자가 나타나면 받는 사람을 찾아 선택 하 고 **추가 >** 를 클릭 합니다. 필요한 만큼 이 단계를 반복합니다. 작업을 마친 후 **확인**을 클릭합니다.

소유자를 제거 하려면 소유자를 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.

#### <a name="membership"></a>구성원

이 탭을 사용 하 여 그룹 구성원을 추가 하거나 제거 합니다. 그룹 소유자는 그룹의 구성원이 아니어도 됩니다.

구성원을 추가 하려면 추가 아이콘 **추가를 클릭** ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다. 대화 상자가 나타나면 받는 사람 또는 그룹을 찾아 선택한 다음 **추가 >** 를 클릭 합니다. 필요한 만큼 이 단계를 반복합니다. 작업을 마친 후 **확인**을 클릭합니다.

구성원을 제거 하려면 구성원을 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.

### <a name="use-the-eac-to-remove-groups"></a>EAC를 사용 하 여 그룹 제거

1. EAC에서 **받는 사람** \> **그룹**으로 이동 합니다.

2. 그룹 목록에서 제거할 메일 그룹을 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.

## <a name="use-powershell-to-manage-groups"></a>PowerShell을 사용 하 여 그룹 관리

### <a name="use-standalone-eop-powershell-to-view-groups"></a>독립 실행형 EOP PowerShell을 사용 하 여 그룹 보기

독립 실행형 EOP PowerShell에서 모든 메일 그룹 및 메일 사용이 가능한 보안 그룹의 요약 목록을 반환 하려면 다음 명령을 실행 합니다.

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

그룹 구성원 목록을 반환 하려면 \<GroupIdentity\> 그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행 합니다.

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

구문과 매개 변수에 대 한 자세한 내용은 Get-distributiongroupmember 및 get [-](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember) [Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) 를 참조 하십시오.

### <a name="use-standalone-eop-powershell-to-create-groups"></a>독립 실행형 EOP PowerShell을 사용 하 여 그룹 만들기

독립 실행형 EOP PowerShell에서 메일 그룹 또는 메일 사용이 가능한 보안 그룹을 만들려면 다음 구문을 사용 합니다.

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**참고**:

- _Name_ 매개 변수는 필수 이며, 최대 길이는 64 자 이며 고유 해야 합니다. _DisplayName_ 매개 변수를 사용하지 않는 경우에는 _Name_ 매개 변수의 값이 표시 이름에 사용됩니다.

- _Alias_ 매개 변수를 사용 하지 않는 경우에는 _Name_ 매개 변수가 별칭 값에 사용 됩니다. 공백은 제거 되 고 지원 되지 않는 문자는 물음표 (?)로 변환 됩니다.

- _PrimarySmtpAddress_ 매개 변수를 사용 하지 않으면 별칭 값은 _PrimarySmtpAddress_ 매개 변수에 사용 됩니다.

- _Type_ 매개 변수를 사용 하지 않으면 기본값은 분포입니다.

이 예에서는 지정 된 속성을 사용 하 여 IT 관리자 라는 메일 그룹을 만듭니다.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

구문과 매개 변수에 대 한 자세한 내용은 [set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)를 참조 하십시오.

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>독립 실행형 EOP PowerShell을 사용 하 여 그룹 수정

독립 실행형 EOP PowerShell에서 그룹을 수정 하려면 다음 구문을 사용 합니다.

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

이 예에서는 시애틀 Employees 그룹에 대 한 기본 SMTP 주소 (회신 주소 라고도 함)가 sea.employees@contoso.com로 변경 됩니다.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

이 예에서는 보안 팀 그룹의 현재 구성원을 Kitty Petersen 및 Tyson Fawcett로 바꿉니다로 대체 합니다.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

이 예에서는 Tyson Fawcett로 바꿉니다 라는 새 사용자를 Security Team 이라는 그룹에 추가 하 고 해당 그룹의 현재 구성원을 유지 합니다.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

구문 및 매개 변수에 대 한 자세한 내용은 [set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) 및 [Update-에서는 update-eopdistributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)를 참조 하십시오.

### <a name="remove-a-group-using-remote-windows-powershell"></a>원격 Windows PowerShell을 사용 하 여 그룹 제거

이 예에서는 IT Administrators 라는 메일 그룹을 제거 합니다.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

구문과 매개 변수에 대 한 자세한 내용은 [set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)를 참조 하십시오.

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

메일 그룹을 성공적으로 만들거나, 수정 하거나, 제거 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- EAC에서 **받는 사람** \> **그룹**으로 이동 합니다. 그룹이 나열 되는지, 목록에 표시 되지 않았는지, **그룹 유형** 값을 확인 합니다. 그룹을 선택 하 고 세부 정보 창에서 정보를 보거나 편집 아이콘 **편집** ![ 을 클릭 ](../../media/ITPro-EAC-AddIcon.png) 하 여 설정을 확인 합니다.

- 독립 실행형 EOP PowerShell에서 다음 명령을 실행 하 여 그룹이 나열 되는지 확인 합니다 (또는 나열 되지 않음).

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- \<GroupIdentity\>그룹의 이름, 별칭 또는 전자 메일 주소로 대체 하 고 다음 명령을 실행 하 여 설정을 확인 합니다.

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- 그룹 구성원을 보려면 \<GroupIdentity\> 그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행 합니다.

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
