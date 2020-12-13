---
title: Advanced eDiscovery의 테스트관행성 분석
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: Advanced eDiscovery에서 일괄 계산 후 테스트 탭을 사용하여 전체 처리 품질을 테스트, 비교 및 유효성을 검사하는 방법을 학습합니다.
ms.openlocfilehash: e408d79aac8015da210f983b7b388ace84fc383a
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663421"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery-classic"></a>Advanced eDiscovery(클래식)의 테스트관행성 분석

> [!NOTE]
> Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다. 
  
Advanced eDiscovery의 테스트 탭을 사용하면 전체 처리 품질을 테스트, 비교 및 확인할 수 있습니다. 이러한 테스트는 일괄 계산 후 수행됩니다. 전문가는 컬렉션의 파일에 태그를 지정하여 태그가 지정된 각 파일이 실제로 사례와 관련이 있는지 여부를 최종적으로 판단합니다. 
  
단일 및 다중 문제 시나리오에서는 일반적으로 문제당 테스트가 수행됩니다. 각 테스트 후에 결과를 볼 수 있으며 지정된 샘플 테스트 파일을 사용하여 테스트 결과를 다시 작업할 수 있습니다.
  
## <a name="testing-the-rest"></a>나머지 테스트

"나머지 테스트" 테스트는 선별 결정의 유효성을 검사하는 데 사용됩니다. 예를 들어 최종 Advanced eDiscovery 결과에 따라 특정 관련성 컷오프 점수 이상의 파일만 검토합니다. 전문가는 선택한 컷오프 점수의 파일 샘플을 검토하여 해당 집합 내의 관련 파일 수를 평가합니다.
  
이 테스트에서는 검토 집합과 Rest 테스트 인구 간의 통계 및 비교를 제공합니다. 검토 집합의 결과는 교육 중의 해당성으로 계산됩니다. 결과에는 다음과 같은 설정 및 입력 매개 변수를 기반으로 하는 계산이 포함됩니다.
  
- 샘플의 파일 수와 식별된 관련 파일의 샘플 통계를 테스트합니다. 
    
- 검토 집합 및 Rest의 Population 매개 변수(예: 파일 수, 예상 관련 파일 수, 예상 풍부한 정보 및 추가 관련 파일을 찾는 평균 비용)의 테이블 형식 비교 비용 매개 변수 설정은 관리자가 설정할 수 있습니다.
    
1. **타당성 테스트 탭을 \> 열** 수 있습니다. 
    
2. 테스트 **탭에서** 새 **테스트를 클릭합니다.** 다음 **예제와** 같이 테스트 만들기 대화 상자가 표시됩니다. 
    
    ![나머지 결과 테스트 하는 관련성](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. 테스트 **이름 및** **설명에** 이름과 설명을 입력합니다.
    
4. 테스트 **유형 목록에서** **나머지** 테스트 선택
    
5. **문제/범주 목록에서** 문제 이름을 선택합니다. 
    
6. 로드 **목록에서** 로드를 선택합니다. 
    
7. 읽기 **%에서** 기본값을 수락하거나 잘라 내는관성 점수의 값을 선택합니다. 
    
8. Set **크기로** 설정하거나 기본값을 수락합니다. 복원 아이콘은 기본값을 복원합니다.
    
9. 태그 **지정 시작을 클릭합니다.** 테스트 샘플이 생성됩니다.
    
10. **Relevance \> Tag** 탭에서 각 파일을 검토하고 태그를 지정하고 완료하면 계산을 **클릭합니다.**
    
11. 테스트 탭에서 결과 보기를 클릭하여 테스트 결과를 볼 수 있습니다.  다음 그림에는 예제가 나와 있습니다. 
    
    ![나머지 결과 테스트 합니다.](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
위의 그림에서 표의 **샘플** 매개 변수 섹션에는 전문가가 태그를 지정한 샘플의 파일 수와 해당 샘플에서 찾은 관련 파일 수에 대한 세부 정보가 포함되어 있습니다. 
  
표의 **Population 매개** 변수 섹션에는 선택한 컷오프보다 점수가 높은 파일의 검토 집합 인구와 선택한 컷오프 이상의 점수가 있는 "나머지" 파일 인구를 포함하는 테스트 결과가 포함되어 있습니다. 각 인구에 대해 다음과 같은 결과가 표시됩니다. 
  
- 읽기 % - 상태 컷오프가 포함된 파일 포함
    
- 총 파일 수 
    
- 예상 관련 파일 수 
    
- 예상 풍부한 
    
- 다른 관련 파일을 찾는 데 드는 평균 검토 비용
    
## <a name="testing-the-slice"></a>조각 테스트

"슬라이스 테스트" 테스트는 "나머지 테스트" 테스트와 유사하게 테스트를 수행하지만, 파일 집합의 세그먼트는 읽기 전용으로 지정합니다.
  
1. **타당성 테스트 탭을 \> 열** 수 있습니다. 
    
2. 테스트 **탭에서** 새 **테스트를 클릭합니다.** 테스트 **만들기 대화** 상자가 표시됩니다. 
    
3. 테스트 **이름 및** **설명에** 정보를 입력합니다.
    
4. 테스트 **유형 목록에서** 조각 **테스트를 선택합니다.**
    
5. 문제 **목록에서** 문제 이름을 선택합니다. 
    
6. 로드 **목록에서** 로드를 선택합니다. 
    
7. 읽기 **사이의 읽기 %에서** 기본 낮음 및 높은 범위 값을 수락하거나 컷오프된 관계 점수에 대한 값을 선택합니다. 
    
8. 설정 **크기에서** 값을 선택하거나 기본값을 수락합니다.
    
    복원 아이콘은 기본값을 복원합니다.
    
9. 태그 **지정 시작을 클릭합니다.** 테스트 샘플이 생성됩니다.
    
10. **Relevance \> Tag** 탭에서 각 파일을 검토하고 태그를 지정하고 완료하면 계산을 **클릭합니다.** 
    
11. 테스트 탭에서 결과 보기를 클릭하여 테스트 결과를 볼 수 있습니다.  
    
## <a name="see-also"></a>참고 항목

[고급 eDiscovery (클래식)](office-365-advanced-ediscovery.md)
  
[이해와 무관성 평가](assessment-in-relevance-in-advanced-ediscovery.md)
  
[태그 지정 및 평가](tagging-and-assessment-in-advanced-ediscovery.md)
  
[태그 지정 및관련성 교육](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[추적과정성 분석](track-relevance-analysis-in-advanced-ediscovery.md)
  
[결과에 따라 결정](decision-based-on-the-results-in-advanced-ediscovery.md)

