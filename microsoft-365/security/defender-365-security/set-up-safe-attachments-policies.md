---
title: Microsoft Defender for Office 365에서 안전한 첨부 파일 정책 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 전자 메일의 악의적인 파일로부터 조직을 보호하기 위해 안전한 첨부 파일 정책을 정의하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e96babff19ea981b953d35929813b1e08c000e32
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071199"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365에서 안전한 첨부 파일 정책 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 이 문서는 [Office 365용 Microsoft Defender](whats-new-in-defender-for-office-365.md)가 있는 비즈니스 고객을 대상으로 합니다. Outlook에서 첨부 파일 검색에 대한 정보를 찾고 있는 가정용 사용자는 고급 보안 [Outlook.com 참조하세요.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

안전한 첨부 파일은 [EOP(Exchange Online](anti-malware-protection.md)Protection)에서 맬웨어 방지 보호를 통해 검색된 후 받는 사람에게 배달되기 전에 가상 환경을 사용하여 인바운드 전자 메일 메시지의 첨부 파일을 검사하는 [Microsoft Defender for Office 365의](whats-new-in-defender-for-office-365.md) 기능입니다. 자세한 내용은 [Microsoft Defender for Office 365의](safe-attachments.md)안전한 첨부 파일을 참조하세요.

기본 제공 또는 기본 안전 첨부 파일 정책이 없습니다. 전자 메일 메시지 첨부 파일에 대한 안전한 첨부 파일 검색을 사용하려면 이 문서에 설명된 하나 이상의 안전 첨부 파일 정책을 만들어야 합니다.

보안 & 준수 센터 또는 PowerShell에서 안전한 첨부 파일 정책을 구성할 수 있습니다(Exchange Online에 사서함이 있는 적격 Microsoft 365 조직의 경우 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell, Office 365 추가 기능 구독의 경우 Defender 사용).

안전한 첨부 파일 정책의 기본 요소는 다음입니다.

- **안전한** 첨부 파일 정책: 알 수 없는 맬웨어 검색에 대한 작업, 맬웨어 첨부 파일이 있는 메시지를 지정된 전자 메일 주소로 보낼지 여부 및 안전한 첨부 파일 검색을 완료할 수 없는 경우 메시지를 배달할지 여부를 지정합니다.
- **안전한 첨부 파일 규칙:** 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.

보안 및 준수 센터에서 안전 첨부 파일 & 두 요소의 차이는 명확하지 않습니다.

- 안전한 첨부 파일 정책을 만들 때 실제로 동일한 이름을 사용하여 안전한 첨부 파일 규칙과 연결된 안전한 첨부 파일 정책을 동시에 만들게 됩니다.
- 안전 첨부 파일 정책을 수정할 때 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 안전한 첨부 파일 규칙을 수정합니다. 다른 모든 설정은 연결된 안전한 첨부 파일 정책을 수정합니다.
- 안전 첨부 파일 정책을 제거하면 안전한 첨부 파일 규칙 및 연결된 안전한 첨부 파일 정책이 제거됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다. 자세한 내용은 이 문서 부분의 Exchange Online PowerShell 또는 독립 실행형 [EOP PowerShell을](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 사용하여 안전한 첨부 파일 정책 구성 섹션을 참조하세요.

> [!NOTE]
> 안전 첨부 파일 설정의 전역 설정 영역에 있는 안전 첨부 파일 정책에 종속되지 않는 기능을 구성합니다. 지침은 [Microsoft 365 E5에서](safe-docs.md) [SharePoint, OneDrive 및 Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) 및 안전한 문서에 대한 안전한 첨부 파일 켜기 를 참조하세요.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 안전한 첨부 파일 페이지로 직접 **이동하기 위해** 를 <https://protection.office.com/safeattachmentv2> 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다.
  - 안전한 첨부 파일 정책을 만들고 수정하고 삭제하려면 보안 &  준수 센터에서 조직 관리 또는 보안 관리자  역할 그룹의 구성원이자 Exchange Online의 조직 관리 역할 그룹의 구성원이 되어야 합니다.  
  - 안전 첨부 파일 정책에 대한 읽기 전용 액세스 권한을  사용하려면  보안 및 준수 센터에서 전역 읽기 & 역할 그룹의 구성원이 되어야 합니다.

  자세한 내용은 [Security & Compliance Center의](permissions-in-the-security-and-compliance-center.md) 사용 권한 및 Exchange Online의 사용 권한을 [참조하세요.](/exchange/permissions-exo/permissions-exo)

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.

- 안전한 첨부 파일 정책에 대한 권장 설정은 안전 첨부 파일 [설정을 참조하세요.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- 새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>보안 및 & 센터를 사용하여 안전한 첨부 파일 정책 만들기

보안 & 준수 센터에서 사용자 지정 안전 첨부 파일 정책을 만들면 동일한 이름을 사용하여 안전한 첨부 파일 규칙과 연결된 안전한 첨부 파일 정책을 동시에 만듭니다.

1. 보안 및 & 센터에서 **위협** 관리 정책 \>  \> **ATP 안전한 첨부 파일로 이동하십시오.**

2. 안전한 **첨부 파일 페이지에서** 만들기를 **클릭합니다.**

3. 새 **안전 첨부 파일 정책 마법사가** 열립니다. 정책 **이름 지정 페이지에서** 다음 설정을 구성합니다.

   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다.

   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. 설정 **페이지가** 나타나면 다음 설정을 구성합니다.

   - 안전한 첨부 파일 알 수 **없는 맬웨어 응답:** 다음 값 중 하나를 선택합니다.

     - **Off:** 일반적으로 이 값은 권장되지 않습니다.
     - **모니터**
     - **Block**: 이 값은 기본값으로, Standard 및 Strict 미리 설정 보안 정책의 [권장 값입니다.](preset-security-policies.md)
     - **바꾸기**
     - **동적 배달(미리 보기 기능)**

     이러한 값은 안전 첨부 파일 정책 [설정 에 설명됩니다.](safe-attachments.md#safe-attachments-policy-settings)

   - 다음 전자 메일 주소로 첨부 파일 **보내기:** 작업 값 **차단,** 모니터링 또는 바꾸기 에 대해 맬웨어 첨부 파일이 포함된 메시지를 분석 및 조사를 위해 지정된 내부 또는 외부 전자 메일 주소로 보내기 위해 리디렉션 사용 을 선택할 수 있습니다.  

     표준 및 엄격한 정책 설정에 대한 권장은 리디렉션을 사용하도록 설정하는 것입니다. 자세한 내용은 안전 첨부 파일 [설정을 참조하세요.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

   - **첨부 파일에** 대한 맬웨어 검색의 시간이 멀거나 오류가  발생하는 경우 위의 선택을 적용합니다. 안전한 첨부 파일 검색을 완료할 수 없는 경우에도 메시지에 대해 안전한 첨부 파일 알 수 없는 맬웨어 응답으로 지정된 작업이 수행됩니다. 이 옵션을 선택한 경우 항상 리디렉션 **사용 을 선택합니다.** 그렇지 않으면 메시지가 손실될 수 있습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. 적용 **대상** 페이지가 나타나면 정책이 적용되는 내부 받는 사람을 식별합니다.

   조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

   조건 **추가를 클릭합니다.** 나타나는 드롭다운에서 적용된 조건(있는 **경우)을 선택합니다.**

   - **받는 사람:** 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.
   - **받는 사람이 :의 구성원입니다.** 조직에서 하나 이상의 그룹을 지정합니다.
   - **받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.

   조건을 선택하면 해당 드롭다운이 다음 상자와 **함께** 나타납니다.

   - 상자를 클릭하고 선택할 값 목록을 스크롤합니다.
   - 상자를 클릭하고 입력을 시작하여 목록을 필터링하고 값을 선택합니다.
   - 값을 더 추가하려면 상자의 빈 영역을 클릭합니다.
   - 개별 항목을 제거하려면 값에서 **제거** ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.
   - 전체 조건을 제거하려면 **조건에서** 제거 ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.

   조건을 더 추가하려면 조건 추가를 **클릭하고** 적용된 경우 아래에서 나머지 **값을 선택합니다.**

   예외를 추가하려면 조건 추가를 **클릭하고** 다음의 경우 **제외에서 예외를 선택합니다.** 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

6. 나타나는 **설정** 검토 페이지에서 설정을 검토합니다. 각 설정에서 **편집을** 클릭하여 수정할 수 있습니다.

   완료되면 마친 을 **클릭합니다.**

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>보안 및 & 센터를 사용하여 안전한 첨부 파일 정책 보기

1. 보안 및 & 센터에서 **위협** 관리 정책 \>  \> **ATP 안전한 첨부 파일로 이동하십시오.**

2. 안전 **첨부 파일** 페이지에서 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).

   정책 세부 정보가 플라이아웃에 표시됩니다.

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>보안 및 & 센터를 사용하여 안전한 첨부 파일 정책 수정

1. 보안 및 & 센터에서 **위협** 관리 정책 \>  \> **ATP 안전한 첨부 파일로 이동하십시오.**

2. 안전 **첨부 파일** 페이지에서 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).

3. 정책 세부 정보 플라이아웃이 나타나면 정책 편집 **을 클릭합니다.**

플라이아웃에서 사용할 수 있는 설정은 보안 및 준수 센터를 사용하여 안전한 첨부 파일 정책 & 설명된 설정과 [동일합니다.](#use-the-security--compliance-center-to-create-safe-attachments-policies)

정책을 사용하도록 설정하거나 사용하지 않도록 설정하거나 정책 우선 순위를 설정하려면 다음 섹션을 참조하세요.

### <a name="enable-or-disable-safe-attachments-policies"></a>안전 첨부 파일 정책 사용 또는 사용 안 하도록 설정

1. 보안 및 & 센터에서 **위협** 관리 정책 \>  \> **ATP 안전한 첨부 파일로 이동하십시오.**

2. 상태 열의 **값을 확인할 수** 있습니다.

   - 토글을 왼쪽으로 이동 ![정책 끄기](../../media/scc-toggle-off.png) 을(를) 사용하지 않도록 설정해야 합니다.

   - 토글을 오른쪽으로 이동 ![정책 켜기](../../media/scc-toggle-on.png) 를 사용하여 정책을 사용하도록 설정할 수 있습니다.

### <a name="set-the-priority-of-safe-attachments-policies"></a>안전 첨부 파일 정책의 우선 순위 설정

기본적으로 안전한 첨부 파일 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.

안전한 첨부 파일 정책은 처리되는 순서대로 표시됩니다(첫 번째  정책의 우선 순위 값은 0).

**참고:** 보안 & 준수 센터에서 안전 첨부 파일 정책의 우선 순위를 변경한 후에만 변경할 수 있습니다. PowerShell에서 안전한 첨부 파일 규칙을 만들 때 기본 우선 순위를 다시 정할 수 있습니다(기존 규칙의 우선 순위에 영향을 줄 수 있습니다).

정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.

1. 보안 및 & 센터에서 **위협** 관리 정책 \>  \> **ATP 안전한 첨부 파일로 이동하십시오.**

2. 안전 **첨부 파일** 페이지에서 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).

3. 정책 세부 정보 플라이아웃이 나타나면 사용 가능한 우선 순위 단추를 클릭합니다.

   - 우선 순위 값이 **0인** 안전 첨부 파일 정책에는 우선 순위 감소 **단추만** 사용할 수 있습니다. 

   - 우선 순위 값이 가장  낮은 안전 첨부 파일 정책(예: **3)에는** 사용 가능한 우선 순위 늘리기 **단추만** 있습니다.

   - 안전 첨부 파일 정책이 세 개 이상 있는 경우 우선 순위가 가장 높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 단추를 모두 사용할 **수** 있습니다. 

4. 우선 **순위 늘리기 또는** **우선** 순위 감소를 클릭하여 우선 순위 값을 **변경합니다.**

5. 작업을 마쳤으면 **닫기** 를 클릭합니다.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>보안 및 & 센터를 사용하여 안전한 첨부 파일 정책 제거

1. 보안 및 & 센터에서 **위협** 관리 정책 \>  \> **ATP 안전한 첨부 파일로 이동하십시오.**

2. 안전 **첨부 파일** 페이지에서 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).

3. 정책 세부 정보 플라이아웃이 나타나면 정책 삭제를  클릭한 다음 나타나는 경고 대화 상자에서 예를 클릭합니다. 

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 안전한 첨부 파일 정책 구성

앞서 설명한 바와 같이 안전한 첨부 파일 정책은 안전한 첨부 파일 정책과 안전한 첨부 파일 규칙으로 구성됩니다.

PowerShell에서는 안전한 첨부 파일 정책과 안전한 첨부 파일 규칙의 차이점이 분명합니다. **\* -SafeAttachmentPolicy** cmdlet을 사용하여 안전한 첨부 파일 정책을 관리하고 **\* -SafeAttachmentRule** cmdlet을 사용하여 안전한 첨부 파일 규칙을 관리합니다.

- PowerShell에서 먼저 안전한 첨부 파일 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 안전한 첨부 파일 규칙을 생성합니다.
- PowerShell에서는 안전한 첨부 파일 정책 및 안전한 첨부 파일 규칙의 설정을 별도로 수정합니다.
- PowerShell에서 안전한 첨부 파일 정책을 제거하면 해당 안전 첨부 파일 규칙이 자동으로 제거되지 않습니다.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell을 사용하여 안전한 첨부 파일 정책 만들기

PowerShell에서 안전한 첨부 파일 정책을 만드는 과정은 다음 두 단계로 진행됩니다.

1. 안전한 첨부 파일 정책을 만들 수 있습니다.
2. 규칙이 적용되는 안전한 첨부 파일 정책을 지정하는 안전한 첨부 파일 규칙을 만들 수 있습니다.

 **참고:**

- 새 안전한 첨부 파일 규칙을 만들고 연결되지 않은 기존 안전 첨부 파일 정책을 할당할 수 있습니다. 안전한 첨부 파일 규칙은 두 개 이상의 안전한 첨부 파일 정책과 연결될 수 없습니다.

- 정책을 만든 후에야 보안 및 준수 센터에서 사용할 수 & PowerShell의 새 안전한 첨부 파일 정책에 대해 다음 설정을 구성할 수 있습니다.
  - 새 정책을 사용하지 않도록 `$false` **설정합니다(New-SafeAttachmentRule** cmdlet에서 사용).
  -  _\<Number\>_ **New-SafeAttachmentRule** cmdlet에서 만들 때 정책의 우선 순위( 우선 순위)를 설정하십시오.

- PowerShell에서 만든 새 안전한 첨부 파일 정책은 안전한 첨부 파일 규칙에 정책을 할당할 때까지 & 준수 센터에 표시되지 않습니다.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>1단계: PowerShell을 사용하여 안전한 첨부 파일 정책 만들기

안전한 첨부 파일 정책을 만들 수 있도록 다음 구문을 사용 합니다.

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

이 예에서는 다음 값을 가지는 Contoso All이라는 안전한 첨부 파일 정책을 만듭니다.

- 안전한 문서 검사에서 맬웨어를 포함하는 것으로 확인된 메시지를 _차단합니다(Action_ 매개 변수를 사용하지는 않습니다. 기본값은 `Block` 입니다).
- 리디렉션이 사용하도록 설정되어 있으며 맬웨어가 포함된 것으로 확인된 메시지는 분석 및 조사를 위해 sec-ops@contoso.com 전송됩니다.
- 안전 첨부 파일 검색을 사용할 수 없는 경우 또는 오류가 발생하는 경우 메시지를 배달하지 _않습니다(ActionOnError_ 매개 변수를 사용하지 않습니다. 기본값은 `$true` 입니다).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

구문과 매개 변수에 대한 자세한 내용은 [New-SafeAttachmentPolicy를 참조하십시오.](/powershell/module/exchange/new-safeattachmentpolicy)

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>2단계: PowerShell을 사용하여 안전한 첨부 파일 규칙 만들기

안전한 첨부 파일 규칙을 만들 수 있도록 다음 구문을 사용 합니다.

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

이 예에서는 다음 조건을 통해 Contoso All이라는 안전한 첨부 파일 규칙을 만듭니다.

- 이 규칙은 Contoso All이라는 안전한 첨부 파일 정책과 연결됩니다.
- 이 규칙은 도메인의 모든 받는 사람에게 contoso.com 적용됩니다.
- Priority 매개 변수를  사용하지 않을 것이기 때문에 기본 우선 순위가 사용됩니다.
- 이 규칙은 사용하도록 설정됩니다(Enabled  매개 변수를 사용하지 않습니다. 기본값은 `$true` 입니다).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

구문과 매개 변수에 대한 자세한 내용은 [New-SafeAttachmentRule을 참조하십시오.](/powershell/module/exchange/new-safeattachmentrule)

### <a name="use-powershell-to-view-safe-attachment-policies"></a>PowerShell을 사용하여 안전한 첨부 파일 정책 보기

기존의 안전한 첨부 파일 정책을 보시고 다음 구문을 사용하시기 바랍니다.

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예에서는 모든 안전한 첨부 파일 정책의 요약 목록을 반환합니다.

```PowerShell
Get-SafeAttachmentPolicy
```

이 예에서는 Contoso Executives라는 안전 첨부 파일 정책에 대한 자세한 정보를 반환합니다.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

구문과 매개 변수에 대한 자세한 내용은 [Get-SafeAttachmentPolicy를 참조하십시오.](/powershell/module/exchange/get-safeattachmentpolicy)

### <a name="use-powershell-to-view-safe-attachment-rules"></a>PowerShell을 사용하여 안전한 첨부 파일 규칙 보기

기존의 안전한 첨부 파일 규칙을 보시고 다음 구문을 사용하시기 바랍니다.

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예에서는 모든 안전한 첨부 파일 규칙의 요약 목록을 반환합니다.

```PowerShell
Get-SafeAttachmentRule
```

활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

이 예에서는 Contoso Executives라는 안전한 첨부 파일 규칙에 대한 자세한 정보를 반환합니다.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

구문과 매개 변수에 대한 자세한 내용은 [Get-SafeAttachmentRule 을 참조하십시오.](/powershell/module/exchange/get-safeattachmentrule)

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>PowerShell을 사용하여 안전한 첨부 파일 정책 수정

PowerShell에서 안전한 첨부 파일 정책의 이름을 다시 설정할 수 **없습니다(Set-SafeAttachmentPolicy** cmdlet에는 _Name_ 매개 변수가 없음). 보안 및 준수 센터에서 안전한 첨부 파일 정책의 이름을 & 안전한 첨부 파일 규칙의 이름만 다시 _매기게 됩니다._

그렇지 않으면 이 문서 앞부분의 [1단계: PowerShell을](#step-1-use-powershell-to-create-a-safe-attachment-policy) 사용하여 안전한 첨부 파일 정책 만들기 섹션에 설명된 대로 안전한 첨부 파일 정책을 만들 때 동일한 설정을 사용할 수 있습니다.

안전한 첨부 파일 정책을 수정하려면 다음 구문을 사용 합니다.

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentPolicy를 참조하십시오.](/powershell/module/exchange/set-safeattachmentpolicy)

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell을 사용하여 안전한 첨부 파일 규칙 수정

PowerShell에서 안전한 첨부 파일 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용되지 않는 규칙을 만들 수 있는 _Enabled_ 매개 변수뿐입니다. 기존 안전 첨부 파일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.

그렇지 않으면 이 문서 앞부분의 [2단계: PowerShell을](#step-2-use-powershell-to-create-a-safe-attachment-rule) 사용하여 안전한 첨부 파일 규칙 만들기 섹션에 설명된 대로 규칙을 만들 때 동일한 설정을 사용할 수 있습니다.

안전한 첨부 파일 규칙을 수정하려면 다음 구문을 사용 합니다.

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentRule을 참조하십시오.](/powershell/module/exchange/set-safeattachmentrule)

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell을 사용하여 안전한 첨부 파일 규칙을 사용 또는 사용하지 않도록 설정

PowerShell에서 안전한 첨부 파일 규칙을 설정하거나 사용하지 않도록 설정하면 전체 안전 첨부 파일 정책(안전한 첨부 파일 규칙 및 할당된 안전한 첨부 파일 정책)을 활성화하거나 사용하지 않도록 설정할 수 있습니다.

PowerShell에서 안전한 첨부 파일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

이 예에서는 Marketing Department라는 안전 첨부 파일 규칙을 사용하지 않도록 설정합니다.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) 및 [Disable-SafeAttachmentRule을 참조하십시오.](/powershell/module/exchange/disable-safeattachmentrule)

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>PowerShell을 사용하여 안전한 첨부 파일 규칙의 우선 순위 설정

규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다. 설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다. 예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다. 기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다. 예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.

PowerShell에서 안전한 첨부 파일 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다. 우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**참고:** 새 규칙을 만들 때 새 규칙의 우선  순위를 설정하기 위해 **New-SafeAttachmentRule** cmdlet에서 Priority 매개 변수를 대신 사용합니다.

구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentRule을 참조하십시오.](/powershell/module/exchange/set-safeattachmentrule)

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>PowerShell을 사용하여 안전한 첨부 파일 정책 제거

PowerShell을 사용하여 안전한 첨부 파일 정책을 제거하면 해당 안전 첨부 파일 규칙이 제거되지 않습니다.

PowerShell에서 안전한 첨부 파일 정책을 제거하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

이 예에서는 Marketing Department라는 안전 첨부 파일 정책을 제거합니다.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeAttachmentPolicy를 참조하십시오.](/powershell/module/exchange/remove-safeattachmentpolicy)

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>PowerShell을 사용하여 안전한 첨부 파일 규칙 제거

PowerShell을 사용하여 안전한 첨부 파일 규칙을 제거하면 해당 안전 첨부 파일 정책이 제거되지 않습니다.

PowerShell에서 안전한 첨부 파일 규칙을 제거하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

이 예에서는 Marketing Department라는 안전 첨부 파일 규칙을 제거합니다.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeAttachmentRule 을 참조하십시오.](/powershell/module/exchange/remove-safeattachmentrule)

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

안전한 첨부 파일 정책을 성공적으로 만들거나 수정하거나 제거한 경우 다음 단계를 수행하십시오.

- 보안 및 & 센터에서 **위협** 관리 정책 \>  \> **ATP 안전한 첨부 파일로 이동하십시오.** 정책 목록, 해당 **상태 값** 및 우선 순위 값을 **검증합니다.** 자세한 내용을 확인하려면 목록에서 정책을 선택하고 플라이아웃에서 세부 정보를 하세요.

- Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 설정을 \<Name\> 확인합니다.

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

안전한 첨부 파일이 메시지를 검사하는지 확인하기 위해 사용 가능한 Defender for Office 365 보고서를 확인 합니다. 자세한 내용은 [Office 365용 Defender에](view-reports-for-mdo.md) 대한 보고서 보기 및 보안 및 준수 센터에서 [탐색기 & 참조하세요.](threat-explorer.md)
