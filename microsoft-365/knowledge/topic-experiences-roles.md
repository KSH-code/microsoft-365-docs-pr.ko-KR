---
title: Microsoft Viva 주제 역할
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Viva 항목의 사용자 역할에 대해 자세히 알아보습니다.
ms.openlocfilehash: 6d93046a96b60779c3cd3bd6c6aa600cb443118f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917359"
---
# <a name="microsoft-viva-topics-roles"></a>Microsoft Viva 주제 역할 

Microsoft 365 환경에서 Viva 항목을 사용하는 경우 사용자는 다음과 같은 역할을 할 수 있습니다.
-   항목 뷰어
-   항목 참가자
-   지식 관리자
-   지식 관리자

## <a name="topic-viewer"></a>항목 뷰어

주제 뷰어는 조직의 사용자로, SharePoint 최신 사이트, SharePoint를 통한 Microsoft Search 및 Office.com 센터에서 강조 표시된 항목을 볼 수 있습니다. 항목 페이지에서 항목에 대한 자세한 내용을 볼 수 있습니다. 

항목 강조 및 해당 항목 페이지를 항목 뷰어에 표시하려면 사용자가 다음을 해야 합니다.
-   Microsoft 365 관리자가 [Viva Topics](./set-up-topic-experiences.md#assign-licenses) 라이선스를 할당합니다.
-   항목에 대한 가시성을 확보할 수 있습니다. 이 작업은 Microsoft 365 관리 센터의 Viva 항목 설정 페이지에서 기술 관리자가 수행합니다.


## <a name="topic-contributors"></a>주제 참가자

항목 참가자는 조직의 사용자로, 항목 보기 권한뿐만 아니라 기존 항목을 편집하거나 새 항목을 만들 수도 있는 사용자입니다. 항목 페이지의 정보(AI 또는 수동으로 제공된 정보 모두)의 정보를 수동으로 "큐레이터"하여 품질을 보장하는 데 중요한 역할을 합니다.

항목 참가자 권한이 있는 사용자는 항목  페이지에 편집 단추가 표시되어 항목을 업데이트하고 게시할 수 있습니다.

또한 주제 참가자가 항목 센터를 통해 새 항목을 만들고 게시할 수 있습니다.

항목을 만들고 편집하려면 사용자가 다음을 해야 합니다.

-   Microsoft 365 관리자가 [Viva Topics](./set-up-topic-experiences.md#assign-licenses) 라이선스를 할당합니다.
-   항목을 만들고 편집할 수 있는 사용 [권한을 할당합니다.](./topic-experiences-user-permissions.md#change-who-has-permissions-to-do-tasks-on-the-topic-center) 이 작업은 Microsoft 365 관리 센터의 Viva 항목 설정 페이지에서 기술 관리자가 수행합니다.

## <a name="knowledge-managers"></a>지식 관리자

지식 관리자는 조직에서 항목을 관리하는 사용자입니다.  항목 관리는 항목 센터의 항목 관리 페이지를 통해 수행하며 지식 관리자에게만 표시됩니다.

항목 관리 페이지에서 기술 관리자는 다음 작업을 수행할 수 있습니다.
-   AI 추천 항목을 시청하세요.
-   항목을 검토하여 해당 항목의 유효성을 검사합니다.
-   사용자에게 표시되지 않을 항목을 제거합니다.

또한 기술 관리자는 기존 항목을 편집하거나 새 항목을 만들 수 있습니다.

항목을 관리하려면 사용자가 다음을 해야 합니다.
-   Microsoft 365 관리자가 [Viva Topics](./set-up-topic-experiences.md#assign-licenses) 라이선스를 할당합니다.
-   항목을 관리할 수 [있는 사용 권한을 할당합니다.](./topic-experiences-user-permissions.md#change-who-has-permissions-to-do-tasks-on-the-topic-center) 이 작업은 Microsoft 365 관리 센터의 Viva 항목 설정 페이지에서 기술 관리자가 수행합니다.

비즈니스에 대한 전반적 지식이 있는 사용자는 지식 관리자 역할에 대한 좋은 후보가 될 수 있습니다. 이러한 사용자들은 주제가 유효한지 알 수 있을 뿐만 아니라 해당 항목과 관련된 회사 내의 사용자도 알고 있을 수 있습니다.


## <a name="knowledge-admins"></a>지식 관리자

지식 관리자는 Microsoft 365 환경에서 Viva 항목을 설정하고 구성하는 관리자입니다. 또한 설정이 완료된 후 Viva 항목 설정을 관리합니다. Microsoft 365 관리 센터에서 설정 및 관리를 수행하기 때문에 지식 관리자 역할은 Microsoft 365 전역 또는 SharePoint 관리자로 설정해야 합니다.
설치 중에 지식 관리자는 다음을 위해 Viva 항목을 구성할 수 있습니다.

-   항목에 대해 크롤링할 SharePoint 사이트를 선택합니다.
-   항목을 볼 수 있는 사용이 허가된 사용자를 선택합니다(항목 뷰어).
-   식별에서 제외할 항목을 선택합니다.
-   항목을 만들고 편집할 수 있는 사용이 허가된 사용자를 선택합니다(항목 참가자).
-   항목을 관리할 수 있는 사용이 허가된 사용자(기술 관리자)를 선택합니다.
-   항목 센터의 이름을 지정합니다.

지식 관리자는 조직의 모든 Viva 주제 관련자와 협의하여 구성 방법을 알 수 있도록 해야 합니다. 예를 들어 새 프로젝트에 중요한 정보가 있는 경우, SharePoint 사이트가 항목에 대해 크롤링되지 않는지 또는 특정 항목 이름을 제외해야 하는지 알릴 수 있도록 기술 관리자에게 정보를 제공해야 합니다.


## <a name="see-also"></a>참고 항목