---
title: 클라우드에서 클라우드 첨부 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 조사 또는 사례에서 Advanced eDiscovery 클라우드 첨부 파일을 수집하는 데 사용할 수 있습니다.
ms.openlocfilehash: 22986c8f844f035f4da57ccdfa3ee523e39118ec
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717559"
---
# <a name="collect-cloud-attachments-in-advanced-ediscovery-preview"></a>클라우드에서 클라우드 첨부 Advanced eDiscovery(미리 보기)

클라우드 첨부 파일은 일반적으로 사이트 및 웹 사이트에 저장되는 문서에 SharePoint 링크 OneDrive. 따라서 전자 메일 메시지 또는 Teams 대화에 문서의 실제 복사본을 첨부하는 대신 파일에 대한 링크를 공유할 수 있습니다. 클라우드 첨부 파일은 문서를 공유하고 조직의 다른 사용자와 공동 작업을 하는 효과적인 방법입니다. 그러나 클라우드 첨부 파일은 공유 문서의 실제 콘텐츠가 아닌 클라우드 첨부 파일 링크만 eDiscovery 검색에서 반환하기 때문에 eDiscovery 워크플로 중에 어려움이 있습니다. 이 문제를 해결하기 위해 Advanced eDiscovery 클라우드 첨부 파일을 수집하기 위한 두 가지 솔루션을 제공합니다.  

- 클라우드 첨부 파일에 연결된 문서의 라이브 버전을 수집합니다.

- 클라우드 첨부 파일에서 공유된 문서의 버전을 수집합니다.

## <a name="collecting-cloud-attachments"></a>클라우드 첨부 파일 수집

초안 컬렉션을 만들고 검색 결과에 클라우드 첨부 파일이 포함된 항목이 포함된 경우 초안 컬렉션을 검토 집합으로 커밋할 때 클라우드 첨부 파일 대상을 수집할 수 있는 옵션이 제공됩니다. 이 옵션을 선택하면 Advanced eDiscovery 링크된 문서를 검토 집합에 추가합니다. 이렇게 하면 대상 문서를 검토하고 문서가 사례 또는 조사와 관련이 있는지 확인할 수 있습니다.

다음 스크린샷은 검토 집합에 컬렉션을 커밋할 때 클라우드 첨부 파일 대상을 포함하기 위한 옵션을 보여줍니다.

![검토 집합에 컬렉션을 커밋할 때 클라우드 첨부 파일을 포함하기 위한 옵션](../media/CollectCloudAttachments1.png)

> [!NOTE]
>- 큰 대/소문자 형식을 Advanced eDiscovery 검토 집합에 클라우드 첨부 파일을 포함하기 위한 옵션이 기본적으로 선택되어 있으며 선택을 선택하지 않습니다. [](advanced-ediscovery-large-cases.md)<br/>
>- 또한 검토 집합에 클라우드 첨부 파일의 모든 버전(공유된 버전 외에)을 포함할 수도 있습니다.  
컬렉션을 검토 집합으로 커밋하는 지침은 검토 집합에 초안 컬렉션 [커밋을 참조하세요.](commit-draft-collection.md)

## <a name="collecting-the-version-shared-in-a-cloud-attachment"></a>클라우드 첨부 파일에서 공유되는 버전 수집

클라우드 Advanced eDiscovery 수집을 위한 워크플로에는 최신 버전의 클라우드 첨부 파일을 검토 집합에 추가하는 작업만 포함됩니다. 즉, 수집되어 검토 집합에 추가되는 버전은 원래 클라우드 첨부 파일에서 공유된 버전과 다를 수 있습니다. 따라서 공유 당시 클라우드 첨부 파일에 있는 콘텐츠가 제거되어 검토 집합에 추가된 현재 버전에 존재하지 않을 수 있습니다.

이제 조직에서는 문서가 클라우드 첨부 파일로 공유된 Microsoft 365 보존 레이블을 사용하여 문서의 버전을 보존할 수 있습니다. 이 작업을 수행하기 위해 조직에서 보존 레이블을 만들고, 클라우드 첨부 파일에 레이블을 적용하는 옵션을 선택한 다음, 조직 및 클라우드에 저장된 문서에 레이블을 SharePoint OneDrive. 이 구성을 설정하면 파일을 공유할 때 문서의 복사본이 만들어집니다. 또한 문서를 수정하고 클라우드 첨부 파일로 다시 공유하면 수정된 버전도 보존됩니다. 파일을 수정하고 다시 공유하면 파일의 새 복사본이 새 버전으로 보존됩니다.

클라우드 첨부 파일 공유 버전을 보존하면 조직에서 현재 라이브 버전이 아닌 공유된 문서의 특정 버전에 대한 관련 콘텐츠의 보존 및 모음 범위를 지정하는 데 도움이 될 수 있습니다. 이 보존 솔루션을 구현하면 클라우드 첨부 파일의 현재 라이브 버전과 클라우드 첨부 파일에서 공유된 버전이 모두 수집되어 검토 집합에 추가됩니다.

보존 레이블을 설정하고 클라우드 첨부 파일에 자동으로 적용하는 방법에 대한 지침은 클라우드 첨부 파일에 레이블 자동 [적용을 참조하세요.](apply-retention-labels-automatically.md#auto-apply-labels-to-cloud-attachments)

다음 스크린샷은 검토 집합에 추가된 *XYZ* Research.docx라는 클라우드 첨부 파일 문서를 보여줍니다. 문서가 채팅 대화에서 클라우드 첨부 파일로 Teams했습니다. 검토 집합에는 원래 클라우드 첨부 파일에서 공유된 버전도 포함되어 있습니다. 이 버전의 클라우드 첨부 파일 이름은 시스템에 의해 생성되어 작성자는 에 의해 **SharePoint.**

![검토 집합에 공유된 클라우드 첨부 파일 버전](../media/CollectCloudAttachments2.png)

또한 현재 라이브 버전과 공유된 버전은 부모 개체의 **FamilyId(예:** 전자 메일 메시지 또는 Teams 채팅 대화)의 **FamilyId** 속성 값이 동일합니다. 이렇게 하면 클라우드 첨부 파일을 공유된 항목으로 그룹화할 수 있습니다.

보존 레이블을 구현하고 SharePoint 문서에 레이블을 자동으로 적용한 후에도 초안 컬렉션을 검토 집합에 커밋할 때 클라우드 첨부 파일을 수집하는 옵션을 선택합니다. 클라우드 첨부 파일이 수집될 때 현재 라이브 버전과 원래 공유된 버전이 모두 검토 집합에 추가됩니다.
