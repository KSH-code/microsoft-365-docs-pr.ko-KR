---
title: Advanced eDiscovery에서 변호사-클라이언트 권한 검색 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 고급 eDiscovery 사례의 콘텐츠를 검토할 때 변호사-클라이언트 권한 검색 모델을 사용하여 권한이 부여된 콘텐츠의 기계 학습 기반 검색을 사용할 수 있습니다.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358044"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>Advanced eDiscovery에서 변호사-클라이언트 권한 검색 설정

eDiscovery 프로세스의 검토 단계 중 주요하고 비용이 많이 드는 측면은 권한이 부여된 콘텐츠에 대한 문서를 검토하는 것입니다. Advanced eDiscovery는 이 프로세스를 더 효율적으로 만들기 위해 권한이 부여된 콘텐츠에 대한 기계 학습 기반 검색을 제공합니다. 이 기능을 *변호사-클라이언트 권한 검색이라고 합니다.*

## <a name="how-does-it-work"></a>작동 방식

변호사-클라이언트 권한 검색을 사용하도록 설정하면 검토 집합의 데이터를 분석할 때 검토 집합의 [](analyzing-data-in-review-set.md) 모든 문서가 변호사-클라이언트 권한 검색 모델에 의해 처리됩니다. 이 모델은 다음 두 가지를 재합니다.

- 권한 있는 콘텐츠 - 모델에서는 기계 학습을 사용하여 문서에 본질적으로 합법적인 콘텐츠가 포함되어 있는지 여부를 판단합니다.

- 참가자 - 변호사-클라이언트 권한 검색 설정의 일부로 조직에 대한 변호사 목록을 제출해야 합니다. 그런 다음 이 모델은 문서의 참가자와 변호인 목록을 비교하여 문서에 적어도 한 명 이상의 변호사 참가자가 있는지 여부를 파악합니다.

이 모델에서는 모든 문서에 대해 다음과 같은 세 가지 속성을 생성합니다.

- **AttorneyClientPrivilegeScore:** 문서가 실제로 법적으로 준수할 가능성 점수의 값은 **0에서 1** **사이입니다.**

- **HasAttorney:** 문서 참가자 중 한 명이 변호사 목록에 나열된 경우 이 속성은 **true로** 설정됩니다. 그렇지 않으면 값이 **false입니다.** 조직에서 변호사 목록을 업로드하지 않은 경우 이 값은 **false로** 설정됩니다.

- **IsPrivilege:** 이 속성은 **AttorneyClientPrivilegeScore** 값이 임계값을 초과하거나  문서에 변호사 참가자가 있는 경우 **true로** 설정됩니다. 그렇지 않으면 값이 **false로 설정됩니다.**

다음 스크린샷과 같이 이러한 속성과 해당 값은 검토 집합에 있는 문서의 파일 메타데이터에 추가됩니다.

![파일 메타데이터에 표시된 변호사-클라이언트 권한 속성](../media/AeDAttorneyClientPrivilegeMetadata.png)

이러한 세 속성은 검토 집합 내에서도 검색할 수 있습니다. 자세한 내용은 [검토 집합의 데이터 쿼리를 참조하세요.](review-set-search.md)

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>변호사-클라이언트 권한 검색 모델 설정

변호인 권한 검색 모델을 사용하도록 설정하려면 조직에서 이를 켜고 변호사 목록을 업로드해야 합니다.

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a>1단계: 변호사-클라이언트 권한 검색 켜기

조직의 eDiscovery 관리자(eDiscovery 관리자 역할 그룹의 eDiscovery 관리자 하위 그룹의 구성원)는 Advanced eDiscovery 사례에서 모델을 사용할 수 있도록 해야 합니다.

1. Security & 준수 센터에서 **eDiscovery > 고급 eDiscovery로 이동합니다.**

2. Advanced **eDiscovery** 홈 페이지의 설정  타일에서 전역 분석 설정 **구성을 클릭합니다.**

   !["실험적 기능 구성"을 선택합니다.](../media/AeDExperimentalFeatures.png)

3. 분석 설정 **탭에서** **변호사-클라이언트** 권한 관리 설정을 선택합니다.

4. **변호사-클라이언트 권한** 플라이아웃 페이지에서 토글을 사용하여 기능을 켜고 저장을 **선택합니다.**

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>2단계: 변호사 목록 업로드(선택 사항)

변호사-클라이언트 권한 검색 모델을 전체적으로 활용하고 이전에 설명한 Has **Law** 또는 **Potentially Privileged** detection의 결과를 사용하려면 조직에서 일하는 변호사 및 법률 담당자의 전자 메일 주소 목록을 업로드하는 것이 좋습니다. 

변호사 클라이언트 권한 검색 모델에서 사용할 변호사 목록을 업로드하려면 다음을 실행합니다.

1. 헤더 행 없이 .csv 파일을 만들고 적절한 각 사용자에 대한 전자 메일 주소를 별도의 줄에 추가합니다. 이 파일을 로컬 컴퓨터에 저장합니다.

2. Advanced **eDiscovery** 홈 페이지의 설정  타일에서 실험적 기능 구성을 선택한 다음 **변호사-클라이언트** 권한 관리 설정을 선택합니다.

   **변호사-클라이언트 권한** 페이지가 표시되고 **변호사-클라이언트** 권한 검색 토글이 켜져 있습니다.

   ![변호사-클라이언트 권한 플라이아웃 페이지](../media/AeDUploadAttorneyList.png)

3. **찾아보기를** 선택하고 1단계에서 만든 .csv 파일을 찾아 선택합니다.

4. **저장을** 선택하여 변호사 목록을 업로드합니다.

## <a name="use-the-attorney-client-privilege-detection-model"></a>변호인 권한 검색 모델 사용

이 섹션의 단계에 따라 검토 집합의 문서에 대해 변호사-클라이언트 권한 검색을 사용하세요.

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>1단계: 변호사-클라이언트 권한 검색 모델을 사용하여 스마트 태그 그룹 만들기

검토 프로세스에서 변호사-클라이언트 권한 검색 결과를 보는 주요 방법 중 하나는 스마트 태그 그룹을 사용하는 것입니다. 스마트 태그 그룹은 변호사-클라이언트 권한 검색의 결과를 나타내고 스마트 태그 그룹의 태그 옆에 인라인으로 결과를 보여줍니다. 이렇게 하면 문서 검토 중에 권한이 부여될 수 있는 문서를 빠르게 식별할 수 있습니다. 또한 스마트 태그 그룹의 태그를 사용하여 문서에 권한이 부여되거나 권한이 없는 문서에 태그를 지정할 수도 있습니다. 스마트 태그에 대한 자세한 내용은 [Advanced eDiscovery에서](smart-tags.md)스마트 태그 설정을 참조하세요.

1. 1단계에서 분석한 문서가 포함된 검토 집합에서 검토  집합 관리를 선택한 다음 태그 **관리를 선택합니다.**
 
2. 태그 **아래에서** 그룹 추가 옆에  있는 풀다운을 선택한 다음 스마트 태그 **그룹 추가를 선택합니다.**

   !["스마트 태그 그룹 추가"를 선택합니다.](../media/AeDCreateSmartTag.png)

3. On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege.**

   변호사-클라이언트 **권한이라는** 태그 그룹이 표시됩니다. 이 태그에는 모델에서 생성되는 가능한 결과에 해당하는 **양수** 및 음수라는 두 개의 자식 태그가 포함되어 있습니다. 

   ![변호사-클라이언트 권한 스마트 태그 그룹](../media/AeDAttorneyClientSmartTagGroup.png)

3. 검토에 적합한 태그 그룹과 태그의 이름을 변경합니다. 예를 들어 양수 이름을  **Privileged로,** **음수는** **권한** 없습니다.

### <a name="step-2-analyze-a-review-set"></a>2단계: 검토 집합 분석

검토 집합의 문서를 분석할 때 변호사-클라이언트 권한 검색 모델도 실행됩니다. 그리고 [](#how-does-it-work) 해당 속성(작동 방식에 설명되어 있는 설명)이 검토 집합의 모든 문서에 추가됩니다. 검토 집합에서 데이터를 분석하는 데 대한 자세한 내용은 [Advanced eDiscovery에서](analyzing-data-in-review-set.md)검토 집합의 데이터 분석을 참조하세요.

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>3단계: 스마트 태그 그룹을 사용하여 권한 있는 콘텐츠 검토

검토 집합을 분석하고 스마트 태그를 설정한 후 다음 단계는 문서를 검토하는 것입니다. 모델에서 문서가 잠재적으로 권한이 부여된 것으로 판단되면  태그 지정 패널의 해당 스마트 태그는 변호사-클라이언트 권한 검색에서 생성되는 다음과 같은 결과를 나타냅니다.

- 문서에 본질적으로 법적이 될 수 있는 콘텐츠가 있는 경우 **레이블 Legal** 콘텐츠가 해당 스마트 태그(이 경우 기본 **양수** 태그) 옆에 표시됩니다.

- 문서에 조직의 변호사 목록에 있는 참가자가 있는 경우 해당  스마트 태그 옆에 '변호사' 레이블이 표시됩니다(이 경우 기본 **양수** 태그).

- 문서에 본질적으로 법적이 될 수 있는 콘텐츠가 있으며 참가자가  변호사  목록에 있는 경우 법률 콘텐츠와 변호사 레이블이 모두 표시됩니다.  

모델에서 문서에 본질적으로 합법적인 콘텐츠가 포함되어 있지 않은 경우 또는 변호사 목록의 참가자가 포함되지 않은 것으로 확인되면 태그 지정 패널에 두 레이블이 모두 표시되지 않습니다.

예를 들어 다음 스크린샷에는 두 개의 문서가 나와 있습니다. 첫 번째 콘텐츠에는 본질적으로 합법적인 콘텐츠가 포함되어 있으며 참가자가 변호사 목록에 있습니다. 두 번째는 둘 다 포함하지 않습니다. 따라서 레이블을 표시하지 않습니다.

![변호사 및 법률 콘텐츠 레이블로 문서화](../media/AeDTaggingPanelLegalContentAttorney.png)

![레이블이 없는 문서](../media/AeDTaggingPanelNegative.png)

문서를 검토하여 권한이 부여된 콘텐츠가 포함되어 있는 경우 해당 태그를 지정하여 문서에 태그를 지정하면 됩니다.
