---
title: 독립 실행형 EOP에서 메일 사용자 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 디렉터리 동기화, EAC 및 PowerShell을 사용하여 사용자를 관리하는 방법을 포함하여 EOP(Exchange Online Protection)에서 메일 사용자를 관리하는 방법에 대해 자세히 알아보십시오.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 34edafea7567da04094ea386d469d3d27937eee5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166396"
---
# <a name="manage-mail-users-in-standalone-eop"></a>독립 실행형 EOP에서 메일 사용자 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
-  [Exchange Online Protection 독립 실행형](https://go.microsoft.com/fwlink/?linkid=2148611)

Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 메일 사용자는 기본 유형의 사용자 계정입니다. 메일 사용자는 독립 실행형 EOP 조직에 계정 자격 증명을 가지며 리소스에 액세스할 수 있습니다(사용 권한이 할당되어 있습니다). 메일 사용자의 전자 메일 주소가 외부(예: 전자 메일 환경의 경우)입니다.

> [!NOTE]
> 메일 사용자를 만들면 Microsoft 365 관리 센터에서 해당 사용자 계정을 사용할 수 있습니다. Microsoft 365 관리 센터에서 사용자 계정을 만들 때 해당 계정을 사용하여 메일 사용자를 만들 수 없습니다.

독립 실행형 EOP에서 메일 사용자를 만들고 관리하는 권장 방법은 디렉터리 동기화 [](#use-directory-synchronization-to-manage-mail-users) 사용에 설명된 바와 같이 디렉터리 동기화를 사용하여 이 문서의 부분에 있는 메일 사용자 관리 섹션을 사용하는 것입니다.

사용자가 적은 독립 실행형 EOP 조직의 경우 이 문서에 설명된 바와 같이 EAC(Exchange 관리 센터) 또는 독립 실행형 EOP PowerShell에서 메일 사용자를 추가하고 관리할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- EAC(Exchange 관리 센터)를 열하려면 독립 실행형 [EOP에서 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)

- 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- EOP PowerShell에서 메일 사용자를 만들 때 스로틀이 발생할 수 있습니다. 또한 EOP PowerShell cmdlet은 일괄 처리 방법을 사용하여 명령 결과가 표시되기 몇 분 전에 전파 지연이 발생하게 됩니다.

- 이 문서의 절차를 수행하려면 먼저 Exchange Online Protection에서 사용 권한을 할당해야 합니다. 특히 조직 관리(전역 관리자) 및 받는 사람 관리 역할 그룹에 기본적으로 할당되는  **Mail Recipient Creation(만들기)** 및 **메일** 받는 사람(수정) 역할이 필요합니다.  자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한을 참조하고 EAC를 사용하여 역할 그룹의 구성원 목록을 [수정합니다.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 이 문서의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 [Exchange Online의 Exchange](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)관리 센터에 대한 바로 가기 키를 참조하십시오.

> [!TIP]
> 문제가 있습니까? Exchange 포럼에서 도움을 요청하세요. Exchange [Online Protection 포럼을 방문하세요.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Exchange 관리 센터를 사용하여 메일 사용자 관리

### <a name="use-the-eac-to-create-mail-users"></a>EAC를 사용하여 메일 사용자 만들기

1. EAC에서 받는 사람  \> **연락처로 이동**

2. 새로 **추가** ![ ](../../media/ITPro-EAC-AddIcon.png) 아이콘을 클릭합니다. 새 메일 **사용자** 페이지가 열리면 다음 설정을 구성합니다. 필수 설정으로 표시된 <sup>\*</sup> 설정이 필요합니다.

   - **이름**

   - **이니셜**: 사람의 중간 이니셜입니다.

   - **성**

   - <sup>\*</sup>**표시 이름:** 기본적으로 이 상자에는 **이름,** 이니셜 및 성 상자의 **값이** 표시됩니다.  이 값을 수락하거나 변경할 수 있습니다. 값은 고유해야 하며 최대 길이는 64자입니다.

   - <sup>\*</sup>**별칭:** 사용자에 대해 최대 64자를 사용하여 고유한 별칭 입력

   - **외부 전자 메일 주소:** 사용자의 전자 메일 주소를 입력합니다. 도메인은 클라우드 기반 조직 외부에 있습니다.

   - <sup>\*</sup>**사용자 ID:** 사용자가 서비스에 로그인하는 데 사용할 계정을 입력합니다. 사용자 ID는 @(@) 기호 왼쪽의 사용자 이름과 오른쪽에 있는 도메인으로 구성됩니다.

   - <sup>\*</sup>**새 암호** 및 <sup>\*</sup> **암호 확인:** 계정 암호를 입력하고 다시 입력합니다. 암호가 조직의 암호 길이, 복잡성 및 기록 요구 사항을 준수하는지 확인합니다.

3. 모든 설정이 끝나면 **저장** 을 클릭하여 메일 사용자를 만듭니다.

### <a name="use-the-eac-to-modify-mail-users"></a>EAC를 사용하여 메일 사용자 수정

1. EAC에서 **받는 사람** \> **연락처** 로 이동합니다.

2. 수정할 메일 사용자를 선택하고 편집  ![ 아이콘을 ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.

3. 열 수 있는 메일 사용자 속성 페이지에서 다음 탭 중 하나를 클릭하여 속성을 보거나 변경합니다.

   작업을 마쳤으면 **저장** 을 클릭합니다.

#### <a name="general"></a>일반 사항

일반 **탭을** 사용하여 메일 사용자에 대한 기본 정보를 보거나 변경합니다.

- **이름**

- **이니셜**

- **성**

- **표시 이름:** 이 이름은 조직의 주소 책, 전자 메일의 To: 및 From: 줄 및 EAC의 연락처 목록에 표시됩니다. 표시 이름 앞뒤에는 빈 공간을 포함할 수 없습니다.

- **사용자 ID:** Microsoft 365의 사용자 계정입니다. 여기서는 이 값을 수정할 수 없습니다.

#### <a name="contact-information"></a>연락처 정보

연락처 정보 **탭을** 사용하여 사용자의 연락처 정보를 보거나 변경합니다. 이 페이지의 정보는 주소록에 표시됩니다.

- **Street**
- **구/군/시**
- **시/도**
- **우편 번호**
- **국가/지역**
- **회사 전화**
- **휴대폰**
- **팩스**
- **기타 옵션**

  - **사무실**
  - **집 전화**
  - **웹 페이지**
  - **참고**

#### <a name="organization"></a>조직

조직 **탭을** 사용하여 조직에서 사용자 역할에 대한 자세한 정보를 기록합니다.

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>EAC를 사용하여 메일 사용자 제거

1. EAC에서 **받는 사람** \> **연락처** 로 이동합니다.

2. 제거할 메일 사용자를 선택하고 **제거** ![ 아이콘을 ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.

## <a name="use-powershell-to-manage-mail-users"></a>PowerShell을 사용하여 메일 사용자 관리

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>독립 실행형 EOP PowerShell을 사용하여 메일 사용자 보기

독립 실행형 EOP PowerShell에서 모든 메일 사용자의 요약 목록을 반환하기 위해 다음 명령을 실행합니다.

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

특정 메일 사용자에 대한 자세한 정보를 확인하려면 메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 명령을 \<MailUserIdentity\> 실행합니다.

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

구문과 매개 변수에 대한 자세한 내용은 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) 및 [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user)를 참조하십시오.

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>독립 실행형 EOP PowerShell을 사용하여 메일 사용자 만들기

독립 실행형 EOP PowerShell에서 메일 사용자를 만들 경우 다음 구문을 사용 합니다.

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**참고**:

- _Name_ 매개 변수는 필수 매개 변수로, 최대 길이는 64자입니다. _DisplayName_ 매개 변수를 사용하지 않는 경우에는 _Name_ 매개 변수의 값이 표시 이름에 사용됩니다.
- 별칭 매개 변수를  사용하지 않는 경우 _MicrosoftOnlineServicesID_ 매개 변수의 왼쪽이 별칭에 사용됩니다.
- _ExternalEmailAddress_ 매개 변수를 사용하지 않는 경우 외부 전자 메일 주소에 _MicrosoftOnlineServicesID_ 값이 사용됩니다.

이 예에서는 다음 설정을 사용하여 메일 사용자를 만듭니다.

- 이름은 JeffreyZeng, 표시 이름은 Jeffrey Zeng입니다.
- 이름은 Jeffrey고 성은 Zeng입니다.
- 별칭은 jeffreyz입니다.
- 외부 전자 메일 주소는 jzeng@tailspintoys.com입니다.
- 계정 이름이 jeffreyz@contoso.onmicrosoft.com.
- 암호는 Pa$$word1입니다.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

구문과 매개 변수에 대한 자세한 내용은 [New-EOPMailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>독립 실행형 EOP PowerShell을 사용하여 메일 사용자 수정

독립 실행형 EOP PowerShell에서 기존 메일 사용자를 수정하려면 다음 구문을 사용 합니다.

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

다음 예에서는 Pilar Pinilla의 외부 전자 메일 주소를 설정합니다.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

다음 예에서는 모든 메일 사용자의 Company 속성을 Contoso로 설정합니다.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

구문과 매개 변수에 대한 자세한 내용은 [Set-EOPMailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>독립 실행형 EOP PowerShell을 사용하여 메일 사용자 제거

독립 실행형 EOP PowerShell에서 메일 사용자를 제거하려면 메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 \<MailUserIdentity\> 명령을 실행합니다.

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

이 예에서는 Jeffrey Zeng의 메일 사용자를 제거합니다.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-EOPMailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

독립 실행형 EOP에서 메일 사용자를 성공적으로 만들거나 수정 또는 제거한 경우 다음 절차 중 원하는 절차를 수행하십시오.

- EAC에서 **받는 사람** \> **연락처** 로 이동합니다. 메일 사용자가 나열되어 있는지 또는 목록에 없는지 확인 메일 사용자를 선택하고 세부 정보 창에서 정보를 보거나  편집 아이콘을 클릭하여 설정을 ![ ](../../media/ITPro-EAC-AddIcon.png) 확인합니다.

- 독립 실행형 EOP PowerShell에서 다음 명령을 실행하여 메일 사용자가 나열되어 있는지(또는 목록에 없는지) 확인

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- 메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 명령을 실행하여 설정을 \<MailUserIdentity\> 확인합니다.

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>디렉터리 동기화를 사용하여 메일 사용자 관리

독립 실행형 EOP에서는 Exchange Active Directory가 있는 고객이 디렉터리 동기화를 사용할 수 있습니다. 계정의 복사본이 클라우드에 저장되는 Azure AD(Azure Active Directory)에 해당 계정을 동기화할 수 있습니다. 기존 사용자 계정을 Azure Active Directory와 동기화할 때 EAC(Exchange 관리 센터)의 받는 사람 창 또는 독립 실행형 EOP PowerShell에서 해당 사용자를 볼 수 있습니다. 

**참고**:

- 디렉터리 동기화를 사용하여 받는 사람을 관리하는 경우 Microsoft 365 관리 센터에서 사용자를 추가하고 관리할 수 있지만 이러한 사용자는 사용자와 동기화되지 않습니다. 이는 디렉터리 동기화가 클라우드로의 받는 사람만 동기화하기 위한 것입니다.

- 다음 기능을 사용하려면 디렉터리 동기화를 사용하는 것이 좋습니다.

  - **Outlook 수신 - 보낸** 사람 목록 및 수신 차단된 보낸 사람 목록: 서비스에 동기화할 때 이러한 목록이 서비스의 스팸 필터링보다 우선합니다. 이를 통해 사용자는 개별 보낸 사람 및 도메인 항목으로 자신의 수신 -보낸 사람 목록 및 수신 차단된 보낸 사람 목록을 관리할 수 있습니다. 자세한 내용은 [Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.

  - **DBEB(디렉터리** 기반 Edge 차단) : DBEB에 대한 자세한 내용은 디렉터리 기반 Edge 차단을 사용하여 잘못된 받는 사람에게 보낸 메시지를 [거부합니다.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

  - **최종 사용자에** 대한 인증 액세스: 받는 사람이 해당 메시지에 액세스하려면 서비스에서 유효한 사용자 ID와 암호가 있어야 합니다. Quarantine에 대한 자세한 내용은 사용자로 고지된 메시지 찾기 및 [릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)

  - **메일 흐름 규칙(전송** 규칙) : 디렉터리 동기화를 사용하는 경우 기존 Active Directory 사용자 및 그룹이 클라우드에 자동으로 업로드되며, 그런 다음 서비스에 수동으로 추가할 필요 없이 특정 사용자 및/또는 그룹을 대상으로 하는 메일 흐름 규칙을 만들 수 있습니다. 동적 메일 [그룹은](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) 디렉터리 동기화를 통해 동기화할 수 없습니다.

Azure Active Directory의 하이브리드 ID란? 설명에 따라 필요한 사용 권한을 얻고 디렉터리 [동기화를 준비합니다.](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Azure Active Directory Connect(AAD Connect)와 디렉터리 동기화

1. Azure AD Connect 동기화에 설명된 대로 디렉터리 동기화 활성화: 동기화 이해 및 [사용자 지정.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

2. Azure AD Connect의 선행 구성에 설명된 바와 같이 AAD Connect를 실행하도록 On-premises 컴퓨터를 설치 [및 구성합니다.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Azure AD Connect에 사용할 설치 유형을 선택합니다.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [사용자 지정](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [통과 인증](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Azure Active Directory 동기화 도구 구성 마법사를 완료하면 Active Directory 포리스트에 **MSOL_AD_SYNC** 계정이 만들어집니다. 이 계정을 사용하여 온-프레미스 Active Directory 정보를 읽고 동기화합니다. 디렉터리 동기화가 정상적으로 작동하도록 하려면 로컬 디렉터리 동기화 서버의 TCP 443이 열려 있는지 확인합니다.

동기화를 구성한 후 AAD Connect가 올바르게 동기화하고 있는지 확인해야 합니다. 이렇게 하려면 EAC에서 **받는 사람** \> **연락처** 로 이동한 다음 온-프레미스 환경에서 사용자 목록이 올바르게 동기화되었는지 확인합니다.
