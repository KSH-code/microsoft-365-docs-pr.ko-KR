---
title: Office 365 그룹 명명 정책
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Office 365 그룹에 대 한 명명 정책을 만드는 방법을 알아봅니다.
ms.openlocfilehash: 11e2907462d325e4ad421914ae5a0deb5013e695
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352719"
---
# <a name="office-365-groups-naming-policy"></a>Office 365 그룹 명명 정책

그룹 명명 정책을 사용 하 여 조직의 사용자가 만든 그룹에 대 한 일관 된 명명 전략을 적용 합니다. 명명 정책을 통해 그룹, 구성원, 지리적 위치 또는 그룹을 만든 사용자의 기능을 식별 하는 데 도움이 될 수 있습니다. 또한 명명 정책은 주소록의 그룹을 분류 하는 데 도움이 됩니다. 정책을 사용 하 여 그룹 이름 및 별칭에 특정 단어를 사용 하지 못하도록 차단할 수 있습니다.

명명 정책은 모든 그룹 작업 (예: Outlook, Microsoft 팀, SharePoint, Planner, Yammer 등)에 걸쳐 만들어지는 그룹에 적용 됩니다. 그룹 이름과 그룹 별칭에 모두 적용 됩니다. 사용자가 그룹을 만들 때와 기존 그룹에 대 한 그룹 이름 또는 별칭을 편집한 경우에 적용 됩니다.

> [!TIP]
> Office 365 그룹 명명 정책은 Office 365 그룹에만 적용 됩니다. Exchange Online에서 만든 메일 그룹에는 적용 되지 않습니다. 메일 그룹에 대 한 명명 정책을 만들려면 [메일 그룹 명명 정책 만들기](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)를 참조 하십시오.

그룹 명명 정책은 다음과 같은 기능으로 구성 됩니다.

- **접두사 접미사 명명 정책**: 접두사 또는 접미사를 사용 하 여 그룹 명명 규칙을 정의할 수 있습니다 (예: "GRP\_US\_내 그룹\_엔지니어링"). 접두사/접미사는 고정 문자열이 나 [부서]와 같은 사용자 특성으로, 그룹을 만드는 사용자에 따라 대체 될 수 있습니다.

- **사용자 지정 차단 된 단어**: 사용자가 만든 그룹에서 차단 되는 조직에 대 한 차단 되는 단어 집합을 업로드할 수 있습니다. (예: "CEO, 급여, HR").

## <a name="licensing-requirements"></a>라이선스 요구 사항

Office 365 그룹에 대해 Azure AD 명명 정책을 사용 하려면 하나 이상의 Office 365 그룹 구성원 인 각 고유 사용자 (게스트 포함)에 대해 Azure Active Directory Premium P1 라이선스 또는 Azure AD Basic .EDU 라이선스를 소유 하 고 있지 않아도 됩니다.
이는 그룹 명명 정책을 만드는 관리자 에게도 필요 합니다.

## <a name="prefix-suffix-naming-policy"></a>접두사 접미사 명명 정책

접두사와 접미사는 고정 문자열이 나 사용자 특성 일 수 있습니다.

### <a name="fixed-strings"></a>고정 문자열

그룹 작업의 GAL 및 왼쪽 탐색 창에 있는 그룹을 구별 하는 데 도움이 되는 짧은 문자열을 사용할 수 있습니다. 일반적인 접두사 접미사 중 일부는 ' Grp\_Name ', '\#name ', '\_name '과 같은 키워드입니다.

### <a name="attributes"></a>특성만

[부서] 그룹과 같은 그룹을 만든 사람과이를 [Country] like에서 만든 위치를 식별 하는 데 도움이 되는 특성을 사용할 수 있습니다.

|||
|:-----|:-----|
|**예제**|Policy = "GRP [GroupName] [부서]"|
||사용자의 부서 = 공학|
||만든 그룹 이름 = "그룹 엔지니어링 그룹화"|

지원 되는 Azure Active Directory (Azure AD) 특성은 [부서], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]입니다.

- 지원 되지 않는 사용자 특성은 고정 문자열로 간주 됩니다. 예:. "[postalCode]"

- Extension 특성 및 사용자 지정 특성은 지원 되지 않습니다.

조직의 모든 사용자에 대해 값이 채워진 특성을 사용 하 고 값이 더 긴 특성을 사용 하지 않는 것이 좋습니다.

### <a name="things-to-look-out-for"></a>검색할 사항

- 정책 생성 중 총 접두사 및 접미사 문자열 길이는 53 자로 제한 됩니다.

- 접두사와 접미사는 그룹 이름 및 그룹 별칭에서 지원 되는 특수 문자를 포함할 수 있습니다. 접두사 및 접미사에 그룹 별칭에서 허용 되지 않는 특수 문자가 포함 되어 있으면 그룹 별칭에 해당 문자를 제거 하 고 적용 합니다. 따라서 그룹 이름에 적용 되는 접두사와 접미사는 그룹 별칭에 적용 된 접두 번호와 접미사가 다릅니다.

- Yammer \#Office 365 연결 된 그룹을 사용 하는 경우에는 이름 지정 정책에 @,, \[ \] \<, 및와 \>같은 문자를 사용 하지 않도록 합니다. 이러한 문자가 이름 지정 정책에 있는 경우 일반 Yammer 사용자는 그룹을 만들 수 없습니다.

## <a name="custom-blocked-words"></a>사용자 지정 차단 된 단어

그룹 이름 및 별칭에서 차단 되는 차단 된 단어의 쉼표로 구분 된 목록을 입력할 수 있습니다.

차단 된 단어 확인은 사용자가 입력 한 그룹 이름에 대해 수행 됩니다. 사용자가 ' darnit '를 입력 하 고 '\_접두사 '가 명명 정책 인 경우 '\_접두사 darnit '가 실패 합니다.

하위 문자열 검색은 수행 되지 않습니다. 특히 오류를 발생 시키려면 사용자가 입력 한 이름과 사용자 지정 차단 된 단어 사이에 정확 하 게 일치 하는 이름이 필요 합니다. ' Ass '이 차단 된 경우에도 사용자가 ' Class '와 같은 일반적인 단어 중 일부를 사용할 수 있도록 하위 문자열 검색이 수행 되지 않습니다.

다음 **항목을 확인 해야 합니다**.

- 차단 된 단어는 대/소문자를 구분 하지 않습니다.

- 사용자가 차단 된 단어를 입력 하면 그룹 클라이언트는 차단 된 단어와 함께 오류 메시지를 표시 합니다.

- 차단 된 단어에는 문자 제한이 적용 되지 않습니다.

- 차단 된 단어로 설정할 수 있는 5000 단어의 상한선이 한도입니다.

## <a name="admin-override"></a>관리 재정의

선택적 관리자는 모든 그룹 작업 및 끝점에서 이러한 정책 으로부터 제외 되므로 이러한 차단 된 단어를 사용 하 여 그룹을 만들고 원하는 명명 규칙을 사용할 수 있습니다. 다음은 그룹 명명 정책에서 제외 된 관리자 역할 목록입니다.

- 전역 관리자

- 파트너 계층 1 지원

- 파트너 계층 2 지원

- 사용자 계정 관리자

- 디렉터리 작성자

## <a name="how-to-set-up-the-naming-policy"></a>명명 정책을 설정 하는 방법

명명 정책을 설정 하려면 다음을 수행 합니다.

1. [Azure Active Directory](https://aad.portal.azure.com)의 **관리**에서 **그룹**을 클릭 합니다.
2. **설정**아래에서 **이름 지정 정책을**클릭 합니다.
3. **그룹 명명 정책** 탭을 선택 합니다.
4. **현재 정책**에서 접두사 또는 접미사를 필요한 경우 또는 둘 다를 선택 하 고 해당 하는 확인란을 선택 합니다.
5. 각 줄에 대해 **특성** 및 **문자열** 을 선택한 다음 특성 또는 문자열을 지정 합니다.
6. 필요한 접두 번호와 접미사를 추가한 후 **저장**을 클릭 합니다.

![Azure Active Directory의 그룹 명명 정책 설정 스크린샷](../../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a>Office 365 앱 전반의 명명 정책 환경

사용자가 그룹 이름 및 별칭을 입력할 때 Office 365 앱은 접두사 및 접미사를 포함 하는 명명 정책 그룹 이름의 미리 보기를 표시 하도록 업데이트 되었습니다. 사용자가 차단 된 단어를 입력 하면 차단 되는 단어를 제거할 수 있도록 오류 메시지가 표시 됩니다.

## <a name="outlook-on-the-web"></a>웹용 Outlook

웹에서 outlook (이전의 Outlook Web App 또는 OWA)은 사용자가 그룹 이름 또는 그룹 별칭을 입력할 때 이름이 데코레이팅된 이름으로 표시 됩니다. 사용자가 차단 된 사용자 지정 단어를 입력 하면 사용자가 제거할 수 있도록 차단 된 단어와 함께 오류 메시지가 UI에 표시 됩니다. 아래에는 웹 환경 스냅숏의 Outlook이 나와 있습니다.

![Office 365 그룹의 그룹 명명 정책의 나란히 보기](../../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a>Outlook 데스크톱

Outlook 데스크톱에서 만든 그룹은 명명 정책을 따릅니다. Outlook 데스크톱 앱은 아직 명명 정책의 미리 보기를 표시 하지 않으며 사용자가 그룹 이름을 입력할 때 차단 된 사용자 지정 단어 오류를 반환 하지 않습니다. 그러나 그룹 이름 또는 별칭에 사용자 지정 차단 단어가 있으면 create/edit를 선택 하면 명명 정책이 자동으로 적용 되 고 사용자에 게 오류가 표시 됩니다.

## <a name="microsoft-teams"></a>Microsoft Teams

Microsoft 팀은 사용자가 팀 이름을 입력할 때 명명 정책을 데코레이팅된 이름으로 표시 합니다. 사용자가 차단 된 사용자 지정 단어를 입력 하면 사용자가 해당 단어를 제거할 수 있도록 차단 된 word와 함께 오류 메시지가 표시 됩니다.

![Microsoft 팀의 그룹 명명 정책 차단 됨 예](../../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a>SharePoint

SharePoint는 사용자가 사이트 이름 또는 그룹 전자 메일 주소를 입력할 때 이름 지정 정책 이름을 표시 합니다. 사용자가 차단 된 사용자 지정 단어를 입력 하면 사용자가 해당 단어를 제거할 수 있도록 차단 된 word와 함께 오류 메시지가 표시 됩니다.

![그룹 명명 정책-SharePoint 사이트 차단 된 이름](../../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a>Microsoft Stream

Microsoft Stream은 사용자가 그룹 이름 또는 그룹 전자 메일 별칭을 입력할 때 명명 정책을 데코레이팅된 이름으로 표시 합니다. 사용자가 차단 된 사용자 지정 단어를 입력 하면 사용자가 해당 메시지를 제거할 수 있도록 차단 된 단어와 함께 오류 메시지가 표시 됩니다.

![Microsoft Stream에 대 한 그룹 명명 정책 차단 된 예제](../../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a>Outlook iOS 및 Android 앱

Outlook 앱에서 만든 그룹은 명명 정책을 따릅니다. Outlook mobile은 그룹 이름을 입력할 때 명명 정책 미리 보기를 표시 합니다. 사용자가 차단 된 사용자 지정 단어를 입력 하면 그룹을 만들 때 오류 메시지가 표시 되므로 사용자가 차단 된 단어를 제거할 수 있습니다.

## <a name="planner"></a>Planner

Planner는 명명 정책을 따릅니다. Planner 계획 이름을 입력할 때 이름 지정 정책 미리 보기를 표시 합니다. 사용자가 차단 된 사용자 지정 단어를 입력 하면 계획을 만들 때 오류 메시지가 표시 되므로 사용자가 차단 된 단어를 제거할 수 있습니다.

![그룹 명명 정책-새 계획 차단 됨 만들기 예제](../../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a>고객 계약에 대 한 Dynamics 365

고객 계약에 대 한 Dynamics 365는 명명 정책을 준수 합니다. Dynamics 365은 사용자가 그룹 이름 또는 그룹 전자 메일 별칭을 입력할 때 이름이 데코레이팅된 이름 지정 정책을 보여 줍니다. 사용자가 차단 된 사용자 지정 단어를 입력 하면 사용자가 해당 메시지를 제거할 수 있도록 차단 된 단어와 함께 오류 메시지가 표시 됩니다.

![Dynamics 365](../../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a>SDS (학교 데이터 동기화)

SDS를 통해 만들어진 그룹은 명명 정책을 준수 하지만 명명 정책은 자동으로 적용 되지 않습니다. SDS 관리자는 그룹을 만들어야 하는 클래스 이름에 접두사와 접미사를 추가한 다음 SDS에 업로드 해야 합니다. 그렇지 않으면 그룹 만들기/편집이 실패 합니다.

## <a name="outlook-customer-manager-ocm"></a>OCM (Outlook 고객 관리자)

Outlook 고객 관리자는 명명 정책을 준수 합니다. 명명 정책은 Outlook Customer Manager에서 만든 그룹에 자동으로 적용 됩니다. "모든 영업 팀" 내의 단어 중 일부가 사용자 지정 차단 된 단어로 정의 된 경우에는 OCM에서 그룹을 만들 수 없게 됩니다. 사용자가 OCM 그룹을 만들 수 없으며 OCM 앱을 사용 하지 못하도록 차단 됩니다. "

## <a name="classroom-app"></a>교실 앱

강의실 앱에서 만든 그룹은 명명 정책을 준수 하지만, 명명 정책이 자동으로 적용 되지 않으며, 강의 그룹 이름을 입력 하는 동안에는 명명 정책 미리 보기가 사용자에 게 표시 되지 않습니다. 사용자가 접두사와 접미사를 사용 하 여 데코레이팅된 교실 그룹 이름을 입력 해야 합니다. 그렇지 않으면 교실 그룹 만들기 또는 편집이 오류로 인해 실패 합니다.

## <a name="power-bi"></a>Power BI

Power BI 작업 영역에서 만들어진 그룹은 명명 정책을 준수 하지만 명명 정책은 자동으로 적용 되지 않습니다. 또한 명명 정책 미리 보기는 사용자가 Power BI 작업 영역 이름을 입력할 때 표시 되지 않습니다.

명명 정책이 적용 된 권장 이름은 작업 영역 만들기 또는 편집의 오류 세부 정보에 표시 됩니다. 즉, 사용자는 접두사와 접미사로 데코레이팅된 작업 영역 이름을 입력 해야 합니다. 그렇지 않으면 작업 영역 만들기 또는 편집이 오류로 인해 실패 합니다.

## <a name="yammer"></a>Yammer

Azure Active Directory 계정을 사용 하 여 Yammer에 로그인 한 사용자가 그룹을 만들거나 그룹 이름을 편집 하는 경우 그룹 이름은 명명 정책을 따릅니다. 이는 Office 365 연결 된 그룹과 기타 모든 Yammer 그룹에 적용 됩니다.

명명 정책이 적용 되기 전에 Office 365 연결 된 그룹을 만든 경우에는 그룹 이름이 자동으로 이름 지정 정책을 따르지 않습니다. 사용자가 그룹 이름을 편집할 때 접두사와 접미사를 추가 하 라는 메시지가 표시 됩니다.

이름 정책에 Yammer 그룹 이름에 사용할 수 없는 문자가 포함 된 경우 관리자만 Yammer에서 연결 된 그룹을 만들 수 있습니다.

## <a name="staffhub"></a>StaffHub

StaffHub 팀은 명명 정책을 따르지 않지만 기본 Office 365 그룹에서는 수행 됩니다. StaffHub 팀 이름은 접두사와 접미사를 적용 하지 않으며 사용자 지정 차단 된 단어를 확인 하지 않습니다. 그러나 StaffHub는 접두사와 접미사를 적용 하 고 기본 Office 365 그룹에서 차단 된 단어를 제거 합니다.

## <a name="exchange-powershell"></a>Exchange PowerShell(Windows PowerShell)

Exchange PowerShell cmdlet은 명명 정책을 준수 합니다. 사용자는 그룹 이름 및 그룹 별칭에 명명 규칙을 사용 하지 않는 경우 제안 된 접두사 및 접미사와 사용자 지정 차단 단어에 대 한 적절 한 오류 메시지를 받게 됩니다.

## <a name="azure-active-directory-powershell-cmdlets"></a>Azure Active Directory PowerShell cmdlet

Azure Active Directory PowerShell cmdlet은 명명 정책을 준수 합니다. 사용자는 그룹 이름 및 그룹 별칭에 명명 규칙을 사용 하지 않는 경우 제안 된 접두사 및 접미사와 사용자 지정 차단 단어에 대 한 적절 한 오류 메시지를 받게 됩니다.

## <a name="exchange-admin-center"></a>Exchange 관리 센터

EAC (Exchange 관리 센터)는 명명 정책을 따릅니다. 만들기 또는 편집 작업 시 사용자는 그룹 이름 및 그룹 별칭에 명명 규칙을 사용 하지 않는 경우 제안 된 접두사 및 접미사와 사용자 지정 차단 단어에 대 한 적절 한 오류 메시지를 받게 됩니다.

## <a name="microsoft-365-admin-center"></a>Microsoft 365 관리 센터

Microsoft 365 관리 센터는 명명 정책을 준수 합니다. 만들기 또는 편집 작업에서 이름 지정 정책이 자동으로 적용 됩니다. 사용자가 차단 된 사용자 지정 단어를 입력 하면 해당 오류 메시지가 표시 됩니다. Microsoft 365 관리 센터에서 명명 정책의 미리 보기가 표시 되지 않고 사용자가 그룹 이름을 입력할 때 사용자 지정 차단 된 단어 오류가 반환 되지 않습니다.

## <a name="azure-active-directory-portal"></a>Azure Active Directory 포털

Azure Active Directory 포털이 명명 정책을 준수 합니다. Azure Active Directory portal은 그룹 이름으로 들어갈 때 명명 정책 미리 보기를 표시 합니다. 사용자가 차단 된 사용자 지정 단어를 입력 하면 그룹을 만들 때 오류 메시지가 표시 되므로 사용자가 차단 된 단어를 제거할 수 있습니다.

## <a name="more-articles-on-naming-policy"></a>명명 정책에 대 한 추가 문서

[Azure Active Directory에서 Office 365 그룹에 대 한 명명 정책 적용](https://go.microsoft.com/fwlink/?linkid=868340)

[그룹 설정 구성을 위한 Azure Active Directory cmdlet](https://go.microsoft.com/fwlink/?linkid=868341)
