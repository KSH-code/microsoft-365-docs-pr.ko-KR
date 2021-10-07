---
title: Microsoft Defender에서 금고 링크 정책 Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft Defender for 금고 링크 정책 및 전역 금고 링크 설정을 보고, 만들고, 수정하고 삭제하는 방법을 Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85d2ad698ffc1a450afc302586134bdd5e566eb5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207550"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender에서 금고 링크 정책 Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 이 문서는 [Office 365용 Microsoft Defender](defender-for-office-365.md)가 있는 비즈니스 고객을 대상으로 합니다. 사용자 계정의 Safelinks에 대한 정보를 찾는 가정용 사용자인 Outlook [고급 Outlook.com 보안 을 참조하세요.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

금고 Microsoft [Defender for Office 365](defender-for-office-365.md) 메일 흐름에서 인바운드 전자 메일 메시지의 URL 검색과 전자 메일 메시지 및 기타 위치에서 URL 및 링크 확인을 클릭하는 시간을 제공합니다. 자세한 내용은 microsoft [Defender에서](safe-links.md)금고 링크를 참조하세요Office 365.

기본 제공 또는 기본 금고 정책이 없습니다. URL의 금고 검색하려면 이 문서에 설명된 하나 이상의 금고 링크 정책을 만들어야 합니다.

> [!NOTE]
>
> 링크 정책 외부에서 금고 링크 **보호에** 대한 전역 금고 구성합니다. 자세한 내용은 [Configure global settings for 금고 Links in Microsoft Defender for Office 365.](configure-global-settings-for-safe-links.md)
>
> 관리자는 링크에 대한 다양한 구성 금고 고려해야 합니다. 사용 가능한 옵션 중 하나는 링크에 사용자 식별 정보를 금고 것입니다. 이 기능을 사용하면 *보안 Ops* 팀에서 잠재적인 사용자 손상을 조사하고, 수정 조치를 취하고, 비용이 많이 드는 위반을 제한할 수 있습니다.

Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online PowerShell)에서 Exchange Online 사서함이 있는 적합한 Microsoft 365 조직에 대해 Exchange Online 링크 정책을 구성할 수 있습니다. 금고 Exchange Online 추가 기능 구독용 Microsoft Defender를 Office 365)

링크 정책의 금고 요소는 다음입니다.

- 안전한 링크 **정책:** 금고 링크 보호를 켜고, 실시간 URL 검색을 켜고, 메시지를 배달하기 전에 실시간 검색이 완료될 때까지 기다릴지 여부를 지정하고, 내부 메시지 검색을 켜고, URL에서 사용자 클릭을 추적할지 여부를 지정하고, 사용자가 원래 URL로 휴지통을 클릭할 수 있도록 허용할지 여부를 지정합니다.
- **안전한 링크 규칙:** 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.

이러한 두 요소 간의 차이는 금고 포털에서 링크 정책을 관리할 때 명확하지 Microsoft 365 Defender 않습니다.

- 금고 링크 정책을 만들면 실제로 동일한 이름을 사용하여 안전한 링크 규칙과 연결된 안전한 링크 정책을 동시에 만들게 됩니다.
- 링크 정책을 금고, 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 안전한 링크 규칙을 수정합니다. 다른 모든 설정은 연결된 안전한 링크 정책을 수정합니다.
- 링크 금고 제거하면 안전한 링크 규칙 및 연결된 안전한 링크 정책이 제거됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다. 자세한 내용은 이 문서의 Exchange Online PowerShell 또는 독립 실행형 [EOP PowerShell을](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 사용하여 금고 링크 정책 구성 섹션을 참조하세요.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com/>에서 Microsoft 365 Defender 포털을 엽니다. 링크 페이지로 직접 금고 **를** <https://security.microsoft.com/safelinksv2> 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다.
  - 금고 링크 정책을 만들고 수정하고 삭제하려면 Microsoft 365 Defender 포털에서 조직 관리 또는  보안 관리자 역할 그룹의 구성원이자  조직의 조직  관리 역할 그룹의 구성원인 Exchange Online. 
  - 링크 정책에 금고 읽기 전용으로 액세스하려면 전역 읽기 사용자  또는 보안 읽기 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.

  자세한 내용은 Microsoft 365 Defender [포털의](permissions-microsoft-365-security-center.md) 사용 권한 및 [Exchange Online.](/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  >
  > - Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 포털에서 필요한 사용 권한 및 Microsoft 365 Defender 포털의  다른 기능에 대한 사용 권한이 Microsoft 365. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  . - 조직의 보기 전용 **조직** 관리 [역할 Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 기능에 대한 읽기 전용 액세스 권한을 제공합니다.

- 링크 정책에 대한 권장 금고 링크 정책 금고 [설정을 참조하세요.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

- 새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.

- [새로운 기능은 계속해서](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Microsoft Defender for Office 365. 새 기능이 추가될 때 기존 링크 정책에 대한 조정을 금고 있습니다.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>Microsoft 365 Defender 포털을 사용하여 금고 정책 만들기

Microsoft 365 Defender 포털에서 사용자 지정 금고 링크 정책을 만들면 동일한 이름을 사용하여 안전한 링크 규칙과 연결된 안전한 링크 정책이 동시에 생성됩니다.

1. Microsoft 365 Defender 포털에서 정책 & 정책  정책 섹션에서 금고 \>  \>  \> **로 이동하세요.**

2. 링크 **금고 만들기** ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **만들기**.

3. 새 **금고 링크 정책 마법사가** 열립니다. 정책 **이름 지정 페이지에서** 다음 설정을 구성합니다.

   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다.
   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. 나타나는 **사용자 및 도메인** 페이지에서 정책이 적용되는 내부 받는 사람을 식별합니다(받는 사람 조건).
   - **사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.
   - **그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.
   - **도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.

   적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다. 이 프로세스를 필요한 만큼 반복합니다. 기존 값을 제거하려면 제거를 클릭합니다. ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 값 옆에 있습니다.

   사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다. 사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.

   동일한 조건의 여러 값은 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 서로 다른 조건은 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

   - **다음 사용자, 그룹 및 도메인 제외**: 해당 정책의 적용 대상인 내부의 받는 사람에게 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다. 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. 나타나는 **보호 설정** 페이지에서 다음 설정을 구성합니다.
   - **메시지의** 알 수 없는 악의적인 URL에  대한 작업 선택: 전자 메일 메시지의 링크에 대한 금고 보호를 사용하도록 설정하려면 을 선택합니다. 이 설정을 켜면 다음 설정을 사용할 수 있습니다.
     - **파일을 지정하는** 의심스러운 링크 및 링크에 대한 실시간 URL 검색 적용: 전자 메일 메시지의 링크를 실시간으로 검색할 수 있도록 설정하려면 이 옵션을 선택합니다. 이 설정을 켜면 다음 설정을 사용할 수 있습니다.
       - **메시지를 배달하기** 전에 URL 검색이 완료될 때까지 기다렸다가 : 메시지를 배달하기 전에 실시간 URL 검색이 완료될 때까지 기다리는 경우 이 옵션을 선택합니다.
     - **조직 금고** 보내는 전자 메일 메시지에 대한 링크 적용: 내부 보낸 사람과 내부 받는 사람 간의 메시지에 금고 링크 정책을 적용하려면 이 옵션을 선택합니다.
   - **내 알 수 없는 URL** 또는 잠재적으로 악의적인  URL에 대한 작업을 Microsoft Teams: 을 선택하여 금고 링크 보호를 사용하도록 Teams. 이 설정을 적용하는 데 최대 24시간이 걸릴 수 있습니다.
   - **사용자 클릭 추적 안** 하세요. 추적 사용자가 전자 메일 메시지의 URL을 클릭할 수 있도록 설정하려면 이 설정을 선택하지 않은 그대로 하세요.
   - **사용자가 원래 URL을 클릭할** 수 있도록 허용 안 하도록 허용: 사용자가 경고 페이지에서 원래 URL을 클릭하지 못하도록 차단하려면 이 [옵션을 선택합니다.](safe-links.md#warning-pages-from-safe-links)
   - **다음 URL을** 다시 덮어치지 않습니다. 링크에서 차단할 지정된 URL에 액세스할 금고 있습니다.

     상자에 원하는 URL 또는 값을 입력한 다음 추가를 **클릭합니다.** 필요한 만큼 이 단계를 반복합니다.

     기존 항목을 제거하려면 ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 항목 옆의

     항목 구문은 "다음 URL을 다시 덮어치지 않습니다." 목록의 항목 [구문을 참조하세요.](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   이러한 설정에 대한 자세한 내용은 전자 [메일 메시지에](safe-links.md#safe-links-settings-for-email-messages) 대한 금고 링크 설정 및 금고 링크 설정을 [Microsoft Teams.](safe-links.md#safe-links-settings-for-microsoft-teams)

   표준 및 엄격한 정책 설정에 대한 권장 값은 금고 링크 정책 설정을 [참조하세요.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

   작업을 마친 후 **다음** 을 클릭합니다.

6. 알림 **페이지가** 나타나면 사용자에게 어떻게 알리시겠습니까?에 대해 다음 값 중 하나를 **선택합니다.**
   - **기본 알림 텍스트 사용**
   - **사용자 지정 알림** 텍스트 사용: 이 값을 선택하면(길이가 200자 초과할 수 없는 경우) 다음 설정이 나타납니다.
     - **자동 Microsoft 번역기 설정 사용**
     - **사용자 지정 알림 텍스트:** 이 상자에 사용자 지정 알림 텍스트를 입력합니다.

   작업을 마친 후 **다음** 을 클릭합니다.

7. 표시되는 **검토** 페이지에서 설정을 검토합니다. 각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다. 또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.

   작업을 마쳤으면 **제출** 을 클릭합니다.

8. 표시되는 확인 페이지에서 **완료** 를 클릭합니다.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>Microsoft 365 Defender 포털을 사용하여 금고 정책 보기

1. Microsoft 365 Defender 포털에서 정책 & 정책  정책 섹션에서 금고 \>  \>  \> **로 이동하세요.**

2. 금고  링크 페이지에는 다음 속성이 링크 정책 금고 표시됩니다.
   - **이름**
   - **상태**
   - **우선 순위**

3. 이름을 클릭하여 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>Microsoft 365 Defender 포털을 사용하여 링크 금고 수정

1. Microsoft 365 Defender 포털에서 정책 & 정책  정책 섹션에서 금고 \>  \>  \> **로 이동하세요.**

2. 링크 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.

3. 표시되는 정책 세부 정보 플라이아웃에서 각 섹션에서 **편집** 을 선택하여 섹션 내의 설정을 수정합니다. 설정에 대한 자세한 내용은 이 문서의 이전 Microsoft 365 Defender [포털을 사용하여](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) 금고 링크 정책 만들기 섹션을 참조하세요.

정책을 사용하도록 설정하거나 사용하지 않도록 설정하거나 정책 우선 순위를 설정하려면 다음 섹션을 참조하세요.

### <a name="enable-or-disable-safe-links-policies"></a>링크 정책 금고 사용 또는 사용 안 하도록 설정

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 \>  \> **금고** \> **링크로** 이동하세요. 

2. 링크 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.

3. 표시되는 정책 세부 정보 플라이아웃 맨 위에 다음 값 중 하나가 표시됩니다.
   - **정책 꺼짐**: 정책을 켜려면 ![켜기 아이콘.](../../media/m365-cc-sc-turn-on-off-icon.png) **켜기** 를 클릭합니다.
   - **정책 켜짐**: 정책을 끄려면 ![끄기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **끄기** 를 클릭합니다.

4. 표시되는 확인 대화 상자에서 **켜기** 또는 **끄기** 를 클릭합니다.

5. 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.

기본 정책 페이지로 돌아가면 정책의 **상태** 값이 **켜짐** 또는 **꺼짐** 입니다.

### <a name="set-the-priority-of-safe-links-policies"></a>링크 정책의 금고 설정

기본적으로 금고 링크에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

정책의 우선 순위를 변경하려면 정책 속성에서 **우선 순위를 높이** 거나 **우선 순위를 낮춥** 니다(Microsoft 365 Defender 포털에서 **우선 순위** 번호를 직접 수정할 수 없습니다). 정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우에만 의미가 있습니다.

**참고**:

- Microsoft 365 Defender 포털에서 만든 후 금고 링크 정책의 우선 순위만 변경할 수 있습니다. PowerShell에서 안전한 링크 규칙을 만들 때 기본 우선 순위를 다시 정할 수 있습니다(기존 규칙의 우선 순위에 영향을 줄 수 있습니다).
- 금고 링크 정책은 표시되는 순서대로 처리됩니다(첫 번째 정책의  우선 순위 값은 0). 우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 \>  \> **금고** \> **링크로** 이동하세요. 

2. 링크 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.

3. 표시되는 정책 세부 정보 플라이아웃 맨 위에 현재 우선 순위 값 및 사용자 지정 정책 수를 기준으로 **우선순위 증가** 또는 **우선순위 감소** 가 표시됩니다.
   - 우선 순위  값이 **0인** 정책에는 우선 순위 감소 옵션만 사용할 **수** 있습니다.
   - 우선 순위 값이 가장 **낮은** 정책(예: **3)에는** 우선 순위 늘리기 옵션만 사용할 **수** 있습니다.
   - 세 개 이상의 정책이 있는 경우 우선 순위가 가장  높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 옵션을 모두 사용할 **수** 있습니다.

   ![우선 순위 증가 아이콘](../../media/m365-cc-sc-increase-icon.png) **우선 순위 증가** 또는 ![우선 순위 감소 아이콘](../../media/m365-cc-sc-decrease-icon.png) **우선순위 감소** 를 클릭하여 **우선 순위** 값을 변경합니다.

4. 작업을 마쳤으면 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>Microsoft 365 Defender 포털을 사용하여 링크 금고 제거

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 \>  \> **금고** \> **링크로** 이동하세요. 

2. 링크 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다. 표시되는 정책 세부 정보 플라이아웃 상단에서 ![추가 작업 아이콘](../../media/m365-cc-sc-more-actions-icon.png)을 클릭합니다. **추가 작업** \> ![정책 아이콘 삭제](../../media/m365-cc-sc-delete-icon.png) **정책 삭제**.

3. 확인 대화 상자가 나타나면 **예** 를 클릭합니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 금고 정책 구성

앞서 설명한 금고 링크 정책은 안전한 링크 정책과 안전한 링크 규칙으로 구성됩니다.

PowerShell에서 안전한 링크 정책과 안전한 링크 규칙의 차이는 분명합니다. **\* -SafeLinksPolicy** cmdlet을 사용하여 안전한 링크 정책을 관리하고 **\* -SafeLinksRule** cmdlet을 사용하여 안전한 링크 규칙을 관리합니다.

- PowerShell에서 먼저 안전한 링크 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 안전한 링크 규칙을 생성합니다.
- PowerShell에서는 안전한 링크 정책 및 안전한 링크 규칙의 설정을 별도로 수정합니다.
- PowerShell에서 안전한 링크 정책을 제거하면 해당 안전 링크 규칙이 자동으로 제거되지 않습니다.

### <a name="use-powershell-to-create-safe-links-policies"></a>PowerShell을 사용하여 금고 정책 만들기

PowerShell에서 금고 링크 정책을 만드는 과정은 다음 두 단계로 진행됩니다.

1. 안전한 링크 정책을 만들 수 있습니다.
2. 규칙이 적용되는 안전한 링크 정책을 지정하는 안전한 링크 규칙을 만들 수 있습니다.

> [!NOTE]
>
> - 새 안전한 링크 규칙을 만들고 연결되지 않은 기존 안전한 링크 정책을 할당할 수 있습니다. 안전한 링크 규칙은 두 개 이상의 안전한 링크 정책과 연결될 수 없습니다.
>
> - 정책을 만든 후까지 Microsoft 365 Defender 포털에서 사용할 수 없는 PowerShell의 새 안전한 링크 정책에 대해 다음 설정을 구성할 수 있습니다.
>   - 새 정책을 사용하지 않도록 `$false` **설정(New-SafeLinksRule** cmdlet에서 사용)으로 설정합니다.
>   -  _\<Number\>_ **New-SafeLinksRule** cmdlet에서 만들 때 정책의 우선 순위( 우선 순위)를 설정하십시오.
>
> - PowerShell에서 만든 새 안전한 링크 정책은 안전한 링크 규칙에 정책을 할당할 때까지 Microsoft 365 Defender 포털에 표시되지 않습니다.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>1단계: PowerShell을 사용하여 안전한 링크 정책 만들기

안전한 링크 정책을 만들 수 있도록 다음 구문을 사용하세요.

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - _DoNotRewriteUrls_ 매개 변수에 사용할 항목 구문에 대한 자세한 내용은 "다음 URL을 다시 덮어치지 않습니다" 목록의 항목 구문을 [참조하세요.](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)
>
> - **Set-SafeLinksPolicy** cmdlet을 사용하여 기존 안전한 링크 정책을 수정할 때 _DoNotRewriteUrls_ 매개 변수에 사용할 수 있는 추가 구문은 이 문서 의 부분에 있는 [PowerShell을](#use-powershell-to-modify-safe-links-policies) 사용하여 안전한 링크 정책 수정 섹션을 참조하세요.

이 예에서는 다음 값을 지정하여 Contoso All이라는 안전한 링크 정책을 만듭니다.

- 전자 메일 메시지에서 URL 검색 및 다시 끄기
- 2016에서 URL 검색을 Teams.
- 파일을 지점하는 클릭된 링크를 포함하여 클릭한 URL에 대한 실시간 검색을 하게 합니다.
- URL 검색이 완료될 때까지 기다렸다가 메시지를 배달합니다.
- 내부 메시지에 대해 URL 검색 및 다시 덮기 기능을 켜세요.
- 금고 링크 보호와 관련된 사용자 클릭 _추적(DoNotTrackUserClicks_ 매개 변수를 사용하지는 않습니다. 기본값은 $false, 즉 사용자 클릭이 추적됩니다.)입니다.
- 사용자가 원래 URL을 클릭할 수 있도록 허용하지 않습니다.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

구문과 매개 변수에 대한 자세한 내용은 [New-SafeLinksPolicy를 참조하십시오.](/powershell/module/exchange/new-safelinkspolicy)

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>2단계: PowerShell을 사용하여 안전한 링크 규칙 만들기

안전한 링크 규칙을 만들 수 있도록 다음 구문을 사용하세요.

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

이 예에서는 다음 조건을 통해 Contoso All이라는 안전한 링크 규칙을 만듭니다.

- 이 규칙은 Contoso All이라는 안전한 링크 정책과 연결됩니다.
- 이 규칙은 도메인의 모든 받는 사람에게 contoso.com 적용됩니다.
- Priority 매개 변수를  사용하지 않을 것이기 때문에 기본 우선 순위가 사용됩니다.
- 이 규칙은 사용하도록 설정됩니다(Enabled  매개 변수를 사용하지 않습니다. 기본값은 `$true` 입니다).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

구문과 매개 변수에 대한 자세한 내용은 [New-SafeLinksRule을 참조하십시오.](/powershell/module/exchange/new-safelinksrule)

### <a name="use-powershell-to-view-safe-links-policies"></a>PowerShell을 사용하여 안전한 링크 정책 보기

기존 안전한 링크 정책을 보시고 다음 구문을 사용하세요.

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예에서는 모든 안전한 링크 정책의 요약 목록을 반환합니다.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

이 예에서는 Contoso Executives라는 안전한 링크 정책에 대한 자세한 정보를 반환합니다.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

구문과 매개 변수에 대한 자세한 내용은 [Get-SafeLinksPolicy를 참조하십시오.](/powershell/module/exchange/get-safelinkspolicy)

### <a name="use-powershell-to-view-safe-links-rules"></a>PowerShell을 사용하여 안전한 링크 규칙 보기

기존 안전한 링크 규칙을 보시고 다음 구문을 사용하세요.

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예에서는 모든 안전한 링크 규칙의 요약 목록을 반환합니다.

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

이 예에서는 Contoso Executives라는 안전한 링크 규칙에 대한 자세한 정보를 반환합니다.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

구문과 매개 변수에 대한 자세한 내용은 [Get-SafeLinksRule 을 참조하십시오.](/powershell/module/exchange/get-safelinksrule)

### <a name="use-powershell-to-modify-safe-links-policies"></a>PowerShell을 사용하여 안전한 링크 정책 수정

PowerShell에서 안전한 링크 정책의 이름을 다시 설정할 수 **없습니다(Set-SafeLinksPolicy** cmdlet에는 _Name_ 매개 변수가 없음). 금고 포털에서 금고 정책의 이름을 Microsoft 365 Defender 안전한 링크 규칙의 이름만 다시 _매기게 됩니다._

PowerShell에서 안전한 링크 정책을 수정할 때 고려해야 할 유일한 추가 고려 사항은 _DoNotRewriteUrls_ 매개 변수("다음 URL을 다시 덮어 두지 [않습니다" 목록)에](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)사용할 수 있는 구문입니다.

- 기존 항목을 대체할 값을 추가하기 위해 다음 구문을 `"Entry1","Entry2,..."EntryN"` 사용합니다. .
- 다른 기존 항목에 영향을 주지 않고 값을 추가하거나 제거하려면 다음 구문을 사용합니다. `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

그렇지 않으면 이 문서 앞부분의 [1단계: PowerShell을](#step-1-use-powershell-to-create-a-safe-links-policy) 사용하여 안전한 링크 정책 만들기 섹션에 설명된 대로 안전한 링크 정책을 만들 때 동일한 설정을 사용할 수 있습니다.

안전한 링크 정책을 수정하려면 다음 구문을 사용하세요.

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-SafeLinksPolicy를 참조하십시오.](/powershell/module/exchange/set-safelinkspolicy)

### <a name="use-powershell-to-modify-safe-links-rules"></a>PowerShell을 사용하여 안전한 링크 규칙 수정

PowerShell에서 안전한 링크 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용하지 않도록 설정된 규칙을 만들 수 있는 _Enabled_ 매개 변수뿐입니다. 기존 안전한 링크 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.

그렇지 않으면 이 문서 앞부분의 [2단계: PowerShell을](#step-2-use-powershell-to-create-a-safe-links-rule) 사용하여 안전한 링크 규칙 만들기 섹션에 설명된 대로 규칙을 만들 때 동일한 설정을 사용할 수 있습니다.

안전한 링크 규칙을 수정하려면 다음 구문을 사용하세요.

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-SafeLinksRule을 참조하십시오.](/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>PowerShell을 사용하여 안전한 링크 규칙을 사용 또는 사용하지 않도록 설정

PowerShell에서 안전한 링크 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하면 전체 금고 링크 정책(안전한 링크 규칙 및 할당된 안전한 링크 정책)을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.

PowerShell에서 안전한 링크 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

이 예에서는 Marketing Department라는 안전한 링크 규칙을 사용하지 않도록 설정합니다.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) 및 [Disable-SafeLinksRule을 참조하십시오.](/powershell/module/exchange/disable-safelinksrule)

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>PowerShell을 사용하여 안전한 링크 규칙의 우선 순위 설정

규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다. 설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다. 예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다. 기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다. 예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.

PowerShell에서 안전한 링크 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용하세요.

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다. 우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> 새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-SafeLinksRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.

구문과 매개 변수에 대한 자세한 내용은 [Set-SafeLinksRule을 참조하십시오.](/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-remove-safe-links-policies"></a>PowerShell을 사용하여 안전한 링크 정책 제거

PowerShell을 사용하여 안전한 링크 정책을 제거하면 해당 안전한 링크 규칙이 제거되지 않습니다.

PowerShell에서 안전한 링크 정책을 제거하려면 다음 구문을 사용하세요.

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

이 예에서는 Marketing Department라는 안전한 링크 정책을 제거합니다.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeLinksPolicy를 참조하십시오.](/powershell/module/exchange/remove-safelinkspolicy)

### <a name="use-powershell-to-remove-safe-links-rules"></a>PowerShell을 사용하여 안전한 링크 규칙 제거

PowerShell을 사용하여 안전한 링크 규칙을 제거하면 해당 안전한 링크 정책이 제거되지 않습니다.

PowerShell에서 안전한 링크 규칙을 제거하려면 다음 구문을 사용하세요.

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

이 예에서는 Marketing Department라는 안전한 링크 규칙을 제거합니다.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeLinksRule을 참조하십시오.](/powershell/module/exchange/remove-safelinksrule)

링크가 금고 검사하는지 확인을 위해 사용 가능한 Microsoft Defender에서 보고서의 Office 365 합니다. 자세한 내용은 Office 365 포털에서 [Defender에](view-reports-for-mdo.md) 대한 보고서 Office 365 [탐색기 Microsoft 365 Defender 참조하세요.](threat-explorer.md)

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

링크 정책이 만들어지거나 수정 또는 제거 금고 다음 단계를 수행하십시오.

- Microsoft 365 Defender 포털에서 정책 & 위협  정책 금고 \>  \> **로 이동하세요.** 정책 목록, 해당 **상태 값** 및 우선 순위 값을 **검증합니다.** 자세한 내용을 확인하려면 목록에서 정책을 선택하고 플라이아웃에서 세부 정보를 하세요.

- PowerShell Exchange Online PowerShell Exchange Online Protection PowerShell에서 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 설정을 \<Name\> 확인합니다.

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
