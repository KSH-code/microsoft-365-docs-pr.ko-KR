---
title: 보안 및 개인 정보 보호 Microsoft Viva 항목
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
ms.localizationpriority: medium
description: Microsoft Viva 항목에서 보안 및 개인 정보 보호를 계획하는 방법을 배워야 합니다.
ms.openlocfilehash: 4b0c94244badab9aa7e294b04b20b09149ead3b7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168437"
---
# <a name="security-and-privacy-in-microsoft-viva-topics"></a>보안 및 개인 정보 보호 Microsoft Viva 항목

항목에서는 관리 컨트롤과 함께 Microsoft 365 기존 콘텐츠 보안 기능을 사용하여 조직의 사용자에게 표시되는 AI 생성 콘텐츠를 제어합니다. 보안 설정(Microsoft 365, 파일 및 폴더에 대한 사용 권한)과 특정 사용자가 항목에 볼 수 있는 항목을 결정하는 항목 관리 설정의 조합입니다.

Topics를 설정하더라도 조직의 콘텐츠에 대한 기존 액세스 제어는 수정되지 않습니다. 사용자는 이미 액세스 권한을 가진 항목만 보게 됩니다.

이 문서에서는 보안 관점에서 항목의 작동 방식과 지식 관리자와 지식 관리자가 항목 표시를 제어해야 하는 옵션에 대해 설명하고 있습니다. 항목 계획의 일부로 이 문서를 [읽어 읽습니다.](plan-topic-experiences.md)

이 문서를 읽기 전에 항목, [](topic-center-overview.md)항목 센터 및 [](manage-topics.md) 항목 센터의 항목으로 작업하는 방법에 대해 잘 알고 있습니다. [](topic-experiences-overview.md)

## <a name="what-users-can-see-in-topics"></a>사용자가 항목에서 볼 수 있는 항목

항목을 표시하려면 사용자가 다음을 해야 합니다.

- Viva 항목 라이선스가 있는 경우
- 주제 [뷰어,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization)참가자 [또는 기술 관리자](topic-experiences-user-permissions.md)

이 두 가지를 통해 사용자는 항목 센터에 대한 액세스 권한을 부여하고 강조 표시 및 항목 카드를 볼 수 있습니다.

항목 작성자는 항목에 대한 [사용](topic-experiences-user-permissions.md) 권한을 추가로 만들고 편집할 수 있으며, 기술 관리자는 항목을 확인하거나 제거할 수 있습니다.

주제가 처음 발견될 때 지식 관리자는 항목 센터에서 항목을 볼 수 있습니다. 항목의 완성도와 관련성에 따라 항목 보기가 항목 카드에 제시된 항목을 보거나 볼 수 없습니다.

항목에는 AI에서 생성된 정보와 항목 참가자 또는 지식 관리자가 추가하거나 편집한 정보가 포함될 수 있습니다.

- AI에 의해 추가된 항목 정보는 원본 콘텐츠에 접근 권한이 있는 사용자에게만 표시됩니다.
- 항목 참가자 또는 기술 관리자가 수동으로 추가하거나 편집한 텍스트는 항목을 볼 수 있는 모든 사람이 볼 수 있습니다.

주제 뷰어 및 참가자는 항목 센터에서 확인 및 게시된 항목 목록을 볼 수 있지만 특정 사용자가 볼 수 있는 항목 세부 정보는 원본 자료에 대한 사용 권한 및 해당 항목을 수동으로 편집한지 여부에 따라 결정됩니다.

다음 표에서는 사용자의 사용 권한에 따라 특정 항목에서 볼 수 있는 사용자( 주제 뷰어, 참가자 및 기술 관리자)에 대해 설명합니다.

|토픽 항목|사용자가 볼 수 있는 내용|
|:---------|:------------------|
|토픽 이름|사용자는 항목 센터에서 항목 이름을 볼 수 있습니다. 사용자가 원본 콘텐츠에 대한 사용 권한이 없는 경우 또는 사용자에게 관련성이 낮은 경우 일부 항목은 표시되지 않을 수 있습니다.|
|토픽 설명|AI에서 생성된 설명은 소스 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다. 수동으로 입력하거나 편집한 설명은 모든 사용자에게 표시됩니다.|
|사용자|고정된 사용자는 모든 사용자에게 표시됩니다. 추천된 사용자는 소스 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|
|파일|파일은 소스 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|
|페이지|페이지는 소스 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|
|사이트|사이트는 소스 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.|

## <a name="users-personal-and-private-data"></a>사용자의 개인 및 개인 데이터

Viva 항목은 지정한 SharePoint 항목만 검색합니다. 개인 메일 또는 사용자와 같은 사용자의 개인 OneDrive 포함되지 않습니다.

## <a name="best-practices"></a>모범 사례

항목에서는 콘텐츠에 대한 기존 사용 권한에 따라 사용자에게 정보를 제공합니다. Microsoft 365 중요한 콘텐츠가 적절한 사용자로 제한되도록 하는 다양한 방법을 제공합니다. 표준 팀 또는 사이트 권한 이외에 민감도 레이블 [](../compliance/dlp-learn-about-dlp.md) 또는 데이터 손실 방지를 [](/azure/active-directory/governance/access-reviews-overview) 사용하여 콘텐츠 및 액세스 검토에 대한 액세스를 제한하여 중요한 정보에 대한 사용자 액세스를 주기적으로 검토할 수 있습니다. [](../compliance/sensitivity-labels.md)

이러한 도구를 사용하여 조직 내에서 콘텐츠 사용 권한을 적절하게 설정하는 것이 좋습니다. 그러면 사용자는 항목 환경에서 유용하고 적절한 정보를 얻을 수 있습니다.

항목 환경에서 완전히 제외하려는 주제가 있는 경우 다음을 할 수 있습니다.

- [항목 검색에서 SharePoint 제외합니다.](topic-experiences-discovery.md#select-sharepoint-topic-sources) 이러한 사이트의 콘텐츠는 항목 환경에 나타나지 않습니다.

- [이름으로 항목을 제외합니다.](topic-experiences-discovery.md#exclude-topics-by-name) 명시적으로 제외된 항목은 항목 환경에 나타나지 않습니다.

- 지식 관리자가 항목 센터에서 항목을 제거하게 합니다.

또한 다음 모범 사례를 권장합니다.

- 조직의 여러 영역에서 지식 관리자를 모집합니다. 다양한 전문 지식이 있는 지식 관리자와 AI에서 사용하는 기반 콘텐츠에 대한 액세스 권한을 부여하면 사용자에게 가장 유용한 지식을 큐에 추가하고 중요한 정보가 발견된 경우 이를 제거할 수 있습니다.

- 변경 내용을 요청하기 위한 워크플로를 설정합니다. 지식 관리자 또는 팀 또는 사이트 소유자는 조직 내에서 새 프로젝트가 시작되거나 부적절한 사용 권한 설정이 있는 콘텐츠를 찾을 때 항목 또는 사이트 제외를 요청할 수 있는 프로세스가 필요합니다.

- 항목 설명을 만들 때 대상 그룹 및 정보의 민감도에 주의하세요. 이러한 설명은 항목의 원본 콘텐츠에 대한 사용 권한이 없는 사용자에게 표시될 수 있습니다.

개별 항목 페이지에 대한 사용 권한을 변경하여 특정 사용자 그룹에 대한 액세스를 좁힐 수 있습니다. 그러나 많은 관리 노력이 필요하기 때문에 이 방법은 권장되지 않습니다.

## <a name="see-also"></a>참고 항목

[3 계층 보안으로 Teams 구성](../solutions/configure-teams-three-tiers-protection.md)

[계획 주제 경험](plan-topic-experiences.md)

[주제 경험 설정](set-up-topic-experiences.md)
