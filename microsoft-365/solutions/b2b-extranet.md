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
description: 파트너 조직의 관리되는 게스트를 사용하여 B2B 엑스트라넷 사이트 또는 팀을 만드는 방법을 자세히 알아보고
ms.openlocfilehash: cfb7cc4310cb83f9ce7761c95f021724b7d75faf
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613599"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>관리 대상 게스트와 B2B 엑스트라넷 작성

[Azure Active Directory 권리](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) 관리에서 B2B 엑스트라넷을 만들어 Azure Active Directory를 사용하는 파트너 조직과 공동 작업을 할 수 있습니다. 이렇게 하면 사용자가 엑스트라넷 사이트 또는 팀에 자체 등록하고 승인 워크플로를 통해 액세스 권한을 받을 수 있습니다.

파트너 조직은 이러한 공동 작업용 리소스를 공유하여 게스트를 최종적으로 유지 관리 및 승인하고 IT 부서의 부담을 줄이고 공동 작업 계약에 가장 익숙한 사용자가 사용자 액세스를 관리할 수 있도록 지원할 수 있습니다.

이 문서에서는 셀프 서비스 액세스 등록 모델을 통해 파트너 조직과 공유할 수 있는 리소스 패키지(이 경우 사이트 또는 팀)를 만드는 단계를 단계로 진행합니다. 

시작하기 전에 파트너 조직과 공유할 사이트 또는 팀을 만들고 게스트 공유를 사용하도록 설정해야 합니다. 자세한 [내용은 사이트의 게스트와](collaborate-in-site.md) [](collaborate-as-team.md) 공동 작업 또는 팀의 게스트와 공동 작업하기를 참조하세요. 게스트와 공동 작업할 때 거버넌스 정책을 유지 관리하는 데 사용할 수 있는 보안 및 규정 준수 기능에 대한 정보는 보안 게스트 공유 환경 만들기를 검토하는 것이 좋습니다. [](create-secure-guest-sharing-environment.md)

## <a name="license-requirements"></a>라이선스 요구 사항

이 기능을 사용하려면 Azure AD Premium P2 라이선스가 필요합니다. 

Azure Germany 및 Azure China 21Vianet과 같은 특수 클라우드는 현재 사용할 수 없습니다.

## <a name="video-demonstration"></a>동영상 데모

이 비디오에서는 이 문서에서 다루는 절차를 보여 제공합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>파트너 조직 연결

파트너 조직에서 게스트를 초대하려면 Azure Active Directory에서 파트너의 도메인을 연결된 조직으로 추가해야 합니다.

연결된 조직을 추가하려면
1. [Azure Active Directory에서](https://aad.portal.azure.com)ID 거버넌스를 **클릭합니다.**
2. 연결된 **조직을 클릭합니다.**
4. 연결된 **조직 추가를 클릭합니다.**
5. 조직의 이름과 설명을 입력하고 **다음: 디렉터리 + 도메인을 클릭합니다.**
6. 디렉터리 **+ 도메인 추가를 클릭합니다.**
7. 연결할 조직의 도메인을 입력하고 추가를 **클릭합니다.**
8. **Connect(연결)를** 클릭한 **다음: 스폰서(Sponsors)를 클릭합니다.**
9. 게스트에 대한 액세스를 승인할 조직 또는 연결하려는 조직의 사람을 추가합니다.
10. 다음을 **클릭합니다. 검토 + 만들기.**
11. 선택한 설정을 검토하고 만들기를 **클릭합니다.**

    ![Azure Active Directory의 연결된 조직 페이지 스크린샷](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>공유할 리소스 선택

파트너 조직과 공유할 리소스를 선택하는 첫 번째 단계는 해당 리소스를 포함할 카탈로그를 만드는 것입니다.

카탈로그를 만들 경우
1. [Azure Active Directory에서](https://aad.portal.azure.com)ID 거버넌스를 **클릭합니다.**
2. 카탈로그를 **클릭합니다.**
3. 새 **카탈로그를 클릭합니다.**
4. 카탈로그의 이름과 설명을 입력하고 외부  사용자에 대해 **사용** 및 사용이 모두 예로 설정되어 있도록 **합니다.**
5. **만들기** 를 클릭합니다.

   ![Azure Active Directory ID 거버넌스 카탈로그 페이지의 스크린샷](../media/identity-governance-catalogs.png)

카탈로그를 만든 후 파트너 조직과 공유할 SharePoint 사이트 또는 팀을 추가합니다.

카탈로그에 리소스를 추가하는 경우
1. Azure AD ID 거버넌스에서 카탈로그를 클릭한 다음 리소스를 추가할 카탈로그를 클릭합니다. 
2. 자원을 **클릭한** 다음 리소스 **추가를 클릭합니다.**
3. 엑스트라넷에 포함할 팀 또는 SharePoint 사이트를 선택하고 추가를 **클릭합니다.**

   ![Azure Active Directory ID 거버넌스 카탈로그 리소스 페이지의 스크린샷](../media/identity-governance-catalog-resource.png)

공유할 리소스를 정의한 다음에는 파트너 사용자에게 부여되는 액세스 유형과 액세스를 요청하는 새 파트너 사용자의 승인 프로세스를 정의하는 액세스 패키지를 만들어야 합니다.

액세스 패키지를 만들 경우
1. Azure AD ID 거버넌스에서 카탈로그를 클릭한 다음 액세스 패키지를 만들 카탈로그를 클릭합니다. 
2. Access **패키지를** 클릭한 다음 새 액세스 **패키지를 클릭합니다.**
3. 액세스 패키지의 이름과 설명을 입력하고 다음: 리소스 **역할을 클릭합니다.**
4. 카탈로그에서 엑스트라넷에 사용할 리소스를 선택합니다.
5. 각 리소스의 **역할** 열에서 엑스트라넷을 사용하는 게스트에게 부여할 사용자 역할을 선택 합니다.
6. 다음: **요청**.
7. 액세스를 **요청할 수** 있는 사용자 아래에서 디렉터리에 없는 **사용자에 대해 선택하십시오.**
8. 연결된 **특정** 조직 옵션이 선택되어 있는지 확인한 다음 추가를 **클릭합니다.**
9. 앞서 추가한 연결된 조직을 선택하고 **선택을 클릭합니다.**
10. 승인 **아래에서** **승인 필요를** 위해 **예를 선택 합니다.**
11. 첫 **번째 승인자에서** 앞서 추가한 스폰서 중 하나를 선택하거나 특정 사용자를 선택합니다.
12. Fallback **추가를 클릭하고** 폴백 승인을 선택합니다.
13. **사용에서** 예를 **선택**
14. 다음: **수명 주기를 클릭합니다.**
15. 사용할 만료 및 액세스 검토 설정을 선택하고 **다음: 검토 + 만들기를 클릭합니다.**
16. 설정을 검토하고 만들기를 **클릭합니다.**

    ![Azure Active Directory ID 거버넌스의 액세스 패키지 화면 스크린샷](../media/identity-governance-access-packages.png)

대규모 조직과 협력하는 경우 액세스 패키지를 숨길 수 있습니다. 패키지가 숨겨져 있는 경우 파트너 조직의 사용자는 내 *액세스* 포털에 패키지를 볼 수 없습니다. 대신 패키지에 등록하려면 직접 링크를 전송해야 합니다. 액세스 패키지를 숨기면 부적절한 액세스 요청의 수가 줄어들고 파트너 조직의 포털에서 사용 가능한 액세스 패키지를 구성하는 데 도움이 될 수 있습니다.

액세스 패키지를 숨김으로 설정
1. Azure AD ID 거버넌스에서 **Access** 패키지를 클릭한 다음 액세스 패키지를 클릭합니다.
2. 개요 **페이지에서** 편집을 **클릭합니다.**
3. **속성에서** **숨김에 예를** **선택한** 다음 저장을 **클릭합니다.**

   ![액세스 패키지 속성 편집 화면 스크린샷](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>파트너 사용자 초대

액세스 패키지를 숨김으로 설정한 경우 사이트 또는 팀에 대한 액세스를 요청할 수 있도록 파트너 조직으로 직접 링크를 보내야 합니다.

액세스 포털 링크를 찾으면
1. Azure AD ID 거버넌스에서 **Access** 패키지를 클릭한 다음 액세스 패키지를 클릭합니다.
2. 개요 **페이지에서** 내  Access 포털 링크의 클립보드에 복사 **링크를 클릭합니다.**

   ![액세스 포털 링크가 있는 액세스 패키지 속성의 스크린샷](../media/identity-governance-access-portal-link.png)

링크를 복사한 후 파트너 조직의 담당자와 링크를 공유할 수 있으며 공동 작업 팀의 사용자에게 링크를 보낼 수 있습니다.

## <a name="see-also"></a>참고 항목

[보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md)
