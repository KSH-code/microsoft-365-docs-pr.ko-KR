---
title: 테넌트 허용/차단 목록에서 허용 및 차단된 URL 관리
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
description: 관리자는 보안 및 준수 센터의 테넌트 허용/차단 목록에서 URL & 수 있습니다.
ms.openlocfilehash: 4bf5e2e29a9f48c434be527a2447ca4bf98c4208
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660001"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록의 URL 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기로 제공되어 있으며 변경될 수 있으며 일부 조직에서는 사용할 수 없습니다.

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EOP 필터링 판정에 동의하지 않을 수 있습니다. 예를 들어 좋은 메시지는 나쁜 메시지(가음성)로 표시되거나 잘못된 메시지가 통과(거짓 부정)될 수 있습니다.

보안 및 규정 준수 센터의 테넌트 허용/차단 & Microsoft 365 필터링 판정을 수동으로 다시우는 방법을 제공합니다. 테넌트 허용/차단 목록은 메일 흐름 중과 사용자가 클릭할 때 사용됩니다. 테넌트 허용/차단 목록에서 허용하거나 차단할 URL을 지정할 수 있습니다.

이 항목에서는 보안 & 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 테넌트 허용/차단 목록의 항목을 구성하는 방법에 대해 설명합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 테넌트 **허용/차단** 목록 페이지로 직접 이동하기 위해 <https://protection.office.com/tenantAllowBlockList> 다음을 사용하세요.

- 사용 가능한 URL 값은 이 문서 부분의 테넌트 [허용/차단 목록 섹션에](#url-syntax-for-the-tenant-allowblock-list) 대한 URL 구문에 설명되어 있습니다.

- 테넌트 허용/차단 목록에는 URL에 최대 500개 항목이 허용됩니다.

- 15분 이내에 항목이 활성화됩니다.

- 차단 항목은 허용 항목보다 우선합니다.

- 기본적으로 테넌트 허용/차단 목록의 항목은 30일 후에 만료됩니다. 날짜를 지정하거나 만료되지 않는 것으로 설정할 수 있습니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.
  - 테넌트 허용/차단 목록에서 값을 추가하고 제거하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되거나 제거해야 합니다.
  - 테넌트 허용/차단 목록에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나,

  자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에 URL 항목 만들기

URL 항목의 구문에 대한 자세한 내용은 이 문서 부분의 [테넌트 허용/차단 목록 섹션에](#url-syntax-for-the-tenant-allowblock-list) 대한 URL 구문을 참조하십시오.

1. 보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**

2. **테넌트 허용/차단 목록** 페이지에서 **URL** 탭이 선택되어 있는지 확인한 다음 **추가를 클릭합니다.**

3. 나타나는 **새 URL** 추가 플라이아웃에서 다음 설정을 구성합니다.

   - **와일드카드를** 사용하여 URL 추가: 줄당 URL을 하나씩 입력하고 최대 20개까지 입력할 수 있습니다.

   - **차단/허용:** 지정한 URL을  허용할지 차단할지 여부를 선택합니다. 

   - **만료 안 하세요.** 다음 단계 중 하나를 수행합니다.

     - 설정이 꺼져 있는지(토글 해제) 확인란을 사용하여 항목의 만료 날짜를 ![ ](../../media/scc-toggle-off.png) 지정합니다. 

     또는

     - 토글을 오른쪽으로 이동하여 항목이 만료되지 않습니다. ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **선택 사항**: 항목에 대한 설명 텍스트를 입력합니다.

4. 완료되면 추가를 **클릭합니다.**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 보기

1. 보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**

2. URL **탭을** 선택합니다.

다음 열 제목을 클릭하여 오차 또는 내선 순서로 정렬합니다.

- **값**
- **작업:** **차단** **또는** 허용.
- **마지막 업데이트 날짜**
- **만료 날짜**
- **참고**

그룹을 **클릭하여** 작업(차단  또는 **허용)** 또는 없음으로 항목을 **그룹화합니다.**

검색을 **클릭하고** 값의 전체 또는 일부를 입력한 다음 Enter를 눌러 특정 값을 찾습니다. 완료되면 검색 지우기 **검색 아이콘을** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 클릭합니다.

필터를 **클릭합니다.** 필터  플라이아웃이 나타나면 다음 설정을 구성합니다.

- **작업:** **허용,** **차단** 또는 둘 다를 선택합니다.

- **만료 안**:를 선택(해제)하거나 (토글) ![ ](../../media/scc-toggle-off.png) ![ 을(를) ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 끄기.

- **Last updated**: Select a start date **(From),** an end date (**To)** or both.

- **만료 날짜:** 시작 날짜(시작 **날짜),** 종료 날짜(끝 **날짜)** 또는 둘 다를 선택합니다.

완료되면 적용을 **클릭합니다.**

기존 필터를 지우려면 **필터를** 클릭하고 나타나는 필터  플라이아웃에서 필터 **지우기 를 클릭합니다.**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 수정

URL 값 자체는 수정할 수 없습니다. 대신 항목을 삭제하고 다시 해야 합니다.

1. 보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**

2. URL **탭을** 선택합니다.

3. 수정할 항목을 선택하고 편집  ![ 아이콘을 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 클릭합니다.

4. 플라이아웃이 나타나면 다음 설정을 구성합니다.

   - **차단/허용:** 허용 **또는 차단을** **선택합니다.**

   - **만료 안 하세요.** 다음 단계 중 하나를 수행합니다.

     - 설정이 꺼져 있는지(토글 해제) 확인란을 사용하여 항목의 만료 날짜를 ![ ](../../media/scc-toggle-off.png) 지정합니다. 

     또는

     - 토글을 오른쪽으로 이동하여 항목이 만료되지 못하도록 구성합니다. ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **선택 사항**: 항목에 대한 설명 텍스트를 입력합니다.

5. 작업을 마쳤으면 **저장** 을 클릭합니다.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에서 항목 제거

1. 보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**

2. URL **탭을** 선택합니다.

3. 제거할 항목을 선택하고 삭제 **아이콘을** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 클릭합니다.

4. 나타나는 경고 대화 상자에서 삭제를 **클릭합니다.**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 테넌트 허용/차단 목록 구성

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 추가

테넌트 허용/차단 목록에 항목을 추가하기 위해 다음 구문을 사용하세요.

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

이 예제에서는 contoso.com 및 모든 하위 contoso.com, www.contoso.com 및 하위 xyz.abc.contoso.com URL 블록 항목을 추가합니다. ExpirationDate 또는 NoExpiration 매개 변수를 사용하지 않았기 때문에 항목이 30일 후에 만료됩니다.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 보기

테넌트 허용/차단 목록의 항목을 표시하기 위해 다음 구문을 사용하세요.

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

이 예제에서는 차단된 URL을 모두 반환합니다.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 수정

URL 값 자체는 수정할 수 없습니다. 대신 항목을 삭제하고 다시 해야 합니다.

테넌트 허용/차단 목록의 항목을 수정하려면 다음 구문을 사용하세요.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

이 예제에서는 지정한 항목의 만료 날짜를 변경합니다.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>PowerShell을 사용하여 테넌트 허용/차단 목록에서 항목 제거

테넌트 허용/차단 목록에서 항목을 제거하려면 다음 구문을 사용하세요.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

이 예에서는 테넌트 허용/차단 목록에서 지정된 URL 항목을 제거합니다.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에 대한 URL 구문

- IP4v 및 IPv6 주소는 허용되지만 TCP/UDP 포트는 사용할 수 없습니다.

- 파일 이름 확장명은 허용되지 않습니다(예: test.pdf.

- 유니코드는 지원되지 않지만 Punycode는 지원됩니다.

- 다음 명령문이 모두 true이면 호스트 이름을 허용합니다.

  - 호스트 이름에 기간이 포함되어 있습니다.
  - 기간 왼쪽에 하나 이상의 문자가 있습니다.
  - 기간의 오른쪽에 두 개 이상의 문자가 있습니다.

  예를 들어 허용되거나 `t.co` `.com` 허용되지 `contoso.` 않습니다.

- 하위 경로는 암시적이지 않습니다.

  예를 들어 `contoso.com` . `contoso.com/a`

- 와일드카드(*)는 다음 시나리오에서 허용됩니다.

  - 하위omain을 지정하려면 왼쪽 와일드카드 다음에 기간이 와야 합니다.

    예를 들어 `*.contoso.com` 허용됩니다. `*contoso.com` 허용되지 않습니다.

  - 오른쪽 와일드카드는 슬래시(/)를 따라 경로를 지정해야 합니다.

    예를 들어 허용되거나 `contoso.com/*` `contoso.com*` 허용되지 `contoso.com/ab*` 않습니다.

  - 모든 하위 경로는 오른쪽 와일드카드로 암시되지 않습니다.

    예를 들어 `contoso.com/*` . `contoso.com/a`

  - `*.com*` 가 잘못되었습니다(확인 가능한 도메인이 아니며 오른쪽 와일드카드가 슬래시를 따르지 않습니다).

  - 와일드카드는 IP 주소에서 허용되지 않습니다.

- 다음과 같은 시나리오에서 선조(~) 문자를 사용할 수 있습니다.

  - 왼쪽 누적은 도메인 및 모든 하위 도메인을 암시합니다.

    예를 들어 `~contoso.com` 다음을 `contoso.com` `*.contoso.com` 포함합니다.

- URL 항목은 모든 프로토콜에 적용될 수 있기 때문에 프로토콜(예: 또는 )을 포함하는 URL 항목은 `http://` `https://` `ftp://` 실패합니다.

- 사용자 이름 또는 암호는 지원되거나 필요하지 않습니다.

- 따옴표(' 또는 ")는 잘못된 문자입니다.

- URL에는 가능한 경우 모든 리디렉션이 포함되어야 합니다.

### <a name="url-entry-scenarios"></a>URL 입력 시나리오

유효한 URL 항목 및 해당 결과는 다음 섹션에 설명되어 있습니다.

#### <a name="scenario-no-wildcards"></a>시나리오: 와일드카드 없음

**항목:**`contoso.com`

- **일치 허용**: contoso.com

- **일치하지 않는 경우:**

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

**항목:**`*.contoso.com`

- **일치 및** **차단 일치 허용:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>시나리오: 경로 맨 위에 있는 오른쪽 와일드카드

**항목:**`contoso.com/a/*`

- **일치 및** **차단 일치 허용**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>시나리오: 왼쪽으로 밀기

**항목:**`~contoso.com`

- **일치 및** **차단 일치 허용:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>시나리오: 오른쪽 와일드카드 접미사

**항목:**`contoso.com/*`

- **일치 및** **차단 일치 허용:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>시나리오: 왼쪽 와일드카드 하위omain 및 오른쪽 와일드카드 접미사

**항목:**`*.contoso.com/*`

- **일치 및** **차단 일치 허용:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>시나리오: 왼쪽 및 오른쪽 바른 바른 선

**항목:**`~contoso.com~`

- **일치 및** **차단 일치 허용:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>시나리오: IP 주소

**항목:**`1.2.3.4`

- **일치 및** **차단 일치** 허용 : 1.2.3.4

- **일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>오른쪽 와일드카드가 있는 IP 주소

**항목:**`1.2.3.4/*`

- **일치 및** **차단 일치 허용:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>잘못된 항목의 예

유효하지 않은 항목은 다음과 같습니다.

- **누락되었거나 잘못된 도메인 값:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **텍스트의 와일드카드:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **포트가 있는 IP 주소:**

  - contoso.com:443
  - abc.contoso.com:25

- **설명하지 않는 와일드카드:**

  - \*
  - \*.\*

- **중간 와일드카드**:

  - conto \* so.com
  - conto~so.com

- **이중 와일드카드**

  - contoso.com/\*\*
  - contoso.com/\*/\*
