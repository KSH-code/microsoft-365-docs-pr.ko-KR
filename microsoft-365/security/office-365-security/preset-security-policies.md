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
description: 관리자는 EOP(Exchange Online Protection) 및 Office 365 ATP(Advanced Threat Protection)의 보호 기능에서 표준 및 고급 정책 설정을 적용하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: a2f0472d8dd44c90fd5db14e71d2db0d5d323b50
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825260"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a>EOP 및 Office 365 ATP의 미리 설정된 보안 정책

미리 설정된 보안 정책을 사용하면 권장되는 모든 스팸, 맬웨어 및 피싱 정책을 사용자에게 한 번에 적용할 수 있는 중앙 위치가 제공됩니다. 정책 설정은 구성할 수 없습니다. 대신 Microsoft에서 지원하며, 작업을 지장하지 않으면서 사용자로부터 유해한 콘텐츠를 유지할 수 있도록 데이터 센터의 관찰 및 환경을 기반으로 합니다.

이 항목의 나머지 부분에서는 미리 설정된 보안 정책 및 이러한 정책을 구성하는 방법에 대해 설명합니다.

## <a name="what-preset-security-policies-are-made-of"></a>미리 설정된 보안 정책의 개시

미리 설정된 보안 정책은 다음 요소로 구성됩니다.

- 프로필
- 정책
- 정책 설정

또한 동일한 사용자에 여러 개의 미리 설정된 보안 정책 및 기타 정책이 적용된 경우 우선 순위가 중요합니다.

### <a name="profiles-in-preset-security-policies"></a>미리 설정된 보안 정책의 프로필

프로필은 보호 수준을 결정합니다. 사용할 수 있는 프로필은 다음과 같습니다.

- **표준 보호:** 대부분의 사용자에게 적합한 기준 보호 프로필입니다.
- **고급 보호**: 선택한 사용자를 위한 더 욱적극적인 보호 프로필(가치가 높은 대상 또는 우선 순위 사용자).

프로필이 적용되거나 적용되지 않는 사람을 확인하는 조건 및 예외와 함께 규칙을 사용합니다.

조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

사용 가능한 조건 및 예외는 다음과 같습니다.

- **받는 사람은 조직의**사서함, 메일 사용자 또는 메일 연락처입니다.
- **받는 사람이 조직의 구성원:** 그룹의 구성원입니다.
- **받는 사람 도메인은**Microsoft 365에서 구성된 허용 도메인입니다.

### <a name="policies-in-preset-security-policies"></a>미리 설정된 보안 정책의 정책

미리 설정된 보안 정책은 EOP 및 Office 365 ATP의 다양한 보호 기능에서 제공하는 해당 정책을 사용합니다. 이러한 정책은 표준 _보호 또는_ **[Strict Protection)** **보호 정책을 사용자에게 할당한** 후 생성됩니다. 이러한 정책은 수정할 수 없습니다.

- **EOP(Exchange Online Protection) 정책**: Exchange Online 사서함과 함께 Microsoft 365 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직이 포함됩니다.
  
  - [표준 미리 설정된 보안](configure-your-spam-filter-policies.md) **정책 및 Strict** 미리 **설정된 보안 정책이라는 스팸 방지 정책.**
  - [표준 사전 보안 정책](configure-anti-malware-policies.md) **및 Strict 미리 설정된 보안** **정책이라고 하는 맬웨어 방지 정책.**
  - [표준 사전 설정 보안 정책 및](set-up-anti-phishing-policies.md#spoof-settings) **Strict** **미리** 설정된 보안 정책(스푸핑 설정)이라고 하는 EOP 피싱 방지 정책

- **Office 365 ADVANCED Threat Protection(ATP) 정책:** 여기에는 Microsoft 365 E5 또는 Office 365 ATP 추가 기능 구독을 사용하는 조직이 포함됩니다.

  - 다음을 포함하는 표준 사전 설정된 보안 정책 **및** **Strict 미리**설정 보안 정책이라고 하는 ATP 피싱 방지 정책

    - [EOP피싱 방지 정책에서](set-up-anti-phishing-policies.md#spoof-settings) 사용할 수 있는 것과 동일한 스푸핑 설정
    - [가장 설정](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [고급 피싱 임계값](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [표준 사전 설정 보안](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) 정책 및 **Strict 미리 설정된 보안 정책이라고 하는 안전 링크**정책. **Standard Preset Security Policy**

  - [표준 미리 설정된 보안](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) 정책 및 **Strict 미리 설정된 보안 정책이라고 하는 안전 첨부 파일**정책. **Standard Preset Security Policy**

EOP 보호와는 다른 사용자에게 EOP 보호를 적용할 수 있습니다.

### <a name="policy-settings-in-preset-security-policies"></a>미리 설정된 보안 정책의 정책 설정

보호 프로필의 정책 설정은 수정할 수 없습니다. EOP **및** Office 365 ATP 보안에 대한 권장 설정에서는 표준 및 **Strict** [정책 설정에 대한 값이 설명되어 있습니다.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>미리 설정된 보안 정책 및 기타 정책의 우선 순위

여러 정책이 사용자에게 적용된 경우 다음 순서가 가장 높은 우선 순위부터 최하위 우선 순위로 적용됩니다.

1. **Strict Protection** 미리 설정된 보안 정책
2. **표준 보호** 미리 설정된 보안 정책
3. 사용자 지정 보안 정책
4. 기본 보안 정책

즉, [보안 보호 정책" **설정은 표준** 보호 정책의 설정을 재정의하는 **표준** 보호 정책의 설정을 재정의합니다. 이 정책의 설정은 사용자 지정 정책의 설정을 무시합니다. 이 경우 기본 정책의 설정이 무시됩니다.

## <a name="assign-preset-security-policies-to-users"></a>사용자에게 미리 설정된 보안 정책 할당

### <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 미리 설정된 보안 정책 **페이지로 직접 이동하려면 다음을** 사용합니다. <https://protection.office.com/presetSecurityPolicies>

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 미리 설정된 보안 정책을 구성하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 미리 설정된 보안 정책에 대한 읽기 전용 액세스를 위해는 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>보안 그룹 & 준수 센터를 사용하여 미리 설정된 보안 정책 할당

1. 보안 전부 & 보안 센터에서 위협 관리 **정책 미리** \> **설정된 보안** \> **정책으로 이동합니다.**

2. Standard **Protection 또는** **Strict Protection에서 편집을** **클릭합니다.**

3. 표준 **보호 적용 또는** **[관리 보호 적용) 마법사가** 시작됩니다. EOP **보호가 단계에 적용되는 단계에는** EOP 보호가 적용되는 내부 [받는 사람을](#policies-in-preset-security-policies) 확인합니다.

   1. 조건 **추가를 클릭합니다.** 표시되는 드롭다운 메뉴에서 다음과 같은 경우 적용된 **조건을 선택합니다.**

      - **받는 사람이 다음과 같습니다.**
      - **받는 사람이 다음의 구성원인 경우**
      - **받는 사람 도메인이 다음과 같습니다.**

      조건은 한 번만 사용할 수 있지만 조건에는 여러 값을 지정할 수 있습니다. 동일한 조건의 여러 값은 OR 논리(예: or)를 _\<recipient1\>_ _\<recipient2\>_ 사용합니다.

   2. 선택한 조건이 음중 섹션에 표시됩니다. 이 섹션에서 다음 **상자를 클릭합니다.** 잠시 기다리면 값을 선택할 수 있도록 목록이 표시됩니다. 또는 값을 입력하여 목록을 필터링하고 값을 선택할 수 있습니다. 필요한 만큼 이 단계를 반복합니다. 개별 값을 제거하려면 값에서 **제거** ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다. 전체 조건을 제거하려면 해당 **조건에서** ![ 제거 아이콘 ](../../media/scc-remove-icon.png) 제거아이콘을 클릭합니다.

   3. 다른 조건을 추가하려면 **조건 추가를** 클릭하고 나머지 조건에서 선택합니다. 다른 조건에는 AND 논리(예: 및)가 _\<recipient1\>_ _\<member of group 1\>_ 사용됩니다.

      위 단계를 반복하여 조건에 값을 추가한 다음 필요한 만큼 또는 조건이 부과할 때까지 이 단계를 반복합니다.

   4. 예외를 추가하려면 조건 **추가를 클릭합니다.** 표시되는 드롭다운에서 ** 제외** 필드를 선택합니다. 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음**을 클릭합니다.

4. 조직에 Office 365 ATP가 있는 [경우, Office 365](#policies-in-preset-security-policies) **ATP 보호가** 적용되는 내부 받는 사람을 식별하기 위해 ATP 보호 조치가 적용됩니다.

   설정 및 동작은 EOP 보호 단계와 **정확히 동일합니다.**

   작업을 마친 후 **다음**을 클릭합니다.

5. 확인 **단계에서** 선택 사항을 확인하고 확인을 **클릭합니다.**

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>보안 서비스 & 센터를 사용하여 미리 설정된 보안 정책 할당 수정

표준 보호 또는 **Strict** **Protection** 보안 정책 할당을 수정하는 단계는 처음에 미리 설정된 보안 [정책을 사용자에게 할당한 단계와 동일합니다.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)

기존 조건 **및 예외를** **유지하면서 표준** 보호 또는 고급 보호 보안 정책을 사용하지 않도록 설정하려면 토글을 사용 안 함으로 **밀어 넣습니다.** 정책을 사용하려면 토글을 사용으로 **밀어 서는 방법을 합니다.**

### <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

표준 보호 또는 **Strict** 보호 보안 정책을 사용자에게 성공적으로 할당되었는지 확인하려면 기본값이 표준 보호 설정과 다른 보호 **Standard protection** 설정([Strict **Protection)** 설정과는 다른 **보호 설정을 사용합니다.**

예를 들어 스팸(높은 신뢰도의 스팸이 아님)으로 검색된 전자 메일의 경우 해당 메시지가 **표준** 보호 사용자의 정크 메일 폴더에 배달되고, **Strict Protection 사용자를 위해 격리되는지 확인합니다.**

또는 [대량 전자 메일의](bulk-complaint-level-values.md)경우, BCL 값이 6 이상인 표준 보호 사용자를 위해 **Standard protection** 메시지를 정크 메일 폴더에 배달하고, BCL 값 4 이상이 **Strict Protection 사용자에 대한 메시지를 격리하는지 확인합니다.**
