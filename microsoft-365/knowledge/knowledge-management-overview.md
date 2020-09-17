---
title: 지식 관리 개요 (미리 보기)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex의 지식 관리에 대 한 개요입니다.
ms.openlocfilehash: 80750ee94248b21b8ac7bd3869830a7986de34b9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949375"
---
# <a name="knowledge-management-0verview-preview"></a>지식 관리 0verview (Preview)

> [!Note] 
> 이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다. [Project Cortex에 대해 자세히 알아보기](https://aka.ms/projectcortex) 

지식 관리는 microsoft의 인공 지능 기술, Microsoft 365, Delve, 검색 및 기타 구성 요소 및 서비스를 사용 하 여 Microsoft 365 환경에서 지식 네트워크를 구축 합니다. 

   ![지식 관리 흐름](../media/content-understanding/knowledge-management-flowchart.png) </br> 

Outlook, 팀 및 SharePoint와 같이 매일 사용 하는 앱에서 사용자에 게 정보를 전달 하는 것이 목표입니다.

예를 들어 사용자는 전자 메일, SharePoint 사이트 또는 팀 대화에 익숙하지 않은 용어를 볼 수 있습니다. 지식 관리는 AI를 사용 하 여 이러한 **항목**을 자동으로 검색 하 고 식별 하며, 해당 항목에 대 한 간단한 설명, 주제 전문가, 해당 항목과 관련 된 사이트, 파일 및 페이지에 대 한 정보를 컴파일합니다. 필요에 따라 항목 정보를 업데이트 하도록 선택할 수 있습니다. 그런 다음 사용자가 항목을 사용할 수 있으므로 Outlook, 팀, SharePoint 등의 앱에 나타나는 모든 항목에 대해 텍스트가 강조 표시 됩니다. 사용자는 세부 정보를 통해이 항목을 선택 하 여 자세히 알아볼 수 있습니다.


## <a name="topic-discovery"></a>항목 검색

지식 관리는 Microsoft 인공 지능 기술을 사용 하 여 Office 365 환경에서 **항목** 을 검색 합니다.

항목은 조직 차원 중요 또는 중요성을 나타내는 구 또는 용어입니다. 조직에 대 한 특별 한 의미를 가지 며, 사용자가이를 이해 하 고이에 대 한 자세한 정보를 확인할 수 있는 리소스를 포함 합니다.

항목이 검색 되 면 다음과 같은 항목 검색을 통해 수집 된 정보를 포함 하는 **항목 페이지** 를 만듭니다.

- 항목에 대 한 간단한 설명입니다.
- 주제에 대 한 전문 지식을 가진 사용자입니다.
- 항목과 관련 된 파일, 페이지 및 사이트


## <a name="topic-management"></a>항목 관리

항목 관리는 조직의 **항목 센터**에서 수행 됩니다. 항목 센터 사이트는 설치 중에 만들어지며, 조직에 대 한 지식 중심으로 작용 합니다. 여기에는 해당 항목에 대해 만들어진 모든 항목 페이지 뿐 아니라 환경에서 검색 된 모든 항목의 목록이 포함 됩니다. 

올바른 사용 권한을 제공 하는 사용자는 센터 항목에서 다음을 수행할 수 있습니다.

- 테 넌 트에서 검색 된 항목을 확인 하거나 거부 합니다.
- 필요에 따라 수동으로 새 항목 만들기 (예: AI를 통해 검색할 수 있는 정보가 충분 하지 않은 경우)
- 기존 항목 페이지를 편집 합니다.</br>

자세한 내용은 [센터 항목의 작업 항목](work-with-topics.md) 을 참조 하십시오.  


## <a name="admin-controls"></a>관리 컨트롤

Microsoft 365 관리 센터의 관리 컨트롤을 사용 하 여 지식 네트워크를 관리할 수 있습니다. Microsoft 365 글로벌 또는 SharePoint 관리자가 다음을 수행할 수 있도록 허용 합니다.

- 조직에서 클라이언트 앱 또는 SharePoint 검색 결과의 항목을 볼 수 있는 사용자를 제어 합니다.
- 항목을 검색 하기 위해 크롤링할 SharePoint 사이트를 제어 합니다.
- 토픽 검색을 구성 하 여 항목으로 원하지 않는 특정 용어를 제외 합니다.
- 항목 센터의 항목을 확인 하거나 거부할 수 있는 사용자를 제어 합니다.
- 항목 센터에서 항목을 만들고 편집할 수 있는 사용자를 제어 합니다.

자세한 내용은 [지식 네트워크 관리](manage-knowledge-network.md) 를 참조 하세요. 

## <a name="topic-curation"></a>항목 curation

사용자 환경에서 변경 내용이 적용 됨에 따라 사용자가 항목을 개선할 수 있도록 추천을 제공 하기 위해 AI가 지속적으로 작동 합니다.

액세스를 허용 하는 사용자는 일상 작업의 항목을 볼 수 있습니다. 예를 들어 사용자가 항목 페이지를 보고, 잘못 되었거나 추가 해야 하는 정보를 볼 수 있는 경우 항목 페이지의 링크를 통해 정보를 업데이트 하기 위한 요청을 제출 하면 됩니다.

또한 적절 한 사용 권한이 있는 사용자는 해당 항목과 관련 된 팀 대화와 같은 항목에 태그를 지정 하 여 특정 항목에 추가할 수 있습니다.




## <a name="see-also"></a>참고 항목
[지식 관리 설정](set-up-knowledge-network.md)</br>
[항목 센터 개요](topic-center-overview.md)
