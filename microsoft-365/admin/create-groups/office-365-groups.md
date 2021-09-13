---
title: 관리자를 위한 Microsoft 365 그룹 개요
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: 그룹 Microsoft 365 사용하면 사용자 그룹에 공유 리소스 모음에 대한 액세스 권한을 Microsoft 365 팀워크를 주도할 수 있습니다.
ms.openlocfilehash: 08e90d5197e59f6c1cf6dc89343b263194925bf4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184932"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>관리자를 위한 Microsoft 365 그룹 개요

Microsoft 365 그룹은 모든 팀워크를 모든 팀워크로 구동하는 기본 멤버십 Microsoft 365. 그룹 Microsoft 365 공유 리소스 모음에 대한 액세스 권한을 사용자 그룹에 부여할 수 있습니다. 이러한 리소스는 다음과 같습니다.

- 공유 Outlook 받은 편지함
- 공유 일정
- 문서 SharePoint 라이브러리
- A Planner
- OneNote 전자 필기장
- Power BI
- Yammer(그룹이 Yammer)
- 팀(그룹이 팀에서 만들어진 Teams)
- 로드맵(웹용 Project 있는 경우)
- Stream

그룹 Microsoft 365 이러한 각 리소스에 대한 사용 권한을 수동으로 할당할 필요는 없습니다. 그룹에 사용자 추가는 자동으로 필요한 사용 권한을 부여합니다.

특정 사용자 집합으로 그룹 만들기를 제한하지 않는 한 모든 사용자는 그룹을 [만들 수 있습니다.](../../solutions/manage-creation-of-groups.md) 그룹 만들기를 제한하면 그룹을 만들 수 없는 사용자는 SharePoint 사이트, 플래너, 팀, Outlook 그룹 일정, 스트림 그룹, Yammer 그룹, OneDrive의 공유 라이브러리 또는 공유 Power BI 작업 영역으로 만들 수 없습니다. 이러한 서비스를 사용하려면 그룹을 만드는 사람이 그룹을 만들 수 있게 됩니다. 사용자는 Planner에서 작업을 만들거나 그룹 구성원인 경우 Teams 채팅을 사용하는 등의 그룹 활동에 계속 참여할 수 있습니다.

그룹에는 다음과 같은 역할이 있습니다.

- **소유자** - 그룹 소유자는 구성원을 추가 또는 제거하고 공유 받은 편지함에서 대화를 삭제하거나 그룹에 대한 다른 설정을 변경하는 기능과 같은 고유한 사용 권한을 가지게 됩니다. 그룹 소유자는 그룹 이름을 변경하고 설명이나 그림을 업데이트할 수 있습니다.
- **구성원** - 구성원은 그룹의 모든 정보에 액세스할 수 있지만 그룹 설정을 변경할 수 없습니다. 기본적으로 그룹 구성원은 게스트를 그룹에 가입하게 초대할 수 있습니다. 그러나 이 설정을 [제어할 수 있습니다.](manage-guest-access-in-groups.md)
- **게스트** - 그룹 게스트는 조직 외부의 구성원입니다.

전역 관리자, 사용자 관리자 및 그룹 관리자만 에서 그룹을 만들고 관리할 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">수 Microsoft 365 관리 센터.</a> 위임된 관리자는 그룹을 만들 수 없습니다(예: 관리자를 대신하여 활동하는 컨설턴트).

관리자는 다음을 할 수 있습니다.

- [그룹을 만들 수 있는 사용자 지정](../../solutions/manage-creation-of-groups.md)
- [조직의 그룹에 대한 이름 정책 만들기](../../solutions/groups-naming-policy.md)
- [그룹을 만들 때 사용할 도메인 선택](../../solutions/choose-domain-to-create-groups.md)
- [그룹에 대한 게스트 액세스 관리](manage-guest-access-in-groups.md)
- [삭제된 그룹 복구(삭제](restore-deleted-group.md) 후 30일 이내에)

Microsoft 365 그룹의 수명 주기를 보다 자동화된 방식으로 관리하기를 원하는 경우 만료 정책을 사용하여 특정 시간 간격으로 그룹을 만료할 수 있습니다. 그룹의 소유자는 그룹 만료 30일, 15일 및 1일 전에 전자 메일을 수신하게 되기 때문에 필요한 경우 그룹을 갱신할 수 있습니다. 자세한 내용은 [Microsoft 365 만료 정책 을 참조합니다.](../../solutions/microsoft-365-groups-expiration-policy.md)

또는 [PowerShell을](../../enterprise/manage-microsoft-365-groups-with-powershell.md)사용하여 Microsoft 365 관리 센터 관리할 수 있습니다.

대기업이나 대기업 등의 사용자가 많은 경우 다양한 용도로 그룹을 만드는 사용자가 많이 있을 수 있습니다. 모범 사례를 위해 Microsoft 365 거버넌스 [계획을](../../solutions/collaboration-governance-overview.md) 검토하는 것이 좋습니다.

## <a name="group-limits"></a>그룹 제한

다음 제한은 Microsoft 365 적용됩니다.

|최대값...|값|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|관리자가 만들 수 있는 그룹|최대 기본 테넌트 제한 500 K|
|구성원 수|1,000개가 넘는 경우 1,000개만 그룹 대화에 동시 액세스할 수 있습니다. <br>사용자는 일정에 액세스할 때 지연을 알 수 있으며 대규모 그룹의 대화에 액세스할 때 Outlook.|
|사용자가 구성원이 될 수 있는 그룹 수|7,000|
|파일 저장소|구독한 사용자당 1 테라바이트 + 10GB + 구입한 다른 저장소 무제한의 추가 저장소를 구입할 수 있습니다.|
|그룹 사서함 크기|50 GB|

조직에서 사용할 수 있는 Microsoft 365 그룹의 기본 최대 수는 500,000개입니다. 기본 제한을 초과하려면 Microsoft 지원에 문의해야 합니다. 그룹 제한에 Microsoft 365 대한 자세한 내용은 Microsoft 365 [그룹 - 관리자 도움말을 참조하세요.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

그룹 사용 Microsoft 365 실행 가능한 정보가 있는 경우 그룹 관리가 더 효과적입니다. 이 Microsoft 365 관리 센터 저장소 사용, 활성 그룹 수 및 사용자가 그룹을 사용하는 방법을 볼 수 있는 보고 도구가 있습니다. 자세한 [Microsoft 365 센터의](../activity-reports/office-365-groups.md) 보고서 보기를 참조하세요.

## <a name="sensitivity-labels"></a>민감도 레이블

조직의 사용자가 그룹 그룹을 만들 때 설정할 수 있는 민감도 레이블을 Microsoft 365 있습니다. 민감도 레이블을 사용하여 다음을 구성할 수 있습니다. 

- 개인 정보(공개 또는 비공개)
- 외부 사용자 액세스
- 관리되지 않는 장치 액세스

예를 들어 기밀이라는 레이블을  만들고 이 레이블로 만든 모든 그룹이 비공개로 지정하고 외부 사용자를 허용하지 못하도록 지정할 수 있습니다. 조직의 사용자가 그룹을 만들 때 이 레이블을 선택하면 그룹이 비공개로 설정되어 있으며 그룹 구성원은 그룹에 외부 사용자를 추가할 수 없습니다.

> [!IMPORTANT]
> 현재 분류 레이블을 사용하는 경우 민감도 레이블을 사용하도록 설정하면 그룹을 만드는 사용자가 더 이상 해당 레이블을 사용할 수 없습니다. 

민감도 레이블 만들기, 관리 및 사용에 대한 자세한 내용은 민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint [사이트를 참조하세요.](../../compliance/sensitivity-labels-teams-groups-sites.md)

## <a name="which-microsoft-365-plans-include-groups"></a>그룹을 Microsoft 365 계획은 무엇입니까?

온라인 Microsoft 365 및 Exchange Online SharePoint 모든 구독이 그룹을 지원합니다. 여기에는 Business Essentials 및 Business Premium 계획과 E1, E3 Enterprise 요금제가 포함됩니다. 그룹은 그룹을 만든 사람의 라이선스를 관리합니다(그룹의 "이끌이"라고도 알려지기). 이끌이가 그룹에 필요한 기능에 대한 적절한 라이선스가 있는 한 해당 라이선스는 그룹에 전달됩니다.

> [!NOTE]
> 서비스 패밀리 및 계획에 Microsoft 365 대한 자세한 내용은 Microsoft 365 [옵션을 참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Exchange 전용 계획이 있는 경우 Outlook 그룹의 공유 받은 편지함 및 공유 일정 기능을 계속 사용할 수 있지만 문서 라이브러리, Planner 또는 기타 기능은 사용할 수 없습니다.

Microsoft 365 그룹은 사용자와 함께 Azure Active Directory. 사용할 수 있는 그룹 기능은 Azure Active Directory 구독 및 그룹의 이끌이에게 할당되는 라이선스에 따라 다를 수 있습니다.

> [!IMPORTANT]
> 모든 그룹 기능에 대해 Azure AD Premium 구독이 있는 경우 사용자에게 AAD P1 라이선스가 할당되어 있는지 여부에 따라 사용자가 그룹에 가입할 수 있습니다. 라이선스가 적용되지 않습니다.
> 라이선스가 누락된 사용자를 알려 주기적으로 사용 현황 보고서를 생성하고 라이선스 요구 사항을 준수하기 위해 할당된 사용자가 필요합니다. 예를 들어 사용자에게 라이선스가 없는 경우 이름 정책이 적용된 그룹에 추가된다고 합니다. 보고서에 라이선스가 필요하다는 플래그가 지정됩니다.

## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) 그룹(문서)에 대해 자세히 알아보시고
[메일 그룹을 Microsoft 365 그룹으로](../manage/upgrade-distribution-lists.md) 업그레이드(문서)\
[PowerShell을 Microsoft 365 그룹](../../enterprise/manage-microsoft-365-groups-with-powershell.md) 관리(문서)\
[SharePoint 온라인](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 제한(문서)\
[Microsoft Stream에서 그룹 및 채널](/stream/groups-channels-organization) 구성(문서)
