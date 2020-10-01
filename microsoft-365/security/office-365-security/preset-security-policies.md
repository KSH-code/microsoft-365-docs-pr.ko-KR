---
title: 보안 정책 미리조정
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
description: 관리자는 EOP (Exchange Online Protection) 및 Office 365 Advanced Threat Protection (ATP)의 보호 기능을 통해 표준 및 엄격한 정책 설정을 적용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 8431d36779069b0b289a2533fbd6b85abee24536
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326546"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a>EOP 및 Office 365 ATP의 미리 설정 된 보안 정책

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


미리 설정 된 보안 정책은 권장 되는 모든 스팸, 맬웨어 및 피싱 정책을 사용자에 게 한 번에 적용 하기 위한 중앙 집중식 위치를 제공 합니다. 정책 설정을 구성할 수 없습니다. 대신, 이러한 기능은 우리에 의해 설정 되며, 데이터 센터의 관찰 및 경험에 따라 작업을 방해 하지 않고 사용자에 게 해로운 콘텐츠를 보관 하는 것 간의 균형을 맞출 수 있습니다.

이 항목의 나머지 부분에서는 미리 설정 된 보안 정책 및 이러한 정책을 구성 하는 방법에 대해 설명 합니다.

## <a name="what-preset-security-policies-are-made-of"></a>미리 설정 된 보안 정책 구성

미리 설정 된 보안 정책은 다음 요소로 구성 됩니다.

- 프로필
- 정책
- 정책 설정

또한 미리 설정 된 여러 보안 정책 및 기타 정책이 동일한 사람에 게 적용 되는 경우에는 우선 순위 순서가 중요 합니다.

### <a name="profiles-in-preset-security-policies"></a>미리 설정 된 보안 정책의 프로필

프로필은 보호 수준을 결정 합니다. 다음과 같은 프로필을 사용할 수 있습니다.

- **표준 보호**: 대부분의 사용자에 게 적합 한 기본 보호 프로필입니다.
- **엄격한 보호**: 선택한 사용자 (높은 값 목표 또는 우선 순위 사용자)에 대 한 적극적인 보호 프로필입니다.

프로필을 지정 하거나 적용 하지 않을 사람을 결정 하는 조건 및 예외 사항에 규칙을 사용 합니다.

조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

사용 가능한 조건 및 예외는 다음과 같습니다.

- **받는 사람은**조직의 사서함, 메일 사용자 또는 메일 연락처입니다.
- **받는 사람은**조직의 그룹 구성원입니다.
- **받는 사람 도메인**은 Microsoft 365에 구성 되어 있는 허용 도메인입니다.

### <a name="policies-in-preset-security-policies"></a>미리 설정 된 보안 정책의 정책

미리 설정 된 보안 정책은 EOP 및 Office 365 ATP의 다양 한 보호 기능에서 해당 하는 정책을 사용 합니다. 이러한 정책은 **표준 보호** 또는 **엄격한 보호** 사전 설정 보안 정책을 사용자에 게 할당 _한 후_ 에 만들어집니다. 이러한 정책은 수정할 수 없습니다.

- **EOP (Exchange Online Protection) 정책**: exchange online 사서함을 사용 하는 Microsoft 365 조직과 exchange online 사서함이 없는 독립 실행형 EOP 조직이 포함 됩니다.
  
  - **표준 사전 설정 보안 정책** 및 **엄격한 사전 설정 보안 정책**이라는 [스팸 방지 정책](configure-your-spam-filter-policies.md)
  - **표준 사전 설정 보안 정책** 및 **엄격한 사전 설정 보안 정책**이라는 [맬웨어 방지 정책](configure-anti-malware-policies.md)
  - **표준 사전 설정 보안 정책** 및 **엄격한 미리 설정 된 보안 정책** (스푸핑 설정) 이라는 [EOP 피싱 방지 정책](set-up-anti-phishing-policies.md#spoof-settings)

- **Office 365 atp (Advanced Threat Protection) 정책**: 여기에는 Microsoft 365 E5 또는 OFFICE 365 ATP 추가 기능 구독이 있는 조직이 포함 됩니다.

  - 다음을 포함 하는 **표준 사전 설정 보안 정책** 및 **엄격한 미리 설정 보안 정책**이라는 ATP 피싱 방지 정책

    - EOP 피싱 방지 정책에서 사용할 수 있는 것과 동일한 [스푸핑 설정](set-up-anti-phishing-policies.md#spoof-settings)
    - [가장 설정](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [고급 피싱 임계값](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [안전한 링크 정책](set-up-atp-safe-links-policies.md) **표준 사전 설정 보안 정책** 및 **엄격한 미리 설정 된 보안 정책**

  - [안전한 첨부 파일 정책](set-up-atp-safe-attachments-policies.md) **표준 미리 설정 보안 정책** 및 **엄격한 미리 설정 된 보안 정책**이라고 합니다.

ATP 보호와는 다른 사용자에 게 EOP 보호를 적용할 수 있습니다.

### <a name="policy-settings-in-preset-security-policies"></a>미리 설정 된 보안 정책의 정책 설정

보호 프로필에서 정책 설정은 수정할 수 없습니다. **표준** 및 **엄격한** 정책 설정 값은 [EOP 및 Office 365 ATP 보안에 대 한 권장 설정](recommended-settings-for-eop-and-office365-atp.md)에 설명 되어 있습니다.

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>미리 설정 된 보안 정책 및 기타 정책의 우선 순위 순서

여러 정책이 사용자에 게 적용 되는 경우 다음 순서는 가장 높은 우선 순위에서 가장 낮은 우선 순위로 적용 됩니다.

1. **엄격한 보호** 사전 설정 보안 정책
2. **표준 보호** 사전 설정 보안 정책
3. 사용자 지정 보안 정책
4. 기본 보안 정책

즉, **엄격한 보호** 정책 설정은 기본 정책의 설정을 재정의 하는 사용자 지정 정책의 설정을 재정의 하는 **표준 보호** 정책의 설정을 재정의 합니다.

## <a name="assign-preset-security-policies-to-users"></a>사용자에 게 미리 설정 된 보안 정책 할당

### <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **미리 설정 된 보안 정책** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/presetSecurityPolicies> 합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 미리 설정 된 보안 정책을 구성 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 미리 설정 된 보안 정책에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>보안 & 준수 센터를 사용 하 여 사용자에 게 미리 설정 된 보안 정책 할당

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **미리 설정 된 보안 정책**으로 이동 합니다.

2. **표준 보호** 또는 **엄격한 보호**에서 **편집**을 클릭 합니다.

3. **표준 보호 적용** 또는 **엄격한 보호 적용** 마법사가 시작 됩니다. **EOP 보호 적용** 단계에서 [EOP 보호](#policies-in-preset-security-policies) 를 적용할 내부 받는 사람을 식별 합니다.

   1. **조건 추가를**클릭 합니다. 표시 되는 드롭다운 목록에서 다음의 **경우 적용**아래의 조건을 선택 합니다.

      - **받는 사람이**
      - **받는 사람이 다음 구성원 인 경우**
      - **받는 사람 도메인이**

      조건을 한 번만 사용할 수 있지만 조건에 대해 여러 값을 지정할 수 있습니다. 동일한 조건 사용 또는 논리의 여러 값 (예: _\<recipient1\>_ or _\<recipient2\>_ )

   2. 선택한 조건이 음영 처리 된 구역에 표시 됩니다. 해당 섹션에서 **다음 상자 중 하나** 를 클릭 합니다. 잠시 기다리면 값을 선택할 수 있는 목록이 표시 됩니다. 또는 값을 입력 하 여 목록을 필터링 하 고 값을 선택할 수 있습니다. 필요한 만큼 이 단계를 반복합니다. 개별 값을 제거 하려면 값에서 제거 아이콘 **제거** 를 클릭 ![ ](../../media/scc-remove-icon.png) 합니다. 전체 조건을 제거 하려면 **Remove** ![ 조건에서 제거 아이콘 제거를 클릭 ](../../media/scc-remove-icon.png) 합니다.

   3. 다른 조건을 추가 하려면 **조건 추가** 를 클릭 하 고 나머지 조건에서 선택 합니다. 서로 다른 조건 및 논리가 사용 됩니다 (예: _\<recipient1\>_ and _\<member of group 1\>_ ).

      이전 단계를 반복 하 여 조건에 값을 추가 하 고, 필요에 따라 또는 조건이 없어질 때까지이 단계를 반복 합니다.

   4. 예외를 추가 하려면 **조건 추가**를 클릭 합니다. 표시 되는 드롭다운 목록에서 **When 제외**아래의 조건을 선택 합니다. 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음**을 클릭합니다.

4. 조직에 Office 365 ATP가 있는 경우 **ATP 보호를 적용** 하 여 [office 365 atp 보호가](#policies-in-preset-security-policies) 적용 되는 내부 받는 사람을 식별 하는 단계를 수행 합니다.

   설정 및 동작은 **EOP 보호 적용** 단계와 동일 합니다.

   작업을 마친 후 **다음**을 클릭합니다.

5. **확인** 단계에서 선택한 항목을 확인 하 고 **확인**을 클릭 합니다.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>보안 & 준수 센터를 사용 하 여 미리 설정 된 보안 정책의 할당 수정

**표준 보호** 또는 **엄격한 보호** 보안 정책에 대 한 할당을 수정 하는 단계는 [미리 설정 된 보안 정책을 사용자에 게 처음 할당](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)했을 때와 동일 합니다.

기존 조건 및 예외를 유지 하면서 **표준 보호** 또는 **엄격한 보호** 보안 정책을 사용 하지 않도록 설정 하려면 슬라이드를 **사용 안 함으로**설정 합니다. 정책을 사용 하도록 설정 하려면 설정/해제를 **사용**으로 이동 합니다.

### <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

사용자에 게 **표준 보호** 또는 **엄격한 보호** 보안 정책이 할당 되었는지 확인 하려면 기본 값이 **표준 보호** 설정과 다른 경우 ( **엄격한 보호** 설정과는 다름) 보호 설정을 사용 합니다.

예를 들어 스팸이 아닌 스팸으로 검색 되는 전자 메일 (신뢰도가 높은 스팸 아님)의 경우 메시지가 **표준 보호** 사용자에 대 한 정크 메일 폴더로 배달 되 고 **엄격한 보호** 사용자에 대해 격리 되어 있는지 확인 합니다.

또는 [대량 전자 메일](bulk-complaint-level-values.md)의 경우, bcl 값 6 이상이 **표준 보호** 사용자의 정크 메일 폴더에 메시지를 전달 하 고, Bcl 값 4 이상이 **엄격한 보호** 사용자에 대 한 메시지를 설정별 확인 합니다.
