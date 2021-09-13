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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 공유 사서함을 설정할 때 오류가 발생할 수 있습니다. 공유 사서함에 문제가 있는 경우 이러한 솔루션을 사용해 하세요.
ms.openlocfilehash: ae76bc1cb97c44087be57adc7791ea8814b94b40
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184683"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>공유 사서함의 문제 해결

공유 사서함을 만들거나 사용할 때 오류 메시지가 표시될 경우 이러한 가능한 해결 방법을 시도해 봐야 합니다. 

## <a name="error-when-creating-shared-mailboxes"></a>공유 사서함을 만들 때 오류 발생
<a name="bkmk_Fix"> </a>

오류 메시지가 표시될 경우 프록시 주소 "smtp:<공유 사서함 이름"이 이미 프록시 주소나 **\> "의 LegacyExchangeDN에서 \<name> 사용 중입니다. 다른 프록시 주소** 를 선택하세요. 즉, 공유 사서함에 이미 사용 중인 이름을 지정하려고 합니다. 예를 들어 공유 사서함 이름을 info@domain1 및 info@domain2로 지정하려 합니다. 이 작업을 수행하는 방법은 다음 두 가지입니다.

  - 이 Windows PowerShell. 자세한 내용은 다음 블로그 게시물을 참조하세요. [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - 두 번째 공유 사서함의 이름을 시작과 다르게 지정하여 오류를 해결합니다. 그런 다음 관리 센터에서 공유 사서함의 이름을 원하는 것으로 변경합니다.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>공유 사서함을 사용할 때 보내기 권한이 없는 경우의 오류

공유 사서함을 만든 후 해당 사서함에서 메시지를 보내려고 시도하면 다음을 얻을 수 있습니다.

**이 메시지를 보낼 수 없습니다. 지정된 사용자를 대신하여 메시지를 보낼 수 있는 권한이 없습니다.**

이 메시지는 Microsoft 365 대기 시간 문제가 발생하면 표시됩니다. 새 공유 사서함(또는 추가된 사용자)에 대한 정보가 모든 데이터 센터에 복제되는 경우 1시간 정도 지나지 않습니다. 1시간을 기다렸다가 다시 시도하여 메시지를 보내려고 시도합니다.

## <a name="related-content"></a>관련 콘텐츠

[공유 사서함 정보](about-shared-mailboxes.md)(문서)\
[공유 사서함](create-a-shared-mailbox.md) 만들기(문서)\
[공유 사서함 구성](configure-a-shared-mailbox.md)(문서)\
[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)(문서)\
[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)(문서)


    

