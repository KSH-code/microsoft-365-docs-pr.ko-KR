---
title: EOP에서 스팸 방지 정책 구성하기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online 사서함을 사용하거나 없는 EOP(Exchange Online Protection) 조직에서 사용할 수 있는 피싱 방지 정책을 만들고 수정하고 삭제하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5bab5e791cb58c4e681a802179583471bb6ab165
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287916"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>EOP에서 스팸 방지 정책 구성하기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)

Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에는 기본적으로 사용하도록 설정된 제한된 수의 스푸핑 방지 기능을 포함하는 기본 피싱 방지 정책이 있습니다. 자세한 내용은 피싱 방지 정책의 [스푸핑 설정을 참조하세요.](set-up-anti-phishing-policies.md#spoof-settings)

관리자는 기본 피싱 방지 정책을 보고 편집하고 구성할 수 있지만 삭제할 수 없습니다. 세분성을 강화하기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 피싱 방지 정책을 만들 수도 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.

Exchange Online 사서함이 있는 조직은 보안 및 준수 센터 또는 Exchange Online powerShell에서 & 피싱 방지 정책을 구성할 수 있습니다. 독립 실행형 EOP 조직은 보안 및 준수 & 수 있습니다.

Office 365용 Defender에서 사용할 수 있는 Microsoft Defender for Office 365에서 보다 고급 피싱 방지 정책을 만들고 수정하는 데 대한 자세한 내용은 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.

피싱 방지 정책의 기본 요소는 다음입니다.

- **피싱** 방지 정책: 사용하도록 설정하거나 사용하지 않도록 설정할 피싱 보호와 옵션을 적용할 작업을 지정합니다.
- **피싱** 방지 규칙: 피싱 방지 정책에 대한 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.

보안 및 준수 센터에서 피싱 방지 정책을 관리할 때 이러한 두 요소의 차이는 & 명확하지 않습니다.

- 피싱 방지 정책을 만들 때 실제로는 둘 다에 대해 동일한 이름을 사용하여 피싱 방지 규칙과 연결된 피싱 방지 정책을 동시에 만들게 됩니다.
- 피싱 방지 정책을 수정할 때 이름, 우선 순위, 사용 또는 사용 안 하도록 설정, 받는 사람 필터와 관련된 설정은 피싱 방지 규칙을 수정합니다. 다른 모든 설정은 연결된 피싱 방지 정책을 수정합니다.
- 피싱 방지 정책을 제거하면 피싱 방지 규칙 및 연결된 피싱 방지 정책이 제거됩니다.

Exchange Online PowerShell에서는 정책과 규칙을 별도로 관리합니다. 자세한 내용은 이 문서 부분의 [Exchange Online PowerShell을](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 사용하여 피싱 방지 정책 구성 섹션을 참조하십시오.

모든 조직에는 다음 속성이 있는 Office365 AntiPhish Default라는 기본 제공 피싱 방지 정책이 있습니다.

- 이 정책은 정책과 연결된 피싱 방지 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 적용됩니다.
- 정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨). 사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.
- 그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.

피싱 방지 보호의 효율성을 높이기 위해 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 피싱 방지 정책을 만들 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 피싱 방지 **페이지로** 직접 이동하기 위해 다음을 <https://protection.office.com/antiphishing> 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

  독립 실행형 EOP PowerShell에서는 피싱 방지 정책을 관리할 수 없습니다.

- 이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.
  - 피싱 방지 정책을 추가, 수정 및 삭제하려면 조직 관리 또는  보안 관리자 역할 그룹의 구성원이 **되거나** 삭제해야 합니다.
  - 피싱 방지 정책에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 그룹 또는 보안 읽기 권한이 있는 역할 그룹의 구성원이 **되거나,** <sup>\*</sup>

  자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  - [또한 Exchange Online의](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 보기 **전용 조직 관리** 역할 그룹은 기능에 대한 읽기 전용 액세스 권한을 <sup>\*</sup> 제공합니다.
  - <sup>\*</sup> 보안 & 준수 센터에서 읽기 전용 액세스를 통해 사용자는 사용자 지정 피싱 방지 정책 설정을 볼 수 있습니다. 읽기 전용인 사용자는 기본 피싱 방지 정책의 설정을 볼 수 없습니다.

- 독립 실행형 EOP에서 피싱 방지 정책을 만들고 수정하려면 테넌트에 대한 하이드레이션이 필요한 작업을 해야 합니다.  예를 들어 EAC(Exchange 관리 센터)에서 사용  권한 탭으로 이동하여 기존  역할 그룹을 선택하고 편집 아이콘을 클릭한 다음 역할을 제거할 수 있습니다(최종적으로 다시 추가). ![ ](../../media/ITPro-EAC-EditIcon.png) 테넌트가 하이드레이션된 적이 없는 경우  성공적으로 완료해야 하는 진행률 표시줄이 있는 조직 설정 업데이트라는 대화 상자가 표시됩니다. 하이드레이션에 대한 자세한 내용은 [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet(독립 실행형 EOP PowerShell 또는 Security & 준수 센터에서는 사용할 수 없습니다.)를 참조하세요.

- 피싱 방지 정책에 대한 권장 설정은 EOP 기본 피싱 방지 정책 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

- 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.

- 필터링 파이프라인에서 피싱 방지 정책이 적용되는 위치는 전자 메일 보호의 순서 및 우선 순위를 [참조하세요.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>보안 및 & 센터를 사용하여 피싱 방지 정책 만들기

보안 및 준수 센터에서 사용자 지정 피싱 & 정책을 만들면 피싱 방지 규칙과 연결된 피싱 방지 정책이 동시에 두 가지 모두에 대해 동일한 이름을 사용하여 생성됩니다.

피싱 방지 정책을 만들 때 정책이 적용되는 사람을 식별하는 정책 이름, 설명 및 받는 사람 필터만 지정할 수 있습니다. 정책을 만든 후 기본 피싱 방지 설정을 변경하거나 검토하도록 정책을 수정할 수 있습니다.

1. 보안 & 준수 센터에서 위협 **관리** 정책 피싱 \>  \> **방지로 이동합니다.**

2. 피싱 **방지 페이지에서** 만들기를 **클릭합니다.**

3. 새 피싱 방지 정책 **만들기 마법사가** 열립니다. 정책 **이름 페이지에서** 다음 설정을 구성합니다.

   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다.

   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. 적용 **대상** 페이지가 나타나면 정책이 적용되는 내부 받는 사람을 식별합니다.

   조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

   조건 **추가를 클릭합니다.** 나타나는 드롭다운에서 적용된 조건(다음의 **경우)을 선택합니다.**

   - **받는 사람:** 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.
   - **받는 사람이 다음의 구성원인** 경우 조직에서 하나 이상의 그룹을 지정합니다.
   - **받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.

   조건을 선택하면 다음 상자와 함께 해당 **드롭다운이** 나타납니다.

   - 상자를 클릭하고 선택할 값 목록을 스크롤합니다.
   - 상자를 클릭하고 입력을 시작하여 목록을 필터링하고 값을 선택합니다.
   - 값을 더 추가하려면 상자의 빈 영역을 클릭합니다.
   - 개별 항목을 제거하려면  값에서 제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.
   - 전체 조건을 제거하려면 **조건에서** 제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.

   조건을 더 추가하려면 **조건** 추가를 클릭하고 적용된 경우 나머지 **값을 선택합니다.**

   예외를 추가하려면 **조건** 추가를 클릭하고 다음의 예외를 **선택합니다.** 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. 나타나는 **설정** 검토 페이지에서 설정을 검토합니다. 각 **설정에서** 편집을 클릭하여 수정할 수 있습니다.

   완료되면 이 정책 **만들기를 클릭합니다.**

6. 확인 **대화** 상자가 나타나면 확인을 클릭합니다.

이러한 일반 정책 설정을 사용하여 피싱 방지 정책을 만든 후 다음 섹션의 지침을 사용하여 정책의 보호 설정을 구성합니다.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>보안 및 & 센터를 사용하여 피싱 방지 정책 수정

다음 절차에 따라 만든 새 정책 또는 이미 사용자 지정한 기존 정책과 같은 피싱 방지 정책을 수정합니다.

1. 아직 없는 경우 보안 및 준수 센터를 & 위협 **관리** 정책 피싱 \>  \> **방지로 이동 합니다.**

2. 수정할 사용자 지정 피싱 방지 정책을 선택합니다. 이미 선택되어 있는 경우 선택을 다시 선택하지 않습니다.

3. 정책 **편집 \<name\> 플라이아웃이** 나타납니다. 모든 **섹션에서** 편집을 클릭하면 해당 섹션의 설정에 액세스할 수 있습니다.

   - 다음 단계는 섹션이 나타나는 순서대로 나타나지만 순서에 따라 섹션을 선택 및 수정할 수 있습니다.

   - 섹션에서  편집을 클릭하면 사용 가능한 설정이 마법사 형식으로 제공되지만 순서에 따라 페이지 내에서 점프할 수 있으며,    ![ ](../../media/scc-remove-icon.png) **\<name\>** 페이지에서 저장 또는 닫기 아이콘을 클릭하여 정책 편집 페이지로 돌아올 수 있습니다(저장하거나 남기기 위해 마법사의 마지막 페이지를 방문할 필요는 없음).

4. **정책 설정:** **편집을** 클릭하여 이전 섹션에서 [](#use-the-security--compliance-center-to-create-anti-phishing-policies) 정책을 만들 때 사용 가능한 설정과 동일한 설정을 수정합니다.

   - **이름**
   - **설명**
   - **적용 대상**
   - **설정 검토**

   완료되면 페이지에서 **저장을** 클릭합니다.

5. **스푸핑**: **편집을** 클릭하여 스푸핑 인텔리전스를 켜거나 끄고, Outlook에서 식별되지 않은 보낸 사람 ID를 설정 또는 해제하고, 차단된 스푸핑된 보낸 사람이 보낸 메시지에 적용할 작업을 구성합니다. 자세한 내용은 피싱 방지 정책의 [스푸핑 설정을 참조하세요.](set-up-anti-phishing-policies.md#spoof-settings)

   이러한 동일한 설정은 Office 365용 Defender의 피싱 방지 정책에서도 사용할 수 있습니다.

   - **스푸핑 필터 설정:** 기본값은 **On으로** 설정되어 있으며 그대로 두는 것이 좋습니다. 끄기 위해 토글을 끄면 **끄기** 자세한 내용은 [EOP에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)

     > [!NOTE]
     > MX 레코드가 Microsoft 365를 사용하지 않는 경우 스푸핑 방지 보호 기능을 사용하지 않도록 설정할 필요가 없습니다. 대신 커넥터에 대해 향상된 필터링을 사용하도록 설정할 수 있습니다. 자세한 내용은 Exchange Online의 커넥터에 대한 향상된 [필터링을 참조하세요.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **사용 안 하도록** 설정 보낸 사람 기능 : 기본값은 **On입니다.** 끄기 위해 토글을 끄면 **끄기**

   - **작업:** 스푸핑 인텔리전스에 실패한 메시지에 대해 수행할 작업을 지정합니다.

     **도메인을 스푸핑할** 수 없는 사람이 전자 메일을 보낸 경우:

     - **받는 사람의 정크 메일 폴더로 메시지 이동**
     - **메시지 Quarantine the message**

   - **설정 검토:** 각 개별 단계를 클릭하는 대신 설정이 요약에 표시됩니다.

     - 각 **섹션에서** 편집을 클릭하여 관련 페이지로 다시 이동하면 됩니다.
     - 이 페이지에서 직접 다음 설정을  **설정 또는** 해제할 수 있습니다.

       - **스푸핑 방지 보호 사용**
       - **비인식 보낸 사람 기능 사용**

   완료되면 페이지에서 **저장을** 클릭합니다.

6. 정책 편집 **\<Name\> 페이지에서** 설정을 검토한 다음 닫기 를 **클릭합니다.**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>보안 및 & 센터를 사용하여 기본 피싱 방지 정책 수정

기본 피싱 방지 정책의 이름은 Office365 AntiPhish Default로 지정되어 있으며 정책 목록에는 나타나지 않습니다. 기본 피싱 방지 정책을 수정하려면 다음 단계를 수행합니다.

1. 보안 & 준수 센터에서 위협 **관리** 정책 피싱 \>  \> **방지로 이동합니다.**

2. 피싱 **방지 페이지에서** 기본 정책을 **클릭합니다.**

3. The **Edit your policy Office365 AntiPhish Default** page appears. 사용자 지정 정책을 수정할 때와 동일한 설정을 포함하는 다음 섹션을 사용할 [수 있습니다.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)

   - **가장**
   - **스푸핑**
   - **고급 설정**

   기본 정책을 수정할 때 다음 설정을 사용할 수 없습니다.

   - 정책 설정  섹션과 값을 볼 수 있지만  편집 링크는 있으므로 설정(정책 이름, 설명 및 정책이 적용되는 사람)을 수정할 수 없습니다(모든 받는 사람에게 적용).
   - 기본 정책은 삭제할 수 없습니다.
   - 기본 정책의 우선 순위는 변경할 수 없습니다(항상 마지막에 적용).

4. On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>사용자 지정 피싱 방지 정책 사용 또는 사용 안 하도록 설정

1. 보안 & 준수 센터에서 위협 **관리** 정책 피싱 \>  \> **방지로 이동합니다.**

2. 상태 열의 **값을** 확인할 수 있습니다.

   - 토글을 **해제로 밀어** 정책을 사용하지 않도록 합니다.

   - 토글을 **설정으로 밀어 정책을** 사용하도록 설정합니다.

기본 피싱 방지 정책을 사용하지 않도록 설정할 수 없습니다.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>사용자 지정 피싱 방지 정책의 우선 순위 설정

기본적으로 피싱 방지 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.

사용자 지정 피싱 방지 정책은 처리되는 순서대로 표시됩니다(첫 번째  정책의 우선 순위 값은 0). Office365 AntiPhish Default라는 기본 피싱 방지 정책의 사용자 지정 우선 순위 값이 **가장** 낮습니다. 이 정책은 변경할 수 없습니다.

 **참고:** 보안 & 준수 센터에서는 피싱 방지 정책을 만든 후에만 변경할 수 있습니다. PowerShell에서 피싱 방지 규칙을 만들 때 기본 우선 순위를 다시 정할 수 있습니다(기존 규칙의 우선 순위에 영향을 줄 수 있습니다).

정책의 우선 순위를 변경하려면 정책  속성에서 우선 순위 늘리기 또는 우선 순위  감소를 클릭합니다(보안 및 준수 센터에서 직접 & 수 없습니다).  정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우만 의미가 있습니다.

1. 보안 & 준수 센터에서 위협 관리  \>  \> **정책 ATP 피싱 방지로 이동합니다.**

2. 수정할 정책을 선택합니다. 이미 선택되어 있는 경우 선택을 다시 선택하지 않습니다.

3. 정책 **편집 \<name\> 플라이아웃이** 나타납니다.

   - 우선 순위 값이 **0인**  사용자 지정 피싱 방지 정책에는 우선 순위 감소 단추만 사용할 **수** 있습니다.

   - 우선 순위 값이 가장 낮은 사용자  지정 피싱 방지 정책(예: **3)에는** 우선 순위 늘리기 단추만 사용할 **수** 있습니다.

   - 사용자 지정 피싱 방지 정책이 세 개 이상 있는 경우 우선 순위가 가장 높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 단추를 모두 사용할 **수** 있습니다. 

4. 우선 **순위 늘리기 또는** 우선 순위 **감소를** 클릭하여 우선 순위 값을 **변경합니다.**

5. 작업을 마쳤으면 **닫기** 를 클릭합니다.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>보안 및 & 센터를 사용하여 피싱 방지 정책 보기

1. 보안 & 준수 센터에서 위협 관리  정책 피싱 \>  \> **방지로 이동**

2. 다음 단계 중 하나를 수행합니다.

   - 보하려는 사용자 지정 피싱 방지 정책을 선택합니다. 이미 선택되어 있는 경우 선택을 다시 선택하지 않습니다.

   - 기본 **정책을 클릭하여** 기본 피싱 방지 정책을 볼 수 있습니다.

3. 설정 **및 \<name\> 값을 볼** 수 있는 정책 플라이아웃 편집이 나타납니다.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>보안 및 & 센터를 사용하여 피싱 방지 정책 제거

1. 보안 & 준수 센터에서 위협 **관리** 정책 피싱 \>  \> **방지로 이동합니다.**

2. 제거할 정책을 선택합니다. 이미 선택되어 있는 경우 선택을 다시 선택하지 않습니다.

3. 나타나는 정책 플라이아웃 편집에서 정책 삭제를 클릭한 다음 나타나는 경고 대화 상자에서 **예를** 클릭합니다. **\<name\>**

기본 정책은 제거할 수 없습니다.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Exchange Online PowerShell을 사용하여 피싱 방지 정책 구성

앞서 설명한 바와 같이 피싱 방지 정책은 피싱 방지 정책과 피싱 방지 규칙으로 구성됩니다.

Exchange Online PowerShell에서는 피싱 방지 정책과 피싱 방지 규칙의 차이점이 분명합니다. **\* -AntiPhishPolicy** cmdlet을 사용하여 피싱 방지 정책을 관리하고 **\* -AntiPhishRule** cmdlet을 사용하여 피싱 방지 규칙을 관리합니다.

- PowerShell에서 피싱 방지 정책을 먼저 만든 다음 규칙이 적용되는 정책을 식별하는 피싱 방지 규칙을 생성합니다.
- PowerShell에서는 피싱 방지 정책 및 피싱 방지 규칙의 설정을 별도로 수정합니다.
- PowerShell에서 피싱 방지 정책을 제거하면 해당 피싱 방지 규칙이 자동으로 제거되지 않습니다.

> [!NOTE]
> 다음 PowerShell 절차는 Exchange Online Protection PowerShell을 사용하는 독립 실행형 EOP 조직에서는 사용할 수 없습니다.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell을 사용하여 피싱 방지 정책 만들기

PowerShell에서 피싱 방지 정책을 만드는 과정은 다음 두 단계로 진행됩니다.

1. 피싱 방지 정책을 생성합니다.
2. 규칙이 적용되는 피싱 방지 정책을 지정하는 피싱 방지 규칙을 생성합니다.

 **참고:**

- 새 피싱 방지 규칙을 만들고 기존의 통합되지 않은 피싱 방지 정책을 할당할 수 있습니다. 피싱 방지 규칙은 피싱 방지 정책과 두 개 이상 연결될 수 없습니다.

- PowerShell에서 보안 및 준수 센터에서 사용할 수 없는 새 피싱 방지 정책에 대해 다음 설정을 구성할 & 정책을 만든 후에 구성할 수 있습니다.

  - 새 정책을 사용할 수 `$false` **없습니다(New-AntiPhishRule** cmdlet에서 사용).
  -  _\<Number\>_ **New-AntiPhishRule** cmdlet에서 만들기 중 정책의 우선 순위(우선 순위)를 설정합니다.

- PowerShell에서 만든 새로운 피싱 방지 정책은 피싱 방지 규칙에 정책을 할당할 때까지 보안 & 준수 센터에 표시되지 않습니다.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>1단계: PowerShell을 사용하여 피싱 방지 정책 만들기

피싱 방지 정책을 만들 경우 다음 구문을 사용 합니다.

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

이 예에서는 다음 설정을 사용하여 Research Quarantine이라는 피싱 방지 정책을 만듭니다.

- 설명은 리서치 부서 정책입니다.
- 스푸핑에 대한 기본 작업을 Quarantine으로 변경합니다.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>2단계: PowerShell을 사용하여 피싱 방지 규칙 만들기

피싱 방지 규칙을 만들 경우 다음 구문을 사용 합니다.

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

이 예에서는 다음 조건을 통해 Research Department라는 피싱 방지 규칙을 만듭니다.

- 이 규칙은 Research Quarantine이라는 피싱 방지 정책과 연결됩니다.
- 이 규칙은 Research Department 그룹의 구성원에게 적용됩니다.
- Priority 매개 변수를  사용하지 않는 경우 기본 우선 순위가 사용됩니다.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell을 사용하여 피싱 방지 정책 보기

기존 피싱 방지 정책을 보시다시피 다음 구문을 사용 합니다.

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예에서는 지정된 속성과 함께 모든 피싱 방지 정책의 요약 목록을 반환합니다.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

이 예에서는 Executives라는 피싱 방지 정책의 모든 속성 값을 반환합니다.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell을 사용하여 피싱 방지 규칙 보기

기존 피싱 방지 규칙을 보시다시피 다음 구문을 사용 합니다.

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예제에서는 지정된 속성과 함께 모든 피싱 방지 규칙의 요약 목록을 반환합니다.

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

이 예에서는 Contoso Executives라는 피싱 방지 규칙의 모든 속성 값을 반환합니다.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell을 사용하여 피싱 방지 정책 수정

다음 항목 이외에도 PowerShell에서 피싱 방지 정책을 수정할 때와 동일한 설정을 사용할 수 있습니다. [1단계: PowerShell을](#step-1-use-powershell-to-create-an-anti-phish-policy) 사용하여 이 문서의 앞부분에서 설명한 대로 피싱 방지 정책을 만들 수 있습니다.

- 지정된 정책을 기본 정책으로 전환하는 _MakeDefault_ 스위치는 PowerShell에서 피싱 방지 정책을 수정할 때만 사용할 수 있습니다(모든 사용자에 적용, 항상 최하위 우선 순위 및 삭제할 수 없습니다). 

- 피싱 방지 정책의 이름을 다시 설정할 수 **없습니다(Set-AntiPhishPolicy** cmdlet에는 Name 매개 _변수가_ 없음). 보안 및 준수 센터에서 피싱 방지 정책의 이름을 & 피싱 방지 규칙의 이름만 다시 _매기게 됩니다._

피싱 방지 정책을 수정하려면 다음 구문을 사용 합니다.

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell을 사용하여 피싱 방지 규칙 수정

PowerShell에서 피싱 방지 규칙을 수정할 때 사용할 수 없는 설정은 _사용되지_ 않는 규칙을 만들 수 있는 Enabled 매개 변수뿐입니다. 기존 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.

그렇지 않으면 [2단계: PowerShell을](#step-2-use-powershell-to-create-an-anti-phish-rule) 사용하여 이 문서 앞부분의 피싱 방지 규칙 섹션을 만들 때와 동일한 설정을 사용할 수 있습니다.

피싱 방지 규칙을 수정하려면 다음 구문을 사용 합니다.

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell을 사용하여 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정

PowerShell에서 피싱 방지 규칙을 설정하거나 사용하지 않도록 설정하면 전체 피싱 방지 정책(피싱 방지 규칙 및 할당된 피싱 방지 정책)을 활성화하거나 사용하지 않도록 설정할 수 있습니다. 기본 피싱 방지 정책을 활성화하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용).

PowerShell에서 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

이 예에서는 Marketing Department라는 피싱 방지 규칙을 사용하지 않도록 설정합니다.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 및 [Disable-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell을 사용하여 피싱 방지 규칙의 우선 순위 설정

규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다. 설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다. 예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다. 기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다. 예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.

PowerShell에서 피싱 방지 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다. 우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**참고:**

- 새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-AntiPhishRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.

- 기본 피싱 방지 정책에는 해당하는 피싱 방지 규칙이 없습니다. 항상 가장 낮은 우선 순위 값이 **가장 낮습니다.**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell을 사용하여 피싱 방지 정책 제거

PowerShell을 사용하여 피싱 방지 정책을 제거하면 해당 피싱 방지 규칙이 제거되지 않습니다.

PowerShell에서 피싱 방지 정책을 제거하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

이 예에서는 Marketing Department라는 피싱 방지 정책을 제거합니다.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell을 사용하여 피싱 방지 규칙 제거

PowerShell을 사용하여 피싱 방지 규칙을 제거하면 해당 피싱 방지 정책이 제거되지 않습니다.

PowerShell에서 피싱 방지 규칙을 제거하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

이 예에서는 Marketing Department라는 피싱 방지 규칙을 제거합니다.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

Office 365용 Microsoft Defender에서 피싱 방지 정책을 성공적으로 구성한지 확인하기 위해 다음 단계를 수행합니다.

- 보안 & 준수 센터에서 위협 **관리** 정책 피싱 \>  \> **방지로 이동합니다.** 정책 목록, 정책  상태 값 및 **우선** 순위 값을 검증합니다. 자세한 내용을 확인하기 위해 다음 단계 중 하나를 수행합니다.

  - 목록에서 정책을 선택하고 플라이아웃에서 세부 정보를 볼 수 있습니다.
  - 기본 **정책을 클릭하고** 플라이아웃에서 세부 정보를 볼 수 있습니다.

- Exchange Online PowerShell에서 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 설정을 \<Name\> 확인합니다.

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
