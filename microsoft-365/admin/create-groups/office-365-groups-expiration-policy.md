---
title: 그룹 만료 정책
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 그룹 만료 정책에 대해 자세히 알아봅니다.
ms.openlocfilehash: be61c66b310ada07876c5b3b005e6a7eb660092d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630058"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365 그룹 만료 정책

Microsoft 365 그룹의 사용이 증가 함에 의해 관리자와 사용자는 사용 되지 않은 그룹을 정리할 수 있는 방법이 필요 합니다. 만료 정책은 시스템에서 비활성 그룹을 제거 하는 데 도움이 될 수 있습니다.

그룹이 만료 되 면 관련 된 모든 서비스 (사서함, Planner, SharePoint 사이트, 팀 등)도 삭제 됩니다.

그룹이 만료 되 면 "일시 삭제"가 되어 최대 30 일 동안 복구할 수 있다는 것을 의미 합니다.

관리자는 만료 기간을 지정할 수 있으며 해당 기간 끝에 도달 하 고 갱신 되지 않은 비활성 그룹은 삭제 됩니다. 만료 기간은 그룹을 만들 때 또는 마지막으로 갱신 된 날짜에 시작 됩니다. 그룹 소유자는 만료 되기 전에 자동으로 전자 메일을 보내 다른 만료 간격으로 그룹을 갱신할 수 있습니다. 팀 사용자는 팀에 영구 알림을 볼 수 있습니다.

현재 사용 중인 그룹은 자동으로 갱신 됩니다. 다음 작업 중 하나를 수행 하면 그룹이 자동으로 갱신 됩니다.
- SharePoint-파일을 보고, 편집 하 고, 다운로드 하거나, 이동 하거나, 공유 하거나, 업로드 합니다.
- Outlook-그룹에서 그룹 메시지를 읽거나 메시지를 작성 합니다 (예를 들어, 웹에서 Outlook).
- 팀-팀 채널을 방문 합니다.

> [!IMPORTANT]
> 만료 정책을 변경 하면 서비스에서 각 그룹의 만료 날짜를 다시 계산 합니다. 항상 그룹을 만든 날짜부터 계산을 시작 하 고 새 만료 정책을 적용 합니다.

만료는 기본적으로 꺼져 있다는 것을 알아야 합니다. 관리자가 사용 하려는 조직에 대해이를 사용 하도록 설정 해야 합니다.

> [!NOTE]
> Microsoft 365 그룹에 대 한 만료 정책을 구성 하 고 사용 하려면 만료 정책이 적용 되는 모든 그룹의 구성원에 대해 Azure AD Premium 라이선스를 소유 하 고 반드시 할당 해야 하는 것은 아닙니다. 자세한 내용은 [Azure Active Directory Premium 시작을](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)참조 하세요.

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Microsoft 365 groups 만료 정책을 구성 하 고 사용할 수 있는 사람은 누구 인가요?

|역할|수행할 수 있는 작업|
|---------|---------|
|전역 관리자 (Azure, 회사 관리자), 사용자 관리자|Microsoft 365 groups 만료 정책 설정을 만들거나, 읽거나, 업데이트 하거나, 삭제 합니다.|
|사용자|자신이 소유한 Microsoft 365 그룹 갱신 또는 [복원](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)|

## <a name="how-to-set-the-expiration-policy"></a>만료 정책을 설정 하는 방법

위에서 설명한 것 처럼 만료는 기본적으로 해제 되어 있습니다. 관리자는 만료 정책을 사용 하도록 설정 하 고 속성을 설정 해야 해당 정책이 적용 됩니다. 이 기능을 사용 하도록 설정 > 하려면 **AAD (Azure Active Directory)****그룹** > **만료**로 이동 합니다. 여기에서 기본 그룹 수명을 설정 하 고 첫 번째 및 두 번째 만료 알림이 그룹 소유자에 게 이동 하기 전 까지의 간격을 지정할 수 있습니다.

그룹 수명은 일 단위로 지정 되며 180, 365 또는 지정한 사용자 지정 값으로 설정할 수 있습니다. 사용자 지정 값은 30 일 이상 이어야 합니다.

그룹에 소유자가 없으면 만료 전자 메일이 지정 된 관리자에 게 전달 됩니다.

모든 그룹에 대 한 정책, 선택한 그룹만 설정할 수 있으며, **없음 (없음**)을 선택 하 여 완전히 끌 수도 있습니다. 현재 다른 그룹에 대해 서로 다른 정책을 사용할 수 없습니다.

![Azure Active Directory의 그룹 만료 설정 스크린샷](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>보존 정책에서 만료 작동 방식

그룹에 대 한 보안 및 준수 센터의 설치 보존 정책을 사용 하는 경우 만료 정책이 보존 정책과 함께 원활 하 게 작동 합니다. 그룹이 만료 되 면 메일 상자의 그룹 대화와 그룹 사이트의 파일은 보존 정책에 정의 된 특정 기간 (일) 동안 보존 컨테이너에 보존 됩니다. 그러나 만료 후에는 사용자에 게 그룹이 나 해당 콘텐츠가 표시 되지 않습니다.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>그룹이 만료 되는 경우 그룹 소유자가 학습 하는 방식 및 시기

그룹 소유자는 전자 메일을 통해서만 알림을 받습니다. Planner, SharePoint 또는 다른 앱을 통해 그룹을 만든 경우에는 항상 전자 메일을 통해 만료 알림이 제공 됩니다. 팀을 통해 그룹을 만든 경우 그룹 소유자는 활동 섹션을 통해 갱신 하 라는 알림을 받게 됩니다. 그룹 소유자에 게 유효한 전자 메일 주소가 없는 경우에는 그룹에서 만료를 사용 하지 않는 것이 좋습니다.

30 일 동안 그룹이 만료 되는 경우 그룹 소유자 (또는 소유자가 없는 그룹에 대해 지정한 전자 메일 주소)는 그룹을 쉽게 갱신할 수 있도록 전자 메일을 받습니다. 갱신 하지 않으면 만료 되기 15 일 전에 다른 갱신 전자 메일이 수신 됩니다. 아직 갱신 하지 않은 경우에는 만료 되기 전에 하루 동안 전자 메일 알림을 한 번 더 받게 됩니다.

어떤 이유로 든 소유자 또는 관리자가 만료 되기 전에 그룹을 갱신 하지 않을 경우 관리자는 만료 후 최대 30 일 동안 그룹을 복원할 수 있습니다. 자세한 내용은 [삭제 된 Microsoft 365 그룹 복원을](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)참조 하십시오.

## <a name="related-articles"></a>관련 문서

[보존 정책 개요](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[분리된 그룹에 새 소유자 할당](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Microsoft 365 그룹 만료 구성](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal) '
