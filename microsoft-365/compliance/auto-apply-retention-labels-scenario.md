---
title: 보존 레이블을 사용하여 SharePoint Online에 저장된 제품 문서의 수명주기 관리
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 솔루션 시나리오에서는 보존 레이블을 사용하여 SharePoint Online에 저장된 제품 관련 문서의 수명 주기를 관리하는 방법을 설명합니다. 이 작업은 문서 메타 데이터를 사용하여 콘텐츠를 분류하고, 특히 보존 레이블을 자동으로 적용하며 이벤트 기반 보존을 구성하여 수행됩니다.
ms.openlocfilehash: 214384fcdf5099f71c36425102bb62866859f910
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636396"
---
# <a name="manage-the-lifecycle-of-sharepoint-documents-with-retention-labels"></a>보존 레이블을 사용하여 SharePoint 문서의 수명 주기 관리

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

이 문서에서는 보존 레이블을 사용하고, 레이블을 자동으로 적용하며, 이벤트 기반 보존을 구성하여 SharePoint Online에 저장된 제품 관련 문서의 수명주기를 관리하는 방법에 대해 설명합니다. 자동 적용 기능은 SharePoint 메타 데이터를 사용하여 문서 분류를 활용합니다. 이 문서의 시나리오는 제품 관련 문서를 기반으로 하지만 다른 시나리오에도 동일한 개념을 사용할 수 있습니다. 예를 들어 석유 및 가스 산업에서는 석유 플랫폼, 석유정 로그 또는 생산 라이선스와 같은 물리적 자산과 관련된 문서의 수명주기를 관리할 수 있습니다. 금융 서비스 산업에서는 은행 계좌, 모기지 또는 보험 계약과 관련된 문서를 관리할 수 있습니다. 공공 부문에서는 건설 허가 또는 세금 양식과 관련된 문서를 관리할 수 있습니다.

이 문서의 시나리오에 대해 살펴보겠습니다. 정보 아키텍처와 보존 레이블의 정의에 대해 살펴보겠습니다. 그런 다음 레이블을 자동으로 적용하여 문서를 분류하고 마지막으로 보존 기간 시작을 실행하는 이벤트를 생성하는 방법을 살펴보겠습니다.

## <a name="information-architecture"></a>정보 아키텍처

이 문서의 시나리오는 SharePoint Online을 사용하여 회사가 개발하는 제품과 관련된 모든 문서를 저장하는 제조 회사를 기준으로 합니다. 이러한 문서에는 제품 사양, 공급자와의 계약 및 사용자 매뉴얼이 포함됩니다. 엔터프라이즈 콘텐츠 관리 정책의 일부로 SharePoint에 이러한 문서를 저장하는 경우, 문서 메타 데이터를 정의하고 사용하여 분류할 수 있습니다. 각 문서에는 다음과 같은 메타 데이터 속성이 있습니다.

- **문서 유형** (예 : 제품 사양, 계약 및 사용자 매뉴얼)

- **제품 이름**

- **상태** (초안 또는 최종)

이 메타 데이터는 모든 문서에 대해 **생산 문서**라는 기본 콘텐츠 유형을 형성합니다.

![제품 설명서에 대한 메타 데이터](../media/SPRetention1.png)

> [!NOTE]
> **문서 유형** 및 **상태** 속성은 시나리오의 뒷부분에 나오는 보존 정책에서 보존 레이블을 분류하고 자동 적용하는 데 사용됩니다.

다양한 유형의 문서를 나타내는 몇 가지 콘텐츠 유형이 있을 수 있지만 제품 문서에 중점을 두겠습니다.

이 시나리오에서는 관리되는 메타 데이터 서비스 및 용어 저장소를 사용하여 **문서 유형**에 대한 용어 집합과 **제품 이름**에 대한 용어 집합을 만듭니다. 각 용어 집합에 대해 각 값에 대한 용어를 만듭니다. SharePoint 조직의 용어 저장소에 다음과 같이 표시됩니다.

![용어 저장소의 제품 설명서에 대한 용어 집합](../media/SPRetention2.png)

콘텐츠 유형은 [콘텐츠 유형 허브](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b)를 사용하여 작성하고 게시할 수 있습니다. 콘텐츠 유형은 또한 [PnP 프로비저닝 프레임워크](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-framework) 또는 [사이트 디자인 JSON 스키마](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type)와 같은 사이트 제공 도구를 사용하여 만들고 게시할 수도 있습니다.

각 제품에는 하나의 문서 라이브러리가 포함된 전용 SharePoint Online 사이트가 있으며 올바른 콘텐츠 유형이 활성화되어 있습니다. 모든 문서는 이 문서 라이브러리에 저장됩니다.

![제품 설명서에 대한 문서 라이브러리](../media/SPRetention3.png)

> [!NOTE]
> 이 시나리오의 제조 회사는 제품별로 SharePoint Online 사이트를 보유하는 대신 지속적인 채팅과 같은 팀 구성원과의 공동 작업을 지원하는 팀 단위의 제품 별 Microsoft Team을 사용하고 문서 관리를 위해 팀의 **파일** 탭을 사용할 수 있습니다. 이 문서에서는 단지 문서에만 중점을 두므로 사이트만 사용하겠습니다.

다음은 스피닝 위젯 제품의 문서 라이브러리 보기입니다.

![스피닝 위젯 문서 라이브러리](../media/SPRetention4.png)

이제 문서 관리를 위한 기본 정보 아키텍처가 준비되었으므로 메타 데이터 및 문서 분류를 사용하는 문서의 보존 및 폐기 전략을 살펴보겠습니다.

## <a name="retention-and-disposition"></a>보존 및 폐기

제조 회사의 규정 준수 및 데이터 거버넌스 정책에 따라 데이터 보존 및 폐기 방법이 결정됩니다. 제품 관련 문서는 제품이 제조되는 동안 및 그 이후 일정 기간동안 보관해야합니다. 이 기간은 제품 사양, 계약 및 사용자 매뉴얼에 따라 다릅니다. 다음 표는 보존 및 폐기 요구 사항을 나타냅니다.

| **문서 유형**          | **보존**                          | **폐기**                              |
| -------------------------- | -------------------------------------- | -------------------------------------------- |
| 제품 사양      | 생산 중단 이후 5년  | 삭제                                       |
| 제품 계약          | 생산 중단 이후 10년 | 검토                                       |
| 사용자 매뉴얼                | 생산 중단 이후 5년  | 삭제                                       |
| 다른 모든 유형의 문서 | 다른 문서를 적극적으로 보존하지 않음  | 문서가 3년보다 오래된 경우 삭제<sup>\*</sup>  |
|||

> [!NOTE]
> <sup>\*</sup> 지난 3년 동안 수정하지 않은 문서는 3년이 지난 것으로 간주됩니다.

보안 및 준수 센터를 사용하여 다음과 같은 보존 레이블을 만듭니다.

  - 제품 사양

  - 제품 계약

  - 사용자 매뉴얼

이 문서에서는 제품 사양 보존 레이블을 작성하고 자동 적용하는 방법만을 보여줍니다. 전체 시나리오를 구현 하려면 다른 두 개의 문서 유형에 대한 보존 레이블을 만들어 자동 적용합니다.

### <a name="settings-for-the-product-specification-retention-label"></a>제품 사양 보존 레이블 설정

제품 사양 보존 레이블에 대한 [파일 계획](file-plan-manager.md)은 다음과 같습니다. 

- **이름:** 제품 사양

- **관리자를 위한 설명:** 제품 사양 레이블, 생산 중단 이후 5년 간 보존, 자동 삭제, 이벤트 기반 보존, 이벤트 유형은 제품 중단입니다.

- **사용자를 위한 설명:** 생산 중단 이후 5년 간 보존

- **보존 작업:** 유지 및 삭제

- **보존 기간:** 5년 (1,825일)

- **레코드 레이블**: 콘텐츠를 [레코드](labels.md#using-retention-labels-for-records-management)로 분류하기 위해 보존 레이블을 구성합니다. (레코드로 분류된 문서는 사용자가 수정하거나 삭제할 수 없음)

- **파일 계획 설명자:** (시나리오 단순화를 위해 파일 설명자가 제공되지 않음)

다음 스크린샷은 보안 및 준수 센터에서 제품 사양 [보존 레이블](labels.md)을 만들 때의 설정을 보여줍니다. 보존 레이블을 만들 때 **제품 중단** 이벤트 유형을 만들 수 있습니다. 아래 단계를 참조하세요.

![제품 사양 보존 레이블 설정](../media/SPRetention5.png)

> [!NOTE]
> 실용적인 목적 및 문서가 자동으로 삭제되는 것을 보기 위해 5년 간 기다려야 하는 것을 방지하려면, 테스트 환경에서 이 시나리오를 재작성하는 경우 보존 기간을 1일로 설정합니다.

### <a name="create-an-event-type-when-creating-a-retention-label"></a>보존 레이블을 만들 때 이벤트 유형 만들기

1. 드롭다운 목록의 **콘텐츠를 보존 또는 삭제**에서 **이벤트**를 선택합니다.

2. **이벤트 유형 선택**을 선택합니다.

   ![제품 사양 레이블에 대한 새 이벤트 유형 만들기](../media/SPRetention6.png)

3. **이벤트 유형 선택** 페이지에서, **여기에서 새 이벤트 유형을 만들 수 있습니다**를 선택합니다.

4. **제품 중단**이라는 이벤트 유형을 만들고 설명을 입력한 후 **완료**를 선택하여 만듭니다. 

5. **이벤트 유형 선택** 페이지로 돌아간 후 사용자가 만든 **제품 중단** 이벤트 유형을 선택한 다음 **추가**를 선택합니다.

제품 사양 보존 레이블의 설정은 다음과 같습니다. **이 레이블 만들기**를 선택하여 만듭니다.

![새 제품 사양 레이블 설정](../media/SPRetention7.png)

> [!TIP]
> 자세한 단계는 [보존 기간이 이벤트를 기반으로 하는 레이블 만들기](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event)를 참조하세요.

이제 보존 레이블을 생성했으므로 보존 레이블을 제품 사양 컨텐츠에 자동 적용하는 방법을 살펴보겠습니다.

## <a name="classifying-content-by-auto-applying-retention-labels"></a>보존 레이블을 자동 적용하여 콘텐츠 분류

KQL (키워드 쿼리 언어)을 사용하여 이 시나리오를 위해 만든 보존 레이블을 [자동 적용](labels.md#applying-a-retention-label-automatically-based-on-conditions)합니다. KQL은 검색 쿼리를 작성하는 데 사용되는 언어입니다. KQL에서는 키워드 또는 관리 속성을 사용하여 검색할 수 있습니다. KQL에 대한 자세한 내용은 <https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference>을 참조하세요.

개략적으로 Microsoft 365에 "**최종** **상태** 및 **문서 유형**이 **제품 사양**인 모든 문서에 **제품 사양** 보존 레이블을 적용"하라고 주문하고 싶습니다. **상태** 및 **문서 유형**은 [정보 아키텍처](#information-architecture) 섹션에서 제품 문서 콘텐츠 유형에 대해 이전에 정의했던 사이트 열입니다. 이를 위해서는 검색 스키마를 구성해야 합니다.

SharePoint는 콘텐츠를 인덱싱할 때 각 사이트 열에 대해 크롤링된 속성을 자동으로 생성합니다. 이 시나리오에서 우리는 **문서 종류** 및 **상태** 속성에 관심이 있습니다. 검색시 크롤링된 속성을 만들려면 올바른 콘텐츠 유형을 사용하는 라이브러리에 문서가 필요하고, 또한 사이트 열이 채워져 있어야합니다.

SharePoint 관리 센터에서 검색 구성을 열고 **검색 스키마 관리**를 선택하여 크롤링된 속성을 확인하고 이를 구성할 수 있습니다.

![검색 스키마의 크롤링된 속성](../media/SPRetention8.png)

**크롤링된 속성** 상자에 **상태**를 입력하고 녹색 화살표를 선택하면 다음과 같은 결과가 표시됩니다.

![ows_Status 크롤링된 속성](../media/SPRetention9.png)

우리가 관심을 가지고 있는 속성은 **ows\_\_상태** (이중 밑줄에 주목)입니다. 이는 생산 문서 콘텐츠 유형의 **상태** 속성에 매핑됩니다.

이제 **ows\_문서**를 입력하고 녹색 화살표를 선택하면 다음과 같이 표시됩니다.

![Ows_Doc_Type 크롤링된 속성](../media/SPRetention10.png)

**ows\_문서\_x0020\_유형** 속성은 우리가 관심있는 두 번째 속성입니다. 이는 프로덕션 문서 콘텐츠 유형의 **문서 유형** 특성에 맵핑됩니다.

> [!TIP]
> 이 시나리오의 크롤링된 속성 이름을 확인하려면 생산 문서가 포함된 문서 라이브러리로 이동한 다음 라이브러리 설정으로 이동합니다. **열**에서 열 이름 (예: **상태** 또는 **문서 유형**)을 선택하여 사이트 열 페이지를 엽니다. 해당 페이지의 URL에서 **필드** 매개 변수에 필드 이름이 포함되어 있습니다. "ows_" 접두사가 붙는 필드 이름은 크롤링된 속성의 이름입니다. 예를 들어 URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status`은 **ows\_\_상태** 크롤링된 속성에 해당합니다.

원하는 크롤링된 속성이 SharePoint 관리 센터의 검색 스키마 관리 섹션에 나타나지 않으면 다음 중 하나일 수 있습니다.

- 문서가 인덱싱되지 않았습니다. 문서 라이브러리 설정 > 고급 설정으로 이동하여 라이브러리를 강제로 다시 인덱싱할 수 있습니다.

- 문서 라이브러리가 최신 사이트에 있는 경우 SharePoint 관리자도 사이트 모음 관리자인지 확인합니다.

크롤링된 속성과 관리 속성에 대한 자세한 내용은 [SharePoint Server에서 자동으로 작성된 관리 속성](https://docs.microsoft.com/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint)을 참조하세요.

### <a name="mapping-crawled-properties-to-pre-defined-managed-properties"></a>크롤링된 속성을 사전 정의된 관리 속성에 매핑

KQL은 검색 쿼리에서 크롤링된 속성을 사용할 수 없습니다. 관리 속성을 사용해야 합니다. 일반적인 검색 시나리오에서는 관리 속성을 만들어 필요한 크롤링된 속성에 매핑합니다. 그러나 자동 적용된 보존 레이블의 경우 사용자 지정 관리 속성이 아닌 KQL 사전 정의 관리 속성에서만 지정할 수 있습니다. 문자열 RefinableString00에서 RefinableString199까지 사용할 수 있도록 시스템에 이미 사전 정의된 관리 속성 집합이 있습니다. 전체 목록은 [기본 미사용 관리 속성](https://docs.microsoft.com/sharepoint/manage-search-schema#default-unused-managed-properties)을 참조하세요. 이러한 기본 관리 속성은 일반적으로 검색 구체화를 정의하는 데 사용됩니다.

KQL 쿼리를 사용하여 올바른 보존 레이블을 제품 문서 내용에 자동으로 적용하기 위해 크롤링된 속성 **ows\_문서\_x0020\_유형**과 **ows\_\_상태**를 두 개의 정의 가능한 관리 속성에 맵핑합니다. 이 시나리오의 테스트 환경에서는 **RefinableString00** 및 **RefinableString01**은 사용되지 않습니다. 이를 위해 SharePont 관리 센터의 **검색 스키마 관리**에서 **관리 속성**을 살펴보았습니다.

![검색 스키마의 관리 속성](../media/SPRetention12.png)

이전 스크린 샷의 **매핑된 크롤링 속성** 열이 비어있는 것을 주목하세요.

**ows\_문서\_x0020\_유형** 크롤링된 속성에 매핑하려면 다음을 실행합니다.

1. **관리 속성** 필터 상자에 **RefinableString00**을 입력하고 녹색 화살표를 선택합니다.

2. 결과 목록에서 **RefinableString00** 링크를 선택한 다음 아래로 스크롤하여 **크롤링된 속성에 매핑** 섹션으로 이동합니다.  

3. **매핑 추가**를 선택하고 **크롤링된 속성 선택** 창의 **크롤링된 속성 이름 검색** 상자에 **ows\_문서\_x0020\_유형**을 입력합니다. **찾기**를 선택합니다.  

4. 결과 목록에서 **ows\_문서\_x0020\_유형**을 선택한 다음 **확인**을 선택합니다.

   **맵핑된 크롤링 속성** 섹션에 다음 스크린샷과 유사한 내용이 표시됩니다.

   ![맵핑된 크롤링 속성 섹션에서 맵핑 추가를 선택합니다.](../media/SPRetention13.png)

5. 페이지 맨 아래로 스크롤하고 **확인**을 선택하여 맵핑을 저장합니다.

이 절차를 반복하여 RefinableString01과 ows\_\_상태를 맵핑합니다.

이제 두 개의 크롤링된 속성에 맵핑된 두 가지 관리 속성이 있습니다.

![크롤링 속성은 관리 속성에 매핑됩니다.](../media/SPRetention14.png)

엔터프라이즈 검색을 실행하여 이 모든 것이 올바르게 설정되었는지 확인하겠습니다. 브라우저에서 https://yourtenant.sharepoint.com/search로 이동합니다. 검색 상자에 **RefinableString00:"제품 사양"** 을 입력하고 엔터키를 누릅니다. 이렇게 하면 제품 사양을 포함하는 모든 문서를 **문서 유형**으로 반환합니다.

이제 검색 상자에 **RefinableString00:"Product Specification" AND RefinableString01:Final**을 입력하고 엔터키를 누릅니다. 이 경우 제품 사양을 포함하는 모든 문서를 **문서 유형**으로 또한 **최종**상태가 반환됩니다.

### <a name="creating-the-auto-apply-label-policies"></a>자동 적용 레이블 정책 만들기

이제 KQL 쿼리가 올바르게 작동하는지 확인했으므로 KQL 쿼리를 사용하여 제품 사양 보존 레이블을 해당 문서에 자동으로 적용하는 레이블 정책을 작성하겠습니다.

1. [보안 및 준수 센터](https://protection.office.com)에서 **분류** > **보존 레이블**로 이동한 다음 **레이블 자동 적용**을 선택합니다. 

   ![레이블 페이지에서 레이블 자동 적용을 선택합니다.](../media/SPRetention16.png)

2. **자동 적용할 레이블 선택** 마법사 페이지에서 **자동 적용할 레이블 선택**을 선택합니다.

3. 레이블 목록에서 **제품 사양**을 선택하고 **추가**를 선택한 후 **다음**을 선택합니다.

4. **특정 단어나 구를 포함하는 콘텐츠에 레이블 적용**을 선택한 후 **다음**을 선택합니다.

   ![특정 단어나 구 또는 속성을 포함하는 콘텐츠에 레이블 적용을 선택합니다.](../media/SPRetention17.png)

   다음 단계에서는 이전 섹션에서 테스트한 것과 동일한 KQL 검색 쿼리를 제공합니다. 기억 하시겠지만, 이 쿼리는 최종 상태인 모든 제품 사양 문서를 반환했습니다. 레이블 정책에서 이와 동일한 쿼리를 사용하면 제품 사양 보존 레이블이 해당 검색 쿼리와 일치하는 모든 문서에 자동으로 적용됩니다.

5. **키워드 쿼리 편집기** 상자에서 **RefinableString00:"Product Specification" AND RefinableString01:Final**을 입력하고 **다음**을 선택합니다.

   ![키워드 쿼리 편집기 상자에서 쿼리를 지정합니다.](../media/SPRetention19.png)

6. 이름(예: **제품 사양 레이블 자동 적용**)과 레이블 정책에 대한 설명(선택 사항)을 입력한 후 **다음**을 선택합니다. 

7. **위치 선택** 마법사 페이지에서 정책을 적용하려는 콘텐츠 위치를 선택합니다. 이 시나리오에서는 모든 생산 문서가 SharePoint 문서 라이브러리에만 저장되므로 SharePoint 위치에만 정책을 적용합니다. 따라서 **직접 특정 위치 선택**을 선택하고 Exchange 전자 메일, OneDrive 계정 및 Microsoft 365 그룹 상태를 해제로 전환한 후 SharePoint 사이트 상태가 설정되어 있는지 확인합니다. 

    ![특정 사이트를 선택하여 레이블을 자동 적용할 수 있습니다.](../media/SPRetentionSPlocations.png)

   > [!TIP]
   > 정책을 모든 SharePoint 사이트에 적용하는 대신 **사이트 선택**을 선택하여 특정 SharePoint 사이트의 URL을 추가할 수 있습니다.

8. **다음**을 선택하여 **설정 검토** 페이지를 표시합니다. 

    ![레이블 자동 적용 설정](../media/SPRetention18.png)

9. **자동 적용**을 선택하여 레이블 정책을 만듭니다. 사용자가 제공한 KQL 검색 쿼리와 일치하는 모든 문서에 제품 사양 레이블을 자동으로 적용하는 데 최대 7일이 걸립니다.

### <a name="verifying-the-retention-label-was-automatically-applied"></a>보존 레이블이 자동으로 적용되었는지 확인

7일 후, 보안 및 준수 센터에서 [레이블 활동 탐색기](view-label-activity-for-documents.md)를 사용하여 앞서 작성한 레이블 정책이 이 시나리오의 보존 레이블을 제품 문서에 자동으로 적용했는지 확인합니다. 이 문서에서 이러한 보존 레이블과 레이블 정책 만들기에 대해 설명하지는 않았지만 다음 스크린샷에서 제품 계약과 사용자 매뉴얼에도 보존 레이블이 적용되었음을 알 수 있습니다.

![레이블 활동 탐색기를 사용하여 레이블이 자동 적용되었는지 확인합니다.](../media/SPRetention20.png)

또 다른 확인 단계는 문서 라이브러리의 문서 속성을 확인하는 것입니다. 정보 패널에서 보존 레이블이 선택된 문서에 적용되어 있음을 확인할 수 있습니다.

![문서 라이브러리에서 문서 속성을 확인하여 레이블이 적용되었는지 확인합니다.](../media/SPRetention21.png)

보존 레이블이 문서에 자동으로 적용되었으므로 보존 레이블이 문서를 레코드로 선언하도록 구성되었기 때문에 문서가 삭제되지 않습니다. 이 보호 기능의 예로 이러한 문서 중 하나를 삭제하려고 하면 다음 스크린샷에 표시된 오류 메시지가 나타납니다.

![레이블이 문서 레코드를 선언하므로 문서를 삭제할 수 없습니다.](../media/SPRetention22.png)

## <a name="generating-the-events-that-trigger-the-start-of-the-retention-period"></a>보존 기간 시작을 트리거하는 이벤트 생성

이제 보존 레이블이 자동으로 적용되었으므로 특정 제품의 생산 종료를 나타내는 이벤트에 중점을 두겠습니다. 이 이벤트가 발생하면 문서에 자동으로 적용된 보존 레이블에 정의된 보존 기간의 시작을 트리거합니다. 예를 들어 제품 사양 문서의 경우 "생산 종료" 이벤트가 트리거되면 5년의 보존 기간이 시작됩니다.

**레코드 관리** > **이벤트**로 이동하여 이벤트 유형을 선택한 후 올바른 자산 ID를 설정하고 이벤트 날짜를 입력하여 보안 및 준수 센터에서 이벤트를 수동으로 만들 수 있습니다. 자세한 내용은 [이벤트 기반 보존의 개요](event-driven-retention.md)를 참조하세요.

이 시나리오에서는 외부 생산 시스템에서 이벤트를 생성하여 자동으로 작성합니다. 이 경우 이벤트를 생성하는 시스템은 제품이 생산 중인지 여부를 나타내는 간단한 SharePoint 목록 및 그과 관련된 [Microsoft Flow](https://docs.microsoft.com/flow/getting-started)이며, 이것이 이벤트를 트리거합니다. 실제 시나리오에서는 HR 또는 CRM 시스템과 같이 이벤트를 생성하는 모든 시스템이 될 수 있습니다. Flow에는 Exchange, SharePoint, Teams 및 Dynamics 365와 같은 Microsoft 365 워크로드뿐만 아니라 Twitter, Box, Salesforce 및 Workdays와 같은 타사 앱을 위한 다양하고 즉시 사용 가능한 상호 작용 및 구성 요소가 포함되어 있습니다. 따라서 Flow를 이러한 시스템과 쉽게 통합할 수 있습니다. 자세한 내용은 [이벤트 기반 보존의 자동화](automate-event-driven-retention.md)를 참조하세요.

다음 스크린샷은 이벤트를 트리거하는 데 사용되는 SharePoint 목록을 보여줍니다. 

![보존 이벤트를 트리거하도록 하는 데 사용되는 목록](../media/SPRetention23.png)

현재 생산중인 두 가지 제품이 있으며 **생산 중** 열에 **예** 값으로 표시됩니다. 이 열의 값을 제품에 대해 **아니요**로 설정하면 목록과 관련된 흐름에서 자동으로 이벤트를 생성합니다. 그러면 해당 제품 문서에 자동으로 적용된 보존 레이블의 보존 기간 시작이 트리거됩니다.

이 시나리오에서는 다음 흐름을 사용하여 이벤트를 트리거합니다.

![이벤트를 트리거하는 흐름의 구성](../media/SPRetention24.png)

이 흐름을 만들려면 SharePoint 커넥터에서 시작하여 **항목을 만들거나 수정할 때** 트리거를 선택합니다. 사이트 주소와 목록 이름을 지정한 다음 **생산 중** 목록 열 값이 **아니오**로 설정되는 경우를 기준으로 조건을 추가합니다 (또는 조건 카드에서 false와 같은 경우). 그런 다음 기본 제공 HTTP 서식 파일을 기반으로 하는 작업을 추가합니다. 다음 섹션의 값을 사용하여 HTTP 작업을 구성합니다. 아래 섹션에서 URI와 Body 속성의 값을 복사하여 서식 파일에 붙여넣을 수 있습니다.

- **메서드**: POST
- **URI**: https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
- **헤더**: Key = Content-Type, Value = application/atom+xml
- **Body**:

```HTML
<?xml version='1.0' encoding='utf-8' standalone='yes'>
<entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices' xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata' xmlns='https://www.w3.org/2005/Atom'>
<category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent'>
<updated>9/9/2017 10:50:00 PM</updated>
<content type='application/xml'>
<m:properties>
<d:Name>Cessation Production @{triggerBody()?['Product_x0020_Name']?['Value']}</d:Name>
<d:EventType>Product Cessation&lt;</d:EventType>
<d:SharePointAssetIdQuery>ProductName:&quot;@{triggerBody()?['Product_x0020_Name']?['Value']}<d:SharePointAssetIdQuery>
<d:EventDateTime>@{formatDateTime(utcNow(),'yyyy-MM-dd')}</d:EventDateTime>
</m:properties>
</content&gt>
</entry>
```

다음 표에서는 이 시나리오에 맞게 구성해야 하는 작업의 *Body* 속성에 포함된 매개 변수를 설명합니다.

- **Name**: 이 매개 변수는 보안 및 규정 준수 센터에서 생성되는 이벤트 이름을 지정합니다. 이 시나리오에서, 이름은 "Cessation Production xxx"입니다. 여기서 xxx는 앞에서 만든 ProductName 관리 속성의 값입니다.
- **EventType**: 이 매개 변수의 값은 생성된 이벤트가 적용되는 이벤트 유형에 해당합니다. 이 이벤트 유형은 보존 레이블을 생성할 때 정의되었습니다. 이 시나리오의 경우 이벤트 유형은 "Product Cessation"입니다.
- **SharePointAssetIdQuery**: 이 매개 변수는 이벤트의 자산 ID를 정의합니다. 이벤트 기반 보존에는 문서에 대한 고유 식별자가 필요합니다. 자산 ID를 사용하여 특정 이벤트가 적용 가능한 문서를 식별하거나 이 시나리오에서와 같이 메타데이터 열, 고유한 제품 이름을 사용할 수 있습니다. 이렇게 하려면 KQL 쿼리에 사용할 수 있는 ProductName이라는 새 관리 속성을 만들어야 합니다 (또는 새 관리 속성을 만드는 대신 RefinableString00을 사용할 수도 있음). 또한 이 새로운 관리 속성을 ows_Product_x0020_Name 크롤링된 속성에 맵핑해야합니다. 다음은 이 관리 속성의 스크린샷입니다.

    ![보존 관리 속성](../media/SPRetention25.png)

- **EventDateTime**: 이 매개 변수는 이벤트 발생 날짜를 정의합니다. 현재 날짜 형식 *formatDateTime(utcNow(),'yyyy-MM-dd'*)을 사용합니다.

### <a name="putting-it-all-together"></a>모든 항목 요약

이제 보존 레이블이 만들어지고 자동 적용되며 흐름을 구성하고 작성했으므로 제품 목록에서 스피닝 위젯 제품에 대한 **생산 중**열에 있는 값이 **예**에서 **아니요**로 변경될 때 발생하는 상황은 다음과 같습니다. 흐름이 트리거되고 이벤트가 생성됩니다. 보안 및 준수 센터에서 이 이벤트를 보려면 **레코드 관리** > **이벤트**로 이동합니다.

![보안 및 준수 센터의 이벤트 페이지에 표시되는 흐름으로 트리거되는 이벤트](../media/SPRetention28.png)

이벤트를 선택하여 플라이 아웃 페이지에서 세부 정보를 확인합니다. 이벤트를 만든 후에도 이벤트 상태의 세부 정보에는 SharePoint 사이트 또는 문서가 처리되지 않은 것으로 표시됩니다.

![이벤트 세부 정보](../media/SPRetention29.png)

그러나 일정 시간이 지나면 이벤트 상태 섹션에 SharePoint 사이트 및 SharePoint 문서가 처리된 것으로 표시됩니다.  

![이벤트 세부 정보는 문서가 처리된 것으로 표시합니다.](../media/SPRetention31.png)
 
이는 생산 중단 스피닝 위젯 이벤트의 이벤트 날짜를 기준으로 스피닝 위젯 제품 문서에 적용된 레이블의 보존 기간이 시작되었음을 의미합니다. 1일 보존 기간을 구성하여 테스트 환경에서 시나리오를 구현한 경우에는 해당 이벤트를 만든 다음 며칠이 지난 후에 제품 문서를 볼 수 있는 문서 라이브러리로 이동하여 문서가 삭제되었는지 확인할 수 있습니다 (SharePoint의 삭제 작업을 실행한 후).

### <a name="more-about-asset-ids"></a>자산 ID에 대한 자세한 정보

[이벤트 기반 보존 개요](event-driven-retention.md)에서 설명했듯이 이벤트 유형, 레이블, 이벤트 및 자산 ID간의 관계를 이해하는 것이 중요합니다. 자산 ID는 SharePoint 및 OneDrive의 또 다른 문서 속성입니다. 이를 통해 이벤트에 의해 보존 기간이 시작되는 문서를 추가로 식별하는 데 도움이 됩니다. 기본적으로 SharePoint에는 이벤트 기반 보존에 사용할 수 있는 자산 ID 속성이 있습니다.

![문서 속성 세부 정보 페이지에서 표시되는 자산 ID 속성](../media/SPRetention26.png)

다음 스크린샷에 표시된대로 자산 ID 관리 속성을 **ComplianceAssetId**라고 합니다.

![ComplianceAssetId 관리 속성](../media/SPRetention27.png)

이 시나리오에서와 같이 기본 자산 ID 속성을 사용하는 대신 다른 속성을 사용할 수도 있습니다. 그러나 이벤트에 대해 자산 ID 또는 키워드를 지정하지 않으면 해당 이벤트 유형의 레이블이 있는 모든 콘텐츠가 이벤트에 의해 트리거된 보존 기간을 갖게 됩니다.

### <a name="using-advanced-search-in-sharepoint"></a>SharePoint에서 고급 검색 사용

이전 스크린샷에서 **ComplianceTag**라는 보존 레이블과 관련된 다른 관리 속성이 있으며, 이는 크롤링된 속성에 맵핑되어 있음을 확인할 수도 있습니다. **ComplianceAssetId** 관리 속성도 크롤링된 속성에 맵핑되어 있습니다. 이는 고급 검색에서 이러한 관리 속성을 사용하여 보존 레이블로 태그가 지정된 모든 문서를 검색할 수 있음을 의미합니다.

## <a name="summary"></a>요약

이 문서에서는 SharePoint의 사이트 열을 기반으로 보존 레이블을 자동으로 적용한 문서 관리 시나리오를 보여줍니다. 그런 다음 이벤트 기반 보존 및 Microsoft Flow를 사용하여 외부 이벤트를 기반으로 보존 기간 시작을 자동으로 트리거했습니다.

## <a name="credits"></a>크레딧

이 시나리오의 작성자는 다음과 같습니다. 

Frederic Lapierre<br/>Principal Consultant, Microsoft Services
