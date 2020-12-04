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
description: 관리자는 EOP(Exchange Online Protection) 및 Office 365용 Microsoft Defender의 보호 기능에 표준 및 엄격한 정책 설정을 적용하는 방법을 배울 수 있습니다.
ms.openlocfilehash: e968f7ea768ac8a0b402c28f3830a52b44afa342
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572780"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP 및 Office 365용 Microsoft Defender에서 보안 정책 미리 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


미리 설정한 보안 정책은 권장되는 모든 스팸, 맬웨어 및 피싱 정책을 사용자에게 한 동시에 적용할 수 있는 중앙 위치를 제공합니다. 정책 설정은 구성할 수 없습니다. 대신, 사용자가 업무를 중단하지 않고 유해한 콘텐츠를 사용자에게 노출하지 못하게 하는 균형을 위해 데이터 센터의 관찰 및 경험을 기반으로 합니다.

이 항목의 나머지에서는 미리 설정한 보안 정책 및 구성 방법에 대해 설명하고 있습니다.

## <a name="what-preset-security-policies-are-made-of"></a>미리 설정한 보안 정책

미리 설정한 보안 정책은 다음 요소로 구성됩니다.

- 프로필
- 정책
- 정책 설정

또한 미리 설정한 여러 보안 정책 및 기타 정책이 동일한 사용자에 적용되는 경우 우선 순위가 중요합니다.

### <a name="profiles-in-preset-security-policies"></a>미리 설정한 보안 정책의 프로필

프로필에 따라 보호 수준이 결정됩니다. 다음 프로필을 사용할 수 있습니다.

- **표준 보호:** 대부분의 사용자에게 적합한 기준 보호 프로필입니다.
- **엄격한 보호:** 선택한 사용자(높은 가치의 대상 또는 우선 순위 사용자)에 대한 보다 적극적인 보호 프로필입니다.

프로필이 누구인지 또는 적용되지 않는지 결정하는 조건 및 예외와 함께 규칙을 사용할 수 있습니다.

조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

사용 가능한 조건 및 예외는 다음입니다.

- **받는 사람은 조직의** 사서함, 메일 사용자 또는 메일 연락처입니다.
- **받는 사람이 조직의** 그룹 구성원입니다.
- **받는 사람 도메인은** Microsoft 365에 구성된 허용 도메인입니다.

### <a name="policies-in-preset-security-policies"></a>미리 설정한 보안 정책의 정책

미리 설정한 보안 정책은 EOP 및 Office 365용 Microsoft Defender의 다양한 보호 기능의 해당 정책을 사용 합니다. 이러한 정책은 **Standard 보호** _또는_ **엄격한** 보호 미리 설정 보안 정책을 사용자에게 할당한 후에 만들어집니다. 이러한 정책은 수정할 수 없습니다.

- **EOP(Exchange Online Protection)** 정책: Exchange Online 사서함이 있는 Microsoft 365 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직이 포함됩니다.
  
  - [Standard 미리 설정](configure-your-spam-filter-policies.md) 보안 정책 및 엄격한 미리 **설정** 보안 **정책이라는** 스팸 방지 정책
  - [Standard 미리](configure-anti-malware-policies.md) 설정 **Standard Preset Security Policy** 보안 정책 및 엄격한 미리 설정 보안 정책이라는 맬웨어 **방지 정책**
  - 표준 미리 설정 보안 정책 **Standard Preset Security Policy** 및 엄격한 미리 **Strict Preset Security Policy** 설정 보안 정책(스푸핑 설정)이라는 [EOP](set-up-anti-phishing-policies.md#spoof-settings) 피싱 방지 정책

- **Office 365용 Microsoft Defender** 정책: 여기에는 Microsoft 365 E5 또는 Office 365용 Defender 추가 기능 구독이 있는 조직이 포함됩니다.

  - Standard **Preset Security Policy** 및 Strict **Preset Security** Policy라는 Microsoft Defender for Office 365의 피싱 방지 정책에는 다음이 포함됩니다.

    - EOP [피싱](set-up-anti-phishing-policies.md#spoof-settings) 방지 정책에서 사용할 수 있는 동일한 스푸핑 설정입니다.
    - [가장 설정](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [고급 피싱 임계값](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [표준 미리 설정](set-up-atp-safe-links-policies.md) 보안 정책 및 엄격한 미리 설정 보안 **정책이라는** 안전 **링크 정책**

  - [표준 미리 설정](set-up-atp-safe-attachments-policies.md) 보안 정책 및 엄격한 미리 **설정** 보안 **정책이라는** 안전 첨부 파일 정책

Office 365 보호를 위한 Microsoft Defender와는 다른 사용자에게 EOP 보호를 적용할 수 있습니다.

### <a name="policy-settings-in-preset-security-policies"></a>미리 설정한 보안 정책의 정책 설정

보호 프로필에서는 정책 설정을 수정할 수 없습니다. 표준 **및** **엄격한** 정책 설정 값은 EOP 및 [Office 365용 Microsoft Defender](recommended-settings-for-eop-and-office365-atp.md)보안에 대한 권장 설정에 설명되어 있습니다.

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>미리 설정한 보안 정책 및 기타 정책의 우선 순위

사용자에게 여러 정책을 적용하면 우선 순위가 가장 높은 순서부터 가장 낮은 우선 순위까지 다음 순서가 적용됩니다.

1. **엄격한 보호** 미리 설정 보안 정책
2. **표준 보호** 미리 설정 보안 정책
3. 사용자 지정 보안 정책
4. 기본 보안 정책

즉, **Strict 보호** 정책의 설정은 표준 보호 정책의 설정을 대신하여 기본 정책의 설정을 정의하는 사용자 지정 정책의 설정을 정의합니다. **Standard protection**

## <a name="assign-preset-security-policies-to-users"></a>사용자에게 미리 설정한 보안 정책 할당

### <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 미리 설정한 보안 정책 페이지로 직접 **이동하기 위해** <https://protection.office.com/presetSecurityPolicies> 다음을 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다.

  - 미리 설정한 보안 정책을 구성하려면 Security & **Organization Management** 준수 **Security Administrator** 센터에서 조직 관리 [또는 보안 관리자 역할의 구성원 & 합니다.](permissions-in-the-security-and-compliance-center.md)

  - 미리 설정한 보안 정책에 대한 읽기 전용 액세스 권한을 **Global Reader** 사용하려면 Security & 준수 센터에서 전역 [읽기 & 합니다.](permissions-in-the-security-and-compliance-center.md)

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>보안 및 & 센터를 사용하여 미리 설정한 보안 정책을 사용자에게 할당

1. 보안 & 준수 센터에서 **위협** 관리 정책 \> **Policy** \> **미리 설정 보안 정책으로 이동합니다.**

2. 표준 **보호 또는** 엄격한 **보호에서** 편집을 **클릭합니다.**

3. 표준 **보호 적용 또는** 엄격한 보호 적용 **마법사가** 시작됩니다. **EOP 보호는** 단계에 적용될 때 [EOP](#policies-in-preset-security-policies) 보호가 적용되는 내부 받는 사람을 식별합니다.

   1. 조건 **추가를 클릭합니다.** 나타나는 드롭다운에서 적용된 조건(다음의 **경우)을 선택합니다.**

      - **받는 사람은**
      - **받는 사람이 다음의 구성원입니다.**
      - **받는 사람 도메인**

      조건을 한 번만 사용할 수 있지만 조건에 대해 여러 값을 지정할 수 있습니다. 같은 조건의 여러 값이 OR 논리(예: 또는 )를 _\<recipient1\>_ _\<recipient2\>_ 사용합니다.

   2. 선택한 조건이 음영이 있는 섹션에 표시됩니다. 해당 섹션에서 다음 상자를 **클릭합니다.** 잠시 기다리면 값을 선택할 수 있도록 목록이 나타납니다. 또는 값을 입력하여 목록을 필터링하고 값을 선택할 수 있습니다. 필요한 만큼 이 단계를 반복합니다. 개별 값을 제거하려면 **Remove** 값에서 제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다. 전체 조건을 제거하려면 **조건에서** 제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.

   3. 다른 조건을 추가하려면 조건 추가를 **클릭하고** 나머지 조건에서 선택합니다. 조건마다 AND 논리(예: _\<recipient1\>_ _\<member of group 1\>_ )를 사용합니다.

      이전 단계를 반복하여 조건에 값을 추가하고 필요한 수만큼 또는 조건을 다 사용할 때까지 이 단계를 반복합니다.

   4. 예외를 추가하려면 **조건 추가를 클릭합니다.** 나타나는 드롭다운에서 다음의 조건을 **선택합니다.** 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. 조직에 Office 365용 Microsoft Defender가 있는 경우 MICROSOFT [Defender for Office 365](#policies-in-preset-security-policies) 보호가 적용되는 내부 받는 사람을 식별하기 위한 **단계로 ATP** 보호가 적용됩니다.

   설정 및 동작은 **단계에 적용되는 EOP 보호와 정확히 같습니다.**

   작업을 마친 후 **다음** 을 클릭합니다.

5. 확인 **단계에서** 선택을 확인하고 확인을 **클릭합니다.**

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>보안 및 & 센터를 사용하여 미리 설정한 보안 정책 할당 수정

표준 보호 또는 엄격한 **Standard protection** 보호 보안 **Strict protection** 정책 할당을 수정하는 단계는 미리 설정한 보안 정책을 사용자에게 처음 할당할 때와 [동일합니다.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)

기존 조건 및 예외를 보존하면서 **표준** 보호 또는 **엄격한** 보호 보안 정책을 사용하지 않도록 설정하고 토글을 사용 안 하게 **합니다.** 정책을 사용하도록 설정하려면 토글을 **사용으로** 설정합니다.

### <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

사용자에게 **표준** 보호 또는 엄격한 보호 보안 **Strict protection** 정책이 할당되어 있는지 확인하기 위해 기본값이 **Standard** 보호 설정과 다른 보호 설정을 사용(Strict **protection** 설정과는 다를 수 있습니다.

예를 들어 스팸으로 검색된 전자 메일(높은 신뢰도 스팸 아님)의 경우 표준 **Standard protection** 보호 사용자를 위해 메시지가 정크 메일 폴더로 배달되고 고급 보호 사용자에 대해 스팸으로 분류된지 **확인합니다.**

또는 대량 [bulk email](bulk-complaint-level-values.md)전자 메일의 경우 BCL 값이 6 이상이 **표준** 보호 사용자를 위해 정크 메일 폴더로 메시지를 배달하는지 확인하고 BCL 값이 4 이상이면 **엄격한** 보호 사용자에 대해 메시지를 차단합니다.
