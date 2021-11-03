---
title: 미리 설정된 보안 정책
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection) 및 Microsoft Defender for Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8058a9165ef97c82c2e600db0c98b14616bc175
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60666713"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP 및 Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

미리 설정한 보안 정책은 권장되는 모든 스팸, 맬웨어 및 피싱 정책을 한에 적용할 수 있는 중앙 집중식 위치를 제공합니다. 정책 설정은 구성할 수 없습니다. 대신 사용자로부터 유해한 콘텐츠를 보호하고 불필요한 중단을 방지하는 것 사이의 균형을 위해 데이터 센터의 관찰 및 환경을 기반으로 설정됩니다.

이 문서의 나머지부분에서는 미리 설정한 보안 정책과 이를 구성하는 방법에 대해 설명하고 있습니다.

## <a name="what-preset-security-policies-are-made-of"></a>미리 설정한 보안 정책의 적용

미리 설정한 보안 정책은 다음 요소로 구성됩니다.

- 프로필
- 정책
- 정책 설정

또한 미리 설정한 여러 보안 정책 및 기타 정책이 동일한 사용자에 적용되는 경우 우선 순위가 중요합니다.

### <a name="profiles-in-preset-security-policies"></a>미리 설정한 보안 정책의 프로필

프로필에 따라 보호 수준이 결정됩니다. 다음 프로필을 사용할 수 있습니다.

- **표준 보호**: 대부분의 사용자에게 적합한 기준 보호 프로필입니다.
- **엄격한 보호:** 선택한 사용자(높은 가치의 대상 또는 우선 순위 사용자)에 대한 보다 적극적인 보호 프로필입니다.

  **표준 보호 및** **엄격한** 보호의 경우, 프로필이 누구인지 또는 적용되지 않은지 결정하는 조건 및 예외와 함께 규칙을 사용하게 됩니다.

  사용 가능한 조건 및 예외는 다음입니다.

  - **사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.
  - **그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.
  - **도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.

  조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

- **기본 제공** 보호(Defender for Office 365): 첨부 파일 보호만 금고 금고 프로필입니다. 이 설정은 기본 정책이 없는 금고 및 금고 첨부 파일에 대한 기본 정책을 효과적으로 제공합니다.

  > [!NOTE]
  > 기본 **제공 보호** 미리 설정 보안 정책은 현재 미리 보기로 제공되어 있으며 모든 조직에서 사용할 수 있으며 변경될 수 있습니다.

  기본 **제공 보호의** 경우 사전 설정한 보안 정책은 모든 고객용 모든 Defender에 Office 365 있습니다. 권장되지는 않습니다. 그러나 **사용자,** 그룹 및 도메인에 따라  예외를 구성하여 특정 사용자에게 보호가 적용되지 않습니다.

사용자에게 정책을 할당할 때까지 **Standard** 및 **Strict** 미리 설정한 보안 정책은 아무에게도 할당되지 않습니다. 반면, **기본** 제공 보호 미리 설정 보안 정책은 기본적으로 모든 받는 사람에게 할당되지만 예외를 구성할 수 있습니다.

### <a name="policies-in-preset-security-policies"></a>미리 설정한 보안 정책의 정책

미리 설정한 보안 정책은 EOP 및 Microsoft Defender for Office 365. 이러한 정책은 **Standard** _보호_ 또는 **엄격한** 보호 미리 설정 보안 정책을 사용자에게 할당한 후에 만들어집니다. 이러한 정책의 설정은 수정할 수 없습니다.

- **Exchange Online Protection(EOP)** 정책: Microsoft 365 사서함이 없는 Exchange Online 독립 실행형 EOP Exchange Online 포함됩니다.

  - [Standard 미리](configure-your-spam-filter-policies.md) 설정  보안 정책 및 엄격한 미리 설정 보안 정책 이라는 스팸 **방지 정책**
  - [Standard 미리](configure-anti-malware-policies.md) 설정  보안 정책 및 엄격한 미리 설정 보안 정책 이라는 맬웨어 **방지 정책**
  - 표준 미리 설정 보안 정책  및 엄격한 미리  설정 보안 정책(스푸핑 설정)이라는 [EOP](set-up-anti-phishing-policies.md#spoof-settings) 피싱 방지 정책

- **Microsoft Defender for Office 365** 정책: Microsoft 365 E5 추가 기능 구독에 대한 Office 365 조직이 포함됩니다.
  - Standard Preset Security Policy 및 Strict **Preset** Security **Policy라는** 이름의 Microsoft Defender의 피싱 Office 365 다음을 포함합니다.
    - EOP [](set-up-anti-phishing-policies.md#spoof-settings) 피싱 방지 정책에서 사용할 수 있는 동일한 스푸핑 설정입니다.
    - [가장 설정](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [고급 피싱 임곗값](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [금고 미리](set-up-safe-links-policies.md) 설정 보안 **정책,** **엄격한** 미리 설정 보안 정책 및 기본 제공 보호 정책 이라는 링크 **정책입니다.**
  - [금고 미리](set-up-safe-attachments-policies.md) 설정 보안 **정책,** **엄격한** 미리 설정 보안 정책 및 기본 제공 보호 정책 이라는 첨부 **파일 정책입니다.**

Microsoft Defender와는 다른 사용자에게 EOP 보호를 적용할 수 Office 365 있습니다.

### <a name="policy-settings-in-preset-security-policies"></a>미리 설정한 보안 정책의 정책 설정

보호 프로필에서는 정책 설정을 수정할 수 없습니다. **표준,** **엄격한** 및  기본 제공 보호 정책 설정 값은 EOP 및 Microsoft Defender for [Office 365 설정에 설명되어 있습니다.](recommended-settings-for-eop-and-office365.md)

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>미리 설정한 보안 정책 및 기타 정책의 우선 순위

사용자에게 여러 정책이 적용될 경우 우선 순위가 가장 높은 순서부터 가장 낮은 우선 순위까지 다음 순서가 적용됩니다.

1. **엄격한 보호** 미리 설정 보안 정책
2. **표준 보호** 미리 설정 보안 정책
3. 사용자 지정 보안 정책
4. **기본 제공 보호 미리** 설정 보안 정책 및 기본 보안 정책

즉, 엄격한 보호 정책의 설정은 기본 제공 보호  미리 설정 보안 정책(금고 링크 및 금고 첨부 파일) 및 기본  정책(스팸 방지, 맬웨어 방지 및 피싱 방지)의 설정을 정의하는 사용자 지정 정책의 설정을 보다 정의하는 표준 보호 정책의 설정을 정의합니다. 

예를 들어 **표준** 보호에 보안 설정이 있는 경우 관리자가 사용자에 대해 **표준** 보호를 사용하도록 설정한 경우 표준 보호 설정은 사용자 지정 정책 또는 기본 정책(동일한 사용자)에서 해당 설정에 대해 구성된 설정 대신 적용됩니다.  특정 요구 사항을 충족하기 위해 조직의 다른 사용자에게 사용자 지정  정책을 적용하는 동안 **표준** 또는 엄격한 보호 정책만 적용하려는 조직의 일부가 있을 수 있습니다.

**기본 제공 보호는** 기존 금고 첨부 파일 정책의 금고 영향을 주지 않습니다. **표준** **보호,** 엄격한 보호 또는 사용자 지정 금고 링크 또는 금고 첨부 파일 정책을 이미 구성한  경우 이러한 정책은 항상 기본 제공 보호 전에 적용되기 때문에 이러한 기존 미리 설정한 정책이나 사용자 지정 정책에 이미 정의된 받는 사람에게는 아무 영향도 없습니다. 

## <a name="assign-preset-security-policies-to-users"></a>미리 설정한 보안 정책을 사용자에게 할당

### <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다. 미리 설정 보안 정책 페이지로 직접 **이동하기 위해** 를 <https://security.microsoft.com/presetSecurityPolicies> 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.
  - 미리 설정한 보안 정책을 구성하려면 조직 관리  또는 보안 관리자 역할 그룹의 **구성원이** 해야 합니다.
  - 미리 설정한 보안 정책에 대한 읽기 전용 액세스의 경우 전역 읽기 전용 역할 그룹의 **구성원이** 해야 합니다.

  자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  **참고:** Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 역할의 다른 기능에 필요한  사용 권한 및 사용 권한이 Microsoft 365. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

### <a name="use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users"></a>Microsoft 365 Defender 포털을 사용하여 사용자에게 표준 및 엄격한 미리 설정 보안 정책을 할당합니다.

1. Microsoft 365 Defender 포털의 템플릿 기반 정책  섹션에서 전자 메일 & 공동 작업 정책 & 규칙 위협 정책 미리 설정 보안 \>  \>  \>  **정책 섹션으로** 이동하십시오.

2. 보안 정책 사전 **설정** 페이지에서  표준  보호 또는 엄격한 보호 섹션에서 **관리를** 클릭합니다.

3. 표준 **보호 적용 또는** 엄격한 보호 적용 **마법사가** 플라이아웃에서 시작됩니다. **EOP 보호가** 페이지에 적용됨 페이지에서 [EOP](#policies-in-preset-security-policies) 보호가 적용되는 내부 받는 사람을 식별합니다(받는 사람 조건).
   - **사용자**
   - **그룹**
   - **도메인**

   적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다. 이 프로세스를 필요한 만큼 반복합니다. 기존 값을 제거하려면 제거를 클릭합니다. ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 값 옆에 있습니다.

   사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다. 사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.

   - **다음 사용자, 그룹 및 도메인 제외**: 해당 정책의 적용 대상인 내부의 받는 사람에게 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다. 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. Office 365 조직용 Microsoft Defender에서는 Office 365 보호를 위한 [Defender로](#policies-in-preset-security-policies) 이동하여 microsoft **Defender for** Office 365 보호가 적용되는 내부 받는 사람을 식별합니다(받는 사람 조건).

   설정 및 동작은 이전 단계에서 **페이지에 적용되는 EOP** 보호와 정확히 같습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. 변경 **내용 검토 및 확인 페이지에서** 선택 사항을 확인하고 확인을 **클릭합니다.**

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-standard-and-strict-preset-security-policies"></a>기본 Microsoft 365 Defender 사용하여 표준 및 엄격한 미리 설정 보안 정책의 할당 수정

**표준** 보호 또는 **엄격한** 보호 미리 설정 보안 정책의 할당을 수정하는 단계는 미리 설정한 보안 정책을 사용자에게 처음 할당할 때와 [동일합니다.](#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users)

표준 보호 **또는** **엄격한** 보호는 기존 조건 및 예외를 보존하면서 보안 정책을 미리 설정하지 않도록 설정하고, 토글을 **사용** 안 하게 토글 해제로 ![ 밀어 끄기합니다. ](../../media/scc-toggle-off.png) 정책을 사용하도록 설정하려면 토글을 사용 토글 **으로** ![ 밀어 으로 끄면 ](../../media/scc-toggle-on.png) 됩니다.

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-the-built-in-protection-preset-security-policy"></a>기본 Microsoft 365 Defender 포털을 사용하여 기본 제공 보호 미리 설정 보안 정책의 할당 수정

기본 제공  보호 미리 설정 보안 정책은 모든 받는 사람에게 할당되고 **Standard protection** 또는 Strict **protection** 미리 설정 보안 정책 또는 사용자 지정 금고 링크 또는 첨부 파일 정책에 정의된 금고 영향을 주지 않습니다.

따라서 기본 제공 보호 미리 설정  보안 정책에 대한 예외는 일반적으로 권장하지 않습니다.

1. Microsoft 365 Defender 포털의 템플릿 기반 정책  섹션에서 전자 메일 & 공동 작업 정책 & 규칙 위협 정책 미리 설정 보안 \>  \>  \>  **정책 섹션으로** 이동하십시오.

2. 보안 정책 **사전 설정** 페이지에서  기본 제공 보호 섹션에서 제외 추가(권장하지 **않음)를** 선택합니다.

3. 기본  제공 보호에서 제외 플라이아웃이 표시될 때 기본 제공 금고 및 첨부 파일 보호에서 제외된 금고 식별합니다.
   - **사용자**
   - **그룹**
   - **도메인**

   적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다. 이 프로세스를 필요한 만큼 반복합니다. 기존 값을 제거하려면 제거를 클릭합니다. ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 값 옆에 있습니다.

   사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다. 사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.

   작업을 마쳤으면 **저장** 을 클릭합니다.

### <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

사용자에게 표준 보호 또는 엄격한  보호 보안  정책이 할당되어 있는지 확인하기 위해 기본값이 표준 보호  설정과 다른 보호 설정을 사용해야 합니다. 이는 **Strict protection** 설정과 다릅니다.

예를 들어 스팸으로 검색된 전자 메일(높은 지수 스팸 아님)의 경우 표준  보호 사용자를 위해 메시지가 정크  메일 폴더로 배달되고 고급 보호 사용자에 대해 검역됩니다.

또는 대량 [](bulk-complaint-level-values.md)메일의 경우 BCL 값 6 이상이 **표준** 보호 사용자를 위해 메시지를 정크 메일 폴더로 배달하고 BCL 값 4 이상이 **엄격한** 보호 사용자에 대한 메시지를 차단하는지 확인합니다.
