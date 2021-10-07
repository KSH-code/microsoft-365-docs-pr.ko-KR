---
title: 콘텐츠 검색에 대한 기능 참조
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
description: 이 게시물은 Microsoft 365 규정 준수 센터의 콘텐츠 검색 eDiscovery 도구에 대한 참조 정보를 포함하며, 콘텐츠 검색 세부 정보를 제공하여 사용자의 이해를 돕습니다.
ms.openlocfilehash: 0688f3119b500f8e11675aa101d92942a3063e8b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175410"
---
# <a name="feature-reference-for-content-search"></a>콘텐츠 검색에 대한 기능 참조

이 문서는 콘텐츠 검색의 특징 및 기능을 설명합니다.

## <a name="content-search-limits"></a>콘텐츠 검색 제한

콘텐츠 검색 기능에 적용되는 제한 사항에 대한 설명을 보려면 [콘텐츠 검색 제한](limits-for-content-search.md)을 참조하세요.

## <a name="building-a-search-query"></a>검색 쿼리 작성

검색 쿼리 작성, 부울 검색 연산자 및 검색 조건 사용, 조직 외부 사용자와 공유되는 중요한 정보 유형 및 콘텐츠 검색에 대한 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.

키워드 목록을 사용하여 검색 쿼리를 만들 때 다음 사항에 유의하세요.

- **키워드 목록 표시** 확인란을 선택한 다음 각 행의 키워드(또는 키워드 문구)가 **OR** 연산자로 연결된 검색어를 만들려면 별도의 행에 각 키워드를 입력해야 합니다. 키워드 상자에 키워드 목록을 붙여넣거나 키워드를 입력한 후 **Enter** 키를 누르면 **OR** 연산자로 연결되지 않습니다. 다음은 키워드 목록을 추가하는 방법의 올바른 예와 잘못된 예입니다.

    **잘못된 예**

    ![목록을 키워드 상자에 붙여넣어 키워드 목록의 서식을 지정하는 잘못된 방법입니다.](../media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)

    **올바른 예**

    ![확인란을 선택한 다음 목록을 붙여넣어 키워드 목록의 서식을 지정하는 올바른 방법입니다.](../media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)

- Excel 파일이나 일반 텍스트 파일에서 키워드나 키워드 구문 목록을 준비한 다음 키워드 목록에 목록을 복사하여 붙여넣을 수도 있습니다. 이렇게 하려면 **키워드 목록 표시** 확인란을 선택해야 합니다. 그런 다음 키워드 목록의 첫 번째 행을 클릭하고 목록을 붙여넣습니다. Excel 또는 텍스트 파일의 각 줄은 키워드 목록의 별도 행에 붙여넣어집니다.

- 키워드 목록을 사용하여 쿼리를 만든 후에는 의도한 것과 일치하는 검색쿼리 구문인지 확인하는 것이 좋습니다. 세부 정보 창의 **쿼리** 아래에 표시된 검색 쿼리에서 키워드는 텍스트 **(c:s)** 로 구분됩니다. 이는 키워드가 **OR** 연산자와 기능상 유사한 논리 연산자로 연결됨을 의미합니다. 마찬가지로 검색 쿼리에 조건이 포함된 경우 키워드와 조건은 텍스트 **(c:c)** 로 구분됩니다. 이는 키워드가 **AND** 연산자와 기능상 유사한 논리 연산자를 사용하여 조건에 연결됨을 의미합니다. 다음은 키워드 목록과 조건을 사용할 때 발생하는 검색 쿼리(세부 정보 창에 표시됨)의 예입니다.

    ![키워드 목록 및 조건을 사용하여 만든 검색 쿼리의 예](../media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)

- 콘텐츠 검색을 실행하면 Microsoft 365에서 검색 쿼리에서 지원되지 않는 문자와 대문자로 표시되지 않은 부울 연산자를 자동으로 확인합니다. 지원되지 않는 문자는 종종 숨겨져 있으며 일반적으로 검색 오류를 발생시키거나 예기치 않은 결과를 반환할 수 있습니다. 검사의 대상이 되는 지원되지 않는 문자에 대한 자세한 내용은 [오류에 대한 콘텐츠 검색 쿼리 확인](check-your-content-search-query-for-errors.md)을 참조하세요.

- 영어가 아닌 문자(예: 중국어 문자)에 대한 키워드가 포함된 검색 쿼리가 있는 경우 **쿼리 언어-국가/지역**![콘텐츠 검색의 쿼리 언어-국가/지역 아이콘](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)을 클릭할 수 있습니다. 그리고 검색에 대한 언어-국가 문화권 코드 값을 선택합니다. 기본 언어/지역은 중립입니다. 콘텐츠 검색에 대해 언어 설정을 변경해야 하는지 어떻게 알 수 있나요? 특정 콘텐츠 위치에 검색 중인 영어 이외의 문자가 포함되어 있지만 검색 결과가 나타나지 않으면 언어 설정이 원인일 수 있습니다.

## <a name="partially-indexed-items"></a>부분적으로 인덱싱된 항목

- 앞서 설명한 것처럼 사서함의 부부분적으로 인덱싱된 항목은 예상 검색 결과에 포함됩니다. SharePoint 및 OneDrive의 부분적으로 인덱싱된 항목은 예상 검색 결과에 포함되지 않습니다. 자세한 내용은 [eDiscovery에서 부분적으로 인덱싱된 항목](partially-indexed-items-in-content-search.md)을 참조하세요.

## <a name="searching-onedrive-accounts"></a>OneDrive 계정 검색

- 조직의 OneDrive 사이트에 대한 URL 목록을 수집하려면 [조직의 모든 OneDrive 위치 목록 만들기](/onedrive/list-onedrive-urls)를 참조하세요. 이 문서의 스크립트는 모든 OneDrive 사이트 목록이 포함된 텍스트 파일을 만듭니다. 이 스크립트를 실행하려면 SharePoint Online 관리 셸을 설치하고 사용해야 합니다. 조직의 MySite 도메인에 대한 URL을 검색하려는 각 OneDrive 사이트 앞에 붙입니다. 이것은 모든 OneDrive 도메인을 포함하는 도메인입니다(예: `https://contoso-my.sharepoint.com`). 사용자의 OneDrive 사이트에 대한 URL의 예는 다음과 같습니다.  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

    드물게 사용자의 UPN(사용자 계정 이름)이 변경되는 경우 해당 OneDrive 위치의 URL이 새 UPN을 통합하도록 변경됩니다. 이 경우 사용자의 새 OneDrive URL을 추가하고 이전 항목을 제거하여 콘텐츠 검색을 수정해야 합니다. 자세한 내용은 [UPN 변경 내용이 OneDrive URL에 미치는 영향](/onedrive/upn-changes)을 참조하세요.

## <a name="searching-microsoft-teams-and-microsoft-365-groups"></a>Microsoft Teams 및 Microsoft 365 그룹 검색

Microsoft 365 그룹 또는 Microsoft Teams와 연결된 사서함을 검색할 수 있습니다. Microsoft Teams는 Microsoft 365 그룹을 기반으로 하기 때문에 유사한 검색이 가능합니다. 두 경우 모두 그룹 또는 팀 사서함만 검색됩니다. 그룹 또는 팀 구성원의 사서함은 검색되지 않습니다. 이를 검색하려면 검색에 구체적으로 이들을 추가해야 합니다.

Microsoft Teams 및 Microsoft 365 그룹에서 콘텐츠를 검색할 때 다음 사항에 유의하세요.

- Teams 및 Microsoft 365 그룹에 있는 콘텐츠를 검색하려면 Teams 또는 그룹과 연결된 사서함과 SharePoint 사이트를 지정해야 합니다.

- 개인 채널의 콘텐츠는 팀 사서함이 아닌 각 사용자의 사서함에 저장됩니다. 개인 채널에서 콘텐츠를 검색하려면 [개인 채널의 eDiscovery](/microsoftteams/ediscovery-investigation#ediscovery-of-private-channels)을 참조하세요.

- Exchange Online에서 **Get-UnifiedGroup** cmdlet을 실행하여 팀 또는 Microsoft 365 그룹의 속성을 볼 수 있습니다. 이는 팀 또는 그룹에 연결된 사이트의 URL을 가져오는 데 적합합니다. 예를 들어, 다음 명령을 실행하면 Senior Leadership Team이라는 Microsoft 365 그룹의 선택된 속성이 표시됩니다.

  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > **Get-UnifiedGroup** cmdlet를 실행하려면 Exchange Online에서 보기 전용 받는 사람 역할을 할당받았거나 보기 전용 받는 사람 역할이 할당된 역할 그룹의 구성원이어야 합니다.

- 사용자의 사서함이 검색될 때 사용자가 구성원인 팀이나 Microsoft 365 그룹은 검색되지 않습니다. 마찬가지로 팀 또는 Microsoft 365 그룹을 검색하면 지정한 그룹 사서함 및 그룹 사이트만 검색됩니다. 그룹 구성원의 사서함 및 비즈니스용 OneDrive 계정은 검색에 명시적으로 추가하지 않는 한 검색되지 않습니다.

- Teams 또는 Microsoft 365 그룹의 구성원 목록을 가져오려면 Microsoft 365 관리 센터의 **홈**\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**그룹**</a> 페이지에서 속성을 볼 수 있습니다. 또는 Exchange Online PowerShell에서 다음 명령을 실행할 수 있습니다.

  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
  ```

    > [!NOTE]
    > **Get-UnifiedGroupLinks** cmdlet를 실행하려면 Exchange Online에서 보기 전용 받는 사람 역할을 할당받았거나 보기 전용 받는 사람 역할이 할당된 역할 그룹의 구성원이어야 합니다.

- 팀 채널의 일부인 대화는 팀과 연결된 사서함에 저장됩니다. 마찬가지로 팀 구성원이 채널에서 공유하는 파일은 팀의 SharePoint 사이트에 저장됩니다. 따라서 채널의 대화 및 파일을 검색하려면 팀 사서함과 SharePoint 사이트를 콘텐츠 위치로 추가해야 합니다.

- 또는 팀의 채팅 목록에 포함된 대화는 채팅에 참여하는 사용자의 Exchange Online 사서함에 저장됩니다. 사용자가 채팅 대화에서 공유하는 파일은 파일을 공유하는 사용자의 비즈니스용 OneDrive 계정에 저장됩니다. 따라서 채팅 목록의 대화와 파일을 검색하려면 개별 사용자 사서함과 비즈니스용 OneDrive 계정을 콘텐츠 위치로 추가해야 합니다.

    > [!NOTE]
    > Exchange 하이브리드 배포에서는 온-프레미스 사서함이 있는 사용자가 Teams 채팅 목록에 포함된 대화에 참여할 수 있습니다. 이 경우 해당 대화의 콘텐츠는 온-프레미스 사서함이 있는 사용자의 클라우드 기반 저장소 영역(*온-프레미스 사용자를 위한 클라우드 기반 사서함* 이라고 함)에 저장되므로 이러한 콘텐츠도 검색할 수 있습니다. 자세한 내용은 [온-프레미스 사용자의 Teams 채팅 데이터 검색](search-cloud-based-mailboxes-for-on-premises-users.md)을 참조하세요.

- 모든 팀 또는 팀 채널에는 메모 작성 및 공동 작업을위한 Wiki가 포함되어 있습니다. Wiki 콘텐츠는 자동으로 .mht 형식의 파일에 저장됩니다. 이 파일은 팀의 SharePoint 사이트에 있는 Teams Wiki Data 문서 라이브러리에 저장됩니다. 콘텐츠 검색 도구를 사용하여 팀의 SharePoint 사이트를 검색할 콘텐츠 위치로 지정하여 Wiki를 검색할 수 있습니다.

    > [!NOTE]
    > Wiki에서 팀 또는 채널을 검색하는 기능(팀의 SharePoint 사이트 검색 시)은 2017년 6월 22일에 릴리스되었습니다. 해당 날짜나 그 이후에 저장되거나 업데이트된 Wiki 페이지를 검색할 수 있습니다. 해당 날짜 이전에 마지막으로 저장되거나 업데이트된 Wiki 페이지는 검색할 수 없습니다.

- Teams 채널의 모임 및 통화에 대한 요약 정보는 모임 또는 전화를 건 사용자의 사서함에도 저장됩니다. 즉, 콘텐츠 검색을 사용하여 이러한 요약 레코드를 검색할 수 있습니다. 요약 정보에는 다음이 포함됩니다.

  - 모임 또는 통화의 날짜, 시작 시간, 종료 시간 및 기간

  - 각 참가자가 모임에 참석하거나 퇴장한 날짜와 시간

  - 음성 메일로 전송된 전화

  - 부재 중 또는 응답되지 않은 통화

  - 두 개의 개별 통화로 표시되는 호출 전송

  모임 및 통화 요약 레코드를 검색할 수 있게 되기까지 최대 8시간이 걸릴 수 있습니다.

  검색 결과에서 모임 요약은 **유형 필드** 에서 **모임** 으로 식별되고 통화 요약은 **통화** 로 식별됩니다. 또한 Teams 채널과 1xN 채팅의 일부인 대화는 **유형** 필드에서 **IM** 으로 식별됩니다.

  ![Teams 모임, 통화 및 1xN 채팅은 유형 필드에서 식별됩니다.](../media/O365-ContentSearch-Teams-MessageKind.png)

   자세한 내용은 [Microsoft Teams에서 통화 및 모임을 위해 eDiscovery 시작하기](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-launches-ediscovery-for-calling-and-meetings/ba-p/210947)를 참조하세요.

- Teams 채널, 1:1 채팅 및 1xN 채팅의 앱에서 생성된 카드 콘텐츠는 편지함에 저장되어 검색할 수 있습니다. *카드* 는 짧은 내용의 UI 컨테이너입니다. 카드는 여러 가지 속성 및 첨부 파일을 가질 수 있으며 카드 작업을 트리거할 수 있는 단추를 포함할 수 있습니다. 자세한 내용은 [카드](/microsoftteams/platform/task-modules-and-cards/what-are-cards)를 참조하세요.

  다른 Teams 콘텐츠와 마찬가지로 카드 콘텐츠가 저장되는 위치는 카드가 사용된 위치를 기준으로 합니다. Teams 채널에 사용되는 카드의 내용은 Teams 그룹 사서함에 저장됩니다. 1:1 및 1xN 채팅의 카드 콘텐츠는 채팅 참가자의 우편함에 저장됩니다.

  카드 내용을 검색하려면 `kind:microsoftteams` 또는 `itemclass:IPM.SkypeTeams.Message` 검색 조건을 사용할 수 있습니다. 검색 결과를 검토할 때 Teams 채널에서 봇에서 생성한 카드 콘텐츠에는 **보낸 사람/작성자** 전자 메일 속성을 `<appname>@teams.microsoft.com`으로 가집니다. 여기서 `appname` 카드 콘텐츠를 생성한 앱의 이름입니다. 사용자가 카드 내용을 생성한 경우 **보낸 사람/작성자** 의 값이 사용자를 식별합니다.

  내용 검색 결과에서 카드 내용을 볼 때 내용은 메시지에 첨부 파일로 나타납니다. 첨부 파일의 이름은 `appname.html`이며, 여기서 `appname`은 카드 콘텐츠를 생성한 앱의 이름입니다. 다음 스크린샷은 (Asana라는 이름의 앱의 경우) 카드 콘텐츠가 팀 및 검색 결과에 나타나는 방식을 보여 줍니다.

  **Teams의 카드 콘텐츠**

  ![Teams 채널 메시지의 카드 콘텐츠](../media/CardContentTeams.png)

  **검색 결과의 카드 콘텐츠**

  ![내용 검색 결과에 있는 동일한 카드 콘텐츠](../media/CardContentEdiscoverySearchResults.png)

  > [!NOTE]
  > 현재 검색 결과에 카드 zhs텐츠의 이미지를 표시하려면(예: 이전 스크린샷의 체크마크) 검색 결과를 보기 위해 사용하는 브라우저 세션의 다른 탭에 있는 https://teams.microsoft.com)에서 Teams에 로그인해야 합니다. 그렇지 않으면 이미지 자리 표시자가 표시됩니다.

- **종류** 이메일 속성 또는 **메시지 종류** 검색 조건을 사용하여 Teams 콘텐츠를 구체적으로 검색할 수 있습니다.

  - 키워드 검색 쿼리의 일부로 **종류** 속성을 사용하려면 검색 쿼리의 **키워드** 상자에 `kind:microsoftteams`를 입력합니다.

    ![키워드 상자에 kind:microsoftteams 사용](../media/O365-ContentSearch-Teams-Keywords.png)

  - 검색 조건을 사용하려면 **메시지 종류** 조건을 추가하고 값 `microsoftteams`을 사용합니다.

    ![microsoftteams 값을 사용하여 메시지 종류 조건을 사용합니다.](../media/O365-ContentSearch-Teams-MessageKindCondition.png)

   조건은 **AND** 연산자에 의해 키워드 쿼리에 논리적으로 연결됩니다. 즉, 항목이 키워드 쿼리와 검색 조건에 모두 일치해야 검색 결과에 반환됩니다. 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)의 “조건 사용 지침” 섹션을 참조하세요.

## <a name="searching-yammer-groups"></a>Yammer 그룹 검색

**ItemClass** 전자 메일 속성 또는 **유형** 검색 조건을 사용하여 Yammer 그룹의 대화 항목을 구체적으로 검색할 수 있습니다.

  - 키워드 검색 쿼리의 일부로 **ItemClass** 속성을 사용하려면 검색 쿼리의 **키워드** 상자에 다음 속성:값 쌍 중 하나(또는 모두)를 입력할 수 있습니다.

     - ItemClass:IPM.Yammer.message
     - ItemClass:IPM.Yammer.poll
     - ItemClass:IPM.Yammer.praise
     - ItemClass:IPM.Yammer.question

    예를 들어 다음 검색 쿼리를 사용하여 Yammer 메시지와 Yammer 칭찬 항목을 반환할 수 있습니다.

    ![ItemClass 속성을 사용하여 Yammer 항목을 검색합니다.](../media/YammerContentSearch1.png)

  - 또는 **유형** 전자 메일 조건을 사용하고 **Yammer 메시지** 를 선택하여 Yammer 항목을 반환할 수 있습니다. 예를 들어 다음 검색 쿼리는 "기밀" 이라는 키워드를 포함하는 모든 Yammer 대화 항목을 반환합니다.

    ![유형 조건 카드를 사용하여 Yammer 대화 항목을 검색합니다.](../media/YammerContentSearch2.png)

## <a name="searching-inactive-mailboxes"></a>비활성 사서함 검색

콘텐츠 검색에서 비활성 사서함을 검색할 수 있습니다. 조직의 비활성 사서함 목록을 가져오려면 Exchange Online PowerShell에서 `Get-Mailbox -InactiveMailboxOnly` 명령을 실행합니다. 또는 보안 및 준수 센터에서 **정보 거버넌스**\>**보존** 으로 이동한 다음 **추가**![탐색 모음 줄임표를 클릭할 수 있습니다.](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **비활성 사서함**

다음은 비활성 사서함을 검색할 때 유의해야 하는 몇 가지 사항입니다.

- 기존 콘텐츠 검색에 사용자 사서함이 포함되고 해당 사서함이 비활성화되는 경우, 비활성 상태가 된 후 검색을 다시 실행하면 콘텐츠 검색에서 비활성 사서함을 계속 검색합니다.

- 경우에 따라 사용자가 활성 상태인 사서함과 동일한 SMTP 주소를 사용하는 비활성 사서함을 가지고 있을 수 있습니다. 이 경우 콘텐츠 검색의 위치로 선택하는 특정 사서함만 검색됩니다. 즉, 검색에 사용자의 사서함을 추가하는 경우 활성 사서함과 비활성 사서함이 모두 검색된다고 가정할 수 없습니다. 사용자가 검색에 명시적으로 추가하는 사서함만 검색됩니다.

- 보안 및 준수 센터 PowerShell을 사용하여 비활성 사서함을 검색할 콘텐츠 검색을 만들 수 있습니다. 이 작업을 수행하려면   비활성 사서함의 전자 메일 주소 앞에 마침표를 추가해야 합니다. 예를 들어, 다음 명령은 전자 메일 주소 pavelb@contoso.onmicrosoft.com를 사용하여 비활성 사서함을 검색하는 콘텐츠 검색을 만듭니다.

   ```powershell
   New-ComplianceSearch -Name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- 동일한 SMTP 주소를 사용하는 활성 사서함과 비활성 사서함은 없는 것이 좋습니다. 비활성 사서함에 지정된 SMTP 주소를 다시 사용해야 하는 경우 비활성 사서함을 복구하거나 비활성 사서함의 콘텐츠를 활성 사서함(또는 활성 사서함의 아카이브)으로 복원한 다음 비활성 사서함을 삭제하는 것이 좋습니다. 자세한 내용은 다음 항목 중 하나를 참조하십시오.

  - [Office 365에서 비활성 사서함 복구](recover-an-inactive-mailbox.md)

  - [Office 365에서 비활성 사서함 복원](restore-an-inactive-mailbox.md)

  - [Office 365에서 비활성 사서함 삭제](delete-an-inactive-mailbox.md)

## <a name="searching-disconnected-or-de-licensed-mailboxes"></a>연결이 끊어졌거나 라이선스가 없는 사서함 검색

Exchange Online 라이선스(또는 전체 Microsoft 365 라이선스)가 사용자 계정이나 Azure Active Directory에서 제거된 경우, 사용자의 사서함은 *연결이 끊어진* 사서함이 됩니다. 즉, 사서함과 사용자 계정이 더 이상 연결되지 않습니다. 다음은 연결이 끊어진 사서함을 검색할 때 발생하는 사항입니다.

- 사서함에서 라이선스가 제거되는 경우, 해당 사서함은 더 이상 검색할 수 없습니다.

- 기존 콘텐츠 검색에 라이선스가 제거된 사서함이 포함되어 있는 경우, 콘텐츠 검색을 다시 실행하면 연결이 끊어진 사서함의 검색 결과가 반환되지 않습니다.

- **New-ComplianceSearch** cmdlet을 사용하여 콘텐츠 검색을 만들고 연결이 끊어진 사서함을 Exchange 콘텐츠 위치로 지정하여 검색한 경우 콘텐츠 검색에서 연결이 끊어진 사서함의 검색 결과를 반환하지 않습니다.

검색이 가능할 수 있도록 연결이 끊어진 사서함에서 데이터를 보존해야 하는 경우 라이선스를 제거하기 전에 사서함을 보류 설정해야 합니다. 이렇게 하면 데이터가 보존되고 보류 설정이 해제될 때까지 연결이 끊어진 사서함이 검색 가능한 상태로 유지됩니다. 보류에 대한 자세한 내용은 [Exchange Online 사서함의 보류 유형을 식별하는 방법](identify-a-hold-on-an-exchange-online-mailbox.md)을 참조하세요.

## <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a>SharePoint 다중 지역 환경에서 콘텐츠 검색

eDiscovery 관리자가 [SharePoint 다중 지역 환경](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)의 여러 지역에서 SharePoint 및 OneDrive의 콘텐츠를 검색해야 하는 경우 다음과 같은 작업을 수행해야 합니다.

1. eDiscovery 관리자가 검색해야 하는 각 위성 지리적 위치에 대한 별도의 사용자 계정을 만듭니다. 해당 지리적 위치에 있는 사이트의 콘텐츠를 검색하려면 eDiscovery 관리자가 해당 위치에 대해 만든 계정에 로그인한 다음 콘텐츠 검색을 실행해야 합니다.

2. eDiscovery 관리자가 검색해야 하는 각 위성 지리적 위치 (및 해당 사용자 계정)에 대한 검색 권한 필터를 만듭니다. 이러한 각 검색 권한 필터는 eDiscovery 관리자가 해당 위치와 연결된 사용자 계정에 로그인한 경우 콘텐츠 검색의 범위를 특정 지리적 위치로 제한합니다.

> [!TIP]
> [고급 eDiscovery](overview-ediscovery-20.md)에서 검색 도구를 사용하는 경우에는 이 전략을 사용할 필요가 없습니다. 이는 고급 eDiscovery에서 SharePoint 사이트 및 OneDrive 계정을 검색하는 경우 모든 데이터 센터가 검색되기 때문입니다. 콘텐츠 검색 도구를 사용하고 [eDiscovery 사례](./get-started-core-ediscovery.md)와 연결된 검색을 실행하는 경우에만 지역별 사용자 계정 및 검색 권한 필터를 사용해야 합니다.

예를 들어 eDiscovery 관리자가 북미, 유럽 그리고 아시아 태평양에서 위성 위치에 SharePoint 및 OneDrive 콘텐츠를 검색해야 한다고 가정해 보겠습니다. 첫 번째 단계는 각 위치마다 하나씩 세 개의 사용자 계정을 만드는 것입니다. 다음 단계는 각 위치 *와* 해당 사용자 계정에 하나씩 세 개의 검색 권한 필터를 만드는 것입니다. 다음은 이 시나리오에 대한 세 가지 검색 권한 필터의 예입니다. 각 예제에서 **지역** 은 해당 지역에 대한 SharePoint 데이터 센터 위치를 지정하고 **사용자** 매개 변수는 해당 사용자 계정을 지정합니다.

**북미**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-NAM" -Users ediscovery-nam@contoso.com -Region NAM -Action ALL
```

**유럽**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-EUR" -Users ediscovery-eur@contoso.com -Region EUR -Action ALL
```

**아시아 태평양**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-APC" -Users ediscovery-apc@contoso.com -Region APC -Action ALL
```

검색 권한 필터를 사용하여 다중 지역 환경에서 콘텐츠를 검색하는 경우 다음 사항에 유의하세요.

- **지역** 매개 변수는 검색을 지정된 위성 위치로 보냅니다. eDiscovery 관리자가 검색 권한 필터에 지정된 지역 외부에 있는 SharePoint 및 OneDrive 사이트만 검색하는 경우 검색 결과가 반환되지 않습니다.

- **지역** 매개 변수가 Exchange 사서함의 검색을 제어하지 않습니다. 사서함을 검색하는 경우 모든 데이터 센터가 검색됩니다.

다중 지역 환경에서 검색 권한 필터를 사용하는 방법에 대한 자세한 내용은 [eDiscovery 검사에 대한 규정 준수 경계 설정](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)의 "다중 지역 환경에서 콘텐츠 검색 및 내보내기" 섹션을 참조하세요.
