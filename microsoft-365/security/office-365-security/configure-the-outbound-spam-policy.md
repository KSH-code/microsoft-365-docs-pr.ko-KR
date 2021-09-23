---
title: 아웃바운드 스팸 필터링 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(2013)에서 아웃바운드 스팸 정책을 보고, 만들고, 수정하고, 삭제하는 Exchange Online Protection 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec82ce1f1049039fc6f4317662e5de016ba381d7
ms.sourcegitcommit: 0ed93816e2c1e6620e68bd1c0f00390062911606
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59483822"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>EOP에서 아웃바운드 스팸 필터링 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 Exchange Online 사서함이 없는 조직에서는 EOP를 통해 전송되는 아웃바운드 전자 메일 메시지에서 스팸 및 비정상적인 보내는 활동이 자동으로 확인됩니다.

조직의 사용자로부터의 아웃바운드 스팸은 일반적으로 손상된 계정을 나타냅니다. 의심스러운 아웃바운드 메시지는 스팸으로 표시되어(스팸 지수 또는 SCL에 관계없이) [](high-risk-delivery-pool-for-outbound-messages.md) 서비스의 신뢰도 보호를 위해 고위험 배달 풀을 통해 라우팅됩니다(즉, ip 차단 목록에서 Microsoft 365 원본 전자 메일 서버를 유지). 관리자는 경고 정책을 통해 의심스러운 아웃바운드 전자 메일 활동 및 차단된 사용자에게 자동으로 [알림을 수신합니다.](../../compliance/alert-policies.md)

EOP는 스팸에 대한 조직의 전반적인 방어의 일부로 아웃바운드 스팸 정책을 사용 합니다. 자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조하세요.

관리자는 기본 아웃바운드 스팸 정책을 보고, 편집하고, 구성할 수 있지만 삭제할 수 없습니다. 세분성을 강화하기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 아웃바운드 스팸 정책을 만들 수도 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.

Microsoft 365 Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online PowerShell)에서 Microsoft 365 사서함이 있는 Exchange Online 독립 실행형 EOP PowerShell에서 아웃바운드 스팸 정책을 구성할 수 있습니다. 조직에 Exchange Online 없는 조직)

EOP에서 아웃바운드 스팸 정책의 기본 요소는 다음입니다.

- **아웃바운드 스팸** 필터 정책: 아웃바운드 스팸 필터링 판정 및 알림 옵션에 대한 작업을 지정합니다.
- **아웃바운드** 스팸 필터 규칙: 아웃바운드 스팸 필터 정책에 대한 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.

이러한 두 요소 간의 차이는 웹 사이트 포털에서 아웃바운드 스팸 Microsoft 365 Defender 명확하지 않습니다.

- 정책을 만들 때 실제로 둘 다에 대해 동일한 이름을 사용하여 아웃바운드 스팸 필터 규칙과 연결된 아웃바운드 스팸 필터 정책을 동시에 만들게 됩니다.
- 정책을 수정할 때 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 아웃바운드 스팸 필터 규칙을 수정합니다. 다른 모든 설정은 연결된 아웃바운드 스팸 필터 정책을 수정합니다.
- 정책을 제거하면 아웃바운드 스팸 필터 규칙 및 연결된 아웃바운드 스팸 필터 정책이 제거됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다. 자세한 내용은 이 문서의 Exchange Online PowerShell 또는 독립 실행형 [EOP PowerShell을](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 사용하여 아웃바운드 스팸 정책 구성 섹션을 참조하세요.

모든 조직에는 Default라는 기본 제공 아웃바운드 스팸 정책이 있습니다. 이 정책에는 다음 속성이 있습니다.

- 정책과 연결된 아웃바운드 스팸 필터 규칙(받는 사람 필터)이 없는 경우에도 이 정책은 조직의 모든 받는 사람에게 적용됩니다.
- 정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨). 사용자가 만든 모든 사용자 지정 정책은 항상 기본 정책보다 우선합니다.
- 그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.

아웃바운드 스팸 필터링의 효율성을 높이기 위해 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 아웃바운드 스팸 정책을 만들 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다. **스팸 방지 설정** 페이지로 바로 이동하려면 <https://security.microsoft.com/antispam>을 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.
  - 아웃바운드 스팸 정책을 추가, 수정 및 삭제하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이면** 됩니다.
  - 아웃바운드 스팸 정책에 대한 읽기 전용 액세스의  경우 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이면** 됩니다.

  자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹도 기능에 대한 읽기 전용 권한을 부여합니다.

- 아웃바운드 스팸 정책에 대한 권장 설정은 [EOP 아웃바운드 스팸 필터 정책 설정 을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)

- 이름이 [](../../compliance/alert-policies.md) Email **sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** **(Global admins**) group about unusual outbound email activity and blocked users due to outbound spam. 자세한 내용은 [제한된 사용자에 대한 경고 설정 확인을 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) 아웃바운드 스팸 정책의 알림 옵션 대신 이러한 경고 정책을 사용하는 것이 좋습니다.

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a>Microsoft 365 Defender 포털을 사용하여 아웃바운드 스팸 정책 만들기

Microsoft 365 Defender 포털에서 사용자 지정 아웃바운드 스팸 정책을 만들면 스팸 필터 규칙과 연결된 스팸 필터 정책이 동시에 동일한 이름을 사용하여 생성됩니다.

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. 스팸 **방지 정책 페이지에서** 만들기 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **정책을 만든** 다음 드롭다운 목록에서 아웃바운드를 선택합니다. 

3. 정책 마법사가 열립니다. **정책 이름 페이지** 에서 다음 설정을 구성합니다.
   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다.
   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. 표시되는 **사용자, 그룹 및 도메인** 페이지에서 정책이 적용되는 내부 받는 사람(받는 사람 조건)을 식별합니다.
   - **사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.
   - **그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.
   - **도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.

   적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다. 이 프로세스를 필요한 만큼 반복합니다. 기존 값을 제거하려면 제거를 클릭합니다. ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 값 옆에 있습니다.

   사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다. 사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.

   동일한 조건의 여러 값은 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 서로 다른 조건은 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

   - **다음 사용자, 그룹 및 도메인 제외**: 정책이 적용되는 내부 받는 사람에 대한 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다. 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. 열 **수 있는 보호 설정** 페이지에서 다음 설정을 구성합니다.
   - **메시지 제한:** 이 섹션의 설정은 사서함의 아웃바운드 전자 **메일 메시지에 Exchange Online** 구성합니다.
     - **외부 메시지 제한 설정:** 시간당 최대 외부 받는 사람 수입니다.
     - **내부 메시지 제한 설정:** 시간당 최대 내부 받는 사람 수입니다.
     - **일별 메시지 제한 설정:** 하루 최대 받는 사람 수입니다.

     유효한 값은 0에서 10000까지입니다. 기본값은 0으로, 서비스 기본값이 사용됩니다. 자세한 내용은 보내기 [제한을 참조하세요.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

    상자에 값을 입력하거나 상자에 늘리기/축소 화살표를 사용할 수 있습니다.

   - **메시지 제한에** 도달한 사용자에게 적용된 제한: 보호 설정 섹션의 제한이  초과되는 경우 드롭다운 목록에서 작업을 선택합니다.

     모든 작업에 대해 사용자에 지정된  받는 사람이 전자 메일 경고 정책을 보내지  못하도록 제한했습니다(그리고 이 페이지의 나중에 아웃바운드 스팸 설정으로 인해 보낸 사람이 차단된 경우 현재 중복된 알림에서) 전자 메일 알림을 수신합니다.

     - **다음 날까지 사용자가** 메일을 보내지 못하도록 제한 : 이 값은 기본값입니다. 전자 메일 알림이 전송됩니다. 사용자는 UTC 시간을 기준으로 다음 날까지 더 이상 메시지를 보낼 수 없습니다. 관리자가 이 블록을 다시 정할 수 있는 방법은 없습니다.
       - 전자 메일을 보내지 못하도록 제한된 **사용자라는** 경고 정책은  관리자에게 전자 메일 및 인시던트 & 경고 보기 페이지를 통해 알림을 \>  제공합니다.
       - 정책의 아웃바운드 스팸 보내기 설정으로 인해 보낸 사람이 차단된 경우 특정 사용자에게 알림에 지정된 받는 사람도 알림을 보냅니다. 
       - 사용자는 UTC 시간을 기준으로 다음 날까지 더 이상 메시지를 보낼 수 없습니다. 관리자가 이 블록을 다시 정할 수 있는 방법은 없습니다.
     - **사용자가 메일을** 보내지 못하도록 제한: 전자 메일 알림이 전송되고, 사용자가 Microsoft 365 Defender 포털에서 제한된 사용자에게 추가되고, 관리자가 제한된 사용자에서 제거될 때까지 전자 메일을 보낼 수  <https://security.microsoft.com/restrictedusers> 없습니다.  관리자가 목록에서 사용자를 제거한 후 해당 일에 대해 사용자를 다시 제한하지 않습니다. 자세한 내용은 스팸 전자 메일을 전송한 후 제한된 사용자 포털에서 [사용자 제거를 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md)
     - **작업 없음, 알림만:** 전자 메일 알림이 전송됩니다.

   - **전달 규칙:** 이 섹션의 설정을 사용하여 사서함을 외부 보낸 **Exchange Online 자동** 전자 메일 전달을 제어합니다. 자세한 내용은 에서 자동 외부 전자 메일 전달 [제어를 Microsoft 365.](external-email-forwarding.md)

     > [!NOTE]
     > 자동 전달을 사용하지 않도록 설정하면 외부 보낸 사람이 전달이 있는 사서함으로 전자 메일을 보내는 경우 받는 사람은 배달 못함 보고서(NDR 또는 반송 메시지라고도함)를 받게 됩니다. 내부 보낸 사람이 메시지를 보내고  전달 방법이 사서함 [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) _전달(SMTP_ 전달)인 경우 내부 보낸 사람이 NDR을 얻습니다. 받은 편지함 규칙으로 인해 전달이 발생한 경우 내부 보낸 사람이 NDR을 얻지 못합니다.

     자동 전달 규칙 드롭다운 목록에서 다음 작업 중 **하나를** 선택합니다.

     - **자동 - 시스템 제어**: 아웃바운드 스팸 필터링을 통해 자동 외부 전자 메일 전달을 제어할 수 있습니다. 이 값은 기본값입니다.
     - **On**: 정책에 의해 자동 외부 전자 메일 전달을 사용하지 않도록 설정되지 않습니다.
     - **Off:** 정책에 의해 모든 자동 외부 전자 메일 전달을 사용하지 않도록 설정됩니다.

   - **알림:** 섹션의 설정을 사용하여 의심스러운 아웃바운드 전자 메일 메시지의 복사본 및 알림을 수신해야 하는 추가 받는 사람을 구성합니다.

     - **이러한 사용자** 및 그룹에 이러한 제한을 초과하는 의심스러운 아웃바운드 복사본 보내기: 이 설정은 지정된 받는 사람을 의심스러운 아웃바운드 메시지의 Bcc 필드에 추가합니다.

       > [!NOTE]
       > 이 설정은 기본 아웃바운드 스팸 정책에서만 작동합니다. 만드는 사용자 지정 아웃바운드 스팸 정책에서는 작동하지 않습니다.

       이 설정을 사용하도록 설정하려면 확인란을 선택합니다. 상자가 나타나면 상자를 클릭하고 유효한 전자 메일 주소를 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 전체 값을 선택합니다.

       필요한 만큼 이 단계를 반복합니다. 기존 값을 제거하려면 제거를 클릭합니다. ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 값 옆에 있습니다.

   - **아웃바운드 스팸 전송으로 인해 보낸 사람이 차단된 경우 이러한 사용자 및 그룹에 알릴 수 있습니다.**

     > [!IMPORTANT]
     >
     > - 이 설정은 아웃바운드 스팸 정책에서 사용되지 않습니다.
     >
     > - 전자 [메일을](../../compliance/alert-policies.md) 보내지 않는 **사용자라는** 기본 경고 정책은 사용자가 받는 사람 제한 섹션의 제한을 초과하여 차단된 경우 **이미 TenantAdmins(전역** **관리자)** 그룹의 구성원에게 전자 메일 알림을 보냅니다.  아웃바운드 스팸 정책에서 이 설정이 아닌 경고 정책을 사용하여 관리자 및 다른 사용자에게 **알리는 것이 좋습니다.** 자세한 내용은 [제한된 사용자에 대한 경고 설정 확인을 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)

   작업을 마친 후 **다음** 을 클릭합니다.

6. 표시되는 **검토** 페이지에서 설정을 검토합니다. 각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다. 또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.

   작업을 마쳤으면 **닫기** 를 클릭합니다.

7. 표시되는 확인 페이지에서 **완료** 를 클릭합니다.

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a>Microsoft 365 Defender 포털을 사용하여 아웃바운드 스팸 정책 보기

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. **스팸 방지 정책** 페이지에서 다음 값 중 하나를 찾습니다.
   - 유형 **값은** 사용자 지정 **아웃바운드 스팸 정책입니다.**
   - Name **값은** **스팸 방지 아웃바운드 정책(기본값)입니다.**

   스팸 방지 정책 목록에는 다음 속성이 표시됩니다.

   - **이름**
   - **상태**
   - **우선 순위**
   - **유형**

3. 이름을 클릭하여 아웃바운드 스팸 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a>Microsoft 365 Defender 포털을 사용하여 아웃바운드 스팸 정책 수정

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. 스팸 **방지 정책 페이지에서** 이름을 클릭하여 목록에서 아웃바운드 스팸 정책을 선택합니다.
   - 유형 열의 값이 사용자 지정  아웃바운드 스팸 정책인 경우 만든 사용자 지정 **정책입니다.**
   - 스팸 방지 아웃바운드 **정책(기본값)이라는 기본 정책입니다.**

3. 표시되는 정책 세부 정보 플라이아웃에서 각 섹션에서 **편집** 을 선택하여 섹션 내의 설정을 수정합니다. 설정에 대한 자세한 내용은 이 문서의 이전 Microsoft 365 Defender [포털을](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies) 사용하여 아웃바운드 스팸 정책 만들기 섹션을 참조하세요.

   기본 아웃바운드 스팸  정책의 경우 적용된 섹션을 사용할 수 없습니다(정책은 모든 사람에 적용), 정책의 이름을 바출 수 없습니다.

정책을 사용하도록 설정하거나 사용하지 않도록 설정하거나, 정책 우선 순위 순서를 설정하거나, 최종 사용자 알림을 구성하려면 다음 섹션을 참조하세요.

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>사용자 지정 아웃바운드 스팸 정책 사용 또는 사용 안 하도록 설정

기본 아웃바운드 스팸 정책은 사용하지 않도록 설정할 수 없습니다.

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. 스팸 **방지 정책 페이지에서** 이름을 클릭하여 목록에서 사용자 지정  **아웃바운드** 스팸 정책 유형 값이 있는 정책을 선택합니다.

3. 표시되는 정책 세부 정보 플라이아웃 맨 위에 다음 값 중 하나가 표시됩니다.
   - **정책 꺼짐**: 정책을 켜려면 ![켜기 아이콘.](../../media/m365-cc-sc-turn-on-off-icon.png) **켜기** 를 클릭합니다.
   - **정책 켜짐**: 정책을 끄려면 ![끄기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **끄기** 를 클릭합니다.

4. 표시되는 확인 대화 상자에서 **켜기** 또는 **끄기** 를 클릭합니다.

5. 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.

기본 정책 페이지로 돌아가면 정책의 **상태** 값이 **켜짐** 또는 **꺼짐** 입니다.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>사용자 지정 아웃바운드 스팸 정책의 우선 순위 설정

기본적으로 아웃바운드 스팸 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

정책의 우선 순위를 변경하려면 정책 속성에서 **우선 순위를 높이** 거나 **우선 순위를 낮춥** 니다(Microsoft 365 Defender 포털에서 **우선 순위** 번호를 직접 수정할 수 없습니다). 정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우에만 의미가 있습니다.

 **참고**:

- Microsoft 365 Defender 포털에서 아웃바운드 스팸 정책을 만든 후에만 우선 순위를 변경할 수 있습니다. PowerShell에서 사용자는 기존 규칙의 우선순위에 영향을 줄 수 있는 스팸 필터 규칙을 만들 때 기본 우선순위를 재정의할 수 있습니다.
- 아웃바운드 스팸 정책은 표시되는 순서대로 처리됩니다(첫 번째  정책의 우선 순위 값은 0). 기본 아웃바운드 스팸 정책의 우선 순위 값은 **가장** 낮습니다. 이 값은 변경할 수 없습니다.

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. 스팸 **방지 정책** 페이지에서 이름을 클릭하여 목록에서  사용자 지정 **아웃바운드** 스팸 정책 유형 값이 있는 정책 선택을 선택합니다.

3. 표시되는 정책 세부 정보 플라이아웃 맨 위에 현재 우선 순위 값 및 사용자 지정 정책 수를 기준으로 **우선순위 증가** 또는 **우선순위 감소** 가 표시됩니다.
   - 우선 순위 값이 **0인** 아웃바운드 스팸 정책에는 우선 순위 감소 옵션만 사용할 **수** 있습니다. 
   - 우선 순위 값이 가장  낮은 아웃바운드 스팸 정책(예: **3)에는** 우선 순위 늘리기 옵션만 사용할 **수** 있습니다.
   - 아웃바운드 스팸 정책이 세 개 이상 있는 경우 우선 순위가 가장 높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 옵션을 모두 사용할 **수** 있습니다. 

   ![우선 순위 증가 아이콘](../../media/m365-cc-sc-increase-icon.png) **우선 순위 증가** 또는 ![우선 순위 감소 아이콘](../../media/m365-cc-sc-decrease-icon.png) **우선순위 감소** 를 클릭하여 **우선 순위** 값을 변경합니다.

4. 작업을 마쳤으면 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a>Microsoft 365 Defender 포털을 사용하여 사용자 지정 아웃바운드 스팸 정책 제거

Microsoft 365 Defender 포털을 사용하여 사용자 지정 아웃바운드 스팸 정책을 제거하면 스팸 필터 규칙과 해당 스팸 필터 정책이 모두 삭제됩니다. 기본 아웃바운드 스팸 정책은 제거할 수 없습니다.

1. Microsoft 365 Defender 포털의 **정책** 섹션에서 **전자 메일 및 공동 작업**\>**정책 및 규칙**\>**위협 정책**\>**스팸 방지** 로 이동합니다.

2. 스팸 **방지 정책 페이지에서** 이름을 클릭하여 목록에서 사용자 지정  **아웃바운드** 스팸 정책 유형 값이 있는 정책을 선택합니다. 표시되는 정책 세부 정보 플라이아웃 상단에서 ![추가 작업 아이콘](../../media/m365-cc-sc-more-actions-icon.png)을 클릭합니다. **추가 작업** \> ![정책 아이콘 삭제](../../media/m365-cc-sc-delete-icon.png) **정책 삭제**.

3. 확인 대화 상자가 나타나면 **예** 를 클릭합니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 아웃바운드 스팸 정책 구성

앞서 설명한 바와 같이 아웃바운드 스팸 정책은 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙으로 구성됩니다.

PowerShell Exchange Online 독립 실행형 EOP PowerShell에서 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙의 차이는 분명합니다. **\* -HostedOutboundSpamFilterPolicy** cmdlet을 사용하여 아웃바운드 스팸 필터 정책을 관리하고 **\* -HostedOutboundSpamFilterRule** cmdlet을 사용하여 아웃바운드 스팸 필터 규칙을 관리합니다.

- PowerShell에서 아웃바운드 스팸 필터 정책을 먼저 만든 다음 규칙이 적용되는 정책을 식별하는 아웃바운드 스팸 필터 규칙을 생성합니다.
- PowerShell에서는 아웃바운드 스팸 필터 정책 및 아웃바운드 스팸 필터 규칙의 설정을 별도로 수정합니다.
- PowerShell에서 아웃바운드 스팸 필터 정책을 제거하면 해당 아웃바운드 스팸 필터 규칙이 자동으로 제거되지 않습니다.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell을 사용하여 아웃바운드 스팸 정책 만들기

PowerShell에서 아웃바운드 스팸 정책을 만드는 과정은 다음 두 단계로 진행됩니다.

1. 아웃바운드 스팸 필터 정책을 생성합니다.
2. 규칙이 적용되는 아웃바운드 스팸 필터 정책을 지정하는 아웃바운드 스팸 필터 규칙을 생성합니다.

   **참고**:

   - 새 아웃바운드 스팸 필터 규칙을 만들고 기존의 통합되지 않은 아웃바운드 스팸 필터 정책을 할당할 수 있습니다. 아웃바운드 스팸 필터 규칙은 두 개 이상의 아웃바운드 스팸 필터 정책과 연결될 수 없습니다.
   - 정책을 만든 후까지 Microsoft 365 Defender 포털에서 사용할 수 없는 PowerShell의 새 아웃바운드 스팸 필터 정책에 대해 다음 설정을 구성할 수 있습니다.
     - 새 정책을 사용하지 않도록 `$false` **설정합니다(New-HostedOutboundSpamFilterRule** cmdlet에서 사용).
     -  _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet에서 만들 때 정책의 우선 순위(우선 순위)를 설정하십시오.
   - PowerShell에서 만든 새 아웃바운드 스팸 필터 정책은 아웃바운드 스팸 필터 규칙에 정책을 할당할 때까지 Microsoft 365 Defender 포털에 표시되지 않습니다.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>1단계: PowerShell을 사용하여 아웃바운드 스팸 필터 정책 만들기

아웃바운드 스팸 필터 정책을 만들 경우 다음 구문을 사용 합니다.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

이 예에서는 다음 설정을 사용하여 Contoso Executives라는 새 아웃바운드 스팸 필터 정책을 만듭니다.

- 받는 사람 비율 제한은 기본값인 더 작은 값으로 제한됩니다. 자세한 내용은 여러 옵션 에서 Microsoft 365 [참조하세요.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

- 제한 중 하나에 도달하면 사용자가 메시지를 보낼 수 없습니다.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

구문과 매개 변수에 대한 자세한 내용은 [New-HostedOutboundSpamFilterPolicy를 참조하십시오.](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>2단계: PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 만들기

아웃바운드 스팸 필터 규칙을 만들 경우 다음 구문을 사용 합니다.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

이 예에서는 다음 설정을 사용하여 Contoso Executives라는 새 아웃바운드 스팸 필터 규칙을 만듭니다.

- Contoso Executives라는 아웃바운드 스팸 필터 정책은 규칙과 연결됩니다.
- 이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

구문과 매개 변수에 대한 자세한 내용은 [New-HostedOutboundSpamFilterRule을 참조하십시오.](/powershell/module/exchange/new-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 정책 보기

모든 아웃바운드 스팸 필터 정책의 요약 목록을 반환하기 위해 다음 명령을 실행합니다.

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

특정 아웃바운드 스팸 필터 정책에 대한 자세한 정보를 반환하기 위해 다음 구문을 사용하세요.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

이 예에서는 Executives라는 아웃바운드 스팸 필터 정책의 모든 속성 값을 반환합니다.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

구문과 매개 변수에 대한 자세한 내용은 [Get-HostedOutboundSpamFilterPolicy를 참조하십시오.](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 보기

기존 아웃바운드 스팸 필터 규칙을 표시하기 위해 다음 구문을 사용 합니다.

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

모든 아웃바운드 스팸 필터 규칙의 요약 목록을 반환하기 위해 다음 명령을 실행합니다.

```PowerShell
Get-HostedOutboundSpamFilterRule
```

활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

특정 아웃바운드 스팸 필터 규칙에 대한 자세한 정보를 반환하기 위해 다음 구문을 사용하세요.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

이 예에서는 Contoso Executives라는 아웃바운드 스팸 필터 규칙의 모든 속성 값을 반환합니다.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

구문과 매개 변수에 대한 자세한 내용은 [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule)을 참조하십시오.

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 정책 수정

이 문서 앞부분의 [1단계: PowerShell을](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 사용하여 아웃바운드 스팸 필터 정책 만들기 섹션에 설명된 대로 PowerShell에서 맬웨어 필터 정책을 수정할 때와 동일한 설정을 사용할 수 있습니다.

> [!NOTE]
> 아웃바운드 스팸 필터 정책의 이름을 바울 수 **없습니다(Set-HostedOutboundSpamFilterPolicy** cmdlet에 _Name_ 매개 변수가 없음). Microsoft 365 Defender 포털에서 아웃바운드 스팸 정책의 이름을 바출 경우 아웃바운드 스팸 필터 규칙의 이름만 _바입니다._

아웃바운드 스팸 필터 정책을 수정하려면 다음 구문을 사용 합니다.

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-HostedOutboundSpamFilterPolicy를 참조하십시오.](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 수정

PowerShell에서 아웃바운드 스팸 필터 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용되지 않는 규칙을 만들 수 있는 _Enabled_ 매개 변수뿐입니다. 기존 아웃바운드 스팸 필터 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.

그렇지 않으면 PowerShell에서 아웃바운드 스팸 필터 규칙을 수정할 때 추가 설정을 사용할 수 없습니다. 이 문서 앞부분의 [2단계: PowerShell을](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 사용하여 아웃바운드 스팸 필터 규칙 만들기 섹션에 설명된 대로 규칙을 만들 때도 동일한 설정을 사용할 수 있습니다.

아웃바운드 스팸 필터 규칙을 수정하려면 다음 구문을 사용 합니다.

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-HostedOutboundSpamFilterRule을 참조하십시오.](/powershell/module/exchange/set-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 사용 또는 사용 안 하도록 설정

PowerShell에서 아웃바운드 스팸 필터 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하면 전체 아웃바운드 스팸 정책(아웃바운드 스팸 필터 규칙 및 할당된 아웃바운드 스팸 필터 정책)을 활성화하거나 사용하지 않도록 설정할 수 있습니다. 기본 아웃바운드 스팸 정책을 활성화하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용됩니다).

PowerShell에서 아웃바운드 스팸 필터 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

이 예에서는 Marketing Department라는 아웃바운드 스팸 필터 규칙을 사용하지 않도록 설정합니다.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 및 [Disable-HostedOutboundSpamFilterRule을 참조하십시오.](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 규칙의 우선 순위 설정

규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다. 설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다. 예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다. 기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다. 예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.

PowerShell에서 아웃바운드 스팸 필터 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다. 우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**참고:**

- 새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-HostedOutboundSpamFilterRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.
- 아웃바운드 기본 스팸 필터 정책에는 해당하는 스팸 필터 규칙이 없습니다. 항상 가장 낮은 우선 순위 값이 **가장 낮습니다.**

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 정책 제거

PowerShell을 사용하여 아웃바운드 스팸 필터 정책을 제거하면 해당 아웃바운드 스팸 필터 규칙이 제거되지 않습니다.

PowerShell에서 아웃바운드 스팸 필터 정책을 제거하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

이 예에서는 Marketing Department라는 아웃바운드 스팸 필터 정책을 제거합니다.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-HostedOutboundSpamFilterPolicy를 참조하십시오.](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 제거

PowerShell을 사용하여 아웃바운드 스팸 필터 규칙을 제거하면 해당 아웃바운드 스팸 필터 정책이 제거되지 않습니다.

PowerShell에서 아웃바운드 스팸 필터 규칙을 제거하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

이 예에서는 Marketing Department라는 아웃바운드 스팸 필터 규칙을 제거합니다.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-HostedOutboundSpamFilterRule을 참조하십시오.](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)

## <a name="for-more-information"></a>자세한 내용

[제한된 사용자 포털에서 차단된 사용자 제거](removing-user-from-restricted-users-portal-after-spam.md)

[아웃바운드 메시지용 높은 위험 배달 풀](high-risk-delivery-pool-for-outbound-messages.md)

[스팸 방지 및 보호 FAQ](anti-spam-protection-faq.yml)

[자동 전달 메시지 보고서](mfi-auto-forwarded-messages-report.md)
