---
title: 공유 사서함의 문제 해결
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 공유 사서함에 문제가 있는 경우 이러한 해결 방법을 시도해 보아야 합니다.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926489"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>공유 사서함의 문제 해결

공유 사서함을 만들거나 사용할 때 오류 메시지가 표시될 경우 이러한 해결 방법을 시도해 봐야 합니다. 

## <a name="error-when-creating-shared-mailboxes"></a>공유 사서함을 만들 때 오류
<a name="bkmk_Fix"> </a>

오류 메시지가 표시될 경우 프록시 주소 "smtp:<공유 사서함 이름"이 프록시 주소 또는 **\> ""의 LegacyExchangeDN에서 이미 사용 \<name> 중입니다. 다른 프록시 주소를 선택하세요.** 즉, 공유 사서함에 이미 사용 중인 이름을 지정하려고 합니다. 예를 들어 공유 사서함 이름을 info@domain1 및 info@domain2로 지정하려 합니다. 이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.

  - 이 Windows PowerShell. 지침은 다음 블로그 게시물을 참조하세요. 다른 도메인에서 동일한 별칭을 사용하여 공유 사서함 [만들기](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - 두 번째 공유 사서함의 이름을 시작과 다르게 지정하여 오류를 해결합니다. 그런 다음 관리 센터에서 공유 사서함의 이름을 원하는 것으로 변경합니다.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>공유 사서함을 사용할 때 보내기 권한이 없는 경우의 오류

공유 사서함을 만든 후 공유 사서함에서 메시지를 보내려고 시도하면 다음 메시지가 표시될 수 있습니다.

**이 메시지를 보낼 수 없습니다. 지정된 사용자를 대신하여 메시지를 보낼 수 있는 권한이 없습니다.**

이 메시지는 Microsoft 365에서 복제 대기 시간 문제가 발생하는 경우 표시됩니다. 새 공유 사서함(또는 추가된 사용자)에 대한 정보가 모든 데이터 센터에 복제될 때 1시간 정도 지나지 않습니다. 한 시간 동안 기다렸다가 메시지를 다시 보내려고 시도합니다.

## <a name="related-articles"></a>관련 문서

[공유 사서함 정보](about-shared-mailboxes.md)

[공유 사서함 만들기](create-a-shared-mailbox.md)

[공유 사서함 구성](configure-a-shared-mailbox.md)

[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)

[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)


    

