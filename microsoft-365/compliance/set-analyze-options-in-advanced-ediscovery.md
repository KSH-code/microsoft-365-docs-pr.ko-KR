---
title: Advanced eDiscovery에서 분석 옵션 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 중복에 가까운 항목, 전자 메일 스레드 및 테마를 포함하여 Advanced eDiscovery에서 분석 프로세스에 대한 옵션을 설정하는 단계를 검토합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ff51402cd79f2966730677a982fa5173b7e9b98
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663503"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a>Advanced eDiscovery(클래식)에서 분석 옵션 설정

> [!NOTE]
> Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다. 
  
Advanced eDiscovery에서 Analyze를 실행하기 전에 분석 옵션을 설정하십시오.
  
## <a name="set-analyze-options"></a>분석 옵션 설정

Open **Prepare \> Analyze** \> **Setup**. 다음 창이 표시됩니다.
  
![세트 옵션 분석](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **중복에 가까운 전자 메일 스레드** 분석을 실행하려는 경우 이 확인란을 선택합니다. 이 옵션은 기본적으로 선택되어 있습니다. 
  
 **문서 유사성** 중복에 가까운 임계값을 입력하거나 기본값인 65%를 수락합니다. 
  
 **테마** 모든 파일을 처리하고 테마를 할당하려면 이 확인란을 선택합니다. 기본적으로 이 확인란은 선택되어 있지 않습니다. 테마 처리를 수행하려는 경우 다음 옵션을 입력합니다.
  
- **최대 테마 수** 만들 테마 수에 대한 값을 입력하거나 선택합니다. 기본값은 200입니다. 
    
    > [!NOTE]
    > 테마 수를 늘리면 성능과 테마를 일반화할 수 있는 능력에 영향을 미치게 됩니다. 테마 수가 높을수록 테마 수가 세분화됩니다. 예를 들어 50개 테마 집합에 "바스켓, 스퍼, 클립퍼, 호반" 같은 테마가 포함된 경우 300개의 테마에는 "Spurs", "Clippers", "Lakers"라는 별도의 테마가 있을 수 있습니다. "바스켓"을 인식하지 못하고 ECA에 이 기능을 사용하는 경우 "바스켓"을 보는 것이 유용할 수 있습니다. 그러나 처리에 테마가 너무 많을 경우 "바스켓"이라는 단어가 전혀 표시되지 않을 수 있으며, 스퍼와 클립퍼가 부팅을 진행하고 머리에 사용되는 항목이 아니라 검토하기에 좋은 바스켓 테마라는 것을 알지 못합니다. 
  
- **추천 테마** 테마 처리를 제어하기 위해 테마 단어를 제안할 수 있습니다. Advanced eDiscovery는 이러한 추천 단어에 초점을 맞추고 "최대 테마 수" 설정에 따라 하나 이상의 관련 테마를 만들려고 합니다. 
    
    예를 들어 추천 단어가 "컴퓨터"이고 "2"를 "최대 테마 수"로 지정한 경우 Advanced eDiscovery는 단어 "computer"에 관련된 두 개의 테마를 생성하려고 시도합니다. 예를 들어 두 테마는 "컴퓨터 소프트웨어" 및 "컴퓨터 하드웨어"일 수 있습니다. 
    
    ![추천된 테마 추가](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. 제안된 테마를 보거나 추가하거나 편집하려면 수정을 **클릭합니다.**
    
2. 추천 테마 **패널에서** 아이콘 추가  아이콘을 클릭하여 ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 테마를 추가합니다. 제안된 **테마 추가 패널에서** 각 단어를 COMMA로 구분하여 추가합니다. 
    
3. 테마 **수에서** 고급 eDiscovery가 이러한 단어에 대해 생성하려고 시도할 테마 수를 결정하는 값을 선택합니다(기본값은 1개 테마).
    
4. **저장을** 클릭한 다음 대화 상자를 닫습니다. 
    
    > [!NOTE]
    > 총 테마 수에는 추천 테마가 포함됩니다. 총 추천 테마는 총 테마를 초과할 수 없습니다. 전체 테마를 상대로 추천 테마가 많은 경우 대부분의 테마는 추천 테마 전용이기 때문에 시스템에서 몇 가지 "소설" 테마만 검색됩니다. 
  
- **모드** 드롭다운 목록에서 테마 **옵션을** 선택합니다. 
    
  - **모델 만들기 및** 적용: 파일 세그먼트에서 모델별로 테마를 계산한 다음 여러 모델에 파일을 배포합니다.
    
  - **모델 만들기:** 파일 세그먼트에서 테마 모델을 계산합니다. 파일 세분화 적용 프로세스는 다른 시기에 별도로 수행됩니다.
    
  - **모델 적용**: 이 옵션은 이전에 모델을 만들 때만 표시되고 아직 적용되지 않은 경우 표시됩니다. 이렇게 하면 테마에 따라 파일이 분할됩니다.
    
무시 텍스트를 [설정하고](set-ignore-text-in-advanced-ediscovery.md) [분석에 대한 고급 설정 분석도](set-analyze-advanced-settings-in-advanced-ediscovery.md) 설정할 수 있습니다. 
  
이러한 옵션을 설정한 후  분석하여 실행합니다. [분석 결과 보기가](view-analyze-results-in-advanced-ediscovery.md) 표시됩니다. 
  
## <a name="related-topics"></a>관련 항목

[고급 eDiscovery (클래식)](office-365-advanced-ediscovery.md)
  
[문서 유사성 이해](understand-document-similarity-in-advanced-ediscovery.md)
  
[무시 텍스트 설정 ](set-ignore-text-in-advanced-ediscovery.md)
  
[고급 설정 설정 분석](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[결과 분석 보기](view-analyze-results-in-advanced-ediscovery.md)

