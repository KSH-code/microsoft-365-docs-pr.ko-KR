---
title: EOP에서 그룹 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: 독립 실행형 EOP(Exchange Online Protection) 조직의 관리자는 EAC(Exchange 관리 센터) 및 독립 실행형 EOP(Exchange Online Protection) PowerShell에서 메일 그룹 및 메일 사용이 가능한 보안 그룹을 만들고 수정하고 제거하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b97e3fac0840753edada964252875a6e3a4fa04
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205057"
---
# <a name="manage-groups-in-eop"></a>EOP에서 그룹 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
-  [Exchange Online Protection 독립 실행형](exchange-online-protection-overview.md)

Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 다음과 같은 유형의 그룹을 만들고 수정하고 제거할 수 있습니다.

- **메일 그룹:** 메일 사용자 또는 기타 메일 그룹의 모음입니다. 예를 들어 공통 관심 영역으로 전자 메일을 보내거나 받거나 보내야 하는 팀 또는 기타 애드 호크 그룹이 있습니다. 메일 그룹은 전자 메일 메시지를 배포하는 데만 사용할 수 있으며 보안 주체가 아니며 할당된 사용 권한을 사용할 수 없습니다.

- **메일 사용이 가능한 보안 그룹:** 관리자 역할에 대한 액세스 권한이 필요한 메일 사용자 및 기타 보안 그룹 모음입니다. 예를 들어 특정 사용자 그룹에 스팸 방지 및 맬웨어 방지 설정을 구성할 수 있도록 관리자 권한을 부여할 수 있습니다.

    > [!NOTE]
    >
    > - 기본적으로 새 메일 사용이 가능한 보안 그룹은 외부(확인되지 않은) 보낸 사람이 보낸 메시지를 거부합니다.
    >
    > - 메일 사용이 가능한 보안 그룹에 메일 그룹을 추가하지 않습니다.

EAC(Exchange 관리 센터) 및 독립 실행형 EOP PowerShell에서 그룹을 관리할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- Exchange 관리 센터를 열하려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)

- 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 독립 실행형 EOP PowerShell에서 그룹을 관리하는 경우 스로틀이 발생할 수 있습니다. 이 문서의 PowerShell 프로시저에서는 명령 결과가 표시되기 몇 분 전에 전파가 지연되는 일괄 처리 방법을 사용합니다.

- 이 문서의 절차를 수행하려면 먼저 Exchange Online Protection에서 사용 권한을 할당해야 합니다. 특히 조직 관리  및 받는 사람 관리 역할  그룹에 기본적으로 할당되는 메일 그룹 **역할이** 필요합니다. 자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한 및 EAC를 사용하여 역할 그룹의 구성원 목록 [수정을 참조하세요.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 이 문서의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 Exchange Online의 Exchange 관리 센터에 대한 바로 가기 키를 [참조하세요.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 문제가 있나요? [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 포럼에서 도움을 요청하세요.

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Exchange 관리 센터를 사용하여 메일 그룹 관리

### <a name="use-the-eac-to-create-groups"></a>EAC를 사용하여 그룹 만들기

1. EAC에서 받는 사람 **그룹 으로** \> **이동 합니다.**

2. 새로 **추가 아이콘** ![ ](../../media/ITPro-EAC-AddIcon.png) 을 클릭하고 다음 옵션 중 하나를 선택합니다.

   - **메일 그룹**

   - **메일 사용 가능 보안 그룹**

3. 새 그룹 페이지가 열리면 다음 설정을 구성합니다. 으로 표시된 <sup>\*</sup> 설정은 필수입니다.

   - <sup>\*</sup>**표시 이름:** 이 이름은 조직의 주소 책, 이 그룹에 전자 메일을 보낼 때의 To:  줄 및 EAC의 그룹 목록에 표시됩니다. 표시 이름은 필수일 수 있으며 고유해야 하며, 사용자가 인식할 수 있도록 사용자에게 친숙해야 합니다.

   - <sup>\*</sup>**별칭:** 이 상자에 그룹의 별칭 이름을 입력합니다. 별칭은 64자까지 사용할 수 있으며 고유해야 합니다. 사용자가 전자 메일 메시지의 To 줄에 별칭을 입력하면 그룹의 표시 이름으로 확인됩니다.

   - <sup>\*</sup>**전자 메일 주소:** 전자 메일 주소는 @ 기호 왼쪽의 별칭과 오른쪽에 있는 도메인으로 구성됩니다. 기본적으로 별칭 값은  별칭 값에 사용되지만 변경할 수 있습니다. 도메인 값에 대해 드롭다운을 클릭하고 조직에서 허용 도메인을 선택하고 허용합니다.

   - **설명:** 이 설명은 주소부와 EAC의 세부 정보 창에 표시됩니다.

   - <sup>\*</sup>**소유자:** 그룹 소유자가 그룹 구성원을 관리할 수 있습니다. 기본적으로 그룹을 만든 사람이 소유자가 됩니다. 모든 그룹에는 한 명 이상의 소유자가 있어야 합니다.

     소유자를 추가하려면 추가 **아이콘 추가를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다. 나타나는 대화 상자에서 받는 사람 또는 그룹을 찾아 선택한 다음 **->.** 필요한 만큼 이 단계를 반복합니다. 작업을 마친 후 **확인** 을 클릭합니다.

     소유자를 제거하려면 소유자를 선택한 다음 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.

   - **구성원:** 그룹 구성원을 추가 및 제거합니다.

     구성원을 추가하려면 추가 **아이콘 를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다. 나타나는 대화 상자에서 받는 사람 또는 그룹을 찾아 선택한 다음 **->.** 필요한 만큼 이 단계를 반복합니다. 작업을 마친 후 **확인** 을 클릭합니다.

     구성원을 제거하려면 구성원을 선택한 다음 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.

4. 완료되면 저장을 클릭하여 **메일** 그룹을 만들 수 있습니다.

### <a name="use-the-eac-to-modify-distribution-groups"></a>EAC를 사용하여 메일 그룹 수정

1. EAC에서 받는 사람 **그룹 으로** \> **이동 합니다.**

2. 그룹 목록에서 수정할 메일 그룹 또는 메일 사용이 가능한 보안 그룹을 선택하고  편집 편집 아이콘 ![ 을 ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.

3. 메일 그룹 속성 페이지가 열리면 다음 탭 중 하나를 클릭하여 속성을 보거나 변경합니다.

   작업을 마친 후 **저장** 을 클릭합니다.

#### <a name="general"></a>일반 사항

이 탭을 사용하여 그룹에 대한 기본 정보를 보거나 변경합니다.

- **표시 이름:** 이 이름은 주소 목록, 이 그룹에 전자 메일을 보낼 때의 To 줄 및 그룹 목록에 **표시됩니다.** 표시 이름은 필수이며 다른 사람들이 알아 볼 수 있도록 친숙한 형태로 지정해야 합니다. 또한 도메인 내에서 고유해야 합니다.

  그룹 명명 규칙을 구현한 경우에는 표시 이름이 정책에 정의된 명명 규칙을 따라야 합니다.

- **별칭:** 전자 메일 주소에서 @ 기호 왼쪽에 나타나는 부분입니다. 별칭을 변경하면 그룹의 기본 SMTP 주소도 변경되며 새 별칭을 포함하게 됩니다. 또한 이전 별칭을 사용한 전자 메일 주소는 그룹의 프록시 주소로 남아 있습니다.

- **전자 메일 주소:** 전자 메일 주소는 @ 기호 왼쪽의 별칭과 오른쪽에 있는 도메인으로 구성됩니다. 기본적으로 별칭 값은  별칭 값에 사용되지만 변경할 수 있습니다. 도메인 값에 대해 드롭다운을 클릭하고 조직에서 허용 도메인을 선택하고 허용합니다.

- **설명:** 이 설명은 주소부와 EAC의 세부 정보 창에 표시됩니다.

#### <a name="ownership"></a>소유권

이 탭을 사용하여 그룹 소유자를 할당합니다. 그룹 소유자는 그룹 구성원을 관리할 수 있습니다. 기본적으로 그룹을 만든 사람이 소유자가 됩니다. 모든 그룹에는 한 명 이상의 소유자가 있어야 합니다.

소유자를 추가하려면 추가 **아이콘 추가를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다. 나타나는 대화 상자에서 받는 사람을 찾아 선택한 다음 **->.** 필요한 만큼 이 단계를 반복합니다. 작업을 마친 후 **확인** 을 클릭합니다.

소유자를 제거하려면 소유자를 선택한 다음 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.

#### <a name="membership"></a>구성원

이 탭을 사용하여 그룹 구성원을 추가하거나 제거할 수 있습니다. 그룹 소유자는 그룹의 구성원일 필요가 없습니다.

구성원을 추가하려면 추가 **아이콘 를** ![ ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다. 나타나는 대화 상자에서 받는 사람 또는 그룹을 찾아 선택한 다음 **->.** 필요한 만큼 이 단계를 반복합니다. 작업을 마친 후 **확인** 을 클릭합니다.

구성원을 제거하려면 구성원을 선택한 다음 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.

### <a name="use-the-eac-to-remove-groups"></a>EAC를 사용하여 그룹 제거

1. EAC에서 받는 사람 **그룹 으로** \> **이동 합니다.**

2. 그룹 목록에서 제거할 메일 그룹을 선택하고 제거 아이콘 **를** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.

## <a name="use-powershell-to-manage-groups"></a>PowerShell을 사용하여 그룹 관리

### <a name="use-standalone-eop-powershell-to-view-groups"></a>독립 실행형 EOP PowerShell을 사용하여 그룹 보기

독립 실행형 EOP PowerShell에서 모든 메일 그룹 및 메일 사용이 가능한 보안 그룹의 요약 목록을 반환하기 위해 다음 명령을 실행합니다.

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

그룹 구성원 목록을 반환하기 위해 그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 \<GroupIdentity\> 명령을 실행합니다.

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

구문과 매개 변수에 대한 자세한 내용은 [Get-Recipient](/powershell/module/exchange/get-recipient) 및 [Get-DistributionGroupMember를 참조하십시오.](/powershell/module/exchange/get-distributiongroupmember)

### <a name="use-standalone-eop-powershell-to-create-groups"></a>독립 실행형 EOP PowerShell을 사용하여 그룹 만들기

독립 실행형 EOP PowerShell에서 메일 그룹 또는 메일 사용이 가능한 보안 그룹을 만들 경우 다음 구문을 사용 합니다.

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**참고:**

- _Name 매개_ 변수는 필수입니다. 최대 길이는 64자입니다. _DisplayName_ 매개 변수를 사용하지 않는 경우에는 _Name_ 매개 변수의 값이 표시 이름에 사용됩니다.

- _Alias_ 매개 변수를 사용하지 않는 경우 _Name_ 매개 변수가 별칭 값에 사용됩니다. 공백이 제거되고, 미지원 문자는 물음표(?)로 변환됩니다.

- _PrimarySmtpAddress_ 매개 변수를 사용하지 않는 경우 _PrimarySmtpAddress_ 매개 변수에 별칭 값이 사용됩니다.

- _Type_ 매개 변수를 사용하지 않는 경우 기본값은 Distribution입니다.

이 예에서는 지정된 속성을 사용하여 IT Administrators라는 메일 그룹을 만듭니다.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

구문과 매개 변수에 대한 자세한 내용은 [New-EOPDistributionGroup을 참조하십시오.](/powershell/module/exchange/New-EOPDistributionGroup)

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>독립 실행형 EOP PowerShell을 사용하여 그룹 수정

독립 실행형 EOP PowerShell에서 그룹을 수정하려면 다음 구문을 사용 합니다.

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

이 예에서는 Seattle Employees 그룹의 기본 SMTP 주소(회신 주소)를 변경하여 sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

이 예에서는 보안 팀 그룹의 현재 구성원을 Kitty Petersen 및 Tyson Fawcett로 바 대체합니다.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

이 예에서는 그룹의 현재 구성원을 보존하면서 Security Team이라는 그룹에 Tyson Fawcett라는 새 사용자를 추가합니다.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

구문과 매개 변수에 대한 자세한 내용은 [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) 및 [Update-EOPDistributionGroupMember를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)

### <a name="remove-a-group-using-remote-windows-powershell"></a>원격 제어를 사용하여 그룹 Windows PowerShell

이 예에서는 IT Administrators라는 메일 그룹을 제거합니다.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-EOPDistributionGroup을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

메일 그룹 또는 메일 사용이 가능한 보안 그룹을 성공적으로 만들거나 수정하거나 제거한 경우 다음 단계를 수행합니다.

- EAC에서 받는 사람 **그룹 으로** \> **이동 합니다.** 그룹이 나열되어 있는지 또는 나열되지 않는지 확인하고 그룹 유형 **값을** 검증합니다. 그룹을 선택하고 세부 정보 창에서 정보를 보거나  편집 편집 아이콘을 클릭하여 설정을 ![ ](../../media/ITPro-EAC-AddIcon.png) 확인합니다.

- 독립 실행형 EOP PowerShell에서 다음 명령을 실행하여 그룹이 나열되어 있는지(또는 목록에 없는지) 확인

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- 그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행하여 \<GroupIdentity\> 설정을 확인합니다.

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- 그룹 구성원을 확인하거나 그룹의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 \<GroupIdentity\> 명령을 실행합니다.

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```