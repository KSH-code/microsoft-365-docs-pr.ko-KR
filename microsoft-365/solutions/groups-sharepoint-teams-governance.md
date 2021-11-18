---
title: Microsoft 365 그룹, Teams 및 SharePoint 간의 설정 상호 작용
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: 그룹, 그룹 및 Microsoft 365 그룹 Teams 상호 작용에 대해 SharePoint
ms.openlocfilehash: 64f00fcb5ace9e2f2f4a6630def6beb0a51d40bf
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064346"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 그룹, Teams 및 SharePoint 간의 설정 상호 작용

Microsoft 365 그룹, Microsoft Teams 및 SharePoint, Microsoft 365 공유 및 그룹/팀 및 SharePoint 사이트 만들기와 관련된 일부 설정은 서로 겹칩니다. 이 문서에서는 이러한 상호 작용에 대한 설명과 이러한 설정을 사용하여 작업하는 방법에 대한 모범 사례를 제공합니다.

![SharePoint, Teams 및 그룹 기능의 Venn 다이어그램입니다.](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>그룹 및 SharePoint 설정의 영향

|SharePoint 설정|설명|그룹 및 Microsoft 365 그룹에 Teams|권장 사항|
|:-----------------|:----------|:---------------------------------------|:-------------|
|조직 및 사이트에 대한 외부 공유|사이트, 파일 및 폴더를 조직 외부의 사용자와 공유할 수 있는지 여부를 확인합니다.|SharePoint, 그룹 및 Teams 설정이 일치하지 않는 경우 팀의 게스트가 사이트에 액세스하지 못하게 차단되거나 예기치 않은 외부 액세스가 발생할 수 있습니다.|공유 설정을 변경할 때 그룹 설정을 확인하고, Teams 설정을 확인하고, SharePoint 팀 사이트에 대한 사이트 설정을 변경합니다.<br><br> 팀에서 [게스트와 공동 작업하기 참조](./collaborate-as-team.md)|
|도메인 허용/차단|콘텐츠가 지정된 도메인과 공유되는 것을 허용하거나 차단합니다.|그룹 및 Teams 허용 목록 또는 차단 SharePoint 인식할 수 없습니다. 사용자 계정에서 허용되지 SharePoint 팀을 통해 SharePoint 콘텐츠에 액세스할 수 있습니다.|Azure AD 및 도메인에 대한 도메인 허용 목록 또는 차단 SharePoint 관리합니다. 도메인을 허용하고 차단하기 위한 관리 프로세스를 구성합니다.<br><br>도메인 [SharePoint](/sharepoint/restricted-domains-sharing) Azure AD [도메인 설정 참조](/azure/active-directory/b2b/allow-deny-list)|
|특정 보안 그룹의 사용자만 외부로 공유할 수 있도록 허용|외부에서 사이트, 폴더 SharePoint 공유할 수 있는 보안 그룹을 지정합니다.|이 설정은 팀 소유자가 외부에서 팀을 공유하는 것을 차단하지 않습니다. 팀 게스트는 연결된 사이트와 연결된 SharePoint 있습니다.||
|SharePoint 공유 설정|팀 구성원 자격 외부에서 직접 사이트를 공유할 수 있는 사용자 결정 팀 또는 사이트 소유자가 구성합니다.|이 설정은 팀에 직접 영향을 주지 않지만 사용자가 사이트에 추가될 수 있도록 허용하고 팀 자체 또는 기타 리소스에 액세스할 Teams 있습니다.|이 설정을 사용하여 사이트 공유를 직접 제한하고 팀을 통해 사이트 액세스를 관리하는 것이 좋습니다.|
|사용자가 시작 페이지 및 SharePoint 사이트에서 사이트를 만들 수 있도록 OneDrive|사용자가 사이트를 새로 만들 수 SharePoint 지정합니다.|이 설정을 해제한 경우 사용자는 여전히 팀을 만들어 그룹에 연결된 팀 사이트를 만들 수 있습니다.||

## <a name="the-effects-of-groups-settings-on-teams"></a>그룹 설정이 팀에 대한 효과

|Microsoft 365 그룹 설정|설명|이 열에 Teams|권장 사항|
|:---------------------------|:----------|:--------------|:-------------|
|이름 지정 정책|그룹 만들기를 위해 그룹 이름 접두사 및 접미사 및 차단된 단어를 지정합니다.|팀을 만드는 사용자에게 정책이 적용됩니다.||
|그룹 게스트 액세스|조직 외부의 사용자가 그룹에 추가할 수 있는지 지정합니다.|그룹 또는 Teams 공유 설정이 해제된 경우 팀을 게스트와 공유할 수 없습니다.|게스트 공유 설정을 변경할 때 팀과 연결된 Teams, 그룹 및 SharePoint 설정을 확인합니다.<br><br> 팀에서 [게스트와 공동 작업하기 참조](./collaborate-as-team.md)|
|보안 그룹으로 그룹 만들기|그룹은 특정 보안 그룹의 구성원만 만들 수 있습니다.|보안 그룹의 구성원이 아닌 사용자는 팀을 만들 수 없습니다.|그룹 요청 프로세스에 팀 또는 팀 사이트 요청 지침이 포함되어 SharePoint 합니다.|
|그룹 만료 정책|활성으로 사용되지 않는 그룹이 자동으로 삭제되는 기간을 지정합니다.|그룹이 삭제되면 팀 및 연결된 SharePoint 사이트도 삭제됩니다. 보존 정책에 의해 보호되는 콘텐츠는 보존됩니다.|만료 정책을 사용하여 사용되지 않는 팀, 그룹 및 사이트가 출되지 않도록 합니다.|

## <a name="related-topics"></a>관련 주제

[공동 작업 거버넌스 계획 권장 사항](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[공동 작업 거버넌스 계획 만들기](collaboration-governance-first.md)

[조직 외부 사용자와 공동 작업](./collaborate-with-people-outside-your-organization.md)

[SharePoint에서 사이트 만들기 관리](/sharepoint/manage-site-creation)