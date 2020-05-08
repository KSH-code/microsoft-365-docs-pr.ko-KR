---
title: 사용자 사서함을 공유 사서함으로 변환
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '개인 사서함을 여러 사용자가 액세스할 수 있는 공유 사서함으로 변환 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 51817001b02c1dd5dd0e82f5795ef1a3f66bf7c7
ms.sourcegitcommit: 9ffa2fd25776726475e10148940987fa076bbd91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44162701"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>사용자 사서함을 공유 사서함으로 변환

사용자의 사서함을 공유 사서함으로 변환 하면 기존 전자 메일 및 일정이 모두 보존 됩니다. 이제는 여러 사용자가 한 사람을 대신 하 여 액세스할 수 있는 공유 사서함에 있습니다. 나중에 공유 사서함을 다시 사용자 (개인) 사서함으로 변환할 수 있습니다.

**다음은 알아야 할 몇 가지 중요 한 사항입니다.**

- 변환 중인 사용자 사서함에는 라이선스를 공유 사서함으로 변환 하기 전에 할당 해야 합니다. 그렇지 않으면 사서함을 변환 하는 옵션이 표시 되지 않습니다. 라이선스를 제거한 경우 사서함을 변환할 수 있도록 다시 추가 합니다. 공유 사서함으로 변환한 후 사용자의 계정에서 라이선스를 제거할 수 있습니다.

- 공유 사서함에는 라이선스가 할당 되지 않은 데이터를 최대 50GB까지 포함할 수 있습니다. 그 보다 더 많은 데이터를 포함 하려면 라이선스가 할당 되어야 합니다. 라이선스를 제거할 수 있도록 공유 사서함에서 첨부 파일을 포함 하는 대용량 전자 메일을 삭제 하 여 축소 해야 할 수도 있습니다.

- 이전 사용자의 계정을 삭제 하지 마세요. 공유 사서함을 고정 하는 데 필요 합니다. 사용자 계정을 이미 삭제 한 경우에는 삭제 된 [사용자의 사서함 변환을](#convert-the-mailbox-of-a-deleted-user)참조 하십시오.

- 사서함이 공유 사서함으로 변환 된 후에는 규칙이 그대로 유지 됩니다.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Exchange 관리 센터를 사용 하 여 사서함 변환
 
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.

2. **받는 사람** \> **사서함**을 선택 합니다.

3. 사용자 사서함을 선택 합니다. **공유 사서함으로 변환**에서 **변환을**선택 합니다.

4. 사서함이 50GB 보다 작으면 [사용자 로부터 라이선스](../manage/remove-licenses-from-users.md)를 제거 하 고이에 대 한 비용 지불을 중지할 수 있습니다. 사용자의 계정을 삭제 하지 마세요. 공유 사서함에는 기준 위치가 필요 합니다. 조직에서 나가는 직원의 사서함을 변환 하는 경우에는 추가 단계를 수행 하 여 더 이상 로그인 할 수 없도록 해야 합니다. [Microsoft 365에서 이전 직원 제거를](../add-users/remove-former-employee.md)참조 하세요.
    
5. 공유 사서함에 대해 알아야 할 다른 모든 작업은 [공유](about-shared-mailboxes.md) 사서함 및 [공유 사서함 만들기](create-a-shared-mailbox.md)를 참조 하세요.

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a>Microsoft 365 관리 센터를 사용 하 여 사서함 변환

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 해당 사서함을 변환 하려는 사용자의 이름을 선택 합니다.

3. 사용자 암호를 다시 설정 합니다.

> [!NOTE]
> 사서함 변환 중에 사용자 암호를 다시 설정할 필요는 없습니다. 그러나 암호를 다시 설정 하지 않으면 사서함 변환이 끝난 후 **에도 원래 사용자 이름 및 암호가 계속 작동** 합니다.

4. **메일** 탭의 **기타 작업**에서 **공유 사서함으로 변환을**선택 합니다. 

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 해당 사서함을 변환 하려는 사용자를 선택 합니다.

3. 오른쪽 창에서 **메일 설정을**확장 합니다. **기타 설정**옆에 있는 **공유 사서함으로 변환을**선택 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 해당 사서함을 변환 하려는 사용자를 선택 합니다.

3. 오른쪽 창에서 **메일 설정을**확장 합니다. **기타 설정**옆에 있는 **공유 사서함으로 변환을**선택 합니다.

::: moniker-end


사서함이 50GB 보다 작으면 [사용자 로부터 라이선스를 제거](../manage/remove-licenses-from-users.md)하 고이에 대 한 비용 지불을 중지할 수 있습니다. 사용자의 이전 사서함은 삭제 하지 마세요. 공유 사서함에는 기준 위치가 필요 합니다. 조직에서 나가는 직원의 사서함을 변환 하는 경우에는 추가 단계를 수행 하 여 더 이상 로그인 할 수 없도록 해야 합니다. [Microsoft 365에서 이전 직원 제거를](../add-users/remove-former-employee.md)참조 하세요.
    
공유 사서함에 대해 알아야 할 다른 모든 작업은 [공유](about-shared-mailboxes.md) 사서함 및 [공유 사서함 만들기](create-a-shared-mailbox.md)를 참조 하세요.


## <a name="convert-the-mailbox-of-a-deleted-user"></a>삭제 된 사용자의 사서함 변환

사용자 계정을 삭제 했 고 이제 이전 사서함을 공유 사서함으로 변환 하려는 경우를 가정해 보겠습니다. 수행 해야 하는 작업은 다음과 같습니다.

1. [사용자의 계정을 복원](../add-users/restore-user.md)합니다.

2. Microsoft 365 라이선스가 할당 되어 있는지 확인 합니다.

3. 사용자 암호를 다시 설정 합니다.
    
4. 사서함을 다시 만들 때까지 20-30 분 정도 기다립니다.
    
5. 이제이 페이지의 지침에 따라 사서함을 공유 사서함으로 변환 합니다.
    
6. 이 작업을 완료 한 후에는 사용자의 사서함에서 라이선스를 제거할 수 있습니다. 사용자의 이전 사서함은 삭제 하지 마세요. 공유 사서함에는 기준 위치가 필요 합니다.
    
7. 공유 사서함에 구성원을 추가 합니다.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>공유 사서함을 사용자의 (개인) 사서함으로 다시 변환

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.
   
2. **공유**되는 **받는 사람** \> 을 선택 합니다.

3. 공유 사서함을 선택 합니다. **일반 사서함으로 변환**에서 **변환을**선택 합니다.

4. 관리 센터로 다시 이동 합니다. **사용자**에서 이전 공유 사서함과 연결 된 사용자 계정을 선택 합니다. 계정에 라이선스를 할당 하 고 암호를 다시 설정 합니다.

   사서함이 설정 되는 데 몇 분 정도 소요 되지만 그 이후에는 해당 계정을 사용 하려는 사용자가 준비 됩니다. 로그인 할 때 공유 사서함에 있는 것으로 사용 된 전자 메일 및 일정 항목을 볼 수 있습니다.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>하이브리드 환경에서 사용자의 사서함 변환

이 공유 사서함을 하이브리드 환경에서 사용 하는 경우에는 사용자 사서함을 다시 온-프레미스로 변환 하 고 사용자 사서함을 공유 사서함으로 변환한 다음 공유 사서함을 다시 클라우드로 이동 하는 것이 **좋습니다** (거의 필요 합니다).

그 이유는 다음과 같습니다. 클라우드에서 사서함을 변환 하는 경우 새 현실을 다시 온-프레미스로 동기화 하지 않으므로 온-프레미스에서 사서함이 사용자 사서함 인 것으로 간주 합니다.

일반적으로이 문제는 문제가 되지 않지만, 사서함이 사용자 사서함 인 것으로 생각 하는 온-프레미스 특성이 해당 특성의 새 클라우드 버전을 덮어쓸 수 있으며, 결과적으로 사서함이 다시 변환 될 수 있는 시나리오가 있습니다. 사용자 사서함에 라이선스가 필요 **하거나 30 일 후에 일시 삭제**되기 때문에이 문제가 발생 합니다.

이 문제가 발생 하는 대부분의 이유는 아니지만 여전히 가끔씩 발생할 수 있습니다. 안전 하 고 사서함을 다시 온-프레미스로 이동 하는 것이 좋습니다.

> [!NOTE]
> 조직 관리 또는 받는 사람 관리의 일부인 경우 Exchange 관리 셸을 사용 하 여 온-프레미스의 공유 사서함으로 사용자 사서함을 변경할 수 있습니다. 예를 들면 `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`와 같습니다.

> [!TIP]
> [공유 사서함이 예기치 않게 사용자 사서함으로 변환 되는](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di) 경우이 지원 솔루션의 해결 방법 참조
  
## <a name="related-articles"></a>관련 문서

[공유 사서함 정보](about-shared-mailboxes.md)

[공유 사서함 만들기](create-a-shared-mailbox.md)

[공유 사서함 구성](configure-a-shared-mailbox.md)

[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)

[공유 사서함의 문제 해결](resolve-issues-with-shared-mailboxes.md)
