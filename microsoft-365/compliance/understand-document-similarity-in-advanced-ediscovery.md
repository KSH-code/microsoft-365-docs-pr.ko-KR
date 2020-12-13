---
title: Advanced eDiscovery의 문서 유사성 이해
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 두 파일의 최소 유사성 수준인 문서 유사성 값이 Advanced eDiscovery에서 작동하는 방법을 검토합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22eb27e7afdc6ad37ea6fdcba9b64298906f1c35
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663317"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a>Advanced eDiscovery(클래식)에서 문서 유사성 이해

> [!NOTE]
> Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다. 
  
Advanced eDiscovery에서 문서 유사성은 두 문서가 거의 중복된 것으로 간주되는 데 필요한 최소한의 유사성 수준입니다.
  
> [!TIP]
> 대부분의 비즈니스 응용 프로그램의 경우 유사성 값 60%-75%를 사용하는 것이 좋습니다. 품질이 매우 좋지 않은 OCR(광학 문자 인식) 재료의 경우 더 낮은 유사성 값을 적용할 수 있습니다. 
  
> [!NOTE]
> 주어진 사례에 대해 이 값을 설정하고 실행한 후 유사성 값을 변경할 수 없습니다. 
  
ND(Near-duplicate) 집합 내에 유사성 임계값보다 유사한 수준이 있는 문서가 있을 수 있습니다. 문서가 ND 집합에 가입하려면 유사성을 초과하는 유사성 수준이 있는 문서가 ND 집합에 하나 이상 있어야 합니다. 
  
예를 들어 유사도는 80%로, 문서 F1은 85% 수준에서 문서 F2와 비슷하고 문서 F2는 문서 F3과 90% 수준으로 비슷합니다. 
  
그러나 문서 F1은 임계값 미만인 70% 수준에서 문서 F3과 매우 다를 수 있습니다. 그러나 이 예제에서는 문서 F1, F2 및 F3이 모두 하나의 ND 집합에 나타납니다. 마찬가지로 유사성 값 80%를 사용하여 EquiSet-1과 EquiSet-2의 두 집합을 만들 수 있습니다. EquiSet-1에는 문서 E1 및 E2가 포함되어 있습니다. Equiset-2에는 문서 F1, F2 및 F3이 포함되어 있습니다. 
  
다음과 같은 수준이 예시됩니다.
  
![문서 유사성](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
이제 다른 문서 X1이 삽입된 것으로 가정합니다. X1과 E3의 87%는 밝게 나타났습니다. 마찬가지로 X1과 F1의 유사성은 92%입니다. 따라서 이제 EquiSet -1, EquiSet -2 및 X1이 하나의 ND 집합으로 결합됩니다.
  
![문서 유사성](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> 두 개의 문서가 하나의 ND 집합에 할당된 경우 집합에 문서가 추가되거나 집합이 병합되어도 같은 ND 집합에 함께 유지됩니다. 
  
집합이 병합된 후 새 문서를 집합에 추가할 때 피벗 문서를 변경할 수 있습니다. 
  
## <a name="related-topics"></a>관련 항목

[고급 eDiscovery (클래식)](office-365-advanced-ediscovery.md)
  
[설정 분석 옵션](set-analyze-options-in-advanced-ediscovery.md)
  
[텍스트 무시 설정](set-ignore-text-in-advanced-ediscovery.md)
  
[고급 설정 분석 설정](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[분석 결과 보기](view-analyze-results-in-advanced-ediscovery.md)

