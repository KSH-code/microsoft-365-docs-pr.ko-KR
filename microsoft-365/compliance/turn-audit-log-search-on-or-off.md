---
title: 감사 켜기 또는 끄기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: 관리자의 감사 로그 검색 기능을 설정하거나 해제하여 Microsoft 365 규정 준수 센터 감사 로그를 검색할 수 있는 기능을 활성화 또는 비활성화하는 방법
ms.openlocfilehash: 793c76d45f2cd7aed43a959dfcb94edeb9869310
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58575327"
---
# <a name="turn-auditing-on-or-off"></a>감사 켜기 또는 끄기

감사 로깅은 엔터프라이즈 조직 및 Microsoft 365 Office 365 설정됩니다. 그러나 조직에서 새 Microsoft 365 Office 365 설정하는 경우 조직의 감사 상태를 확인해야 합니다. 자세한 내용은 이 문서의 [조직에](#verify-the-auditing-status-for-your-organization) 대한 감사 상태 확인 섹션을 참조하세요. 

조직에서 감사를 Microsoft 365 규정 준수 센터 조직의 사용자 및 관리자 활동이 감사 로그에 기록되고 90일 동안 보존되고 사용자에게 할당된 라이선스에 따라 최대 1년 동안 보존됩니다. 그러나 조직에 감사 로그 데이터를 기록하고 보존하지 않을 이유가 있을 수 있습니다. 이러한 경우 전역 관리자는 전역 관리자의 감사를 해제할 Microsoft 365.

> [!IMPORTANT]
> 조직에서 감사를 Microsoft 365 경우 Office 365 관리 활동 API 또는 Azure Sentinel을 사용하여 조직의 감사 데이터에 액세스할 수 없습니다. 이 문서의 단계를 수행하여 감사를 끄면 감사 로그를 사용하여 감사 로그를 검색하거나 Microsoft 365 규정 준수 센터 PowerShell에서 **Search-UnifiedAuditLog** cmdlet을 실행할 때 결과가 Exchange Online 않습니다. 이는 또한 관리 활동 API 또는 Azure Sentinel을 통해 감사 Office 365 사용할 수 없습니다.
  
## <a name="before-you-turn-auditing-on-or-off"></a>감사를 켜거나 끄기 전에

- 조직에서 감사를 설정하거나 해제하려면 Exchange Online 감사 로그 역할이 Microsoft 365 합니다. 기본적으로 이 역할은 Exchange 관리 센터의 사용 권한  페이지에서 준수 관리 및 조직 관리 역할 그룹에 할당됩니다. 조직의 전역 Microsoft 365 조직 관리 역할 그룹의 구성원입니다Exchange Online.

    > [!NOTE]
    > 감사를 설정하거나 해제하려면 사용자에게 Exchange Online 권한을 할당해야 합니다. 권한 페이지의 권한 페이지에서 사용자에게 감사  로그 역할을 Microsoft 365 규정 준수 센터 감사를 설정하거나 해제할 수 없습니다. 이는 PowerShell cmdlet의 Exchange Online cmdlet이기 때문에입니다.

- 감사 로그 검색에 대한 단계별 지침은 감사 로그 [검색을 참조하세요.](search-the-audit-log-in-security-and-compliance.md) 관리 활동 API의 Microsoft 365 자세한 내용은 Microsoft 365 관리 API [시작을 참조하세요.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="verify-the-auditing-status-for-your-organization"></a>조직의 감사 상태 확인

조직에 대한 감사가 설정되어 있는지 확인하기 위해 [PowerShell에서](/powershell/exchange/connect-to-exchange-online-powershell)다음 명령을 Exchange Online 있습니다.

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

`True` _UnifiedAuditLogIngestionEnabled_ 속성의 값은 감사가 켜져 있는 것입니다. 값은 `False` 감사가 켜져 있지 않다는 것입니다.

## <a name="turn-on-auditing"></a>감사 켜기

조직에 대한 감사가 설정되어 있지 않은 경우 조직에서 또는 PowerShell을 사용하여 Microsoft 365 규정 준수 센터 수 Exchange Online 있습니다. 감사 로그를 검색할 때 결과를 반환하려면 감사를 설정한 후 몇 시간이 걸릴 수 있습니다.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>준수 센터를 사용하여 감사 켜기

1. <https://compliance.microsoft.com>으로 이동하여 로그인합니다.

2. 창의 왼쪽 탐색 창에서 Microsoft 365 규정 준수 센터 **클릭합니다.**

   조직에 대한 감사가 설정되어 있지 않은 경우 사용자 및 관리자 활동 기록을 시작하라는 배너가 표시됩니다.

   ![감사 페이지의 배너.](../media/AuditingBanner.png)

3. 사용자 **및 관리자 활동 기록 시작 배너를** 클릭합니다.

   변경을 적용하는 데 최대 60분이 걸릴 수 있습니다.

### <a name="use-powershell-to-turn-on-auditing"></a>PowerShell을 사용하여 감사 켜기

1. [Exchange Online PowerShell에 연결합니다](/powershell/exchange/connect-to-exchange-online-powershell).

2. 다음 PowerShell 명령을 실행하여 감사를 켜야 합니다.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    변경이 적용되는 데 최대 60분이 걸릴 수 있습니다.
  
## <a name="turn-off-auditing"></a>감사 끄기

감사를 Exchange Online PowerShell을 사용하여 감사를 해제해야 합니다.
  
1. [Exchange Online PowerShell에 연결합니다](/powershell/exchange/connect-to-exchange-online-powershell).

2. 다음 PowerShell 명령을 실행하여 감사를 해제합니다.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 잠시 후 감사가 꺼져 있는지(사용 안 하게) 확인해야 합니다. 이 작업을 수행하는 방법은 다음 두 가지입니다.

    - PowerShell Exchange Online 다음 명령을 실행합니다.

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      `False` _UnifiedAuditLogIngestionEnabled_ 속성의 값은 감사가 해제되어 있는 것입니다.

    - 에서 **감사** 페이지로 Microsoft 365 규정 준수 센터.

      조직에 대한 감사가 설정되어 있지 않은 경우 사용자 및 관리자 활동 기록을 시작하라는 배너가 표시됩니다.
