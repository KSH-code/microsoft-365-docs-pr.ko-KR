---
title: 사이트 및 파일 외부 공유
f1.keywords: NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 89502322-bfbb-43d6-9207-4030f8ce26e0
ROBOTS: NOINDEX
description: '조직 외부의 사용자와 사이트 및 파일을 공유 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: a0a98c9ead997e4748804e4f8a87533a9943ec4f
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610575"
---
# <a name="share-sites-and-files-externally"></a>사이트 및 파일 외부 공유

조직 외부의 사용자와 공동 작업을 하려면 전체 사이트 또는 특정 파일을 외부에서 공유할 수 있습니다. 공유 설정으로 바로 이동하려면 사용하려는 시나리오를 선택합니다.

- [게스트와 문서에서 공동 작업하기](../../solutions/collaborate-on-documents.md)
- [게스트와 현장에서 공동 작업하기](../../solutions/collaborate-in-site.md)
- [게스트와 팀으로 공동 작업하기](../../solutions/collaborate-as-team.md)
  
## <a name="deciding-how-to-share-your-content"></a>콘텐츠 공유 방법 결정

콘텐츠를 외부와 공유할지 여부와 그 방법을 결정할 때는 다음 사항을 고려해야 합니다.
  
- 사이트의 콘텐츠에 대 한 액세스 권한을 부여 하려는 사람 및 하위 사이트가 무엇을 할 수 있도록 하 시겠습니까?
    
- 조직에서 콘텐츠를 외부와 공유할 수 있는 권한이 부여되는 사용자는 누구입니까? 
    
- 조직 외부의 사람들에게 절대 보여주지 말아야 할 콘텐츠가 있습니까?
    
이러한 질문은 콘텐츠 공유 전략을 계획하는 데 도움이 됩니다.
  
|**실행할 작업**|**원하는 작업**|
|:-----|:-----|
|그룹에 게스트 추가  <br/> |조직 외부의 사용자에 게 팀 사이트의 정보 및 콘텐츠에 대 한 지속적인 액세스를 제공 합니다. 사이트의 정식 사용자처럼 콘텐츠를 만들고 편집하고 볼 수 있어야 합니다.  <br/> |
|문서를 공유 하 고 게스트가 인증을 받아야 합니다.  <br/> |조직 외부의 특정 사용자에 게 검토 또는 공동 작업을 위해 문서에 대 한 보안 액세스 권한을 제공 하지만 이러한 사용자는 사이트의 다른 콘텐츠에 액세스할 필요가 없습니다.  <br/> |
|문서를 공유 하 되 인증은 필요 하지 않습니다.  <br/> |중요하지 않거나 기밀이 아닌 문서에 대한 링크를 조직 외부의 사람과 공유하여 이들이 해당 문서를 보고 자신의 의견을 문서에 업데이트할 수 있도록 합니다. 이러한 사용자는 사이트의 콘텐츠에 액세스할 필요가 없습니다.  <br/> |
   
> [!IMPORTANT]
> 외부 공유를 사용 하지 않도록 설정 하면 현재 액세스 권한이 있는 조직 외부의 사용자에 게 더 이상 액세스 권한이 없게 됩니다. 나중에 외부 공유를 다시 켜면 이러한 사용자에 대 한 액세스가 복원 됩니다. 사용자가 공유 콘텐츠에 액세스 하지 못하도록 차단 하려면 [Office 365 그룹에서](/office365/admin/create-groups/add-or-remove-members-from-groups)해당 콘텐츠를 제거 하거나, 사이트에서 사용 권한을 제거 하거나, [파일 또는 폴더를 공유를 중지](https://support.office.com/article/0a36470f-d7fe-40a0-bd74-0ac6c1e13323)합니다. 
  
## <a name="enable-external-sharing-at-the-organization-level"></a>조직 수준에서 외부 공유를 사용 하도록 설정

외부 공유는 기본적으로 조직 수준에서 설정 되지만 모든 새 사이트에 대해 사용 되지는 않습니다. 자세한 내용은 [외부 공유 개요](/sharepoint/external-sharing-overview)를 참조 하세요. 

> [!NOTE]
>  모든 사이트에 대해 외부 공유를 허용 하려면 조직 수준에서 허용 해야 합니다. 
  
1. [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339)에서 홈 페이지의 검색 상자에 "외부"를 입력 하 고 **사이트 외부 공유**를 선택 합니다.
  
2. 페이지가 열리면 사용자가 기존 guests, 신규 및 기존 손님, 누구나 공유할 수 있는지를 선택 합니다. 
    
3. **저장**을 선택합니다.
    
조직 수준에서 외부 공유를 사용 하도록 설정한 후에는 특정 사이트에 대해 외부 공유를 사용 하지 않도록 설정 하 여 공유 설정을 세부적으로 조정할 수 있습니다. 자세한 내용은 [사이트에 대 한 외부 공유 설정 또는 해제](/sharepoint/change-external-sharing-site)를 참조 하세요.
  

  

    

