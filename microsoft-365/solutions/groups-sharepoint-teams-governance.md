---
title: Microsoft 365 그룹, 팀 및 SharePoint 간의 설정 상호 작용
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 그룹, 팀 및 SharePoint 간의 설정 상호 작용에 대해 자세히 알아보기
ms.openlocfilehash: 3ad5011c2d7b4579e054b014237d5771049b3c91
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662763"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 그룹, 팀 및 SharePoint 간의 설정 상호 작용

Microsoft 365의 microsoft 365 그룹, Microsoft 팀 및 SharePoint에 대 한 일부 설정 (특히 공유 및 그룹/팀 및 SharePoint 사이트 작성과 관련)이 서로 겹칩니다. 이 문서에서는 이러한 상호 작용 및 이러한 설정을 사용 하는 방법에 대 한 모범 사례에 대해 설명 합니다.

![SharePoint, 팀 및 그룹 기능의 벤 다이어그램](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>그룹 및 팀에 대 한 SharePoint 설정의 영향

|SharePoint 설정|설명|Microsoft 365 그룹 및 팀에 대 한 영향|권장 사항|
|:-----------------|:----------|:---------------------------------------|:-------------|
|조직 및 사이트에 대 한 외부 공유|사이트, 파일 및 폴더를 조직 외부의 사용자와 공유할 수 있는지 여부를 결정 합니다.|SharePoint, 그룹 및 팀 설정이 일치 하지 않는 경우 팀의 게스트가 사이트 액세스를 차단 하거나 예기치 않은 외부 액세스가 발생할 수 있습니다.|공유 설정을 변경 하는 경우 그룹에 연결 된 팀 사이트의 그룹 설정, 팀 설정 및 SharePoint 사이트 설정을 확인 합니다.<br><br> [팀에서 게스트와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) 을 참조 하세요.|
|도메인 허용/차단|지정 된 도메인과 콘텐츠를 공유 하도록 허용 하거나 금지 합니다.|그룹 및 팀은 SharePoint 허용 또는 차단 목록을 인식 하지 않습니다. SharePoint에서 허용 되지 않는 도메인의 사용자는 SharePoint 사이트 또는 팀을 통해 콘텐츠에 액세스 하는 데 사용할 수 있습니다.|Azure AD 및 SharePoint에 대해 도메인 허용/차단 목록을 함께 관리 합니다. 도메인 허용 및 차단에 대 한 조직 전체의 거 버 넌 스 프로세스를 만듭니다.<br><br>[SharePoint 도메인 설정](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) 및 [Azure AD 도메인 설정](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) 참조|
|특정 보안 그룹의 사용자만 외부에서 공유할 수 있도록 허용|외부에서 SharePoint 사이트, 폴더 및 파일을 공유할 수 있는 보안 그룹을 지정 합니다.|이 설정은 팀 소유자가 외부에서 팀을 공유 하는 것을 막지는 못합니다. 팀 게스트에는 연결 된 SharePoint 사이트에 대 한 액세스 권한이 있습니다.||
|SharePoint 사이트 공유 설정|팀 구성원 외부에서 직접 사이트를 공유할 수 있는 사용자를 결정 합니다. 이는 팀 또는 사이트 소유자가 구성 합니다.|이 설정은 팀에 직접 영향을 주지 않지만 사용자를 사이트에 추가 하 고 팀 자체 또는 기타 팀 리소스에 대 한 액세스 권한이 없는 경우에도 가능 합니다.|이 설정을 사용 하 여 사이트 공유를 직접 제한 하 고 팀을 통해 사이트 액세스를 관리할 수 있습니다.|
|사용자가 SharePoint 시작 페이지 및 OneDrive에서 사이트를 만들 수 있도록 허용|사용자가 새 SharePoint 사이트를 만들 수 있는지 여부를 지정 합니다.|이 설정이 해제 된 경우에도 사용자는 팀을 만들어 그룹 연결 팀 사이트를 만들 수 있습니다.||

## <a name="the-effects-of-groups-settings-on-teams"></a>팀에 대 한 그룹 설정의 영향

|Microsoft 365 groups 설정|설명|팀에 대 한 영향|권장 사항|
|:---------------------------|:----------|:--------------|:-------------|
|이름 지정 정책|그룹 만들기에 대 한 그룹 이름 접두사 및 접미사 및 차단 된 단어를 지정 합니다.|팀을 만드는 사용자에 게 정책이 적용 됩니다.||
|그룹 게스트 액세스|조직 외부의 사용자를 그룹에 추가할 수 있는지 여부를 지정 합니다.|그룹 또는 팀 게스트 공유 설정이 해제 된 경우 팀을 guests와 공유할 수 없습니다.|게스트 공유 설정을 변경할 때는 팀과 연결 된 팀, 그룹 및 SharePoint 사이트에 대 한 설정을 확인 합니다.<br><br> [팀에서 게스트와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) 을 참조 하세요.|
|보안 그룹별 그룹 만들기|그룹은 특정 보안 그룹의 구성원만 만들 수 있습니다.|보안 그룹의 구성원이 아닌 사용자는 팀을 만들 수 없습니다.|그룹을 요청 하는 프로세스에 팀 또는 SharePoint 사이트 요청에 대 한 지침이 포함 되어 있는지 여부|
|그룹 만료 정책|현재 사용 하지 않는 그룹이 자동으로 삭제 되는 기간을 지정 합니다.|그룹을 삭제 하면 팀 및 연결 된 SharePoint 사이트도 삭제 됩니다. 보존 정책에 의해 보호 되는 콘텐츠는 그대로 유지 됩니다.|만료 정책을 사용 하 여 사용 되지 않는 팀, 그룹 및 사이트의 sprawl를 방지 합니다.|

## <a name="related-topics"></a>관련 항목

[조직 외부의 사용자와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[SharePoint에서 사이트 만들기 관리](https://docs.microsoft.com/sharepoint/manage-site-creation)
