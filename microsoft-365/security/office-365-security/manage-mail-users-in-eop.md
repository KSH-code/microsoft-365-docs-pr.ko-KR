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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 디렉터리 동기화, EAC 및 PowerShell을 사용 하 여 사용자를 관리 하는 등의 EOP (Exchange Online Protection)에서 메일 사용자를 관리 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 56e6f8955b5993fb4b5064aa92cdde80a4c67ffe
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201786"
---
# <a name="manage-mail-users-in-standalone-eop"></a>독립 실행형 EOP에서 메일 사용자 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online 사서함이 없는 독립 실행형 EOP (Exchange Online Protection) 조직에서 메일 사용자는 기본 유형의 사용자 계정입니다. 메일 사용자는 독립 실행형 EOP 조직에 계정 자격 증명을 가지 며 사용 권한이 할당 된 리소스에 액세스할 수 있습니다. 메일 사용자의 전자 메일 주소는 외부 (예: 온-프레미스 전자 메일 환경)입니다.

> [!NOTE]
> 메일 사용자를 만들 때는 Microsoft 365 관리 센터에서 해당 사용자 계정을 사용할 수 있습니다. Microsoft 365 관리 센터에서 사용자 계정을 만드는 경우 해당 계정을 사용 하 여 메일 사용자를 만들 수 없습니다.

독립 실행형 EOP에서 메일 사용자를 만들고 관리 하는 데 권장 되는 방법은이 항목 뒷부분의 [디렉터리 동기화를 사용 하 여 메일 사용자 관리](#use-directory-synchronization-to-manage-mail-users) 섹션에 설명 된 대로 디렉터리 동기화를 사용 하는 것입니다.

사용자 수가 적은 독립 실행형 EOP 조직의 경우이 항목에 설명 된 대로 EAC (Exchange 관리 센터) 또는 독립 실행형 EOP PowerShell에서 메일 사용자를 추가 하 고 관리할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- EAC (Exchange 관리 센터)를 열려면 [독립 실행형 EOP에서 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.

- 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- EOP PowerShell에서 메일 사용자를 만들 때 제한이 발생할 수 있습니다. 또한 EOP PowerShell cmdlet은 일괄 처리 방법을 사용 하 여 명령 결과가 표시 되기까지 몇 분 정도 전파 지연을 발생 시킵니다.

- 이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 특히 OrganizationManagement (전역 관리자) 및 RecipientManagement 역할 그룹에 할당 되는 메일 받는 사람 만들기 (만들기) 및 메일 받는 사람 (수정) 역할은 기본적으로 필요 합니다. 자세한 내용은 [권한 독립 실행형 EOP의 사용 권한을](feature-permissions-in-eop.md) 참조 하 고 [EAC를 사용 하 여 역할 그룹의 구성원 목록을 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)합니다.

- 이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.

> [!TIP]
> 문제가 있습니까? Exchange 포럼에서 도움을 요청하세요. [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼을 방문 합니다.

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Exchange 관리 센터를 사용 하 여 메일 사용자 관리

### <a name="use-the-eac-to-create-mail-users"></a>EAC를 사용 하 여 메일 사용자 만들기

1. EAC에서 **받는 사람** \> **연락처로** 이동 합니다.

2. **새로** ![ 만들기 아이콘 ](../../media/ITPro-EAC-AddIcon.png) 을 클릭 합니다. **새 메일 사용자** 페이지가 열리면 다음 설정을 구성 합니다. 로 표시 된 설정은 <sup>\*</sup> 필수입니다.

   - **이름**

   - **이니셜**: 사람의 중간 이니셜입니다.

   - **성**

   - <sup>\*</sup>**표시 이름**:이 상자에는 기본적으로 **이름**, **이니셜**및 **성** 상자의 값이 표시 됩니다. 이 값을 그대로 사용 하거나 변경할 수 있습니다. 이 값은 고유 해야 하며 최대 길이는 64 자입니다.

   - <sup>\*</sup>**별칭**: 사용자에 대해 최대 64 문자를 사용 하 여 고유한 별칭을 입력 합니다.

   - **외부 전자 메일 주소**: 사용자의 전자 메일 주소를 입력 합니다. 도메인은 클라우드 기반 조직 외부에 있어야 합니다.

   - <sup>\*</sup>**사용자 ID**: 사용자가 서비스에 로그인 할 때 사용할 계정을 입력 합니다. 사용자 ID는 @ 기호 왼쪽의 사용자 이름 및 오른쪽에 있는 도메인으로 구성 됩니다.

   - <sup>\*</sup>**새 암호** 및 <sup>\*</sup> **암호 확인**: 계정 암호를 입력 하 고 다시 입력 합니다. 암호가 조직의 암호 길이, 복잡도 및 기록 요구 사항을 따르는지 확인 합니다.

3. 모든 설정이 끝나면 **저장**을 클릭하여 메일 사용자를 만듭니다.

### <a name="use-the-eac-to-modify-mail-users"></a>EAC를 사용 하 여 메일 사용자 수정

1. EAC에서 **받는 사람** \> **연락처**로 이동합니다.

2. 수정할 메일 사용자를 선택 하 고 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.

3. 메일 사용자 속성 페이지가 열리면 다음 탭 중 하나를 클릭 하 여 속성을 보거나 변경 합니다.

   작업을 마쳤으면 **저장**을 클릭합니다.

#### <a name="general"></a>일반

**일반** 탭을 사용 하 여 메일 사용자에 대 한 기본 정보를 보거나 변경 합니다.

- **이름**

- **이니셜**

- **성**

- **표시 이름**:이 이름은 조직의 주소록, 전자 메일의 대상: 및 보낸 사람: 줄 및 EAC의 연락처 목록에 표시 됩니다. 표시 이름 앞뒤에는 빈 공간을 포함할 수 없습니다.

- **사용자 ID**: Microsoft 365의 사용자 계정입니다. 여기서는이 값을 수정할 수 없습니다.

#### <a name="contact-information"></a>연락처 정보

사용자의 연락처 정보를 보거나 변경 하려면 **연락처 정보** 탭을 사용 합니다. 이 페이지의 정보는 주소록에 표시됩니다.

- **주소**
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

**조직 탭을** 사용 하 여 조직에서 사용자의 역할에 대 한 세부 정보를 기록 합니다.

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>EAC를 사용 하 여 메일 사용자 제거

1. EAC에서 **받는 사람** \> **연락처**로 이동합니다.

2. 제거할 메일 사용자를 선택한 다음 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.

## <a name="use-powershell-to-manage-mail-users"></a>PowerShell을 사용 하 여 메일 사용자 관리

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>독립 실행형 EOP PowerShell을 사용 하 여 메일 사용자 보기

독립 실행형 EOP PowerShell에 있는 모든 메일 사용자의 요약 목록을 반환 하려면 다음 명령을 실행 합니다.

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

특정 메일 사용자에 대 한 자세한 정보를 보려면 \<MailUserIdentity\> 메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 명령을 실행 합니다.

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

구문 및 매개 변수에 대 한 자세한 내용은 [get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [get-help](https://docs.microsoft.com/powershell/module/exchange/get-user)를 참조 하십시오.

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>독립 실행형 EOP PowerShell을 사용 하 여 메일 사용자 만들기

독립 실행형 EOP PowerShell에서 메일 사용자를 만들려면 다음 구문을 사용 합니다.

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**참고:**

- _Name_ 매개 변수는 필수 이며, 최대 길이는 64 자 이며 고유 해야 합니다. _DisplayName_ 매개 변수를 사용하지 않는 경우에는 _Name_ 매개 변수의 값이 표시 이름에 사용됩니다.
- _Alias_ 매개 변수를 사용 하지 않으면 _MicrosoftOnlineServicesID_ 매개 변수의 왼쪽이 별칭에 사용 됩니다.
- _ExternalEmailAddress_ 매개 변수를 사용 하지 않으면 외부 전자 메일 주소에 _MicrosoftOnlineServicesID_ 값이 사용 됩니다.

이 예에서는 다음 설정을 사용 하 여 메일 사용자를 만듭니다.

- 이름은 JeffreyZeng이 고 표시 이름은 Jeffrey Zeng입니다.
- 이름은 Jeffrey고 성은 Zeng입니다.
- 별칭은 jeffreyz입니다.
- 외부 전자 메일 주소는 jzeng@tailspintoys.com입니다.
- 계정 이름은 jeffreyz@contoso.onmicrosoft.com입니다.
- 암호는 Pa$$word1입니다.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

구문 및 매개 변수에 대 한 자세한 내용은 [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)를 참조 하십시오.

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>독립 실행형 EOP PowerShell을 사용 하 여 메일 사용자 수정

독립 실행형 EOP PowerShell에서 기존 메일 사용자를 수정 하려면 다음 구문을 사용 합니다.

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

구문 및 매개 변수에 대 한 자세한 내용은 [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)를 참조 하십시오.

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>독립 실행형 EOP PowerShell을 사용 하 여 메일 사용자 제거

독립 실행형 EOP PowerShell에서 메일 사용자를 제거 하려면 \<MailUserIdentity\> 메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 명령을 실행 합니다.

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

이 예에서는 Jeffrey Zeng의 메일 사용자를 제거 합니다.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

구문 및 매개 변수에 대 한 자세한 내용은 [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)를 참조 하십시오.

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

독립 실행형 EOP에서 메일 사용자를 성공적으로 생성, 수정 또는 제거 했는지 확인 하려면 다음 절차 중 하나를 사용 하십시오.

- EAC에서 **받는 사람** \> **연락처**로 이동합니다. 메일 사용자가 나열 되어 있거나 나열 되지 않았는지 확인 합니다. 메일 사용자를 선택 하 고 세부 정보 창에서 정보를 보거나 편집 아이콘 **편집** ![ 을 클릭 ](../../media/ITPro-EAC-AddIcon.png) 하 여 설정을 확인 합니다.

- 독립 실행형 EOP PowerShell에서 다음 명령을 실행 하 여 메일 사용자가 나열 되어 있거나 나열 되지 않았는지 확인 합니다.

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- \<MailUserIdentity\>메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 명령을 실행 하 여 설정을 확인 합니다.

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>디렉터리 동기화를 사용하여 메일 사용자 관리

독립 실행형 EOP에서는 온-프레미스 Active Directory를 사용 하는 고객에 게 디렉터리 동기화를 사용할 수 있습니다. 이러한 계정을 azure AD (Active Directory)와 동기화 하 여 계정의 복사본이 클라우드에 저장 되는 것을 확인할 수 있습니다. 기존 사용자 계정을 Azure Active Directory에 동기화 하는 경우 EAC (Exchange 관리 센터)의 **받는 사람** 창이 나 독립 실행형 EOP PowerShell에서 해당 사용자를 볼 수 있습니다.

**참고:**

- 디렉터리 동기화를 사용 하 여 받는 사람을 관리 하는 경우에도 Microsoft 365 관리 센터에서 사용자를 추가 및 관리할 수 있지만 온-프레미스 Active Directory와 동기화 되지 않습니다. 디렉터리 동기화는 온-프레미스 Active Directory의 받는 사람만 클라우드로 동기화 하기 때문입니다.

- 다음 기능을 사용하려면 디렉터리 동기화를 사용하는 것이 좋습니다.

  - **Outlook 수신 허용-보낸 사람 목록 및 수신 거부 목록**: 서비스에 동기화 된 경우 이러한 목록이 서비스의 스팸 필터링 보다 우선 적용 됩니다. 이렇게 하면 개별 보낸 사람 및 도메인 항목을 사용 하 여 사용자의 수신 허용-보낸 사람의 목록 및 수신 거부 목록을 관리할 수 있습니다. 자세한 내용은 [Exchange Online 사서함에 대한 정크 메일 설정 구성하기](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes)를 참조하세요.

  - **Dbeb (디렉터리 기반 Edge 차단)**: dbeb에 대 한 자세한 내용은 [Use Directory Based edge 차단은 잘못 된 받는 사람에 게 보낸 메시지를 거부](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)합니다 .를 참조 하세요.

  - **최종 사용자에 게 격리에 대 한 액세스 권한**: 격리 된 메시지에 액세스 하려면 받는 사람에 게 서비스의 유효한 사용자 ID와 암호가 있어야 합니다. 격리에 대 한 자세한 내용은 [사용자로 격리 된 메시지 찾기 및 릴리스](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)를 참조 하세요.

  - **메일 흐름 규칙 (전송 규칙이 라고도 함)**: 디렉터리 동기화를 사용 하는 경우 기존 Active directory 사용자 및 그룹이 클라우드로 자동 업로드 되 고, 서비스에서 해당 사용자 및/또는 그룹을 수동으로 추가 하지 않고도이를 대상으로 하는 메일 흐름 규칙을 만들 수 있습니다. [동적 메일 그룹](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) 은 디렉터리 동기화를 통해 동기화 할 수 없습니다.

[Azure Active directory를 사용한 하이브리드 id 란?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)에 설명 된 대로 필요한 사용 권한을 얻고 디렉터리 동기화를 준비 합니다.

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Azure Active Directory Connect를 사용한 디렉터리 동기화 (AAD 연결)

1. [AZURE AD Connect 동기화: 이해 및 사용자 지정 동기화](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)에 설명 된 대로 디렉터리 동기화를 활성화 합니다.

2. [AZURE AD Connect 필수 구성 요소](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)에 설명 된 대로 AAD connect를 실행 하는 온-프레미스 컴퓨터를 설치 하 고 구성 합니다.

3. [AZURE AD Connect에 사용할 설치 유형을 선택 합니다](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [사용자 지정](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [통과 인증](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Azure Active Directory 동기화 도구 구성 마법사를 완료하면 Active Directory 포리스트에 **MSOL_AD_SYNC** 계정이 만들어집니다. 이 계정을 사용하여 온-프레미스 Active Directory 정보를 읽고 동기화합니다. 디렉터리 동기화가 정상적으로 작동하도록 하려면 로컬 디렉터리 동기화 서버의 TCP 443이 열려 있는지 확인합니다.

동기화를 구성한 후 AAD 연결이 제대로 동기화 되는지 확인 해야 합니다. 이렇게 하려면 EAC에서 **받는 사람** \> **연락처**로 이동한 다음 온-프레미스 환경에서 사용자 목록이 올바르게 동기화되었는지 확인합니다.
