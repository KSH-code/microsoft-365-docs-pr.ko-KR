---
title: Microsoft 365 게스트 공유 설정 참조
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
f1.keywords: NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkTEAMS
ms.localizationpriority: high
recommendations: false
description: 조직 외부 사용자와의 공유에 영향을 줄 수 있는 Microsoft 365에서 사용할 수 있는 게스트 공유 설정에 대해 알아봅니다.
ms.openlocfilehash: 8028258b1b5a7ec13c2a9c9e2e89e52756c97d38
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202348"
---
# <a name="microsoft-365-guest-sharing-settings-reference"></a>Microsoft 365 게스트 공유 설정 참조

이 문서에서는 Teams, Microsoft 365 그룹, SharePoint 및 OneDrive와 같이 Microsoft 365 작업에서 조직 외부 사용자와 공유하는 데 영향을 줄 수 있는 다양한 설정에 대한 참조를 제공합니다. 이러한 설정은 Azure Active Directory, Microsoft 365, Teams 및 SharePoint 관리 센터에 있습니다.

## <a name="azure-active-directory"></a>Azure Active Directory

**관리자 역할:** 전역 관리자 

Azure Active Directory는 Microsoft 365에서 사용하는 디렉터리 서비스입니다. Azure Active Directory 조직 관계 설정은 Teams, Microsoft 365 그룹, SharePoint 및 OneDrive의 공유에 직접적인 영향을 미칩니다.

> [!NOTE]
> 이 설정은 [Azure Active Directory B2B와 Sharepoint 및 OneDrive 통합(미리 보기)](/sharepoint/sharepoint-azureb2b-integration-preview)이 구성된 경우에만 Sharepoint에 영향을 줍니다. 아래 표는 이 구성을 가정합니다.

### <a name="external-collaboration-settings"></a>외부 공동 작업 설정

**탐색:** [Azure Active Directory 관리 센터](https://aad.portal.azure.com) > Azure Active Directory > 외부 ID > 외부 공동 작업 설정

![Azure Active Directory 조직 관계 설정 페이지 스크린샷.](../media/azure-ad-organizational-relationships-settings.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|게스트 사용자 액세스|게스트 사용자는 디렉터리 개체의 속성 및 구성원 자격에 대해 제한된 액세스 권한을 가집니다|[Azure Active Directory에서 게스트가 갖는 사용 권한을](/azure/active-directory/fundamentals/users-default-permissions) 결정합니다.|
|게스트 초대 설정|조직의 모든 사용자가 게스트 및 비관리자를 포함한 게스트 사용자를 초대할 수 있습니다|게스트, 구성원 및 관리자가 게스트를 조직에 초대할 수 있는지 여부를 결정합니다. <p> 이 설정은 Teams 및 SharePoint와 같은 Microsoft 365 공유 환경에 영향을 줍니다.|
|사용자 흐름을 통해 게스트 셀프 서비스 가입 사용|아니요|사용자가 만든 앱에 다른 사람이 가입하고 새 게스트 계정을 만들 수 있는 사용자 흐름을 만들 수 있는지 여부를 결정합니다.|
|공동 작업 제한 사항|모든 도메인에 초대를 보낼 수 있도록 허용|이 설정을 사용하면 공유에 허용되거나 차단된 도메인 목록을 지정할 수 있습니다. 허용 도메인이 지정되면 해당 도메인에만 공유 초대를 보낼 수 있습니다. 거부된 도메인을 지정하면 공유 초대장을 해당 도메인으로 보낼 수 없습니다. <p> 이 설정은 Teamsdhk SharePoint와 같은 Microsoft 365 공유 환경에 영향을 줍니다. SharePoint 또는 Teams의 도메인 필터링을 사용하여 더 세분화된 수준으로 도메인을 허용하거나 차단할 수 있습니다.|

이러한 설정은 사용자가 디렉터리에 초대되는 방식에 영향을 줍니다. 이미 디렉토리에 있는 게스트와의 공유에는 영향을 주지 않습니다.

## <a name="microsoft-365"></a>Microsoft 365

**관리자 역할:** 전역 관리자 

Microsoft 365 관리 센터에는 공유 및 Microsoft 365 그룹에 대한 조직 수준 설정이 있습니다.

### <a name="sharing"></a>공유

**탐색:** [Microsoft 365 관리 센터](https://admin.microsoft.com) > **설정** > **조직 설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**보안 및 개인 정보 보호** 탭</a> > **공유**.

![Microsoft 365 관리 센터의 보안 및 개인 정보 게스트 공유 설정 스크린샷.](../media/sharepoint-security-privacy-sharing-setting.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|사용자가 조직에 새 게스트를 추가하도록 허용|켜짐|**예** 로 설정된 경우 Azure AD 구성원이 Azure AD를 통해 게스트를 초대할 수 있습니다. **아니요** 로 설정된 경우 할 수 없습니다. **예** 로 설정된 경우 Microsoft 365 그룹 구성원이 게스트를 소유자 승인으로 초대할 수 있습니다. **아니요** 로 설정된 경우 Microsoft 365 그룹 구성원은 소유자 승인으로 게스트를 초대할 수 있지만, 소유자는 승인하기 위해 전역 관리자여야 합니다. <p> **구성원이 게스트를 초대할 수 있음** 은 Microsoft 365에서 사이트 또는 그룹 구성원이 아니라 Azure AD의 구성원(게스트와 반대되는)을 언급함을 유의합니다. <p> Azure Active Directory 조직 관계 설정에서 **구성원이 게스트를 초대할 수 있음** 설정과 동일합니다.|

### <a name="microsoft-365-groups"></a>Microsoft 365 그룹

**탐색:** [Microsoft 365 관리 센터](https://admin.microsoft.com) > **설정** > **조직 설정** > Microsoft 365 그룹

![Microsoft 365 관리 센터의 Microsoft 365 그룹 게스트 설정 스크린샷.](../media/office-365-groups-guest-settings.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|조직 외부의 그룹 구성원이 그룹 콘텐츠에 액세스하도록 허용|켜짐|**켜짐** 으로 설정되면 게스트가 그룹 콘텐츠에 액세스할 수 있습니다. **해제** 로 설정하면 할 수 없습니다. 게스트가 Microsoft 365 그룹 또는 Teams와 상호 작용하는 모든 시나리오의 경우 이 설정을 **켜짐** 으로 지정해야 합니다.|
|그룹 소유자가 조직 외부의 사람을 그룹에 추가하도록 허용|켜짐|**켜짐** 으로 설정되면 Microsoft 365 그룹 또는 Teams 소유자는 새 게스트를 그룹에 초대할 수 있습니다. 이 기능을 **해제** 하면 소유자는 이미 디렉토리에 있는 게스트만 초대할 수 있습니다.|

이러한 설정은 조직 수준에 있습니다. PowerShell을 사용하여 그룹 수준에서 이러한 설정을 변경하는 방법에 대한 자세한 내용은 [특정 그룹에 대한 설정 만들기](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#create-settings-for-a-specific-group)를 참조하세요.

## <a name="teams"></a>Teams

다른 게스트 설정을 사용하려면 Teams 마스터 게스트 액세스 스위치, **Teams에서 게스트 액세스 허용** 이 **켜짐** 상태에 있어야 합니다.

**관리자 역할:** Teams 서비스 관리자

### <a name="guest-access"></a>게스트 액세스

**탐색:** [Teams 관리 센터](https://admin.teams.microsoft.com) > **조직 전체 설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**게스트 액세스**</a>

![Teams 게스트 액세스 토글 스크린샷.](../media/teams-guest-access-toggle.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|Teams에서 게스트 액세스 허용|해제|Teams 전체에 대한 게스트 액세스를 설정하거나 해제합니다. 이 설정을 변경하는 데 24시간이 걸릴 수 있습니다.|

### <a name="guest-calling"></a>게스트 통화

**탐색:** [Teams 관리 센터](https://admin.teams.microsoft.com) > **조직 전체 설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**게스트 액세스**</a>

![Teams 게스트 통화 옵션 스크린샷.](../media/teams-guest-calling-setting.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|개인 전화 걸기|켜짐|**켜짐** 으로 설정하면 게스트가 Teams에서 피어 투 피어 통화를 할 수 있습니다. **해제** 되어 있을 때는 할 수 없습니다.|

### <a name="guest-meeting"></a>게스트 모임

**탐색:** [Teams 관리 센터](https://admin.teams.microsoft.com) > **조직 전체 설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**게스트 액세스**</a>

![Teams 게스트 모임 설정 스크린샷.](../media/teams-guest-meeting-settings.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|IP 비디오 허용|켜짐|**켜짐** 으로 설정하면 게스트는 통화 및 회의에서 비디오를 사용할 수 있습니다. **해제** 되어 있을 때는 할 수 없습니다.|
|화면 공유 모드|전체 화면|**사용 안 함** 으로 설정되면 게스트는 Teams에서 화면을 공유할 수 없습니다. **단일 응용 프로그램** 으로 설정되면 게스트는 화면에서 하나의 응용 프로그램만 공유할 수 있습니다. **전체 화면** 으로 설정되면 게스트가 프로그램 또는 전체 화면을 공유하도록 선택할 수 있습니다.|
|모임 시작 허용|켜짐|**켜짐** 으로 설정하면 게스트는 Teams에서 모임 시작 기능을 사용할 수 있습니다. **해제** 되어 있을 때는 할 수 없습니다.|

### <a name="guest-messaging"></a>게스트 메시징

**탐색:** [Teams 관리 센터](https://admin.teams.microsoft.com) > **조직 전체 설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**게스트 액세스**</a>

![Teams 게스트 메시징 설정 스크린샷.](../media/teams-guest-messaging-settings.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|보낸 메시지 편집|켜짐|**켜짐** 으로 설정되면 게스트는 이전에 보낸 메시지를 편집할 수 있습니다. **해제** 되어 있을 때는 할 수 없습니다.|
|보낸 메시지 삭제|켜짐|**켜짐** 으로 설정되면 게스트는 이전에 보낸 메시지를 삭제할 수 있습니다. **해제** 되어 있을 때는 할 수 없습니다.|
|채팅|켜짐|**켜짐** 으로 설정하면 게스트는 Teams에서 채팅을 사용할 수 있습니다. **해제** 되어 있을 때는 할 수 없습니다.|
|대화에서 Giphy 사용|켜짐|**켜짐** 으로 설정하면 게스트가 Giphys를 대화에서 사용할 수 있습니다. **해제** 되어 있을 때는 할 수 없습니다.|
|Giphy 콘텐츠 등급|보통|**모든 콘텐츠를 허용** 하도록 설정하면 게스트는 콘텐츠 등급과 상관없이 모든 Giphy를 채팅에 삽입할 수 있습니다. **보통** 으로 설정하면 게스트는 채팅에 Giphy를 삽입할 수 있지만 성인용 콘텐츠는 보통으로 제한됩니다. **엄격** 으로 설정하면 게스트는 채팅에 Giphy를 삽입할 수 있지만 성인용 콘텐츠 삽입이 제한됩니다.|
|대화에서 Memes 사용|켜짐|**켜짐** 으로 설정하면 게스트는 memes를 대화에서 사용할 수 있습니다. **해제** 되어 있을 때는 사용할 수 없습니다.|
|대화에 사용자 스티커|켜짐|**켜짐** 으로 설정하면 게스트는 스티커를 대화에서 사용할 수 있습니다. **해제** 되어 있을 때는 사용할 수 없습니다.|
|몰입형 리더가 메시지를 볼 수 있도록 허용|켜짐|**켜짐** 으로 설정하면 게스트는 몰입형 리더에서 메시지를 볼 수 있습니다. **해제** 되어 있을 때는 사용할 수 없습니다.|

## <a name="sharepoint-and-onedrive-organization-level"></a>SharePoint 및 OneDrive(조직 수준)

**관리자 역할:** SharePoint 관리자

이러한 설정은 조직의 모든 사이트에 영향을 줍니다. Microsoft 365 그룹 또는 Teams에 직접 영향을 주지는 않지만, 사용자 환경 문제를 피하기 위해 Microsoft 365 그룹 및 Teams의 설정을 사용하여 이 설정을 조정하는 것이 좋습니다. (예를 들어 게스트 공유는 Teams에서 허용되지만 SharePoint에서는 허용되지 않는 경우 Teams 파일이 SharePoint에 저장되므로 Teams의 게스트는 파일 탭에 액세스할 수 없습니다.)

### <a name="sharepoint-and-onedrive-sharing-settings"></a>SharePoint 및 OneDrive에서 공유 설정

OneDrive는 SharePoint 내의 사이트 계층 구조이므로 조직 수준 공유 설정은 다른 SharePoint 사이트와 마찬가지로 OneDrive에 직접 영향을 줍니다.

**탐색:** SharePoint 관리 센터 > 공유

![SharePoint 조직 수준 공유 설정 스크린샷.](../media/external-sharing.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|SharePoint|누구나|SharePoint 사이트에 허용되는 최대 허용 공유 권한을 지정합니다.|
|OneDrive|누구나|OneDrive 사이트에 허용되는 최대 허용 공유 권한을 지정합니다. 이 설정은 SharePoint 설정보다 더 허용되지 않습니다.|

### <a name="sharepoint-and-onedrive-advanced-sharing-settings"></a>SharePoint 및 OneDrive에서 고급 공유 설정

**탐색:** SharePoint 관리 센터 > 공유

![SharePoint 조직 수준 추가 공유 설정 스크린샷.](../media/external-sharing.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|도메인별 외부 공유 제한|해제|이 설정을 사용하면 공유에 허용되거나 차단된 도메인 목록을 지정할 수 있습니다. 허용 도메인이 지정되면 해당 도메인에만 공유 초대를 보낼 수 있습니다. 거부된 도메인을 지정하면 공유 초대장을 해당 도메인으로 보낼 수 없습니다. <p> 이 설정은 조직의 모든 SharePoint 및 OneDrive 사이트에 영향을 줍니다.|
|Allow only users in specific security groups to share externally(특정 보안 그룹의 사용자만 외부로 공유할 수 있도록 허용)|해제|SharePoint 및 OneDrive에서 게스트와 공유할 수 있는 사용자를 제한 하려면 지정된 보안 그룹에 있는 사용자와의 공유를 제한하는 것이 좋습니다. 이러한 설정은 Microsoft 365 그룹 또는 Teams를 통한 공유에는 영향을 주지 않습니다. 그룹 또는 팀을 통해 초대한 게스트는 관련 사이트에도 액세스할 수 있지만, 문서 및 폴더 공유는 지정된 보안 그룹의 사용자만 수행할 수 있습니다. <p> 지정된 각 그룹에서 모든 사용자 링크를 공유할 수 있는 사용자를 선택할 수 있습니다.|
|게스트는 공유 초대장이 전송된 계정과 동일한 계정으로 로그인해야 함|해제|게스트가 초대장과 다른 전자 메일 주소를 사용하여 사이트 공유 초대장을 사용할 수 없도록 합니다. <p> [Azure AD B2B(미리 보기)와 SharePoint 및 OneDrive 통합](/sharepoint/sharepoint-azureb2b-integration-preview)에서는 초대가 전송된 이메일 주소를 기반으로 디렉터리에 모든 게스트가 추가되기 때문에 이 설정을 사용하지 않습니다. 대체 이메일 주소는 사이트에 액세스하는 데 사용할 수 없습니다.|
|게스트가 소유하지 않은 항목을 공유할 수 있도록 허용|켜짐|**켜짐** 을 설정되면 게스트는 다른 사용자나 게스트와 소유하지 않는 항목을 공유할 수 있습니다. **해제** 된 경우에는 할 수 없습니다. 게스트는 항상 모든 권한을 보유한 항목을 공유할 수 있습니다.|
|People who use a verification code must reauthenticate after this many days(확인 코드를 사용하는 사용자는 다음 기간(일) 후에 다시 인증해야 함)|해제|이 설정을 사용하면 일회용 암호로 인증하는 사용자가 특정 기간(일) 후에 다시 인증해야 합니다.|
|사이트 또는 OneDrive 게스트 액세스가 이 기간 후에 자동으로 만료됩니다.|설정|관리자가 게스트 액세스에 대한 만료 시간을 설정한 경우, 사이트에 초대하거나 개별 파일 및 폴더를 공유하는 각 게스트에게 일정 기간(일) 동안 액세스 권한이 부여됩니다. 자세한 내용은 [사이트에 대한 게스트 만료 관리](https://support.microsoft.com/en-us/office/manage-guest-expiration-for-a-site-25bee24f-42ad-4ee8-8402-4186eed74dea)를 참조하세요.

### <a name="sharepoint-and-onedrive-file-and-folder-link-settings"></a>SharePoint 및 OneDrive 파일 및 폴더 링크 설정

SharePoint 및 OneDrive에서 파일 및 폴더를 공유하는 경우 공유받는 사람에게 파일 또는 폴더에 대한 직접 액세스 권한이 부여되지 않고 파일 또는 폴더에 대한 사용 권한이 있는 링크가 전송됩니다. 여러 유형의 링크를 사용할 수 있으며, 사용자가 파일이나 폴더를 공유할 때 사용자에게 표시되는 기본 링크 유형을 선택할 수 있습니다. *모든 사용자* 링크에 대한 사용 권한 및 만료 옵션을 설정할 수도 있습니다.

**탐색:** SharePoint 관리 센터 > 공유

![SharePoint 조직 수준 파일 및 폴더 공유 설정 스크린샷.](../media/sharepoint-organization-files-folders-sharing-settings.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|파일 및 폴더 링크|링크가 있는 모든 사용자|사용자가 파일이나 폴더를 공유할 때 기본적으로 표시되는 공유 링크를 지정합니다. 사용자가 원하는 경우 공유하기 전에 옵션을 변경할 수 있습니다. 기본값이 **링크가 있는 모든 사용자** 로 설정되어 있고 지정된 사이트에 대해 *모든 사용자* 공유를 허용하지 않으면 **조직의 사용자만** 해당 사이트의 기본값으로 표시됩니다.|
|이 링크는 며칠 이내에 만료되어야 합니다.|해제(만료 없음)|*모든 사용자* 링크를 만든 후 만료될 때까지 남은 일수를 지정합니다. 만료된 링크는 갱신할 수 없습니다. 만료 이후 계속 공유해야 하는 경우 새 링크를 만듭니다.|
|파일 사용 권한|보기 및 편집|사용자가 *모든 사용자* 링크를 만들 때 사용할 수 있는 파일 사용 권한 수준을 지정합니다. **보기** 를 선택하면 사용자는 보기 권한이 있는 *모든 사용자* 파일 링크만 만들 수 있습니다. **보기 및 편집** 이 선택되면 사용자는 링크를 만들 때 보기와 보기 및 편집 권한을 선택할 수 있습니다.|
|폴더 권한|보기, 편집 및 업로드|사용자가 *모든 사용자* 링크를 만들 때 사용할 수 있는 폴더 사용 권한 수준을 지정합니다. **보기** 를 선택하면 사용자는 보기 권한이 있는 *모든 사용자* 폴더 링크만 만들 수 있습니다. **보기, 편집 및 업로드** 가 선택되면 사용자는 링크를 만들 때 보기와 보기 및 편집 권한을 선택할 수 있습니다.|

## <a name="sharepoint-site-level"></a>SharePoint(사이트 수준)

**관리자 역할:** SharePoint 관리자

이 설정은 SharePoint에 대한 조직 전체 설정의 영향을 받을 수 있기 때문에 조직 수준 설정이 변경되면 사이트에 대한 효과적인 공유 설정이 변경될 수 있습니다. 여기서 설정을 선택하고 조직 수준이 더 제한적인 값으로 설정되는 경우 이 사이트는 더 제한적인 값으로 작동합니다. 예를 들어, **모든 사용자** 를 선택하고 나중에 조직 수준 설정을 **신규 및 기존 게스트** 로 설정하는 경우 이 사이트는 새 게스트와 기존 게스트만 사용할 수 있습니다. 그런 다음 조직 수준 설정을 다시 **모든 사용자** 로 설정하면 이 사이트에서 *모든 사용자* 링크를 다시 허용합니다.

### <a name="site-sharing"></a>사이트 공유

SharePoint의 각 사이트에 대한 게스트 공유 권한을 설정할 수 있습니다. 이 설정은 사이트 공유와 파일 및 폴더 공유 둘 다에 적용됩니다. (사이트 공유에는 *모든 사용자* 공유는 사용할 수 없습니다. **모든 사용자** 를 선택하면 사용자는 *모든 사용자* 링크를 사용하여 파일 및 폴더를 공유하고 사이트 자체는 신규 및 기존 게스트와 공유할 수 있습니다.

사이트에 민감도 레이블이 적용된 경우, 해당 레이블이 외부 공유 설정을 컨트롤할 수 있습니다. 자세한 내용은 [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호](../compliance/sensitivity-labels-teams-groups-sites.md)를 참조하세요.

**탐색:** SharePoint 관리 센터 > 활성 사이트 > 사이트 선택 > 정책 탭 > 외부 공유 편집

![SharePoint 사이트 외부 공유 설정 스크린샷.](../media/sharepoint-site-external-sharing-settings.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|콘텐츠를 다음과 공유할 수 있습니다.|사이트 유형에 따라 다름(아래 표 참조)|이 사이트에 허용되는 외부 공유 유형을 표시합니다. 여기에서 사용할 수있는 옵션은 SharePoint에 대한 조직 수준 공유 설정에 따릅니다.|

### <a name="site-file-and-folder-link-settings"></a>사이트 파일 및 폴더 링크 설정

링크 유형 및 사용 권한에 대해 기본값을 설정하고, 각 사이트의 *모든 사용자* 링크에 대해 만료 설정을 설정할 수 있습니다. 사이트 수준에서 설정되는 경우, 이 설정이 조직 수준 설정보다 우선합니다. 조직 수준에서 *모든 사용자* 링크를 사용 하지 않도록 설정한 경우에는 *모든 사용자* 가 사이트 수준에서 사용 가능한 링크 유형이 되지 않습니다.

**탐색:** SharePoint 관리 센터 > 활성 사이트 > 사이트 선택 > 정책 탭 > 외부 공유 편집

![SharePoint 사이트 수준 링크 공유 설정 스크린샷.](../media/sharepoint-site-link-sharing-settings.png)

| 설정 | 기본값 | 설명 |
|:-----|:-----|:-----|
|도메인별 공유 제한|해제|이 설정을 사용하면 공유에 허용되거나 차단된 도메인 목록을 지정할 수 있습니다. 허용 도메인이 지정되면 해당 도메인에만 공유 초대를 보낼 수 있습니다. 거부된 도메인을 지정하면 공유 초대장을 해당 도메인으로 보낼 수 없습니다. <p> 이 설정을 사용하여 조직 또는 Azure AD 수준에 설정된 도메인 제한을 재정의할 수 없습니다.|
|기본 공유 링크 유형|조직 수준 설정과 동일|이 설정을 사용하면 이 사이트에서 사용자에게 표시되는 기본 공유 링크를 지정할 수 있습니다. *조직 수준 설정과 동일* 옵션이 조직 및 사이트 공유 설정의 조합으로 정의됩니다.|
|모든 사용자 링크 고급 설정|조직 수준 설정과 동일|이 사이트에서 만료되는 파일에 대한 *모든 사용자* 링크가 만들어진 후 일 수를 지정합니다. 만료된 링크는 갱신할 수 없습니다. 만료 이후 계속 공유해야 하는 경우 새 링크를 만듭니다.|
|기본 링크 사용 권한|조직 수준 설정과 동일|이 설정을 사용하면 이 사이트에 있는 파일에 대해 만든 공유 링크에 기본 사용 권한(보기 또는 편집)을 지정할 수 있습니다.|

### <a name="default-site-sharing-settings"></a>기본 사이트 공유 설정

아래 표에는 각 사이트 유형에 대한 기본 공유 설정이 나와 있습니다.

| 사이트 유형 | 기본 공유 설정 |
|:-----|:-----|
|Classic|**조직 내부 사용자만**|
|OneDrive|**모든 사용자**|
|그룹 연결 사이트(Teams 포함)|**신규 및 기존 게스트** Microsoft 365 그룹 설정 **그룹 소유자가 조직 외부 사람을 그룹에 추가하도록 허용** 이 **켜져** 있는 경우에 해당합니다. 그렇지 않으면 **기존 게스트만** 해당됩니다.|
|통신|**조직 내부 사용자만**|
|그룹이 없는 최신 사이트 (#STS3 TeamSite)|**조직 내부 사용자만**|

> [!NOTE]
> 루트 통신 사이트(Tenant-name.sharepoint.com)에는 **사용자** 의 기본 공유 설정이 있습니다.

## <a name="see-also"></a>참고 항목

[SharePoint 및 OneDrive 외부 공유 개요](/sharepoint/external-sharing-overview)

[Microsoft Teams의 게스트 액세스](/MicrosoftTeams/guest-access)

[Microsoft 365 그룹에 게스트 추가하기](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)
