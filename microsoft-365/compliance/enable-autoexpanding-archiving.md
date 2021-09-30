---
title: 자동 확장 보관 사용 - 관리자 도움말
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
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: '관리자용: 자동 확장 보관을 사용하도록 설정하여 사용자에게 사서함에 대한 추가 저장소를 Exchange Online 방법을 배워야 합니다. 전체 조직 또는 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정할 수 있습니다.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2222cceabc183aeb3cee3021060128a48219747b
ms.sourcegitcommit: f9e038dd8420e7af2d1b0244d3567b376475c641
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015493"
---
# <a name="enable-auto-expanding-archiving---admin-help"></a>자동 확장 보관 사용 - 관리자 도움말

자동 확장 보관 Exchange Online 기능을 사용하여 보관 사서함에 대한 추가 저장소 공간을 사용하도록 설정할 수 있습니다. 자동 확장 보관이 설정되어 있는 경우 저장소 제한인 1.5 TB에 도달할 때까지 사용자의 보관 사서함에 추가 저장소 공간이 자동으로 추가됩니다. 조직의 모든 사용자 또는 특정 사용자에 대해 자동 확장 보관을 끄면 됩니다. 자동 확장 보관에 대한 자세한 내용은 자동 확장 보관 개요를 [참조하세요.](autoexpanding-archiving.md)

## <a name="before-you-enable-auto-expanding-archiving"></a>자동 확장 보관을 사용하도록 설정하기 전에

- 전체 조직 또는 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정하려면 Exchange Online 조직의 전역 관리자 또는 조직 관리 역할 그룹의 구성원이 되어야 합니다. 또는 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정하려면 Mail Recipients 역할이 할당된 역할 그룹의 구성원이 되어야 합니다.

- 자동 확장 보관을 사용하려면 먼저 사용자의 보관 사서함을 사용하도록 설정해야 합니다. 사용자에게 보관 사서함을 사용하도록 Exchange Online 계획 2 라이선스를 할당해야 합니다. 사용자에게 Exchange Online 계획 1 라이선스가 할당된 경우 보관 사서함을 사용하도록 설정하려면 별도의 Exchange Online Archiving 라이선스를 할당해야 합니다. 보관 [사서함 사용 을 참조합니다.](enable-archive-mailboxes.md)

- PowerShell을 사용하여 보관 사서함을 사용하도록 설정할 수도 있습니다. 조직의 [모든](#more-information) 사용자에 대해 보관 사서함을 사용하도록 설정하는 데 사용할 수 있는 PowerShell 명령의 예는 추가 정보 섹션을 참조하세요.

- 자동 확장 보관 기능은 공유 사서함도 지원합니다. 공유 사서함에 대해 보관을 사용하도록 설정하려면 Exchange Online 계획 2 라이선스 또는 Exchange Online 라이선스가 있는 Exchange Online Archiving 계획 1 라이선스가 필요합니다.

- 자동 확장 보관을 사용하면 비활성 사서함을 복구하거나 복원할 [수 없습니다.](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes) 즉, 사서함에 대해 자동 확장 보관을 사용하도록 설정하고 나중에 사서함이 비활성 상태로 설정되어 있는 [](recover-an-inactive-mailbox.md) 경우 비활성 사서함을 활성 사서함으로 복구하거나 [](restore-an-inactive-mailbox.md) 기존 사서함에 내용을 통합하여 복원할 수 없습니다. 비활성 사서함에서 자동 확장 보관을 사용하도록 설정한 경우 데이터를 복구하는 유일한 방법은 사서함의 콘텐츠 검색 도구를 Microsoft 365 규정 준수 센터 사서함에서 데이터를 내보내고 다른 사서함으로 가져오는 것입니다. 자세한 내용은 비활성 사서함 개요의 "비활성 사서함 및 자동 확장 보관함" [섹션을 참조하십시오.](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives)

- 자동 확장 보관을 사용하도록 Exchange 관리 센터 또는 Microsoft 365 규정 준수 센터 사용할 수 없습니다. PowerShell을 사용하여 Exchange Online 합니다. 원격 PowerShell을 Exchange Online 조직에 연결하기 위해 PowerShell을 커넥트 [Exchange Online 참조합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>전체 조직에 대해 자동 확장 보관 사용

전체 조직에 대해 자동 확장 보관을 사용하도록 설정할 수 있습니다. 이 기능을 설정하면 기존 사용자 사서함 및 새로 만든 사용자 사서함에 대해 자동 확장 보관이 사용하도록 설정됩니다. 사용자 사서함을 만들 때 자동 확장 보관 기능이 새 사용자 사서함에 대해 작동하도록 사용자의 기본 보관 사서함을 사용하도록 설정해야 합니다.
  
1. [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)

2. PowerShell에서 Exchange Online 명령을 실행하여 전체 조직에 대해 자동 확장 보관을 사용하도록 설정할 수 있습니다.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>특정 사용자에 대해 자동 확장 보관 사용

조직의 모든 사용자에 대해 자동 확장 보관을 사용하도록 설정하는 대신 특정 사용자에 한해 보관을 사용하도록 설정할 수 있습니다. 일부 사용자만 대용량 보관 저장소 용량을 필요로 할 수 있기 때문에 이 작업을 할 수 있습니다.
  
특정 사용자 및 사용자의 사서함에 대해 자동 확장 보관을 사용하도록 설정하거나 보존 정책에 할당하면 다음과 같은 두 가지 구성이 변경됩니다.
  
- 사용자의 기본 보관 사서함에 대한 저장소 할당량은 10GB(100GB에서 110GB)로 증가합니다. 보관 경고 할당량도 10GB(90GB에서 100GB)로 증가합니다.

- 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더의 저장소 할당량은 10GB(또한 100GB에서 110GB)로 증가합니다. 복구 가능한 항목 경고 할당량도 10GB(90GB에서 100GB)로 증가합니다. 이러한 변경 내용은 보류된 사서함 또는 보존 정책에 할당된 경우만 적용됩니다.

자동 확장 보관이 프로비전되기 전에 발생할 수 있는 저장소 문제를 방지하기 위해 이 추가 공간이 추가되었습니다. 이전  *섹션에서*  설명한 바와 같이 전체 조직에 대해 자동 확장 보관을 사용하도록 설정하면 추가 저장소 공간이 추가되지 않습니다.
  
1. [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)

2. PowerShell에서 Exchange Online 명령을 실행하여 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정할 수 있습니다. 앞서 설명한 것 처럼 사용자의 보관 사서함(기본 보관함)을 사용하도록 설정해야 해당 사용자에 대한 자동 확장 보관을 사용하도록 설정해야 합니다.

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> Exchange 하이브리드 배포에서는 **Enable-Mailbox -AutoExpandingArchive** 명령을 사용하여 기본 사서함이 사내에 있으며 보관 사서함이 클라우드 기반인 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정할 수 없습니다. Exchange 하이브리드 배포에서 클라우드 기반 보관 사서함에 대해 자동 확장 보관을 사용하도록 설정하려면 Exchange Online PowerShell에서 **Set-OrganizationConfig -AutoExpandingArchive** 명령을 실행하여 전체 조직에 대해 자동 확장 보관을 사용하도록 설정해야 합니다. 사용자의 기본 사서함과 보관 사서함이 모두 클라우드 기반인 경우 **Enable-Mailbox -AutoExpandingArchive** 명령을 사용하여 해당 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정할 수 있습니다.
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>자동 확장 보관이 사용하도록 설정되어 있는지 확인

조직에 대해 자동 확장 보관이 사용하도록 설정되어 있는지 확인하기 위해 PowerShell에서 Exchange Online 실행합니다.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

값은 자동 확장 보관이 조직에 대해 사용하도록 설정되어 있는  `True` 것입니다. 
  
특정 사용자에 대해 자동 확장 보관이 사용하도록 설정되어 있는지 확인하기 위해 PowerShell에서 Exchange Online 실행합니다.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

값은 자동 확장 보관이 사용자에 대해 사용하도록 설정되어 있는  `True` 것입니다.
  
자동 확장 보관이 비활성 사서함에 대해 사용하도록 설정되어 있는지 확인하기 위해 PowerShell에서 Exchange Online 실행합니다.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL UserPrincipalName,AutoExpandingArchiveEnabled
```

값은 자동 확장 보관이 비활성 사서함에 대해 사용하도록 설정되어 있는  `True` 것입니다. 값이면 자동 확장 보관을 사용할 `False` 수 없습니다.

자동 확장 보관을 사용하도록 설정한 후 다음에 유의해야 합니다.
  
- **Set-OrganizationConfig -AutoExpandingArchive** 명령을 실행하여 조직에 대해 자동 확장 보관을 사용하도록 설정하는 경우 개별 사서함에서 **Enable-Mailbox -AutoExpandingArchive를** 실행할 수 없습니다. 조직에 대해 자동 확장 보관을 사용하도록 설정하기 위해 **Set-OrganizationConfig** cmdlet을 실행해도 사용자 사서함의  *AutoExpandingArchiveEnabled*  속성은 로 변경되지 `True` 않습니다.

- 마찬가지로 보관 자동 확장을 사용하도록 설정하면  *ArchiveQuota*  및  *ArchiveWarningQuota*  사서함 속성의 값이 변경되지 않습니다. 실제로 사용자 사서함에 대해 자동 확장 보관을 사용하도록 설정하고  *AutoExpandingArchiveEnabled*  속성을 로 설정하면  `True`  *ArchiveQuota*  및  *ArchiveWarningQuota*  속성은 무시됩니다. 사용자의 사서함에 대해 자동 확장 보관을 사용하도록 설정한 후 이러한 사서함 속성의 예는 다음과 같습니다. 

    ![자동 확장 보관을 사용하도록 설정하면 ArchiveQuota 및 ArchiveWarningQuota 속성이 무시됩니다.](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a>추가 정보

- PowerShell을 사용하여 보관 사서함을 사용하도록 설정할 수도 있습니다. 예를 들어 PowerShell에서 다음 명령을 Exchange Online 보관 사서함을 아직 사용하도록 설정하지 않은 모든 사용자에 대해 보관 사서함을 사용하도록 설정할 수 있습니다.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- 조직 또는 특정 사용자에 대해 자동 확장 보관을 설정하면 보관 사서함(복구 가능한 항목 폴더 포함)이 90GB에 도달하면 보관 사서함이 자동 확장 보관함으로 변환됩니다. 추가 저장소 공간을 프로비전하는 데 최대 30일이 걸릴 수 있습니다.

- 자동 확장 보관을 설정한 후 해제할 수 없는 경우 또한 관리자는 자동 확장 보관에 대한 저장소 할당량도 조정할 수 없습니다.

- 자동 확장 보관은 클라우드 기반 보관 사서함에 대해 Exchange 기본 사서함이 있는 사용자를 위해 하이브리드 배포에서 지원됩니다. 그러나 클라우드 기반 보관 사서함에 대해 자동 확장 보관을 사용하도록 설정한 후 사서함을 다시 클라우드 기반 보관 사서함으로 오프보드할 Exchange 없습니다. 자동 확장 보관은 모든 버전의 사서함에 대해 지원되지 Exchange Server.

- 사용자가 보관 사서함의 추가 저장소 영역에 있는 항목에 액세스하는 데 사용할 수 있는 Outlook 클라이언트 목록은 Overview [of auto-expanding archiving의](autoexpanding-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)"자동 확장 보관함의 항목에 액세스하기 위한 Outlook 요구 사항" 섹션을 참조하세요.

- 앞서 설명한 것 처럼 **Enable-Mailbox -AutoExpandingArchive** 명령을 실행할 때 사용자의 기본 보관 사서함의 저장소 할당량(사서함이 보류된 경우 복구 가능한 항목 폴더)에 10GB가 추가됩니다. 이렇게 하면 자동 확장 저장소 공간이 프로비전될 때까지(최대 30일이 걸릴 수) 추가 저장소를 제공합니다. 이 추가 저장소 공간은 **Set-OrganizationConfig -AutoExpandingArchive를** 실행하여 조직의 모든 사서함에 대해 자동 확장 보관을 사용하도록 설정할 때 추가되지 않습니다. 전체 조직에 대해 자동 확장 보관을 사용하도록 설정했지만 특정 사용자에 대해 10GB의 저장소 공간을 더 추가해야 하는 경우 해당 사서함에서 **Enable-Mailbox -AutoExpandingArchive** 명령을 실행할 수 있습니다. 자동 확장 보관이 이미 사용하도록 설정되어 있지만 추가 저장소 공간이 사서함에 추가됩니다.

> [!IMPORTANT]
> 자동 확장 보관은 개별 사용자가 사용하는 사서함 또는 하루 1GB를 초과하지 않는 증가율의 공유 사서함에 한해 지원됩니다. 보관 목적으로 저널링, 전송 규칙 또는 자동 전달 규칙을 사용하여 메시지를 보관 사서함에 복사할 수 없습니다. 사용자의 보관 사서함은 해당 사용자만을 위한 것입니다. Microsoft는 사용자의 보관 사서함이 다른 사용자의 보관 데이터를 저장하는 데 사용되거나 부적절한 사용의 경우 추가 보관을 거부할 수 있는 권리가 있습니다.
