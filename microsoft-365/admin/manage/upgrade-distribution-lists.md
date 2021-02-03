---
title: Outlook에서 메일 그룹을 Microsoft 365 그룹으로 업그레이드
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 하나 또는 여러 메일 그룹을 Outlook의 Microsoft 365 그룹으로 업그레이드하는 방법과 PowerShell을 사용하여 여러 메일 그룹을 동시에 업그레이드하는 방법을 알아보고 있습니다.
ms.openlocfilehash: 95f887b4386b349dc9d8bb471deab19b5425f6f5
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080530"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook에서 메일 그룹을 Microsoft 365 그룹으로 업그레이드

Outlook을 사용하여 메일 그룹을 Microsoft 365 그룹으로 업그레이드할 수 있습니다. 이는 조직의 메일 그룹에 Microsoft 365 그룹의 모든 기능을 제공하는 좋은 방법입니다. [Outlook에서 배포 목록을 그룹으로 업그레이드해야 하는 이유](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

DLS를 한 번씩 업그레이드하거나 여러 개를 동시에 업그레이드할 수 있습니다.

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook에서 메일 그룹 하나 또는 여러 개를 Microsoft 365 그룹으로 업그레이드

메일 그룹 업그레이드를 위해 전역 관리자 또는 Exchange 관리자 되어야 합니다. Microsoft 365 그룹으로 업그레이드하려면 메일 그룹에 사서함이 있는 소유자가 있어야 합니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.

2. Exchange 관리 센터에서 받는 사람 **그룹으로** \> **이동 합니다.**<br/>Microsoft 365 그룹으로 업그레이드할 수 있는  메일 그룹(메일 그룹이라고도 하는 메일 그룹)이 있는 것을 나타내는 알림이 표시됩니다.<br/> ![시작 단추 선택](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. 그룹 페이지에서 하나 이상의 메일 그룹(메일 그룹이라고도 합니다)을 선택합니다.  <br/>![메일 그룹 선택](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. 업그레이드 아이콘을 선택합니다.<br/>![Microsoft 365 그룹 아이콘으로 업그레이드](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. 정보 대화 상자에서 **업그레이드를 확인하려면 예를** 선택합니다. 프로세스가 즉시 시작됩니다. 업그레이드할 DLS의 크기와 수에 따라 프로세스에 몇 분 또는 몇 시간이 걸릴 수 있습니다.<br/>메일 목록을 업그레이드할 수 없는 경우 해당 대화 상자가 나타납니다. 업그레이드할 수 없는 메일 [목록을 참조하세요.](#which-distribution-lists-cant-be-upgraded)

6. 여러 메일 목록을 업그레이드하는 경우 드롭다운 목록을 사용하여 업그레이드된 메일 목록을 필터링합니다. 목록이 완료되지 않은 경우 잠시 기다렸다가 **새로** 고침을 선택하여 성공적으로 업그레이드된 것을 볼 수 있습니다.<br/>선택한 모든 DLS에 대해 업그레이드 프로세스가 완료된 경우를 알 수 없습니다. 업그레이드 또는 업그레이드된 **DLS에** 사용할 수  있는 아래에 나열된 것을 보고 이를 알아 볼 수 있습니다.

7. 업그레이드를 위해 DL을 선택했지만 여전히 페이지에 업그레이드 가능한 것으로 나타나면 업그레이드하지 못했습니다. 업그레이드가 작동하지 않는 경우 할 [일에 대한 자세한 내용은 다음을 참조합니다.](#what-to-do-if-the-upgrade-doesnt-work)

> [!NOTE]
> 그룹 다이제스트 전자 메일을 받고 있는 경우 소유자인 적합한 메일 그룹을 업그레이드할 수 있는 메일 그룹이 제공될 수 있습니다. [다이제스트 전자 메일에](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) 대한 자세한 내용은 Outlook에서 그룹 대화 보기를 참조하세요.

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>업그레이드가 작동하지 않는 경우의 작업

업그레이드에 실패한 메일 목록은 변경되지 않습니다.

하나 이상의  적합한 메일 목록을 업그레이드할 수 없는 경우 지원 티켓을 [여는 것입니다.](../contact-support-for-business-products.md) 문제를 알아내기 위해 이 문제는 그룹 엔지니어링 팀으로 에스컬레이터해야 합니다.

서비스 정전으로 메일 목록이 업그레이드되지 않았을 수 있지만 거의 업그레이드되지는 않습니다. 원하는 경우 잠시 기다렸다가 DL을 다시 업그레이드합니다.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>PowerShell을 사용하여 여러 메일 목록을 동시에 업그레이드하는 방법

PowerShell 사용 경험이 있는 경우 UI를 사용하는 대신 이 경로를 이동해야 할 수 있습니다. 메일 목록을 업그레이드하는 데 도움이 되는 cmdlet 집합이 있습니다. 아래를 참조하세요.

### <a name="upgrade-a-single-dl"></a>단일 DL 업그레이드

단일 DL을 업그레이드하려면 다음 명령을 실행합니다.

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

예를 들어 SMTP 주소가 있는 DLS를 업그레이드하려는 dl1@contoso.com 다음 명령을 실행합니다.

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet을 사용하여 단일 메일 그룹을 Microsoft 365 그룹으로 업그레이드할 수도 있습니다.

### <a name="upgrade-multiple-dls-in-a-batch"></a>일괄 처리로 여러 DLS 업그레이드

여러 DLS를 일괄 처리로 전달하고 함께 업그레이드할 수도 있습니다.

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

예를 들어 5개의 DLS를 SMTP 주소 및 DLS로 업그레이드하고 다음 명령을 `dl1@contoso.com` `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` 실행합니다.

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>모든 적합한 DLS 업그레이드

모든 적합한 DLS를 업그레이드하는 방법에는 두 가지가 있습니다.

> [!NOTE]
> 이러한 Upgrade-DistributionGroup cmdlet은 파이프라인에서 데이터를 받지 못합니다. 이러한 이유로 "foreach-object" 연산자를 사용하여 성공적으로 {} 실행해야 합니다.

1. 테넌트에서 적합한 DLS를 얻었다가 업그레이드 명령을 사용하여 업그레이드합니다.

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. 모든 DLS 목록을 표시하고 적합한 DLS만 업그레이드합니다.

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook에서 메일 그룹을 Microsoft 365 그룹으로 업그레이드하는 데 대한 FAQ

### <a name="which-distribution-lists-cant-be-upgraded"></a>업그레이드할 수 없는 메일 목록은 무엇입니까?

클라우드에서 관리되는 단순하고 중첩되지 않은 메일 그룹만 업그레이드할 수 있습니다. 아래 표에는 업그레이드할 수 없는 메일 **목록이** 나열됩니다.

|**속성**|**적합한가요?**|
|:-----|:-----|
|On-premises managed distribution list.  <br/> |아니요  <br/> |
|중첩된 메일 그룹 메일 그룹은 하위 그룹을 들이거나 다른 그룹의 구성원입니다.  <br/> |아니요  <br/> |
|**UserMailbox,** **SharedMailbox, TeamMailbox,** **MailUser가** 구성원이 없는 **RecipientTypeDetails가** 있는 메일 목록   <br/> |아니요  <br/> |
|소유자가 100명 이상인 메일 목록  <br/> |아니요  <br/> |
|구성원만 있지만 소유자가 없는 메일 목록  <br/> |아니요  <br/> |
|특수 문자를 포함하는 별칭이 있는 메일 목록  <br/> |아니요  <br/> |
|메일 목록이 공유 사서함의 전달 주소로 구성된 경우  <br/> |아니요  <br/> |
|DL이 다른 DL에서 **보낸** 사람 제한의 일부인 경우  <br/> |아니요  <br/> |
|보안 그룹  <br/> |아니요  <br/> |
|동적 메일 그룹  <br/> |아니요  <br/> |
|**RoomLists로** 변환된 메일 목록  <br/> |아니요  <br/> |
|**MemberJoinRestriction** 및/또는 **MemberDepartRestriction이 닫힌** 메일 목록   <br/> |아니요  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>업그레이드할 수 있는 DLS 확인

DL이 적합한지 여부를 확인하려는 경우 다음 명령을 실행할 수 있습니다.

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

업그레이드할 수 있는 DLS를 확인하려면 다음 명령을 실행하면 됩니다.

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>업그레이드 스크립트를 실행할 수 있는 사람

전역 관리자 또는 Exchange 관리자 권한이 있는 사용자

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>연락처 카드에 메일 목록이 계속 표시된 이유는 무엇입니까? 업그레이드된 메일 목록이 자동 제안 목록에 표시되지 않도록 방지하려면 어떻게 해야 하나요?

- Outlook의 경우: 마이그레이션 후 Microsoft 365 그룹 이름을 입력하여 Outlook에서 전자 메일을 보내면 받는 사람이 그룹이 아닌 메일 그룹으로 확인됩니다. 받는 사람의 연락처 카드는 메일 목록 연락처 카드가 됩니다. 이는 Outlook의 받는 사람 캐시 또는 별칭 이름 캐시 때문에입니다. 전자 메일이 그룹에 전송되지만 보낸 사람에 혼동을 일으킬 수 있습니다.<br/>이 항목의 단계인 [Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) 자동 완료 목록에 대한 정보를 수행하여 캐시를 다시 설정하면 이 문제가 해결됩니다.

- 웹용 Outlook의 경우: 웹용 Outlook의 경우 메일 목록 받는 사람은 여전히 캐시에 남아 있습니다. 자동 완성 목록에서 [](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) 제안된 이름 또는 전자 메일 주소 제거의 단계에 따라 캐시를 새로 고쳐 그룹 연락처 카드를 볼 수 있습니다.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>새 그룹 구성원이 받은 편지함에서 환영 전자 메일을 받을 수 있나요?

아니요. 환영 메시지를 사용하도록 설정하는 설정은 기본적으로 false로 설정됩니다. 이 설정은 마이그레이션이 완료된 후 참가할 수 있는 기존 그룹 구성원과 새 그룹 구성원 모두에 영향을 미치게 됩니다. 나중에 그룹 소유자가 게스트 사용자를 허용하는 경우 게스트 사용자는 받은 편지함에서 환영 전자 메일을 받지 않습니다. 게스트 구성원은 그룹 작업을 계속할 수 있습니다.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>DLS 중 하나 또는 일부가 업그레이드되지 않은 경우 어떻게 하나요?

DL을 사용할 수 있지만 업그레이드할 수 없는 경우도 있습니다. DL은 업그레이드되지 않고 DL로 남아 있습니다.

- 관리자가 조직의  그룹에 대해 그룹 전자 메일 주소 정책을 적용한 경우 조건을 충족하지 않는 DLS를 업그레이드하려고 시도하면 DL이 업그레이드되지 않습니다.

- **MemberJoinRestriction** 또는 **MemberDepartRestriction이** **Closed로** 설정된 DLS를 업그레이드할 수 없습니다.

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>EAC에서 업그레이드가 실패하면 DL은 어떻게 하나요?

업그레이드는 통화가 서버에 전송될 때만 진행됩니다. 업그레이드가 실패하면 DLS가 변경되지 않습니다. 이 두 는 사용 처럼 작동 합니다.
