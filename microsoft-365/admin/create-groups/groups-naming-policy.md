---
title: 그룹 명명 정책
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Microsoft 365 그룹에 대 한 명명 정책을 만드는 방법을 알아봅니다.
ms.openlocfilehash: 38b5bbed0c6e4c12af2f529568a53df329d9a933
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44388008"
---
# <a name="groups-naming-policy"></a>그룹 명명 정책

그룹 명명 정책을 사용 하 여 조직의 사용자가 만든 그룹에 대 한 일관 된 명명 전략을 적용 합니다. 명명 정책을 통해 그룹, 구성원, 지리적 위치 또는 그룹을 만든 사용자의 기능을 식별 하는 데 도움이 될 수 있습니다. 또한 명명 정책은 주소록의 그룹을 분류 하는 데 도움이 됩니다. 정책을 사용 하 여 그룹 이름 및 별칭에 특정 단어를 사용 하지 못하도록 차단할 수 있습니다.

명명 정책은 모든 그룹 작업 (예: Outlook, Microsoft 팀, SharePoint, Planner, Yammer 등)에 걸쳐 만들어지는 그룹에 적용 됩니다. 그룹 이름과 그룹 별칭에 모두 적용 됩니다. 사용자가 그룹을 만들 때와 기존 그룹에 대 한 그룹 이름 또는 별칭을 편집한 경우에 적용 됩니다.

> [!TIP]
> Microsoft 365 그룹 명명 정책은 Microsoft 365 그룹에만 적용 됩니다. Exchange Online에서 만든 메일 그룹에는 적용 되지 않습니다. 메일 그룹에 대 한 명명 정책을 만들려면 [메일 그룹 명명 정책 만들기](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)를 참조 하십시오.

그룹 명명 정책은 다음과 같은 기능으로 구성 됩니다.

- **접두사 접미사 명명 정책**: 접두사 또는 접미사를 사용 하 여 그룹 명명 규칙을 정의할 수 있습니다 (예: "US \_ My Group \_ 엔지니어링"). 접두사/접미사는 고정 문자열이 나 [부서]와 같은 사용자 특성으로, 그룹을 만드는 사용자에 따라 대체 될 수 있습니다.

- **사용자 지정 차단 된 단어**: 사용자가 만든 그룹에서 차단 되는 조직에 대 한 차단 되는 단어 집합을 업로드할 수 있습니다. (예: "CEO, 급여, HR").

## <a name="licensing-requirements"></a>라이선스 요구 사항

Microsoft 365 그룹에 대해 Azure AD 명명 정책을 사용 하려면 하나 이상의 Microsoft 365 그룹 구성원 인 각 고유 사용자 (게스트 포함)에 대해 Azure Active Directory Premium P1 라이선스 또는 Azure AD Basic .EDU 라이선스를 소유 하 고 있지 않아도 됩니다.

이는 그룹 명명 정책을 만드는 관리자 에게도 필요 합니다.

## <a name="prefix-suffix-naming-policy"></a>접두사 접미사 명명 정책

접두사와 접미사는 고정 문자열이 나 사용자 특성 일 수 있습니다.

### <a name="fixed-strings"></a>고정 문자열

그룹 작업의 GAL 및 왼쪽 탐색 창에 있는 그룹을 구별 하는 데 도움이 되는 짧은 문자열을 사용할 수 있습니다. 일반적인 접두사 접미사 중 일부는 ' Grp \_ Name ', ' \# name ', ' \_ name '과 같은 키워드입니다.

### <a name="attributes"></a>특성만

[부서] 그룹과 같은 그룹을 만든 사람과이를 [Country] like에서 만든 위치를 식별 하는 데 도움이 되는 특성을 사용할 수 있습니다.

|||
|:-----|:-----|
|**예제**|Policy = "GRP [GroupName] [부서]"|
||사용자의 부서 = 공학|
||만든 그룹 이름 = "그룹 엔지니어링 그룹화"|

지원 되는 Azure Active Directory (Azure AD) 특성은 [부서], [Company], [Office], [StateOrProvince], [CountryOrRegion] 및 [Title]입니다.

- 지원 되지 않는 사용자 특성은 고정 문자열로 간주 됩니다. 예:. "[postalCode]"

- Extension 특성 및 사용자 지정 특성은 지원 되지 않습니다.

조직의 모든 사용자에 대해 값이 채워진 특성을 사용 하 고 값이 더 긴 특성을 사용 하지 않는 것이 좋습니다.

### <a name="things-to-look-out-for"></a>검색할 사항

- 정책 생성 중 총 접두사 및 접미사 문자열 길이는 53 자로 제한 됩니다.

- 접두사와 접미사는 그룹 이름 및 그룹 별칭에서 지원 되는 특수 문자를 포함할 수 있습니다. 접두사 및 접미사에 그룹 별칭에서 허용 되지 않는 특수 문자가 포함 되어 있으면 그룹 이름에만 적용 됩니다. 따라서 그룹 이름에 적용 되는 접두사와 접미사는 그룹 별칭에 적용 된 접두 번호와 접미사가 다릅니다.

- Yammer Microsoft 365 연결 그룹을 사용 하는 경우에는 이름 지정 정책에 @,,,,에서 다음 문자를 사용 하지 않도록 \# \[ \] \<, and \> 합니다. 이러한 문자가 이름 지정 정책에 있는 경우 일반 Yammer 사용자는 그룹을 만들 수 없습니다.

## <a name="custom-blocked-words"></a>사용자 지정 차단 된 단어

그룹 이름 및 별칭에서 차단 되는 차단 된 단어의 쉼표로 구분 된 목록을 입력할 수 있습니다.

하위 문자열 검색은 수행 되지 않습니다. 특히 오류를 발생 시키려면 사용자가 입력 한 이름과 사용자 지정 차단 된 단어 사이에 정확 하 게 일치 하는 이름이 필요 합니다. ' Ass '이 차단 된 경우에도 사용자가 ' Class '와 같은 일반적인 단어 중 일부를 사용할 수 있도록 하위 문자열 검색이 수행 되지 않습니다.

다음 **항목을 확인 해야 합니다**.

- 차단 된 단어는 대/소문자를 구분 하지 않습니다.

- 사용자가 차단 된 단어를 입력 하면 그룹 클라이언트는 차단 된 단어와 함께 오류 메시지를 표시 합니다.

- 차단 된 단어에는 문자 제한이 적용 되지 않습니다.

- 차단 된 단어로 설정할 수 있는 5000 단어는 제한이 없습니다.

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

> [!NOTE]
> StaffHub 팀은 명명 정책을 따르지 않지만 기본 Microsoft 365 그룹은 수행 합니다. StaffHub 팀 이름은 접두사와 접미사를 적용 하지 않으며 사용자 지정 차단 된 단어를 확인 하지 않습니다. 그러나 StaffHub에서는 접두사와 접미사를 적용 하 고 기본 Microsoft 365 그룹에서 차단 된 단어를 제거 합니다.

## <a name="more-articles-on-naming-policy"></a>명명 정책에 대 한 추가 문서

[Azure Active Directory에서 Microsoft 365 그룹에 대 한 명명 정책 적용](https://go.microsoft.com/fwlink/?linkid=868340)

[그룹 설정 구성을 위한 Azure Active Directory cmdlet](https://go.microsoft.com/fwlink/?linkid=868341)
