---
title: 삭제된 그룹 Microsoft 365 복원
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 삭제된 그룹은 30일 동안 보존되고 그룹을 복원할 수 있습니다. 30일이 지난 후 그룹 및 해당 콘텐츠는 영구적으로 삭제됩니다.
ms.openlocfilehash: 926cfa18972a7ca72009258b02b565bd28a183be
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165703"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>삭제된 그룹 Microsoft 365 복원

그룹을 삭제한 경우 기본적으로 30일 동안 보존됩니다. 이 30일 기간은 그룹을 복원할 수 있기 때문에 "소프트 삭제"로 간주됩니다. 30일이 지난 후 그룹 및 관련 콘텐츠는 영구적으로 삭제되고 복원할 수 없습니다.

그룹이 복원되면 다음 콘텐츠가 복원됩니다.
  
- Azure Active Directory(AD) Microsoft 365, 속성 및 구성원을 지정합니다.
    
- 그룹의 전자 메일 주소입니다.
    
- Exchange Online 받은 편지함 및 일정을 공유합니다.
    
- SharePoint 온라인 팀 사이트 및 파일.
    
- OneNote 전자 필기장
    
- Planner
    
- Teams

- Yammer 및 그룹 콘텐츠(Microsoft 365 그룹이 Yammer)

- Power BI 작업 [영역](/power-bi/collaborate-share/service-create-workspaces)

> [!NOTE]
> 이 문서에서는 그룹만 복원하는 Microsoft 365 설명되어 있습니다. 다른 모든 그룹은 한 번 삭제하면 복원할 수 없습니다.

## <a name="restore-a-group"></a>그룹 복원

# <a name="outlook"></a>[Outlook](#tab/outlook)

Microsoft 365 그룹의 소유자인 경우 다음 단계를 수행하여 그룹 웹용 Outlook 복원할 수 있습니다.

1. 삭제된 [그룹 페이지에서](https://outlook.office.com/people/group/deleted)그룹  노드 아래에서 그룹 관리 옵션을 **선택한** 다음 **삭제를 선택합니다.**

2. 복원할 **그룹** 옆의 복원 탭을 클릭합니다.

삭제된 그룹이 여기에 나타나지 않는 경우 관리자에게 문의하십시오.

# <a name="admin-center"></a>[관리 센터](#tab/admin-center)

전역 관리자 또는 그룹 관리자인 경우 그룹에서 삭제된 그룹을 복원할 수 Microsoft 365 관리 센터.

1. [관리 센터](https://admin.microsoft.com)로 이동합니다.
2. 그룹을 **확장한** 다음 삭제된 **그룹을 클릭합니다.**
3. 복원할 그룹을 선택한 다음 그룹 **복원 을 클릭합니다.**

> [!NOTE]
> 경우에 따라 그룹 및 모든 데이터를 복원하는 데 24시간이 걸릴 수 있습니다. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>그룹에 대한 Microsoft 365 있나요?

Microsoft [Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 방문하여 질문을 게시하고 Microsoft 365 그룹에 대한 대화에 참여하세요. 
  
## <a name="related-content"></a>관련 콘텐츠

[PowerShell을 Microsoft 365 그룹](../../enterprise/manage-microsoft-365-groups-with-powershell.md) 관리(문서)\
[Remove-UnifiedGroup cmdlet을](/powershell/module/exchange/remove-unifiedgroup) 사용하여 그룹 삭제(문서)\
[그룹에 연결된 팀 사이트 설정](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) 관리(문서)\
[사용자 계정에서 Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) 삭제(문서)
