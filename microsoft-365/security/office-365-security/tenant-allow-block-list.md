---
title: 테 넌 트 허용/차단 목록에서 허용 및 차단 되는 Url 및 파일 관리
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
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 보안 & 준수 센터의 테 넌 트 허용/차단 목록에서 URL 및 파일 항목을 구성 하는 방법을 알아봅니다.
ms.openlocfilehash: db34abf28b5ead8106eb0b1447052d63072b2da3
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391569"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록의 URL과 파일 관리

> [!NOTE]
> 이 항목에서 설명 하는 기능은 미리 보기에 있으며, 변경 될 수 있으며, 일부 조직에서는 제공 되지 않습니다.

Exchange online 사서함을 사용 하지 않는 exchange Online 또는 독립 실행형 EOP (Exchange Online Protection) 조직의 사서함이 있는 Microsoft 365 조직에서는 EOP 필터링 결과에 동의할 수 없습니다. 예를 들어 좋은 메시지는 불량 (가양성)으로 표시 되거나 잘못 된 메시지 (가양성)를 통해 허용 될 수 있습니다.

보안 & 준수 센터의 테 넌 트 허용/차단 목록에서는 Microsoft 365 필터링 verdicts를 수동으로 다시 정의할 수 있는 방법을 제공 합니다. 메일 흐름 중 및 사용자가 클릭 했을 때의 테 넌 트 허용/차단 목록이 사용 됩니다. 테 넌 트 허용/차단 목록에서 허용 하거나 차단할 Url 및 파일을 지정할 수 있습니다.

이 항목에서는 보안 & 준수 센터 또는 PowerShell (exchange online 사서함이 없는 조직에 대해 exchange Online의 사서함이 있는 Microsoft 365 조 직의 경우 Exchange online PowerShell)의 테 넌 트 허용/차단 목록에서 항목을 구성 하는 방법에 대해 설명 합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **테 넌 트 허용/차단 목록** 페이지로 바로 이동 하려면를 사용 <https://protection.office.com/tenantAllowBlockList> 합니다.

- 파일의 SHA256 해시 값을 사용 하 여 파일을 지정 합니다. Windows에서 파일의 SHA256 해시 값을 찾으려면 명령 프롬프트에서 다음 명령을 실행 합니다.

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  예를 들면 값은 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 입니다. PHash (가시 범위 해시) 값은 허용 되지 않습니다.

- 사용 가능한 URL 값은이 항목 뒷부분의 [테 넌 트 허용/차단 목록 섹션에 대 한 URL 구문](#url-syntax-for-the-tenant-allowblock-list) 에 설명 되어 있습니다.

- 테 넌 트 허용/차단 목록에서 Url에 대해 최대 500 항목을 허용 하 고 파일 해시에 대해 500 항목을 사용할 수 있습니다.

- 15 분 내에 항목을 활성화 해야 합니다.

- 차단 항목은 허용 항목 보다 우선적으로 적용 됩니다.

- 기본적으로 테 넌 트 허용/차단 목록의 항목은 30 일 후에 만료 됩니다. 날짜를 지정 하거나 만료 되지 않도록 설정할 수 있습니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 테 넌 트 허용/차단 목록에서 값을 추가 및 제거 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 테 넌 트 허용/차단 목록에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록에 URL 항목 만들기

URL 항목의 구문에 대 한 자세한 내용은이 항목 뒷부분의 [테 넌 트 허용/차단 목록 섹션에 대 한 URL 구문을](#url-syntax-for-the-tenant-allowblock-list) 참조 하십시오.

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.

2. **테 넌 트 허용/차단 목록** 페이지에서 **url** 탭이 선택 되어 있는지 확인 한 다음 **추가** 를 클릭 합니다.

3. **새 Url 추가** 플라이 아웃이 나타나면 다음 설정을 구성 합니다.

   - **와일드 카드를 사용 하 여 Url 추가**: 한 줄당 url을 하나씩 입력 합니다 (최대 20 개).

   - **차단/허용**: 지정 된 Url을 **허용** 하거나 **차단할지** 여부를 선택 합니다.

   - 사용 **기간 제한 없음**: 다음 단계 중 하나를 수행 합니다.

     - 설정이 꺼져 있는지 ( ![ 토글 해제)를 확인 하 ](../../media/scc-toggle-off.png) 고 **만료** 날짜 상자를 사용 하 여 항목의 만료일을 지정 합니다.

     또는

     - 오른쪽으로 토글을 이동 하 여 만료 되지 않도록 항목을 구성 합니다. ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **선택 사항**: 항목에 대 한 설명 텍스트를 입력 합니다.

4. 작업이 완료 되 면 **추가**를 클릭 합니다.

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록에 파일 항목 만들기

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.

2. **테 넌 트 허용/차단 목록** 페이지에서 **파일** 탭을 선택 하 고 **추가**를 클릭 합니다.

3. **새 파일** 플라이 아웃 추가 표시 되 면 다음 설정을 구성 합니다.

   - **파일 해시 추가**: 줄당 최대 20 개까지 한 줄에 하나씩 SHA256 해시 값을 입력 합니다.

   - **차단/허용**: 지정 된 파일을 **허용할지** 아니면 **차단할지** 를 선택 합니다.

   - 사용 **기간 제한 없음**: 다음 단계 중 하나를 수행 합니다.

     - 설정이 꺼져 있는지 ( ![ 토글 해제)를 확인 하 ](../../media/scc-toggle-off.png) 고 **만료** 날짜 상자를 사용 하 여 항목의 만료일을 지정 합니다.

     또는

     - 오른쪽으로 토글을 이동 하 여 만료 되지 않도록 항목을 구성 합니다. ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **선택 사항**: 항목에 대 한 설명 텍스트를 입력 합니다.

4. 작업이 완료 되 면 **추가**를 클릭 합니다.

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록의 URL 및 파일 항목 보기

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.

2. **Url** 탭 또는 **파일** 탭을 선택 합니다.

다음 열 머리글을 클릭 하 여 오름차순 또는 내림차순으로 정렬 합니다.

- **값**: URL 또는 파일 해시입니다.
- **작업**: **차단** 또는 **허용**합니다.
- **마지막 업데이트 날짜**
- **만료 날짜**
- **참고**

**그룹** 을 클릭 하 여 **작업** (**차단** 또는 **허용**)을 기준으로 항목을 그룹화 하거나 **아무 것도**선택 하지 않습니다.

**검색**을 클릭 하 고 URL 또는 파일 값의 일부나 전체를 입력 한 다음 enter 키를 눌러 특정 값을 찾습니다. 작업이 끝나면 검색 지우기 검색 아이콘 **을 클릭** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 합니다.

**필터**를 클릭 합니다. **필터** 플라이 아웃이 나타나면 다음 설정을 구성 합니다.

- **작업**: **Allow**, **Block** 또는 both를 선택 합니다.

- 사용 **기간 제한 없음**: 해제 (설정 ![ /해제 ](../../media/scc-toggle-off.png) ) 또는 설정 ( ![ 토글 켜기)을 선택 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 합니다.

- **마지막 업데이트**: 시작 날짜 (**원본**), 종료 날짜 (**대상**) 또는 두 가지 모두를 선택 합니다.

- **만료 날짜**: 시작 날짜 (**From**), 종료 날짜 (**대상**) 또는 둘 다를 선택 합니다.

작업이 완료 되 면 **적용**을 클릭 합니다.

기존 필터를 지우려면 **필터**를 클릭 하 고 **필터** 플라이 아웃이 나타나면 **필터 해제**를 클릭 합니다.

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록의 URL 및 파일 항목 수정

URL 또는 파일 값 자체는 수정할 수 없습니다. 대신 항목을 삭제 하 고 다시 만들어야 합니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.

2. **Url** 탭 또는 **파일** 탭을 선택 합니다.

3. 수정 하려는 항목을 선택 하 고 편집 아이콘 편집을 클릭 **Edit** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 합니다.

4. 플라이 아웃이 나타나면 다음 설정을 구성 합니다.

   - **차단/허용**: **허용** 또는 **차단**을 선택 합니다.

   - 사용 **기간 제한 없음**: 다음 단계 중 하나를 수행 합니다.

     - 설정이 꺼져 있는지 ( ![ 토글 해제)를 확인 하 ](../../media/scc-toggle-off.png) 고 **만료** 날짜 상자를 사용 하 여 항목의 만료일을 지정 합니다.

     또는

     - 오른쪽으로 토글을 이동 하 여 항목이 만료 되지 않도록 구성 합니다. ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **선택 사항**: 항목에 대 한 설명 텍스트를 입력 합니다.

5. 작업을 마쳤으면 **저장**을 클릭합니다.

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록에서 URL 및 파일 항목 제거

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.

2. **Url** 탭 또는 **파일** 탭을 선택 합니다.

3. 제거할 항목을 선택한 다음 삭제 아이콘 **삭제** 를 클릭 ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 합니다.

4. 경고 대화 상자가 나타나면 **삭제**를 클릭 합니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용 하 여 테 넌 트 허용/차단 목록을 구성 합니다.

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a>PowerShell을 사용 하 여 테 넌 트 허용/차단 목록에 URL 및 파일 항목 추가

테 넌 트 허용/차단 목록에 URL 및 파일 항목을 추가 하려면 다음 구문을 사용 합니다.

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

이 예에서는 contoso.com 및 모든 하위 도메인 (예: contoso.com, www.contoso.com 및 xyz.abc.contoso.com)에 대 한 URL 블록 항목을 추가 합니다. ExpirationDate 또는 NoExpiration 매개 변수를 사용 하지 않았으므로 30 일 후에 항목이 만료 됩니다.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

이 예에서는 지정 된 파일에 대해 만료 되지 않는 파일을 추가 합니다.

구문과 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)를 참조 하십시오.

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>PowerShell을 사용 하 여 테 넌 트 허용/차단 목록에서 URL 및 파일 항목 보기

테 넌 트 허용/차단 목록에서 URL 및 파일 항목을 보려면 다음 구문을 사용 합니다.

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

이 예에서는 차단 된 모든 Url을 반환 합니다.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

이 예제에서는 지정 된 파일 해시 값에 대 한 정보를 반환 합니다.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

구문과 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)를 참조 하십시오.

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>PowerShell을 사용 하 여 테 넌 트 허용/차단 목록에서 URL 및 파일 항목 수정

URL 또는 파일 값 자체는 수정할 수 없습니다. 대신 항목을 삭제 하 고 다시 만들어야 합니다.

테 넌 트 허용/차단 목록에서 URL 및 파일 항목을 수정 하려면 다음 구문을 사용 합니다.

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

다음은 지정 된 항목의 만료 날짜를 변경 하는 예제입니다.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

구문 및 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)를 참조 하십시오.

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>PowerShell을 사용 하 여 테 넌 트 허용/차단 목록에서 URL 및 파일 항목 제거

테 넌 트 허용/차단 목록에서 URL 및 파일 항목을 제거 하려면 다음 구문을 사용 합니다.

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

이 예에서는 테 넌 트 허용/차단 목록에서 지정 된 URL 항목을 제거 합니다.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

구문과 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)를 참조 하십시오.

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>테 넌 트 허용/차단 목록에 대 한 URL 구문

- IP4v 및 IPv6 주소를 사용할 수 있지만 TCP/UDP 포트는 허용 되지 않습니다.

- 파일 이름 확장명은 허용 되지 않습니다 (예: test.pdf).

- 유니코드는 지원 되지 않지만, Punycode는입니다.

- 다음의 모든 조건에 해당 하는 경우에는 호스트 이름이 허용 됩니다.

  - 호스트 이름에 마침표가 포함 되어 있습니다.
  - 마침표 왼쪽에 문자가 하나 이상 있습니다.
  - 마침표 오른쪽에 2 개 이상의 문자가 있습니다.

  예를 들어, `t.co` 허용 `.com` 되지 않거나 `contoso.` 허용 되지 않습니다.

- 하위 경로는 포함 되지 않습니다.

  예를 들어에 `contoso.com` 는가 포함 되지 않습니다 `contoso.com/a` .

- 다음과 같은 시나리오에서는 와일드 카드 (*)를 사용할 수 있습니다.

  - 하위 도메인을 지정 하려면 left 와일드 카드 다음에 마침표가와 야 합니다.

    예를 들어, 허용 `*.contoso.com` `*contoso.com` 되지 않습니다.

  - 경로를 지정 하려면 오른쪽 와일드 카드는 슬래시 (/) 다음에와 야 합니다.

    예를 들어, `contoso.com/*` 허용 `contoso.com*` 되지 않거나 `contoso.com/ab*` 허용 되지 않습니다.

  - 모든 서브 경로는 오른쪽 와일드 카드에서 암시 되지 않습니다.

    예를 들어에 `contoso.com/*` 는가 포함 되지 않습니다 `contoso.com/a` .

  - `*.com*`잘못 되었습니다 (확인할 수 있는 도메인이 아님, 올바른 와일드 카드가 슬래시 다음에 없음).

  - IP 주소에는 와일드 카드를 사용할 수 없습니다.

- 물결표 (~) 문자는 다음과 같은 시나리오에서 사용할 수 있습니다.

  - 왼쪽 물결표는 도메인과 모든 하위 도메인을 의미 합니다.

    예를 `~contoso.com` 들어 `contoso.com` and를 포함 `*.contoso.com` 합니다.

- `http://` `https://` `ftp://` Url 항목은 모든 프로토콜에 적용 되므로 프로토콜 (예:, 또는)을 포함 하는 url 항목은 실패 합니다.

- 사용자 이름 또는 암호는 지원 되지 않거나 필수입니다.

- 따옴표 (' 또는 ")는 잘못 된 문자입니다.

- URL에는 가능한 모든 리디렉션이 포함 되어야 합니다.

### <a name="url-entry-scenarios"></a>URL 입력 시나리오

유효한 URL 항목 및 결과는 다음 섹션에 설명 되어 있습니다.

#### <a name="scenario-no-wildcards"></a>시나리오: 와일드 카드 없음

**항목**:`contoso.com`

- **일치 허용**: contoso.com

- **일치 하지 않는 항목 허용**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. .com/q = a@contoso
  
- **일치 블록**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. .com/q = a@contoso

- **일치 하지 않는 블록**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>시나리오: Left 와일드 카드 (하위 도메인)

**항목**:`*.contoso.com`

- **일치 허용** 및 **일치 차단**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **일치 하지 않는** 항목과 **일치**하는 블록 허용:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>시나리오: 경로 맨 위의 오른쪽 와일드 카드

**항목**:`contoso.com/a/*`

- **일치 허용** 및 **일치 차단**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso/a/? q = joe@t .com

- **일치 하지 않는** 항목과 **일치**하는 블록 허용:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www. .com/q = a@contoso
  
#### <a name="scenario-left-tilde"></a>시나리오: 왼쪽 물결표

**항목**:`~contoso.com`

- **일치 허용** 및 **일치 차단**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **일치 하지 않는** 항목과 **일치**하는 블록 허용:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>시나리오: 오른쪽 와일드 카드 접미사

**항목**:`contoso.com/*`

- **일치 허용** 및 **일치 차단**:

  - contoso/? q = whatever@fabrikam
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **일치 하지 않음** 및 **일치**하는 블록 허용: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>시나리오: Left 와일드 카드 하위 도메인 및 오른쪽 와일드 카드 접미사

**항목**:`*.contoso.com/*`

- **일치 허용** 및 **일치 차단**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **일치 하지 않음** 및 **일치**하는 블록 허용: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>시나리오: 왼쪽과 오른쪽 물결표

**항목**:`~contoso.com~`

- **일치 허용** 및 **일치 차단**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **일치 하지 않는** 항목과 **일치**하는 블록 허용:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>시나리오: IP 주소

**항목**:`1.2.3.4`

- **일치 허용** 및 **일치 차단**: 1.2.3.4

- **일치 하지 않는** 항목과 **일치**하는 블록 허용:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>오른쪽 와일드 카드를 사용한 IP 주소

**항목**:`1.2.3.4/*`

- **일치 허용** 및 **일치 차단**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>잘못 된 항목의 예

다음 항목은 유효 하지 않습니다.

- **누락 되었거나 잘못 된 도메인 값**:

  - 극동
  - \*극동.\*
  - \*.com
  - \*.pdf

- **텍스트에 와일드 카드 사용 또는 공백 문자 없는**경우:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **포트를 포함 하는 IP 주소**:

  - contoso.com:443
  - abc.contoso.com:25

- **설명적이 아닌 와일드 카드**:

  - \*
  - \*.\*

- **중간 와일드 카드**:

  - \*so.com
  - ~ ~ .com

- **이중 와일드 카드**

  - contoso.com/\*\*
  - contoso.com/\*/\*
