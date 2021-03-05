---
title: 보안 격리를 사용하여 팀 구성하기
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: 보안을 위한 고유한 민감도 레이블이 있는 팀을 만드는 방법을 알아봅니다.
ms.openlocfilehash: 5ddd42f9e2f2779ca6bf864554140a3f18d2cdea
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405705"
---
# <a name="configure-a-team-with-security-isolation"></a>보안 격리를 사용하여 팀 구성하기

이 문서에서는 Microsoft Teams에서 비공개 팀을 구성하는 데 필요한 사항과 단계를 제공하고 팀 구성원만 암호를 해독할 수 있도록 고유한 민감도 레이블을 사용하여 파일을 암호화하는 방법을 설명합니다.

개인 액세스를 넘어서, 이 문서에서는 높은 규제 대상 데이터를 저장하는 데 필요한 추가 보안을 위해 팀 채널의 **파일** 섹션에서 액세스할 수 있는 연결된 SharePoint 사이트를 구성하는 방법을 설명합니다.

보안 격리 팀을 위한 구성 요소는 다음과 같습니다.

- 비공개 팀
- 팀의 연결된 SharePoint 사이트에 대한 추가 보안 기능은 다음과 같습니다.
  - 사이트 구성원이 다른 사용자와 사이트를 공유하지 못하도록 합니다.
  - 사이트의 구성원 이외의 사용자가 사이트 액세스 권한을 요청하지 못하도록 합니다.
- 이 팀에 대한 민감도 레이블은 다음과 같은 특징이 있습니다.
    - 관리되지 않는 장치에서 SharePoint 콘텐츠에 액세스하지 못하도록 방지합니다.
    - 요구 사항에 따라 팀에 게스트 액세스를 허용하거나 거부합니다.
    - 레이블이 적용된 문서를 암호화합니다.

> [!IMPORTANT]
> 이 문서의 단계를 진행하기 전에 [Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에서 콘텐츠를 보호할 수 있도록 민감도 레이블](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)을 사용하도록 설정했는지 확인하세요.

이 비디오를 시청하고 배포 프로세스에 대한 개요를 확인하세요.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a>이 시나리오에 대한 1페이지 요약을 보려면 [보안 격리 포스터를 사용한 Microsoft Teams를 참조하세요](../downloads/team-security-isolation-poster.pdf).

[![보안 격리를 사용하여 Microsoft Teams 구성하기](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)

이 포스터를 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf)나 [PowerPoint](https://download.microsoft.com/download/8/0/5/8057fc16-c044-40b6-a652-7ed555ba2895/team-security-isolation-poster.pptx) 형식으로 다운로드할 수 있고 편지형, 법률형, 타블로이드(11 x 17) 크기 용지에 인쇄할 수도 있습니다.

[이 지침](team-security-isolation-dev-test.md)을 사용해서 본인 테스트 랩에서 이 구성을 시도해 보세요.

Contoso Corporation이 극비 프로젝트에 보안 팀을 사용한 방법을 [이 사례 연구](contoso-team-for-top-secret-project.md)에서 확인해 보세요.

## <a name="initial-protections"></a>초기 보호

팀과 기본 SharePoint 사이트에 대한 액세스를 보호하려면 다음과 같은 모범 사례를 검토하세요.
- [ID 및 장치 액세스 정책](../security/office-365-security/identity-access-policies.md)
- [SharePoint Online 액세스 정책](../security/office-365-security/sharepoint-file-access-policies.md)
- [기준 보호를 사용하여 팀 배치하기](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a>게스트 공유

업무 특성에 따라 이 팀에서 게스트 공유 기능을 사용하거나 사용하지 않을 수 있습니다. 팀에서 조직 외부의 사용자와 공동 작업을 수행하려는 경우에는 게스트 공유를 사용하세요. 

게스트와 안전하게 공유하는 방법에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [보안 게스트 공유 환경 만들기](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

게스트 공유를 허용하거나 차단하기 위해 나중에 설명할 팀의 민감도 레이블과 연결된 SharePoint 사이트의 사이트 수준 공유 제어를 조합해서 사용합니다.

## <a name="create-a-private-team"></a>비공개 팀 만들기

이 팀을 위해 특별히 민감도 레이블을 만들고 있으므로 다음 단계는 팀을 만드는 것입니다. 기존 팀이 있는 경우 기존 팀을 사용할 수 있습니다.

중요한 정보를 위해 팀을 만들려면
1. Teams에서 앱 왼쪽에 있는 **Teams** 를 클릭한 다음, 팀 목록 아래에서 **팀 참가 또는 만들기** 를 클릭합니다.
2. **팀 만들기** 를 클릭합니다(첫 번째 카드, 왼쪽 위 모서리).
3. **처음부터 팀 만들기** 를 선택합니다.
4. **민감도** 목록에서 기본값을 유지합니다.
5. **개인 정보 보호** 에서 **비공개** 를 클릭합니다.
6. 중요한 프로젝트와 관련된 팀의 이름을 입력합니다. 예를 들어 **프로젝트 Saturn** 이 있습니다.
7. **만들기** 를 클릭합니다.
8. 팀에 사용자를 추가한 다음 **닫기** 를 클릭합니다.

## <a name="private-channel-settings"></a>비공개 채널 설정

비공개 채널 만들기를 팀 소유자로 제한하는 것이 좋습니다.

비공개 채널 만들기를 제한하려면
1. 팀에서 **추가 옵션** 을 클릭한 다음 **팀 관리** 를 클릭합니다.
2. **설정** 탭에서 **구성원 사용 권한** 을 확장합니다.
3. **구성원이 비공개 채널을 만들 수 있도록 허용** 확인란을 선택 취소합니다.

[팀 정책](https://docs.microsoft.com/MicrosoftTeams/teams-policies)을 사용하여 비공개 채널을 만들 수 있는 사용자를 제어할 수도 있습니다.

## <a name="create-a-sensitivity-label"></a>민감도 레이블 만들기

보안 격리를 위해 팀을 구성하기 위해 이 팀을 위해 특별히 만든 민감도 레이블을 사용합니다. 이 레이블은 팀 수준에서 게스트 공유를 제어하고 관리되지 않는 장치에서의 액세스를 차단하는 데 사용됩니다. 팀 소유자와 구성원만 열 수 있도록 팀의 개별 파일을 분류하고 암호화하는 데도 사용할 수 있습니다.

암호화된 문서를 볼 수 있지만 편집할 수는 없는 내부 파트너 또는 관련자 그룹이 있다면 보기 전용 권한을 사용하여 레이블에 해당 사용자를 추가할 수 있습니다. 그런 다음 독자 권한을 사용하여 팀의 SharePoint 사이트에 이러한 사용자를 추가할 수 있으며, 해당 사용자는 문서가 보관되는 사이트에 읽기 전용 권한으로 액세스할 수 있지만 팀 자체에는 액세스할 수 없습니다.


민감도 레이블을 만들려면
1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.
2. **솔루션** 에서 **정보 보호** 를 클릭합니다.
3. **레이블 만들기** 를 클릭합니다.
4. 레이블에 이름을 지정합니다. 함께 사용할 팀의 이름을 따라 이름을 짓는 것을 권장합니다.
5. 표시 이름과 설명을 추가하고 **다음** 을 클릭합니다.
6. **이 레이블에 대한 범위 정의 페이지** 에서 **파일 및 전자 메일** 과 **그룹 및 사이트** 를 선택하고 **다음** 을 클릭합니다.
7. **파일 및 전자 메일에 대한 보호 설정 선택** 페이지에서 **파일 및 전자 메일 암호화** 를 선택하고 **다음** 을 클릭합니다.
8. **암호화** 페이지에서 **암호화 설정 구성** 을 선택합니다.
9. **사용자 또는 그룹 추가** 를 클릭하고, 만든 팀을 선택한 다음, **추가** 를 클릭합니다.
10. **사용 권한 선택** 을 클릭합니다.
11. 드롭다운 목록에서 **공동 작성** 을 선택한 다음 **저장** 을 클릭합니다.
12. 레이블이 있는 파일에 읽기 전용 권한이 있는 사용자 또는 그룹 포함하기:
    1. **사용 권한 할당** 을 클릭합니다.
    1. **사용자 또는 그룹 추가** 를 클릭하고, 추가하려는 사용자 또는 그룹을 선택한 다음, **추가** 를 클릭합니다.
    1. **사용 권한 선택** 을 클릭합니다.
    1. 드롭다운 목록에서 **뷰어** 를 선택한 다음 **저장** 을 클릭합니다.
13.  **저장** 을 클릭한 다음 **다음** 을 클릭합니다.
14. *파일 및 전자 메일에 자동 레이블 지정** 페이지에서 **다음** 을 클릭합니다.
15. **그룹 및 사이트에 대한 보호 설정 정의** 페이지에서 **개인 정보 및 외부 사용자 액세스 설정** 과 **장치 액세스 및 외부 공유 설정** 을 선택 하고 **다음** 을 클릭합니다.
16. **개인 정보 및 외부 사용자 액세스 설정 정의** 페이지의 **개인 정보** 에서 **개인 정보 보호** 옵션을 선택합니다.
17. 게스트 액세스를 허용하려면 **외부 사용자 액세스** 에서 **Microsoft 365 그룹 소유자가 조직 외부의 사용자를 그룹에 게스트로 추가하도록 허용** 을 선택합니다.
18. **다음** 을 클릭합니다.
19. **외부 공유 및 장치 액세스 설정 정의** 페이지에서 **레이블이 지정된 SharePoint 사이트에서 외부 공유를 제어** 를 선택합니다.
20. **콘텐츠를 함께 공유할 수 있습니다** 에서 게스트 액세스를 허용하는 경우에는 **신규 및 기존의 게스트** 를 선택하고, 그렇지 않은 경우 **조직에 있는 사용자만** 을 선택합니다.
21. **관리되지 않는 장치** 에서 **액세스 차단** 을 선택합니다.
22. **다음** 을 클릭합니다.
23. **Office 앱에 대한 자동 레이블 지정** 페이지에서 **다음** 을 클릭합니다.
24. **레이블 만들기** 를 클릭한 다음 **완료** 를 클릭합니다.

레이블을 만든 후에는 레이블을 사용할 사용자에게 게시해야 합니다. 이 경우 팀의 사용자만 레이블을 사용할 수 있도록 설정합니다.

민감도 레이블을 게시하려면
1. Microsoft 365 규정 준수 센터의 **정보 보호** 페이지에서 **레이블 정책** 탭을 선택합니다.
2. **레이블 게시** 를 클릭합니다.
3. **민감도 레이블을 게시하도록 선택** 페이지에서 **민감도 레이블을 게시하도록 선택** 을 클릭합니다.
4. 만든 레이블을 선택한 다음 **추가** 를 클릭합니다.
5. **다음** 을 클릭합니다.
6. 사용자 및 그룹에 게시 페이지에서 **사용자 및 그룹 선택** 을 클릭합니다.
7. **추가** 를 클릭한 다음 만든 팀을 선택합니다.
8. **추가** 를 클릭한 다음 **완료** 를 클릭합니다.
9. **다음** 을 클릭합니다.
10. 정책 설정 페이지에서 **사용자가 레이블이나 하위 분류 레이블을 제거하려면 정당성을 제공해야 함** 확인란을 선택한 후 **다음** 을 클릭합니다.
11. 정책 이름을 입력한 후 **다음** 을 클릭합니다.
12. **제출** 을 클릭한 다음 **완료** 를 클릭합니다.

## <a name="apply-the-label-to-the-team"></a>팀에 레이블 적용하기

레이블을 게시한 후에 게스트 공유 및 관리되는 장치 설정을 적용하려면 팀에 레이블을 적용해야 합니다. SharePoint 관리 센터에서 이 작업을 수행합니다. 레이블을 게시한 후 사용할 수 있을 때까지 다소 시간이 걸릴 수 있습니다.

민감도 레이블을 적용하려면
1. [SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.
2. **사이트** 에서 **활성 사이트** 를 클릭합니다.
3. 팀과 연결된 사이트를 클릭합니다.
4. **정책** 탭의 **민감도** 에서 **편집** 을 클릭합니다.
5. 만든 레이블을 선택한 다음 **저장** 을 클릭합니다.

## <a name="sharepoint-settings"></a>SharePoint 설정

SharePoint에서 수행해야 하는 세 단계는 다음과 같습니다.

- SharePoint 관리 센터에서 사이트에 대한 게스트 공유 설정을 업데이트하여 레이블을 만들 때 선택한 내용과 맞게 설정하고, 기본 공유 링크를 *기존 액세스가 있는 사용자* 로 업데이트합니다.
- 구성원이 파일, 폴더 또는 사이트를 공유하지 못하도록 사이트의 사이트 공유 설정을 업데이트하고 액세스 요청을 해제합니다.
- 뷰어 권한으로 레이블에 사용자 또는 그룹을 추가한 경우에는 읽기 권한을 사용하여 SharePoint 사이트에 사용자 또는 그룹을 추가할 수 있습니다.

### <a name="sharepoint-guest-settings"></a>SharePoint 게스트 공유

레이블을 만들 때 선택한 게스트 공유 설정(팀 구성원에게만 영향을 미침)은 다음과 같이 연결된 SharePoint 사이트의 게스트 공유 설정과 일치해야 합니다.

|레이블 설정|SharePoint 사이트 설정|
|:------------|:----------------------|
|**Office 365 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 허용** 선택됨|**신규 및 기존 게스트**(새 팀의 기본값)|
|**Office 365 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 허용** 선택 안 됨|**조직 내부 사용자만**|

또한 기본 공유 링크 유형을 업데이트하여 의도한 것보다 더 많은 사용자에게 실수로 파일과 폴더를 공유하는 위험을 줄입니다.

사이트 설정을 업데이트하려면
1. [SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.
2. **사이트** 에서 **활성 사이트** 를 클릭합니다.
3. 팀과 연결된 사이트를 클릭합니다.
4. **정책** 탭의 **외부 공유** 에서 **편집** 을 클릭합니다.
5. 중요 레이블을 만들 때 게스트 공유를 허용한 경우 **신규 및 기존 게스트** 가 선택되어 있는지 확인합니다. 레이블을 만들 때 공유를 허용하지 않은 경우 **조직 내부 사용자만** 을 선택합니다.
6. 기본 공유 링크 유형에서 **조직 수준 설정과 동일** 확인란을 선택 취소하고 **기존 액세스가 있는 사용자** 를 선택합니다.
7. **저장** 을 클릭합니다.

#### <a name="private-channels"></a>비공개 채널

팀에 비공개 채널을 추가하면 각 비공개 채널이 기본 공유 설정을 포함하는 새 SharePoint 사이트를 만듭니다. 이러한 사이트는 SharePoint 관리 센터에 표시되지 않으므로 다음 매개 변수와 함께 [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet을 사용하여 게스트 공유 설정을 업데이트해야 합니다.

- 게스트 공유를 해제하려면 `-SharingCapability Disabled`(기본적으로 켜져 있음)
- 기본 공유 링크를 *특정 사용자* 로 변경하려면 `-DefaultSharingLinkType Internal`

팀에서 비공개 채널을 사용하지 않는 경우 팀 구성원이 [팀 설정](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc)의 **구성원 사용 권한** 에서 비공개 채널을 만들 수 있는 기능을 해제하는 것이 좋습니다.

### <a name="site-sharing-settings"></a>사이트 공유 설정

팀 구성원이 아닌 사용자와 SharePoint 사이트를 공유하지 못하게 하도록 이러한 공유는 소유자로 제한합니다. 파일 및 폴더 공유도 팀 소유자로 제한합니다. 이를 통해 파일이 팀 외부의 다른 사용자와 공유될 때마다 소유자가 알 수 있습니다.

소유자 전용 사이트 공유를 구성하려면
1. Teams에서 업데이트하려는 팀의 **일반** 탭으로 이동합니다.
2. 팀의 도구 막대에서 **파일** 을 클릭합니다.
3. 줄임표를 클릭한 다음 **SharePoint에서 열기** 를 클릭합니다.
4. 기본 SharePoint 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한** 을 클릭합니다.
5. 사이트 사용 권한 창에 있는 **공유 설정** 에서 **공유 설정 변경** 을 클릭합니다.
6. **사용 권한 공유** 에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있음** 을 선택한 다음 **저장** 을 클릭합니다.

### <a name="custom-site-permissions"></a>사용자 지정 사이트 사용 권한

뷰어 권한이 있는 사용자를 민감도 레이블에 추가한 경우에는 해당 사용자를 파일에 쉽게 액세스할 수 있도록 읽기 권한으로 SharePoint 사이트에 추가할 수 있습니다.

사이트에 사용자를 추가하려면
1. 사이트에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한** 을 클릭합니다.
2. **사용자 초대** 를 클릭한 다음 **사이트만 공유** 를 클릭합니다.
3. 초대하려는 사용자 및 그룹의 이름을 입력합니다.
4. 추가하는 각 사용자 또는 그룹의 사용 권한을 **편집** 에서 **읽기** 로 변경합니다.
5. 해당 사이트에 대한 링크가 포함된 전자 메일을 보낼 것인지 선택합니다.
6. **추가** 를 클릭합니다.

## <a name="additional-protections"></a>추가 보호

Microsoft 365에서는 콘텐츠를 보호하기 위한 추가 방법을 제공합니다. 다음 옵션이 조직의 보안을 개선하는 데 도움이 되는지 고려해 보세요.

- 게스트 사용자가 [사용 약관](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)에 동의하도록 합니다.
- 게스트 사용자에 대한 [세션 시간 초과 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)을 구성합니다.
- [중요한 정보 유형](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)을 만들고 [데이터 손실 방지](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)를 사용하여 중요한 정보에 액세스하는 방법에 대한 정책을 설정합니다.
- [Azure Active Directory 액세스](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) 검토를 사용하여 팀 액세스 및 구성원을 주기적으로 검토합니다.

## <a name="drive-user-adoption-for-team-members"></a>팀 구성원을 위한 사용자 채택 유도하기

팀이 준비되면 팀 구성원에게 팀과 추가 보안 기능의 채택을 유도할 시점입니다.

### <a name="train-your-users"></a>사용자 교육하기

팀의 구성원은 채팅, 모임 및 기타 앱을 포함하여 팀과 모든 리소스에 액세스할 수 있습니다. 채널의 **파일** 섹션에서 파일에 대한 작업을 하는 경우, 팀의 구성원은 만든 파일에 민감도 레이블을 할당해야 합니다.

레이블이 파일에 적용되면 암호화됩니다. 팀의 구성원은 실시간으로 파일을 열고 공동 작업할 수 있습니다. 파일이 사이트를 떠나 악의적인 사용자에게 전달되는 경우, 파일을 열고 콘텐츠를 보려면 팀의 구성원인 사용자 계정의 자격 증명을 제공해야 합니다. 

팀 구성원 교육하기:

- 채팅, 모임, 파일 및 SharePoint 사이트의 기타 리소스를 위한 새 팀 사용의 중요성 및 높은 규제 대상의 데이터 유출 결과(예: 법적 영향, 규제 벌금, 랜섬웨어 또는 경쟁적 우위 박탈)
- 팀에 액세스 하는 방법
- 사이트에서 새 파일을 만들고 로컬에 저장된 새 파일을 업로드하는 방법
- 팀에 대한 올바른 민감도 레이블을 사용하여 파일에 레이블을 할당하는 방법
- 파일이 사이트 외부로 유출된 경우에도 레이블이 파일을 보호하는 방법

이 교육에는 팀 구성원이 이러한 기능과 해당 결과를 경험해볼 수 있도록 하기 위한 실무 위주의 연습이 포함되어 있습니다.

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a>정기적인 사용 현황 검토 및 팀 구성원 피드백 처리하기

교육 후 몇 주 안에:

- 팀 구성원의 피드백을 신속하게 처리하고 정책과 구성을 세부적으로 조정합니다.
- 팀의 사용 현황을 분석하고 예상 사용 현황과 비교합니다.
- 높은 규제 대상 파일에 적절한 민감도 레이블이 지정되었는지 확인합니다. SharePoint에서 폴더를 보고 **열 추가** 의 **열 표시/숨기기** 옵션을 통해 **민감도** 열을 추가하여 레이블이 할당된 파일을 볼 수 있습니다.

필요에 따라 사용자를 재교육합니다.

## <a name="see-also"></a>기타 참고 항목

[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)
