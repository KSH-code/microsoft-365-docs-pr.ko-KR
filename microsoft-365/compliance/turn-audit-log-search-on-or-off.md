---
title: 감사 로그 검색 켜기 또는 끄기
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
description: 관리자가 감사 로그를 검색할 수 있도록 설정하거나 사용하지 않도록 설정하기 위해 보안 & 준수 센터에서 감사 로그 검색 기능을 켜거나 끄는 방법
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976331"
---
# <a name="turn-audit-log-search-on-or-off"></a>감사 로그 검색 켜기 또는 끄기

Microsoft 365 및 Office 365 엔터프라이즈 조직에서는 기본적으로 감사 로그 검색이 켜져 있습니다. 여기에는 E3/G3 또는 E5/G5 구독이 있는 조직이 포함됩니다. 준수 센터에서 감사 로그 검색을 설정하면 조직의 사용자 및 관리자 활동이 감사 로그에 기록되고 90일 동안, 그리고 사용자에게 할당된 라이선스에 따라 최대 1년 동안 보존됩니다. 그러나 조직에 감사 로그 데이터를 기록하고 보존하지 않을 이유가 있을 수 있습니다. 이러한 경우 전역 관리자는 Microsoft 365에서 감사를 해제할 수 있습니다.

> [!IMPORTANT]
> Microsoft 365에서 감사 로그 검색을 끄면 Office 365 관리 활동 API 또는 Azure Sentinel을 사용하여 조직의 감사 데이터에 액세스할 수 없습니다. 이 문서의 단계를 수행하여 감사 로그 검색을 끄면 보안 및 준수 센터를 사용하여 감사 로그를 검색하거나 Exchange Online PowerShell에서 **Search-UnifiedAuditLog** cmdlet을 & 결과가 반환되지 않습니다. 즉, Office 365 관리 활동 API 또는 Azure Sentinel을 통해 감사 로그를 사용할 수 없습니다.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>감사 로그 검색을 켜거나 끄기 전에

- Microsoft 365 조직에서 감사 로그 검색을 설정하거나 해제하려면 Exchange Online에서 감사 로그 역할을 할당해야 합니다. 기본적으로 이 역할은 Exchange 관리 센터의 사용 권한  페이지에서 준수 관리 및 조직 관리 역할 그룹에 할당됩니다. Microsoft 365의 전역 관리자는 Exchange Online의 조직 관리 역할 그룹의 구성원입니다. 
    
    > [!NOTE]
    > 감사 로그 검색을 설정하거나 해제하려면 사용자에게 Exchange Online에서 사용 권한을 할당해야 합니다. 보안 및 준수 센터의 사용  권한 페이지에서 사용자에게 감사 로그 역할을 & 감사 로그 검색을 설정하거나 해제할 수 없습니다. 이는 주 cmdlet이 Exchange Online PowerShell cmdlet이기 때문에입니다. 
    
- 감사 로그 검색에 대한 단계별 지침은 보안 및 준수 센터에서 감사 [로그를 & 참조하세요.](search-the-audit-log-in-security-and-compliance.md) Microsoft 365 관리 활동 API에 대한 자세한 내용은 [Microsoft 365 관리 API 시작을 참조하세요.](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)

- 감사 로그 검색이 켜져 있는지 확인하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    `True` _UnifiedAuditLogIngestionEnabled_ 속성의 값은 감사 로그 검색이 켜져 있는지를 나타냅니다. 
    
## <a name="turn-on-audit-log-search"></a>감사 로그 검색 켜기

조직에 대해 감사 로그 검색이 설정되어 있지 않은 경우 준수 센터에서 또는 Exchange Online PowerShell을 사용하여 로그 검색을 켜면 됩니다. 감사 로그를 검색할 때 결과를 반환하려면 감사 로그 검색을 켜고 몇 시간이 걸릴 수 있습니다.
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>준수 센터를 사용하여 감사 로그 검색 켜기

1. [준수 센터로 이동하여](https://protection.office.com) 로그인합니다.

2. 준수 센터에서 검색 감사 로그  >  **검색으로 이동 합니다.**

   조직에 대해 감사 로그 검색이 설정되어 있지 않은 경우 사용자 및 관리자 활동을 기록하기 위해 감사를 설정해야 하다는 배너가 표시됩니다.

3. 감사 **켜기 를 클릭합니다.**

    ![감사 켜기 클릭](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    감사 로그가 준비되고 있으며 몇 시간 후에 사용자 및 관리자 활동을 검색할 수 있도록 배너가 업데이트되었습니다.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>PowerShell을 사용하여 감사 로그 검색 켜기

1. [Exchange Online PowerShell에 연결](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Office 365에서 감사 로그 검색을 켜기 위해 다음 PowerShell 명령을 실행합니다.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    변경이 적용되는 데 최대 60분이 걸릴 수 있습니다.
  
## <a name="turn-off-audit-log-search"></a>감사 로그 검색 끄기

Exchange Online PowerShell을 사용하여 감사 로그 검색을 해제해야 합니다.
  
1. [Exchange Online PowerShell에 연결](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. 다음 PowerShell 명령을 실행하여 감사 로그 검색을 해제합니다.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 잠시 후 감사 로그 검색이 꺼져 있는지(사용하지 않도록 설정) 확인해야 합니다. 이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.

    - Exchange Online PowerShell에서 다음 명령을 실행합니다.

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      `False` _UnifiedAuditLogIngestionEnabled_ 속성의 값은 감사 로그 검색이 꺼져 있는 것입니다. 

    - 준수 [센터에서](https://protection.office.com)검색 감사 **로그** \> **검색으로 이동 합니다.**

      사용자 및 관리자 활동을 기록하기 위해 감사를 설정해야 하다는 배너가 표시됩니다.
