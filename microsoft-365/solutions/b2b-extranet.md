---
title: 관리 대상 게스트와 B2B 엑스트라넷 작성
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
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: 파트너 조직의 관리되는 게스트를 사용하여 B2B 엑스트라넷 사이트 또는 팀을 만드는 방법을 학습합니다.
ms.openlocfilehash: 7e3ddf12473095b0a7ac91ded01256e77c299ddf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185515"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>관리 대상 게스트와 B2B 엑스트라넷 작성

권한 [부여](/azure/active-directory/governance/entitlement-management-overview) 관리에서 Azure Active Directory 사용하여 B2B 엑스트라넷을 만들어 사용자 자격 관리를 사용하는 파트너 조직과 공동 작업을 Azure Active Directory. 이를 통해 사용자는 엑스트라넷 사이트 또는 팀에 자체 등록하고 승인 워크플로를 통해 액세스 권한을 받을 수 있습니다.

파트너 조직은 공동 작업을 위해 리소스를 공유하는 이 방법을 통해 게스트를 끝에 유지 관리하고 승인하여 IT 부서의 부담을 줄이고 공동 작업 계약에 가장 익숙한 사용자가 사용자 액세스를 관리할 수 있도록 할 수 있습니다.

이 문서에서는 셀프 서비스 액세스 등록 모델을 통해 파트너 조직과 공유할 수 있는 리소스 패키지(이 경우 사이트 또는 팀)를 만드는 단계를 단계로 진행합니다. 

시작하기 전에 파트너 조직과 공유할 사이트 또는 팀을 만들고 게스트 공유를 사용하도록 설정하세요. 자세한 [내용은 사이트에서 게스트와](collaborate-in-site.md) [](collaborate-as-team.md) 공동 작업 또는 팀의 게스트와 공동 작업을 참조하세요. 게스트와 공동 작업할 때 거버넌스 정책을 유지 관리하는 데 사용할 수 있는 보안 및 규정 준수 기능에 대한 정보는 보안 게스트 공유 환경 만들기를 검토하는 것이 좋습니다. [](create-secure-guest-sharing-environment.md)

## <a name="license-requirements"></a>라이선스 요구 사항

이 기능을 사용하려면 라이선스가 Azure AD Premium P2 합니다. 

Azure Germany 및 Azure China 21Vianet과 같은 특수 클라우드는 현재 사용할 수 없습니다.

## <a name="video-demonstration"></a>동영상 데모

이 비디오에서는 이 문서에서 다루는 절차를 보여 제공합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>커넥트 조직 구성

파트너 조직에서 게스트를 초대하려면 파트너의 도메인을 파트너의 도메인에 연결된 조직으로 Azure Active Directory.

연결된 조직을 추가하려면
1. 에서 [Azure Active Directory](https://aad.portal.azure.com)ID **거버넌스 를 클릭합니다.**
2. 연결된 **조직 을 클릭합니다.**
4. 연결된 **조직 추가를 클릭합니다.**
5. 조직의 이름과 설명을 입력하고 **다음: 디렉터리 + 도메인 을 클릭합니다.**
6. 디렉터리 **+ 도메인 추가를 클릭합니다.**
7. 연결할 조직의 도메인을 입력한 다음 추가를 **클릭합니다.**
8. 를 **커넥트** **다음: 스폰서 를 클릭합니다.**
9. 게스트에 대한 액세스를 승인할 사용자에 연결하려는 조직 또는 조직의 사람을 추가합니다.
10. **다음: 검토 + 만들기** 를 클릭합니다.
11. 선택한 설정을 검토하고 만들기를 **클릭합니다.**

    ![조직의 연결된 조직 페이지 Azure Active Directory.](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>공유할 리소스 선택

파트너 조직과 공유할 리소스를 선택하는 첫 번째 단계는 포함할 카탈로그를 만드는 것입니다.

카탈로그를 만들면
1. 에서 [Azure Active Directory](https://aad.portal.azure.com)ID **거버넌스 를 클릭합니다.**
2. 카탈로그를 **클릭합니다.**
3. 새 **카탈로그 를 클릭합니다.**
4. 카탈로그의 이름과 설명을 입력하고 외부  사용자에 대해 **사용** 및 사용이 모두 예로 설정되어 있도록 **합니다.**
5. **만들기** 를 클릭합니다.

   ![ID 거버넌스에 있는 카탈로그 Azure Active Directory 스크린샷.](../media/identity-governance-catalogs.png)

카탈로그를 만든 후 파트너 SharePoint 공유할 사이트 또는 팀을 추가합니다.

카탈로그에 리소스를 추가하는 경우
1. Azure AD ID 거버넌스에서 카탈로그를 **클릭한** 다음 리소스를 추가할 카탈로그를 클릭합니다.
2. 리소스를 **클릭한** 다음 리소스 **추가 를 클릭합니다.**
3. 엑스트라넷에 포함할 팀 또는 SharePoint 사이트를 선택한 다음 추가를 **클릭합니다.**

   ![ID 거버넌스에 있는 카탈로그 리소스 Azure Active Directory 스크린샷.](../media/identity-governance-catalog-resource.png)

공유할 리소스를 정의한 다음에는 파트너 사용자에게 부여되는 액세스 유형과 액세스를 요청하는 새 파트너 사용자의 승인 프로세스를 정의하는 액세스 패키지를 만들어야 합니다.

액세스 패키지를 만들 수 있습니다.
1. Azure AD ID 거버넌스에서 카탈로그를 클릭한 다음 액세스 패키지를 만들 카탈로그를 클릭합니다. 
2. Access **패키지 를** 클릭한 다음 새 액세스 패키지 **를 클릭합니다.**
3. 액세스 패키지의 이름과 설명을 입력하고 다음: 리소스 **역할을 클릭합니다.**
4. 카탈로그에서 엑스트라넷에 사용할 리소스를 선택합니다.
5. 각 리소스의 **역할** 열에서 엑스트라넷을 사용하는 게스트에게 부여할 사용자 역할을 선택 합니다.
6. 다음: **요청 을 클릭합니다.**
7. 액세스를 **요청할 수 있는 사용자 아래에서** 디렉터리에 없는 사용자 **를 선택하십시오.**
8. 특정 연결된 조직 **옵션이** 선택되어 있는지 확인한 다음 추가를 **클릭합니다.**
9. 앞에서 추가한 연결된 조직을 선택한 다음 **선택을 클릭합니다.**
10. 승인 **아래에서** **승인 필요 에** 대해 예를 선택 **합니다.**
11. 첫 **번째 승인자에서** 앞서 추가한 스폰서 중 하나를 선택하거나 특정 사용자를 선택합니다.
12. Add **fallback(변경 추가)을** 클릭하고 fallback approver(변경 승인자)를 선택합니다.
13. 사용 **에서** 예를 **선택 .**
14. 다음: **수명 주기 를 클릭합니다.**
15. 사용할 만료 및 액세스 검토 설정을 선택하고 **다음: 검토 + 만들기를 클릭합니다.**
16. 설정을 검토하고 만들기를 **클릭합니다.**

    ![ID 거버넌스에 있는 액세스 패키지 Azure Active Directory 스크린샷.](../media/identity-governance-access-packages.png)

대규모 조직과 파트너가 될 경우 액세스 패키지를 숨길 수 있습니다. 패키지가 숨겨져 있는 경우 파트너 조직의 사용자는 내 액세스 포털에 패키지를 볼 *수* 없습니다. 대신 패키지에 등록하려면 직접 링크를 전송해야 합니다. 액세스 패키지를 숨기면 부적절한 액세스 요청 수가 줄어들고 파트너 조직의 포털에서 사용 가능한 액세스 패키지를 구성하여 유지하는 데도 도움이 될 수 있습니다.

액세스 패키지를 숨김으로 설정
1. Azure AD ID 거버넌스에서 **Access 패키지를** 클릭한 다음 액세스 패키지를 클릭합니다.
2. 개요 **페이지에서** 편집을 **클릭합니다.**
3. **속성에서** **숨김에 예를** **선택하고** 저장을 **클릭합니다.**

   ![액세스 패키지 속성 편집 화면의 스크린샷.](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>파트너 사용자 초대

액세스 패키지를 숨김으로 설정하는 경우 사이트 또는 팀에 대한 액세스를 요청할 수 있도록 파트너 조직에 직접 링크를 보내야 합니다.

액세스 포털 링크를 찾으면
1. Azure AD ID 거버넌스에서 **Access 패키지를** 클릭한 다음 액세스 패키지를 클릭합니다.
2. 개요 **페이지에서** 내 **액세스** 포털 링크의 클립보드에 복사 **링크를 클릭합니다.**

   ![액세스 포털 링크가 있는 액세스 패키지 속성의 스크린샷.](../media/identity-governance-access-portal-link.png)

링크를 복사한 후 해당 링크를 파트너 조직의 연락처와 공유할 수 있으며 공동 작업 팀의 사용자에게 링크를 보낼 수 있습니다.

## <a name="see-also"></a>참고 항목

[보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md)