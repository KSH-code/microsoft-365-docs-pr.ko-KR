---
title: 관리자를 위한 Microsoft 365 그룹 개요
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 그룹에 대해 알아봅니다.
ms.openlocfilehash: 711ab7e7818b266d7cbdbe076e30355d29bc3eeb
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307268"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>관리자를 위한 Microsoft 365 그룹 개요

Microsoft 365 Groups는 모든 팀 작업를 Microsoft 365에서 구동 하는 기본 멤버 자격 서비스입니다. Microsoft 365 그룹을 사용 하는 경우 사용자 그룹에 게 해당 사용자가 공유할 공동 작업 자원 모음에 대 한 액세스 권한을 부여할 수 있습니다. 이러한 리소스는 다음과 같습니다.

- 공유 Outlook 받은 편지함
- 공유 일정
- SharePoint 문서 라이브러리
- Planner
- OneNote 전자 필기장
- Power BI
- Yammer (그룹이 Yammer에서 만들어진 경우)
- 팀 (그룹이 팀에서 만든 경우)
- 로드맵 (웹에 대 한 Project가 있는 경우)

Microsoft 365 그룹에서는 그룹에 사용자를 추가 하는 경우 그룹이 제공 하는 도구에 필요한 사용 권한을 자동으로 부여 하므로 이러한 각 리소스에 대 한 사용 권한을 수동으로 할당할 필요가 없습니다.

[그룹 만들기를 특정 사용자 집합으로 제한](manage-creation-of-groups.md)하지 않으면 모든 사용자가 그룹을 만들 수 있습니다. 그룹 만들기를 제한 하는 경우 그룹을 만들 수 없는 사용자는 SharePoint 사이트, 계획 또는 팀을 만들 수 없습니다. 이러한 서비스를 만드는 사용자가 그룹을 만들 수 있도록 요구 합니다. 사용자는 Planner에서 작업을 만들거나 팀 채팅을 사용 하는 경우 그룹의 구성원 인 경우에도 그룹 작업에 참가할 수 있습니다.

그룹에는 다음과 같은 역할이 있습니다.

- **소유자** -그룹 소유자는 구성원을 추가 또는 제거할 수 있으며 공유 받은 편지함에서 대화를 삭제 하거나 그룹에 대 한 서로 다른 설정을 변경 하는 기능과 같은 고유한 사용 권한이 있습니다. 그룹 소유자는 그룹 이름을 바꾸고 설명 또는 사진 등을 업데이트할 수 있습니다.
- **구성원** -구성원은 그룹의 모든 항목에 액세스할 수 있지만 그룹 설정은 변경 되지 않습니다. 기본적으로 그룹 구성원은 그룹에 참가 하도록 게스트를 초대할 수 있지만 [해당 설정을 제어할](manage-guest-access-in-groups.md)수 있습니다.
- **게스트** 그룹 게스트는 조직 외부의 구성원입니다.

전역 관리자, 사용자 관리자 및 그룹 관리자만 Microsoft 365 관리 센터에서 그룹을 만들고 관리할 수 있습니다. 위임된 관리자는 그룹을 만들 수 없습니다(예: 관리자를 대신하여 활동하는 컨설턴트).

관리자는 다음 작업을 수행할 수 있습니다.

- [그룹을 만들 수 있는 사용자 지정](manage-creation-of-groups.md)
- [조직의 그룹에 대 한 명명 정책 만들기](groups-naming-policy.md)
- [그룹을 만들 때 사용할 도메인 선택](choose-domain-to-create-groups.md)
- [그룹에 대한 게스트 액세스 관리](manage-guest-access-in-groups.md)
- [삭제 된 그룹 복구](restore-deleted-group.md) (삭제 후 30 일 이내)

Microsoft 365 그룹의 수명 주기를 보다 자동화 된 방식으로 관리 하려면 만료 정책을 사용 하 여 특정 시간 간격으로 그룹을 만료 시킬 수 있습니다. 그룹 소유자는 그룹 만료를 위해 30, 15, 1 일 전에 전자 메일을 받게 되며,이는 여전히 필요한 경우 그룹을 쉽게 갱신할 수 있도록 합니다. 참고: [Microsoft 365 그룹 만료 정책](office-365-groups-expiration-policy.md)

Microsoft 365 관리 센터에서 또는 [PowerShell을 사용](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel)하 여 그룹을 관리할 수 있습니다.

대기업 또는 기업 등의 사용자가 많은 경우 다양 한 용도로 그룹을 만드는 사용자가 여러 명 있을 수 있습니다. 모범 사례를 보려면 [Microsoft 365 그룹의 거 버 넌 스 계획](plan-for-groups-governance.md) 을 검토 하는 것이 좋습니다.

## <a name="group-limits"></a>그룹 제한

Microsoft 365 그룹에는 다음과 같은 제한이 적용 됩니다.

|최대 ...|값|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|관리자가 만들 수 있는 그룹|최대 기본 테 넌 트 제한인 500K|
|구성원 수|1000 이상이 며 1000만 그룹 대화에 동시에 액세스할 수 있습니다. <br>Outlook에서 매우 큰 그룹의 일정 및 대화에 액세스할 때 지연이 발생할 수 있습니다.|
|사용자가 구성원으로 속해 있을 수 있는 그룹 수|1,000|
|파일 저장소|1 테라바이트 + 10 g b 구독 된 사용자 당 및 구매한 추가 저장소를 사용 합니다. 무제한의 추가 저장소를 구입할 수 있습니다.|
|그룹 사서함 크기|50GB|

조직에서 사용할 수 있는 Microsoft 365 그룹의 기본 최대 개수는 50만입니다. 기본 제한 값 이상으로 이동 하려면 Microsoft 지원에 문의 해야 합니다. Microsoft 365 그룹 제한에 대 한 자세한 내용은 [microsoft 365 groups-Admin help](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)를 참조 하십시오.

그룹 사용에 대 한 정보를 사용할 수 있는 경우 Microsoft 365 그룹을 관리 하는 것이 보다 효율적입니다. Microsoft 365 관리 센터에는 저장소 사용, 보유 하 고 있는 활성 그룹 수 및 사용자가 그룹을 사용 하는 방법에 대 한 작업을 볼 수 있는 보고 도구가 있습니다. 자세한 내용은 [관리 센터의 Microsoft 365 보고서](../activity-reports/office-365-groups.md) 를 참조 하세요.

## <a name="sensitivity-labels"></a>민감도 레이블

조직의 사용자가 Microsoft 365 그룹을 만들 때 설정할 수 있는 민감도 레이블을 만들 수 있습니다. 민감도 레이블을 사용 하 여 다음을 구성할 수 있습니다. 

- 개인 정보 보호 (공용 또는 개인)
- 외부 사용자 액세스
- 관리 되지 않는 장치 액세스

예를 들어 *높은 기밀* 이라는 레이블을 만들고이 레이블로 만든 모든 그룹은 비공개로 지정 하 고 외부 사용자를 허용 하지 않도록 지정할 수 있습니다. 조직의 사용자가 그룹을 만드는 동안이 레이블을 선택 하는 경우 그룹이 개인 그룹으로 설정 되 고 그룹 구성원에 게 외부 사용자를 추가할 수 없게 됩니다.

> [!IMPORTANT]
> 현재 분류 레이블을 사용 하는 경우 민감도 레이블이 사용 되도록 설정 되 면 그룹을 만드는 사용자는 더 이상 사용할 수 없게 됩니다. 

민감도 레이블을 만들고 관리 하 고 사용 하는 방법에 대 한 자세한 내용은 [Microsoft 팀, microsoft 365 그룹 및 SharePoint 사이트의 콘텐츠를 보호 하려면 사용 민감도 레이블을](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)참조 하세요.

## <a name="which-microsoft-365-plans-include-groups"></a>어떤 Microsoft 365 계획에 그룹이 포함 됩니까?

Exchange Online 및 SharePoint Online이 포함 된 모든 Microsoft 365 구독에서는 그룹을 지원 합니다. 여기에는 Business Essentials 및 Business Premium 요금제와 Enterprise E1, E3 및 E5 요금제가 포함 됩니다. 그룹은 그룹을 만든 사용자 (그룹의 "이끌이" 라고도 함)를 사용 하 여 라이선스를 받습니다. 이끌이는 그룹에 포함 하려는 모든 기능에 적합 한 라이선스를가지고 있으면 해당 라이선스가 그룹에 전달 됩니다.

> [!NOTE]
> Microsoft 365 서비스 제품군 및 계획에 대 한 자세한 내용은 [microsoft 365 계획 옵션](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)을 참조 하십시오.

Exchange 전용 요금제가 있는 경우에도 Outlook에서 공유 받은 편지함 및 공유 일정 기능을 가져올 수는 있지만 문서 라이브러리, Planner 또는 기타 기능은 제공 되지 않습니다.

Microsoft 365 groups는 AAD (Azure Active Directory)를 사용 하 여 작동 합니다. 얻을 수 있는 그룹 기능은 사용 하는 Azure Active Directory 구독 및 그룹 구성 도우미에 할당 된 라이선스에 따라 달라 집니다.

> [!IMPORTANT]
> 모든 그룹 기능에서 Azure AD Premium 구독을 사용 하는 경우 사용자는 AAD P1 라이선스가 할당 되어 있는지 여부에 관계 없이 그룹에 가입할 수 있습니다. 라이선스가 적용 되지 않습니다.
> 정기적으로 사용 현황 보고서를 생성 하 여 라이선스가 누락 된 사용자를 확인 하 고, 라이선스 요구 사항을 충족 하기 위해 할당 해야 하는 것이 있어야 합니다. 예를 들어 사용자에 게 라이선스가 없고 명명 정책이 적용 되는 그룹에 추가 된다고 가정해 보겠습니다. 보고서는 라이선스가 필요 하다 고 사용자에 게 플래그를 지정 합니다.

## <a name="related-articles"></a>관련 문서

[Microsoft 365 그룹에 대 한 자세한 정보](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Microsoft 365 그룹으로 메일 그룹 업그레이드](../manage/upgrade-distribution-lists.md)

[PowerShell을 사용 하 여 Microsoft 365 그룹 관리](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[SharePoint Online 제한 사항](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
