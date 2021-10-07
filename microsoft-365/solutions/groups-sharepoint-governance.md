---
title: 설정 그룹과 Microsoft 365 상호 작용 SharePoint
ms.reviewer: mmclean
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
description: Microsoft 365 그룹과 그룹 간의 설정 상호 작용에 대해 SharePoint
ms.openlocfilehash: 2978e2f0a450c72d7b4abf71edb208a5d9f364c6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208892"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>설정 그룹과 Microsoft 365 상호 작용 SharePoint

Microsoft 365 그룹 및 SharePoint Microsoft 365, 특히 공유 및 그룹 및 팀 사이트 만들기와 관련된 일부 설정은 서로 겹칩니다. 이 문서에서는 이러한 상호 작용에 대한 설명과 이러한 설정을 사용하여 작업하는 방법에 대한 모범 사례를 제공합니다.

![SharePoint, Yammer 및 그룹 기능의 Venn 다이어그램입니다.](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>그룹에서 SharePoint 설정이 Microsoft 365 효과

|SharePoint 설정|설명|그룹 Microsoft 365 영향|권장 사항|
|:-----------------|:----------|:-----------------------------|:-------------|
|조직 및 사이트에 대한 외부 공유|사이트, 파일 및 폴더를 조직 외부의 사용자와 공유할 수 있는지 여부를 확인합니다.|그룹 SharePoint 설정이 일치하지 않는 경우 그룹의 게스트가 사이트에 액세스하지 못하게 차단되거나, 사이트에서 외부 액세스를 사용할 수 있지만 그룹은 사용할 수 없습니다.|공유 설정을 변경할 때 그룹 설정과 그룹 연결 SharePoint 사이트 설정을 모두 확인합니다.<br><br>사이트에서 [게스트와 공동 작업을 참조하세요.](./collaborate-in-site.md)|
|도메인 허용/차단|콘텐츠가 지정된 도메인과 공유되는 것을 허용하거나 차단합니다.|그룹이 허용 또는 차단 SharePoint 인식하지 못합니다. 사용자 계정에서 허용되지 SharePoint 그룹을 통해 SharePoint 액세스할 수 있습니다.|Azure AD에 대한 도메인 허용/차단 목록을 관리하고 함께 SharePoint 관리합니다. 도메인을 허용하고 차단하기 위한 관리 프로세스를 구성합니다.<br><br>도메인 [SharePoint](/sharepoint/restricted-domains-sharing) Azure AD [도메인 설정 참조](/azure/active-directory/b2b/allow-deny-list)|
|Allow only users in specific security groups to share externally(특정 보안 그룹의 사용자만 외부로 공유할 수 있도록 허용)|외부에서 사이트, 폴더 및 파일을 공유할 수 있는 보안 그룹을 지정합니다.|이 설정은 그룹 소유자 공유 그룹에 외부적으로 영향을 주지 않습니다. 그룹 게스트는 연결된 사이트와 연결된 SharePoint 있습니다.||
|SharePoint 공유 설정|그룹 구성원 자격 외부에서 직접 사이트를 공유할 수 있는 사용자 결정 그룹 또는 사이트 소유자가 구성합니다.|이 설정은 그룹에 직접 영향을 주지 않지만 사용자가 사이트에 추가될 수 있도록 허용하고 다른 그룹 리소스에 액세스할 수 없습니다.|이 설정을 사용하여 사이트 공유를 직접 제한하고 그룹을 통해 사이트 액세스를 관리하는 것이 좋습니다.|
|사용자가 시작 페이지 및 SharePoint 사이트에서 사이트를 만들 수 있도록 OneDrive|사용자가 사이트를 새로 만들 수 SharePoint 지정합니다.|이 설정을 해제한 경우 사용자는 그룹을 만들어 그룹 연결 팀 사이트를 만들 수 있습니다.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>그룹 설정이 Microsoft 365 그룹 설정이 SharePoint

|Microsoft 365 그룹 설정|설명|이 열에 SharePoint|권장 사항|
|:---------------------------|:----------|:-------------------|:-------------|
|이름 지정 정책|그룹 만들기를 위해 그룹 이름 접두사 및 접미사 및 차단된 단어를 지정합니다.|그룹 연결 팀 사이트를 만드는 사용자에게는 정책이 적용되지만 다른 서식 파일과의 통신 사이트나 사이트는 만들지 않습니다.|필요한 경우 통신 사이트에 대한 별도의 이름 지침을 만들 수 있습니다.|
|그룹 게스트 액세스|조직 외부의 사용자가 그룹에 추가할 수 있는지 지정합니다.|그룹 SharePoint 설정이 일치하지 않는 경우 그룹의 게스트가 사이트에 액세스하지 못하게 차단되거나, 사이트에서 외부 액세스를 사용할 수 있지만 그룹은 사용할 수 없습니다.|공유 설정을 변경할 때 그룹 설정과 그룹 연결 SharePoint 사이트 설정을 모두 확인합니다.<br><br>사이트에서 게스트와 공동 [작업을 참조하세요.](./collaborate-in-site.md)|
|보안 그룹으로 그룹 만들기|그룹은 특정 보안 그룹의 구성원만 만들 수 있습니다.|보안 그룹의 구성원이 아닌 사용자는 그룹에 연결된 팀 사이트를 만들 수 없습니다.|그룹을 요청하는 프로세스에 사이트 요청 지침이 포함되어야 합니다.|
|그룹 만료 정책|활성으로 사용되지 않는 그룹이 자동으로 삭제되는 기간을 지정합니다.|그룹이 삭제되면 연결된 SharePoint 사이트도 삭제됩니다. 보존 정책에 의해 보호되는 콘텐츠는 보존됩니다.|만료 정책을 사용하여 사용되지 않는 그룹 및 사이트가 출되지 않도록 합니다.|

## <a name="related-topics"></a>관련 항목

[공동 작업 거버넌스 계획 단계별](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[공동 작업 거버넌스 계획 만들기](collaboration-governance-first.md)

[조직 외부 사용자와 공동 작업](./collaborate-with-people-outside-your-organization.md)

[SharePoint에서 사이트 만들기 관리](/sharepoint/manage-site-creation)