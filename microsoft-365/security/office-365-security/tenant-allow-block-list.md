---
title: 테넌트 허용/차단 목록에서 허용되고 차단된 URL 관리
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
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 보안 및 준수 센터의 테넌트 허용/차단 목록에서 URL 항목을 구성하는 방법을 & 있습니다.
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845945"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록의 URL 관리

> [!NOTE]
> 이 항목에서 설명하는 기능은 미리 보기에 제공되고 변경될 수 있고 일부 조직에서는 사용할 수 없습니다.

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EOP 필터링 통계에 이를 집계할 수 있습니다. 예를 들어 좋은 메시지는 좋은 메시지(가양성)로 표시되거나 부정(거짓 부정)으로 표시될 수 있습니다.

보안 센터의 테넌트 허용/차단 & 목록은 Microsoft 365 필터링 결과를 수동으로 재정의하는 방법을 제공합니다. 테넌트 허용/차단 목록은 메일 흐름도 진행되는 동안 또는 사용자가 클릭할 때 사용됩니다. 테넌트 허용/차단 목록에서 허용하거나 차단할 URL을 지정할 수 있습니다.

이 항목에서는 보안 & 규정 준수 센터 또는 PowerShell(Exchange Online 사서함을 사용하는 Microsoft 365 조직의 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)의 테넌트 허용/차단 목록의 항목을 구성하는 방법에 대해 설명합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 테넌트 **허용/차단 목록 페이지로 직접 이동하려면** 다음을 사용합니다. <https://protection.office.com/tenantAllowBlockList>

- 사용 가능한 URL 값은 이 항목 뒷부분의 [테넌트 허용/차단 목록 섹션에 대한 URL](#url-syntax-for-the-tenant-allowblock-list) 구문에 설명되어 있습니다.

- 테넌트 허용/차단 목록을 통해 URL에 최대 500개의 항목을 입력할 수 있습니다.

- 15분 내에 항목을 활성화해야 합니다.

- 차단 항목은 허용 항목보다 우선합니다.

- 기본적으로 테넌트 허용/차단 목록의 항목은 30일 후에 만료됩니다. 날짜를 지정하거나 만료되지 않도록 설정할 수 있습니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 테넌트 허용/차단 목록에서 값을 추가하거나 제거하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 테넌트 허용/차단 목록에 대한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>보안 센터 보안 & 사용하여 테넌트 허용/차단 목록에 URL 항목 만들기

URL 항목에 대한 구문에 대한 자세한 내용은 이 항목 [뒷부분의 테넌트 허용/차단 목록 섹션에 대한 URL](#url-syntax-for-the-tenant-allowblock-list) 구문을 참조하세요.

1. 보안 센터 보안 & 위협 관리 정책 테넌트 **Threat management** \> **Policy** \> **허용/차단 목록으로 이동합니다.**

2. 테넌트 **허용/차단 목록 페이지에서** URL 탭이 **선택되어 있는지** 확인하고 다음 추가를 클릭합니다. **Add**

3. 표시되는 새 **URL 플라이아웃** 추가에서 다음 설정을 구성합니다.

   - **와일드카드로 URL 추가:** 한 줄당 한 URL을, 최대 20개까지 입력합니다.

   - **차단/허용:** 지정한 URL을 **허용할지 또는** **차단할지를** 선택합니다.

   - **만료 되지 않음:** 다음 단계 중 하나를 수행합니다.

     - 설정이 ![ 꺼짐(토글 해제)되어 있는지 확인하고 상자 ](../../media/scc-toggle-off.png) 상기에 따라 항목에 대한 만료 날짜를 지정합니다. **Expires on**

     또는

     - 토글을 오른쪽으로 이동하여 만료되지 않도록 항목을 구성합니다. ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.

4. 작업을 마치면 추가를 **클릭합니다.**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>보안 센터 보안 & 사용하여 테넌트 허용/차단 목록에서 항목 보기

1. 보안 센터 보안 & 위협 관리 정책 테넌트 **Threat management** \> **Policy** \> **허용/차단 목록으로 이동합니다.**

2. URL **탭을** 선택합니다.

다음 열 머리글을 클릭하여 오름차순 또는 오름차순으로 정렬합니다.

- **값**
- **작업:** **차단 또는** **허용**.
- **마지막 업데이트 날짜**
- **만료 날짜**
- **참고**

그룹을 **클릭하여** 작업(차단 또는 **허용)** **또는** **없음으로 항목을** **그룹화합니다.**

검색을 **클릭하고**모든 값을 입력한 다음 Enter 키를 눌러 특정 값을 찾습니다. Finish you're finished, click **Clear search** ![ clear search ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) icon.

필터를 **클릭합니다.** 표시되는 **필터** 플라이아웃에서 다음 설정을 구성합니다.

- **작업:** **허용선택, 차단** **또는** 둘 다를 선택합니다.

- **만료 안 됨:** 설정(토글 ![ ](../../media/scc-toggle-off.png) 해제) 또는 켜기(토글)입니다. ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

- **마지막 업데이트됨**: 시작 날짜**선택(시작 날짜)** 및 끝 날짜(끝**날짜) 또는**두 가지 모두를 선택합니다.

- **만료 날짜: 시작 날짜**선택(시작**날짜)** 및 종료 날짜(끝 날짜)**또는 둘**다를 선택합니다.

작업을 마치면 "적용"을 **클릭합니다.**

기존 필터를 지우려면 **필터를 클릭한 다음 필터**플라이아웃에서 필터 지우기를 **클릭합니다.** **Filter**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>보안 설정 준수 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 수정

URL 값은 수정할 수 없습니다. 대신 항목을 삭제하여 다시 만들어해야 합니다.

1. 보안 센터 보안 & 위협 관리 정책 테넌트 **Threat management** \> **Policy** \> **허용/차단 목록으로 이동합니다.**

2. URL **탭을** 선택합니다.

3. 수정할 항목을 선택하고 편집 아이콘을 **Edit** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 클릭합니다.

4. 플라이아웃이 나타나면 다음 설정을 구성합니다.

   - **차단/허용:** 허용 **또는** 차단 **선택.**

   - **만료 되지 않음:** 다음 단계 중 하나를 수행합니다.

     - 설정이 ![ 꺼짐(토글 해제)되어 있는지 확인하고 상자 상입기를 사용하여 ](../../media/scc-toggle-off.png) 항목의 만료 날짜를 지정합니다. **Expires on**

     또는

     - 토글을 오른쪽으로 이동하여 만료되지 않도록 항목을 구성합니다. ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **선택 사항**사항: 항목에 대한 설명 텍스트를 입력합니다.

5. 작업을 마쳤으면 **저장**을 클릭합니다.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>보안 그룹 규정 & 사용하여 테넌트 허용/차단 목록에서 항목 제거

1. 보안 센터 보안 & 위협 관리 정책 테넌트 **Threat management** \> **Policy** \> **허용/차단 목록으로 이동합니다.**

2. URL **탭을** 선택합니다.

3. 제거할 항목을 선택한 다음 삭제 아이콘을 **Delete** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 클릭합니다.

4. 표시되는 경고 대화 상자에서 ** 삭제**를 클릭합니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 테넌트 허용/차단 목록 구성

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>PowerShell을 사용하여 테넌트 허용/차단 목록에서 항목 추가

테넌트 허용/차단 목록에 항목을 추가하려면 다음 구문을 사용합니다.

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

이 예에서는 연결 로그 및 모든 하위 contoso.com(예: 검색, www.contoso.com 및 www.contoso.com)에 contoso.com 대한 URL www.contoso.com 하나xyz.abc.contoso.com. 만료 날짜 또는 NoExpiration 매개 변수를 사용하지 않기 때문에 해당 항목은 30일 후 만료됩니다.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>PowerShell을 사용하여 테넌트 허용/차단 목록에서 항목 보기

테넌트 허용/차단 목록에서 항목을 확인하려면 다음 구문을 사용합니다.

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

이 예제에서는 차단된 모든 URL을 반환합니다.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 수정

URL 값은 수정할 수 없습니다. 대신 항목을 삭제하여 다시 만들어해야 합니다.

테넌트 허용/차단 목록에서 항목을 수정하려면 다음 구문을 사용합니다.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

다음은 지정한 항목의 만료 날짜를 변경하는 예제입니다.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>PowerShell을 사용하여 테넌트 허용/차단 목록에서 항목 제거

테넌트 허용/차단 목록에서 항목을 제거하려면 다음 구문을 사용합니다.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

이 예에서는 테넌트 허용/차단 목록에서 지정된 URL 항목을 제거합니다.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에 대한 URL 구문

- IP4v 및 IPv6 주소는 허용되지만 TCP/UDP 포트는 허용되지 않습니다.

- 파일 이름 확장명은 허용되지 않습니다(예: test.pdf).

- 유니코드는 지원되지 않지만 Punycode는 다음과 같습니다.

- 다음 설명이 모두 참인 경우 호스트 이름을 사용할 수 있습니다.

  - 호스트 이름에 마침표가 포함됩니다.
  - 기계의 왼쪽에 문자가 하나 이상 있습니다.
  - 마침표의 오른쪽에 두 자 이상이 있습니다.

  예를 들어 `t.co` 허용되는지 또는 `.com` `contoso.` 허용되지 않습니다.

- 하위 경로는 암시적이지 않습니다.

  예를 들어 `contoso.com` 포함하지 `contoso.com/a` 않습니다.

- 다음과 같은 시나리오에서 와일드카드(*)를 사용할 수 있습니다.

  - 왼쪽 와일드카드 다음에 기간이 오도록 하여 하위 도메인을 지정해야 합니다.

    예를 들어 `*.contoso.com` 허용되지 `*contoso.com` 만나고 허용되지 않음

  - 오른쪽 와일드카드는 경로를 지정하기 위해 Slash(/)를 따라야 합니다.

    예를 들어 `contoso.com/*` 허용되는지 또는 `contoso.com*` `contoso.com/ab*` 허용되지 않습니다.

  - 일부 하위 경로는 오른쪽 와일드카드의 암시적이 지나지 않습니다.

    예를 들어 `contoso.com/*` 포함하지 `contoso.com/a` 않습니다.

  - `*.com*` 값이 잘못되었습니다. 확인 가능한 도메인이 아다는 것은 발밝기가 되지만 오른쪽 와일드카드가 전달(forward slash)을 따르지 않습니다.

  - IP 주소에서는 와일드카드를 사용할 수 없습니다.

- 다음과 같은 시나리오에서 는 자동데(~) 문자를 사용할 수 있습니다.

  - 왼쪽과 같은 설명은 도메인 및 모든 하위 도메인을 의미합니다.

    예를 `~contoso.com` `contoso.com` 들어 `*.contoso.com`

- URL 항목이 모든 프로토콜에 적용되므로 `http://` 이러한 `https://` 프로토콜(예: `ftp://` 또는)을 포함하는 URL 항목이 실패합니다.

- 사용자 이름 또는 암호는 지원되지 않거나 암호가 필요하지 않습니다.

- 따로 바따(' 또는 ")는 잘못된 문자입니다.

- URL에는 가능한 경우 모든 리디렉션이 포함되어야 합니다.

### <a name="url-entry-scenarios"></a>URL 항목 시나리오

다음 섹션에서는 유효한 URL 항목과 해당 결과에 대해 설명합니다.

#### <a name="scenario-no-wildcards"></a>시나리오: 와일드카드 없음

**항목:**`contoso.com`

- **Allow match**: contoso.com

- **일치하지 않음**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
- **차단 일치**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **차단과 일치하지 않는**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>시나리오: 왼쪽 와일드카드(하위 도메인)

**항목:**`*.contoso.com`

- **일치 및** 차단 **일치 허용**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **일치하지 않음 및 차단이** **일치하지 않음:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>시나리오: 경로의 위쪽와 일드카드 오른쪽

**항목:**`contoso.com/a/*`

- **일치 및** 차단 **일치 허용**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **일치하지 않음 및 차단이** **일치하지 않음:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
#### <a name="scenario-left-tilde"></a>시나리오: 왼쪽 자동열드

**항목:**`~contoso.com`

- **일치 및** 차단 **일치 허용**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **일치하지 않음 및 차단이** **일치하지 않음:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>시나리오: 오른쪽 와일드카드 접미사

**항목:**`contoso.com/*`

- **일치 및** 차단 **일치 허용**:

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **일치하지 않음 및** **차단이 일치하지 않음:** contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>시나리오: 왼쪽 와일드카드 하위 도메인 및 오른쪽 와일드카드 접미사

**항목:**`*.contoso.com/*`

- **일치 및** 차단 **일치 허용**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **일치하지 않음 및** **차단이 일치하지 않음:** contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>시나리오: 왼쪽 및 오른쪽 가로 표시

**항목:**`~contoso.com~`

- **일치 및** 차단 **일치 허용**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **일치하지 않음 및 차단이** **일치하지 않음:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>시나리오: IP 주소

**항목:**`1.2.3.4`

- **일치 및** **차단 일치 허용**: 1.2.3.4

- **일치하지 않음 및 차단이** **일치하지 않음:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>오른쪽 와일드카드를 사용한 IP 주소

**항목:**`1.2.3.4/*`

- **일치 및** 차단 **일치 허용**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>잘못된 항목의 예

다음 항목은 유효하지 않습니다.

- **누락되어 있거나 잘못된 도메인 값:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **텍스트또는 간격 지시 문자 없는 와일드카드:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **포트를 사용한 IP 주소:**

  - contoso.com:443
  - abc.contoso.com:25

- **설명이 없는 와일드카드:**

  - \*
  - \*.\*

- **중간 와일드카드:**

  - conto \* so.com
  - conto~so.com

- **이중 와일드카드**

  - contoso.com/\*\*
  - contoso.com/\*/\*
