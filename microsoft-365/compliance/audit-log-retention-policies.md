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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 감사 로그 보존 정책은 Microsoft 365의 새로운 고급 감사 기능의 일부입니다. 감사 로그 보존 정책을 사용하여 조직에서 감사 로그를 보존할 기간을 지정할 수 있습니다.
ms.openlocfilehash: 32bb9510d789b56bc48b133dee4abd948009e3a9
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960254"
---
# <a name="manage-audit-log-retention-policies"></a>로그 보존 정책 감사 관리

보안 및 준수 센터에서 감사 로그 보존 정책을 작성하고 관리할 수 있습니다. 감사 로그 보존 정책은 Microsoft 365의 새로운 고급 감사 기능의 일부입니다. 감사 로그 보존 정책을 사용하여 조직에서 감사 로그를 보존할 기간을 지정할 수 있습니다. 감사 로그를 최대 1년 동안 보유할 수 있습니다. 다음 조건을 기준으로 정책을 만들 수 있습니다.

- 하나 이상의 Microsoft 365 서비스에서의 모든 활동

- 모든 사용자 또는 특정 사용자가 수행하는 (특정 서비스에서의) 특정 활동

- 조직에 여러 정책이 있을 때 더 중시하는 정책을 지정하는 우선 순위

## <a name="default-audit-log-retention-policy"></a>기본 로그 보존 정책 감사

Microsoft 365의 고급 감사는 모든 조직에 기본 감사 로그 보존 정책을 제공합니다. 이 정책은 1년 동안 모든 Exchange, SharePoint 및 Azure Active Directory 감사 레코드를 보존합니다. 이 기본 정책은 **Workload** 속성(활동이 발생한 서비스)에 대한 **AzureActiveDirectory**, **Exchange** 또는 **SharePoint** 값을 포함하는 감사 레코드를 유지합니다. 기본 정책은 수정할 수 없습니다. 기본 정책에 포함된 각 워크로드의 레코드 유형 목록은 이 문서의 [추가 정보](#more-information) 섹션을 참조하십시오.

> [!NOTE]
> 기본 감사 로그 보존 정책은 Office 365 또는 Microsoft 365 E5 라이선스가 할당되었거나 Microsoft 365 E5 준수 애드온 라이선스가 있는 사용자가 수행한 활동에 대한 감사 레코드에만 적용됩니다. 조직에 E5 이외의 사용자가 있는 경우 해당 감사 레코드는 90일 동안 유지됩니다.

## <a name="before-you-begin"></a>시작하기 전에

- 사용자는 감사 보존 정책을 만들거나 수정하기 위해 보안 및 준수 센터에서 조직 구성 역할을 할당 받아야 합니다.

- 조직에서 최대 50개의 감사 로그 보존 정책을 가질 수 있습니다.

- 감사 로그를 90일 이상 유지하려면 감사 로그를 생성한 사용자에게 Office 365 또는 Microsoft 365 E5 라이선스가 할당되거나 Microsoft 365 E5 준수 애드온 라이선스가 있어야 합니다.

- 조직에서 생성한 모든 사용자 지정 감사 로그 보존 정책은 기본 보존 정책보다 우선합니다. 예를 들어, 보존 기간이 1년보다 짧은 Exchange 사서함 활동에 대한 감사 로그 보존 정책을 만들면 Exchange 사서함 활동에 대한 감사 레코드가 사용자 지정 정책에 의해 지정된 기간 동안 유지됩니다.

## <a name="create-an-audit-log-retention-policy-in-the-security--compliance-center"></a>보안 및 준수 센터에서 감사 로그 보존 정책 생성

1. [https://protection.office.com](https://protection.office.com)으로 이동하여 지정된 사용자 계정으로보안 및 준수 센터의 조직 구성 역할로 로그인하십시오. 

2. 보안 및 규정 준수 센터의 왼쪽 창에서 **검색** > **감사 로그 검색**을 클릭하십시오.

    **감사 로그 검색** 페이지가 표시됩니다.

    ![감사 로그 검색 페이지](media/AuditLogRetentionPolicy1.png)

3. **새 보존 정책**을 클릭한 후 플라이 아웃 페이지에서 다음 필드를 완료하십시오.

    ![감사 로그 보존 정책 플라이 아웃 페이지](media/AuditLogRetentionPolicy2.png)

   a. **이름:** 감사 로그 보존 정책의 이름 이 이름은 조직에서 고유해야 합니다.
   
   b. **설명:** 선택 사항이지만 레코드 유형 또는 워크로드, 정책에 지정된 사용자 및 기간과 같은 정책에 대한 정보를 제공하는 데 도움이 됩니다.

   c. **레코드 유형:** 정책이 적용되는 감사 레코드 유형. 하나 이상의 레코드 유형을 선택하면 정책이 선택한 레코드 유형의 모든 활동에 적용되므로 활동을 선택할 수 없습니다. 또한 이 속성을 비워두면 **사용자** 상자에서 사용자를 선택해야합니다.

   d. **활동:** 이 상자를 사용하여 선택한 레코드 유형에서 활동을 선택하십시오. 정책을 적용할 특정 활동을 선택할 수 있습니다. 특정 활동을 선택하지 않으면 선택한 레코드 유형의 모든 활동에 정책이 적용됩니다.

   e. **사용자:** 정책을 적용할 하나 이상의 사용자를 선택하십시오. 이 상자를 비워 두면 정책이 모든 사용자에 게 적용됩니다. **레코드 유형**을 비워둔 경우, 반드시 사용자를 선택해야 합니다.

   f. **기간:** 정책 기준을 충족하는 감사 로그를 보유하는 시간입니다.

   g. **우선 순위:** 이 값은 조직의 감사 로그 보존 정책이 처리되는 순서를 결정합니다. 값이 높을수록 우선 순위가 높습니다. 예를 들어, 우선 순위 값이 **5**인 정책은 우선 순위 값이 **0**인 정책보다 우선합니다. 앞에서 설명한 것처럼 사용자 지정 감사 로그 보존 정책은 조직의 기본 정책보다 우선합니다.

6. **저장**을 클릭하여 새 감사 로그 보존 정책을 만듭니다. 

이 시점에서는 보존 정책이 생성되었다는 표시가 없습니다. 감사 로그 보존 정책의 속성 보기에 대해서는 다음 섹션을 참조하십시오.

## <a name="create-an-audit-log-retention-policy-in-powershell"></a>PowerShell에서 감사 로그 보존 정책 생성

Office 365 보안 및 준수 센터 PowerShell을 사용하여 감사 로그 보존 정책을 만들 수도 있습니다. 

1. [보안 및 준수 센터 PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)

2. 다음 명령을 실행하여 감사 로그 보존 정책을 생성하십시오. 

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TwelveMonths -Priority 100
   ```
    
    이 예에서는 다음 설정으로 "Microsoft Teams Audit Policy"라는 감사 로그 보존 정책을 만듭니다.

   - 정책에 대한 설명입니다.

   - 모든 Microsoft Teams 활동을 유지합니다(*RecordType* 매개 변수로 정의된 대로).

   - 1년 동안 Microsoft Teams 감사 로그를 유지합니다.

   - 우선 순위 100위

다음은 감사 로그 보존 정책을 만드는 또 다른 예시입니다. 이 정책은 사용자 admin@contoso.onmicrosoft.com에 대해 6 개월 동안 "사용자 로그인" 활동에 대한 감사 로그를 유지합니다.

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

자세한 정보는 [New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-unifiedauditlogretentionpolicy)를 참조하십시오.

## <a name="view-audit-log-retention-policies"></a>로그 보존 정책 감사 보기

현재 사용자 지정 감사 로그 보존 정책을 보는 유일한 방법은 보안 및 규정 준수 센터 PowerShell에서 **Get-UnifiedAuditRetentionPolicy** cmdlet을 사용하는 것입니다. 다음은 조직의 감사 로그 보존 정책에 대한 설정(이전 단계에서 구성한)을 표시하는 샘플 명령입니다. 이 명령은 정책을 가장 높은 우선 순위에서 가장 낮은 우선 순위로 정렬합니다.

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> 현재 **Get-UnifiedAuditLogRetentionPolicy** cmdlet은 조직의 기본 감사 로그 정책을 반환하지 않습니다.

자세한 정보는 [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/get-unifiedauditlogretentionpolicy)를 참조하십시오.

## <a name="more-information"></a>추가 정보

- 보안 및 규정 센터 PowerShell에서 **Set-UnifiedAuditLogRetentionPolicy** cmdlet을 사용하여 기존 감사 로그 보존 정책을 수정하십시오. 자세한 정보는 [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/set-unifiedauditlogretentionpolicy)를 참조하십시오.

- 보안 및 준수 센터 PowerShell에서 **Remove-UnifiedAuditLogRetentionPolicy** cmdlet을 사용하여 감사 로그 보존 정책을 삭제하십시오. 정책을 완전히 제거하는 데 최대 30분이 걸릴 수 있습니다. 자세한 정보는 [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/remove-unifiedauditlogretentionpolicy)를 참조하십시오.

- 앞에서 설명한 것처럼 Azure Active Directory, Exchange 및 SharePoint의 작업에 대한 감사 레코드는 1년 동안 유지됩니다. 다음 표에는 기본 감사 로그 보존 정책에 포함된 (이러한 서비스 각각에 대한) 모든 레코드 유형이 나열되어 있습니다. 이는 특정 레코드 유형, 작업 또는 사용자에 대해 사용자 지정 감사 로그 보존 정책이 우선하지 않는 한 이 레코드 유형의 작업에 대한 감사 로그가 1년 동안 보존됨을 의미합니다. 각 레코드 유형에 대한 Enum 값(감사 레코드의 RecordType 속성 값으로 표시됨)이 괄호 안에 표시됩니다.

   |AzureActiveDirectory |Exchange  |SharePoint|
   |:---------|:---------|:---------|
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
