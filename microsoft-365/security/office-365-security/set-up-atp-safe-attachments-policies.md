---
title: Office 365 ATP에서 안전한 첨부 파일 정책 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 안전한 첨부 파일 정책을 정의 하 여 전자 메일의 악의적인 파일 로부터 조직을 보호 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e50e5e961e1a45b0b6535995727029222539ff03
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326964"
---
# <a name="set-up-safe-attachments-policies-in-office-365-atp"></a>Office 365 ATP에서 안전한 첨부 파일 정책 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> 이 문서는 [Office 365 ATP (Advanced Threat Protection)](office-365-atp.md)가 있는 비즈니스 고객을 위한 것입니다. Outlook에서 첨부 파일을 검색 하는 방법에 대 한 자세한 내용은 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)를 참조 하세요.

안전한 첨부 파일은 [EOP (Exchange Online Protection)에서 맬웨어 방지 보호](anti-malware-protection.md)를 통해 검색 한 후, 받는 사람에 게 배달 되기 전에 가상 환경을 사용 하 여 인바운드 전자 메일 메시지의 첨부 파일을 확인 하는 [Office 365 ATP (Advanced Threat Protection)](office-365-atp.md) 의 기능입니다. 자세한 내용은 [Office 365 ATP의 안전한 첨부 파일](atp-safe-attachments.md)을 참조 하십시오.

기본 제공 또는 기본 안전 첨부 파일 정책이 없습니다. 전자 메일 메시지 첨부 파일에 대 한 안전한 첨부 파일 검색을 받으려면이 문서에 설명 된 대로 하나 이상의 안전한 첨부 파일 정책을 만들어야 합니다.

보안 & 준수 센터 또는 PowerShell (exchange online에 사서함이 있는 적격 Microsoft 365 조직에 대해 exchange online PowerShell, exchange online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell, Office 365 ATP 추가 기능 구독이 있는 경우)에서 안전한 첨부 파일 정책을 구성할 수 있습니다.

안전한 첨부 파일 정책의 기본 요소는 다음과 같습니다.

- **안전한 첨부 파일 정책**: 알 수 없는 맬웨어 검색, 지정 된 전자 메일 주소에 맬웨어 첨부 파일을 포함 하는 메시지를 보낼지 여부 및 안전한 첨부 파일 검사를 완료할 수 없는 경우 메시지를 배달할 지 여부를 지정 합니다.
- **Safe 첨부 파일 규칙**: 우선 순위 및 받는 사람 필터 (정책이 적용 되는 사용자)를 지정 합니다.

보안 & 준수 센터에서 안전한 첨부 파일 정책을 관리할 때는 이러한 두 가지 요소 간의 차이가 명확 하지 않습니다.

- 안전한 첨부 파일 정책을 만드는 경우 실제로는 둘 다에 대해 동일한 이름을 사용 하 여 안전한 첨부 파일 규칙과 연결 된 안전한 첨부 파일 정책을 동시에 만드는 것입니다.
- 안전한 첨부 파일 정책을 수정 하면 이름, 우선 순위, 사용/사용 안 함 및 받는 사람 필터와 관련 된 설정이 안전한 첨부 파일 규칙을 수정 합니다. 다른 모든 설정은 연결 된 안전한 첨부 파일 정책을 수정 합니다.
- 안전한 첨부 파일 정책을 제거 하면 안전한 첨부 파일 규칙과 연결 된 안전한 첨부 파일 정책이 제거 됩니다.

Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다. 자세한 내용은이 문서 뒷부분에 나오는 [Exchange Online PowerShell 또는 독립 실행형 EOP powershell을 사용 하 여 안전한 첨부 파일 정책 구성](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 섹션을 참조 하십시오.

> [!NOTE]
> 안전한 첨부 파일 설정의 전역 설정 영역에서 안전한 첨부 파일 정책에 종속 되지 않는 기능을 구성 합니다. 지침에 대해서는 [microsoft 365 E5의](safe-docs.md) [SharePoint, OneDrive 및 Microsoft 팀 및 안전 문서에 대 한 ATP 끄기를](turn-on-atp-for-spo-odb-and-teams.md) 참조 하세요.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **ATP 안전한 첨부 파일** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/safeattachmentv2> 합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 안전한 첨부 파일 정책을 보고, 만들고, 수정 하 고, 삭제 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

  - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리**

- 안전한 첨부 파일 정책에 대 한 권장 설정에 대 한 자세한 내용은 [안전한 첨부 파일 설정을](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)참조 하십시오.

- 새 정책이 나 업데이트 된 정책을 적용할 최대 30 분을 허용 합니다.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>보안 & 준수 센터를 사용 하 여 안전한 첨부 파일 정책 만들기

보안 & 준수 센터에서 사용자 지정 안전 첨부 파일 정책을 만들면 둘 다에 대해 동일한 이름을 사용 하 여 안전한 첨부 파일 규칙과 연결 된 안전한 첨부 파일 정책이 동시에 만들어집니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동 합니다.

2. **안전한 첨부 파일** 페이지에서 **만들기**를 클릭 합니다.

3. **새 안전 첨부 파일 정책** 마법사가 열립니다. **정책 이름** 설정 페이지에서 다음 설정을 구성 합니다.

   - **이름**: 정책을 설명하는 고유한 이름을 입력합니다.

   - **설명**: 정책에 대한 선택적 설명을 입력합니다.

   작업을 마친 후 **다음**을 클릭합니다.

4. **설정** 페이지가 나타나면 다음 설정을 구성 합니다.

   - **안전한 첨부 파일 알 수 없는 맬웨어 응답**: 다음 값 중 하나를 선택 합니다.

     - **해제**: 일반적으로이 값을 권장 하지 않습니다.
     - **모니터만**
     - **Block**:이 값은 기본값 이며 표준 및 엄격한 [사전 설정 보안 정책](preset-security-policies.md)에서 권장 되는 값입니다.
     - **바꾸기**
     - **동적 배달 (미리 보기 기능)**

     이러한 값은 [안전한 첨부 파일 정책 설정](atp-safe-attachments.md#safe-attachments-policy-settings)에 설명 되어 있습니다.

   - **첨부 파일을 다음 전자 메일 주소로 보내기**: 작업 값 **차단**, **모니터**또는 **바꾸기**에 대해 **리디렉션 사용** 을 선택 하 여 분석 및 조사를 위해 지정 된 내부 또는 외부 전자 메일 주소에 맬웨어 첨부 파일이 포함 된 메시지를 보낼 수 있습니다.

     표준 및 엄격한 정책 설정에 대 한 권장 사항은 리디렉션을 사용 하도록 설정 하는 것입니다. 자세한 내용은 [안전한 첨부 파일 설정을](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)참조 하십시오.

   - **첨부 파일에 대 한 맬웨어 검사 시간이 초과 되거나 오류가 발생 하면 위의 선택 사항을 적용**합니다. **안전한** 첨부 파일에서 지정한 작업은 안전한 첨부 파일 검색을 완료할 수 없는 경우에도 메시지에 대해 수행 됩니다. **사용 리디렉션을**선택 하는 경우 항상이 옵션을 선택 합니다. 그렇지 않으면 메시지가 손실 될 수 있습니다.

   작업을 마친 후 **다음**을 클릭합니다.

5. **적용 대상** 페이지에서 정책이 적용 되는 내부 받는 사람을 식별 합니다.

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

6. **설정 검토** 페이지가 나타나면 설정을 검토 합니다. 각 설정에 대해 **편집** 을 클릭 하 여 수정할 수 있습니다.

   작업이 완료 되 면 **마침을**클릭 합니다.

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>보안 & 준수 센터를 사용 하 여 안전한 첨부 파일 정책 보기

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동 합니다.

2. **안전한 첨부 파일** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).

   정책 세부 정보가 플라이 아웃에 표시 됨

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>보안 & 준수 센터를 사용 하 여 안전한 첨부 파일 정책 수정

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동 합니다.

2. **안전한 첨부 파일** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).

3. 정책 세부 정보가 표시 되 면 **정책 편집**을 클릭 합니다.

즉시 표시 되는 사용 가능한 설정은 [보안 & 준수 센터를 사용 하 여 안전한 첨부 파일 정책 만들기](#use-the-security--compliance-center-to-create-safe-attachments-policies) 섹션에 설명 된 설정과 동일 합니다.

정책을 사용 하거나 사용 하지 않도록 설정 하려면 다음 섹션을 참조 하십시오.

### <a name="enable-or-disable-safe-attachments-policies"></a>안전한 첨부 파일 정책 사용 또는 사용 안 함

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동 합니다.

2. **상태** 열에서 다음 값을 확인 합니다.

   - 왼쪽으로 토글 ![정책 해제](../../media/scc-toggle-off.png) 정책을 사용 하지 않도록 설정 합니다.

   - 오른쪽으로 토글 ![정책 설정](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 정책을 사용 하도록 설정 합니다.

### <a name="set-the-priority-of-safe-attachments-policies"></a>안전한 첨부 파일 정책의 우선 순위 설정

기본적으로 안전한 첨부 파일 정책에는 만들어진 순서를 기준으로 하는 우선 순위가 지정 됩니다 (최신 정책은 이전 정책 보다 낮은 우선 순위). 낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨). 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.

안전한 첨부 파일 정책은 처리 되는 순서 대로 표시 됩니다 (첫 번째 정책의 **우선 순위** 값은 0).

**참고**: 보안 & 준수 센터에서는 안전한 첨부 파일 정책의 우선 순위를 만든 후에만 변경할 수 있습니다. PowerShell에서는 안전한 첨부 파일 규칙을 만들 때 기본 우선 순위를 무시할 수 있습니다 (기존 규칙의 우선 순위에 영향을 줄 수 있음).

정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동 합니다.

2. **안전한 첨부 파일** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).

3. 정책 세부 정보가 표시 되 면 사용 가능한 우선 순위 단추를 클릭 합니다.

   - **우선 순위** 값이 **0** 인 안전 첨부 파일 정책에는 **우선 순위 낮추기** 단추만 사용할 수 있습니다.

   - **우선 순위** 값이 가장 낮은 안전한 첨부 파일 정책 (예: **3**)에는 **우선 순위 향상** 단추만 사용할 수 있습니다.

   - 안전한 첨부 파일 정책이 셋 이상인 경우 가장 높거나 낮은 우선 순위 값 사이의 정책에는 **우선 순위 증가** 와 **우선 순위 낮추기** 단추가 모두 있습니다.

4. 우선 **순위 높임** 또는 **우선 순위 낮추기** 를 클릭 하 여 **우선 순위** 값을 변경 합니다.

5. 작업을 마쳤으면 **닫기**를 클릭합니다.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>보안 & 준수 센터를 사용 하 여 안전한 첨부 파일 정책 제거

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동 합니다.

2. **안전한 첨부 파일** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).

3. 정책 세부 정보가 표시 되 면 **정책 삭제**를 클릭 한 다음 표시 되는 경고 대화 상자에서 **예** 를 클릭 합니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용 하 여 안전한 첨부 파일 정책 구성

앞에서 설명한 것 처럼 안전한 첨부 파일 정책은 안전한 첨부 파일 정책 및 안전한 첨부 파일 규칙으로 구성 됩니다.

PowerShell에서는 안전한 첨부 파일 정책 및 안전한 첨부 파일 규칙 간의 차이가 명백 합니다. ** \* -Get-safeattachmentpolicy** cmdlet을 사용 하 여 안전한 첨부 파일 정책을 관리 하 고 ** \* -disable-safeattachmentrule** cmdlet을 사용 하 여 안전한 첨부 파일 규칙을 관리 합니다.

- PowerShell에서는 먼저 안전한 첨부 파일 정책을 만든 다음 규칙이 적용 되는 정책을 식별 하는 수신 허용-첨부 파일 규칙을 만듭니다.
- PowerShell에서는 안전한 첨부 파일 정책 및 안전한 첨부 파일 규칙의 설정을 개별적으로 수정 합니다.
- PowerShell에서 안전한 첨부 파일 정책을 제거 하면 해당 하는 안전 첨부 파일 규칙이 자동으로 제거 되지 않으며 그 반대의 경우도 마찬가지입니다.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell을 사용 하 여 안전한 첨부 파일 정책 만들기

PowerShell에서 안전한 첨부 파일 정책을 만드는 과정은 두 단계로 진행 됩니다.

1. 안전한 첨부 파일 정책을 만듭니다.
2. 규칙이 적용 되는 안전한 첨부 파일 정책을 지정 하는 안전한 첨부 파일 규칙을 만듭니다.

 **참고:**

- 안전한 첨부 파일 규칙을 새로 만들고 연결 되지 않은 기존 안전한 첨부 파일 정책을 할당할 수 있습니다. 안전한 첨부 파일 규칙은 둘 이상의 안전한 첨부 파일 정책에 연결할 수 없습니다.

- 정책을 만든 후에 야 보안 & 준수 센터에서 사용할 수 없는 PowerShell의 새 안전 첨부 파일 정책에 대해 다음 설정을 구성할 수 있습니다.
  - Disable-safeattachmentrule cmdlet에서_사용 하도록 설정_ 된 새 정책을 사용 하지 않도록 설정 `$false` **New-SafeAttachmentRule** 합니다.
  - Disable-safeattachmentrule cmdlet에 대 한 생성 (_우선 순위_ ) 중에 정책의 우선 순위를 설정 _\<Number\>_ 합니다. **New-SafeAttachmentRule**

- 안전한 첨부 파일 규칙에 정책을 할당 해야 PowerShell에서 만든 새 안전한 첨부 파일 정책이 보안 & 준수 센터에 표시 되지 않습니다.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>1 단계: PowerShell을 사용 하 여 안전한 첨부 파일 정책 만들기

안전한 첨부 파일 정책을 만들려면 다음 구문을 사용 합니다.

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

이 예에서는 다음 값을 사용 하 여 Contoso All 이라는 안전한 첨부 파일 정책을 만듭니다.

- 안전한 문서 검색을 통해 맬웨어가 포함 되도록 찾은 메시지 차단 ( _Action_ 매개 변수를 사용 하지 않으며 기본값은 is `Block` )
- 리디렉션이 사용 되 고 맬웨어를 포함 하는 메시지는 분석 및 조사를 위해 sec-ops@contoso.com로 전송 됩니다.
- 안전한 첨부 파일 검색을 사용할 수 없거나 오류가 발생할 경우 메시지를 배달 하지 않습니다 ( _Actiononerror_ 매개 변수를 사용 하지 않으며 기본값은 is `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

구문과 매개 변수에 대 한 자세한 내용은 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)를 참조 하십시오.

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>2 단계: PowerShell을 사용 하 여 안전한 첨부 파일 규칙 만들기

안전한 첨부 파일 규칙을 만들려면 다음 구문을 사용 합니다.

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

이 예에서는 다음과 같은 조건을 가진 Contoso All 이라는 안전한 첨부 파일 규칙을 만듭니다.

- 이 규칙은 Contoso All 이라는 안전한 첨부 파일 정책에 연결 됩니다.
- 규칙은 contoso.com 도메인의 모든 받는 사람에 게 적용 됩니다.
- _Priority_ 매개 변수를 사용 하지 않으므로 기본 우선 순위가 사용 됩니다.
- 이 규칙이 사용 하도록 설정 되어 있습니다 ( _enabled_ 매개 변수를 사용 하지 않으며 기본값은 `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

구문과 매개 변수에 대 한 자세한 내용은 [disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)를 참조 하십시오.

### <a name="use-powershell-to-view-safe-attachment-policies"></a>PowerShell을 사용 하 여 안전한 첨부 파일 정책 보기

기존의 안전한 첨부 파일 정책을 보려면 다음 구문을 사용 합니다.

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예에서는 모든 안전 첨부 파일 정책의 요약 목록을 반환 합니다.

```PowerShell
Get-SafeAttachmentPolicy
```

이 예에서는 Contoso 임원 이라는 안전한 첨부 파일 정책에 대 한 자세한 정보를 반환 합니다.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

구문과 매개 변수에 대 한 자세한 내용은 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)를 참조 하십시오.

### <a name="use-powershell-to-view-safe-attachment-rules"></a>PowerShell을 사용 하 여 안전한 첨부 파일 규칙 보기

기존의 안전한 첨부 파일 규칙을 보려면 다음 구문을 사용 합니다.

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

이 예에서는 모든 안전 첨부 파일 규칙의 요약 목록을 반환 합니다.

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

이 예에서는 Contoso 임원 이라는 안전한 첨부 파일 규칙에 대 한 자세한 정보를 반환 합니다.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

구문과 매개 변수에 대 한 자세한 내용은 [disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)를 참조 하십시오.

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>PowerShell을 사용 하 여 안전한 첨부 파일 정책 수정

PowerShell에서 안전한 첨부 파일 정책의 이름을 바꿀 수는 없습니다 (Get-safeattachmentpolicy cmdlet은 _Name_ 매개 변수를 **사용** 하지 않음). 보안 & 준수 센터에서 안전 첨부 파일 정책의 이름을 바꾸면 안전한 첨부 파일 _규칙만_변경 됩니다.

그렇지 않은 경우에는이 문서의 앞부분에 나오는 [1 단계: PowerShell을 사용 하 여 안전한 첨부 파일 정책 만들기](#step-1-use-powershell-to-create-a-safe-attachment-policy) 섹션에 설명 된 대로 안전한 첨부 파일 정책을 만드는 경우에도 동일한 설정을 사용할 수 있습니다.

안전한 첨부 파일 정책을 수정 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

구문 및 매개 변수에 대 한 자세한 내용은 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)를 참조 하십시오.

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell을 사용 하 여 안전한 첨부 파일 규칙 수정

PowerShell에서 안전한 첨부 파일 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용 하지 않도록 설정 된 규칙을 만들 수 있는 _Enabled_ 매개 변수입니다. 기존의 안전한 첨부 파일 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 섹션을 참조 하십시오.

그렇지 않은 경우에는이 문서의 앞부분에 나오는 [2 단계: PowerShell을 사용 하 여 안전한 첨부 파일 규칙 만들기](#step-2-use-powershell-to-create-a-safe-attachment-rule) 섹션에 설명 된 대로 규칙을 만들 때도 같은 설정을 사용할 수 있습니다.

안전한 첨부 파일 규칙을 수정 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

구문 및 매개 변수에 대 한 자세한 내용은 [disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)를 참조 하십시오.

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell을 사용 하 여 안전한 첨부 파일 규칙을 사용 하거나 사용 하지 않도록 설정

PowerShell에서 안전한 첨부 파일 규칙을 사용 하거나 사용 하지 않도록 설정 하면 전체 안전 첨부 파일 정책 (안전한 첨부 파일 규칙 및 할당 된 안전한 첨부 파일 정책)을 사용 하거나 사용 하지 않도록 설정 됩니다.

PowerShell에서 안전한 첨부 파일 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 구문을 사용 합니다.

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

이 예에서는 Marketing 부서 라는 안전한 첨부 파일 규칙을 사용 하지 않도록 설정 합니다.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

구문 및 매개 변수에 대 한 자세한 내용은 [Enable-disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) 및 [Disable-disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)을 참조 하십시오.

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>PowerShell을 사용 하 여 안전한 첨부 파일 규칙의 우선 순위 설정

규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다. 설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다. 예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다. 기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다. 예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.

PowerShell에서 안전한 첨부 파일 규칙의 우선 순위를 설정 하려면 다음 구문을 사용 합니다.

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다. 우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**참고**: 새 규칙을 만들 때 우선 순위를 설정 하려면 대신 **Disable-safeattachmentrule** cmdlet에서 _priority_ 매개 변수를 사용 하십시오.

구문 및 매개 변수에 대 한 자세한 내용은 [disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)를 참조 하십시오.

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>PowerShell을 사용 하 여 안전한 첨부 파일 정책 제거

PowerShell을 사용 하 여 안전한 첨부 파일 정책을 제거 해도 해당 하는 안전한 첨부 파일 규칙은 제거 되지 않습니다.

PowerShell에서 안전한 첨부 파일 정책을 제거 하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

이 예에서는 Marketing 학과 라는 안전한 첨부 파일 정책을 제거 합니다.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

구문과 매개 변수에 대 한 자세한 내용은 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)를 참조 하십시오.

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>PowerShell을 사용 하 여 안전한 첨부 파일 규칙 제거

PowerShell을 사용 하 여 안전한 첨부 파일 규칙을 제거 하는 경우 해당 하는 안전한 첨부 파일 정책은 제거 되지 않습니다.

PowerShell에서 안전한 첨부 파일 규칙을 제거 하려면 다음 구문을 사용 합니다.

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

이 예에서는 Marketing 부서 라는 안전한 첨부 파일 규칙을 제거 합니다.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

구문과 매개 변수에 대 한 자세한 내용은 [disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)를 참조 하십시오.

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

안전한 첨부 파일 정책이 성공적으로 생성, 수정 또는 제거 되었는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동 합니다. 정책 목록, 해당 **상태** 값 및 해당 **우선 순위** 값을 확인 합니다. 자세한 내용을 보려면 목록에서 정책을 선택 하 고 플라이 아웃에서 세부 정보를 확인 합니다.

- Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 \<Name\> 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행 하 고 설정을 확인 합니다.

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

안전한 첨부 파일이 메시지를 검색 하는지 확인 하려면 사용 가능한 Advanced Threat Protection 보고서를 확인 합니다. 자세한 내용은 [View reports For Office 365 ATP](view-reports-for-atp.md) 및 [Security & 준수 센터에서 탐색기 사용](threat-explorer.md)을 참조 하십시오.
