---
title: Outlook에서 Microsoft 365 그룹으로 메일 그룹 업그레이드
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
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
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Outlook에서 하나 이상의 메일 그룹을 Microsoft 365 그룹으로 업그레이드 하는 방법 및 PowerShell을 사용 하 여 여러 메일 그룹을 동시에 업그레이드 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 993b0baf46b702322df64693f682e25b0240a0ab
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065672"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook에서 Microsoft 365 그룹으로 메일 그룹 업그레이드

Outlook을 사용 하 여 Microsoft 365 그룹으로 메일 그룹을 업그레이드할 수 있습니다. 이 방법을 통해 조직의 메일 그룹에 Microsoft 365 그룹의 모든 기능과 기능을 제공할 수 있습니다. [Outlook에서 배포 목록을 그룹으로 업그레이드해야 하는 이유](https://support.microsoft.com/en-us/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

Dl은 한 번에 하나씩 또는 여러 개 동시에 업그레이드할 수 있습니다.

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook에서 하나 이상의 메일 그룹을 Microsoft 365 그룹으로 업그레이드

메일 그룹을 업그레이드 하려면 전역 관리자 또는 Exchange 관리자 여야 합니다. Microsoft 365 그룹으로 업그레이드 하려면 메일 그룹에 사서함 소유자가 있어야 합니다. 

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.

2. Exchange 관리 센터에서 **받는 사람** \> **그룹**으로 이동 합니다.<br/>Microsoft 365 그룹으로 업그레이드할 수 있는 메일 **그룹 (메일 그룹이** 라고도 함)이 있음을 알리는 알림이 표시 됩니다.<br/> ![시작 단추를 선택 합니다.](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. **그룹** 페이지에서 하나 이상의 메일 **그룹 (메일 그룹이** 라고도 함)을 선택 합니다.<br/>![메일 그룹 선택](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. 업그레이드 아이콘을 선택 합니다.<br/>![Microsoft 365 그룹으로 업그레이드 아이콘](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. 정보 대화 상자에서 **예** 를 선택 하 여 업그레이드를 확인 합니다. 프로세스가 즉시 시작 됩니다. 업그레이드 중인 Dl의 크기 및 수에 따라 프로세스에 몇 분 또는 몇 시간이 걸릴 수 있습니다.<br/>메일 그룹을 업그레이드할 수 없는 경우에는 대화 상자가 표시 됩니다. [업그레이드할 수 없는 메일 그룹을 확인 하 시겠습니까?](#which-distribution-lists-cannot-be-upgraded).

6. 여러 메일 그룹을 업그레이드 하는 경우 드롭다운 목록을 사용 하 여 업그레이드 된 메일 그룹을 필터링 합니다. 목록이 완료 되지 않으면 잠시 기다린 후 **새로 고침** 을 선택 하 여 업그레이드 된 내용을 확인 합니다.<br/>선택한 모든 Dl에 대해 업그레이드 프로세스가 완료 되 면이를 알리는 알림이 표시 되지 않습니다. 업그레이드 또는 업그레이드 된 **dl**에서 **사용할 수 있는** 항목을 확인 하 여이를 파악할 수 있습니다.

7. 업그레이드할 DL을 선택 했지만 업그레이드 하는 데 사용할 수 있는 페이지에 여전히 표시 되는 경우 업그레이드에 실패 합니다. [업그레이드가 작동 하지 않는 경우 수행할 작업을](#what-to-do-if-the-upgrade-doesnt-work)확인 합니다.

> [!NOTE]
> 그룹 다이제스트 전자 메일을 사용 하는 경우에는 사용자가 담당자로 적합 한 메일 그룹을 업그레이드할 수 있도록 하는 경우를 예로 들 수 있습니다. 다이제스트 전자 메일에 대 한 자세한 내용은 [Outlook에서 그룹 대화 포함를](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) 참조 하세요.


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>업그레이드가 작동 하지 않는 경우 수행할 작업

업그레이드에 실패 한 메일 그룹은 변경 되지 않은 상태로 유지 됩니다.

하나 이상의 **적합** 한 메일 그룹을 업그레이드 하지 못하면 [지원 티켓](../contact-support-for-business-products.md)을 엽니다. 문제를 파악 하기 위해이 문제를 그룹 엔지니어링 팀으로 에스컬레이션 해야 합니다.

서비스 중단으로 인해 메일 그룹이 업그레이드 되지 않을 수 있습니다. 원하는 경우 잠시 기다린 후에 DL을 다시 업그레이드 해 보십시오.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>PowerShell을 사용 하 여 여러 메일 그룹을 동시에 업그레이드 하는 방법

PowerShell을 사용 하 고 있는 경우에는 UI를 사용 하는 대신이 경로를 사용할 수 있습니다. 배포 목록을 업그레이드 하는 데 도움이 되는 일련의 cmdlet이 제공 됩니다. 아래를 참조 하세요.

### <a name="upgrade-a-single-dl"></a>단일 DL 업그레이드

단일 DL을 업그레이드 하려면 다음 명령을 실행 합니다.

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

예를 들어 SMTP 주소 dl1@contoso.com를 사용 하 여 Dl을 업그레이드 하려면 다음 명령을 실행 합니다.

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> [Remove-unifiedgroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet을 사용 하 여 단일 메일 그룹을 Microsoft 365 group으로 업그레이드할 수도 있습니다.

### <a name="upgrade-multiple-dls-in-a-batch"></a>일괄 처리에서 여러 Dl 업그레이드

여러 Dl을 일괄적으로 전달 하 고 함께 업그레이드할 수도 있습니다.

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

예를 들어 SMTP `dl1@contoso.com` 주소 `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com`와을 사용 하 여 5 개의 dl을 업그레이드 하려면 다음 명령을 실행 합니다.

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>모든 적합 한 Dl 업그레이드

모든 적합 한 Dl을 업그레이드 하는 방법에는 두 가지가 있습니다.

> [!NOTE]
> New-distributiongroup cmdlet은 파이프라인의 데이터를 수신 하지 않으므로 "foreach-object{}" 연산자를 사용 하 여 성공적으로 실행 해야 합니다.

1. 테 넌 트에서 적격 Dl을 가져오고 upgrade 명령을 사용 하 여 업그레이드 합니다.

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. 모든 Dl의 목록을 가져오고 적격 Dl만 업그레이드 합니다.

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook에서 메일 그룹을 Microsoft 365 그룹으로 업그레이드 하는 방법에 대 한 FAQ

### <a name="which-distribution-lists-cannot-be-upgraded"></a>업그레이드할 수 없는 메일 그룹은 무엇입니까?

클라우드로 관리 되는 단순 하 고 중첩 되지 않은 메일 목록만 업그레이드할 수 있습니다. 아래 표에는 업그레이드할 **수** 없는 메일 그룹이 나와 있습니다.

|**속성**|**해당?**|
|:-----|:-----|
|온-프레미스 관리 되는 메일 그룹  <br/> |아니요  <br/> |
|중첩 된 메일 그룹 메일 그룹이 하위 그룹을 포함 하거나 다른 그룹의 구성원 이어야 합니다.  <br/> |아니요  <br/> |
|**Usermailbox**, **sharedmailbox**, **teammailbox**, **mailuser** 를 제외한 구성원 **RecipientTypeDetails** 이 포함 된 메일 그룹  <br/> |아니요  <br/> |
|100 개 보다 많은 소유자가 포함 된 메일 그룹  <br/> |아니요  <br/> |
|구성원만 있고 소유자가 없는 메일 그룹  <br/> |아니요  <br/> |
|특수 문자를 포함 하는 별칭이 있는 메일 그룹  <br/> |아니요  <br/> |
|메일 그룹이 공유 사서함의 전달 주소로 구성 된 경우  <br/> |아니요  <br/> |
|DL이 다른 DL의 **보낸 사람 제한** 에 포함 되어 있는 경우  <br/> |아니요  <br/> |
|보안 그룹  <br/> |아니요  <br/> |
|동적 메일 그룹  <br/> |아니요  <br/> |
|**RoomLists** 로 변환 된 메일 그룹  <br/> |아니요  <br/> |
|**Memberjoinrestriction** 및/또는 **MemberDepartRestriction** 가 **닫혀** 있는 메일 그룹  <br/> |아니요  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a>업그레이드할 자격이 있는 Dl을 확인 하려면 어떻게 해야 합니까?

DL이 적합 한지 여부를 확인 하려면 다음 명령을 실행 하면 됩니다.

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

업그레이드할 자격이 있는 Dl을 확인 하려면 다음 명령을 실행 하면 됩니다.

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>업그레이드 스크립트를 실행할 수 있는 사람은 누구 인가요?

전역 관리자 또는 Exchange 관리 권한이 있는 사용자

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>연락처 카드가 여전히 메일 그룹을 표시 하는 이유는 무엇 인가요? 업그레이드 된 메일 그룹이 자동 제안 목록에 표시 되지 않도록 하려면 어떻게 해야 하나요?

- Outlook: 사용자가 마이그레이션 후 Microsoft 365 그룹 이름을 입력 하 여 Outlook에서 전자 메일을 보내려고 하면 받는 사람이 그룹 대신 메일 목록으로 확인 됩니다. 받는 사람의 연락처 카드는 메일 그룹 대화 상대 카드로 표시 됩니다. 이는 받는 사람 캐시 또는 nick 이름 캐시가 Outlook에 있기 때문입니다. 전자 메일을 그룹으로 전송 하지만 보낸 사람에 게 혼란을 줄 수 있습니다.<br/>이 항목의 단계를 수행 하 여 캐시를 다시 설정 하는 [Outlook 자동 완성 목록에 대 한 정보](https://go.microsoft.com/fwlink/?LinkID=798736) 로이 문제를 해결할 수 있습니다.

- 웹용 Outlook의 경우: 웹용 Outlook의 경우 메일 그룹 받는 사람은 여전히 캐시에 남아 있게 됩니다. [자동 완성 목록에서 제안 된 이름 또는 전자 메일 주소 제거](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) 의 단계를 수행 하 여 캐시를 새로 고쳐 그룹 대화 상대 카드를 볼 수 있습니다.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>새 그룹 구성원에 게 받은 편지함에 환영 전자 메일이 전송 됩니까?

아니요. 환영 메시지를 사용 하도록 설정 하는 설정은 기본적으로 false로 설정 됩니다. 이 설정은 마이그레이션이 완료 된 후에 참가할 수 있는 기존 그룹과 새 그룹 구성원에 모두 영향을 줍니다. 나중에 그룹 소유자가 게스트 사용자를 허용 하는 경우 guest 사용자는 자신의 받은 편지함에 환영 전자 메일을 받지 않습니다. 게스트 구성원은 그룹으로 계속 작업할 수 있습니다.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Dl 중 하나 또는 일부가 업그레이드 되지 않으면 어떻게 됩니까?

DL이 적격이 고 업그레이드할 수 없는 경우도 있습니다. DL이 업그레이드 되지 않고 DL로 유지 되지 않습니다.

- 관리자가 조직의 그룹에 대 한 **그룹 전자 메일 주소 정책을** 적용 하 고 기준을 충족 하지 않는 dl을 업그레이드 하려고 하면 dl이 업그레이드 되지 않습니다.

- **Memberjoinrestriction** 또는 **MemberDepartRestriction** 이 **닫힘으로**설정 된 dl은 업그레이드할 수 없습니다.

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>EAC에서 업그레이드가 실패 하는 경우 DL이 어떻게 됩니까?

호출이 서버로 전송 될 때에만 업그레이드 됩니다. 업그레이드가 실패 하는 경우에는 Dl이 그대로 유지 됩니다. 사용 하는 것과 같은 방식으로 작동 합니다.


