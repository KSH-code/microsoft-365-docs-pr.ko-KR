---
title: Microsoft Defender에서 금고 첨부 파일 정책 설정 Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 전자 메일의 악성 금고 보호하기 위해 첨부 파일 정책을 정의하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3ae702417d34351c99ccbd8432c2fc29f11a433f
ms.sourcegitcommit: 7b83e2605895fee5c73cd1d01f4cd16e1457a69f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60907941"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender에서 금고 첨부 파일 정책 설정 Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 이 문서는 [Office 365용 Microsoft Defender](whats-new-in-defender-for-office-365.md)가 있는 비즈니스 고객을 대상으로 합니다. 가정용 사용자인 경우 Outlook 고급 [Outlook.com 보안 을 참조하세요.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

금고 첨부 파일은 [EOP(Exchange Online Protection)에서](whats-new-in-defender-for-office-365.md) 맬웨어 방지 보호를 통해 검색된 후 받는 사람에게 배달되기 전에 [](anti-malware-protection.md)가상 환경을 사용하여 인바운드 전자 메일 메시지의 첨부 파일을 검사하는 Office 365 Microsoft Defender의 기능입니다. 자세한 내용은 microsoft [Defender에서](safe-attachments.md)금고 첨부 파일을 Office 365.

기본 금고 첨부 파일 정책은 있지만 기본  제공 보호 미리 설정 보안 정책은 모든 받는 사람(사용자 지정 금고 첨부 파일 정책에 정의되지 않은 사용자)에게 금고 첨부 파일 보호를 제공합니다. 자세한 내용은 EOP에서 보안 정책 미리 설정 및 Microsoft [Defender for Office 365.](preset-security-policies.md) 이 문서의 절차에 따라 특정 사용자, 그룹 또는 도메인에 금고 첨부 파일 정책을 만들 수도 있습니다.

Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online PowerShell)에서 Microsoft 365 사서함이 있는 Microsoft 365 조직에 대해 Exchange Online 첨부 파일 정책을 구성할 수 있습니다. 없는 조직의 경우 독립 실행형 EOP PowerShell을 사용할 수 있습니다. 금고 Exchange Online 추가 기능 구독용 Defender를 Office 365)

첨부 파일 정책의 금고 요소는 다음입니다.

- **안전한** 첨부 파일 정책: 알 수 없는 맬웨어 검색에 대한 작업, 맬웨어 첨부 파일이 첨부된 메시지를 지정된 전자 메일 주소로 보낼지 여부, 금고 첨부 파일 검색을 완료할 수 없는 경우 메시지를 배달할지 여부를 지정합니다.
- **안전한 첨부 파일 규칙:** 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.

이러한 두 요소 간의 차이는 금고 포털에서 첨부 파일 정책을 관리할 때 명확하지 Microsoft 365 Defender 않습니다.

- 첨부 파일 금고 만들면 실제로 동일한 이름을 사용하여 안전한 첨부 파일 규칙과 연결된 안전한 첨부 파일 정책을 동시에 만들게 됩니다.
- 첨부 파일 정책을 금고, 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 안전한 첨부 파일 규칙을 수정합니다. 다른 모든 설정은 연결된 안전한 첨부 파일 정책을 수정합니다.
- 첨부 파일 금고 제거하면 안전한 첨부 파일 규칙 및 연결된 안전한 첨부 파일 정책이 제거됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다. 자세한 내용은 이 문서의 Exchange Online PowerShell 또는 독립 실행형 [EOP PowerShell을](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 사용하여 금고 첨부 파일 정책 구성 섹션을 참조하세요.

> [!NOTE]
> 첨부 파일 설정의 전역 설정 금고 첨부 파일 정책에 종속되지 않는 금고 구성합니다. 자세한 내용은 [금고 에서 SharePoint,](turn-on-mdo-for-spo-odb-and-teams.md) OneDrive 및 Microsoft Teams 금고 [문서에](safe-docs.md)대한 첨부 파일 Microsoft 365 E5.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다. 첨부 파일 **페이지로** 직접 금고 를 <https://security.microsoft.com/safeattachmentv2> 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 먼저 사용 권한이 필요합니다.
  - 금고 첨부 파일 정책을 만들고 수정하고 삭제하려면 Microsoft 365 Defender 포털에서 조직 관리 또는  보안 관리자 역할 그룹의 구성원이자 조직의  조직 관리 역할 그룹의 구성원이 Exchange Online.  
  - 첨부 파일 정책에 금고 읽기 전용으로 액세스하려면 Microsoft 365 Defender 포털에서  전역  읽기 그룹 또는 보안 읽기 Microsoft 365 Defender 합니다.

  자세한 내용은 Microsoft 365 Defender [포털의](permissions-microsoft-365-security-center.md) 사용 권한 및 [Exchange Online.](/exchange/permissions-exo/permissions-exo)

  **참고:**

  - Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 포털에서 필요한 사용 권한 및 Microsoft 365 Defender 포털의  다른 기능에 대한 사용 권한이 Microsoft 365. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.

- 첨부 파일 정책에 대한 권장 금고 첨부 파일 금고 [참조하세요.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- 새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>Microsoft 365 Defender 포털을 사용하여 첨부 파일 금고 만들기

Microsoft 365 Defender 포털에서 사용자 지정 금고 첨부 파일 정책을 만들면 동일한 이름을 사용하여 안전한 첨부 파일 규칙과 연결된 안전한 첨부 파일 정책이 동시에 생성됩니다.

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 금고 정책으로 \>  \>  \>  이동하세요. 

2. 첨부 **금고 페이지에서** 만들기 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **만들기**.

3. 정책 마법사가 열립니다. 정책 **이름 지정 페이지에서** 다음 설정을 구성합니다.
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

   - **다음 사용자, 그룹 및 도메인 제외**: 정책이 적용되는 내부 받는 사람에 대한 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다. 설정 및 동작은 조건과 정확히 같습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. 설정 **페이지에서** 다음 설정을 구성합니다.

   - 금고 알 수 없는 **맬웨어 응답**: 다음 값 중 하나를 선택합니다.
     - **Off:** 일반적으로 이 값은 권장되지 않습니다.
     - **모니터링**
     - **Block**: 이 값은 기본값으로, Standard 및 Strict 미리 설정 보안 정책의 [권장 값입니다.](preset-security-policies.md)
     - **바꾸기**
     - **동적 배달(미리 보기 기능)**

     이러한 값은 첨부 파일 [정책 금고 설명되어 있습니다.](safe-attachments.md#safe-attachments-policy-settings)

   - **Quarantine policy**: 금고 Attachments(차단, 바꾸기 또는 동적 배달)에 의해 검역되는 메시지에 적용되는 금고 **정책을 선택합니다.** Quarantine policies define what users are able to do to quarantined messages, and whether users receive quarantine notifications. 자세한 내용은 [격리 정책](quarantine-policies.md)을 참조하세요.

     값을 비워 두면 기본 검지 정책이 사용됩니다(첨부 파일에서 전자 메일 검색을 위한 AdminOnlyAccessPolicy를 금고). 나중에 첨부 파일 금고 편집하거나 설정을 볼 때 기본 검지 정책 이름이 표시됩니다.

   - **검색된** 첨부 파일이 있는 메시지 리디렉션: 리디렉션 사용 을 선택하면 지정된 전자 메일 주소 상자에 **차단,** 모니터링 또는 대체된 첨부 파일이 포함된 전자 메일 주소를 지정하여 분석 및 조사를 위해 맬웨어 첨부 파일이 포함된 메시지를 보낼 수 있습니다. 

     표준 및 엄격한 정책 설정에 대한 권장은 리디렉션을 사용하도록 설정하는 것입니다. 자세한 내용은 첨부 [파일 금고 참조하세요.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

   - **검색을** 완료할 수 없는 경우(시간 제한 또는 오류) 금고 금고 첨부 파일  검색 응답 적용 : 첨부 파일 검색을 완료할 수 없는 경우에도 금고 첨부 파일 알 수 없는 맬웨어 응답이 메시지에 대해 수행됩니다. 이 옵션을 선택한 경우  항상 리디렉션 사용 을 선택하고 맬웨어 첨부 파일이 포함된 메시지를 보낼 전자 메일 주소를 지정합니다. 그렇지 않으면 메시지가 손실될 수 있습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

6. 표시되는 **검토** 페이지에서 설정을 검토합니다. 각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다. 또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.

   작업을 마쳤으면 **제출** 을 클릭합니다.

7. 표시되는 확인 페이지에서 **완료** 를 클릭합니다.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>Microsoft 365 Defender 포털을 사용하여 첨부 파일 금고 보기

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 금고 정책으로 \>  \>  \>  이동하세요. 

2. 첨부 **금고** 페이지에 다음 속성이 정책 목록에 표시됩니다.
   - **이름**
   - **상태**
   - **우선 순위**

3. 이름을 클릭하여 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>Microsoft 365 Defender 포털을 사용하여 첨부 파일 금고 수정

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 금고 정책으로 \>  \>  \>  이동하세요. 

2. 첨부 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.

3. 표시되는 정책 세부 정보 플라이아웃에서 각 섹션에서 **편집** 을 선택하여 섹션 내의 설정을 수정합니다. 설정에 대한 자세한 내용은 [](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) 이 문서 앞부분의 Microsoft 365 Defender 포털을 사용하여 금고 정책 만들기 섹션을 참조하십시오.

정책을 사용하거나 사용하지 않도록 설정하거나 정책 우선 순위 순서를 설정하려면 다음 섹션을 참조하세요.

### <a name="enable-or-disable-safe-attachments-policies"></a>첨부 파일 금고 사용 또는 사용 안 하도록 설정

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 금고 정책으로 \>  \>  \>  이동하세요. 

2. 첨부 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.

3. 표시되는 정책 세부 정보 플라이아웃 맨 위에 다음 값 중 하나가 표시됩니다.
   - **정책 꺼짐**: 정책을 켜려면 ![켜기 아이콘.](../../media/m365-cc-sc-turn-on-off-icon.png) **켜기** 를 클릭합니다.
   - **정책 켜짐**: 정책을 끄려면 ![끄기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **끄기** 를 클릭합니다.

4. 표시되는 확인 대화 상자에서 **켜기** 또는 **끄기** 를 클릭합니다.

5. 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.

기본 정책 페이지로 돌아가면 정책의 **상태** 값이 **켜짐** 또는 **꺼짐** 입니다.

### <a name="set-the-priority-of-safe-attachments-policies"></a>첨부 파일 정책의 금고 우선 순위 설정

기본적으로 금고 첨부 파일 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.

금고 첨부 파일 정책은 처리되는 순서대로 표시됩니다(첫 번째  정책의 우선 순위 값은 0).

**참고:** Microsoft 365 Defender 포털에서 첨부 파일 정책을 만든 금고 정책의 우선 순위만 변경할 수 있습니다. PowerShell에서 안전한 첨부 파일 규칙을 만들 때 기본 우선 순위를 다시 정할 수 있습니다(기존 규칙의 우선 순위에 영향을 줄 수 있습니다).

정책의 우선 순위를 변경하려면 정책 속성에서 **우선 순위를 높이거나** **우선 순위를 낮춥니다**(Microsoft 365 Defender 포털에서 **우선 순위** 번호를 직접 수정할 수 없습니다). 정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우에만 의미가 있습니다.

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 금고 정책으로 \>  \>  \>  이동하세요. 

2. 첨부 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.

3. 정책 세부 정보 플라이아웃이 나타나면 현재 우선  순위 값  및 정책 수에 따라 우선 순위 늘리기 또는 우선 순위 감소가 표시됩니다.
   - 우선 순위  값이 **0인** 정책에는 우선 순위 감소 옵션만 사용할 **수** 있습니다.
   - 우선 순위 값이 가장 **낮은** 정책(예: **3)에는** 우선 순위 늘리기 옵션만 사용할 **수** 있습니다.
   - 세 개 이상의 정책이 있는 경우 우선 순위가 가장  높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 옵션을 모두 사용할 **수** 있습니다.

   ![우선 순위 증가 아이콘](../../media/m365-cc-sc-increase-icon.png) **우선 순위 증가** 또는 ![우선 순위 감소 아이콘](../../media/m365-cc-sc-decrease-icon.png) **우선순위 감소** 를 클릭하여 **우선 순위** 값을 변경합니다.

4. 작업을 마쳤으면 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>Microsoft 365 Defender 포털을 사용하여 첨부 파일 금고 제거

1. Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 금고 정책으로 \>  \>  \>  이동하세요. 

2. 첨부 **금고** 페이지에서 정책 이름을 클릭하여 목록에서 사용자 지정 정책을 선택합니다.

3. 표시되는 정책 세부 정보 플라이아웃 상단에서 ![추가 작업 아이콘](../../media/m365-cc-sc-more-actions-icon.png)을 클릭합니다. **추가 작업** \> ![정책 아이콘 삭제](../../media/m365-cc-sc-delete-icon.png) **정책 삭제**.

4. 확인 대화 상자가 나타나면 **예** 를 클릭합니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 금고 정책 구성

앞서 설명한 금고 첨부 파일 정책은 안전한 첨부 파일 정책과 안전한 첨부 파일 규칙으로 구성됩니다.

PowerShell에서는 안전한 첨부 파일 정책과 안전한 첨부 파일 규칙의 차이점이 분명합니다. **\* -SafeAttachmentPolicy** cmdlet을 사용하여 안전한 첨부 파일 정책을 관리하고 **\* -SafeAttachmentRule** cmdlet을 사용하여 안전한 첨부 파일 규칙을 관리합니다.

- PowerShell에서 먼저 안전한 첨부 파일 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 안전한 첨부 파일 규칙을 생성합니다.
- PowerShell에서는 안전한 첨부 파일 정책 및 안전한 첨부 파일 규칙의 설정을 별도로 수정합니다.
- PowerShell에서 안전한 첨부 파일 정책을 제거하면 해당 안전 첨부 파일 규칙이 자동으로 제거되지 않습니다.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell을 사용하여 첨부 파일 금고 만들기

PowerShell에서 금고 첨부 파일 정책을 만드는 과정은 다음 두 단계로 진행됩니다.

1. 안전한 첨부 파일 정책을 만들 수 있습니다.
2. 규칙이 적용되는 안전한 첨부 파일 정책을 지정하는 안전한 첨부 파일 규칙을 만들 수 있습니다.

 **참고:**

- 새 안전한 첨부 파일 규칙을 만들고 연결되지 않은 기존 안전 첨부 파일 정책을 할당할 수 있습니다. 안전한 첨부 파일 규칙은 두 개 이상의 안전한 첨부 파일 정책과 연결될 수 없습니다.

- 정책을 만든 후까지 Microsoft 365 Defender 포털에서 사용할 수 없는 PowerShell의 새 안전 첨부 파일 정책에 대해 다음 설정을 구성할 수 있습니다.
  - 새 정책을 사용하지 않도록 `$false` **설정합니다(New-SafeAttachmentRule** cmdlet에서 사용).
  -  _\<Number\>_ **New-SafeAttachmentRule** cmdlet에서 만들 때 정책의 우선 순위( 우선 순위)를 설정하십시오.

- PowerShell에서 만든 새 안전한 첨부 파일 정책은 안전한 첨부 파일 규칙에 정책을 할당할 때까지 Microsoft 365 Defender 포털에 표시되지 않습니다.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>1단계: PowerShell을 사용하여 안전한 첨부 파일 정책 만들기

안전한 첨부 파일 정책을 만들 수 있도록 다음 구문을 사용 합니다.

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" -Enable $true [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>] [-QuarantineTag <QuarantinePolicyName>]
```

이 예에서는 다음 값을 가지는 Contoso All이라는 안전한 첨부 파일 정책을 만듭니다.

- 문서 검색을 금고 맬웨어가 포함된 것으로 확인된 메시지를 차단합니다(Action  매개 변수를 사용하지 않습니다. 기본값은 `Block` 입니다).
- _QuarantineTag_ 매개 변수를 사용하지 않는 것이기 때문에 기본 검지 정책(AdminOnlyAccessPolicy)이 사용됩니다. [](quarantine-policies.md)
- 리디렉션이 사용하도록 설정되어 있으며 맬웨어가 포함된 것으로 확인된 메시지는 분석 및 조사를 위해 sec-ops@contoso.com 전송됩니다.
- 금고 첨부 파일 검색을 사용할 수 없는 경우 메시지를 배달하지 _않습니다(ActionOnError_ 매개 변수를 사용하지 않습니다. 기본값은 `$true` 입니다).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Enable $true -Redirect $true -RedirectAddress sec-ops@contoso.com
```

구문과 매개 변수에 대한 자세한 내용은 [New-SafeAttachmentPolicy를 참조하십시오.](/powershell/module/exchange/new-safeattachmentpolicy)

> [!NOTE]
> 안전한 첨부 파일 정책에 사용할 검지 정책을 지정하는 자세한 지침은 PowerShell을 사용하여 첨부 파일 정책에서 금고 [지정을 참조하세요.](quarantine-policies.md#safe-attachments-policies-in-powershell) [](quarantine-policies.md)

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

PowerShell에서 안전한 첨부 파일 정책의 이름을 다시 설정할 수 **없습니다(Set-SafeAttachmentPolicy** cmdlet에는 _Name_ 매개 변수가 없음). 금고 포털에서 Microsoft 365 Defender 정책의 이름을 바에는 안전한 첨부 파일 규칙의 이름만 _바입니다._

그렇지 않으면 이 문서 앞부분의 [1단계: PowerShell을](#step-1-use-powershell-to-create-a-safe-attachment-policy) 사용하여 안전한 첨부 파일 정책 만들기 섹션에 설명된 대로 안전한 첨부 파일 정책을 만들 때 동일한 설정을 사용할 수 있습니다.

안전한 첨부 파일 정책을 수정하려면 다음 구문을 사용 합니다.

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentPolicy를 참조하십시오.](/powershell/module/exchange/set-safeattachmentpolicy)

> [!NOTE]
> 안전한 첨부 파일 정책에 사용할 검지 정책을 지정하는 자세한 지침은 PowerShell을 사용하여 첨부 파일 정책에서 금고 [지정을 참조하세요.](quarantine-policies.md#safe-attachments-policies-in-powershell) [](quarantine-policies.md)

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell을 사용하여 안전한 첨부 파일 규칙 수정

PowerShell에서 안전한 첨부 파일 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용되지 않는 규칙을 만들 수 있는 _Enabled_ 매개 변수뿐입니다. 기존 안전 첨부 파일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.

그렇지 않으면 이 문서 앞부분의 [2단계: PowerShell을](#step-2-use-powershell-to-create-a-safe-attachment-rule) 사용하여 안전한 첨부 파일 규칙 만들기 섹션에 설명된 대로 규칙을 만들 때 동일한 설정을 사용할 수 있습니다.

안전한 첨부 파일 규칙을 수정하려면 다음 구문을 사용 합니다.

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentRule을 참조하십시오.](/powershell/module/exchange/set-safeattachmentrule)

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell을 사용하여 안전한 첨부 파일 규칙을 사용 또는 사용하지 않도록 설정

PowerShell에서 안전한 첨부 파일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하면 전체 금고 첨부 파일 정책(안전한 첨부 파일 규칙 및 할당된 안전한 첨부 파일 정책)을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.

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

첨부 파일 정책을 만들거나 수정하거나 제거한 금고 다음 단계를 수행합니다.

- Microsoft 365 Defender 포털에서 정책 섹션의 **전자** 메일 & 공동 작업 정책 & 규칙 위협 금고 정책으로 \>  \>  \>  이동하세요.  정책 목록, 해당 **상태 값** 및 우선 순위 값을 **검증합니다.** 자세한 내용을 보려면 이름을 클릭하여 목록에서 정책을 선택하고 플라이아웃에서 세부 정보를 하세요.

- PowerShell Exchange Online PowerShell Exchange Online Protection PowerShell에서 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 설정을 \<Name\> 확인합니다.

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

첨부 파일이 금고 검사하는지 확인을 위해 사용 가능한 Defender에서 보고서의 Office 365 합니다. 자세한 내용은 Office 365 포털에서 [Defender에](view-reports-for-mdo.md) 대한 보고서 Office 365 [탐색기 Microsoft 365 Defender 참조하세요.](threat-explorer.md)
