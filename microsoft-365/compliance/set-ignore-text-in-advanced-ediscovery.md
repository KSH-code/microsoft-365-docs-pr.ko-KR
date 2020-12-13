---
title: Advanced eDiscovery에서 분석에 텍스트 무시 옵션 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: Advanced eDiscovery에서 분석 및 프로세스 모듈을 사용할 때 특정 텍스트를 무시하는 규칙을 정의하는 방법을 학습합니다.
ms.openlocfilehash: f61724e3964ff4ba7f099dbfb4411e19db258adc
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663473"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a>Advanced eDiscovery(클래식)에서 분석에 대한 텍스트 무시 옵션 설정

> [!NOTE]
> Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다. 
  
텍스트 무시 기능은 전체 또는 다음 고급 eDiscovery 모듈에 적용할 수 있습니다. 분석(중복에 가까운 항목, 전자 메일 스레드, 테마) 및 연결성. 무시된 텍스트는 해당 텍스트와는 무관하게 표시된 파일에 나타나지 않습니다. 분석/계산에서는 무시된 텍스트를 삭제합니다.
  
이미 실행된 모듈에 대해 텍스트 무시 기능을 이전에 정의한 경우 이제 텍스트 무시 설정이 수정되지 않습니다. 그러나 Relevance 모듈의 텍스트 무시 기능은 변경될 수 있습니다.
  
## <a name="how-ignore-text-filters-are-applied"></a>텍스트 필터 무시 적용 방법

여러 무시 텍스트 필터는 입력된 순서대로 적용됩니다. 적용 순서를 변경하려면 해당 순서를 삭제하고 원하는 순서로 다시 입력해야 합니다.
  
예를 들어 텍스트 콘텐츠가 "DAVE BOB ALICE CAROL EVE"이면 다음은 텍스트 무시 항목의 샘플과 이러한 항목이 생성하는 결과입니다.

|**텍스트 항목 무시** <br/> |**결과** <br/> |
|:-----|:-----|
|"ALICE", "BOB CAROL"  <br/> |"DAVE EVE"  <br/> |
|"ALICE", "BOB ALICE CAROL"  <br/> |"DAVE BOB CAROL EVE"  <br/> |
   
두 번째 Ignore 텍스트 항목은 첫 번째 무시 텍스트가 적용된 후와 같이 문자열을 찾을 수 없는 경우 구현되지 않습니다.
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>텍스트 무시를 정의할 때 정규식 사용

텍스트 무시를 정의할 때 정규식이 지원됩니다. 다음은 정규식 구문과 사용법의 예입니다.
  
- 시작에서 줄 끝까지 텍스트를 제거(무시)하려면
    
     `Begin(.*)$`
    
    여기서 "Begin"은 줄에서 이 문자열이 처음 나타난 것입니다.
    
    예를 들어 다음 텍스트에 대해 다음을 입력합니다.
    
    **"This is first sentence and first line**
    
    **This is second sentence and second line"**
    
    정규식이 먼저(. \* ) $는 다음을 하게됩니다.
    
    **"This is**
    
    **This is second sentence and second line"**
    
- 전자 메일 스레드 끝에 자동으로 삽입된 고지 사항 및 법적 설명을 제거하려면
    
     `Begin(.|\s)*End`
    
    여기서 "Begin" 및 "End"는 래핑된 텍스트 단락의 시작과 끝에 있는 고유한 문자열입니다. 
    
    예를 들어 다음 정규식은 Begin 문자열과 End 문자열 사이의 전자 메일 스레드에 있는 고지 사항 및 법적 설명을 제거합니다.
    
    **이 메시지에는 기밀 정보(.| \s) 확인이 필요한 경우 하드 카피 \* 버전을 요청하십시오.**
    
- 고지사항(특수 문자 포함)을 제거하려면 
    
    예를 들어 다음 텍스트(여기에 x's로 표시됨)의 경우 
    
    **/\*\ 이 메시지에는 기밀 정보가 포함되어 있습니다. xxxx xxxx**
    
    **xxxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx**
    
    **xxxx xxxx 확인이 필요한 경우 하드 복사 버전을 요청하십시오. /\*\**
    
    위의 고지 사항 제거 정규식은 다음을 해야 합니다. 
    
    **\/\\*\\이 메시지에는 기밀 \. 정보(.| \s) 확인이 필요한 경우 하드 카피 \* 버전을 요청하십시오. \.\/\\*\\**
    
- 정규식 규칙:
    
  - 공백, "_" 및 "-"를 제외한 알파벳에 속하지 않는 문자 앞에 \" ".
    
  - 일반 eExpression 필드는 길이 제한이 없습니다.
    
> [!TIP]
> 정규식의 설명과 구문에 대한 자세한 내용은 정규식 언어 - 빠른 [참조를 참고합니다.](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx) 
  
## <a name="define-ignore-text-rule"></a>텍스트 무시 규칙 정의

1. 분석 옵션 **\> 관리 \>** 탭의 텍스트  무시 섹션에서 아이콘을 클릭하여 규칙을 **+** 추가합니다. 
    
2. 텍스트 무시 **추가** 대화 상자의 **이름** 필드에 텍스트 무시 규칙의 이름을 입력합니다. 
    
    ![무시 하는 텍스트 추가](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. 텍스트 **상자에** 무시할 텍스트를 입력합니다. 텍스트 필드에는 문자 수에 제한이 없습니다. 
    
    > [!TIP]
    > 위의 창에 표시된 대로  전구를 클릭하여 텍스트 무시 규칙에 대한 일반적인 구문 지침을 확인합니다. 
  
4. 원하는 경우 **대소문자** 구분 확인란을 선택합니다. 
    
5. 적용 **대상** 목록에서 정의를 적용할 Advanced eDiscovery 모듈을 선택합니다. 
    
6. 예제 텍스트에서 테스트를 실행하려면 입력 텍스트 상자에 샘플 텍스트를 **입력하고** 테스트를 **클릭합니다.** 결과는 출력 텍스트 **상자에** 표시됩니다. 
    
7. 확인을 **클릭하여** 텍스트 무시 규칙을 저장합니다. 정의된 무시 텍스트 규칙이 표시됩니다. 
    
    ![무시 설정 텍스트 이름](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>참고 항목

[고급 eDiscovery (클래식)](office-365-advanced-ediscovery.md)
  
[문서 유사성 이해](understand-document-similarity-in-advanced-ediscovery.md)
  
[설정 분석 옵션](set-analyze-options-in-advanced-ediscovery.md)
  
[고급 설정 분석 설정](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[분석 결과 보기](view-analyze-results-in-advanced-ediscovery.md)

