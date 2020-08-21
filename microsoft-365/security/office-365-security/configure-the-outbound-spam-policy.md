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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 아웃바운드 스팸 정책을 보고, 만들고, 수정하고, 삭제하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 530c1af9b7802be6073f19331ce7f6a20bdb2668
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845981"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>EOP에서 아웃바운드 스팸 필터링 구성

Exchange Online 사서함 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 모든 전자 메일 메시지가 자동으로 스팸 및 비정상적 전송 활동임을 확인합니다.

조직의 사용자가 보내는 아웃바운드 스팸은 일반적으로 어디에 있다는 것을 의미합니다. 의심스러운 아웃바운드 메시지는 스팸 지수 또는 SCL에 관계없이 스팸으로 표시되며 위험도가 높은 배달 [풀을](high-risk-delivery-pool-for-outbound-messages.md) 통해 라우팅되어 서비스의 신뢰도를 보호하기 위해(즉, Microsoft 365 원본 전자 메일 서버를 IP 차단 목록으로부터 보호) 보호합니다. 관리자는 경고 정책을 통해 의심스러운 아웃바운드 전자 메일 활동 과정 및 차단된 사용자에게 자동으로 알림을 [받습니다.](../../compliance/alert-policies.md)

EOP는 스팸에 대한 조직의 전반적인 방어의 일부로 아웃바운드 스팸 정책을 사용합니다. 자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조하세요.

관리자는 기본 아웃바운드 스팸 정책을 보고, 편집하고, 구성할 수 있습니다. 세분성을 상세히 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 아웃바운드 스팸 정책을 만들 수도 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.

보안 & 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 아웃바운드 스팸 정책을 구성할 수 있습니다.

EOP에서 아웃바운드 스팸 정책의 기본 요소는 다음과 같습니다.

- **아웃바운드 스팸 필터 정책:** 아웃바운드 스팸 필터링 결과와 알림 옵션에 대한 작업을 지정합니다.
- **아웃바운드 스팸 필터 규칙: 아웃바운드**스팸 필터 정책에 대한 우선순위 및 받는 사람 필터(정책이 적용되는 사용자)를 지정합니다.

준수 센터에서 아웃바운드 스팸 정책을 관리하면, 두 가지 요소의 차이는 & 명확하지 않습니다.

- 정책을 만들면 실제로는 아웃바운드 스팸 필터 규칙과 관련된 아웃바운드 스팸 필터 정책이 같은 이름을 사용하여 동시에 생성됩니다.
- 정책을 수정할 때, 이름, 우선순위, 사용안함 또는 사용 안 함 및 받는 사람 필터와 관련된 설정은 아웃바운드 스팸 필터 규칙을 수정합니다. 다른 모든 설정은 관련 아웃바운드 스팸 필터 정책을 수정합니다.
- 정책을 제거하면 아웃바운드 스팸 필터 규칙과 연결된 아웃바운드 스팸 필터 정책이 제거됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다. 자세한 내용은 이 항목 [뒷부분에 나오는 Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 아웃바운드 스팸 정책](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 섹션을 구성하세요.

모든 조직에는 다음과 같은 속성을 가진 Default라는 기본 제공 아웃바운드 스팸 정책이 있습니다.

- 정책과 연결된 아웃바운드 스팸 필터 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 정책이 적용됩니다.
- 정책의 사용자 지정 우선순위 값은 **가장 낮음**이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨). 사용자가 만든 모든 사용자 지정 정책은 항상 기본 정책보다 우선합니다.
- 그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.

아웃바운드 스팸 필터링의 효율성을 높이려면 특정 사용자 또는 사용자 그룹에 적용되는 더 강격한 설정을 사용하여 사용자 지정 아웃바운드 스팸 정책을 만들 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 아웃바운드 스팸 정책을 추가, 수정 및 삭제하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 아웃바운드 스팸 정책에 대한 읽기 전용 액세스를 위해는 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

- 아웃바운드 스팸 정책에 대한 권장 설정은 EOP 아웃바운드 [스팸 필터 정책 설정을 참조하세요.](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)

- Email sending limit **exceeded, 의심스러운**전자 메일 전송 패턴이 감지되고, **사용자가 이미** [alert policies](../../compliance/alert-policies.md) **TenantAdmins(전역** **관리자)** 그룹의 구성원에게 전자 메일 알림을 보내고 아웃바운드 스팸으로 인해 차단됨에 대한 전자 메일 알림을 보냅니다. **Suspicious email sending patterns detected** 자세한 내용은 제한된 [사용자에 대한 경고 설정 확인을 참조하십시오.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) 아웃바운드 스팸 정책의 알림 옵션 대신 이러한 경고 정책을 사용하는 것이 좋습니다.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>보안 그룹 & 사용하여 아웃바운드 스팸 정책 만들기

보안 센터에서 사용자 지정 아웃바운드 스팸 정책을 & 준수 센터에서 동일한 이름을 사용하여 스팸 필터 규칙과 관련된 스팸 필터 정책이 동시에 생성됩니다.

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. 스팸 **방지 설정 페이지에서 아웃바운드** 정책 **만들기를 클릭합니다.**

3. 아웃바운드 스팸 **필터 정책이 나타나면** 다음 설정을 구성합니다.

   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다.

   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

4. (옵션) 알림 **섹션을** 확장하여 의심스러운 아웃바운드 전자 메일 메시지의 복사본 및 알림을 받을 추가 사용자를 구성합니다.

   - **특정 사람에게 의심스러운 아웃바운드**전자 메일 메시지 복사본 보내기 : 이 설정은 지정된 사용자를 의심스러운 아웃바운드 메시지에 숨은 참조 받는 사람으로 추가합니다.

     > [!NOTE]
     > 이 설정은 기본 아웃바운드 스팸 정책에서만 작동합니다. 이 기능은 사용자가 만드는 사용자 지정 아웃바운드 스팸 정책에서는 작동하지 않습니다.

     이 설정을 사용하려면

     1. 확인란을 선택하여 설정을 사용하도록 설정합니다.

     1. 사용자 **추가를 클릭합니다.** 표시되는 받는 사람 **추가 또는 제거** 플라이아웃에서 다음을 수행합니다.

     1. 보낸 사람의 전자 메일 주소를 입력합니다. 전자 메일 주소가 여러 개인 경우 각 주소를 세미콜론(목록)으로 구분하여 ;) 또는 한 줄에 받는 사람 한 명

     1. 이 ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 을 선택합니다.

        필요한 만큼 이 단계를 반복합니다.

        추가한 받는 사람은 **플라이아웃의** 받는 사람 목록 섹션에 표시됩니다. 받는 사람을 삭제하려면 제거 ![ 단추를 ](../../media/scc-remove-icon.png) 클릭합니다.

     1. 작업을 마쳤으면 **저장**을 클릭합니다.

        이 설정을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.

   - **아웃바운드 스팸 방지로 인해 차단되는 경우 특정 사용자에게 알림:**

     > [!IMPORTANT]
     >
     > - 이 설정은 아웃바운드 스팸 정책에서 더 이상 사용되지 않기 위한 프로세스에서 수행됩니다.
     >
     > - The default [alert policy](../../compliance/alert-policies.md) **restricted from sending email from sending email from sending email** notifications already sending email notifications to members of the **TenantAdmins** (**Global admins)** group when exceeding the **recipient limits** section. 아웃바운드 스팸 정책의 이 설정 대신 다른 사용자에게 알림을 보내려면 알림 **정책을 사용하는 것이 좋습니다.** 자세한 내용은 제한된 [사용자에 대한 경고 설정을 확인합니다.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)

5. (옵션) 받는 사람 **제한 섹션을** 확장하여 의심스러운 아웃바운드 전자 메일 메시지에 대한 제한 및 작업을 구성합니다.

   > [!NOTE]
   > 이러한 설정은 클라우드 기반 사서함에만 해당합니다.

   - **사용자당 최대 받는 사람 수**

     유효한 값은 0에서 10000까지입니다. 기본값은 0이며, 이는 서비스 기본값이 사용됩니다. 자세한 내용은 보내기 [제한을 참조하십시오.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

     - **외부 시간 한도:** 시간당 외부 받는 사람의 최대 수.

     - **내부 시간 한도:** 시간당 내부 받는 사람의 최대 수.

     - **일별 제한:** 하루 최대 받는 사람 수.

   - **사용자가 위한 제한을 초과하는 경우의 작업:** 받는 사람 제한 중 하나를 초과하는 **경우 수행할** 작업 구성 모든 작업에 대해, 사용자가 전자 메일 알림 정책을 보내지 못하도록 **제한된** **Notify specific people if a sender is blocked due to sending outbound spam** 사용자 및 현재 중복된 사용자에 게 아웃바운드 스팸 설정에서 메일 알림을 받으려면 해당 받는 사람이 특정 인사를 알리도록 합니다.

     - **사용자가 메일을 보내지 않도록 제한하면 다음 날:** 기본값입니다. 전자 메일 알림을 보내고 사용자는 UTC 시간에 따라 다음 날까지 더 많은 메시지를 보낼 수 없습니다. 관리자는 이 블록을 재정의할 수 있는 방법이 없습니다.

       - 전자 메일을 **보내지 않도록 제한된 활동 알림은** 전자 메일을 통해 관리자에게 알림을 보냅니다(전자 메일을 통해, **경고 보기** 페이지에서).

       - 정책에서 아웃바운드 스팸 **설정 설정으로 인해** 보낸 사람이 차단된 경우 알림에 지정된 모든 받는 사람에게도 알림을 받습니다.

       - 사용자는 다음 날에 UTC 시간에 따라 더 이상 메시지를 보낼 수 없습니다. 관리자는 이 블록을 재정의할 수 있는 방법이 없습니다.

     - **메일 보내기 제한:** 전자 메일 알림을 보내거나 보안 & 규정 준수 센터에서 **[제한된 사용자] 포털에 <https://sip.protection.office.com/restrictedusers> ** 사용자가 추가되며, 사용자는 관리자가 제한된 사용자 포털에서 제거될 때까지 전자 **메일을** 보낼 수 없습니다. 관리자가 목록에서 사용자를 제거한 후에는 해당 날짜에 대해 사용자를 다시 제한하지 않습니다. 자세한 내용은 스팸 [메일을 전송한 후 제한된 사용자 포털에서 사용자 제거를 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md)

     - **수행하지 않음, 알림만:** 전자 메일 알림만 보냅니다.

6. (옵션) 자동 **전달 섹션을 확장하여** 사용자의 외부 보낸 사람에 대한 자동 전자 메일 전달을 제어합니다. 자동 전달에 대한 자세한 내용은 전자 메일 전달 [구성을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)

   > [!NOTE]
   >
   > - 2020년 9월 이전에는 이러한 설정을 사용할 수 있지만 적용되지는 않습니다.
   >
   > - 이러한 설정은 클라우드 기반 사서함에만 적용됩니다.
   >
   > - 내부 받는 사람에게 자동으로 전달하는 기능은 이 설정의 영향을 받지 않습니다.

   사용 가능한 값은 다음과 같습니다.

   - **자동 - 시스템 제어: 아웃바운드**스팸 필터링을 허용하여 자동 외부 전자 메일 전달을 제어할 수 있습니다. 이 값은 기본값입니다.

   - **설정**: 정책에 의해 자동 외부 전자 메일 전달이 사용하지 않도록 설정되지 않았습니다.

   - **꺼짐:** 모든 자동 외부 전자 메일 전달이 정책에 의해 사용하지 않도록 설정됩니다.

7. (필수) 적용된 **항목섹션을** 확장하여 정책을 적용할 내부 보낸 사람을 식별합니다.

    조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<sender1\>_ 혹은 _\<sender2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<sender1\>_ 및 _\<member of group 1\>_).

    사용 가능한 모든 조건을 보려면 **조건 추가**를 세 번 클릭하는 것이 가장 쉽습니다. ![제거 단추](../../media/scc-remove-icon.png)를 클릭하여 구성하지 않을 조건을 제거할 수 있습니다.

    - **보낸 사람 도메인은**: 조직에서 구성된 허용 도메인 중 하나 이상의 보낸 사람을 지정합니다. **태그 추가** 상자를 클릭하여 도메인을 확인하고 선택합니다. 두 개 이상의 도메인을 사용할 수 있는 경우, **태그 추가** 상자를 다시 클릭하여 추가 도메인을 선택합니다.

    - **보낸 사람:** 조직에서 하나 이상의 사용자를 지정합니다. **태그 추가**를 클릭하고, 입력을 시작하여 목록을 필터링합니다. 태그 추가 **상자를 다시 클릭하여** 추가 보낸 사람을 선택합니다.

    - **보낸 사람이 보낸 사람이 다음의**구성원임 : 조직에서 그룹을 하나 이상 지정합니다. **태그 추가**를 클릭하고, 입력을 시작하여 목록을 필터링합니다. 태그 추가 **상자를 다시 클릭하여** 추가 보낸 사람을 선택합니다.

    - **다음의 경우 제외**: 규칙에 대한 예외를 추가하려면** 조건 추가**를 세 번 클릭하여 사용 가능한 모든 예외를 표시합니다. 설정 및 동작은 조건과 정확히 같습니다.

8. 작업을 마쳤으면 **저장**을 클릭합니다.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>보안 센터 & 사용하여 아웃바운드 스팸 정책 보기

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. 스팸 방지 **설정 페이지에서 확장 아이콘을** ![ 클릭하여 아웃바운드 스팸 ](../../media/scc-expand-icon.png) 정책을 확장합니다.

   - 아웃바운드 스팸 필터 **정책이라는 기본**정책

   - 유형 열의 값이 사용자 지정 아웃바운드 스팸 정책인 **경우에 만든** 사용자 **지정 정책.**

3. 정책 설정이 표시되는 확장된 정책 세부 정보에 표시될 수 있고 정책 편집을 클릭할 **수 있습니다.**

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>보안 센터 & 사용하여 아웃바운드 스팸 정책 수정

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. 스팸 방지 **설정 페이지에서 확장 아이콘을** ![ 클릭하여 아웃바운드 스팸 ](../../media/scc-expand-icon.png) 정책을 확장합니다.

   - 아웃바운드 스팸 필터 **정책이라는 기본**정책

   - 유형 열의 값이 사용자 지정 아웃바운드 스팸 정책인 **경우에 만든** 사용자 **지정 정책.**

3. **정책 편집**을 클릭합니다.

사용자 지정 아웃바운드 스팸 정책의 경우, 플라이아웃에서 표시되는 사용 가능한 설정은 보안 & 준수 센터를 사용하여 아웃바운드 스팸 정책 섹션을 만드는 [것과 같습니다.](#use-the-security--compliance-center-to-create-outbound-spam-policies)

아웃바운드 스팸 필터 정책이라는 기본 아웃바운드 스팸 **Applied to** **정책의**경우 적용된 섹션을 사용할 수 없고(정책은 모든 사용자에게 적용됨) 정책의 이름을 바일 수 없습니다.

정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.

### <a name="enable-or-disable-outbound-spam-policies"></a>아웃바운드 스팸 정책 사용 또는 사용 안 함

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. 스팸 방지 **설정 페이지에서 확장 아이콘을** 클릭하여 만든 사용자 지정 ![ ](../../media/scc-expand-icon.png) 정책을 확장합니다(유형 **열의 값은** **사용자 지정 아웃바운드 스팸 정책입니다).**

3. 표시되는 확장된 정책 세부 정보에서 **켬** 열에 있는 값을 확인합니다.

   토글을 왼쪽으로 이동하여 정책을 사용하지 않도록 설정합니다. ![토글 끔](../../media/scc-toggle-off.png)

   토글을 오른쪽으로 이동하여 정책을 사용하도록 설정합니다. ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

기본 아웃바운드 스팸 정책은 사용하지 않도록 설정할 수 없습니다.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>사용자 지정 아웃바운드 스팸 정책의 우선순위 설정하기

기본적으로 아웃바운드 스팸 정책에는 만들어진 순서에 따라 우선 순위가 지정됩니다(새 정책은 이전 정책보다 우선순위가 낮음). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

사용자 지정 아웃바운드 스팸 정책은 처리되는 순서로 표시됩니다(첫 번째 정책에는 우선 순위 **값 0이** 포함됨). 아웃바운드 스팸 필터 정책이라는 **기본 아웃바운드 스팸 정책은** 우선 순위 **값이 낮은**것이며 변경할 수 없습니다.

정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. 스팸 **방지 설정 페이지에서 유형** 열의 값이 사용자 지정 아웃바운드 스팸 **정책인** **정책을 찾습니다.** **우선순위** 열의 값을 확인합니다.

   - 우선순위가 가장 높은 사용자 지정 아웃바운드 스팸 정책의 값은 아래쪽 ![ 화살표 아이콘 ](../../media/ITPro-EAC-DownArrowIcon.png) **0입니다.**

   - 우선순위가 가장 낮은 사용자 지정 아웃바운드 스팸 정책의 값 위쪽 화살표 ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **아이콘** 이하(예: ![ 위쪽 화살표 아이콘 ](../../media/ITPro-EAC-UpArrowIcon.png) **3).가 있습니다.**

   - 사용자 지정 아웃바운드 스팸 정책이 세 개 이상 있는 경우 가장 높은 우선순위와 가장 낮은 우선순위 사이의 정책은 위쪽 ![ 화살표 아이콘 ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **n** 값(예: 위쪽 화살표 ![ 아이콘 ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2)을 가합니다.**

3. 이 ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) 또는 ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) 을 클릭하여 우선 순위 목록에서 사용자 지정 아웃바운드 스팸 정책을 위나 아래로 이동합니다.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>보안 센터 & 사용하여 아웃바운드 스팸 정책 제거하기

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. 스팸 **방지 설정 페이지에서 확장 아이콘을** 클릭하여 삭제할 사용자 지정 ![ ](../../media/scc-expand-icon.png) 정책을 확장합니다(유형 **열은** **사용자 지정 아웃바운드 스팸 정책입니다).**

3. 표시되는 확장된 정책 세부 정보에서 **정책 삭제**를 클릭합니다.

4. 표시되는 경고 대화 상자에서 **예**를 클릭합니다.

기본 정책은 제거할 수 없습니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 아웃바운드 스팸 정책 구성

앞에서 설명한 바와 같이 아웃바운드 스팸 정책은 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙으로 구성됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서는 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙 사이의 차이가 명시되어 있습니다. ** \* -HostedOutboundSpamFilterPolicy** cmdlet을 사용하여 아웃바운드 스팸 필터 정책을 관리하고, ** \* -HostedOutboundSpamFilterRule** cmdlet을 사용하여 아웃바운드 스팸 필터 규칙을 관리합니다.

- PowerShell에서는 먼저 아웃바운드 스팸 필터 정책을 한 후 규칙이 적용되는 정책을 식별하는 아웃바운드 스팸 필터 규칙을 만듭니다.
- PowerShell에서는 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙의 설정을 별도로 수정합니다.
- PowerShell에서 아웃바운드 스팸 필터 정책을 제거하면 이에 해당하는 아웃바운드 스팸 필터 규칙은 자동으로 제거되지 않습니다. 또한 이에 국한될 수도 있습니다.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell을 사용하여 아웃바운드 스팸 정책 만들기

PowerShell에서 아웃바운드 스팸 정책을 만드는 2단계 프로세스는 다음과 같습니다.

1. 아웃바운드 스팸 필터 정책을 만듭니다.
2. 규칙이 적용되는 아웃바운드 스팸 필터 정책을 지정하는 아웃바운드 스팸 필터 규칙을 만듭니다.

 **참고:**

- 새 아웃바운드 스팸 필터 규칙을 만들고 연결되지 않은 기존 아웃바운드 스팸 필터 정책을 할당할 수 있습니다. 아웃바운드 스팸 필터 규칙은 둘 이상의 아웃바운드 스팸 필터 정책과 연관될 수 없습니다.

- 정책을 만들 때까지 보안 그룹 준수 센터에서 사용할 수 없는 PowerShell의 새 아웃바운드 & 필터 정책에 대해 다음 설정을 구성할 수 있습니다.

  - 새 정책을 만듭니다(New-HostedOutboundSpamFilterRule_Enabled_ `$false` **cmdlet에서 사용함).**
  - _Priority_ _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet에서 생성하는 동안 정책우선순위(우선 순위)를 설정합니다.

- 스팸 필터 규칙에 정책을 할당할 때까지 PowerShell에서 만든 새로운 아웃바운드 & 스팸 보안 센터에 표시되지 않습니다.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>1단계: PowerShell을 사용하여 아웃바운드 스팸 필터 정책 만들기

아웃바운드 스팸 필터 정책을 만들려면 다음 구문을 사용하세요.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 새 아웃바운드 스팸 필터 정책을 만드는 예제입니다.

- 받는 사람 비율 제한은 기본값인 값으로 제한됩니다. 자세한 내용은 [Microsoft 365 옵션별 보내기 제한을 참조하십시오.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

- 한도에 도달하면 메시지를 보낼 수 없습니다.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

구문과 매개 변수에 대한 자세한 내용은 [New-HostedOutboundSpamFilterPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>2단계: PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 만들기

아웃바운드 스팸 필터 규칙을 만들려면 다음 구문을 사용하세요.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 새 아웃바운드 스팸 필터 규칙을 만드는 예제입니다.

- Contoso Executives라는 아웃바운드 스팸 필터 정책은 규칙과 연결됩니다.

- 이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

구문과 매개 변수에 대한 자세한 내용은 [New-HostedOutboundSpamFilterRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 정책 보기

모든 아웃바운드 스팸 필터 정책의 요약 목록을 반환하려면 이 명령을 실행합니다.

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

특정 아웃바운드 스팸 필터 정책에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

다음은 Executives라는 아웃바운드 스팸 필터 정책의 모든 속성 값을 반환하는 예제입니다.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

구문과 매개 변수에 대한 자세한 내용은 [Get-HostedOutboundSpamFilterPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 보기

기존 아웃바운드 스팸 필터 규칙을 확인하려면 다음 구문을 사용하세요.

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

모든 아웃바운드 스팸 필터 규칙의 요약 목록을 반환하려면 이 명령을 실행합니다.

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

특정 아웃바운드 스팸 필터 규칙에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

다음은 Contoso Executives라는 아웃바운드 스팸 필터 규칙의 모든 속성 값을 반환하는 예제입니다.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

구문과 매개 변수에 대한 자세한 내용은 [Get-HostedOutboundSpamFilterRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 정책 수정하기

PowerShell에서 맬웨어 필터 정책을 수정할 때 이 항목의 [앞부분에 나오는 1단계: PowerShell을](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 사용하여 아웃바운드 스팸 필터 정책 섹션을 만들 때와 동일한 설정을 사용할 수 있습니다.

> [!NOTE]
> 아웃바운드 스팸 필터 정책의 이름을 바일 **수없습니다(Set-HostedOutboundSpamFilterPolicy cmdlet에는** Name 매개 _변수가_ 없음). 보안 그룹 준수 센터에서 아웃바운드 스팸 & 이름을 바운드하면 아웃바운드 스팸 필터 규칙의 이름만 _변경됩니다._

아웃바운드 스팸 필터 정책을 수정하려면 다음 구문을 사용하세요.

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

자세한 구문 및 매개 변수 정보는 [Set-HostedOutboundSpamFilterPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 수정하기

PowerShell에서 아웃바운드 스팸 필터 규칙을 수정할 때 사용할 수 없는 설정은 사용 안 함 _규칙을 만들_ 수 있는 사용 안 함 매개 변수입니다. 기존 아웃바운드 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.

그렇지 않으면 PowerShell에서 아웃바운드 스팸 필터 규칙을 수정할 때 추가 설정을 사용할 수 없습니다. [2단계: PowerShell을](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 사용하여 이 항목의 앞부분에 있는 아웃바운드 스팸 필터 규칙 섹션에 설명된 것과 같이 규칙을 만들 때도 동일한 설정을 사용할 수 있습니다.

아웃바운드 스팸 필터 규칙을 수정하려면 다음 구문을 사용하세요.

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-HostedOutboundSpamFilterRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 사용 또는 사용 안 함

PowerShell에서 아웃바운드 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하면 전체 아웃바운드 스팸 정책(아웃바운드 스팸 필터 규칙과 할당된 아웃바운드 스팸 필터 정책)을 사용하거나 사용하지 않도록 설정합니다. 기본 아웃바운드 스팸 정책을 사용하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용됨).

PowerShell에서 아웃바운드 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

다음은 Marketing Department라는 아웃바운드 스팸 필터 규칙을 사용하지 않도록 설정하는 예제입니다.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

자세한 구문 및 매개 변수 정보는 [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 및 [Disable-HostedOutboundSpamFilterRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 규칙의 우선 순위 설정하기

규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다. 설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다. 예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다. 기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다. 예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.

PowerShell에서 아웃바운드 스팸 필터 규칙의 우선순위를 설정하려면 다음 구문을 사용하세요.

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다. 우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - 새 규칙을 만들 때 새 규칙의 우선 순위를 설정하려면 **New-HostedOutboundSpamFilterRule** cmdlet의 _우선_ 순위 매개 변수를 대신 사용하세요.
>
> - 아웃바운드 기본 스팸 필터 정책에는 상용되는 스팸 필터 규칙이 없고 항상 수정할 수 없는 우선순위 값이 **가장 낮습니다.**

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 정책 제거하기

PowerShell을 사용하여 아웃바운드 스팸 필터 정책을 제거할 때 이용하는 아웃바운드 스팸 필터 규칙은 제거되지 않습니다.

PowerShell에서 아웃바운드 스팸 필터 정책을 제거하려면 다음 구문을 사용하세요.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

다음은 Marketing Department라는 아웃바운드 스팸 필터 정책을 제거하는 예제입니다.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-HostedOutboundSpamFilterPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 제거하기

PowerShell을 사용하여 아웃바운드 스팸 필터 규칙을 제거할 때 이에 해당하는 아웃바운드 스팸 필터 정책은 제거되지 않습니다.

PowerShell에서 아웃바운드 스팸 필터 규칙을 제거하려면 다음 구문을 사용하세요.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

다음은 Marketing Department라는 아웃바운드 스팸 필터 규칙을 제거하는 예제입니다.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-HostedOutboundSpamFilterRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)

## <a name="for-more-information"></a>자세한 내용

[제한된 사용자 포털에서 차단된 사용자 제거](removing-user-from-restricted-users-portal-after-spam.md)

[아웃바운드 메시지용 높은 위험 배달 풀](high-risk-delivery-pool-for-outbound-messages.md)

[스팸 방지 및 보호 FAQ](anti-spam-protection-faq.md)

[자동 전달 메시지 보고서](mfi-auto-forwarded-messages-report.md)
