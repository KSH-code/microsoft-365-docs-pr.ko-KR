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
description: 보안 & 준수 센터에서 감사 로그 검색 기능을 설정 하거나 해제 하 여 관리자가 감사 로그를 검색 하는 기능을 사용 하거나 사용 하지 않도록 설정 하는 방법
ms.openlocfilehash: 4571c90c4fa680acd8925e83e32ffcf07de7d626
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819138"
---
# <a name="turn-audit-log-search-on-or-off"></a>감사 로그 검색 켜기 또는 끄기

감사 로그 검색을 시작 하기 전에 사용자 또는 다른 관리자가 감사 로깅을 켜야 합니다. 보안 & 준수 센터에서 감사 로그 검색이 설정 되 면 조직의 사용자 및 관리 활동이 감사 로그에 기록 되 고, 90 일 동안 보존 되며, 사용자에 게 할당 된 라이선스에 따라 최대 1 년까지 유지 됩니다. 그러나 조직에서 감사 로그 데이터를 기록 하 고 유지 하지 않으려는 이유가 있을 수 있습니다. 이러한 경우 전역 관리자가 Microsoft 365에서 감사 기능을 해제 하도록 결정할 수 있습니다.

> [!IMPORTANT]
> Microsoft 365에서 감사 로그 검색을 해제 하면 Office 365 관리 활동 API 또는 Azure 센티널을 사용 하 여 조직의 감사 데이터에 액세스할 수 없습니다. 이 문서에서 설명 하는 단계에 따라 감사 로그 검색을 해제 하면 보안 & 준수 센터를 사용 하 여 감사 로그를 검색 하거나 Exchange Online PowerShell에서 **search-unifiedauditlog** cmdlet을 실행할 때 결과가 반환 되지 않습니다. 이는 또한 Office 365 관리 활동 API 또는 Azure 센티널를 통해 감사 로그를 사용할 수 없다는 것을 의미 합니다.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>감사 로그 검색을 설정 또는 해제 하기 전에

- Microsoft 365 조직에서 감사 로그 검색을 설정 하거나 해제 하려면 Exchange Online에서 감사 로그 역할을 할당 받아야 합니다. 기본적으로이 역할은 Exchange 관리 센터의 **사용 권한** 페이지에 있는 준수 관리 및 조직 관리 역할 그룹에 할당 됩니다. Microsoft 365의 전역 관리자는 Exchange Online의 조직 관리 역할 그룹의 구성원입니다. 
    
    > [!NOTE]
    > 감사 로그 검색을 설정 또는 해제 하려면 사용자에 게 Exchange Online의 사용 권한을 할당 해야 합니다. 보안 & 준수 센터의 **사용 권한** 페이지에서 사용자에 게 감사 로그 역할을 할당 하면 감사 로그 검색을 설정 하거나 해제할 수 없습니다. 이는 기본 cmdlet이 Exchange Online cmdlet 이기 때문입니다. 
    
- 감사 로그를 검색 하는 단계별 지침은 [Security & 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조 하십시오. Microsoft 365 관리 활동 API에 대 한 자세한 내용은 [microsoft 365 관리 api 시작](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)을 참조 하세요.
    
## <a name="turn-on-audit-log-search"></a>감사 로그 검색 켜기

보안 & 준수 센터 또는 PowerShell을 사용 하 여 Microsoft 365에서 감사 로그 검색을 설정할 수 있습니다. 감사 로그 검색을 설정한 후에는 여러 시간이 걸릴 수 있습니다. 감사 로그 검색을 설정 하려면 Exchange Online에서 감사 로그 역할을 할당 받아야 합니다.
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>보안 & 준수 센터를 사용 하 여 감사 로그 검색 설정

1. [보안 & 준수 센터로 이동](https://protection.office.com) 하 여 로그인 합니다.

2. 보안 & 준수 센터에서 **검색** \> **감사 로그 검색**으로 이동 합니다.

   사용자 및 관리 활동을 기록 하기 위해 감사를 설정 해야 한다는 배너가 표시 됩니다.

3. **감사 설정을**클릭 합니다.

    ![감사 사용을 클릭 합니다.](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    이 배너는 감사 로그를 준비 중 이며 몇 시간 내에 사용자 및 관리자 활동을 검색할 수 있다고 표시 하도록 업데이트 됩니다.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>PowerShell을 사용 하 여 감사 로그 검색 설정

1. [Exchange Online PowerShell에 연결](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. 다음 PowerShell 명령을 실행 하 여 Office 365에서 감사 로그 검색을 사용 하도록 설정 합니다.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    변경 내용이 적용 되는 데 최대 60 분이 걸릴 수 있음을 알리는 메시지가 표시 됩니다.
  
## <a name="turn-off-audit-log-search"></a>감사 로그 검색 해제

감사 로그 검색을 해제 하려면 Exchange Online 조직에 연결 된 원격 PowerShell을 사용 해야 합니다. 감사 로그 검색을 설정 하는 것과 마찬가지로 감사 로그 검색을 해제 하려면 Exchange Online에서 감사 로그 역할을 할당 받아야 합니다.
  
1. [Exchange Online PowerShell에 연결](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. 다음 PowerShell 명령을 실행 하 여 Office 365에서 감사 로그 검색을 해제 합니다.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 잠시 후에 감사 로그 검색이 해제 되어 있는지 확인 합니다 (사용 하지 않도록 설정 됨). 이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.

    - PowerShell에서 다음 명령을 실행 합니다.

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      `False` _UnifiedAuditLogIngestionEnabled_ 속성의 값은 감사 로그 검색이 해제 됨을 나타냅니다. 

    - [보안 & 준수 센터](https://protection.office.com)에서 **검색** \> **감사 로그 검색**으로 이동 합니다.

      사용자 및 관리 활동을 기록 하기 위해 감사를 설정 해야 한다는 배너가 표시 됩니다.