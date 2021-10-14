---
title: 테넌트 허용/차단 목록에서 허용 관리
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
description: 관리자는 보안 포털의 테넌트 허용/차단 목록에서 허용을 구성하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 98ae7b53ce793809ae93cf32d574d979e5b7c6e5
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335565"
---
# <a name="add-allows-in-the-tenant-allowblock-list"></a>테넌트 허용/차단 목록에 허용 추가

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

관리자는 테넌트 허용/차단 목록에 직접 허용할 수 없습니다. 대신 관리 제출 프로세스를 사용하여 해당 URL, 파일 및/또는 보낸 사람이 테넌트 허용/차단 목록에 추가될 수 있도록 차단된 메시지를 제출합니다. 메시지가 잘못 차단된 가짓 긍정으로 확인된 대부분의 경우 허용은 시스템에 자연스럽게 허용하는 데 필요한 기간 동안 유지됩니다.

> [!IMPORTANT]
>
> Microsoft는 필요하지 않은 사용자, 보낸 사람, URL 또는 파일을 허용하는 허용을 관리하기 때문에 불량으로 간주되는 파일이 제거됩니다. 이는 환경을 보호하고 허용이 잘못 구성되지 않도록 방지하기 위한 것입니다. 동의하지 않을 수 있는 경우 메시지가 여전히 잘못된 것으로 간주되는 이유를 확인하는 데 도움이 되는 지원 사례가 필요할 수 있습니다.

## <a name="add-allows-using-the-submissions-portal"></a>Add를 사용하면 제출 포털을 사용할 수 있습니다. 

파일, URL 및 보낸 사람에 대한 파일, URL 및 보낸 사람 허용은 Microsoft 365 Defender. 

1. Microsoft 365 Defender 포털에서 전자 메일 &  \> **제출로 이동하세요.**

2. 제출 **페이지에서** 분석용 **제출** 탭이 선택되어 있는지 확인한 다음 광고 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **분석을 위해 Microsoft에 제출합니다.**

3. 검토 플라이아웃을 **위해 Microsoft에** 제출을 사용하여 네트워크 메시지 ID를 추가하거나 전자 메일 파일을 업로드하여 메시지를 제출합니다. 

4. **Microsoft에** 제출할 이유 선택 섹션에서 차단되지 않은 경우(가음성)를 **선택합니다.** 

5. 이 **옵션과 같은 메시지 허용을 으로** 하세요. 

6. 제거 **후 드롭다운** 목록에서 허용 옵션이 작동하도록 할 기간을 지정합니다.

7. 완료되면 제출 **단추를** 클릭합니다.

> [!div class="mx-imgBorder"]
> ![가짓 긍정 제출 예제입니다.](../../media/admin-submission-allow-messages.png)

## <a name="create-spoofed-sender-allow-entries-using-microsoft-365-defender"></a>스푸핑된 보낸 사람 허용 항목을 Microsoft 365 Defender

> [!NOTE]
> 
> - _스푸핑된_ 사용자와 도메인  쌍에 정의된 전송 인프라의 조합만 스푸핑을 특별히 허용하거나 차단합니다.
> - 도메인 쌍에 대해 허용 또는 차단 항목을 구성하면 해당 도메인 쌍의 메시지가 더 이상 스푸핑 인텔리전스 인사이트에 나타나지 않습니다.
> - 스푸핑된 보낸 사람에 대한 항목은 만료되지 않습니다.
> - 스푸핑은 허용 및 차단을 모두 지원합니다. URL은 허용만 지원됩니다.

1. Microsoft 365 Defender 포털에서 정책 &  규칙 규칙 \>  \>  섹션 \> **테넌트 허용/차단 목록으로 이동하세요.**

2. **테넌트 허용/차단 목록** 페이지에서  스푸핑 탭을 선택한 다음 차단 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **추가** 합니다.

3. 나타나는 **새 도메인** 쌍 추가 플라이아웃에서 다음 설정을 구성합니다.
   - **와일드카드를 통해** 새 도메인 쌍 추가: 한 줄에 도메인 쌍을 하나씩 입력하고 최대 20개까지 입력합니다. 스푸핑된 보낸 사람 항목에 대한 구문에 대한 자세한 내용은 [테넌트 허용/차단 목록 관리를 참조하세요.](tenant-allow-block-list.md)
   - **스푸핑 유형:** 다음 값 중 하나를 선택합니다.
     - **내부:** 스푸핑된 보낸 사람이 조직에 속한 도메인(허용 [도메인)에 있습니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **외부:** 스푸핑된 보낸 사람이 외부 도메인에 있습니다.
   - **작업:** 허용 **또는 차단을** **선택합니다.**

4. 작업을 마쳤으면 **추가** 를 클릭합니다.

## <a name="add-spoofed-sender-allow-entries-using-powershell"></a>PowerShell을 사용하여 스푸핑된 보낸 사람 허용 항목 추가

테넌트 허용/차단 목록에 스푸핑된 보낸 사람 항목을 추가하기 위해 다음 구문을 사용하세요.

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)

## <a name="related-articles"></a>관련 문서

- [관리자 제출](admin-submission.md)
- [가짓 긍정 및 거짓 부정 보고](report-false-positives-and-false-negatives.md)
