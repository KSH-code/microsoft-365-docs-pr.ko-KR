---
title: 사이트에 저장된 중요한 데이터를 찾기 위한 쿼리 작성
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: SharePoint Online의 DLP(데이터 손실 방지)를 사용하여 테넌트 전체에서 중요한 데이터가 포함된 문서를 검색합니다.
ms.openlocfilehash: b6a0943aa4e71b61c5f430034d9e445462eebde7
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817707"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>사이트에 저장된 중요한 데이터를 찾기 위한 쿼리 작성

사용자들은 종종 신용 카드 번호, 사회 보장 번호 또는 개인 정보와 같은 중요한 데이터를 사이트에 저장하며, 시간에 지나면서 이로 인해 조직은 심각한 데이터 손실 위험에 처할 수 있습니다. 비즈니스용 OneDrive 사이트를 포함하여 사이트에 저장된 문서는 정보에 액세스할 수 없는 조직 외부의 사용자와 공유할 수 있습니다. SharePoint Online의 DLP(데이터 손실 방지)를 사용하면 테넌트 전체에서 중요한 데이터가 포함된 문서를 검색할 수 있습니다. 문서를 검색한 후 문서 소유자와 함께 작업하여 데이터를 보호할 수 있습니다. 이 항목은 중요한 데이터를 검색하는 쿼리를 작성하는 데 도움이 될 수 있습니다.
  
> [!NOTE]
> 전자 검색 또는 eDiscovery 및 DLP는 [SharePoint Online 계획 2가 필요한 고급 기능입니다.](https://go.microsoft.com/fwlink/?LinkId=510080) 
  
## <a name="forming-a-basic-dlp-query"></a>기본 DLP 쿼리 작성

기본 DLP 쿼리는 중요한 정보 유형, 개수 범위 및 신뢰도 범위의 세 부분으로 구성됩니다. 다음 그림과 같이 **SensitiveType:" \<type\> "은** 필수이며 둘 **|\<count range\>** 다 선택 **|\<confidence range\>** 사항입니다. 
  
![필수 및 옵션으로 구분되는 예제 쿼리](../media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>중요한 정보 유형 - 필수

그렇다면 각 부분이 무엇입니까? SharePoint DLP 쿼리는 일반적으로 중요한 정보 유형 인벤토리의 속성 및 정보 유형 이름으로 시작하여 `SensitiveType:"` 1로 끝날 수 [](https://go.microsoft.com/fwlink/?LinkID=509999) `"` 있습니다. 조직에 대해 만든 사용자 지정 중요한 [정보](create-a-custom-sensitive-information-type.md) 유형의 이름을 사용할 수도 있습니다. 예를 들어 신용 카드 번호가 포함된 문서를 찾고 있을 수 있습니다. 이러한 경우 다음 형식을 사용하게  `SensitiveType:"Credit Card Number"` 됩니다. 개수 범위나 신뢰도 범위를 포함하지 않았기 때문에 쿼리는 신용 카드 번호가 검색되는 모든 문서를 반환합니다. 이 쿼리는 실행할 수 있는 가장 간단한 쿼리로, 대부분의 결과를 반환합니다. 중요한 유형의 맞춤법과 간격은 중요합니다. 
  
### <a name="ranges---optional"></a>범위 - 옵션

다음 두 부분 모두 범위이기 때문에 범위의 모양을 빠르게 살펴보아야 합니다. SharePoint DLP 쿼리에서 기본 범위는 다음과 같은 두 개의 기간으로 구분된 두 개의 숫자로  `[number]..[number]` 표시됩니다. 예를 들어 사용하는 경우 해당  `10..20` 범위는 10에서 20까지의 숫자를 캡처합니다. 이 항목에서는 다양한 범위 조합이 있으며 몇 가지가 다수 다수 다루고 있습니다. 
  
쿼리에 개수 범위를 추가해보아야 합니다. 개수 범위를 사용하여 문서가 쿼리 결과에 포함되기 전에 포함해야 하는 중요한 정보의 발생 횟수를 정의할 수 있습니다. 예를 들어 쿼리에서 정확히 다섯 개의 신용 카드 번호가 포함된 문서만 반환하려는 경우 다음을  `SensitiveType:"Credit Card Number|5"` 사용합니다. 개수 범위는 높은 위험도를 내포하는 문서를 식별하는 데도 도움이 될 수 있습니다. 예를 들어 조직에서는 신용 카드 번호가 5개 이상인 문서를 높은 위험으로 고려할 수 있습니다. 이 기준에 맞는 문서를 찾으면 다음 쿼리를  `SensitiveType:"Credit Card Number|5.."` 사용합니다. 또는 다음 쿼리를 사용하여 신용 카드 번호가 5개 이하인 문서를 찾을 수  `SensitiveType:"Credit Card Number|..5"` 있습니다. 
  
#### <a name="confidence-range"></a>신뢰도 범위

마지막으로 신뢰도 범위는 감지된 중요한 유형이 실제로 일치하는 신뢰도입니다. 신뢰도 범위의 값은 개수 범위와 비슷하게 계산됩니다. 개수 범위를 포함하지 않고 쿼리를 만들 수 있습니다. 예를 들어 신용 카드 번호가 85% 이상인 문서를 검색하는 경우 다음 쿼리를  `SensitiveType:"Credit Card Number|*|85.."` 사용합니다. 
  
> [!IMPORTANT]
> 즉, 모든 값이 작동하는 와일드카드 `*` 문자입니다. 와일드카드 문자()를 개수 범위나 신뢰도 범위에 사용할 수 있지만 중요한 유형에는 사용할 `*` 수 없습니다. 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>eDiscovery 센터에서 사용할 수 있는 추가 쿼리 속성 및 검색 연산자

또한 SharePoint의 DLP에는 LastSensitiveContentScan 속성이 도입됩니다. 이 속성은 특정 기간 내에 검색되는 파일을 검색하는 데 도움이 됩니다. 속성이 있는 쿼리 예제는 다음 섹션의 복잡한 쿼리 `LastSensitiveContentScan` 예제를 참조하십시오. [](#examples-of-complex-queries) 
  
DLP 관련 속성을 사용하여 쿼리를 만들 수 있는 것은 물론, 또는 같은 표준 SharePoint eDiscovery 검색 속성도 사용할  `Author` 수  `FileExtension` 있습니다. 연산자를 사용하여 복잡한 쿼리를 작성할 수 있습니다. 사용 가능한 속성 및 연산자 목록은 [eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093) 블로그 게시물과 함께 검색 속성 및 연산자 사용을 참조하세요. 
  
## <a name="examples-of-complex-queries"></a>예제

다음 예제에서는 서로 다른 중요한 유형, 속성 및 연산자를 사용하여 쿼리를 구체화하여 원하는 정보를 정확히 찾는 방법을 보여 주는 예제입니다.
  
|**Query**|**설명**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |이름이 너무 길기 때문에 이상해 보일 수 있지만 이 이름은 해당 중요한 유형에 대한 올바른 이름입니다. 중요한 정보 유형 인벤토리의 [정확한 이름을 사용하세요.](https://go.microsoft.com/fwlink/?LinkID=509999) 조직에 대해 만든 사용자 지정 중요한 [정보](create-a-custom-sensitive-information-type.md) 유형의 이름을 사용할 수도 있습니다.  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |그러면 중요한 유형 "신용 카드 번호"와 일치하는 문서가 하나 이상 반환됩니다. 각 범위의 값은 해당 최소값 및 최대값입니다. 이 쿼리를 작성하는 더 간단한 방법은 있지만 여기서 재미있는 것은  `SensitiveType:"Credit Card Number"` 어디일까요?  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |이 경우 2018년 8월 11일에서 2018년 8월 13일까지 검사된 신용 카드 번호가 5-25개인 문서를 반환합니다.  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |이 경우 2018년 8월 11일에서 2018년 8월 13일까지 검사된 신용 카드 번호가 5-25개인 문서를 반환합니다. XLSX 확장명을 사용하여 파일은 쿼리 결과에 포함되지 않습니다.  `FileExtension` 은 쿼리에 포함할 수 있는 여러 속성 중 하나입니다. 자세한 내용은 [eDiscovery에서 검색](https://go.microsoft.com/fwlink/?LinkId=510093)속성 및 연산자 사용을 참조하세요.  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |이 쿼리는 신용 카드 번호 또는 사회 보장 번호가 포함된 문서를 반환합니다.  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>예제

모든 쿼리가 동일하게 만들어지는 것은 아닙니다. 다음 표에서는 SharePoint의 DLP에서 작동하지 않는 쿼리의 예를 설명하고 그 이유를 설명합니다.
  
|**지원되지 않는 쿼리**|**이유**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |하나 이상의 숫자를 추가해야 합니다.  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule"은 유효한 중요한 유형 이름이 아니며, 중요한 정보 [](https://go.microsoft.com/fwlink/?LinkID=509999) 유형 인벤토리의 이름만 DLP 쿼리에서 작동됩니다.  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |0은 범위의 최소값 또는 최대값으로 유효하지 않습니다.  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |보기가 어려울 수 있지만 쿼리를 무효화하는 "Credit"과 "Card" 사이에는 추가 공백이 있습니다. 중요한 정보 유형 인벤토리의 정확한 중요한 [유형 이름을 사용하세요.](https://go.microsoft.com/fwlink/?LinkID=509999)  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |2개의 기간 부분은 공백으로 구분하면 안 됩니다.  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |파이프 디지타이터가 너무 많기|). 대신 다음 형식을 따르는 것입니다. `SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |신뢰도 값은 백분율을 나타내기 때문에 100을 초과할 수 없습니다. 따라서 1에서 100 사이의 숫자를 선택하세요.  <br/> |
   
## <a name="for-more-information"></a>자세한 내용

- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)
- [콘텐츠 검색 실행](content-search.md)
- [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)
  

