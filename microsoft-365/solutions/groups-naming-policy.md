---
title: Microsoft 365 그룹 이름 정책
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
recommendations: false
description: 사용자 그룹에 대한 이름 정책을 만드는 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: 9fb75feb255ee6d58313f4cfaf3486c4a8cd63b4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213412"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 그룹 이름 정책

그룹 이름 정책을 사용하여 조직의 사용자가 만든 그룹에 대해 일관된 이름 전략을 적용할 수 있습니다. 명명 정책은 사용자와 그룹, 구성원 자격, 지리적 지역 또는 그룹을 만든 사용자의 기능을 식별하는 데 도움이 될 수 있습니다. 또한 이름 정책은 주소 책의 그룹을 분류하는 데도 도움이 될 수 있습니다. 이 정책을 사용하여 특정 단어가 그룹 이름 및 별칭에 사용되지 못하도록 차단할 수 있습니다.

이름 정책은 모든 그룹 작업(예: Outlook, Microsoft Teams, SharePoint, Planner, Yammer 등)에서 만들어진 그룹에 적용됩니다. 그룹 이름과 그룹 별칭에 모두 적용됩니다. 또한 사용자가 그룹을 만들고 기존 그룹에 대해 그룹 이름, 별칭, 설명 또는 아바타를 편집할 때도 적용됩니다.

> [!TIP]
> Microsoft 365 그룹 이름 정책은 그룹 Microsoft 365 적용됩니다. 메일 그룹에서 만든 메일 그룹에는 적용되지 Exchange Online. 메일 그룹에 대한 이름 정책은 메일 그룹 이름 정책 [만들기를 참조합니다.](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)

그룹 이름 정책은 다음 기능으로 구성됩니다.

- **접두사-접미사** 명명 정책: 접두사 또는 접미어를 사용하여 그룹의 명명 규칙(예: "US \_ My Group Engineering")을 정의할 수 \_ 있습니다. 접두사/접미사는 그룹을 만드는 사용자에 따라 대체되는 [Department] 같은 고정 문자열 또는 사용자 특성일 수 있습니다.

- **사용자 지정** 차단 단어: 사용자가 만든 그룹에서 차단되는 조직 관련 차단된 단어 집합을 업로드할 수 있습니다. (예: "CEO, 급여, HR").

## <a name="licensing-requirements"></a>라이선스 요구사항

Microsoft 365 그룹에 대해 Azure AD 이름 지정 정책을 사용하려면 사용자가 소유해야 하지만 하나 이상의 Microsoft 365 그룹의 구성원인 각 고유 사용자(게스트 포함)에 대해 Azure Active Directory Premium P1 라이선스 또는 Azure AD Basic EDU 라이선스를 할당할 필요는 없습니다.

그룹 이름 정책을 만드는 관리자에게도 필요합니다.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix 이름 정책

접두사와 접미사는 고정 문자열 또는 사용자 특성일 수 있습니다.

### <a name="fixed-strings"></a>고정 문자열

GAL 및 그룹 워크로드의 왼쪽 탐색에서 그룹을 차별화하는 데 도움이 되는 짧은 문자열을 사용할 수 있습니다. 일반적인 접두사 접미사 중 일부는 'Grp \_ Name' , \# 'Name', \_ 'Name' 같은 키워드입니다.

### <a name="attributes"></a>특성

[Department]과 같은 그룹을 만든 사용자와 [Country]과 같이 그룹을 만든 위치를 식별하는 데 도움이 되는 특성을 사용할 수 있습니다.

예제:

- 정책 = "GRP [GroupName] [Department]"
- 사용자 부서 = 엔지니어링
- 만든 그룹 이름 = "GRP 내 그룹 엔지니어링"

지원되는 Azure Active Directory (Azure AD) 특성은 [부서], [회사], [Office], [StateOrProvince], [CountryOrRegion], [Title]입니다.

- 지원되지 않는 사용자 특성은 고정 문자열(예: [postalCode])로 간주됩니다.

- 확장 특성 및 사용자 지정 특성은 지원되지 않습니다.

조직의 모든 사용자에 대해 값이 채워진 특성을 사용하며 값이 긴 특성을 사용하지 않는 것이 좋습니다.

### <a name="things-to-look-out-for"></a>살펴보아야 할 것

- 정책을 만들 때 접두사와 접미사 문자열의 총 길이는 53자로 제한됩니다.

- 접두사와 접미사는 그룹 이름 및 그룹 별칭에서 지원되는 특수 문자를 포함할 수 있습니다. 접두사와 접미사에 그룹 별칭에서 허용되지 않는 특수 문자가 포함되어 있는 경우 그룹 이름에만 적용됩니다. 따라서 이 경우 그룹 이름에 적용되는 접두사와 접미사는 그룹 별칭에 적용된 접두사와 다릅니다.

  > [!NOTE]
  > 이름의 시작 또는 끝을 제외하고 그룹 이름의 아무 곳에나 1000자(.) 또는 하이픈(-)을 사용할 수 있습니다. 이름의 시작 또는 끝을 포함하여 그룹 이름의 아무 곳에나 밑선(_)이 허용됩니다.

- 연결된 Yammer Office 365 사용하는 경우 이름 정책에 @, 에 다음 문자를 사용하지 \# \[ \] 않도록 \<, and \> 합니다. 이러한 문자가 이름 정책에 있는 경우 일반 Yammer 그룹을 만들 수 없습니다.

> [!Tip]
> - 짧은 문자열을 접미사로 사용
> - 값과 함께 특성을 사용합니다.
> - 창의적이지 않은 경우 총 이름 길이는 최대 264자입니다.
> - 업로드 차단된 단어를 조직에서 지정하여 사용을 제한할 수 있습니다.

## <a name="custom-blocked-words"></a>사용자 지정 차단된 단어

그룹 이름 및 별칭에서 차단될 차단된 단어의 콤보로 구분된 목록을 입력할 수 있습니다.

하위 문자열 검색은 수행하지 않습니다. 특히, 사용자가 입력한 이름과 사용자 지정 차단 단어 간의 정확한 일치가 실패를 트리거하는 데 필요합니다.

**다음을 찾아야 합니다.**

- 차단된 단어는 대소문자 미지정입니다.

- 사용자가 차단된 단어를 입력하면 그룹 클라이언트에 차단된 단어가 있는 오류 메시지가 표시됩니다.

- 사용되는 차단된 단어에는 문자 제한이 없습니다.

- 차단된 단어로 설정할 수 있는 단어는 5,000개로 제한됩니다.

## <a name="admin-override"></a>관리자 다시 설정

일부 관리자는 모든 그룹 워크로드 및 끝점에서 이러한 정책에서 제외됩니다. 따라서 이러한 차단된 단어와 원하는 이름 규칙을 사용하여 그룹을 만들 수 있습니다. 다음은 그룹 명명 정책에서 제외된 관리자 역할 목록입니다.

- 전역 관리자

- 파트너 계층 1 지원

- 파트너 계층 2 지원

- 사용자 계정 관리자

## <a name="how-to-set-up-the-naming-policy"></a>이름 정책을 설정하는 방법

이름 정책을 설정하는 경우:

1. 에서 [Azure Active Directory](https://aad.portal.azure.com) **에서 그룹을** **클릭합니다.**
2. 이 **설정** 에서 **이름 정책 을 클릭합니다.**
3. 그룹 이름 **정책 탭을** 선택합니다.
4. 현재 **정책에서** 접두사나 접미사 또는 둘 다를 요구할지 선택하고 적절한 확인란을 선택합니다.
5. 각 **줄에 대해 Attribute** 및 **String을** 선택한 다음 특성 또는 문자열을 지정합니다.
6. 필요한 접두사와 접미사를 추가한 후 저장을 **클릭합니다.**

![Screenshot of the groups naming policy settings in Azure Active Directory.](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>관련 항목

[공동 작업 거버넌스 계획 단계별](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[공동 작업 거버넌스 계획 만들기](collaboration-governance-first.md)

[Azure Active Directory 구성하기 위한 cmdlet](/azure/active-directory/enterprise-users/groups-settings-cmdlets)