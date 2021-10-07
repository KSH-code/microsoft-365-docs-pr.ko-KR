---
title: 게스트와 현장에서 공동 작업하기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 게스트와 공동 작업하기 위해 Microsoft 365 사이트 설정에 필요한 SharePoint 구성 단계에 대해 자세히 알아보십시오.
ms.openlocfilehash: aac548381b8b56ef753f762e9ef7bf0c07cf9163
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190212"
---
# <a name="collaborate-with-guests-in-a-site"></a>게스트와 현장에서 공동 작업하기

문서, 데이터 및 목록에서 게스트와 공동 작업을 해야 하는 경우 SharePoint 있습니다. 최신 SharePoint 사이트는 Microsoft 365 그룹에 연결되고 사이트 구성원을 관리하고 공유 사서함 및 일정과 같은 추가 공동 작업 도구를 제공할 수 있습니다.

이 문서에서는 게스트와 공동 작업을 위해 Microsoft 365 사이트 설정에 필요한 SharePoint 구성 단계를 단계적으로 진행합니다.

## <a name="video-demonstration"></a>동영상 데모

이 비디오에서는 이 문서에서 설명한 구성 단계를 보여줍니다.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 외부 공동 작업 설정

Microsoft 365의 공유는 [Azure Active Directory의 B2B 외부 공동 작업 설정](/azure/active-directory/external-identities/delegate-invitations)에 따라 가자 높은 수준에서 관리됩니다. Azure AD에서 게스트 공유가 비활성화되거나 제한된 경우 이 설정은 Microsoft 365에서 구성하는 모든 공유 설정을 재정의합니다.

B2B 외부 공동 작업 설정을 확인하여 게스트와의 공유가 차단되지 않는지 확인합니다.

![Screenshot of Azure Active Directory External collaboration 설정 page.](../media/azure-ad-organizational-relationships-settings.png)

외부 공동 작업 설정을 지정하려면

1. [https://aad.portal.azure.com](https://aad.portal.azure.com)에서 Azure Active Directory에 로그인합니다.
2. 왼쪽 탐색 창에서 **Azure Active Directory** 를 클릭합니다.
3. **외부 ID** 를 클릭합니다.
4. **시작** 화면의 왼쪽 탐색 창에서 **외부 동 작업 설정** 을 클릭합니다.
5. **게스트 초대자 역할의 관리자 및 사용자가 초대할 수 있음** 및 **구성원이 초대할 수 있음** 이 모두 **예** 로 설정되어 있는지 확인합니다.
6. 변경한 내용이 있으면 **저장** 을 클릭합니다.

**공동 작업 제한** 섹션의 설정을 확인합니다. 공동 작업하려는 게스트의 도메인이 차단되지 않았는지 합니다.

여러 조직의 게스트와 함께 작업하는 경우 디렉터리 데이터에 액세스하는 기능을 제한해야 할 수 있습니다. 이 작업을 수행하면 게스트가 디렉터리에 다른 게스트가 누구인지 볼 수 없습니다. 이 작업을 수행하려면, **게스트 사용자 액세스 제한** 아래에서 **디렉터리 개체 설정의 속성 및 멤버십에 대한 게스트 사용자의 액세스가 제한됨** 또는 **게스트 사용자 액세스가 해당 디렉터리 개체의 속성 및 멤버십으로 제한됨** 을 선택합니다.

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 그룹 게스트 설정

최신 SharePoint 사이트는 Microsoft 365 그룹을 사용하여 사이트 액세스를 제어합니다. Microsoft 365 사이트의 게스트 액세스가 작동하려면 SharePoint 그룹 게스트 설정을 설정해야 합니다.

![Microsoft 365 관리 센터의 Microsoft 365 그룹 게스트 설정 스크린샷.](../media/office-365-groups-guest-settings.png)

Microsoft 365 Groups 게스트 설정을 설정하려면

1. Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **설정** 을 확장합니다.
2. **조직 설정** 을 클릭합니다.
3. 목록에서 **Microsoft 365 그룹** 을 클릭합니다.
4. **그룹 소유자가 조직 외부의 사용자를 Microsoft 365 그룹에 게스트로 추가하도록 허용** 및 **게스트 그룹 구성원이 그룹 콘텐츠에 액세스하도록 허용** 확인란이 모두 선택되어 있는지 확인합니다.
5. 변경한 내용이 있으면 **변경 내용 저장** 을 클릭합니다.

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 수준 공유 설정

게스트가 SharePoint 액세스할 수 있도록 SharePoint 조직 수준 공유 설정에서 게스트와 공유할 수 있어야 합니다.

조직 수준 설정에 따라 개별 사이트에 사용할 수 있는 설정이 결정됩니다. 사이트 설정은 조직 수준 설정보다 더 제한될 수 없습니다.

허용되지 않은 파일 및 폴더 공유를 허용하려는 경우 모든 사람을 **선택하십시오.** 조직 외부의 모든 사용자가 인증을 하도록 하려는 경우 신규 및 기존 게스트 **를 선택 합니다.** 조직의 모든 사이트에서 필요한 가장 적합한 설정을 선택하세요.

![SharePoint 조직 수준 공유 설정 스크린샷.](../media/sharepoint-organization-external-sharing-controls.png)


SharePoint 조직 수준 공유 설정을 설정하려면

1. Microsoft 365 관리 센터의 왼쪽 탐색 창에 있는 **관리 센터** 에서 **SharePoint** 를 클릭합니다.
2. SharePoint 관리 센터의 왼쪽 탐색 창에 있는 **정책에서** 공유를 **클릭합니다.**
3. SharePoint에 대한 외부 공유가 **모든 사용자** 또는 **새 게스트 및 기존 게스트** 로 설정되어 있는지 확인합니다.
4. 변경한 내용이 있으면 **저장** 을 클릭합니다.

## <a name="create-a-site"></a>사이트 만들기

다음 단계는 게스트와 공동 작업하는 데 사용할 사이트를 만드는 것입니다.

사이트를 만들 수 있는 경우
1. SharePoint 관리 센터의 **사이트** 에서 **활성 사이트** 를 클릭하십시오.
2. **만들기** 를 클릭합니다.
3. 팀 **사이트를 클릭합니다.**
4. 사이트 이름을 입력하고 그룹 소유자(사이트 소유자)의 이름을 입력합니다.
5. 고급 **설정에서** 이 사이트를 공용 또는 개인 사이트로 사용할지 선택합니다.
6. **다음** 을 클릭합니다.
7. **마침** 을 클릭합니다.

나중에 사용자를 초대할 것입니다. 다음으로, 이 사이트의 사이트 수준 공유 설정을 점검해야 합니다.

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 사이트 수준 공유 설정

사이트 수준 공유 설정을 확인하여 이 사이트에 대해 원하는 액세스 유형을 허용하는지 확인합니다. 예를 들어 조직 수준 설정을 **모든** 사용자로 설정했지만 모든 게스트가 이 사이트에 대해 인증을 하려는 경우 사이트 수준 공유 설정이 신규 및 기존 게스트로 설정되어 있는지 **확인합니다.**

사이트는 모든 사용자(모든 사용자 설정)와 공유할 수 없지만 개별 파일 및 폴더는 공유할 수 있습니다.

민감도 레이블을 사용하여 사이트의 외부 공유 [설정을 SharePoint 있습니다.](../compliance/sensitivity-labels-teams-groups-sites.md)

![SharePoint 사이트 외부 공유 설정 스크린샷.](../media/sharepoint-site-external-sharing-settings.png)

사이트 수준 공유 설정을 설정하려면
1. SharePoint 관리 센터의 왼쪽 탐색 창에서 **사이트** 를 확장시키고 **Active 사이트** 를 클릭합니다.
2. 공유할 사이트를 선택합니다.
3. ...를 클릭하고 공유를 **클릭합니다.**
4. 공유가 **모든 사용자** 또는 **새 게스트 및 기존 게스트** 로 설정되었는지 확인합니다.
5. 변경한 내용이 있으면 **저장** 을 클릭합니다.

## <a name="invite-users"></a>사용자 초대하기

이제 게스트 공유 설정이 구성되어 내부 사용자 및 게스트를 사이트에 추가할 수 있습니다. 사이트 액세스는 연결된 Microsoft 365 통해 제어되어 있으므로 여기에 사용자를 추가할 것입니다.

내부 사용자를 그룹에 초대
1. 사용자를 추가할 사이트로 이동합니다.
2. 오른쪽 **상단에서** 구성원 수를 나타 내는 구성원 링크를 클릭합니다.
3. **구성원 추가** 를 클릭합니다.
4. 사이트에 초대할 사용자의 이름 또는 전자 메일 주소를 입력한 다음 저장을 **클릭합니다.**

사이트에서 게스트를 추가할 수 없습니다. 다음을 사용하여 추가해야 웹용 Outlook. 따라서 게스트를 그룹에 추가하고 그룹에 초대하려면 URL 열에서 사이트의 **URL을**  클릭하여 사이트별 페이지로 이동합니다. 이 페이지에서 앱 시작 **프로그램** 아이콘을 클릭하고 를 **Outlook.** 아래 절차에 설명된 그룹으로 게스트를 초대할 수 있는 화면입니다.

게스트를 그룹에 초대
1. **그룹에서** 게스트를 초대할 그룹을 클릭합니다.
2. 그룹 연락처 카드를 열고 오른쪽 위에 있는 구성원 링크(구성원 수를 나타 내는 링크)를 클릭합니다. 
3. 구성원 **추가를 클릭합니다.**
4. 초대할 게스트의 전자 메일 주소를 입력한 다음 추가를 **클릭합니다.**
5. **닫기** 를 클릭합니다.
그룹의 소유자가 아니며 그 결과 게스트를 그룹에 추가할 수 없는 경우 닫기만 클릭해야 합니다.  이 경우 그룹에 게스트를 추가하는 요청은 승인을 위해 그룹 소유자에게 전송됩니다.

## <a name="see-also"></a>참고 항목

[인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례](best-practices-anonymous-sharing.md)

[게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한](share-limit-accidental-exposure.md)

[보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md)

[관리 대상 게스트와 B2B 엑스트라넷 작성](b2b-extranet.md)

[Azure AD B2B와 SharePoint 및 OneDrive의 통합(미리 보기)](/sharepoint/sharepoint-azureb2b-integration-preview)