---
title: 게스트와 팀으로 공동 작업하기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Teams에서 게스트와 작업, 대화 및 설명서 공동 작업을 위한 팀을 설정하는 데 필요한 Microsoft 365 구성 단계에 대해 자세히 알아보십시오.
ms.openlocfilehash: 34b7d5d47d7fb0c9196beda70184fa6510b6cc33
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780547"
---
# <a name="collaborate-with-guests-in-a-team"></a>게스트와 팀으로 공동 작업하기

문서, 작업 및 대화에서 게스트와 공동 작업을 해야 하는 경우 Microsoft Teams를 사용하는 것이 좋습니다. Teams는 통합된 사용자 환경의 사용자 지정 및 Extensible 공동 작업 도구 집합과 영구 채팅을 통해 Office 및 SharePoint에서 사용할 수 있는 모든 공동 작업 기능을 제공합니다.

이 문서에서는 게스트와 공동 작업을 위한 팀을 설정하는 데 필요한 Microsoft 365 구성 단계를 진행합니다.

## <a name="video-demonstration"></a>동영상 데모

이 비디오에서는 이 문서에 설명된 구성 단계를 보여줍니다.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 외부 공동 작업 설정

Microsoft 365에서 공유는 [Azure Active Directory의 B2B](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)외부 공동 작업 설정에 의해 가장 높은 수준에서 관리됩니다. Azure AD에서 게스트 공유를 사용하지 않도록 설정하거나 제한하는 경우 이 설정은 Microsoft 365에서 구성한 모든 공유 설정을 다시 적용합니다.

B2B 외부 공동 작업 설정 설정을 확인하여 게스트와의 공유가 차단되지 않는지 확인합니다.

![Azure Active Directory 조직 관계 설정 페이지 스크린샷](../media/azure-ad-organizational-relationships-settings.png)

외부 공동 작업 설정을 설정하려면

1. Azure Active Directory에 [https://aad.portal.azure.com](https://aad.portal.azure.com) 로그인합니다.
2. 왼쪽 탐색 창에서 **Azure Active Directory를 클릭합니다.**
3. 외부 **ID를 클릭합니다.**
4. 시작 **화면의 왼쪽** 탐색 창에서 외부 공동 작업 설정을 **클릭합니다.**
5. 게스트 초대자 역할의 관리자와 **사용자가** 초대할 수 있으며 구성원이 초대할 수 **있는** 사용자가 모두 예로 설정되어 있도록 **합니다.**
6. 변경한 내용이 있으면 **저장** 을 클릭합니다.

공동 작업 제한 섹션의 **설정을 확인합니다.** 공동 작업할 게스트의 도메인이 차단되지 않는지 확인

여러 조직의 게스트와 함께 작업하는 경우 디렉터리 데이터에 액세스하는 기능을 제한할 수 있습니다. 이렇게 하면 다른 사용자가 디렉터리에서 게스트인 것을 볼 수 없습니다. 이를 위해 게스트 사용자 액세스 제한에  따라 선택 게스트 사용자는 디렉터리 개체 설정의 속성 및 멤버 자격에 대한 액세스가 제한되거나 게스트 사용자 액세스는 자신의 디렉터리 개체의 속성 및 멤버 자격으로 제한됩니다. 

## <a name="teams-guest-access-settings"></a>Teams 게스트 액세스 설정

Teams에는 게스트 액세스에 대한 마스터 켜기/끄기 스위치와 게스트가 팀에서 할 수 있는 작업을 제어하는 데 사용할 수 있는 다양한 설정이 있습니다. 마스터 스위치,  **Teams에서 게스트 액세스가 작동하려면 Teams에서** 게스트 액세스 허용이 켜 있어야 합니다.

Teams에서 게스트 액세스를 사용하도록 설정되어 있는지 확인하고 비즈니스 요구에 따라 게스트 설정을 조정합니다. 이러한 설정은 모든 팀에 영향을 미치게 됩니다.

![Teams의 게스트 액세스 토글의 스크린샷](../media/teams-guest-access-toggle-on.png)

Teams 게스트 액세스를 설정하려면 다음을 수행합니다.

1. [https://admin.microsoft.com](https://admin.microsoft.com)에서 Microsoft 365 관리 센터에 로그인합니다.
2. 왼쪽 탐색 창에서 모두 **표시를 클릭합니다.**
3. **관리 센터** 에서 **Teams** 를 클릭합니다.
4. Teams 관리 센터의 왼쪽 탐색 창에서 **Org 전체** 설정을 확장하고 게스트 액세스를 **클릭합니다.**
5. Teams의 **게스트 액세스 허용** 이 **사용** 으로 설정되어 있는지 확인합니다.
6. 추가 게스트 설정을 원하는대로 변경 한 다음 **저장** 을 클릭하세요.

Teams 게스트 액세스가 설정되어 있는 경우 선택적으로 민감도 레이블을 사용하여 개별 팀 및 관련 SharePoint 사이트에 대한 게스트 액세스를 제어할 수 있습니다. 자세한 내용은 [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)를 참조하세요.

> [!NOTE]
> 켜면 Teams 게스트 설정이 활성화되기까지 최대 24시간이 걸릴 수 있습니다.

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 그룹 게스트 설정

Teams는 팀 구성원 자격에 Microsoft 365 그룹을 사용 합니다. Teams에서 게스트 액세스가 작동하려면 Microsoft 365 그룹 게스트 설정을 켜야 합니다.

![Microsoft 365 관리 센터의 Microsoft 365 그룹 게스트 설정 스크린샷](../media/office-365-groups-guest-settings.png)

Microsoft 365 그룹 게스트 설정을 설정하려면

1. Microsoft 365 관리 센터의 왼쪽 탐색 창에서 설정을 **확장합니다.**
2. Org **설정을 클릭합니다.**
3. 목록에서 Microsoft **365** 그룹을 클릭합니다.
4. 그룹 소유자가 조직 외부의 구성원을 **게스트로 추가하고** 게스트  그룹 구성원이 그룹 콘텐츠 확인란에 액세스하도록 허용 확인란을 모두 선택해야 합니다.
5. 변경한 경우 변경 내용 **저장을 클릭합니다.**


## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 조직 수준 공유 설정

파일, 폴더 및 목록과 같은 Teams 콘텐츠는 모두 SharePoint에 저장됩니다. 게스트가 Teams에서 이러한 항목에 액세스할 수 있도록 SharePoint 조직 수준 공유 설정에서 게스트와의 공유를 허용해야 합니다.

조직 수준 설정에 따라 팀과 연결된 사이트를 포함하여 개별 사이트에 사용할 수 있는 설정이 결정됩니다. 사이트 설정은 조직 수준 설정보다 더 많이 사용할 수 없습니다.

허용되지 않은 사용자와 파일 및 폴더 공유를 허용하려는 경우 모든 사람을 **선택하십시오.** 모든 게스트가 인증을 하도록 하려는 경우 신규 및 기존 **게스트를 선택 합니다.** 조직의 모든 사이트에서 필요한 가장 적합한 설정을 선택하십시오.

![SharePoint 조직 수준 공유 설정의 스크린샷](../media/sharepoint-organization-external-sharing-controls.png)


SharePoint 조직 수준 공유 설정을 설정하려면

1. Microsoft 365 관리 센터의 왼쪽 탐색 창에 있는 관리 **센터에서** **SharePoint를 클릭합니다.**
2. SharePoint 관리 센터의 왼쪽 탐색 창에서  정책을 확장한 다음 공유를 **클릭합니다.**
3. SharePoint의 외부 공유가 **모든** 사용자 또는 신규 및 기존 **게스트로 설정되어 있도록 합니다.**
4. 변경한 내용이 있으면 **저장** 을 클릭합니다.


## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 조직 수준 기본 링크 설정

기본 파일 및 폴더 링크 설정에 따라 파일 또는 폴더를 공유할 때 기본적으로 사용자에게 표시되는 링크 옵션이 결정됩니다. 사용자는 원하는 경우 공유하기 전에 링크 유형을 다른 옵션 중 하나로 변경할 수 있습니다.

이 설정은 조직의 모든 팀 및 SharePoint 사이트에 영향을 미치게 됩니다.

사용자가 파일 및 폴더를 공유할 때 기본적으로 선택되는 다음 링크 유형 중 하나를 선택하십시오.

- **링크가 있는** 모든 사용자 - 파일 및 폴더의 무단 공유를 많이 할 것으로 예상되는 경우 이 옵션을 선택합니다. 모든 사용자 링크를 *허용하지만* 실수로 허용되지 않은 공유가 우려되는 경우 다른 옵션 중 하나를 기본값으로 고려합니다. 이 링크 유형은 모든 사용자 공유를 사용하도록 설정한 **경우만 사용할 수** 있습니다.
- **조직의 사용자만** - 대부분의 파일 및 폴더 공유가 조직 내부의 사용자와 공유될 것으로 예상하는 경우 이 옵션을 선택합니다.
- **특정 사용자** - 게스트와 많은 파일 및 폴더 공유를 할 것으로 예상하는 경우 이 옵션을 고려하세요. 이 유형의 링크는 게스트와 함께 작동하며 인증을 요구합니다.
 
![SharePoint 조직 수준 파일 및 폴더 공유 설정 스크린샷](../media/sharepoint-organization-files-folders-sharing-settings.png)


SharePoint 조직 수준 기본 링크 설정을 지정하려면

1. SharePoint 관리 센터의 공유 페이지로 이동합니다.
2. 파일 **및 폴더 링크 아래에서** 사용할 기본 공유 링크를 선택합니다.
3. 변경한 내용이 있으면 **저장** 을 클릭합니다.

## <a name="create-a-team"></a>팀 만들기

다음 단계는 게스트와 공동 작업하는 데 사용할 팀을 만드는 것입니다.

팀을 만들 수 있습니다.
1. Teams의 **Teams** 탭에서 왼쪽  창의 아래쪽에 참가를 클릭하거나 팀을 생성합니다.
2. 팀 **만들기를 클릭합니다.**
3. 처음부터 **팀 구성을 클릭합니다.**
4. 개인 **또는 공용을** **선택**
5. 팀의 이름과 설명을 입력한 다음 만들기를 **클릭합니다.**
6. 건너뛰기 를 **클릭합니다.**

나중에 사용자를 초대합니다. 다음으로 팀과 연결된 SharePoint 사이트의 사이트 수준 공유 설정을 확인합니다.

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 사이트 수준 공유 설정

사이트 수준 공유 설정을 확인하여 이 팀에 대해 원하는 액세스 유형을 허용하는지 확인합니다. 예를 들어 조직 수준 설정을 **모든** 사용자로 설정했지만 모든 게스트가 이 팀에 대해 인증을 하게 하려는 경우 사이트 수준 공유 설정이 신규 및 기존 게스트로 설정되어 있는지 **확인합니다.**

![SharePoint 사이트 외부 공유 설정 스크린샷](../media/sharepoint-site-external-sharing-settings.png)

사이트 수준 공유 설정을 설정하려면
1. SharePoint 관리 센터의 왼쪽 탐색 창에서 사이트를 **확장하고** 활성 **사이트를 클릭합니다.**
2. 방금 생성한 팀의 사이트를 선택합니다.
3. Click ... 및 **공유를 선택 합니다.**
4. 공유가 모든 사용자  또는 신규 및 기존 **게스트로 설정되어 있도록 합니다.**
5. 변경한 내용이 있으면 **저장** 을 클릭합니다.

## <a name="invite-users"></a>사용자 초대하기

이제 게스트 공유 설정이 구성되어 팀에 내부 사용자와 게스트를 추가할 수 있습니다. 

내부 사용자를 팀에 초대
1. 팀에서 추가 **옵션()을** 클릭한 다음 구성원 **\*\*\*** **추가를 클릭합니다.**
2. 초대할 사람의 이름을 입력합니다.
3. **추가** 를 클릭한 다음 **닫기** 를 클릭합니다.

게스트를 팀에 초대
1. 팀에서 추가 **옵션()을** 클릭한 다음 구성원 **\*\*\*** **추가를 클릭합니다.**
2. 초대할 게스트의 전자 메일 주소를 입력합니다.
3. 게스트 **정보 편집을 클릭합니다.**
4. 게스트의 전체 이름을 입력하고 확인 표시를 클릭합니다.
5. **추가** 를 클릭한 다음 **닫기** 를 클릭합니다.

## <a name="see-also"></a>참고 항목

[인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례](best-practices-anonymous-sharing.md)

[게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한](share-limit-accidental-exposure.md)

[보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md)

[관리 대상 게스트와 B2B 엑스트라넷 작성](b2b-extranet.md)

[Azure AD B2B와 SharePoint 및 OneDrive의 통합(미리 보기)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[SharePoint 또는 OneDrive에서 공유하는 경우 공유 옵션이 회색으로 표시됩니다.](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
