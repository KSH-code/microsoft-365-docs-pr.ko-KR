---
title: 테넌트 허용/차단 목록에서 허용 및 차단 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 보안 포털의 테넌트 허용/차단 목록에서 허용 및 차단을 관리하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aca302aedfaa97b9e2661716d7bc7a6e846fa6fb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214242"
---
# <a name="manage-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> 이 문서에 설명된 일부 기능은 미리 보기에 있으며 변경될 수 있으며 일부 조직에서는 사용할 수 없습니다.
>
> 이 문서에 설명된 스푸핑 기능이 조직에 없는 경우 [EOP에서](walkthrough-spoof-intelligence-insight.md)스푸핑 인텔리전스 정책을 사용하여 스푸핑된 보낸 사람 관리에서 이전 스푸핑 관리 환경을 참조하세요.

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 Exchange Online EOP 필터링 판정에 동의하지 않을 수 있습니다. 예를 들어 양호한 메시지는 나쁜 메시지(가음성)로 표시되거나 잘못된 메시지가 통과(거짓 부정)로 표시될 수 있습니다.

테넌트 포털의 테넌트 허용/차단 Microsoft 365 Defender 필터링 판정을 수동으로 Microsoft 365 방법을 제공합니다. 테넌트 허용/차단 목록은 들어오는 메시지에 대한 메일 흐름(반기 메시지에는 적용되지 않습니다)과 사용자 클릭 시에 사용됩니다. 다음과 같은 유형의 다시 지정을 지정할 수 있습니다.

- 차단할 URL입니다.
- 차단할 파일입니다.
- 차단할 보낸 사람 전자 메일 또는 도메인입니다.
- 허용하거나 차단할 스푸핑된 보낸 사람입니다. 스푸핑 인텔리전스 인사이트에서 [](learn-about-spoof-intelligence.md)허용 또는 차단 판정을 다시 설정하면 스푸핑된 보낸 사람이 테넌트 허용/차단 목록의 스푸핑 탭에만 나타나는 수동 허용 또는 차단 항목이 됩니다.  스푸핑 인텔리전스에서 검색되기 전에 여기에 스푸핑된 보낸 사람에 대한 허용 또는 차단 항목을 수동으로 만들 수도 있습니다.
- 허용할 URL입니다.
- 허용할 파일입니다.
- 허용할 보낸 사람 전자 메일 또는 도메인입니다.

이 문서에서는 Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 테넌트 허용/차단 목록의 항목을 구성하는 방법에 대해 설명하고 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com/>에서 Microsoft 365 Defender 포털을 엽니다. 테넌트 **허용/차단** 목록 페이지로 직접 이동하기 위해 를 <https://security.microsoft.com/tenantAllowBlockList> 사용하세요.

- 파일의 SHA256 해시 값을 사용하여 파일을 지정합니다. 파일에서 파일의 SHA256 해시 값을 Windows 명령 프롬프트에서 다음 명령을 실행합니다.

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  값의 예로는 를 들 수 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 있습니다. pHash(지각 해시) 값은 지원되지 않습니다.

- 사용 가능한 URL 값은 이 문서 부분의 [테넌트 허용/차단](#url-syntax-for-the-tenant-allowblock-list) 목록 섹션에 대한 URL 구문에 설명되어 있습니다.

- 테넌트 허용/차단 목록을 사용하면 보낸 사람에 대해 최대 500개 항목, URL 항목 500개, 파일 해시 항목 500개, 스푸핑(스푸핑된 보낸 사람)에 대한 항목 1024개가 허용됩니다.

- 각 항목의 최대 문자 수는 다음입니다.
  - 파일 해시 = 64
  - URL = 250

- 항목이 30분 이내에 활성화됩니다.

- 기본적으로 테넌트 허용/차단 목록의 항목은 30일 후에 만료됩니다. 날짜를 지정하거나 만료되지 않는 날짜로 설정할 수 있습니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 게시물의 절차를 수행하려면 먼저 Exchange Online에서 사용 권한을 할당받아야 합니다.
  - **보낸 사람, URL 및 파일**:
    - 테넌트 허용/차단 목록에서 값을 추가 및 제거하려면 조직 **관리,** 보안 관리자  또는 보안 운영자 역할 그룹의 구성원 또는 테넌트 **AllowBlockList 관리자** 역할이 할당되어 있습니다.
    - 테넌트 허용/차단 목록에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 해야 합니다.
  - **스푸핑:** 다음 조합 중 하나
    - **조직 관리**
    - **보안 관리자** <u>및</u> 보기 전용 **구성** 또는 보기 전용 **조직 관리.**

  자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  > [!NOTE]
  >
  > - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹도 기능에 대한 읽기 전용 권한을 부여합니다.

## <a name="configure-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록 구성

### <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 포털 사용

Microsoft 365 Defender 포털에서 정책 &  규칙 규칙 \>  \>  섹션 \> **테넌트 허용/차단 목록으로 이동하세요.**

모든 블록을 추가하기 위해 [테넌트 허용/차단 목록에서 블록 추가를 참조하세요.](manage-tenant-blocks.md)

모든 허용을 추가하기 위해 [테넌트 허용/차단 목록에서 허용 추가를 참조하세요.](manage-tenant-allows.md)

모든 블록을 수정 및 제거하고 허용하려면 테넌트 허용/차단 목록의 항목 수정 [및 제거를 참조하세요.](modify-remove-entries-tenant-allow-block.md)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell"></a>PowerShell Exchange Online 독립 실행형 EOP PowerShell 사용

모든 허용 및 차단을 관리하려면 [테넌트 허용/차단](manage-tenant-blocks.md)목록의 블록 추가, 테넌트 [허용/차단](manage-tenant-allows.md)목록에서 허용 추가 및 테넌트 허용/차단 목록의 항목 수정 및 제거를 [참조하세요.](modify-remove-entries-tenant-allow-block.md)

## <a name="view-entries-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록의 항목 보기

1. Microsoft 365 Defender 포털에서 정책 &  규칙 규칙 \>  \>  섹션 \> **테넌트 허용/차단 목록으로 이동하세요.**

2. 원하는 탭을 선택합니다. 사용 가능한 열은 선택한 탭에 따라 다를 수 있습니다.

   - **보낸 사람**:
     - **값:** 보낸 사람 도메인 또는 전자 메일 주소입니다.
     - **작업**: 허용 또는 **차단** **값입니다.**
     - **마지막 업데이트**
     - **제거**
     - **참고**
   - **URL**:
     - **값:** URL입니다.
     - **작업**: 허용 또는 **차단** **값입니다.**
     - **마지막 업데이트**
     - **제거**
     - **참고**
   - **파일**
     - **값:** 파일 해시입니다.
     - **작업**: 허용 또는 **차단** **값입니다.**
     - **마지막 업데이트**
     - **제거**
     - **참고**
   - **스푸핑**
     - **스푸핑된 사용자**
     - **인프라 보내기**
     - **스푸핑 유형**: 내부 또는 외부 **값입니다.** 
     - **작업**: 값 **Block** 또는 **Allow입니다.**

   열 제목을 클릭하여 오차 또는 내선 순서로 정렬할 수 있습니다.

   그룹을 **클릭하여** 결과를 그룹화할 수 있습니다. 사용 가능한 값은 선택한 탭에 따라 다를 수 있습니다.

   - **보낸 사람**: 작업을 사용하여 결과를 그룹화할 **수 있습니다.**
   - **URL:** 작업을 사용하여 결과를 그룹화할 수 **있습니다.**
   - **파일**: 작업을 사용하여 결과를 그룹화할 **수 있습니다.**
   - **스푸핑**: 작업 또는 스푸핑 유형별로 결과를 **그룹화할 수 있습니다.** 

   **검색을** 클릭하고 값의 전체 또는 일부를 입력한 다음 Enter를 눌러 특정 값을 찾습니다. 완료되면 검색 아이콘 ![ 지우기 를 클릭합니다.](../../media/m365-cc-sc-close-icon.png) **검색 지우기**.

   **필터를** 클릭하여 결과를 필터링합니다. 필터 플라이아웃에서  사용할 수 있는 값은 선택한 탭에 따라 다를 수 있습니다.

   - **보낸 사람**
     - **작업**
     - **만료되지 않습니다.**
     - **마지막으로 업데이트된 날짜**
     - **제거**
   - **URL**
     - **작업**
     - **만료되지 않습니다.**
     - **마지막으로 업데이트된 날짜**
     - **제거**
   - **파일**
     - **작업**
     - **만료되지 않습니다.**
     - **마지막 업데이트**
     - **제거**
   - **스푸핑**
     - **작업**
     - **스푸핑 유형**

   완료되면 **적용** 을 클릭합니다. 기존 필터를 지우려면 **필터를** 클릭하고 나타나는 필터  플라이아웃에서 필터 **지우기 를 클릭합니다.**

4. 작업을 마쳤으면 **추가** 를 클릭합니다.

## <a name="view-sender-file-or-url-entries-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에서 보낸 사람, 파일 또는 URL 항목 보기

테넌트 허용/차단 목록에서 보낸 사람, 파일 또는 URL 항목을 보거나 차단할 경우 다음 구문을 사용합니다.

```powershell
Get-TenantAllowBlockListItems -ListType <Sender | FileHash | URL> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

이 예제에서는 지정한 파일 해시 값에 대한 정보를 반환합니다.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

이 예제에서는 차단된 URL을 모두 반환합니다.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/get-tenantallowblocklistitems)

## <a name="view-spoofed-sender-entries"></a>스푸핑된 보낸 사람 항목 보기

테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목을 보고 다음 구문을 사용하세요.

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

이 예에서는 테넌트 허용/차단 목록에 있는 스푸핑된 보낸 사람 항목을 모두 반환합니다.

```powershell
Get-TenantAllowBlockListSpoofItems
```

이 예에서는 내부에 있는 스푸핑된 보낸 사람 항목을 모두 반환합니다.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

이 예에서는 외부에 있는 차단된 스푸핑된 보낸 사람 항목을 모두 반환합니다.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에 대한 URL 구문

- IP4v 및 IPv6 주소는 사용할 수 있지만 TCP/UDP 포트는 사용할 수 없습니다.

- 파일 이름 확장명은 허용되지 않습니다(예: test.pdf).

- 유니코드는 지원되지 않지만 Punycode는 지원됩니다.

- 다음 명령문이 모두 true이면 호스트 이름을 허용합니다.
  - 호스트 이름에는 기간이 포함되어 있습니다.
  - 기간 왼쪽에 하나 이상의 문자가 있습니다.
  - 이 기간의 오른쪽에는 두 개 이상의 문자가 있습니다.

  예를 들어 `t.co` 허용되거나 `.com` `contoso.` 허용되지 않습니다.

- 하위 경로는 암시적이지 않습니다.

  예를 들어 `contoso.com` 를 포함하지 `contoso.com/a` 않습니다.

- 와일드카드(*)는 다음과 같은 시나리오에서 허용됩니다.

  - 하위omain을 지정하려면 왼쪽 와일드카드 다음에 기간이 와야 합니다.

    예를 들어 `*.contoso.com` 허용됩니다. `*contoso.com` 허용되지 않습니다.

  - 오른쪽 와일드카드는 슬래시(/)를 따라 경로를 지정해야 합니다.

    예를 들어 `contoso.com/*` 허용되거나 `contoso.com*` `contoso.com/ab*` 허용되지 않습니다.

  - `*.com*` 가 잘못되었습니다(확인 가능한 도메인이 아니며 오른쪽 와일드카드가 슬래시를 따르지 않습니다).

  - 와일드카드는 IP 주소에서 허용되지 않습니다.

- 다음 시나리오에서는 선조(~) 문자를 사용할 수 있습니다.

  - 왼쪽 밀기선은 도메인과 모든 하위 도메인을 암시합니다.

    예를 들어 `~contoso.com` 및 `contoso.com` `*.contoso.com` 을 포함합니다.

- URL 항목이 모든 프로토콜에 적용될 수 있기 때문에 프로토콜(예: , 또는 )이 포함된 URL 항목은 `http://` `https://` `ftp://` 실패합니다.

- 사용자 이름 또는 암호는 지원되거나 필요하지 않습니다.

- 따옴표(' 또는 ")는 잘못된 문자입니다.

- URL에는 가능한 경우 모든 리디렉션이 포함되어야 합니다.

### <a name="url-entry-scenarios"></a>URL 입력 시나리오

유효한 URL 항목 및 해당 결과는 다음 섹션에 설명되어 있습니다.

#### <a name="scenario-no-wildcards"></a>시나리오: 와일드카드 없음

**항목**: `contoso.com`

- **일치 허용**: contoso.com

- **일치하지 않는 허용**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **블록 일치**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **블록이 일치하지 않는 경우**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>시나리오: 왼쪽 와일드카드(하위omain)

**항목**: `*.contoso.com`

- **일치 및** **차단 일치 허용**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>시나리오: 경로 맨 위에 있는 오른쪽 와일드카드

**항목**: `contoso.com/a/*`

- **일치 및** **차단 일치 허용**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>시나리오: 왼쪽 밀기

**항목**: `~contoso.com`

- **일치 및** **차단 일치 허용**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>시나리오: 오른쪽 와일드카드 접미사

**항목**: `contoso.com/*`

- **일치 및** **차단 일치 허용**:

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>시나리오: 왼쪽 와일드카드 하위omain 및 오른쪽 와일드카드 접미사

**항목**: `*.contoso.com/*`

- **일치 및** **차단 일치 허용**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>시나리오: 왼쪽 및 오른쪽 밀기

**항목**: `~contoso.com~`

- **일치 및** **차단 일치 허용**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>시나리오: IP 주소

**항목**: `1.2.3.4`

- **일치 및** **차단 일치** 허용 : 1.2.3.4

- **일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>오른쪽 와일드카드가 있는 IP 주소

**항목**: `1.2.3.4/*`

- **일치 및** **차단 일치 허용**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>잘못된 항목의 예

다음 항목이 잘못되었습니다.

- **누락되었거나 잘못된 도메인 값**:

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **텍스트의 와일드카드 또는 간격 문자가 없는** 경우 :

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **포트가 있는 IP 주소:**

  - contoso.com:443
  - abc.contoso.com:25

- **설명이 없는 와일드카드**:

  - \*
  - \*.\*

- **중간 와일드카드**:

  - conto \* so.com
  - conto~so.com

- **이중 와일드카드**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록의 스푸핑된 보낸 사람 항목에 대한 도메인 쌍 구문

테넌트 허용/차단 목록에서 스푸핑된 보낸 사람에 대한 도메인 쌍은 다음 구문을 사용 `<Spoofed user>, <Sending infrastructure>` 합니다. .

- **스푸핑된 사용자:** 이 값은 전자 메일 클라이언트의 시작 상자에 표시되는  스푸핑된 사용자의 전자 메일 주소와 관련됩니다. 이 주소를 `5322.From` 주소라고도 합니다. 사용할 수 있는 값은 다음과 같습니다.
  - 개별 전자 메일 주소(예: chris@contoso.com).
  - 전자 메일 도메인(예: contoso.com.
  - 와일드카드 문자(예: \* ).

- **보내는 인프라:** 이 값은 스푸핑된 사용자의 메시지 원본을 나타냅니다. 사용할 수 있는 값은 다음과 같습니다.
  - 원본 전자 메일 서버의 IP 주소(예: PTR 레코드)의 역방향 DNS fabrikam.com.
  - 원본 IP 주소에 PTR 레코드가 없는 경우 보내는 인프라는 \<source IP\> /24(예: 192.168.100.100/24)로 식별됩니다.

다음은 스푸핑된 보낸 사람 식별을 위한 유효한 도메인 쌍의 몇 가지 예입니다.

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

스푸핑된 보낸 사람 항목의 최대 수는 1000개입니다.

도메인 쌍을 추가하면 스푸핑된 사용자와 보내는 인프라의 조합만 허용하거나 *차단할* 수 있습니다.  또한 모든 원본에서 스푸핑된 사용자의 전자 메일을 허용하지 않으며, 스푸핑된 사용자에 대해 보내는 인프라 원본의 전자 메일을 허용하지 않습니다. 

예를 들어 다음 도메인 쌍에 대해 허용 항목을 추가합니다.

- **도메인**: gmail.com
- **인프라:** tms.mx.com

해당 도메인 및  보내는 인프라 쌍의 메시지만 스푸핑할 수 있습니다. 스푸핑을 시도하는 gmail.com 허용되지 않습니다. 다른 도메인의 보낸 사람이 보낸 메시지는 tms.mx.com 인텔리전스를 통해 확인됩니다.
