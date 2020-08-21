---
title: EOP에서 피싱 방지 정책 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online 사서함의 사용 여부에 관계없이 EOP(Exchange Online Protection) 조직에서 사용할 수 있는 피싱 방지 정책을 만들고, 수정하고, 삭제하는 방법에 대해 알아보세요.
ms.openlocfilehash: af6577d32d43300867d29a365baaa4e1e7e1b5e3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825752"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>EOP에서 피싱 방지 정책 구성

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에는 기본적으로 사용하는 제한된 수의 스푸핑 방지 기능을 포함하는 기본 피싱 방지 정책이 있습니다. 자세한 내용은 [피싱 방지 정책의 스푸핑 설정을 참조하십시오.](set-up-anti-phishing-policies.md#spoof-settings)

관리자는 기본 피싱 방지 정책을 보고, 편집하고, 구성할 수 있습니다. 세분성을 크게 위해 사용자 지정 피싱 방지 정책을 만들 수 있습니다. 조직의 특정 사용자, 그룹 또는 도메인에 적용됩니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.

Exchange Online 사서함이 있는 조직은 보안 업데이트 및 준수 센터 또는 Exchange Online PowerShell에서 & 정책을 구성할 수 있습니다. 독립 실행형 EOP 조직은 준수 센터에 있는 보안 및 & 있습니다.

Office 365 ATP(Advanced Threat Protection)에서 사용할 수 있는 고급 ATP 피싱 방지 정책을 만들고 수정하는 방법에 대한 자세한 내용은 [ATP 피싱 방지 정책 구성을 참조하세요.](configure-atp-anti-phishing-policies.md)

피싱 방지 정책의 기본 요소는 다음과 같습니다.

- **피싱 방지 정책:** 사용하거나 사용하지 않도록 설정할 피싱 보호 기능과 옵션을 적용할 작업을 지정합니다.
- **피싱 방지 규칙: 피싱 방지**정책에 대한 우선순위 및 받는 사람 필터(정책이 적용되는 사용자)를 지정합니다.

준수 센터에서 보안 설치 제거 정책을 관리하면, 두 가지 요소의 차이는 & 않습니다.

- 피싱 방지 정책을 만들면 실제로 피싱 방지 규칙과 관련된 피싱 방지 정책이 두 가지 모두 동일한 이름을 사용하여 동시에 생성됩니다.
- 피싱 방지 정책을 수정할 때는 이름, 우선순위, 활성화됨 또는 사용 안 함 및 받는 사람 필터와 관련된 설정이 피싱 방지 규칙을 수정합니다. 다른 모든 설정은 관련 피싱 방지 정책을 수정합니다.
- 피싱 방지 정책을 제거할 경우 피싱 방지 규칙과 관련된 피싱 방지 정책이 제거됩니다.

Exchange Online PowerShell에서 정책과 규칙은 별도로 관리합니다. 자세한 내용은 이 항목 [뒷부분에 나오는 피싱 방지 정책](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 구성을 위한 Exchange Online PowerShell 사용 섹션을 참조하십시오.

모든 조직에는 다음과 같은 속성을 가진 Office365 AntiPhish Default라는 피싱 방지 정책이 기본으로 있습니다.

- 정책에 연결된 피싱 방지 규칙(받는 사람 필터)이 없더라도 조직의 모든 받는 사람에게 정책이 적용됩니다.
- 정책의 사용자 지정 우선순위 값은 **가장 낮음**이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨). 사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.
- 그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.

피싱 방지 보호의 효율성을 높이기 위해 특정 사용자 또는 사용자 그룹에 적용되는 더 강조한 설정을 사용하여 사용자 지정 피싱 방지 정책을 만들 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 피싱 방지 **페이지로 직접 이동하려면 을** 사용합니다. <https://protection.office.com/antiphishing>

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

  독립 실행형 EOP PowerShell에서 피싱 방지 정책을 관리할 수는 없습니다.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 피싱 방지 정책을 추가, 수정 및 삭제하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 피싱 방지 정책에 대한 읽기 전용 액세스에 액세스하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

- 독립 실행형 EOP에서 스팸 방지 정책을 만들고 수정하려면 테넌트에 대한 _하이드레이션이 필요한 작업을_ 수행해야 합니다. 예를 들어 EAC(Exchange 관리 센터)에서 **사용 권한** 탭으로 이동하여 기존 **Edit** 역할 그룹을 선택하고 편집 아이콘을 클릭하고 역할을 제거할 수 ![ ](../../media/ITPro-EAC-EditIcon.png) 있습니다(결국적으로 다시 추가). 테넌트가 하이드 산정되지 않았다면 성공적으로 완료되어야 하는 진행률 표시줄이 있는 **조직** 설정 업데이트라는 대화 상자를 가져옵니다. 하이드레이션에 대한 자세한 내용은 [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet(독립 실행형 EOP PowerShell 또는 보안 센터에서는 사용할 수 없음)을 & 참조하십시오.

- 피싱 방지 정책에 대한 권장 설정은 [EOP 기본 피싱 방지 정책 설정을 참조하십시오.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

- 업데이트된 정책이 적용될 수 있도록 최대 30분 간 허용합니다.

- 필터링 파이프라인에서 피싱 방지 정책을 적용한 위치에 대한 자세한 내용은 [전자 메일 보호의 순서 및 우선 순위를 참조하십시오.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>보안 그룹 & 사용하여 피싱 방지 정책 만들기

보안 센터에서 사용자 지정 피싱 방지 정책을 & 만들면 두 서비스 모두동일한 이름을 사용하여 피싱 방지 규칙과 관련된 피싱 방지 정책이 동시에 생성됩니다.

피싱 방지 정책을 만들 때는 정책이 적용되는 사용자를 식별하는 정책 이름, 설명 및 받는 사람 필터만 지정할 수 있습니다. 정책을 만들고 나면 정책을 수정하여 기본 피싱 방지 설정을 변경하거나 검토할 수 있습니다.

1. 보안 그룹 & 위협 관리 **정책 방지** \> **Policy** \> **정책 방지로 이동합니다.**

2. 피싱 **방지 페이지에서 만들기를** **클릭합니다.**

3. 새 **피싱 방지 정책 만들기 마법사가** 열립니다. 정책 이름 **지정 페이지에서** 다음 설정을 구성합니다.

   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다.

   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

   작업을 마친 후 **다음**을 클릭합니다.

4. 페이지에 **정책이** 적용되는 내부 받는 사람을 식별합니다.

   조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

   조건 **추가를 클릭합니다.** 표시되는 드롭다운 메뉴에서 다음과 같은 경우 적용된 **조건을 선택합니다.**

   - **받는 사람은**: 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.
   - **받는 사람이 조직의 그룹**구성원: 조직에서 하나 이상의 그룹을 지정합니다.
   - **받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.

   조건을 선택하면 해당 드롭다운이 다음 상자 중 **하나와 함께 나타납니다.**

   - 상자를 클릭하고 선택할 값 목록을 따라 스크롤합니다.
   - 상자를 클릭하고 입력하여 목록을 필터링하고 값을 선택합니다.
   - 값을 더 추가하려면 상자에서 빈 영역을 클릭합니다.
   - 개별 항목을 제거하려면 **값에서 제거** ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.
   - 전체 조건을 제거하려면 해당 **조건에서 제거** ![ 아이콘 ](../../media/scc-remove-icon.png) 제거아이콘을 클릭합니다.

   조건을 더 추가하려면 조건 **추가를 클릭하고 적용된** 경우에는 나머지 **값을 선택합니다.**

   예외를 추가하려면 조건 **추가를 클릭하고** 다음의 경우 제외를 **선택합니다.** 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음**을 클릭합니다.

5. **나타나는 설정** 검토 페이지에서 설정을 검토합니다. 각 설정에서 **편집을** 클릭하여 수정할 수 있습니다.

   완료되면 이 정책 **만들기를 클릭합니다.**

6. 확인 **대화** 상자가 나타나면 확인을 클릭합니다.

이러한 일반 정책 설정을 사용하여 피싱 방지 정책을 만들고 나면 다음 섹션의 지침을 사용하여 정책의 보호 설정을 구성합니다.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>보안 프리센터 & 사용하여 피싱 방지 정책 수정하기

다음 절차에 따라 사용자가 만든 새 정책 또는 이미 사용자 지정된 기존 정책과 같은 피싱 방지 정책을 수정합니다.

1. 아직 선택되지 않은 경우 보안 센터를 열어 위협 **Threat management** 관리 & 정책 \> **Policy** \> **방지 정책 방지로 이동합니다.**

2. 수정할 사용자 지정 피싱 방지 정책을 선택합니다. 이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.

3. 정책 ** \<name\> 플라이아웃이** 표시됩니다. 섹션에서 **편집을** 클릭하면 해당 섹션의 설정에 액세스할 수 있습니다.

   - 다음 단계는 섹션이 나타나는 순서대로 나와 있지만 순차적이지는 않습니다(순서와대로 구역을 선택하여 수정가능).

   - 섹션에서 **편집을 클릭하면** 사용 가능한 설정이 마법사 형식으로 제공되지만 원하는 순서로 페이지 내로 이동할 수 있고, **Cancel** 페이지에서 **Close** **저장을** 클릭하거나 취소 또는 닫기 아이콘을 클릭하여 정책 편집 ![ ](../../media/scc-remove-icon.png) **페이지로 돌아갈 수 \<name\> ** 있습니다. 마법사의 마지막 페이지를 방문하거나 저장하거나 나갈 필요는 없습니다.

4. **정책 설정:** **편집을** 클릭하여 이전 섹션에서 정책을 만들 때 사용 [가능한 것과 동일한 설정을](#use-the-security--compliance-center-to-create-anti-phishing-policies) 수정합니다.

   - **이름**
   - **설명**
   - **적용 대상**
   - **설정 검토**

   작업을 마쳤을 때 임의의 **페이지에서 저장을** 클릭합니다.

5. **스푸핑**: **편집을 클릭하여** 스푸핑 인텔리전스를 설정 또는 해제하고, Outlook의 인증되지 않은 발신자 식별을 설정 또는 해제하고, 차단된 스푸핑된 보낸 사람의 메시지에 적용할 작업을 구성합니다. 자세한 내용은 [피싱 방지 정책의 스푸핑 설정을 참조하십시오.](set-up-anti-phishing-policies.md#spoof-settings)

   ATP 피싱 방지 정책에서도 이러한 설정을 사용할 수 있습니다.

   - **스푸핑 필터 설정**: 기본값은 **On이며**이 값을 사용하도록 두는 것이 좋습니다. 이 기능을 끄려면 토글을 꺼서 **끄도록 합니다.** 자세한 내용은 [EOP에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)

     > [!NOTE]
     > MX 레코드가 Microsoft 365를 가리키지 않는 경우 스푸핑 방지 보호를 사용하지 않을 필요가 없습니다. 대신 커넥터에 대한 향상된 필터링을 사용하도록 설정합니다. 자세한 내용은 [Exchange Online에서 커넥터에 대한 향상된 필터링을 참조하세요.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **인증되지 않은 보낸 사람 기능 사용**: 기본값은 **켜기입니다.** 이 기능을 끄려면 토글을 꺼서 **끄도록 합니다.**

   - **작업:** 스푸핑 인텔리전스에 실패한 메시지에 대해 수행할 작업을 지정합니다.

     **도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보내는 경우:**

     - **받는 사람의 정크 메일 폴더로 메시지 이동**
     - **메시지 격리**

   - **설정 검토:** 개별 단계를 클릭하는 대신 설정이 요약에 표시됩니다.

     - 각 섹션에서 **편집을** 클릭하여 관련 페이지로 돌아가볼 수 있습니다.
     - 이 페이지에서 다음 설정을 직접 **설정/해제할** 수 있습니다. **On**

       - **맬웨어 방지 보호 기능 사용**
       - **인증되지 않은 보낸 사람 기능 사용**

   작업을 마쳤을 때 임의의 **페이지에서 저장을** 클릭합니다.

6. 정책 편집 **페이지로 \<Name\> 돌아가** 설정을 검토하고 닫기를 **클릭합니다.**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>보안 정책 & 사용하여 기본 피싱 방지 정책 수정

기본 피싱 방지 정책은 Office365 AntiPhish Default라는 이름으로, 정책 목록에 나타나지 않습니다. 기본 피싱 방지 정책을 수정하려면 다음 단계를 수행합니다.

1. 보안 그룹 & 위협 관리 **정책 방지** \> **Policy** \> **정책 방지로 이동합니다.**

2. 피싱 **방지 페이지에서 기본 정책을** **클릭합니다.**

3. 정책 **편집 Office365 AntiPhish Default 페이지가** 나타납니다. 사용자 지정 정책을 수정할 때와 대조한 설정을 포함하는 다음 [섹션을 사용할 수 있습니다.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)

   - **가장**
   - **스푸핑**
   - **고급 설정**

   기본 정책을 수정할 때는 다음과 같은 설정을 사용할 수 없습니다.

   - 정책 설정 **섹션과 값을** 볼 수 있지만 편집 링크가 없기어도 설정을 수정할 수 없습니다(정책 이름, 설명 및 정책이 적용되는 대상(모든 받는 사람에게 적용됨). **Edit**
   - 기본 정책은 삭제할 수 없습니다.
   - 기본 정책의 우선순위를 변경할 수 없습니다(항상 마지막으로 적용됨).

4. 정책 **Office365 AntiPhish Default 페이지에서 설정을** 검토하고 닫기를 **클릭합니다.**

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>사용자 지정 피싱 방지 정책 사용 또는 사용 안 함

1. 보안 그룹 & 위협 관리 **정책 방지** \> **Policy** \> **정책 방지로 이동합니다.**

2. **상태** 열의 값을 확인합니다.

   - 토글을 끌어 정책을 **사용하지 않도록** 설정합니다.

   - 토글을 밀어 정책을 **사용하도록** 설정합니다.

기본 피싱 방지 정책을 사용하지 않도록 설정할 수 없습니다.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>사용자 지정 피싱 방지 정책의 우선순위 설정하기

기본적으로 만들어진 순서에 따라 우선순위가 지정됩니다(새 정책은 이전 정책보다 우선순위가 낮음). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.

사용자 지정 피싱 방지 정책은 처리되는 순서로 표시됩니다(첫 번째 정책에는 **우선** 순위 값 0이 포함됨). Office365 AntiPhish 기본값이라는 기본 피싱 방지 정책은 사용자 지정 우선순위 **값이 가장 낮음이며**변경할 수 없습니다.

 **참고**: 보안 & 센터에서, 만들고 나서 피싱 방지 정책의 우선순위만 변경할 수 있습니다. PowerShell에서 피싱 방지 규칙(기존 규칙의 우선순위에 영향을 줄 수 있는)을 만들 때 기본 우선순위를 재정의할 수 있습니다.

정책의 우선 순위를 변경하려면 **정책** 속성에서 **Decrease priority** 우선 순위 높이기 또는 우선 순위를 높입니다. (Security & Compliance Center에서 우선 순위 **번호를** 직접 수정할 수는 없습니다). 여러 정책을 포함한 경우에만 정책 우선순위를 변경하는 것이 좋습니다.

1. 보안 감사 & 센터에서 위협 **관리** \> **정책** \> **ATP 피싱 방지로 이동합니다.**

2. 수정할 정책을 선택합니다. 이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.

3. 정책 ** \<name\> 플라이아웃이** 표시됩니다.

   - 우선순위 값이 **0인** 사용자 지정 피싱 방지 **정책에는** 사용 가능한 **우선 순위 하이버스 단추만** 있습니다.

   - 우선순위 값이 가장 낮은 사용자 지정 피싱 방지 정책(예: **Priority** **3)에는**우선 순위 **높이 버튼만 사용할** 수 있습니다.

   - 사용자 지정 피싱 방지 정책이 세 개 이상 있는 경우 우선순위 값이 가장 높은 값과 가장 낮은 우선순위 값 사이의 정책은 모두 **사용할** 수 있는 우선 순위와 우선 순위 **낮게 지정** 단추를 모두 사용합니다.

4. Click **Increase priority** or **Decrease priority** to change the **Priority** value.

5. 작업을 마쳤으면 **닫기**를 클릭합니다.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>보안 & 준수 센터를 사용하여 피싱 방지 정책 보기

1. 보안 그룹 & 준수 센터에서 위협 **관리** \> **Policy** \> **정책 방지 정책 방지로 이동합니다.**

2. 다음 단계 중 하나를 수행합니다.

   - 보거나 는 사용자 지정 피싱 방지 정책을 선택합니다. 이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.

   - 기본 **정책을** 클릭하여 기본 피싱 방지 정책을 확인합니다.

3. 정책 ** \<name\> 플라이아웃이** 나타나면, 설정 및 값을 볼 수 있습니다.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Security & 센터를 사용하여 피싱 방지 정책 제거

1. 보안 그룹 & 위협 관리 **정책 방지** \> **Policy** \> **정책 방지로 이동합니다.**

2. 제거할 정책을 선택합니다. 이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.

3. 표시되는 **정책 \<name\> 플라이아웃** 편집에서 **정책 삭제를**클릭한 후 나타나는 경고 대화 상자에서 예를 클릭합니다. **Yes**

기본 정책은 제거할 수 없습니다.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Exchange Online PowerShell을 사용하여 피싱 방지 정책 구성

앞에서 설명한 것과 같이 스팸 방지 정책은 피싱 방지 정책과 피싱 방지 규칙으로 구성됩니다.

Exchange Online PowerShell에서 피싱 방지 정책과 피싱 방지 규칙의 차이는 명백합니다. ** \* -AntiPhishPolicy** cmdlet을 사용하여 피싱 방지 정책을 관리하고, ** \* -AntiPhishRule** cmdlet을 사용하여 피싱 방지 규칙을 관리합니다.

- PowerShell에서 먼저 피싱 방지 정책을 만들고 해당 규칙이 적용되는 정책을 식별하는 피싱 방지 규칙을 만듭니다.
- PowerShell에서는 피싱 방지 정책및 피싱 방지 규칙의 설정을 개별적으로 수정합니다.
- PowerShell에서 피싱 방지 정책을 제거하면 해당피어 제거 규칙은 자동으로 제거되지 않거나, 전또한 경우에 따라 제거됩니다.

> [!NOTE]
> 다음의 PowerShell 절차는 Exchange Online Protection PowerShell을 사용하는 독립 실행형 EOP 조직에서는 사용할 수 없습니다.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell을 사용하여 피싱 방지 정책 만들기

PowerShell에서 피싱 방지 정책을 만드는 두 단계 과정은 다음 두 단계로 구성됩니다.

1. 피싱 방지 정책을 만듭니다.
2. 규칙이 적용되는 피싱 방지 정책을 지정하는 피싱 방지 규칙을 만듭니다.

 **참고:**

- 새로운 피싱 방지 규칙을 만들고 연결되지 않은 기존의 피싱 방지 정책을 할당할 수 있습니다. 피싱 방지 규칙은 두 개 이상의 피싱 방지 정책과 연결될 수 없습니다.

- 정책을 만들 때까지 보안 & 준수 센터에서 사용할 수 없는 PowerShell의 새 피싱 방지 정책에 대해 다음 설정을 구성할 수 있습니다.

  - 새 정책을 만듭니다(New-AntiPhishRule_Enabled_ `$false` **cmdlet에서 사용 안** 함).
  - _Priority_ _\<Number\>_ **New-AntiPhishRule** cmdlet에서 생성하는 동안 정책 우선순위를 설정합니다(우선 순위).

- 피싱 방지 규칙에 정책을 할당할 때까지 PowerShell에서 만든 피싱 방지 정책은 보안 & 준수 센터에 표시되지 않습니다.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>1단계: PowerShell을 사용하여 피싱 방지 정책 만들기

피싱 방지 정책을 만들려면 다음 구문을 사용하세요.

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

이 예에서는 다음 설정을 사용하여 Research Quarantine이라는 피싱 방지 정책을 만듭니다.

- 정책이 사용하도록 설정되었습니다(Enabled 매개 변수를 _사용하지 않지만_ 기본값은 다음과 같음). `$true`
- 설명에: 리서치 부서 정책이 사용됩니다.
- 스푸핑을 위한 기본 동작을 격리로 변경합니다.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>2단계: PowerShell을 사용하여 피싱 방지 규칙 만들기

피싱 방지 규칙을 만들려면 다음 구문을 사용하세요.

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

이 예에서는 다음 조건에 따라 Research Department라는 피싱 방지 규칙을 만듭니다.

- 이 규칙은 Research Quarantine이라는 피싱 방지 정책과 연결됩니다.
- 이 규칙은 Research Department 그룹의 구성원에게 적용됩니다.
- Priority 매개 변수를 사용하지 않는 _기기에_ 기본 우선 순위가 사용됩니다.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell을 사용하여 피싱 방지 정책 보기

기존의 피싱 방지 정책을 확인하려면 다음 구문을 사용합니다.

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예에서는 지정된 속성과 함께 모든 피싱 방지 정책의 요약 목록을 반환합니다.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

이 예에서는 Executives라는 피싱 방지 정책에 대한 모든 속성 값을 반환합니다.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell을 사용하여 피싱 방지 규칙 보기

기존의 피싱 방지 규칙을 확인하려면 다음 구문을 사용합니다.

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예에서는 지정한 속성과 함께 모든 피싱 방지 규칙의 요약 목록을 반환합니다.

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

이 예에서는 Contoso Executives라는 피싱 방지 규칙에 대한 모든 속성 값을 반환합니다.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell을 사용하여 피싱 방지 정책 수정

다음과 같은 항목 외에 PowerShell에서 피싱 방지 정책을 수정할 때 이 항목 앞부분에 있는 [피싱](#step-1-use-powershell-to-create-an-anti-phish-policy) 방지 정책 섹션을 만들 때 같은 설정을 사용할 수 있습니다.

- _지정된 정책을_ 기본 정책으로 바라내는 MakeDefault 스위치(모든 사용자에게 적용, 항상 우선 순위가 가장 **낮은** 스위치, 삭제할 수 없음)는 PowerShell에서 피싱 방지 정책을 수정할 때만 사용할 수 있습니다.

- 피싱 방지 정책의 이름을 바일 수 **없습니다(Set-AntiPhishPolicy cmdlet에** Name 매개 _변수가_ 없음). 보안 서비스 준수 센터에서 피싱 방지 정책의 이름을 & 바는 경우 피싱 방지 규칙의 이름만 _변경됩니다._

피싱 방지 정책을 수정하려면 다음 구문을 사용합니다.

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell을 사용하여 피싱 방지 규칙 수정

PowerShell에서 피싱 방지 규칙을 수정할 때 사용할 수 없는 유일한 _설정은 사용 안_ 함 규칙을 만들 수 있는 사용 안 함 매개 변수입니다. 기존의 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.

그렇지 않으면 PowerShell에서 피싱 방지 규칙을 수정할 때 추가 설정을 사용할 수 없습니다. [2단계: PowerShell을](#step-2-use-powershell-to-create-an-anti-phish-rule) 사용하여 이 항목 앞부분의 피싱 방지 규칙 섹션에 설명된 것과 같이 규칙을 만들 때도 동일한 설정을 사용할 수 있습니다.

피싱 방지 규칙을 수정하려면 다음 구문을 사용합니다.

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell을 사용하여 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정

PowerShell에서 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정하면 전체 피싱 방지 정책(피싱 방지 규칙 및 할당된 피싱 방지 정책)을 사용하거나 사용하지 않도록 설정합니다. 기본 피싱 방지 정책을 사용하거나 사용하지 않도록 설정할 수 없습니다(모든 받는 사람에게 항상 적용됨).

PowerShell에서 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

다음은 Marketing Department라는 피싱 방지 규칙을 사용하지 않도록 설정하는 예제입니다.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Enable-AntiPhishRule 및](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) [Disable-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell을 사용하여 피싱 방지 규칙의 우선 순위 설정하기

규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다. 설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다. 예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다. 기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다. 예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.

PowerShell에서 피싱 방지 규칙의 우선순위를 설정하려면 다음 구문을 사용합니다.

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다. 우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**참고:**

- 새 규칙을 만들 때 새 규칙의 우선 순위를 설정하려면 **New-AntiPhishRule** cmdlet의 _Priority_ 매개 변수를 대신 사용하세요.

- 기본 피싱 방지 정책에는 해당하는 피싱 방지 규칙이 없고 항상 수정할 수 없는 우선순위 값이 **가장 낮습니다.**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell을 사용하여 피싱 방지 정책 제거하기

PowerShell을 사용하여 피싱 방지 정책을 제거할 때 해당 피싱 방지 규칙은 제거되지 않습니다.

PowerShell에서 피싱 방지 정책을 제거하려면 다음 구문을 사용하세요.

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

이 예에서는 Marketing Department라는 피싱 방지 정책을 제거합니다.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell을 사용하여 피싱 방지 규칙 제거

PowerShell을 사용하여 피싱 방지 규칙을 제거할 때 해당 피싱 방지 정책은 제거되지 않습니다.

PowerShell에서 피싱 방지 규칙을 제거하려면 다음 구문을 사용하세요.

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

이 예에서는 Marketing Department라는 피싱 방지 규칙을 제거합니다.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

ATP 피싱 방지 정책을 성공적으로 구성되었는지 확인하려면 다음 단계를 수행하십시오.

- 보안 그룹 & 위협 관리 **정책 방지** \> **Policy** \> **정책 방지로 이동합니다.** 정책, 상태 값 및 **우선** 순위 값 목록을 **확인합니다.** 자세한 내용을 보려면 다음 단계 중 하나를 수행합니다.

  - 목록에서 정책을 선택하 고 플라이아웃에서 세부 정보를 확인 합니다.
  - 기본 **정책을 클릭하고** 플라이아웃에서 세부 정보를 확인합니다.

- Exchange Online PowerShell에서 정책 \<Name\> 또는 규칙의 이름으로 바꾸고, 다음 명령을 실행하여 설정을 확인합니다.

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
