---
title: EOP에서 피싱 방지 정책 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 exchange Online 사서함을 포함 하거나 제외 하는 EOP (Exchange Online Protection) 조직에서 사용할 수 있는 피싱 방지 정책을 만들고, 수정 하 고, 삭제 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: b6b95515ad44a65dbdd8a7516d8e6c8b2a386450
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726779"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>EOP에서 피싱 방지 정책 구성

Exchange online 사서함이 없는 Microsoft 365 조직에서 사서함이 EOP (exchange online Protection) 조직의 경우 기본적으로 사용 하도록 설정 되어 있는 제한 된 수의 스푸핑 방지 기능을 포함 하는 기본 피싱 방지 정책이 있습니다. 자세한 내용은 [피싱 방지 정책에서 스푸핑 설정을](set-up-anti-phishing-policies.md#spoof-settings)참조 하십시오.

관리자는 기본 피싱 방지 정책을 보고 편집 하 고 구성할 수 있습니다 (삭제 하지 않음). 세분성을 높이기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용 되는 사용자 지정 피싱 방지 정책을 만들 수도 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.

Exchange Online 사서함이 있는 조직은 보안 & 준수 센터 또는 Exchange Online PowerShell에서 피싱 방지 정책을 구성할 수 있습니다. 독립 실행형 EOP 조직은 보안 & 준수 센터만 사용할 수 있습니다.

Office 365 Advanced Threat Protection (Office 365 ATP)에서 사용할 수 있는 고급 ATP 피싱 방지 정책을 만들고 수정 하는 방법에 대 한 자세한 내용은 [ATP 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하십시오.

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a>보안 & 준수 센터 vs PowerShell의 피싱 방지 정책

피싱 방지 정책의 기본 요소는 다음과 같습니다.

- **피싱 정책**: 사용 하거나 사용 하지 않도록 설정할 피싱 보호를 지정 하 고 옵션을 적용 하는 작업입니다.

- **피싱 규칙**: 피싱 정책에 대해 정책이 적용 되는 우선 순위 및 받는 사람 필터를 지정 합니다.

보안 & 준수 센터에서 피싱 방지 정책을 관리할 때는 이러한 두 가지 요소 간의 차이가 명확 하지 않습니다.

- 보안 & 준수 센터에서 피싱 방지 정책을 만드는 경우 실제로는 피싱 규칙과 연결 된 피싱 정책을 모두 같은 이름을 사용 하 여 동시에 만드는 것입니다.

- 보안 & 준수 센터에서 피싱 방지 정책을 수정 하는 경우 이름, 우선 순위, 사용/사용 안 함 및 받는 사람 필터와 관련 된 설정이 피싱 규칙을 수정 합니다. 다른 모든 설정은 연결 된 피싱 정책을 수정 합니다.

- 보안 & 준수 센터에서 피싱 방지 정책을 제거 하면 피싱 규칙과 연결 된 피싱 정책이 모두 제거 됩니다.

Exchange Online PowerShell에서 피싱 정책 및 피싱 규칙 간의 차이가 명백 합니다. ** \* -AntiPhishPolicy** cmdlet을 사용 하 여 피싱 정책을 관리 하 고 ** \* -AntiPhishRule** cmdlet을 사용 하 여 피싱 규칙을 관리 합니다.

- PowerShell에서는 먼저 피싱 정책을 만든 다음 규칙이 적용 되는 정책을 식별 하는 피싱 규칙을 만듭니다.

- PowerShell에서는 피싱 정책의 설정과 피싱 규칙을 각각 수정 합니다.

### <a name="default-atp-anti-phishing-policy"></a>기본 ATP 피싱 방지 정책

모든 조직에는 다음과 같은 속성이 포함 된 Office365 AntiPhish Default 라는 피싱 방지 정책이 내장 되어 있습니다.

- 정책과 연결 된 피싱 규칙 (받는 사람 필터)이 없는 경우에도 Office365 AntiPhish Default 라는 정책이 조직의 모든 받는 사람에 게 적용 됩니다.

- Office365 AntiPhish Default 정책에는 수정할 수 없는 사용자 지정 우선 순위 값이 **가장 낮습니다** (정책이 항상 마지막으로 적용 됨)이 있습니다. 만드는 모든 사용자 지정 정책에는 항상 Office365 AntiPhish Default 라는 정책 보다 높은 우선 순위가 부여 됩니다.

- Office365 AntiPhish Default 라는 정책이 기본 정책 ( **IsDefault** 속성에 값이 있음 `True` ) 이며 기본 정책을 삭제할 수 없습니다.

피싱 방지 보호 기능의 효율성을 높이려면 특정 사용자 또는 사용자 그룹에 적용 되는 보다 엄격한 설정을 사용 하 여 사용자 지정 피싱 방지 정책을 만들 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다. **피싱 방지** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/antiphishing> 합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

  독립 실행형 EOP PowerShell에서 피싱 방지 정책을 관리할 수는 없습니다.

- 이 항목의 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다.

  - 피싱 방지 정책을 추가, 수정 및 삭제 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

    - [보안 & 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 또는 **바이러스 관리**

  - 피싱 방지 정책에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

    - 보안 [& 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 독자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 입니다.

- 독립 실행형 EOP에서 스팸 방지 정책을 만들고 수정 하려면 테 넌 트에 대해 _하이드레이션_ 이 필요한 작업을 수행 해야 합니다. 예를 들어 EAC (Exchange 관리 센터)에서 **사용 권한** 탭으로 이동 하 고 기존 역할 그룹을 선택 하 **Edit** ![ 고 편집 아이콘 편집을 클릭 하 ](../../media/ITPro-EAC-EditIcon.png) 고, 궁극적으로 다시 추가할 역할을 제거할 수 있습니다. 테 넌 트가 hydrated 되지 않은 경우 진행률 표시줄과 함께 완료 되는 **조직 설정 업데이트** 라는 대화 상자가 표시 됩니다. 하이드레이션에 대 한 자세한 내용은 독립 실행형 EOP PowerShell 또는 보안 & 준수 센터에서 사용할 수 없는 [OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet을 참조 하십시오.

- 피싱 방지 정책에 대 한 권장 설정에 대 한 자세한 내용은 [EOP 기본 피싱 방지 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)참조 하십시오.

- 업데이트 된 정책을 적용할 최대 30 분을 허용 합니다.

- 필터링 파이프라인에서 피싱 방지 정책이 적용 되는 위치에 대 한 자세한 내용은 [전자 메일 보호의 주문 및 우선 순위](how-policies-and-protections-are-combined.md)를 참조 하세요.

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>보안 & 준수 센터를 사용 하 여 피싱 방지 정책 만들기

보안 & 준수 센터에서 사용자 지정 피싱 방지 정책을 만들면 두 가지 모두에 동일한 이름을 사용 하 여 피싱 규칙과 연결 된 피싱 정책이 동시에 만들어집니다.

피싱 방지 정책을 만들 때 정책 이름, 설명 및 정책이 적용 되는 사람을 식별 하는 받는 사람 필터를 지정할 수만 있습니다. 정책을 만든 후에 정책을 수정 하 여 기본 피싱 방지 설정을 변경 하거나 검토할 수 있습니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **피싱 방지**로 이동 합니다.

2. **피싱 방지** 페이지에서 **만들기**를 클릭 합니다.

3. **새 피싱 방지 정책 만들기** 마법사가 열립니다. **정책 이름** 설정 페이지에서 다음 설정을 구성 합니다.

   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다.

   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

   작업을 마친 후 **다음**을 클릭합니다.

4. **적용 대상** 페이지에서 정책이 적용 되는 내부 받는 사람을 식별 합니다.

   조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

   **조건 추가를**클릭 합니다. 표시 되는 드롭다운 목록에서 다음의 **경우 적용**아래의 조건을 선택 합니다.

   - **받는 사람**: 조직의 사서함, 메일 사용자 또는 메일 연락처를 하나 이상 지정 합니다.
   - **받는 사람이 다음 구성원 인**경우: 조직에서 그룹을 하나 이상 지정 합니다.
   - **받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.

   조건을 선택한 후에는 **이러한 상자 중 하나** 에 해당 하는 dropdown이 표시 됩니다.

   - 상자를 클릭 하 고 선택할 값 목록을 스크롤합니다.
   - 상자를 클릭 하 고 입력을 시작 하 여 목록을 필터링 하 고 값을 선택 합니다.
   - 값을 더 추가 하려면 상자에서 빈 영역을 클릭 합니다.
   - 개별 항목을 제거 하려면 값에서 제거 아이콘 **제거** 를 클릭 ![ ](../../media/scc-remove-icon.png) 합니다.
   - 전체 조건을 제거 하려면 **Remove** ![ 조건에서 제거 아이콘 제거를 클릭 ](../../media/scc-remove-icon.png) 합니다.

   조건을 더 추가 하려면 **조건 추가** 를 클릭 하 고 **적용 된 경우**에는 나머지 값을 선택 합니다.

   예외를 추가 하려면 **조건 추가** 를 클릭 하 고 다음의 **경우 제외**에서 예외를 선택 합니다. 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음**을 클릭합니다.

5. **설정 검토** 페이지가 나타나면 설정을 검토 합니다. 각 설정에 대해 **편집** 을 클릭 하 여 수정할 수 있습니다.

   작업이 완료 되 면 **이 정책 만들기**를 클릭 합니다.

6. 나타나는 확인 대화 상자에서 **확인을** 클릭 합니다.

이러한 일반 정책 설정을 사용 하 여 피싱 방지 정책을 만든 후에는 다음 섹션의 지침을 사용 하 여 정책에서 보호 설정을 구성 합니다.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>보안 & 준수 센터를 사용 하 여 피싱 방지 정책 수정

다음 절차에 따라 새로 만든 정책 또는 이미 사용자 지정 했던 기존 정책을 사용 하 여 피싱 방지 정책을 수정 합니다.

1. 아직 없는 경우 보안 & 준수 센터를 열고 **위협 관리** \> **정책** \> **피싱 방지**로 이동 합니다.

2. 수정 하려는 사용자 지정 피싱 방지 정책을 선택 합니다. 이미 선택 되어 있으면 선택을 취소 하 고 다시 선택 합니다.

3. 정책 플라이 아웃 ** \<name\> 편집** 이 표시 됩니다. 섹션에서 **편집** 을 클릭 하면 해당 섹션의 설정에 액세스할 수 있습니다.

   - 다음 단계는 섹션에 표시 되는 순서 대로 제공 되지만 순서에 관계 없이 섹션을 선택 하 고 수정할 수 있습니다.

   - 섹션에서 **편집** 을 클릭 하면 사용 가능한 설정이 마법사 형식으로 제공 되지만 페이지 **내에서 언제** 든 지 페이지를 이동할 수 있습니다. **또는** 닫기 아이콘을 클릭 하 여 **Close** ![ ](../../media/scc-remove-icon.png) ** \<name\> 정책 편집** 페이지로 돌아갈 수 있습니다 (마법사의 마지막 페이지를 방문 하 여 저장 하거나 나갈 필요가 없음).

4. **정책 설정**: 이전 섹션에서 [정책을 만들](#use-the-security--compliance-center-to-create-anti-phishing-policies) 때 사용 가능한 것과 동일한 설정을 수정 하려면 **편집** 을 클릭 합니다.

   - **이름**
   - **설명**
   - **적용 대상**
   - **설정 검토**

   작업이 끝나면 모든 페이지에서 **저장** 을 클릭 합니다.

5. **스푸핑**: **편집** 을 클릭 하 여 스푸핑 인텔리전스를 설정 하거나 해제 하 고, Outlook에서 인증 되지 않은 보낸 사람 id를 설정/해제 하 고, 차단 된 스푸핑된 보낸 사람 으로부터 메시지에 적용할 작업을 구성 합니다. 자세한 내용은 [피싱 방지 정책에서 스푸핑 설정을](set-up-anti-phishing-policies.md#spoof-settings)참조 하십시오.

   이러한 동일한 설정은 ATP 피싱 방지 정책 에서도 사용할 수 있습니다.

   - **스푸핑 필터 설정**: 기본값은 **on**이며,이 값을 유지 하는 것이 좋습니다. 해제 하려면 **토글을 끕니다.** 자세한 내용은 [Configure 스푸핑이 intelligence IN EOP](learn-about-spoof-intelligence.md)을 참조 하십시오.

     > [!NOTE]
     > MX 레코드가 Microsoft 365를 가리키지 않는 경우 스푸핑 방지 보호를 사용 하지 않도록 설정할 필요가 없습니다. 대신 커넥터에 대 한 향상 된 필터링을 사용 하도록 설정 합니다. 자세한 내용은 [Exchange Online의 커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)을 참조 하십시오.

   - **인증 되지 않은 보낸 사람 기능 사용**: 기본값은 **On**입니다. 해제 하려면 **토글을 끕니다.**

   - **작업**: 스푸핑 인텔리전스에 실패 한 메시지에 대해 수행할 작업을 지정 합니다.

     **도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보낸 경우**:

     - **받는 사람의 정크 메일 폴더로 메시지 이동**
     - **메시지 격리**

   - **설정 검토**: 각 개별 단계를 클릭 하지 않고 설정이 요약으로 표시 됩니다.

     - 각 섹션에서 **편집** 을 클릭 하 여 관련 페이지로 다시 이동할 수 있습니다.
     - 이 **페이지에서 다음** 설정을 직접 설정 하거나 **해제할** 수 있습니다.

       - **스푸핑 방지 보호 사용**
       - **인증 되지 않은 보낸 사람 기능 사용**

   작업이 끝나면 모든 페이지에서 **저장** 을 클릭 합니다.

6. ** \<Name\> 정책 편집** 페이지에서 설정을 검토 하 고 **닫기를**클릭 합니다.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>보안 & 준수 센터를 사용 하 여 기본 피싱 방지 정책 수정

기본 피싱 방지 정책은 Office365 AntiPhish Default로 이름이 지정 되며 정책 목록에 표시 되지 않습니다. 기본 피싱 방지 정책을 수정 하려면 다음 단계를 수행 합니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **피싱 방지**로 이동 합니다.

2. **피싱 방지** 페이지에서 **기본 정책을**클릭 합니다.

3. **정책 편집 Office365 AntiPhish 기본값** 페이지가 나타납니다. [사용자 지정 정책을 수정할](#use-the-security--compliance-center-to-modify-anti-phishing-policies)때의 동일한 설정이 포함 된 다음 섹션을 사용할 수 있습니다.

   - **가장**
   - **신분을**
   - **고급 설정**

   기본 정책을 수정 하는 경우에는 다음 설정을 사용할 수 없습니다.

   - **정책 설정** 섹션 및 값을 볼 수는 있지만 **편집** 링크는 없는 경우에는 설정 (정책 이름, 설명 및 정책을 적용 하는 사람 (모든 받는 사람에 게 적용)을 수정할 수 없습니다.
   - 기본 정책은 삭제할 수 없습니다.
   - 기본 정책의 우선 순위를 변경할 수는 없습니다 (항상 마지막으로 적용 됨).

4. **Policy Office365 AntiPhish 기본값 편집** 페이지에서 설정을 검토 하 고 **닫기를**클릭 합니다.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>사용자 지정 피싱 방지 정책 사용 또는 사용 안 함

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **피싱 방지**로 이동 합니다.

2. **상태** 열에서 다음 값을 확인 합니다.

   - 정책을 사용 하지 않도록 설정 하려면이 설정을 **해제** 로 이동 합니다.

   - 정책을 **사용 하려면 토글을 설정으로 이동** 합니다.

기본 피싱 방지 정책을 사용 하지 않도록 설정할 수 없습니다.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>사용자 지정 피싱 방지 정책의 우선 순위 설정

기본적으로 피싱 방지 정책에는 만든 순서를 기준으로 하는 우선 순위가 지정 됩니다 (최신 정책은 이전 정책 보다 낮은 우선 순위입니다). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위가 같을 수 없습니다.

사용자 지정 피싱 방지 정책은 처리 되는 순서 대로 표시 됩니다 (첫 번째 정책의 **우선 순위** 값은 0). Office365 AntiPhish Default 라는 기본 피싱 방지 정책은 사용자 지정 우선 순위 값이 **가장 낮은**반면,이를 변경할 수는 없습니다.

 **참고**: 보안 & 준수 센터에서는 피싱 방지 정책의 우선 순위를 만든 후에만 변경할 수 있습니다. PowerShell에서는 기존 규칙의 우선 순위에 영향을 줄 수 있는 피싱 규칙을 만들 때 기본 우선 순위를 재정의할 수 있습니다.

정책의 우선 순위를 변경 하려면 정책의 속성에서 우선 **순위 높임** 또는 **우선 순위 낮추기** (보안 & 준수 센터에서 직접 **우선 순위** 번호를 수정할 수 없음)을 클릭 합니다. 정책 우선 순위를 변경 하는 것은 정책이 여러 개인 경우에만 의미가 있습니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 피싱 방지**로 이동 합니다.

2. 수정 하려는 정책을 선택 합니다. 이미 선택 되어 있으면 선택을 취소 하 고 다시 선택 합니다.

3. 정책 플라이 아웃 ** \<name\> 편집** 이 표시 됩니다.

   - **우선 순위** 값이 **0** 인 사용자 지정 피싱 방지 정책에는 **우선 순위 낮추기** 단추만 사용할 수 있습니다.

   - **우선 순위** 값이 가장 낮은 사용자 지정 피싱 방지 정책 (예: **3**)에는 **우선 순위 향상** 단추만 사용할 수 있습니다.

   - 사용자 지정 피싱 방지 정책이 3 개 이상 있는 경우 가장 높거나 낮은 우선 순위 값 사이의 정책에는 **우선 순위 증가** 와 **우선 순위 낮추기** 단추가 모두 있습니다.

4. 우선 **순위 높임** 또는 **우선 순위 낮추기** 를 클릭 하 여 **우선 순위** 값을 변경 합니다.

5. 작업을 마쳤으면 **닫기**를 클릭합니다.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>보안 & 준수 센터를 사용 하 여 피싱 방지 정책 보기

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **피싱 방지**로 이동 합니다.

2. 다음 단계 중 하나를 수행 합니다.

   - 보려는 사용자 지정 피싱 방지 정책을 선택 합니다. 이미 선택 되어 있으면 선택을 취소 하 고 다시 선택 합니다.

   - 기본 **정책을** 클릭 하 여 기본 피싱 방지 정책을 확인 합니다.

3. 설정 및 값을 볼 수 있는 **정책 \<name\> ** 플라이 아웃 편집이 표시 됩니다.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>보안 & 준수 센터를 사용 하 여 피싱 방지 정책 제거

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **피싱 방지**로 이동 합니다.

2. 제거할 정책을 선택 합니다. 이미 선택 되어 있으면 선택을 취소 하 고 다시 선택 합니다.

3. 표시 되는 **정책 \<name\> ** 플라이 아웃 편집에서 **정책 삭제**를 클릭 한 다음 표시 되는 경고 대화 상자에서 **예** 를 클릭 합니다.

기본 정책은 제거할 수 없습니다.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Exchange Online PowerShell을 사용 하 여 피싱 방지 정책 구성

독립 실행형 EOP 조직에서는 다음 절차를 사용할 수 없습니다.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell을 사용 하 여 피싱 방지 정책 만들기

PowerShell에서 피싱 방지 정책을 만드는 과정은 다음 두 단계로 진행 됩니다.

1. 피싱 정책을 만듭니다.

2. 규칙이 적용 되는 피싱 정책을 지정 하는 피싱 규칙을 만듭니다.

 **참고:**

- 새 피싱 규칙을 만들고 연결 되지 않은 기존 피싱 정책을 할당할 수 있습니다. 피싱 규칙을 두 개 이상의 피싱 정책에 연결할 수 없습니다.

- 정책을 만든 후에 야 보안 & 준수 센터에서 사용할 수 없는 PowerShell의 새 피싱 정책에서 다음 설정을 구성할 수 있습니다.

  - AntiPhishRule cmdlet에서_사용 하도록 설정_ 된 새 정책을 사용 하지 않도록 설정 `$false` **New-AntiPhishRule** 합니다.

  - AntiPhishRule cmdlet에 대 한 생성 (_우선 순위_ ) 중에 정책의 우선 순위를 설정 _\<Number\>_ 합니다. **New-AntiPhishRule**

- 피싱 규칙에 정책을 할당 하기 전 까지는 PowerShell에서 만드는 새로운 피싱 정책이 보안 & 준수 센터에 표시 되지 않습니다.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>1 단계: PowerShell을 사용 하 여 피싱 정책 만들기

피싱 정책을 만들려면 다음 구문을 사용 합니다.

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

이 예에서는 다음 설정을 사용 하 여 Research Quarantine 라는 피싱 정책을 만듭니다.

- 정책이 사용 하도록 설정 되어 있습니다 ( _enabled_ 매개 변수를 사용 하지 않으며 기본값은 `$true` ).
- 설명은 부서 정책 연구입니다.
- 격리로 위장 하기 위한 기본 작업을 변경 합니다.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)를 참조 하십시오.

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>2 단계: PowerShell을 사용 하 여 피싱 규칙 만들기

피싱 규칙을 만들려면 다음 구문을 사용 합니다.

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

이 예에서는 다음 조건을 사용 하 여 Research 학과 라는 피싱 규칙을 만듭니다.

- 이 규칙은 조사 검역 이라는 피싱 정책에 연결 됩니다.
- 이 규칙은 Research Department 그룹의 구성원에게 적용됩니다.
- _Priority_ 매개 변수를 사용 하지 않으므로 기본 우선 순위가 사용 됩니다.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)를 참조 하십시오.

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell을 사용 하 여 피싱 정책 보기

기존 피싱 정책을 보려면 다음 구문을 사용 합니다.

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예제에서는 지정 된 속성과 함께 모든 피싱 정책의 요약 목록을 반환 합니다.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

이 예제에서는 중역 이라는 피싱 정책에 대 한 모든 속성 값을 반환 합니다.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)를 참조 하십시오.

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell을 사용 하 여 피싱 규칙 보기

기존 피싱 규칙을 보려면 다음 구문을 사용 합니다.

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예제에서는 지정 된 속성과 함께 모든 피싱 규칙의 요약 목록을 반환 합니다.

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

이 예에서는 Contoso 임원 이라는 피싱 규칙에 대 한 모든 속성 값을 반환 합니다.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)를 참조 하십시오.

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell을 사용 하 여 피싱 정책 수정

다음 항목을 제외 하 고는이 항목 앞부분에 있는 [1 단계: powershell을 사용 하 여 피싱 정책 만들기](#step-1-use-powershell-to-create-an-anti-phish-policy) 섹션에 설명 된 대로, powershell을 만들 때 피싱 정책을 수정할 때도 같은 설정을 사용할 수 있습니다.

- 지정 된 정책을 기본 정책으로 설정 하는 _makedefault_ 스위치 (모든 사용자에 게 적용 되며 항상 **가장 낮은** 우선 순위 이며 삭제할 수 없음)는 PowerShell에서 피싱 정책을 수정 하는 경우에만 사용할 수 있습니다.

- 피싱 정책의 이름을 바꿀 수는 없습니다 (AntiPhishPolicy cmdlet은 _Name_ 매개 변수를 **사용** 하지 않음). 보안 & 준수 센터에서 피싱 방지 정책의 이름을 바꾸면 피싱 _규칙_의 이름도 변경 됩니다.

피싱 정책을 수정 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

구문 및 매개 변수에 대 한 자세한 내용은 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)를 참조 하십시오.

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell을 사용 하 여 피싱 규칙 수정

PowerShell에서 피싱 규칙을 수정할 때 사용할 수 없는 설정은 사용 하지 않도록 설정 된 규칙을 만들 수 있는 _사용_ 가능한 매개 변수입니다. 기존 피싱 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 섹션을 참고 하십시오.

그렇지 않으면 PowerShell에서 피싱 규칙을 수정할 때 추가 설정을 사용할 수 없습니다. 이 항목 앞부분에 있는 [2 단계: PowerShell을 사용 하 여 피싱 규칙 만들기](#step-2-use-powershell-to-create-an-anti-phish-rule) 섹션에 설명 된 대로 규칙을 만들 때도 같은 설정을 사용할 수 있습니다.

피싱 규칙을 수정 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

구문 및 매개 변수에 대 한 자세한 내용은 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)를 참조 하십시오.

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell을 사용 하 여 피싱 규칙을 사용 하거나 사용 하지 않도록 설정

PowerShell에서 피싱 규칙을 사용 하거나 사용 하지 않도록 설정 하면 전체 피싱 방지 정책 (피싱 규칙 및 할당 된 피싱 정책)을 사용 하거나 사용 하지 않도록 설정 됩니다. 기본 피싱 방지 정책을 사용 하거나 사용 하지 않도록 설정할 수는 없습니다 (항상 모든 받는 사람에 게 적용 됨).

PowerShell에서 피싱 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 구문을 사용 합니다.

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

이 예에서는 Marketing 부서 라는 피싱 규칙을 사용 하지 않도록 설정 합니다.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

구문 및 매개 변수에 대 한 자세한 내용은 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) 및 [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)을 참조 하십시오.

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell을 사용 하 여 피싱 규칙의 우선 순위 설정

규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다. 설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다. 예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다. 기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다. 예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.

PowerShell에서 피싱 규칙의 우선 순위를 설정 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다. 우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**참고:**

- 새 규칙을 만들 때 우선 순위를 설정 하려면 대신 **AntiPhishRule** Cmdlet에서 _priority_ 매개 변수를 사용 하십시오.

- 기본 피싱 정책에는 해당 하는 피싱 규칙이 없으며 항상 **가장 낮은**우선 순위 값을 사용 합니다.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell을 사용 하 여 피싱 정책 제거

PowerShell을 사용 하 여 피싱 정책을 제거 하면 해당 하는 피싱 규칙이 제거 되지 않습니다.

PowerShell에서 피싱 정책을 제거 하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

이 예에서는 Marketing 학과 라는 피싱 정책을 제거 합니다.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)를 참조 하십시오.

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell을 사용 하 여 피싱 규칙 제거

PowerShell을 사용 하 여 피싱 규칙을 제거 하면 해당 하는 피싱 정책이 제거 되지 않습니다.

PowerShell에서 피싱 규칙을 제거 하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

이 예에서는 Marketing 학과 라는 피싱 규칙을 제거 합니다.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)를 참조 하십시오.

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

ATP 피싱 방지 정책이 구성 되었는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **피싱 방지**로 이동 합니다. 정책 목록, 해당 **상태** 값 및 해당 **우선 순위** 값을 확인 합니다. 자세한 정보를 보려면 다음 단계 중 하나를 수행 합니다.

  - 목록에서 정책을 선택 하 고 플라이 아웃의 세부 정보를 확인 합니다.
  - **기본 정책을** 클릭 하 고 플라이 아웃에서 세부 정보를 확인 합니다.

- Exchange Online PowerShell에서 \<Name\> 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행 하 고 설정을 확인 합니다.

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
