---
title: Microsoft Viva 항목의 보안 트리밍
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ms.localizationpriority: medium
description: 보안이 Viva 항목의 항목을 보는 데 사용되는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: babf5cf6179df18bdf9f2cc1d68e5a6ed4b6b772
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60214024"
---
# <a name="security-trimming-in-microsoft-viva-topics"></a>Microsoft Viva 항목의 보안 트리밍

Viva 항목 사용자는 기존 항목의 사용 권한이 Office 365 볼 수 없는 항목에서 정보를 볼 수 없습니다. 주제 페이지에서 사용자에게 보이는 모든 정보(예: SharePoint 사이트, 문서, 파일)는 이미 보도록 허용된 정보입니다. Viva Topics에서 기존의 사용 권한을 변경하지 않습니다.

## <a name="why-two-users-might-have-different-views-of-the-same-topic"></a>두 사용자가 동일한 항목에 대해 서로 다른 보기를 가지는 이유

AI 또는 수동 큐레이션을 통해 항목이 생성될 때 항목의 설명, 대체 이름, 항목에 연결된 사용자뿐만 아니라 항목과 관련된 사이트, 페이지 및 파일을 포함할 수 있습니다. 항목 페이지에서 이 정보를 볼 때 동일한 항목을 보는 두 사용자가 동일한 정보를 볼 수 없습니다.
  
예를 들어 사용자 1이 Neptune 주제 페이지를 보는 경우 다음과 같은 주제 페이지 보기가 표시될 수 있습니다.

![사용자 1에 대한 Neptune 항목입니다.](../media/knowledge-management/user2-topic-view.png) </br> 

그러나 사용자 2가 동일한 Neptune 항목 페이지를 보는 경우 보기는 사용자 1과 다릅니다.  사용자 2는 항목 페이지의 고정된 파일 및 페이지 섹션에서  사용자 1에 대해 나타나지 않는 *DG-2000* 제품 개요 파일을 볼 수 있습니다. 

![사용자 2에 대한 Neptune 항목입니다.](../media/knowledge-management/user1-topic-view.png) </br> 

사용자가 동일한 항목에 대해 볼 수 있는 항목의 차이점은 사용자가 관련 사이트 또는 파일을 볼 수 Office 365 권한이 없는 것일 수 있기 때문에입니다.  Viva Topics는 항목의 항목에 대해 설정된 사용 권한을 사용하며 해당 항목에 대한 액세스를 변경할 수 없습니다. 이 예제에서는 사용자 1이 파일을 볼 수 있는 권한이 Office 365 사용자 1의 항목 페이지에서 *DG-2000* 제품 개요 파일을 볼 수 없습니다.

사용자가 항목에 충분한 정보를 볼 수 없는 경우 해당 항목을 사용할 수 없습니다. 이 경우 강조 표시된 항목은 사용자에게 표시되지 않습니다. 항목에서 유용하게 사용할 수 있는 추가 정보에 대한 사용 권한이 있는 다른 사용자는 해당 항목을 볼 수 있습니다.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>지식 관리자 및 주제 참가자에 대한 항목 사용 권한

항목을 관리할 수 있는 권한이 할당된 사용자(기술 관리자)는 항목 내에서 볼 수 있는 권한이 있는 정보만 볼 수 있습니다.

마찬가지로 항목 작성 및 편집 권한(항목 참가자)은 주제 내에서 볼 수 있는 권한이 있는 정보만 볼 수 있습니다. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI 대 수동 큐레이션 적용된 항목 정보

항목에는 AI에서 생성된 정보와 항목 참가자 또는 지식 관리자가 추가하거나 편집한 정보가 포함될 수 있습니다.

 - AI에 의해 추가된 항목 정보는 원본 콘텐츠에 접근 권한이 있는 사용자에게만 표시됩니다.
 - 항목 참가자 또는 기술 관리자가 수동으로 추가하거나 편집한 항목 설명 및 사용자 정보는 해당 항목을 볼 수 있는 모든 사람이 볼 수 있습니다.
 - 파일, 페이지 및 사이트는 수동으로 추가되었든 AI에 의해 추가되었든 관계없이 원본 콘텐츠 접근 권한이 있는 사용자에게만 표시됩니다.

다음 표에서는 사용자의 사용 권한에 따라 특정 항목에서 볼 수 있는 사용자( 주제 뷰어, 참가자 및 기술 관리자)에 대해 설명합니다.

|토픽 항목|사용자가 볼 수 있는 내용|
|:---------|:------------------|
|토픽 이름|사용자는 항목 센터에서 항목 이름을 볼 수 있습니다. 사용자가 원본 콘텐츠에 대한 사용 권한이 없는 경우 또는 사용자에게 관련성이 낮은 경우 일부 항목은 표시되지 않을 수 있습니다.|
|토픽 설명|AI에서 생성된 설명은 소스 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다. 수동으로 입력하거나 편집한 설명은 모든 사용자에게 표시됩니다.|
|사용자|고정된 사용자는 모든 사용자에게 표시됩니다. 추천된 사용자는 소스 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|
|파일|파일은 소스 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|
|페이지|페이지는 소스 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|
|사이트|사이트는 소스 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|




## <a name="see-also"></a>참고 항목

