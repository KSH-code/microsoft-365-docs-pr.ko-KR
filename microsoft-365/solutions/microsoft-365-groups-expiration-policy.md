---
title: Microsoft 365 그룹 만료 정책
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: Microsoft 365 그룹 만료 정책에 대해 자세히 알아보습니다.
ms.openlocfilehash: d55cc7fff939cb07ae2eba92de411e8f0d088885
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613657"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365 그룹 만료 정책

Microsoft 365 그룹 및 Microsoft Teams의 사용이 증가하면 관리자와 사용자는 사용되지 않는 그룹 및 팀을 정리하는 방법이 필요합니다. Microsoft 365 그룹 만료 정책은 시스템에서 비활성 그룹을 제거하고 더 깔끔하게 만드는 데 도움이 될 수 있습니다.

그룹이 만료되면 연결된 모든 서비스(사서함, Planner, SharePoint 사이트, 팀 등)도 삭제됩니다.

그룹이 만료되면 최대 30일 동안 복구할 수 있는 "소프트 삭제"됩니다.

관리자는 만료 기간을 지정할 수 있으며 해당 기간이 끝나면 갱신되지 않는 모든 비활성 그룹이 삭제됩니다. 보관된 팀이 포함됩니다. 만료 기간은 그룹이 만들어지거나 마지막으로 갱신된 날짜에 시작됩니다. 만료되기 전에 그룹 소유자가 다른 만료 간격으로 그룹을 갱신할 수 있는 전자 메일이 자동으로 전송됩니다. Teams 사용자는 Teams에서 영구 알림을 볼 수 있습니다.

적극적으로 사용되고 있는 그룹은 자동으로 갱신됩니다. 다음 작업을 수행하면 그룹이 자동으로 갱신됩니다.
- SharePoint - 파일을 보기, 편집, 다운로드, 이동, 공유 또는 업로드합니다. SharePoint 페이지를 보는 것은 자동 갱신 작업으로 계산되지 않습니다.
- Outlook - 그룹에 가입하거나 그룹에서 그룹 메시지를 읽거나 쓰며 메시지(웹용 Outlook)처럼 표시됩니다.
- Teams - 팀 채널 방문.

> [!IMPORTANT]
> 만료 정책을 변경하면 서비스에서 각 그룹의 만료 날짜를 다시 계산합니다. 항상 그룹이 만들어진 날짜부터 계산을 시작한 다음 새 만료 정책을 적용합니다.

만료는 기본적으로 해제되어 있는지 알아야 합니다. 관리자는 조직에서 사용할 수 있도록 설정해야 합니다.

> [!NOTE]
> Microsoft 365 그룹에 대한 만료 정책을 구성하고 사용하려면 소유해야 하지만 만료 정책이 적용되는 모든 그룹의 구성원에 대해 Azure AD Premium 라이선스를 할당할 필요는 없습니다. 자세한 내용은 [Azure Active Directory Premium 시작을 참조하세요.](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Microsoft 365 그룹 만료 정책을 구성하고 사용할 수 있는 사람

|역할|할 수 있는 일|
|---------|---------|
|Office 365 전역 관리자(Azure의 경우 회사 관리자), 사용자 관리자|Microsoft 365 그룹 만료 정책 설정을 만들거나, 읽거나, 업데이트하거나, 삭제합니다.|
|사용자|소유한 [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) Microsoft 365 그룹 갱신 또는 복원|

## <a name="how-to-set-the-expiration-policy"></a>만료 정책을 설정하는 방법

위에서 설명한 대로 만료는 기본적으로 꺼져 있습니다. 관리자는 만료 정책을 사용하도록 설정하고 해당 정책을 적용하려면 속성을 설정해야 합니다. 사용하도록 설정하려면 **Azure Active Directory** 그룹  >  **만료로**  >  **이동하십시오.** 여기서 기본 그룹 수명을 설정하고 첫 번째 및 두 번째 만료 알림이 그룹 소유자에게 얼마나 미리 전송될지 지정할 수 있습니다.

그룹 수명은 일로 지정하며 180, 365 또는 지정한 사용자 지정 값으로 설정할 수 있습니다. 사용자 지정 값은 30일 이상을 지정해야 합니다.

그룹에 소유자가 없는 경우 만료 전자 메일은 지정된 관리자에게 전달됩니다.

모든 그룹에 대해 정책을 설정하고 선택한 그룹만 설정하거나 없음을 선택하여 정책을 완전히 해제할 **수 있습니다.** 현재 다른 그룹에 대해 다른 정책을 사용할 수 없습니다.

![Azure Active Directory의 그룹 만료 설정 스크린샷](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>보존 정책에 만료가 작동하는 방식

보안 및 준수 센터에서 그룹에 대한 보존 정책을 설정한 경우 만료 정책은 보존 정책과 원활하게 작동합니다. 그룹이 만료되면 그룹 사이트의 사서함 대화 및 파일은 보존 정책에 정의된 특정 일 수 동안 보존 컨테이너에 보존됩니다. 그러나 만료 후 사용자는 그룹 또는 해당 콘텐츠를 볼 수 없습니다.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>그룹 소유자가 그룹이 만료될지 알아보는 방법 및 시간

그룹 소유자는 전자 메일을 통해서만 알림을 하게 됩니다. Planner, SharePoint 또는 다른 앱을 통해 그룹을 만든 경우 만료 알림은 항상 전자 메일을 통해 전송됩니다. Teams를 통해 그룹을 만든 경우 그룹 소유자는 활동 섹션을 통해 갱신할 알림을 받게 됩니다. 그룹 소유자가 유효한 전자 메일 주소가 없는 경우 그룹에서 만료를 사용하도록 설정하지 않는 것이 좋습니다.

그룹이 만료되기 30일 전에 그룹 소유자(또는 소유자가 없는 그룹에 대해 지정한 전자 메일 주소)는 쉽게 그룹을 갱신할 수 있는 전자 메일을 받게 됩니다. 갱신하지 않는 경우 만료 15일 전에 다른 갱신 전자 메일을 받게 됩니다. 아직 갱신하지 않은 경우 만료 전날에 한 번 더 전자 메일 알림을 받게 됩니다.

어떤 이유로 인해 소유자 또는 관리자가 만료되기 전에 그룹을 갱신하지 않은 경우 관리자는 만료 후 최대 30일 동안 그룹을 복원할 수 있습니다. 자세한 내용은 다음을 [참조합니다. 삭제된 Microsoft 365 그룹](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)복원

## <a name="archiving-group-contents"></a>보관 그룹 콘텐츠

더 이상 사용할 계획이 없는 그룹이 있지만 해당 콘텐츠를 보존하려는 경우 보관 [그룹,](end-life-cycle-groups-teams-sites-yammer.md) 팀 및 Yammer 그룹 서비스에서 정보를 내보내는 방법에 대한 자세한 내용을 참조하세요.

## <a name="related-topics"></a>관련 항목

[공동 작업 거버넌스 계획 단계별](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[공동 작업 거버넌스 계획 만들기](collaboration-governance-first.md)

[보존 정책 개요](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[분리된 그룹에 새 소유자 할당](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Microsoft 365 그룹 만료 구성](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
