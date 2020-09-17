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
description: 관리자는 EOP (Exchange Online Protection)에서 아웃 바운드 스팸 정책을 보고, 만들고, 수정 하 고, 삭제 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: ebeebe3486ad4dad926ad72509154904700e320a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949351"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>EOP에서 아웃 바운드 스팸 필터링 구성

Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (독립 실행형 Exchange Online Protection) 조직에서 EOP를 통해 전송 되는 아웃 바운드 전자 메일 메시지는 스팸 및 비정상적인 보내기 활동을 자동으로 확인 합니다.

조직에 있는 사용자의 아웃 바운드 스팸은 일반적으로 계정이 노출 된 것을 나타냅니다. 의심 스러운 아웃 바운드 메시지는 스팸 지 수 또는 SCL에 관계 없이 스팸으로 표시 되며, [높은 위험 배달 풀](high-risk-delivery-pool-for-outbound-messages.md) 을 통해 라우팅되는 서비스의 신뢰도를 보호 하는 데 도움이 됩니다 (즉, Microsoft 365 원본 전자 메일 서버를 IP 차단 목록 밖으로 유지). 관리자는 [경고 정책을](../../compliance/alert-policies.md)통해 의심 스러운 아웃 바운드 전자 메일 활동 및 차단 된 사용자에 게 자동으로 알림을 보냅니다.

EOP에서는 스팸을 방지 하기 위해 조직의 전반적인 방어 과정에서 아웃 바운드 스팸 정책을 사용 합니다. 자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조하세요.

관리자는 기본 아웃 바운드 스팸 정책을 보고 편집 하 고 구성할 수 있습니다 (삭제 하지 않음). 세분성을 높이기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용 되는 사용자 지정 아웃 바운드 스팸 정책을 만들 수도 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.

보안 & 준수 센터 또는 PowerShell (exchange online 사서함이 없는 조직에 대 한 사서함이 있는 Microsoft 365 조 직 용 Exchange online PowerShell)에서 아웃 바운드 스팸 정책을 구성할 수 있습니다.

EOP의 아웃 바운드 스팸 정책의 기본 요소는 다음과 같습니다.

- **아웃 바운드 스팸 필터 정책**: 아웃 바운드 스팸 필터링 verdicts 및 알림 옵션에 대 한 작업을 지정 합니다.
- **아웃 바운드 스팸 필터 규칙**: 아웃 바운드 스팸 필터 정책에 대해 정책이 적용 되는 우선 순위 및 받는 사람 필터를 지정 합니다.

보안 & 준수 센터에서 아웃 바운드 스팸 정책을 관리할 때는 이러한 두 가지 요소 간의 차이가 명확 하지 않습니다.

- 정책을 만들 때 실제로는 두 사용자에 대해 같은 이름을 사용 하 여 아웃 바운드 스팸 필터 규칙과 연결 된 모든 아웃 바운드 스팸 필터 정책을 동시에 만드는 것입니다.
- 정책을 수정 하면 이름, 우선 순위, 사용 또는 사용 안 함 및 받는 사람 필터와 관련 된 설정이 아웃 바운드 스팸 필터 규칙을 수정 합니다. 다른 모든 설정은 연결 된 아웃 바운드 스팸 필터 정책을 수정 합니다.
- 정책을 제거 하면 아웃 바운드 스팸 필터 규칙과 연결 된 아웃 바운드 스팸 필터 정책이 제거 됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다. 자세한 내용은이 항목 뒷부분에 나오는 [Exchange Online PowerShell 또는 독립 실행형 EOP powershell을 사용 하 여 아웃 바운드 스팸 정책 구성](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 섹션을 참조 하십시오.

모든 조직에는 다음과 같은 속성을 갖는 기본 제공 아웃 바운드 스팸 정책 (기본값)이 있습니다.

- 정책과 연결 된 아웃 바운드 스팸 필터 규칙 (받는 사람 필터)이 없는 경우에도이 정책은 조직의 모든 받는 사람에 게 적용 됩니다.
- 정책의 사용자 지정 우선순위 값은 **가장 낮음**이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨). 사용자가 만든 모든 사용자 지정 정책은 항상 기본 정책보다 우선합니다.
- 그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.

아웃 바운드 스팸 필터링의 효율성을 높이려면 특정 사용자 또는 사용자 그룹에 적용 되는 보다 엄격한 설정을 사용 하 여 사용자 지정 아웃 바운드 스팸 정책을 만들 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 아웃 바운드 스팸 정책을 추가, 수정 및 삭제 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 아웃 바운드 스팸 정책에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

- 아웃 바운드 스팸 정책에 대 한 권장 설정에 대 한 자세한 내용은 [EOP outbound 스팸 필터 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)참조 하십시오.

- **전자 메일 전송 제한 초과**, **의심 스러운 전자 메일 전송 패턴 감지**및 아웃 바운드 스팸으로 인해 차단 된 사용자에 대 한 전자 메일 알림 (**글로벌 관리자**) 그룹의 구성원에 게 전자 메일을 보낼 **수 없도록 하** **는 기본** [알림 정책이](../../compliance/alert-policies.md) 있습니다. 자세한 내용은 [제한 된 사용자에 대 한 알림 설정 확인](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)을 참조 하십시오. 아웃 바운드 스팸 정책에서 알림 옵션 대신 이러한 경고 정책을 사용 하는 것이 좋습니다.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>보안 & 준수 센터를 사용 하 여 아웃 바운드 스팸 정책 만들기

보안 & 준수 센터에서 사용자 지정 아웃 바운드 스팸 정책을 만들면 두 가지 모두에 대해 동일한 이름을 사용 하 여 스팸 필터 규칙과 연결 된 스팸 필터 정책이 동시에 만들어집니다.

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. **스팸 방지 설정** 페이지에서 **아웃 바운드 정책 만들기**를 클릭 합니다.

3. **아웃 바운드 스팸 필터 정책** 날아가기가 열리면 다음 설정을 구성 합니다.

   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다.

   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

4. 반드시 **알림** 섹션을 확장 하 여 의심 스러운 아웃 바운드 전자 메일 메시지에 대 한 복사본 및 알림을 수신 해야 하는 추가 사용자를 구성 합니다.

   - **의심 스러운 아웃 바운드 전자 메일 메시지의 복사본을 특정 사용자에 게 보내기**:이 설정은 지정한 사용자를 숨은 참조로 받는 사람에 게 의심 되는 아웃 바운드 메시지에 추가 합니다.

     > [!NOTE]
     > 이 설정은 기본 아웃 바운드 스팸 정책 에서만 작동 합니다. 사용자가 만든 아웃 바운드 스팸 정책에서는 작동 하지 않습니다.

     이 설정을 사용 하도록 설정 하려면:

     1. 확인란을 선택 하 여 설정을 사용 하도록 설정 합니다.

     1. **사용자 추가**를 클릭 합니다. 표시 되는 **받는 사람 추가 또는 제거** 플라이 아웃에서 다음을 수행 합니다.

     1. 보낸 사람의 전자 메일 주소를 입력합니다. 세미콜론으로 구분 하 여 여러 전자 메일 주소를 지정할 수 있습니다 (;) 한 줄에 한 명 또는 여러 명의 받는 사람이 있습니다.

     1. 이 ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 받는 사람을 추가 합니다.

        필요한 만큼 이 단계를 반복합니다.

        추가한 받는 사람이 플라이 아웃의 **받는 사람 목록** 섹션에 표시 됩니다. 받는 사람을 삭제 하려면 ![ 제거 단추를 클릭 ](../../media/scc-remove-icon.png) 합니다.

     1. 작업을 마쳤으면 **저장**을 클릭합니다.

        이 설정을 사용 하지 않도록 설정 하려면 확인란의 선택을 취소 합니다.

   - **아웃 바운드 스팸 전송로 인해 보낸 사람이 차단 된 경우 특정 사용자에 게 알림**:

     > [!IMPORTANT]
     >
     > - 이 설정은 아웃 바운드 스팸 정책에서 더 이상 사용 되지 않는 프로세스에 있습니다.
     >
     > - **받는 사람 제한** 섹션의 제한을 초과 하 여 사용자가 **차단 된 경우** **전자 메일을 보내는** 것이 제한**Global admins**된 사용자에 게 이미 전자 메일 알림이 전송 됩니다. 라는 기본 [경고 정책](../../compliance/alert-policies.md) **아웃 바운드 스팸 정책에서이 설정이 관리자 및 기타 사용자에 게 알리도록 설정 하는 것이 아니라 경고 정책을 사용 하는 것이 좋습니다**. 자세한 내용은 [제한 된 사용자에 대 한 알림 설정 확인](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)을 참조 하십시오.

5. 반드시 **받는 사람 제한** 섹션을 확장 하 여 의심 스러운 아웃 바운드 전자 메일 메시지에 대 한 제한 및 작업을 구성 합니다.

   > [!NOTE]
   > 이러한 설정은 클라우드 기반 사서함에만 적용 됩니다.

   - **사용자 당 최대 받는 사람 수**

     유효한 값은 0 ~ 1만입니다. 기본값은 0 이며이 값은 서비스 기본값을 사용 함을 의미 합니다. 자세한 내용은 [제한 보내기를](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)참조 하십시오.

     - **외부 시간 제한**: 시간당 최대 외부 받는 사람 수입니다.

     - **내부 시간 제한**: 시간당 내부 받는 사람의 최대 수입니다.

     - **일별 제한**: 일별 최대 받는 사람 수입니다.

   - **사용자가 위의 제한을 초과**하는 경우: **받는 사람 한도** 를 초과 하는 경우 수행할 작업을 구성 합니다. 모든 작업의 경우 사용자에 게 **전자 메일 알림 정책 전송 제한** , 즉 아웃 바운드 스팸 정책 수신 전자 메일 알림을 보내는 **아웃 바운드 스팸 설정으로 인해 보낸 사람이 차단 되는 경우** 에는 중복 알림에 특정 사용자에 게 지정 됩니다.

     - **다음 날까지 사용자가 메일을 보낼 수 없도록 제한**합니다:이 값은 기본값입니다. 전자 메일 알림이 전송 되 고 사용자가 UTC 시간을 기준으로 다음 날까지 메시지를 더 이상 보낼 수 없게 됩니다. 관리자가이 블록을 무시할 수 있는 방법은 없습니다.

       - **사용자가 전자 메일을 보낼 수 없도록 제한** 된 작업 경고는 전자 메일을 통해 관리자에 게 알림 페이지를 **표시** 합니다.

       - 정책에서 **아웃 바운드 스팸 설정을 전송 하 여 보낸 사람이 차단 되는 경우 특정 사용자에 게 알림** 메시지가 지정 된 모든 받는 사람은 알림을 받습니다.

       - 사용자는 UTC 시간을 기준으로 다음 날까지 메시지를 더 이상 보낼 수 없게 됩니다. 관리자가이 블록을 무시할 수 있는 방법은 없습니다.

     - **사용자가 메일을 보낼 수 없도록 제한**: 전자 메일 알림이 전송 되 고 사용자가 보안 & 준수 센터의 **[제한 된 사용자] <https://sip.protection.office.com/restrictedusers> ** 포털에 추가 되 고 관리자가 제한 된 **사용자** 포털에서 제거 될 때까지 사용자가 전자 메일을 보낼 수 없습니다. 관리자가 목록에서 사용자를 제거 하면 해당 날짜에 대해 사용자가 다시 제한 되지 않습니다. 자세한 내용은 [스팸 메일을 보낸 후 제한 된 사용자 포털에서 사용자 제거](removing-user-from-restricted-users-portal-after-spam.md)를 참조 하세요.

     - **작업 없음, 알림만**: 전자 메일 알림을 보냅니다.

6. 반드시 **자동 전달** 섹션을 확장 하 여 사용자가 외부 보낸 사람에 대 한 자동 전자 메일 전달을 제어 합니다. 자동 전달에 대 한 자세한 내용은 [전자 메일 전달 구성을](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)참조 하십시오.

   > [!NOTE]
   >
   > - 9 월 2020 이전에는 이러한 설정을 사용할 수 있지만 적용 되지는 않습니다.
   >
   > - 이러한 설정은 클라우드 기반 사서함에만 적용 됩니다.
   >
   > - 내부 받는 사람에 대 한 자동 전달은 이러한 설정의 영향을 받지 않습니다.

   사용 가능한 값은 다음과 같습니다.

   - **자동 시스템 제어**: 아웃 바운드 스팸 필터링을 사용 하 여 자동 외부 전자 메일 전달을 제어할 수 있습니다. 이 값은 기본값입니다.

   - **켜기**: 정책에 따라 자동 외부 전자 메일 전달이 사용 하지 않도록 설정 되지 않습니다.

   - **해제**: 정책에 의해 모든 자동 외부 전자 메일 전달이 사용 하지 않도록 설정 됩니다.

7. 않아도 **적용 대상** 섹션을 확장 하 여 정책이 적용 되는 내부 보낸 사람을 식별 합니다.

    조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<sender1\>_ 혹은 _\<sender2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<sender1\>_ 및 _\<member of group 1\>_).

    사용 가능한 모든 조건을 보려면 **조건 추가**를 세 번 클릭하는 것이 가장 쉽습니다. ![제거 단추](../../media/scc-remove-icon.png)를 클릭하여 구성하지 않을 조건을 제거할 수 있습니다.

    - **보낸 사람 도메인**: 조직에서 구성 된 허용 도메인 중 하나 이상에 있는 보낸 사람을 지정 합니다. **태그 추가** 상자를 클릭하여 도메인을 확인하고 선택합니다. 두 개 이상의 도메인을 사용할 수 있는 경우, **태그 추가** 상자를 다시 클릭하여 추가 도메인을 선택합니다.

    - **Sender is**: 조직에서 사용자를 한 명 이상 지정 합니다. **태그 추가**를 클릭하고, 입력을 시작하여 목록을 필터링합니다. **태그 추가** 상자를 다시 클릭 하 여 추가 보낸 사람을 선택 합니다.

    - **보낸 사람이 다음 구성원 인 경우**: 조직의 그룹을 하나 이상 지정 합니다. **태그 추가**를 클릭하고, 입력을 시작하여 목록을 필터링합니다. **태그 추가** 상자를 다시 클릭 하 여 추가 보낸 사람을 선택 합니다.

    - **다음의 경우 제외**: 규칙에 대한 예외를 추가하려면** 조건 추가**를 세 번 클릭하여 사용 가능한 모든 예외를 표시합니다. 설정 및 동작은 조건과 정확히 같습니다.

8. 작업을 마쳤으면 **저장**을 클릭합니다.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>보안 & 준수 센터를 사용 하 여 아웃 바운드 스팸 정책 보기

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. **스팸 방지 설정** 페이지에서 ![ 확장 아이콘을 클릭 하 여 ](../../media/scc-expand-icon.png) 아웃 바운드 스팸 정책을 확장 합니다.

   - **아웃 바운드 스팸 필터 정책**이라는 기본 정책

   - **Type** 열의 값이 **사용자 지정 아웃 바운드 스팸 정책**인 경우 만든 사용자 지정 정책입니다.

3. 표시 되는 확장 된 정책 세부 정보에 정책 설정이 표시 되거나, **정책 편집**을 클릭할 수 있습니다.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>보안 & 준수 센터를 사용 하 여 아웃 바운드 스팸 정책 수정

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. **스팸 방지 설정** 페이지에서 ![ 확장 아이콘을 클릭 하 여 ](../../media/scc-expand-icon.png) 아웃 바운드 스팸 정책을 확장 합니다.

   - **아웃 바운드 스팸 필터 정책**이라는 기본 정책

   - **Type** 열의 값이 **사용자 지정 아웃 바운드 스팸 정책**인 경우 만든 사용자 지정 정책입니다.

3. **정책 편집**을 클릭합니다.

사용자 지정 아웃 바운드 스팸 정책에서 표시 되는 플라이 아웃의 사용 가능 설정은 [보안 & 준수 센터를 사용 하 여 아웃 바운드 스팸 정책 만들기](#use-the-security--compliance-center-to-create-outbound-spam-policies) 섹션에 설명 된 설정과 동일 합니다.

**아웃 바운드 스팸 필터 정책**이라는 기본 아웃 바운드 스팸 정책의 경우 **적용 대상** 섹션을 사용할 수 없으며 정책이 모든 사용자에 게 적용 되며 정책의 이름을 바꿀 수 없습니다.

정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.

### <a name="enable-or-disable-outbound-spam-policies"></a>아웃 바운드 스팸 정책 사용 또는 사용 안 함

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. **스팸 방지 설정** 페이지에서 확장 아이콘을 클릭 ![ 하 여 ](../../media/scc-expand-icon.png) 만든 사용자 지정 정책 ( **유형** 열의 값은 **사용자 지정 아웃 바운드 스팸 정책**)을 확장 합니다.

3. 표시되는 확장된 정책 세부 정보에서 **켬** 열에 있는 값을 확인합니다.

   토글을 왼쪽으로 이동하여 정책을 사용하지 않도록 설정합니다. ![토글 끔](../../media/scc-toggle-off.png)

   토글을 오른쪽으로 이동하여 정책을 사용하도록 설정합니다. ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

기본 아웃 바운드 스팸 정책을 사용 하지 않도록 설정할 수 없습니다.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>사용자 지정 아웃 바운드 스팸 정책의 우선 순위 설정

기본적으로 아웃 바운드 스팸 정책에는 만든 순서를 기준으로 하는 우선 순위가 지정 됩니다 (최신 정책은 이전 정책 보다 낮은 우선 순위). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

사용자 지정 아웃 바운드 스팸 정책은 처리 되는 순서 대로 표시 됩니다 (첫 번째 정책의 **우선 순위** 값은 0). **아웃 바운드 스팸 필터 정책** 이라는 기본 아웃 바운드 스팸 정책에서는 우선 순위 값이 **가장 낮은**것 이며,이를 변경할 수는 없습니다.

정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. **스팸 방지 설정** 페이지에서 **유형** 열의 값이 **사용자 지정 아웃 바운드 스팸 정책**인 정책을 찾습니다. **우선순위** 열의 값을 확인합니다.

   - 우선 순위가 가장 높은 사용자 지정 아웃 바운드 스팸 정책의 값은 ![ 아래쪽 화살표 아이콘 ](../../media/ITPro-EAC-DownArrowIcon.png) **0**입니다.

   - 우선 순위가 가장 낮은 사용자 지정 아웃 바운드 스팸 정책의 값 ![ 위쪽 화살표 아이콘 ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (예: ![ 위쪽 화살표 아이콘 ](../../media/ITPro-EAC-UpArrowIcon.png) **3**)이 사용 됩니다.

   - 사용자 지정 된 아웃 바운드 스팸 정책이 3 개 이상인 경우 위쪽/최저 우선 순위 간의 정책에는 위쪽 화살표 아이콘 ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ 아래쪽 화살표 아이콘 ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (예를 들어, ![ 위 화살표가 아이콘 ](../../media/ITPro-EAC-UpArrowIcon.png)![ 아래쪽 화살표 아이콘 ](../../media/ITPro-EAC-DownArrowIcon.png) **2**)로 설정 됩니다.

3. 이 ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) 또는 ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) 사용자 지정 아웃 바운드 스팸 정책을 우선 순위 목록에서 위아래로 이동 합니다.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>보안 & 준수 센터를 사용 하 여 아웃 바운드 스팸 정책 제거

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. **스팸 방지 설정** 페이지에서 ![ 확장 아이콘을 클릭 하 여 ](../../media/scc-expand-icon.png) 삭제할 사용자 지정 정책 ( **유형** 열은 **사용자 지정 아웃 바운드 스팸 정책**)을 확장 합니다.

3. 표시되는 확장된 정책 세부 정보에서 **정책 삭제**를 클릭합니다.

4. 표시되는 경고 대화 상자에서 **예**를 클릭합니다.

기본 정책은 제거할 수 없습니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용 하 여 아웃 바운드 스팸 정책 구성

앞에서 설명한 것 처럼 아웃 바운드 스팸 정책은 아웃 바운드 스팸 필터 정책 및 아웃 바운드 스팸 필터 규칙으로 구성 됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서는 아웃 바운드 스팸 필터 정책 및 아웃 바운드 스팸 필터 규칙 간의 차이가 명백 합니다. ** \* -Get-hostedoutboundspamfilterpolicy** cmdlet을 사용 하 여 아웃 바운드 스팸 필터 정책을 관리 하 고 ** \* -HostedOutboundSpamFilterRule** cmdlet을 사용 하 여 아웃 바운드 스팸 필터 규칙을 관리 합니다.

- PowerShell에서 먼저 아웃 바운드 스팸 필터 정책을 만든 다음 규칙이 적용 되는 정책을 식별 하는 아웃 바운드 스팸 필터 규칙을 만듭니다.
- PowerShell에서는 아웃 바운드 스팸 필터 정책 및 아웃 바운드 스팸 필터 규칙의 설정을 개별적으로 수정 합니다.
- PowerShell에서 아웃 바운드 스팸 필터 정책을 제거 하면 해당 하는 아웃 바운드 스팸 필터 규칙이 자동으로 제거 되지 않으며 그 반대의 경우도 마찬가지입니다.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell을 사용 하 여 아웃 바운드 스팸 정책 만들기

PowerShell에서 아웃 바운드 스팸 정책을 만드는 과정은 다음 두 단계로 진행 됩니다.

1. 아웃 바운드 스팸 필터 정책을 만듭니다.
2. 규칙이 적용 되는 아웃 바운드 스팸 필터 정책을 지정 하는 아웃 바운드 스팸 필터 규칙을 만듭니다.

 **참고**:

- 새 아웃 바운드 스팸 필터 규칙을 만들고 연결 되지 않은 기존 아웃 바운드 스팸 필터 정책을 할당할 수 있습니다. 아웃 바운드 스팸 필터 규칙을 두 개 이상의 아웃 바운드 스팸 필터 정책에 연결할 수 없습니다.

- 정책을 만든 후에 야 보안 & 준수 센터에서 사용할 수 없는 PowerShell에서 새 아웃 바운드 스팸 필터 정책에 대해 다음 설정을 구성할 수 있습니다.

  - HostedOutboundSpamFilterRule cmdlet에서_사용 하도록 설정_ 된 새 정책을 사용 하지 않도록 설정 `$false` **New-HostedOutboundSpamFilterRule** 합니다.
  - HostedOutboundSpamFilterRule cmdlet에 대 한 생성 (_우선 순위_ ) 중에 정책의 우선 순위를 설정 _\<Number\>_ 합니다. **New-HostedOutboundSpamFilterRule**

- 사용자가 PowerShell에서 만든 새 아웃 바운드 스팸 필터 정책이 보안 & 준수 센터에 표시 되지 않는 경우에는 해당 정책을 스팸 필터 규칙에 할당할 수 있습니다.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>1 단계: PowerShell을 사용 하 여 아웃 바운드 스팸 필터 정책 만들기

아웃 바운드 스팸 필터 정책을 만들려면 다음 구문을 사용 합니다.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

이 예에서는 다음 설정을 사용 하 여 Contoso 임원 이라는 새 아웃 바운드 스팸 필터 정책을 만듭니다.

- 받는 사람 비율 제한은 기본값 보다 작은 값으로 제한 됩니다. 자세한 내용은 [Microsoft 365 옵션을 통한 제한 보내기](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)를 참조 하세요.

- 한도에 도달한 후에는 사용자가 메시지를 보낼 수 없습니다.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

구문과 매개 변수에 대 한 자세한 내용은 [get-hostedoutboundspamfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)를 참조 하십시오.

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>2 단계: PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙 만들기

아웃 바운드 스팸 필터 규칙을 만들려면 다음 구문을 사용 합니다.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

이 예에서는 다음 설정을 사용 하 여 Contoso 임원 이라는 새 아웃 바운드 스팸 필터 규칙을 만듭니다.

- Contoso 임원 이라는 아웃 바운드 스팸 필터 정책이 규칙과 연결 됩니다.

- 이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

구문과 매개 변수에 대 한 자세한 내용은 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)를 참조 하십시오.

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell을 사용 하 여 아웃 바운드 스팸 필터 정책 보기

모든 아웃 바운드 스팸 필터 정책의 요약 목록을 반환 하려면 다음 명령을 실행 합니다.

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

특정 아웃 바운드 스팸 필터 정책에 대 한 자세한 정보를 반환 하려면 다음 구문을 사용 합니다.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

이 예에서는 임원 라는 아웃 바운드 스팸 필터 정책에 대 한 모든 속성 값을 반환 합니다.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

구문과 매개 변수에 대 한 자세한 내용은 [get-hostedoutboundspamfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)를 참조 하십시오.

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙 보기

기존 아웃 바운드 스팸 필터 규칙을 보려면 다음 구문을 사용 합니다.

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

모든 아웃 바운드 스팸 필터 규칙의 요약 목록을 반환 하려면 다음 명령을 실행 합니다.

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

특정 아웃 바운드 스팸 필터 규칙에 대 한 자세한 정보를 반환 하려면 다음 구문을 사용 합니다.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

이 예에서는 Contoso 임원 이라는 아웃 바운드 스팸 필터 규칙에 대 한 모든 속성 값을 반환 합니다.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

구문과 매개 변수에 대 한 자세한 내용은 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)를 참조 하십시오.

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell을 사용 하 여 아웃 바운드 스팸 필터 정책 수정

이 항목 앞부분의 [1 단계: powershell을 사용 하 여 아웃 바운드 스팸 필터 정책 만들기](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 섹션에 설명 된 대로, powershell에서 맬웨어 필터 정책을 수정 하는 경우에도 동일한 설정을 사용할 수 있습니다.

> [!NOTE]
> 아웃 바운드 스팸 필터 정책의 이름을 바꿀 수는 없습니다 (Get-hostedoutboundspamfilterpolicy cmdlet은 _Name_ 매개 변수를 **사용** 하지 않음). 보안 & 준수 센터에서 아웃 바운드 스팸 정책의 이름을 바꿀 때 아웃 바운드 스팸 필터 _규칙만_이름을 변경 하는 것입니다.

아웃 바운드 스팸 필터 정책을 수정 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

구문 및 매개 변수에 대 한 자세한 내용은 [get-hostedoutboundspamfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)를 참조 하십시오.

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙 수정

PowerShell에서 아웃 바운드 스팸 필터 규칙을 수정할 때 사용할 수 없는 설정은 사용 하지 않도록 설정 된 규칙을 만들 수 있는 _사용_ 가능한 매개 변수입니다. 기존 아웃 바운드 스팸 필터 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 섹션을 참조 하십시오.

그렇지 않으면 PowerShell에서 아웃 바운드 스팸 필터 규칙을 수정할 때 사용할 수 있는 추가 설정이 없습니다. 이 항목 앞부분의 [2 단계: PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙 만들기](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 섹션에 설명 된 대로 규칙을 만들 때도 같은 설정을 사용할 수 있습니다.

아웃 바운드 스팸 필터 규칙을 수정 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

구문 및 매개 변수에 대 한 자세한 내용은 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)를 참조 하십시오.

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙을 사용 하거나 사용 하지 않도록 설정

PowerShell에서 아웃 바운드 스팸 필터 규칙을 사용 하거나 사용 하지 않도록 설정 하면 전체 아웃 바운드 스팸 정책 (아웃 바운드 스팸 필터 규칙 및 할당 된 아웃 바운드 스팸 필터 정책)을 사용 하거나 사용 하지 않도록 설정 됩니다. 기본 아웃 바운드 스팸 정책을 사용 하거나 사용 하지 않도록 설정할 수 없습니다 (항상 항상 모든 받는 사람에 게 적용 됨).

PowerShell에서 아웃 바운드 스팸 필터 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 구문을 사용 합니다.

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

이 예에서는 Marketing 부서 라는 아웃 바운드 스팸 필터 규칙을 사용 하지 않도록 설정 합니다.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

구문 및 매개 변수에 대 한 자세한 내용은 [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 및 [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)을 참조 하십시오.

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙의 우선 순위 설정

규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다. 설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다. 예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다. 기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다. 예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.

PowerShell에서 아웃 바운드 스팸 필터 규칙의 우선 순위를 설정 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다. 우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - 새 규칙을 만들 때 우선 순위를 설정 하려면 대신 **HostedOutboundSpamFilterRule** Cmdlet에서 _priority_ 매개 변수를 사용 하십시오.
>
> - 아웃 바운드 기본 스팸 필터 정책에는 해당 하는 스팸 필터 규칙이 없으며 항상이에 해당 하지 않는 우선 순위 값이 **가장 낮습니다**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell을 사용 하 여 아웃 바운드 스팸 필터 정책 제거

PowerShell을 사용 하 여 아웃 바운드 스팸 필터 정책을 제거 하면 해당 하는 아웃 바운드 스팸 필터 규칙이 제거 되지 않습니다.

PowerShell에서 아웃 바운드 스팸 필터 정책을 제거 하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

이 예에서는 Marketing 학과 라는 아웃 바운드 스팸 필터 정책을 제거 합니다.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

구문과 매개 변수에 대 한 자세한 내용은 [get-hostedoutboundspamfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)를 참조 하십시오.

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙 제거

PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙을 제거 하면 해당 하는 아웃 바운드 스팸 필터 정책이 제거 되지 않습니다.

PowerShell에서 아웃 바운드 스팸 필터 규칙을 제거 하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

이 예에서는 Marketing 부서 라는 아웃 바운드 스팸 필터 규칙을 제거 합니다.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

구문과 매개 변수에 대 한 자세한 내용은 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)를 참조 하십시오.

## <a name="for-more-information"></a>자세한 내용

[제한된 사용자 포털에서 차단된 사용자 제거](removing-user-from-restricted-users-portal-after-spam.md)

[아웃바운드 메시지용 높은 위험 배달 풀](high-risk-delivery-pool-for-outbound-messages.md)

[스팸 방지 및 보호 FAQ](anti-spam-protection-faq.md)

[자동 전달 메시지 보고서](mfi-auto-forwarded-messages-report.md)
