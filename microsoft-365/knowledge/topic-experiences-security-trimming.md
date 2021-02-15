---
title: Microsoft Viva Topics 보안 트리밍
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: 항목을 보는 데 보안이 사용되는 방식에 대한 개요입니다.
ms.openlocfilehash: fc8e2a08fcf9af266aee49eee878738f7f17aa59
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107521"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Microsoft Viva Topics 보안 트리밍 

Viva Topics 사용자는 기존 Office 365 권한으로 인해 사용자가 볼 수 없는 항목의 정보를 볼 수 없습니다. 사용자가 항목 페이지에 표시하는 모든 항목(예: SharePoint 사이트, 문서, 파일)은 이미 볼 수 있는 정보가 됩니다. Viva Topics는 기존 사용 권한을 변경하지 않습니다.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>두 사용자가 동일한 항목에 대해 서로 다른 보기를 사용할 수 있는 이유

AI 또는 수동 큐레이터를 통해 항목을 만들 때 항목에 대한 설명, 대체 이름, 항목과 관련된 사용자, 해당 항목과 관련된 사이트, 페이지 및 파일에 대한 설명이 포함될 수 있습니다. 이 정보를 항목 페이지에서 볼 때 동일한 항목을 보는 두 사용자가 동일한 정보를 볼 수 없습니다.
  
예를 들어 사용자 1이 Neptune 항목 페이지를 볼 때 항목 페이지의 이 보기가 표시될 수 있습니다.

![사용자 1에 대한 Neptune 항목](../media/knowledge-management/user2-topic-view.png) </br> 

그러나 사용자 2가 동일한 Neptune 항목 페이지를 보는 경우 해당 보기는 사용자 1과 다릅니다.  사용자 2는 항목 페이지의 고정된 파일 및 페이지 섹션에서  사용자 1에 대해 나타나지 않는 *DG-2000* 제품 개요 파일을 볼 수 있습니다. 

![사용자 2에 대한 Neptune 항목](../media/knowledge-management/user1-topic-view.png) </br> 

사용자가 관련 사이트 또는 파일을 볼 수 있는 Office 365 권한이 없는 경우도 있기 때문에 동일한 항목에 대해 사용자에게 표시될 수 있는 항목의 차이점이 있습니다.  Viva Topics는 항목의 항목에 대해 설정된 사용 권한을 사용하며 해당 항목에 대한 액세스를 변경할 수 없습니다. 이 예제에서는 사용자 1에 파일을 볼 수 있는 Office 365 권한이 있기 때문에 사용자 1은 Neptune의 항목 페이지에서 *DG-2000* 제품 개요 파일을 볼 수 없습니다.

사용자가 유용하게 사용할 수 있도록 항목에 충분한 정보를 볼 수 없는 경우 해당 항목을 사용할 수 없습니다. 이 경우 사용자에게 강조 표시된 항목은 표시되지 않습니다. 유용하게 사용할 수 있도록 항목의 추가 정보에 대한 사용 권한이 있는 다른 사용자가 해당 항목을 볼 수 있습니다.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>지식 관리자 및 주제 참가자에 대한 항목 사용 권한

항목을 관리할 수 있는 권한이 할당된 사용자(기술 관리자)는 항목 내에서 볼 수 있는 권한이 있는 정보만 볼 수 있습니다.

마찬가지로 항목 작성 및 편집 권한(항목 참가자)은 항목 내에서 볼 수 있는 권한이 있는 정보만 볼 수 있습니다. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI와 수동 큐레이터 항목 정보

항목에는 AI에서 생성된 정보와 주제 참가자 또는 지식 관리자가 추가하거나 편집한 정보가 포함될 수 있습니다.

 - AI에서 추가된 항목의 정보는 원본 콘텐츠에 액세스할 수 있는 사용자만 볼 수 있습니다.
 - 항목 작성자 또는 지식 관리자가 수동으로 추가하거나 편집한 정보는 해당 항목을 볼 수 있는 모든 사람이 볼 수 있습니다.

다음 표에서는 사용자(주제 뷰어, 참가자 및 지식 관리자)가 사용 권한에 따라 특정 항목에서 볼 수 있는 항목에 대해 설명합니다.

|항목 항목|사용자에게 표시될 수 있는 것|
|:---------|:------------------|
|항목 이름|사용자는 항목 센터에서 모든 항목의 항목 이름을 볼 수 있습니다. 사용자에게 관련성 수준이 낮은 경우 일부 항목은 표시되지 않을 수 있습니다.|
|항목 설명|AI 생성 설명은 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다. 수동으로 입력하거나 편집한 설명은 모든 사용자에게 표시됩니다.|
|사용자|고정된 사용자는 모든 사용자에게 표시됩니다. 제안된 사용자는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|
|파일|파일은 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|
|페이지|페이지는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|
|사이트|사이트는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|




## <a name="see-also"></a>참고 항목

