---
title: 게스트와 문서 상 공동 작업하기
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
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 이 문서에서는 게스트와 공동 작업하는 방법을 SharePoint OneDrive.
ms.openlocfilehash: e51ec7e9695c564b2994089f0a827ca7ea4b67c6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158961"
---
# <a name="collaborate-with-guests-on-a-document"></a>게스트와 문서 상 공동 작업하기

조직 외부의 사용자와 공동 작업을 해야 하는 경우 SharePoint OneDrive 문서에 대한 공유 링크를 보낼 수 있습니다. 이 문서에서는 조직의 요구에 Microsoft 365 및 사용자에 대한 공유 SharePoint OneDrive 설정하는 데 필요한 OneDrive 구성 단계를 단계적으로 수행합니다.

## <a name="video-demonstration"></a>동영상 데모

이 비디오에서는 이 문서에서 설명한 구성 단계를 보여줍니다.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 외부 공동 작업 설정

Microsoft 365의 공유는 [Azure Active Directory의 B2B 외부 공동 작업 설정](/azure/active-directory/external-identities/delegate-invitations)에 따라 가자 높은 수준에서 관리됩니다. Azure AD에서 게스트 공유를 사용하지 않도록 설정하거나 제한하는 경우 이 설정은 Azure AD에서 구성한 모든 공유 Microsoft 365.

B2B 외부 공동 작업 설정을 확인하여 게스트와의 공유가 차단되지 않는지 확인합니다.

![Azure Active Directory 조직 관계 설정 페이지 스크린샷.](../media/azure-ad-organizational-relationships-settings.png)

외부 공동 작업 설정을 지정하려면

1. [https://aad.portal.azure.com](https://aad.portal.azure.com)에서 Azure Active Directory에 로그인합니다.
2. 왼쪽 탐색 창에서 **Azure Active Directory** 를 클릭합니다.
3. **외부 ID** 를 클릭합니다.
4. **시작** 화면의 왼쪽 탐색 창에서 **외부 동 작업 설정** 을 클릭합니다.
5. **게스트 초대자 역할의 관리자 및 사용자가 초대할 수 있음** 및 **구성원이 초대할 수 있음** 이 모두 **예** 로 설정되어 있는지 확인합니다.
6. 변경한 내용이 있으면 **저장** 을 클릭합니다.

**공동 작업 제한** 섹션의 설정을 확인합니다. 공동 작업하려는 게스트의 도메인이 차단되지 않았는지 합니다.

여러 조직의 게스트와 함께 작업하는 경우 디렉터리 데이터에 액세스하는 기능을 제한해야 할 수 있습니다. 이 작업을 수행하면 게스트가 디렉터리에 다른 게스트가 누구인지 볼 수 없습니다. 이 작업을 수행하려면, **게스트 사용자 액세스 제한** 아래에서 **디렉터리 개체 설정의 속성 및 멤버십에 대한 게스트 사용자의 액세스가 제한됨** 또는 **게스트 사용자 액세스가 해당 디렉터리 개체의 속성 및 멤버십으로 제한됨** 을 선택합니다.

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 수준 공유 설정

조직 외부의 사용자가 SharePoint 또는 OneDrive 문서에 액세스할 수 있도록 SharePoint OneDrive 조직 수준 공유 설정을 통해 조직 외부의 사용자와 공유할 수 있어야 합니다.

조직의 조직 수준 설정에 SharePoint 사이트에 대해 사용할 수 있는 SharePoint 결정됩니다. 사이트 설정은 조직 수준 설정보다 더 제한될 수 없습니다. 조직의 수준 설정에 따라 OneDrive 라이브러리에서 사용할 수 있는 공유 OneDrive 결정됩니다.

이 SharePoint OneDrive 및 폴더 공유를 허용하려는 경우 모든 를 **선택하십시오.** 조직 외부의 사용자가 인증을 하도록 하려는 경우 신규 및 기존 게스트 **를 선택 합니다.** *모든* 사용자 링크는 가장 쉽게 공유할 수 있는 방법입니다. 조직 외부의 사람은 인증 없이 링크를 열 수 있으며 다른 사용자에게 링크를 무료로 전달할 수 있습니다.

이 SharePoint 조직의 모든 사이트에서 필요한 가장 적합한 설정을 선택하세요.

![SharePoint 조직 수준 공유 설정 스크린샷.](../media/sharepoint-organization-external-sharing-controls.png)


SharePoint 조직 수준 공유 설정을 설정하려면

1. Microsoft 365 관리 센터의 왼쪽 탐색 창에 있는 **관리 센터** 에서 **SharePoint** 를 클릭합니다.
2. SharePoint 관리 센터의 왼쪽 탐색 창에 있는 **정책에서** 공유를 **클릭합니다.**
3. 모든 사용자 또는 SharePoint OneDrive 및 기존 게스트로  외부 공유가 **설정되어 있도록 합니다.** 이 설정은 OneDrive 설정보다 더 SharePoint 않습니다.
4. 변경한 내용이 있으면 **저장** 을 클릭합니다.

## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 조직 수준 기본 링크 설정

기본 파일 및 폴더 링크 설정에 따라 사용자가 파일 또는 폴더를 공유할 때 기본적으로 사용자에게 표시되는 링크 옵션이 결정됩니다. 원하는 경우 공유하기 전에 링크 유형을 다른 옵션 중 하나로 변경할 수 있습니다.

이 설정은 조직의 SharePoint 사이트에 영향을 미치며, OneDrive.

사용자가 파일 및 폴더를 공유할 때 기본적으로 선택되는 다음 유형의 링크를 선택하십시오.

- **링크가 있는** 모든 사용자 - 많은 확인되지 않은 파일 및 폴더 공유를 할 것으로 예상하는 경우 이 옵션을 선택합니다. 링크를 *모든 사용자* 에게 공유하고 싶지만 예기치 못한 무단 공유가 우려되는 경우, 다른 옵션 중 하나를 기본값으로 고려하세요. 이 링크 유형은 **모든 사용자** 와 공유할 수 있도록 사용 설정한 경우에만 사용할 수 있습니다.
- **조직 내 사용자만** - 대부분의 파일 및 폴더 공유가 조직 내부 사용자와 공유될 것으로 예상되는 경우 이 옵션을 선택합니다.
- **특정 사용자** - 게스트와 많은 파일 및 폴더 공유를 할 것으로 예상되는 경우 이 옵션을 고려하세요. 이러한 유형의 링크는 게스트와 함께 작동하며 인증을 요구합니다.
 
![SharePoint 조직 수준 파일 및 폴더 공유 설정 스크린샷.](../media/sharepoint-organization-files-folders-sharing-settings.png)


조직 수준의 SharePoint 설정 OneDrive 설정하려면

1. SharePoint 관리 센터의 공유 페이지로 이동합니다.
2. **파일 및 폴더 링크** 에서 사용하려는 기본 공유 링크를 선택합니다.
3. 변경한 내용이 있으면 **저장** 을 클릭합니다.

공유 링크에 대한 사용 권한을 설정하려면 기본적으로 링크 공유에 대해 선택된 사용 권한 **선택에서.**

1. **확인되지** 않은 사용자가 파일 및 폴더를 변경하지 못하게 하려는 경우 보기를 선택합니다.
2. **확인되지** 않은 사용자가 파일 및 폴더를 변경할 수 있도록 허용하려면 편집을 선택합니다.

위의 두 가지 사전 해제 옵션은 게스트/외부 사용자뿐만 아니라 내부 사용자에도 적용할 수 있습니다. 선택하는 권한 옵션은 자체 재량에 따라 결정됩니다.

모든 사용자와 공유를 허용하는 링크에 대한 사용 권한을 설정하려면

1. 이러한 링크 **아래에서 하위** 창, 
    1. 파일 **드롭다운** 목록에서 
        - 확인되지 **않은** 사용자가 파일을 변경할 수 있도록 허용하려면 보기 및 편집을 선택합니다.
        - **확인되지** 않은 사용자가 파일을 변경하지 못하게 하려는 경우 보기를 선택합니다.
    2. 폴더 **드롭다운** 목록에서
        - 확인되지 **않은 사용자가** 폴더를 변경할 수 있도록 허용하려면 보기, 편집 및 업로드를 선택합니다.
        - **확인되지** 않은 사용자가 폴더를 변경하지 못하게 하려는 경우 보기를 선택합니다.

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 사이트 수준 공유 설정

SharePoint 사이트에 있는 파일 및 폴더를 공유하는 경우 해당 사이트의 사이트 수준 공유 설정도 확인해야 합니다.

![SharePoint 사이트 외부 공유 설정 스크린샷.](../media/sharepoint-site-external-sharing-settings.png)

사이트 수준 공유 설정을 설정하려면

1. SharePoint 관리 센터의 왼쪽 탐색 창에서 **사이트** 를 확장하고 **활성 사이트** 를 클릭합니다.
2. 게스트와 파일 및 폴더를 공유할 사이트를 선택합니다.
3. 선택한 사이트가 있는 행을 마우스 오른쪽 단추로 스크롤하고 외부 공유 열에서 아무 **곳이나** 클릭합니다.
4. 팝업 페이지에서 정책 **탭을** 클릭합니다.
5. 외부 공유 **창에서** 편집을 **클릭합니다.**
6. 공유가 **모든 사용자** 또는 **새 게스트 및 기존 게스트** 로 설정되었는지 확인합니다.
7. 변경한 내용이 있으면 **저장** 을 클릭합니다.

## <a name="invite-users"></a>사용자 초대하기

이제 게스트 공유 설정이 구성됩니다. 따라서 사용자는 이제 조직 외부의 사용자와 파일 및 폴더를 공유할 수 있습니다. 자세한 [OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) 파일 및 폴더 공유 및 SharePoint 파일 또는 폴더 [공유를](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) 참조하세요.

## <a name="see-also"></a>참고 항목

[인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례](best-practices-anonymous-sharing.md)

[게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한](share-limit-accidental-exposure.md)

[Azure AD B2B와 SharePoint 및 OneDrive의 통합(미리 보기)](/sharepoint/sharepoint-azureb2b-integration-preview)