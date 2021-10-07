---
title: 테넌트 허용/차단 목록에서 블록 관리
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
description: 관리자는 보안 포털의 테넌트 허용/차단 목록에서 블록을 구성하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e3af53e4cf6776627e7d8c25f41e241f37add8e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174318"
---
# <a name="add-blocks-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에 블록 추가

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 포털 사용 

### <a name="create-block-sender-entries-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에서 차단 보낸 사람 항목 만들기

1. Microsoft 365 Defender 포털에서 정책 &  규칙 규칙 \>  \>  섹션 \> **테넌트 허용/차단 목록으로 이동하세요.**

2. **테넌트 허용/차단 목록** 페이지에서 보낸  사람 탭이 선택되어 있는지 확인한 다음 차단 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **차단**.

3. 보낸 **사람 차단** 플라이아웃이 나타나면 다음 설정을 구성합니다.
   - **보낸 사람 전자** 메일 주소 또는 도메인: 줄당 하나의 보낸 사람(전자 메일 주소 또는 도메인)을 입력하고 최대 20명까지 입력합니다.
   - **만료 안 하세요:** 다음 단계 중 하나를 수행합니다.
     - 설정이 꺼져 있는지 확인(토글 해제) 및 제거 사용 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. 

       또는

     - 토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다. ![토글합니다.](../../media/scc-toggle-on.png).
   - **선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.

4. 작업을 마쳤으면 **추가** 를 클릭합니다.

### <a name="create-block-url-entries-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에서 차단 URL 항목 만들기

1. Microsoft 365 Defender 포털에서 정책 &  규칙 규칙 \>  \>  섹션 \> **테넌트 허용/차단 목록으로 이동하세요.**

2. **테넌트 허용/차단 목록** 페이지에서 URL  탭이 선택되어 있는지 확인한 다음 차단 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **차단**.

3. 나타나는 **URL 차단** 플라이아웃에서 다음 설정을 구성합니다.
   - **와일드카드가** 있는 URL 추가: 줄당 하나의 URL을 입력하고 최대 20개까지 입력합니다. URL 항목의 구문에 대한 자세한 내용은 [Manage the Tenant Allow/Block List](tenant-allow-block-list.md)의 URL 구문 섹션을 참조하십시오.
   - **만료 안 하세요:** 다음 단계 중 하나를 수행합니다.
     - 설정이 꺼져 있는지 확인(토글 해제) 및 제거 사용 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. 

       또는

     - 토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다. ![토글합니다.](../../media/scc-toggle-on.png).
   - **선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.

4. 작업을 마쳤으면 **추가** 를 클릭합니다.

### <a name="create-block-file-entries-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에서 차단 파일 항목 만들기

1. Microsoft 365 Defender 포털에서 정책 &  규칙 규칙 \>  \>  섹션 \> **테넌트 허용/차단 목록으로 이동하세요.**

2. **테넌트 허용/차단 목록** 페이지에서  파일 탭을 선택한 다음 차단 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **차단**.

3. 파일 **차단** 플라이아웃이 나타나면 다음 설정을 구성합니다.
   - **파일 해시 추가:** 줄당 SHA256 해시 값 하나(최대 20개)를 입력합니다.
   - **만료 안 하세요:** 다음 단계 중 하나를 수행합니다.
     - 설정이 꺼져 있는지 확인(토글 해제) 및 제거 사용 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. 

     또는

     - 토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다. ![토글합니다.](../../media/scc-toggle-on.png).
   - **선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.

4. 작업을 마쳤으면 **추가** 를 클릭합니다.

### <a name="create-spoofed-sender-block-entries"></a>스푸핑된 보낸 사람 차단 항목 만들기

**참고**:

- _스푸핑된_ 사용자와 도메인  쌍에 정의된 전송 인프라의 조합만 스푸핑을 특별히 허용하거나 차단합니다.
- 도메인 쌍에 대해 허용 또는 차단 항목을 구성하면 해당 도메인 쌍의 메시지가 더 이상 스푸핑 인텔리전스 인사이트에 나타나지 않습니다.
- 스푸핑된 보낸 사람에 대한 항목은 만료되지 않습니다.
- 스푸핑은 허용 및 차단을 모두 지원합니다. URL은 허용만 지원됩니다.

1. Microsoft 365 Defender 포털에서 정책 &  규칙 규칙 \>  \>  섹션 \> **테넌트 허용/차단 목록으로 이동하세요.**

2. **테넌트 허용/차단 목록** 페이지에서  스푸핑 탭을 선택한 다음 차단 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **추가** 합니다.

3. 나타나는 **새 도메인** 쌍 추가 플라이아웃에서 다음 설정을 구성합니다.
   - **와일드카드를 통해** 새 도메인 쌍 추가: 한 줄에 도메인 쌍을 하나씩 입력하고 최대 20개까지 입력합니다. 스푸핑된 보낸 사람 항목에 대한 구문에 대한 자세한 내용은 [테넌트 허용/차단 목록 관리를 참조하세요.](tenant-allow-block-list.md)
   - **스푸핑 유형:** 다음 값 중 하나를 선택합니다.
     - **내부:** 스푸핑된 보낸 사람이 조직에 속한 도메인(허용 [도메인)에 있습니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **외부:** 스푸핑된 보낸 사람이 외부 도메인에 있습니다.
   - **작업:** 허용 **또는 차단을** **선택합니다.**

4. 작업을 마쳤으면 **추가** 를 클릭합니다.

## <a name="use-powershell"></a>PowerShell 사용

### <a name="add-block-sender-file-or-url-entries-to-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에 차단 보낸 사람, 파일 또는 URL 항목 추가

테넌트 허용/차단 목록에서 차단 보낸 사람, 파일 또는 URL 항목을 추가하기 위해 다음 구문을 사용합니다.

```powershell
New-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

이 예에서는 특정 날짜에 만료되는 지정된 보낸 사람에 대한 차단 보낸 사람 항목을 추가합니다.

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com", "test2@anotherattackerdomain.com" -ExpirationDate 8/20/2021
```

이 예제에서는 만료되지 않는 지정된 파일에 대한 차단 파일 항목을 추가합니다.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

이 예제에서는 contoso.com, contoso.com, www.contoso.com 및 하위 xyz.abc.contoso.com. ExpirationDate 또는 NoExpiration 매개 변수를 사용하지 않았기 때문에 항목이 30일 후에 만료됩니다.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="add-spoofed-sender-block-entries"></a>스푸핑된 보낸 사람 차단 항목 추가 

테넌트 허용/차단 목록에 스푸핑된 보낸 사람 항목을 추가하기 위해 다음 구문을 사용하세요.

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)
