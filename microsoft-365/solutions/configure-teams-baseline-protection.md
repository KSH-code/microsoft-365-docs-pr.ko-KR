---
title: 기본 보호 기능으로 팀 구성
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
- admindeeplinkTEAMS
recommendations: false
description: 기본 수준의 보호로 팀을 배포하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ac16f3a1fd70cca22d0cc44e326d173b30cff77f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208364"
---
# <a name="configure-teams-with-baseline-protection"></a>기본 보호 기능으로 팀 구성

이 문서에서는 기본 수준의 보호 기능으로 팀을 배포하는 방법을 살펴봅니다. 이 수준을 통해 사용자는 다양한 공동 작업 옵션을 사용하면서 권한 관리를 강화하고 과잉 공유에 대한 기본 보호를 제공할 수 있습니다. 이 수준에 대한 권장 보호에는 ID 및 장치 액세스 정책과 맬웨어 방지가 포함됩니다. 또한 필요에 따라 조건부 액세스 정책 및 데이터 손실 방지를 적용할 수 있습니다.

## <a name="initial-protections"></a>초기 보호

첫 번째 단계로 기본 ID 및 장치 액세스 정책을 구성하는 것이 좋습니다. 자세한 내용은 [팀 채팅, 그룹, 파일에 대한 정책 권장 사항](../security/office-365-security/teams-access-policies.md)을 참조하세요.

또한 문서, 첨부 파일 및 링크의 맬웨어를 방지하기 위해 기본 Office 365용 Defender 기능을 설정하는 것이 좋습니다. 다음 표의 각 옵션을 설정하는 것이 좋습니다.

|옵션|정보|
|:------|:-----------|
|SPO, OneDrive 및 Teams용 안전 첨부 파일|[안전 첨부 파일](../security/office-365-security/safe-attachments.md) <p> [Office 365용 Defender - SharePoint, OneDrive 및 Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md)|
|안전 문서|[Office 365용 Microsoft Defender의 안전 문서](../security/office-365-security/safe-docs.md)|
|Teams용 안전 링크|[Teams의 Office 365 안전한 링크](../security/office-365-security/safe-links.md) <p> [안전 링크](../security/office-365-security/safe-links.md)|

## <a name="teams-guest-sharing"></a>Teams 게스트 공유

각 계층에서 조직 외부의 사용자와 공유할 수 있는 옵션이 있습니다. 중요하고 매우 중요한 계층의 경우 중요도 종류 레이블을 사용하여 팀 수준에서 게스트 공유를 해제할 수 있습니다. 그러나 팀에서 게스트 공유를 사용하려면 조직 수준의 게스트 공유 설정을 사용해야 합니다.

![Teams 게스트 액세스 토글 스크린샷.](../media/teams-guest-access-toggle-on.png)

Teams 게스트 액세스를 설정하려면 다음을 수행합니다.

1. [https://admin.microsoft.com](https://admin.microsoft.com)에서 Microsoft 365 관리 센터에 로그인합니다.
2. 왼쪽 탐색 창에서 **모두 표시** 를 클릭합니다.
3. **관리 센터** 에서 **Teams** 를 클릭합니다.
4. Teams 관리 센터의 왼쪽 탐색 창에서 **조직 전체 설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**게스트 액세스**</a>를 확장합니다.
5. Teams의 **게스트 액세스 허용** 이 **사용** 으로 설정되어 있는지 확인합니다.
6. 추가 게스트 설정을 원하는대로 변경 한 다음 **저장** 을 클릭하세요.

> [!NOTE]
> Teams 게스트 설정을 켠 후 활성화되려면 최대 24시간이 걸릴 수 있습니다.

Office 365 그룹 ​​및 SharePoint에서는 게스트 공유가 기본적으로 사용 설정되어 있지만 이전에 조직의 게스트 공유 설정을 변경한 경우 [팀의 게스트와 공동 작업](./collaborate-as-team.md)을 검토하여 게스트 공유를 Teams에서 사용할 수 있는지 확인하는 것이 좋습니다.

## <a name="site-and-file-sharing"></a>사이트 및 파일 공유

실수로 조직 외부 사람과 파일 또는 폴더를 공유 할 위험을 줄이려면 SharePoint의 기본 공유 링크를 *조직 내 사용자 전용* 으로 변경하는 것이 좋습니다. (사용자가 외부에서 공유해야 하고 게스트 공유를 활성화한 경우 공유할 때 링크 유형을 계속 변경할 수 있습니다.)

기본 공유 링크를 변경하려면
1. [SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.
2. **정책** 에서 **공유** 를 클릭하세요.
3. **파일 및 폴더 링크** 에서 **조직 내 사용자만** 을 선택합니다.
4. **저장** 을 클릭합니다.

최상의 게스트 공유 환경을 위해서는 [Azure AD B2B와의 SharePoint 및 OneDrive 통합](/sharepoint/sharepoint-azureb2b-integration-preview)을 사용하는 것이 좋습니다.

## <a name="create-a-team"></a>팀 만들기

기준 수준의 보호에 대한 추가 구성은 팀과 연결된 SharePoint 사이트에서 수행됩니다. 다음 섹션으로 진행하기 전에 [공개 또는 개인 팀을 만드세요](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).

## <a name="site-sharing-settings"></a>사이트 공유 설정

기본적으로 SharePoint 사이트의 구성원은 다른 사용자를 사이트에 초대할 수 있습니다. 사이트가 팀의 일부인 경우 팀 구성원이 사이트 구성원으로 포함됩니다. 그러나 사이트에 직접 추가된 사람들은 나머지 팀에 액세스할 수 없습니다. 따라서 팀을 통해서만 권한을 관리하는 것이 좋습니다.

권한 관리를 돕기 위해 소유자만 사이트를 공유할 수 있도록 연결된 사이트를 구성하는 것이 좋습니다. 이는 권한 관리를 단순화하고 팀 소유자 모르게 사람들이 액세스하지 못하게합니다. 기본 보호가 필요한 각 팀에 대해 이 작업을 수행하세요.

사이트 공유 설정을 업데이트하려면
1. 팀의 도구 막대에서 **파일** 을 클릭합니다.
2. **SharePoint에서 열기** 를 클릭하세요.
3. SharePoint 사이트의 도구 모음에서 설정 아이콘을 클릭한 다음 **사이트 권한** 을 클릭하세요.
4. **사이트 권한** 창의 **사이트 공유에** 서 **멤버 공유 방법 변경** 을 클릭하세요.
5. **권한 공유** 에서 **사이트 소유자 및 회원을 선택하고 편집 권한이 있는 사용자는 파일 및 폴더를 공유할 수 있지만 사이트 소유자 만 사이트를 공유할 수 있습니다** 를 선택한 다음 **저장** 을 클릭합니다.

## <a name="additional-protections"></a>추가 보호

Microsoft 365에서는 콘텐츠를 보호하기 위한 추가 방법을 제공합니다. 다음 옵션이 조직의 보안을 개선하는 데 도움이 되는지 고려해 보세요.

- 게스트들이 [사용 약관](/azure/active-directory/conditional-access/terms-of-use)에서 동의하도록 합니다.
- 게스트 사용자에 대한 [세션 시간 초과 정책](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)을 구성합니다.
- [중요한 정보 유형](../compliance/sensitive-information-type-learn-about.md)을 만들고 [데이터 손실 방지](../compliance/dlp-learn-about-dlp.md)를 사용하여 중요한 정보에 액세스하는 방법에 대한 정책을 설정합니다.

## <a name="see-also"></a>참고 항목

[Teams에서의 모임 정책 관리](/microsoftteams/meeting-policies-in-teams)

[내부자 위험 관리 시작](../compliance/insider-risk-management-configure.md)