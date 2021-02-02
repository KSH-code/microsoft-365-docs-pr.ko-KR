---
title: Microsoft 365의 정보 장벽에 대해 자세히 알아보기
description: 정보 장벽을 사용하여 조직 내에서 Microsoft Teams를 사용하여 커뮤니케이션 규정 준수를 보장합니다.
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 003347d46bed2529831a92681e73630d58a1f653
ms.sourcegitcommit: 8d28bce1a3445878b066864e766cf52cb83becd1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50071273"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Microsoft 365의 정보 장벽에 대해 자세히 알아보기

Microsoft 클라우드 서비스에는 강력한 통신 및 공동 작업 기능이 포함되어 있습니다. 그러나 조직에서 이해 관계가 충돌하지 않도록 두 그룹 간의 통신 및 공동 작업을 제한하려는 경우를 가정해 가정해 야 합니다. 또는 내부 정보를 보호하기 위해 조직 내부의 특정 사용자 간의 통신 및 공동 작업을 제한하려는 경우도 있습니다. Microsoft 365를 사용하면 그룹 및 조직 전체에서 통신 및 공동 작업을 할 수 있으므로 필요한 경우 특정 사용자 그룹 간 통신 및 공동 작업을 제한할 수 있나요? 정보 장벽을 통해 할 수 있습니다!

Microsoft Teams, SharePoint Online 및 비즈니스용 OneDrive는 정보 장벽을 지원합니다. 구독에 정보 [](#required-licenses-and-permissions) 장벽, 준수 관리자 또는 정보 장벽 관리자가 Microsoft Teams의 사용자 그룹 간의 통신을 허용하거나 차단하는 정책을 정의할 수 있습니다. 정보 장벽 정책은 다음 상황에서 사용할 수 있습니다.

- 일의 거래자 그룹 사용자는 마케팅 팀과 파일을 통신하거나 공유하면 안 됩니다.
- 기밀 회사 정보를 작업하는 재무 직원은 조직 내의 특정 그룹과 파일을 통신하거나 공유하면 안 됩니다.
- 거래 비밀 자료가 있는 내부 팀은 조직 내의 특정 그룹의 사용자와 온라인으로 전화를 걸거나 채팅하면 안 됩니다.
- 연구 팀이 제품 개발 팀과만 온라인으로 전화하거나 채팅해야 합니다.
- 일 거래자 그룹을 위한 사이트는 해당 일자 거래자 그룹 외부의 모든 사람이 공유하거나 액세스하면 안 됩니다.

> [!IMPORTANT]
> 정보 장벽 ***는** _양방 제한만 지원됩니다. 마케팅과 같은 한 가지 제한은 일 거래자들과 의사 소통하고 공동 작업을 할 수 있지만 매일 거래자는 마케팅 _*으로 통신하고 공동 작업할 _수_ 없습니다 **.

이러한 모든 예제 시나리오(및 그 이상)에 대해 Microsoft Teams, SharePoint Online 및 OneDrive에서 커뮤니케이션 및 공동 작업을 방지하거나 허용하도록 정보 장벽 정책을 정의할 수 있습니다. 이러한 정책은 사용자가 원치 않는 사용자와 통화하거나 채팅하는 것을 방지하거나, 사용자가 Microsoft Teams의 특정 그룹과만 통신할 수 있도록 할 수 있습니다. 정보 장벽 정책이 적용된 경우 해당 정책이 적용된 사용자가 Microsoft Teams의 다른 사용자와 통신 및 공동 작업을 시도할 때마다 SharePoint Online 또는 OneDrive 검사가 수행되어 정보 장벽 정책에 의해 정의되는 커뮤니케이션 및 공동 작업을 방지(또는 허용)합니다.

정보 장벽이 있는 사용자 경험에 대한 자세한 내용은 다음을 참조하세요.

- [Microsoft Teams의 정보 장벽](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online의 정보 장벽](/sharepoint/information-barriers)
- [OneDrive의 정보 장벽](/onedrive/information-barriers)

> [!IMPORTANT]
> 현재 정보 장벽은 전자 메일 통신에 적용되지 않습니다. 또한 정보 장벽은 규정 준수 [경계와 독립적입니다.](set-up-compliance-boundaries.md)<p> 정보 장벽 정책을 정의하고 적용하기 전에 조직에 [Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) 주소부 정책이 적용되지 않는지 확인해야 합니다. (정보 장벽은 주소부 정책을 기반으로 합니다.)

## <a name="what-happens-with-information-barriers"></a>정보 장벽으로 발생하는 일

정보 장벽 정책이 적용된 경우 다른 특정 사용자와 파일을 통신하거나 공유하면 안되는 사용자는 해당 사용자를 찾고, 선택하거나, 채팅하거나, 전화를 걸 수 없습니다. 정보 장벽으로 무단 통신 및 공동 작업을 방지하기 위한 검사가 진행됩니다. 

정보 장벽은 Microsoft Teams(채팅 및 채널), SharePoint Online 및 OneDrive에 적용됩니다. Microsoft Teams에서 정보 장벽 정책은 다음과 같은 종류의 무단 통신을 결정하고 방지합니다.

- 사용자 검색
- 팀에 구성원 추가
- 다른 사용자와 채팅 세션 시작
- 그룹 채팅 시작
- 다른 사용자가 모임에 참가할 수 있는 경우
- 화면 공유
- 전화 걸기
- 다른 사용자와 파일 공유
- 공유 링크를 통해 파일에 액세스

관련 사용자가 활동을 방지하기 위해 정보 장벽 정책에 포함된 경우 계속할 수 없습니다. 또한 정보 장벽 정책에 포함된 모든 사람이 Microsoft Teams의 다른 사용자와의 통신을 차단할 수 있습니다. 정보 장벽 정책의 영향을 받는 사람이 동일한 팀 또는 그룹 채팅에 참여하는 경우 해당 채팅 세션에서 제거되고 그룹과의 추가 통신이 허용되지 않을 수 있습니다.

정보 장벽이 있는 사용자 경험에 대한 자세한 내용은 Microsoft Teams의 정보 장벽을 [참조하세요.](/MicrosoftTeams/information-barriers-in-teams)

SharePoint Online 및 OneDrive에서 정보 장벽 정책은 다음과 같은 종류의 권한이 없는 공동 작업을 결정하고 방지합니다.

- 사이트에 구성원 추가
- 사용자가 사이트 또는 콘텐츠 액세스
- 다른 사용자와 사이트 또는 콘텐츠 공유
- 사이트 검색

정보 장벽이 있는 사용자 경험에 대한 자세한 내용은 [SharePoint Online의](/sharepoint/information-barriers) 정보 장벽을 참조하세요.

## <a name="required-licenses-and-permissions"></a>필수 라이선스 및 사용 권한

정보 장벽은 이제 출시 중으로, 다음과 같은 구독에 포함됩니다.

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Microsoft 365 규정 준수 E5/A5
- Microsoft 365 내부자 위험 관리

자세한 내용은 보안 및 규정 준수에 대한 [Microsoft 365 & 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

정보 장벽 정책을 정의하거나 [편집하려면](information-barriers-policies.md)다음 역할 중 하나를 할당해야 합니다.

- Microsoft 365 전역 관리자
- Office 365 전역 관리자
- 준수 관리자
- IB 준수 관리

(역할 및 사용 권한에 대한 자세한 내용은 [Office 365 보안](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)및 준수 센터의 사용 & 참조).

정보 장벽 정책을 정의, 유효성 검사 또는 편집하려면 PowerShell cmdlet에 익숙해야 합니다. 방법 문서에서 PowerShell cmdlet의 몇 [](information-barriers-policies.md)가지 예를 제공하겠지만, 조직에 대한 매개 변수와 같은 다른 세부 정보를 알아야 합니다.

## <a name="next-steps"></a>다음 단계

- [Microsoft Teams의 정보 장벽에 대해 자세히 알아보기](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online의 정보 장벽에 대해 자세히 알아보기](/sharepoint/information-barriers)
- [OneDrive의 정보 장벽에 대한 자세한 정보](/onedrive/information-barriers)
- [정보 장벽 정책에 사용할 수 있는 특성을 참조하세요.](information-barriers-attributes.md)
- [정보 장벽에 대한 정책 정의](information-barriers-policies.md)
- [정보 장벽 정책 편집(또는 제거)](information-barriers-edit-segments-policies.md)