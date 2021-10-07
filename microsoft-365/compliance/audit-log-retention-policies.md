---
title: 로그 보존 정책 감사 관리
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 감사 로그 보존 정책은 Microsoft 365의 새로운 고급 감사 기능의 일부입니다. 감사 로그 보존 정책을 사용하여 조직에서 감사 로그를 보존할 기간을 지정할 수 있습니다.
ms.openlocfilehash: f8c269aa4541c438942c69831857ed531681b742
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198748"
---
# <a name="manage-audit-log-retention-policies"></a>로그 보존 정책 감사 관리

Microsoft 365 규정 준수 센터에서 감사 로그 보존 정책을 만들고 관리할 수 있습니다. 감사 로그 보존 정책은 Microsoft 365의 새로운 고급 감사 기능의 일부입니다. 감사 로그 보존 정책을 사용하여 조직에서 감사 로그를 보존할 기간을 지정할 수 있습니다. 감사 로그를 최대 10년 동안 보존할 수 있습니다. 다음 조건을 기준으로 정책을 만들 수 있습니다.

- 하나 이상의 Microsoft 365 서비스에서의 모든 활동
- 모든 사용자 또는 특정 사용자가 수행하는 (Microsoft 365 서비스에서의) 특정 활동
- 조직에 여러 정책이 있을 때 더 중시하는 정책을 지정하는 우선 순위

## <a name="default-audit-log-retention-policy"></a>기본 로그 보존 정책 감사

Microsoft 365의 고급 감사는 모든 조직에 기본 감사 로그 보존 정책을 제공합니다. 이 정책은 모든 Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Azure Active Directory 감사 레코드를 1년 동안 보존합니다. 이 기본 정책은 **Exchange**, **SharePoint**, **OneDrive**, **워크로드** 속성에 대한 **AzureActiveDirectory**(활동이 발생한 서비스)의 값을 포함하는 감사 레코드를 보존합니다. 기본 정책은 수정할 수 없습니다. 기본 정책에 포함된 각 워크로드의 레코드 유형 목록은 이 문서의 [추가 정보](#more-information) 섹션을 참조하십시오.

> [!NOTE]
> 기본 감사 로그 보존 정책은 Office 365 또는 Microsoft 365 E5 라이선스가 할당되었거나 Microsoft 365 E5 준수 또는 E5 eDiscovery 및 감사 애드온 라이선스가 있는 사용자가 수행한 활동에 대한 감사 레코드에만 적용됩니다. 조직에 E5 이외의 사용자 또는 게스트 사용자가 있는 경우 해당 감사 레코드는 90일 동안 유지됩니다.

## <a name="before-you-create-an-audit-log-retention-policy"></a>감사 로그 보존 정책을 생성하기 전에 다음을 수행합니다.

- 사용자는 감사 보존 정책을 만들거나 수정하기 위해 Microsoft 365 규정 준수 센터에서 조직 구성 역할을 할당받아야 합니다.

- 조직에서 최대 50개의 감사 로그 보존 정책을 가질 수 있습니다.

- 감사 로그를 90일(최대 1년) 이상 유지하려면 감사 로(감사된 황동을 실행하여)그를 생성한 사용자에게 Office 365 E5 또는 Microsoft 365 E5 라이선스가 할당되거나 Microsoft 365 E5 규정 준수 또는 E5 eDiscovery 및 감사 추가 기능 라이선스가 있어야 합니다. 감사 로그를 10년 동안 보존하려면 감사 로그를 생성하는 사용자에게 E5 라이선스 외에 10년 감사 로그 보존 추가 기능 라이선스도 할당되어야 합니다.

- 모든 사용자 지정 감사 로그 보존 정책(조직에서 만든)은 기본 보존 정책보다 우선 순위가 적용됩니다. 예를 들어 1년보다 짧은 보존 기간이 있는 Exchange 사서함 활동에 대한 감사 로그 보존 정책을 만드는 경우 사용자 지정 정책에서 지정한 기간이 단축되는 동안 Exchange 사서함 활동에 대한 감사 레코드가 보존됩니다.

## <a name="create-an-audit-log-retention-policy"></a>감사 로그 보존 정책 생성

1. <https://compliance.microsoft.com>으로 이동하여 Microsoft 365 규정 준수 센터의 권한 페이지에서 조직 구성 역할이 할당된 사용자 계정으로 로그인합니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 창에서 **감사** 를 클릭합니다.

3. **감사 보존 정책** 탭을 클릭합니다.

4. **감사 보존 정책 만들기** 를 클릭한 다음 플라이아웃 페이지에서 다음 필드를 완료하십시오.

   ![새 감사 보존 정책 플라이아웃 페이지.](../media/CreateAuditLogRetentionPolicy.png)

   1. **정책 이름:** 감사 로그 보존 정책의 이름입니다. 이 이름은 조직에서 고유해야 하며 정책을 만든 후 변경할 수 없습니다.

   2. **설명:** 선택 사항이지만 레코드 유형 또는 워크로드, 정책에 지정된 사용자 및 기간과 같은 정책에 대한 정보를 제공하는 데 도움이 됩니다.

   3. **사용자:** 정책을 적용할 하나 이상의 사용자를 선택하십시오. 이 상자를 비워 두면 정책이 모든 사용자에 게 적용됩니다. **레코드 유형** 을 비워둔 경우 반드시 사용자를 선택해야 합니다.

   4. **레코드 유형:** 정책이 적용되는 감사 레코드 유형입니다. 또한 해당 속성을 비워둔 경우 **사용자** 상자에서 사용자를 선택해야 합니다. 단일 레코드 유형 또는 다중 레코드 유형을 선택할 수 있습니다.
      - 단일 레코드 유형을 선택하면 **활동** 필드가 동적으로 표시됩니다. 드롭다운 목록을 사용하여 선택한 레코드 유형에서 활동을 선택하고 정책을 적용할 수 있습니다. 특정 활동을 선택하지 않으면 선택한 레코드 유형의 모든 활동에 정책이 적용됩니다.
      - 다중 레코드 유형을 선택한 경우에는 활동을 선택할 수 없습니다. 선택한 레코드 유형의 모든 활동에 해당 정책이 적용됩니다.

   5. **기간:** 정책 기준을 충족하는 감사 로그를 보유하는 기간입니다.

   6. **우선 순위:** 이 값은 조직의 감사 로그 보존 정책이 처리되는 순서를 결정합니다. 값이 작을수록 우선 순위가 높습니다. 유효한 우선 순위의 숫자 값은 **1**~**10000** 사이입니다. **1** 이 가장 높은 우선 순위 값이며, **10000** 이 가장 낮은 우선 순위 값입니다. 예를 들어 값이 **5** 인 정책이 값이 **10** 인 정책보다 우선합니다. 앞에서 설명한 것처럼 사용자 지정 감사 로그 보존 정책은 조직의 기본 정책보다 우선합니다.

5. **저장** 을 클릭하여 새 감사 로그 보존 정책을 만듭니다.

새 정책은 **감사 보존 정책** 탭의 목록에 표시됩니다.

## <a name="manage-audit-log-retention-policies-in-the-microsoft-365-compliance-center"></a>Microsoft 365 규정 준수 센터에서 감사 로그 보존 정책 관리하기

감사 로그 보존 정책은 **감사 보존 정책** 탭(*대시보드* 라고도 함)에 나열됩니다. 대시보드를 사용하여 감사 보존 정책을 보고, 편집하고, 삭제할 수 있습니다.

### <a name="view-policies-in-the-dashboard"></a>대시보드에서 정책 보기

감사 로그 보존 정책은 대시보드에 나열되어 있습니다. 대시보드에서 정책을 볼 때의 이점 중 하나는 **우선 순위** 열을 클릭하여 적용되는 우선 순위로 정책을 나열할 수 있다는 것입니다. 이전에 설명한 대로 값이 높을수록 우선 순위가 더 낮음을 나타냅니다.

![감사 보존 정책 대시보드의 우선 순위 열.](../media/AuditLogRetentionDashboardPriority.png)

플라이아웃 페이지에 설정을 표시하는 정책을 선택할 수도 있습니다.

> [!NOTE]
> 조직의 기본 감사 로그 보존 정책은 대시보드에 표시되지 않습니다.

### <a name="edit-policies-in-the-dashboard"></a>대시보드에서 정책 편집

정책을 편집하려면 정책을 선택하여 플라이아웃 페이지를 표시합니다. 하나 이상의 설정을 수정한 다음 변경 내용을 저장할 수 있습니다.

> [!IMPORTANT]
>
> **New-UnifiedAuditLogRetentionPolicy** cmdlet을 사용하는 경우, 대시보드의 **감사 보존 정책 만들기** 도구에서 사용할 수 없는 레코드 종류나 활동에 대한 감사 로그 보존 정책을 만들 수 있습니다. 이 경우, **감사 보존 정책** 대시보드에서 정책(예: 보존 기간 변경 또는 활동 추가 및 제거)을 편집할 수 없습니다. 규정 준수 센터에서만 정책을 보고 삭제할 수 있습니다. 정책을 편집하려면 보안 및 준수 센터 PowerShell에서 [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet을 사용해야 합니다.>
>
> **팁:** PowerShell을 사용하여 편집해야 하는 정책에 대한 메시지가 플라이아웃 페이지의 맨 위에 표시됩니다.

### <a name="delete-policies-in-the-dashboard"></a>대시보드에서 정책 삭제

정책을 삭제하려면 **삭제**![삭제 아이콘](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)을 클릭합니다. 아이콘을 클릭한 다음 정책을 삭제할지 확인합니다. 정책이 대시보드에서 제거되지만 조직에서 정책이 제거되는 데 최대 30분이 걸릴 수 있습니다.

## <a name="create-and-manage-audit-log-retention-policies-in-powershell"></a>PowerShell에서 감사 로그 보존 정책 만들기 및 관리

보안 및 준수 센터 PowerShell을 사용하여 감사 로그 보존 정책을 만들고 관리할 수도 있습니다. PowerShell을 사용하는 한 가지 이유는 UI에서 사용할 수 없는 레코드 형식 또는 활동에 대한 정책을 만들기 위한 것입니다.

### <a name="create-an-audit-log-retention-policy-in-powershell"></a>PowerShell에서 감사 로그 보존 정책 만들기

다음 단계에 따라 PowerShell에서 감사 로그 보존 정책을 만들 수 있습니다.

1. [보안 및 준수 센터 PowerShell에 연결하기](/powershell/exchange/connect-to-scc-powershell)

2. 다음 명령을 실행하여 감사 로그 보존 정책을 만드세요.

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TenYears -Priority 100
   ```

   이 예에서는 다음 설정으로 "Microsoft Teams Audit Policy"라는 감사 로그 보존 정책을 만듭니다.

   - 정책에 대한 설명입니다.
   - 모든 Microsoft Teams 활동을 유지합니다(*RecordType* 매개 변수로 정의된 대로).
   - Microsoft Teams 감사 로그를 10년 동안 보존합니다.
   - 우선 순위 100위

다음은 감사 로그 보존 정책을 만드는 또 다른 예시입니다. 이 정책은 사용자 admin@contoso.onmicrosoft.com에 대해 6 개월 동안 "사용자 로그인" 활동에 대한 감사 로그를 유지합니다.

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

자세한 정보는 [New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy)를 참조하십시오.

### <a name="view-policies-in-powershell"></a>PowerShell에서 정책 보기

보안 및 준수 센터 PowerShell에서 [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) cmdlet을 사용하여 감사 로그 보존 정책을 볼 수 있습니다.

다음은 조직의 감사 로그 보존 정책에 대한 설정을 표시하는 샘플 명령입니다. 이 명령은 정책을 가장 높은 우선 순위에서 가장 낮은 우선 순위로 정렬합니다.

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> **Get-UnifiedAuditLogRetentionPolicy** cmdlet은 조직의 기본 감사 로그 보존 정책을 반환하지 않습니다.

### <a name="edit-policies-in-powershell"></a>PowerShell에서 정책 편집

보안 및 규정 센터 PowerShell에서 [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet을 사용하여 기존 감사 로그 보존 정책을 편집할 수 있습니다.

### <a name="delete-policies-in-powershell"></a>PowerShell에서 정책 삭제

보안 및 준수 센터 PowerShell에서 [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) cmdlet을 사용하여 감사 로그 보존 정책을 삭제할 수 있습니다. 조직에서 정책이 제거되는 데 최대 30분이 걸릴 수 있습니다.

## <a name="more-information"></a>추가 정보

앞서 설명한 것처럼 Azure Active Directory, Exchange Online, SharePoint Online 및 비즈니스용 OneDrive의 작업에 대한 감사 레코드는 기본적으로 1년 동안 보존됩니다. 다음 표에는 기본 감사 로그 보존 정책에 포함된 모든 레코드 유형(이러한 각 서비스에 대한)이 나열되어 있습니다. 이는 특정 레코드 유형, 작업 또는 사용자에 대해 사용자 지정 감사 로그 보존 정책이 우선하지 않는 한 이 레코드 유형의 작업에 대한 감사 로그가 1년 동안 보존됨을 의미합니다. 각 레코드 유형에 대한 Enum 값(감사 레코드의 RecordType 속성 값으로 표시됨)이 괄호 안에 표시됩니다.

<br>

****

|AzureActiveDirectory|Exchange |SharePoint 또는 OneDrive|
|---|---|---|
|AzureActiveDirectory (8)|ExchangeAdmin (1)|ComplianceDLPSharePoint (11)|
|AzureActiveDirectoryAccountLogon (9)|ExchangeItem (2)|ComplianceDLPSharePointClassification (33)|
|AzureActiveDirectoryStsLogon (15)|캠페인 (62)|프로젝트 (35)|
||ComplianceDLPExchange (13)|SharePoint (4)|
||ComplianceSupervisionExchange (68)|SharePointCommentOperation (37)|
||CustomerKeyServiceEncryption (69)|SharePointContentTypeOperation (55)|
||ExchangeAggregatedOperation (19)|SharePointFieldOperation (56)|
||ExchangeItemAggregated (50)|SharePointFileOperation (6)|
||ExchangeItemGroup (3)|SharePointListOperation (36)|
||InformationBarrierPolicyApplication (53)|SharePointSharingOperation (14)|
||||
