---
title: Microsoft 365 그룹과 SharePoint 간의 설정 상호 작용
ms.reviewer: mmclean
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
description: Microsoft 365 그룹 및 SharePoint 간의 설정 상호 작용에 대해 자세히 알아보기
ms.openlocfilehash: 0c9fdd69db82985039bae03768aa0c19f514c99f
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662764"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Microsoft 365 그룹과 SharePoint 간의 설정 상호 작용

Microsoft 365의 Microsoft 365 그룹 및 SharePoint에 대 한 일부 설정 (특히 공유 및 그룹 및 팀 사이트 작성과 관련)이 서로 겹칩니다. 이 문서에서는 이러한 상호 작용 및 이러한 설정을 사용 하는 방법에 대 한 모범 사례에 대해 설명 합니다.

![SharePoint, Yammer 및 groups 기능의 벤 다이어그램](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>SharePoint 설정이 Microsoft 365 그룹에 미치는 영향

|SharePoint 설정|설명|Microsoft 365 그룹에 대 한 영향|권장 사항|
|:-----------------|:----------|:-----------------------------|:-------------|
|조직 및 사이트에 대 한 외부 공유|사이트, 파일 및 폴더를 조직 외부의 사용자와 공유할 수 있는지 여부를 결정 합니다.|SharePoint 및 그룹 설정이 일치 하지 않는 경우 그룹의 게스트가 사이트 액세스를 차단 하거나, 외부 액세스를 사이트에서 사용할 수 있지만 그룹을 사용 하지 못할 수 있습니다.|공유 설정을 변경할 때는 그룹에 연결 된 팀 사이트의 그룹 설정과 SharePoint 사이트 설정을 모두 확인 합니다.<br><br>[사이트에서 게스트와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)을 참조 하세요.|
|도메인 허용/차단|지정 된 도메인과 콘텐츠를 공유 하도록 허용 하거나 금지 합니다.|그룹은 SharePoint 허용 또는 차단 목록을 인식 하지 않습니다. SharePoint에서 허용 되지 않는 도메인의 사용자는 그룹을 통해 SharePoint에 액세스할 수 있습니다.|Azure AD 및 SharePoint에 대해 도메인 허용/차단 목록을 함께 관리 합니다. 도메인 허용 및 차단에 대 한 조직 전체의 거 버 넌 스 프로세스를 만듭니다.<br><br>[SharePoint 도메인 설정](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) 및 [Azure AD 도메인 설정](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) 참조|
|특정 보안 그룹의 사용자만 외부에서 공유할 수 있도록 허용|외부에서 사이트, 폴더 및 파일을 공유할 수 있는 보안 그룹을 지정 합니다.|이 설정은 외부에서 그룹 소유자 공유 그룹에 영향을 주지 않습니다. 그룹 게스트가 연결 된 SharePoint 사이트에 액세스할 수 있습니다.||
|SharePoint 사이트 공유 설정|그룹 구성원 외부에서 직접 사이트를 공유할 수 있는 사용자를 결정 합니다. 그룹 또는 사이트 소유자가 구성 합니다.|이 설정은 그룹에 직접 영향을 주지 않지만 사용자를 사이트에 추가 하 고 다른 그룹 리소스에 액세스 하지 못하도록 할 수 있습니다.|이 설정을 사용 하 여 사이트 공유를 직접 제한 하 고 그룹을 통해 사이트 액세스를 관리할 수 있습니다.|
|사용자가 SharePoint 시작 페이지 및 OneDrive에서 사이트를 만들 수 있도록 허용|사용자가 새 SharePoint 사이트를 만들 수 있는지 여부를 지정 합니다.|이 설정이 해제 된 경우에도 사용자는 그룹을 만들어 그룹에 연결 된 팀 사이트를 만들 수 있습니다.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>SharePoint의 Microsoft 365 groups 설정 효과

|Microsoft 365 groups 설정|설명|SharePoint에 대 한 영향|권장 사항|
|:---------------------------|:----------|:-------------------|:-------------|
|이름 지정 정책|그룹 만들기에 대 한 그룹 이름 접두사 및 접미사 및 차단 된 단어를 지정 합니다.|그룹 연결 팀 사이트를 만드는 사용자에 게 정책이 적용 되지만 다른 서식 파일을 사용 하는 사이트 또는 통신 사이트는 사용할 수 없습니다.|필요한 경우 통신 사이트에 대 한 별도의 명명 지침을 만듭니다.|
|그룹 게스트 액세스|조직 외부의 사용자를 그룹에 추가할 수 있는지 여부를 지정 합니다.|SharePoint 및 그룹 설정이 일치 하지 않는 경우 그룹의 게스트가 사이트 액세스를 차단 하거나, 외부 액세스를 사이트에서 사용할 수 있지만 그룹을 사용 하지 못할 수 있습니다.|공유 설정을 변경할 때는 그룹에 연결 된 팀 사이트의 그룹 설정과 SharePoint 사이트 설정을 모두 확인 합니다.<br><br>[사이트에서 게스트와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site) 참조|
|보안 그룹별 그룹 만들기|그룹은 특정 보안 그룹의 구성원만 만들 수 있습니다.|보안 그룹의 구성원이 아닌 사용자는 그룹에 연결 된 팀 사이트를 만들 수 없습니다.|그룹 요청 프로세스에는 사이트 요청에 대 한 지침이 포함 되어 있어야 합니다.|
|그룹 만료 정책|현재 사용 하지 않는 그룹이 자동으로 삭제 되는 기간을 지정 합니다.|그룹을 삭제 하면 연결 된 SharePoint 사이트도 삭제 됩니다. 보존 정책에 의해 보호 되는 콘텐츠는 그대로 유지 됩니다.|만료 정책을 사용 하 여 사용 하지 않는 그룹 및 사이트의 sprawl을 방지 합니다.|

## <a name="related-topics"></a>관련 항목

[조직 외부의 사용자와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[SharePoint에서 사이트 만들기 관리](https://docs.microsoft.com/sharepoint/manage-site-creation)