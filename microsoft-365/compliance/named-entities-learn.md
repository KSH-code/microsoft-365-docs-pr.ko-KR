---
title: 명명된 엔터티에 대해 자세히 보기(미리 보기)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 명명된 엔터티가 데이터 손실 방지 정책을 통해 사람, 실제 주소 및 의료 용어가 포함된 중요한 항목을 검색하는 데 어떻게 도움이 되는지 확인
ms.openlocfilehash: 22019e3f3a270c6205b788a48544e2a462d9dfa7
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661906"
---
# <a name="learn-about-named-entities-preview"></a>명명된 엔터티에 대해 자세히 보기(미리 보기)

> [!IMPORTANT]
> 명명된 엔터티 기능은 롤아웃 중으로, 사용 가능한 경우 테넌트에 표시됩니다. 콘텐츠 탐색기 및 DLP(데이터 손실 방지) 정책 작성 흐름에서 해당 정책을 검사합니다. 

*명명된 엔터티는* [SIT(중요한 정보](sensitive-information-type-learn-about.md) 유형)입니다. 이러한 분류자는 사람 이름, 실제 주소 및 의료 약관을 검색하는 데 사용할 수 있는 복잡한 사전 및 패턴 기반 분류자입니다. 중요한 정보 유형에 대한 데이터 **분류 > 규정 > 있습니다.** 다음은 SITS를 사용할 수 있는 부분 목록입니다.

- [DLP(데이터 손실 방지 정책)](dlp-learn-about-dlp.md) 
- [민감도 레이블](sensitivity-labels.md)
- [내부자 위험 관리](insider-risk-management-solution-overview.md)
- [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)

DLP는 조직 요구에 맞게 사용자 지정할 수 있는 미리 구성된 DLP 정책인 고급 정책 템플릿에서 명명된 엔터티를 특별히 활용합니다. 또한 빈 [](create-a-dlp-policy-from-a-template.md) [템플릿에서 자체 DLP](create-test-tune-dlp-policy.md) 정책을 만들고 명명된 ENTITY SIT를 조건으로 사용할 수 있습니다.

<!-- There are many other SITs that detect strings like social security, credit card, or bank account numbers to identify sensitive items. For more information, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md).-->



## <a name="examples-of-named-entity-sits"></a>명명된 엔터티 SITS의 예

명명된 엔터티 SITS는  번들화 및 번들화되지 않은 두 가지로 *제공*

번들로 묶인 명명된 엔터티 SITS는 가능한 모든 일치를 검색합니다. 중요한 항목을 검색하기 위한 DLP 정책에서 광범위한 기준으로 사용할 수 있습니다.

번들화되지 않은 명명된 엔터티 SITS는 단일 국가와 같이 더 좁은 포커스를 가지고 있습니다. 검색 범위가 더 좁은 DLP 정책이 필요한 경우 이 정책을 사용 합니다.
 
다음은 명명된 엔터티 SITS의 몇 가지 예입니다. 이 중 52개는 준수 센터 및 데이터 분류 > 중요한 정보 > **있습니다.**

|명명된 엔터티 |설명  |번들/번들화되지 않은  |
|---------|---------|---------|
|모든 전체 이름    |모든 가능한 전체 이름 일치를 검색합니다.         |   bundled      |
|모든 실제 주소    |가능한 모든 실제 주소 일치를 검색합니다.     | bundled |
|모든 의료 약관    |가능한 모든 의료 약관 일치를 검색합니다. |bundled |
|오스트레일리아 실제 주소 |  오스트레일리아의 실제 주소와 관련된 패턴을 검색합니다. |unbundled |
|피검사 약관     |'hCG'처럼 피 검사와 관련된 용어를 검색합니다. 영어 용어만 해당합니다.      |unbundled |
|브랜드 명칭     |브랜드 인지도의 이름(예: 'Tylenol')을 검색합니다. 영어 용어만 해당합니다.         |unbundled |

## <a name="examples-of-enhanced-dlp-policies"></a>향상된 DLP 정책의 예

다음은 명명된 엔터티 SITS를 사용하는 향상된 DLP 정책의 몇 가지 예입니다. 이 중 10개는 정책 만들기에서 데이터 손실 > **준수 센터에서 > 있습니다.** 향상된 템플릿은 DLP 및 자동 레이블 지정에서 사용할 수 있습니다.

|정책 범주  |서식 파일  |설명  |
|---------|---------|---------|
|금융|미국 GLBA(Gramm-Leach-Bliley Act) 고급         |GLBA(Gramm-Leach-Bliley Act)의 구속을 받는 정보(예: 사회 보장 번호 또는 신용 카드 번호)가 있는지 여부를 검색할 수 있습니다. 이 향상된 템플릿은 사용자 전체 이름(미국/영국)도 검색하여 원본을 확장합니다. passport number, U.S. driver's license number and U.S. physical addresses.         |
| 의료 및 건강   |HRIP Act(호주 보건 기록법) 강화         |일반적으로 호주에서 HRIP(Health Records and Information Privacy - 보건 기록 및 정보 보호) 법의 구속을 받는 것으로 간주되는 정보(예: 의료 계정 번호 및 세금 파일 번호)가 있는지 여부를 검색할 수 있습니다. 이 향상된 템플릿은 사용자 전체 이름, 의료 약관 및 오스트레일리아 실제 주소를 검색하여 원본을 확장합니다.         |
|개인 정보   |GDPR(일반 데이터 보호 규정) 강화         | EU(유럽 연합) 내부 개인의 개인 정보 유무를 검색하여 GDPR 개인 정보 보호 의무를 충족하는 데 도움을 줄 수 있습니다. 이 향상된 템플릿은 EU 국가에 대한 사용자 전체 이름 및 실제 주소를 검색합니다.        |


## <a name="next-steps"></a>다음 단계

- [데이터 손실 방지 정책에 명명된 엔터티 사용(미리 보기)](named-entities-use.md)


## <a name="for-further-information"></a>자세한 내용은
<!--- [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [중요한 정보 유형에 대한 자세한 정보](sensitive-information-type-learn-about.md)
- [사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type.md)
- [PowerShell에서 사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [DLP(데이터 손실 방지 정책)](data-loss-prevention-policies.md) 
- [민감도 레이블](sensitivity-labels.md)
- [보존 레이블](retention.md)
- [커뮤니케이션 규정 준수](communication-compliance.md)
- [자동레이블 정책](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [DLP 정책 생성, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md) 
