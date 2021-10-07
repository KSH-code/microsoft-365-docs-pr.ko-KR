---
title: 테넌트 허용/차단 목록에서 항목 수정 및 제거
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 보안 포털의 테넌트 허용/차단 목록에서 항목을 수정하고 제거하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f2662ac41e5df5cf2eb36413d8a58568ff336841
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60212008"
---
# <a name="modify-and-remove-entries-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에서 항목 수정 및 제거

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

테넌트 허용/Microsoft 365 Defender 포털 또는 PowerShell을 사용하여 테넌트 허용/차단 목록의 항목을 수정하고 제거할 수 있습니다.

## <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 포털 사용

### <a name="modify-entries-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록의 항목 수정

1. Microsoft 365 Defender 포털에서 정책 &  규칙 규칙 \>  \>  섹션 \> **테넌트 허용/차단 목록으로 이동하세요.**

2. 수정할 항목 유형이 포함된 탭을 선택합니다.
   - **Senders)
   - **URL**
   - **파일**
   - **스푸핑**

3. 수정할 항목을 선택하고 편집 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-edit-icon.png) **편집.** 플라이아웃에서 수정할 수 있는 값은 이전 단계에서 선택한 탭에 따라 다를 수 있습니다.
   - **보낸 사람**
     - **만료 및/또는** 만료 날짜가 없습니다.
     - **선택 사항 참고 사항**
   - **URL**
     - **만료 및/또는** 만료 날짜가 없습니다.
     - **선택 사항 참고 사항**
   - **파일**
     - **만료 및/또는** 만료 날짜가 없습니다.
     - **선택 사항 참고 사항**
   - **스푸핑**
     - **작업:** 값을 허용 또는 **차단으로** 변경할 **수 있습니다.**
4. 작업을 마쳤으면 **저장** 을 클릭합니다.

> [!NOTE]
> 생성 날짜 이후 최대 30일 동안만 확장할 수 있습니다. 블록은 최대 90일까지 확장할 수 있지만 허용하는 경우와 달리 만료되지 않는 것으로 설정할 수도 있습니다.

### <a name="remove-entries-from-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에서 항목 제거

1. Microsoft 365 Defender 포털에서 정책 &  규칙 규칙 \>  \>  섹션 \> **테넌트 허용/차단 목록으로 이동하세요.**

2. 제거할 항목 유형이 포함된 탭을 선택합니다.
   - **보낸 사람**
   - **URL**
   - **파일**
   - **스푸핑**

3. 제거할 항목을 선택한 다음 삭제 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-delete-icon.png) **삭제**.

4. 나타나는 경고 대화 상자에서 삭제를 **클릭합니다.**

## <a name="use-powershell"></a>PowerShell 사용

### <a name="modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에서 차단 파일 및 URL 항목 수정

테넌트 허용/차단 목록에서 차단 보낸 사람, 파일 및 URL 항목을 수정하려면 다음 구문을 사용합니다.

```powershell
Set-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

이 예에서는 지정한 블록 URL 항목의 만료 날짜를 변경합니다.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에서 URL 또는 파일 항목 제거

테넌트 허용/차단 목록에서 보낸 사람, 파일 및 URL 항목을 제거하려면 다음 구문을 사용합니다.

```powershell
Remove-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

이 예에서는 테넌트 허용/차단 목록에서 지정된 차단 URL 항목을 제거합니다.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/remove-tenantallowblocklistitems)

### <a name="modify-allow-or-block-spoofed-sender-entries"></a>스푸핑된 보낸 사람 항목 허용 또는 차단 수정

테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목을 허용하거나 차단하려면 다음 구문을 사용하세요.

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

이 예에서는 스푸핑된 보낸 사람 항목을 허용에서 차단으로 변경합니다.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)

### <a name="remove-allow-or-block-spoofed-sender-entries"></a>스푸핑된 보낸 사람 항목 허용 또는 차단 제거

테넌트 허용/차단 목록에서 스푸핑 보낸 사람 항목을 허용하거나 차단하려면 다음 구문을 사용하세요.

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)
