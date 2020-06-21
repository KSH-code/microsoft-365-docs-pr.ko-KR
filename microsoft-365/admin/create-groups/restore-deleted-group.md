---
title: 삭제된 그룹 복원
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 삭제 된 Microsoft 365 그룹을 복원 하는 방법을 알아봅니다.
ms.openlocfilehash: d7cf548816af1661298458f27c704d654845075d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818510"
---
# <a name="restore-a-deleted-group"></a>삭제 된 그룹 복원

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

그룹을 삭제 한 경우에는 기본적으로 30 일간 보존 됩니다. 이 30 일의 기간은 여전히 그룹을 복원할 수 있기 때문에 "일시 삭제"로 간주 됩니다. 30 일이 지나면 그룹 및 관련 내용이 영구적으로 삭제 되며 복원할 수 없습니다.

그룹이 복원되면 다음 콘텐츠가 복원됩니다.
  
- Azure AD (Active Directory) Microsoft 365 Groups 개체, 속성 및 구성원
    
- 그룹의 전자 메일 주소입니다.
    
- Exchange Online 공유 받은 편지함 및 일정
    
- SharePoint Online 팀 사이트 및 파일
    
- OneNote 전자 필기장
    
- Planner
    
- Teams

- Yammer 그룹 및 그룹 콘텐츠 (Yammer에서 Microsoft 365 그룹이 만들어진 경우)

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a>웹에서 Outlook을 사용 하 여 소유한 그룹 복원

Microsoft 365 그룹의 소유자 인 경우 다음 단계를 수행 하 여 웹용 Outlook에서 그룹을 직접 복원할 수 있습니다.

1. 삭제 된 [그룹 페이지](https://outlook.office.com/people/group/deleted)에서 **그룹** 노드 아래의 **그룹 관리** 옵션을 선택한 다음 **삭제**를 선택 합니다.

2. 복원 하려는 그룹 옆에 있는 **복원** 탭을 클릭 합니다.

삭제 된 그룹이 여기에 표시 되지 않으면 관리자에 게 문의 하십시오.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 그룹 복원

전역 관리자 또는 그룹 관리자 인 경우 Microsoft 365 관리 센터에서 삭제 된 그룹을 복원할 수 있습니다.

1. [관리 센터로](https://admin.microsoft.com)이동 합니다.
2. **그룹**을 확장 한 다음 **삭제 된 그룹**을 클릭 합니다.
3. 복원할 그룹을 선택한 다음 **그룹 복원을**클릭 합니다.

> [!NOTE]
> 경우에 따라 그룹 및 해당 모든 데이터를 복원 하는 데 24 시간이 걸릴 수도 있습니다. 
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Microsoft 365 그룹 영구 삭제

경우에 따라 30 일 일시 삭제 기간이 만료 될 때까지 기다리지 않고 그룹을 영구적으로 제거할 수 있습니다. 이렇게 하려면 PowerShell을 시작하고 이 명령을 실행하여 그룹의 개체 ID를 가져옵니다.
  
```
Get-AzureADMSDeletedGroup
```

영구적으로 삭제 하려는 그룹 (또는 그룹)의 개체 ID를 기록해 둡니다.
  
> [!CAUTION]
> 그룹을 제거하면 그룹 및 해당 데이터가 영구적으로 제거됩니다. 
  
그룹을 제거하려면 PowerShell에서 이 명령을 실행합니다.
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted. 
  
## <a name="got-questions-about-microsoft-365-groups"></a>Microsoft 365 그룹에 대 한 질문이 있나요?

[Microsoft 기술 커뮤니티](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 를 방문 하 여 질문을 게시 하 고 microsoft 365 그룹에 대 한 대화에 참여 하세요. 
  
## <a name="related-articles"></a>관련 문서

[PowerShell을 사용 하 여 Microsoft 365 그룹 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[Remove-UnifiedGroup cmdlet을 사용하여 그룹 삭제](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[그룹에 연결된 팀 사이트 설정 관리](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Outlook에서 그룹 삭제](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
