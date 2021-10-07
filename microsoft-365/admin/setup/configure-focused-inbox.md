---
title: 조직의 모든 사용자에 대해 중요 받은 편지함 구성
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: 비즈니스 내 모든 사용자의 전자 메일 설정 구성 책임을 맡고 있다면 이 문서에서 사용자의 중요 받은 편지함 구성 방법에 대해 알아보세요.
ms.openlocfilehash: b2c315b6fb4a4c80f245bcf4731b93996753586a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176094"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>조직의 모든 사용자에 대해 중요 받은 편지함 구성

비즈니스의 모든 사람에게 이메일 작동 방법을 구성하는 책임이 있는 경우 이 문서가 적합합니다! 이 문서는 이메일을 비즈니스에 맞게 사용자 지정하거나 해제하는 방법을 설명하고 [자주 묻는 질문](#faq-for-focused-inbox)에 대한 답변을 제공합니다.

자신의 중요 받은 편지함을 끄려면 [중요 받은 편지함 끄기](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2)를 참조하세요.  

사용자가 예를 들어 HR 또는 급여로부터 비즈니스 관련 전자 메일 메시지를 받을 수 있도록 하려면 이러한 메시지가 중요 보기로 오도록 중요 받은 편지함을 구성할 수 있습니다. 사서함에서 중요 받은 편지함이 조직의 사용자에게 표시되도록 할 것인지를 제어할 수도 있습니다.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>조직의 중요 받은 편지함 켜기 또는 끄기

PowerShell을 사용하여 조직의 모든 사용자에 대해 중요 받은 편지함을 켜거나 끕니다. 이 작업을 Microsoft 365 관리 센터에서 수행하고 싶으세요? 저희 엔지니어링 팀에 알려 주세요. **[여기에서 투표하세요!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
**중요 받은 편지함을 끄는 방법**
  
다음 PowerShell 예제는 조직의 중요 받은 편지함을 **끕니다**. 하지만 이렇게 해도 사용자의 기능 사용 가능성은 차단되지 않습니다. 사용자가 원하는 경우 각 클라이언트에서 중요 받은 편지함을 다시 사용하도록 설정할 수 있습니다. 
  
1. [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)

2. 이 절차를 수행하려면 사용 권한이 할당된 상태여야 합니다. 필요한 사용 권한을 확인하려면 [메시징 정책 및 규정 준수 권한](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help)의 "전송 규칙" 항목을 참조하세요.

3. 
            **Get-OrganizationConfig** cmdlet을 실행합니다. 

    ```powershell
    Get-OrganizationConfig
    ```

4. **FocusedInboxOn** 을 찾아 현재 설정을 확인합니다. 

    ![중요 받은 편지함 상태에서의 PowerShell 응답.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. 다음 cmdlet을 실행하여 중요 받은 편지함을 끕니다.

    ```powershell
    Set-OrganizationConfig -FocusedInboxOn $false
    ```

6. **Get-OrganizationConfig** cmdlet을 다시 실행하면 FocusedInboxOn이 $false로 설정되며, 이는 중요 받은 편지함이 꺼졌음을 의미합니다. 

**중요 받은 편지함을 켜는 방법:**
  
- 위의 5단계에서 다음 cmdlet을 실행하여 중요 받은 편지함을 켭니다.

  ```powershell
  Set-OrganizationConfig -FocusedInboxOn $true
  ```
    
## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>중요 받은 편지함을 켜면 사용자에게 어떻게 표시되나요? 

Outlook을 닫았다가 다시 시작해야 중요 보기가 사용자에게 표시됩니다. Outlook을 다시 시작하면 Outlook 사용자 인터페이스에 새 중요 받은 편지함을 사용하기 위한 옵션을 제공하는 팁이 표시됩니다.
  
![사용자가 처음으로 웹용 Outlook을 열 때 중요 받은 편지함의 이미지입니다.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
낮은 우선 순위 메일에서 중요 받은 편지함으로 전환하는 경우 사용자가 이를 사용하도록 설정할지("사용해 보기") 또는 이 기능을 해제할지를 결정할 수 있습니다. 여러(지원되는) 클라이언트가 있는 경우 사용자는 각각에서 개별적으로 중요 받은 편지함을 사용하거나 사용하지 않도록 설정할 수 있습니다. 팁은 다음과 같습니다.
  
![중요 받은 편지함이 사용자에게 배포되고 Outlook을 다시 열었을 때 중요 받은 편지함이 어떻게 표시되는지를 보여 주는 이미지](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
사용자가 중요 받은 편지함을 사용하기로 결정하면 낮은 우선 순위 메일이 자동으로 사용하지 않도록 설정됩니다. 낮은 우선 순위 메일 폴더는 사용자가 이름을 바꾸거나 삭제할 수 있는 표준 폴더로 변환됩니다.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>특정 사용자에 대해 중요 받은 편지함 켜기 또는 끄기

이 예제에서는 Contoso 조직의 Tim Matthews에 대해 중요 받은 편지함을 **끕니다**. 하지만 이렇게 해도 Tim Matthews의 기능 사용 가능성은 차단되지 않습니다. Tim Matthews가 원하는 경우 각 클라이언트에서 중요 받은 편지함을 다시 사용하도록 설정할 수 있습니다. 
  
1. [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)

2. 이 절차를 수행하려면 사용 권한이 할당된 상태여야 합니다. 필요한 사용 권한을 확인하려면 Messaging policy and compliance permissions(메시징 정책 및 규정 준수 권한) 항목에서 “Transport rules”(전송 규칙) 항목을 참조하세요.

3. **Get-FocusedInbox** cmdlet을 실행합니다. 예를 들면 다음과 같습니다. 

    ```powershell
    Get-FocusedInbox -Identity <tim@contoso.com>
    ```

4. FocusedInboxOn을 찾아 현재 설정을 확인합니다.

    ![중요 받은 편지함 상태에서의 PowerShell 응답.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. 다음 cmdlet를 실행하여 중요 받은 편지함을 끕니다.

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
    ```

    또는 다음 cmdlet을 실행하여 중요 받은 편지함을 켭니다.

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
    ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>UI를 사용하여 전자 메일 메시지를 모든 사용자의 중요 보기로 보내도록 전송 규칙을 만듭니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.

2. **메일 흐름** \>규칙 **으로 이동합니다.** EAC 추가 아이콘![을 선택합니다. ](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif)한 다음 **새 규칙 만들기...** 를 선택합니다. 

3. 새 규칙 만들기가 완료되면 **저장** 을 선택하여 해당 규칙을 시작합니다.

    다음 이미지는 "급여 부서"의 모든 메시지가 중요 받은 편지함으로 배달되는 예를 보여 줍니다.

    ![focusedinbox 급여.](../../media/focusedinbox-transport-rule.PNG)

    > [!NOTE]
    > 이 예제에서 메시지 헤더 값 텍스트는 **X-MS-Exchange-Organization-BypassFocusedInbox** 입니다.
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>PowerShell을 사용하여 전자 메일 메시지를 모든 사용자의 중요 보기로 보내도록 전송 규칙을 만듭니다.

1. [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)

2. 이 절차를 수행하려면 사용 권한이 할당된 상태여야 합니다. 필요한 사용 권한을 확인하려면 [메시징 정책 및 규정 준수 권한](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help)의 "전송 규칙" 항목을 참조하세요.

3. 예를 들어 다음 명령을 실행하여 "급여 부서"의 모든 메시지가 중요 받은 편지함으로 배달되도록 할 수 있습니다.

    ```powershell
    New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
    ```

> [!IMPORTANT]
> 이 예제에서 "X-MS-Exchange-Organization-BypassFocusedInbox" 및 "true" 모두 대소문자를 구분합니다. 또한 중요 받은 편지함은 낮은 우선 순위 메일을 바이패스하는 X-헤더를 준수하므로 낮은 우선 순위 메일에서 이 설정을 사용하는 경우 중요 받은 편지함에서도 사용됩니다. 자세한 구문 및 매개 변수 정보는 [New-TransportRule](/powershell/module/exchange/new-transportrule)을 참조하세요.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

전자 메일 메시지 헤더를 확인하여 중요 받은 편지함 전송 규칙 바이패스로 인해 받은 편지함으로 전자 메일 메시지가 도착하는지 확인할 수 있습니다. 중요 받은 편지함 전송 규칙이 적용된 조직의 사서함에서 전자 메일 메시지를 선택합니다. 메시지에 스탬프 처리된 헤더를 확인하고 **X-MS-Exchange-Organization-BypassFocusedInbox: true** 헤더를 확인해야 합니다. 이는 바이패스가 작동 중임을 의미합니다. 헤더 정보를 찾는 방법에 대한 정보는 [전자 메일 메시지에 대한 인터넷 헤더 정보 확인](https://go.microsoft.com/fwlink/p/?LinkId=822530) 문서를 참조하세요.

### <a name="what-will-the-user-see"></a>사용자에게는 어떻게 표시되나요?

메일 흐름 규칙이 제대로 설정됐다면 재정의 알림이 표시됩니다. 웹용 Outlook의 경우 “항상 기타 받은 편지함으로 이동”이 사용하지 않게 설정되고 도구 설명이 표시됩니다. 데스크톱 Outlook 클라이언트의 경우 “항상 기타 받은 편지함으로 이동” 선택이 허용되며 대화 팝업 메시지가 표시됩니다.

## <a name="turn-onoff-clutter"></a>낮은 우선 순위 메일 켜기/끄기

일부 사용자에서 낮은 우선 순위 메일이 갑자기 작동 중지되었다는 보고를 받았습니다. 이 경우 특정 사용자에 대해 낮은 우선 순위 메일을 다시 사용하도록 설정할 수 있습니다. [조직에 대한 낮은 우선 순위 메일 구성](../email/configure-clutter.md)을 참조하세요.

## <a name="faq-for-focused-inbox"></a>중요 받은 편지함에 대한 FAQ

다음은 중요 받은 편지함에 대한 질문과 대답입니다.

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>조직에서 중요 받은 편지함 배포 방법을 제어할 수 있나요?

예. 전체 조직에 대해 중요 받은 편지함을 켜거나 끌 수도 있고 지정된 사용자에 대해 켜거나 끌 수도 있습니다. 위 내용을 참조하세요.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>중요 받은 편지함은 Office 2016 클라이언트에서만 사용할 수 있는 기능인가요?

예, Office 2016을 사용하는 사용자만 영향을 받습니다. 이 기능은 Outlook 2013 또는 이전 버전에는 적용되지 않습니다.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Outlook에서 중요 받은 편지함 변경 사항을 적용하려면 시간이 얼마나 걸리나요?

중요 받은 편지함을 켜거나 끄고 난 후 사용자가 Outlook을 닫았다가 다시 시작하면 설정이 적용됩니다.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>중요 받은 편지함을 켜면 낮은 우선 순위 메일은 어떻게 나요?

전환한 다음 낮은 우선 순위 메일 폴더로 더 이상 덜 실행 가능한 전자 메일이 수신되지 않습니다. 그 대신 전자 메일이 받은 편지함의 중요 및 기타 탭으로 수신됩니다. 중요 받은 편지함에는 낮은 우선 순위 메일 폴더로 항목을 이동하던 동일한 알고리즘이 적용됩니다. 즉, 낮은 우선 순위 메일로 이동되도록 설정된 모든 전자 메일이 이제는 기타로 이동됩니다. 이미 낮은 우선 순위 메일 폴더에 포함된 메시지는 사용자가 삭제하거나 이동할 때까지 해당 폴더에 남아 있습니다.
  
Microsoft MVP인 [Tony Redmond](https://www.petri.com/author/tony-redmond)의 다음 게시물을 확인해 보세요. [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365)(Office 365 내에서 중요 받은 편지함이 낮은 우선 순위 메일을 대체하는 방법)
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>낮은 우선 순위 메일의 사용자를 유지할 수 있나요? 낮은 우선 순위 메일 및 중요 받은 편지함 사용에 대한 Microsoft의 권장 사항은 무엇인가요?

예, 낮은 우선 순위 메일의 사용자를 유지하고 중요 받은 편지함을 사용하지 않도록 설정할 수 있습니다. 하지만 결국 낮은 우선 순위 메일이 중요 받은 편지함으로 완전히 대체되므로 Microsoft에서는 지금 바로 중요 받은 편지함으로 이동하는 것을 권장합니다. Exchange Online에서 낮은 우선 순위 메일을 사용하는 경우에 대해 자세히 알아보려면 다음 블로그 게시물을 참조하세요. [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)(중요 받은 편지함에 대한 업데이트 및 낮은 우선 순위 메일에 대한 우리의 계획)
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>모든 사용자가 중요 받은 편지함으로 이동하려는 경우 일반 사용자에 대해 낮은 우선 순위 메일을 사용하지 않도록 설정해야 하나요?

아니요. Set-Clutter cmdlet을 실행하여 명시적으로 사서함에 대해 낮은 우선 순위 메일을 사용하지 않도록 설정할 수 있습니다. 그러나 이렇게 하면 이전에 낮은 우선 순위 메일 폴더로 리디렉션된 메시지는 해당 받은 편지함에 그대로 유지되며 중요 받은 편지함을 지원하는 버전으로 해당 클라이언트가 업그레이드될 때까지 이들 메시지를 처리해야 한다는 메시지가 사서함 소유자에게 표시됩니다. 따라서 업그레이드된 클라이언트를 사용할 수 있을 때까지 낮은 우선 순위 메일을 사용하지 않도록 설정하는 것이 가장 좋습니다.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>중요 받은 편지함 관리를 위해 두 가지 cmdlet이 있는 이유는 무엇인가요?

중요 받은 편지함과 연관된 상태는 두 가지가 있습니다.
  
- **조직 수준**: 중요 받은 편지함 상태 및 연관된 마지막 업데이트 타임스탬프입니다.

- **사서함 수준​​**: 중요 받은 편지함 상태 및 연관된 마지막 업데이트 타임스탬프입니다. 

### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Outlook에서 이러한 두 가지 상태로 중요 받은 편지함 환경 표시를 결정하는 방법은 무엇인가요?

Outlook은 최신 타임스탬프가 있는 cmdlet을 선택하여 환경 표시를 결정합니다. 기본적으로 두 타임스탬프 모두 “null”이며 이런 경우에는 이 기능이 사용하도록 설정됩니다.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>조직에서 중요 받은 편지함을 껐는데 Get-FocusedInbox cmdlet에서 “true”를 반환하는 이유는 무엇인가요?

중요 받은 편지함을 제어하는 cmdlet은 두 가지입니다. 사서함에 대해 Get-FocusedInbox를 실행하면 이 기능의 사서함 수준 상태를 반환합니다. Outlook의 환경은 마지막으로 수정된 cmdlet 상태를 기반으로 선택됩니다.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>스크립트를 실행하여 중요 받은 편지함을 설정한 사용자를 확인할 수 있나요?

아니요. 불가능하도록 설계되어 있습니다. 중요 받은 편지함 사용 여부는 클라이언트 쪽 설정이므로 cmdlet에서는 사용자의 사서함을 클라이언트 환경에 사용할 수 있는지만 알려 줄 수 있습니다. 동시에 어떤 클라이언트에서는 사용하도록 설정하고 어떤 클라이언트에서는 사용하지 않도록 설정할 수도 있습니다. 예를 들어 Outlook 앱과 Outlook 모바일에서는 사용하지만 웹용 Outlook에서는 사용하지 않도록 설정할 수 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[조직에 대한 낮은 우선 순위 메일 구성](../email/configure-clutter.md)(문서)\
[공유 사서함 설정 구성](../email/configure-a-shared-mailbox.md)(문서)\
[서명 및 고지 사항 만들기](create-signatures-and-disclaimers.md)(비디오)
