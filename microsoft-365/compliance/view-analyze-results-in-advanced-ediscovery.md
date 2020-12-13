---
title: Advanced eDiscovery에서 결과 분석 보기
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 표시된 작업 옵션의 정의를 포함하여 Advanced eDiscovery에서 분석 프로세스의 결과를 볼 수 있는 위치를 이해합니다.
ms.openlocfilehash: 64c91cb5929a7a74e53d653faff98d5792d3f131
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663262"
---
# <a name="view-analyze-results-in-advanced-ediscovery-classic"></a>Advanced eDiscovery(클래식)에서 결과 분석 보기

> [!NOTE]
> Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다. 
  
Advanced eDiscovery에서 분석 프로세스의 진행률과 결과는 아래 설명된 다양한 디스플레이에서 볼 수 있습니다.
  
## <a name="view-analyze-task-status"></a>작업 상태 분석 보기

결과 **\> 분석 작업 \> \> 준비에서** 프로세스 실행 분석 중 및 후에 상태가 표시됩니다. 
  
![작업 상태를 분석 합니다.](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
표시되는 작업은 선택한 옵션에 따라 다를 수 있습니다. 
  
- **ND/ET: setup**: 실행을 준비합니다(예: 실행 및 대소문자 매개 변수 설정).
    
- **ND/ET: ND 계산:** 파일의 중복에 가까운 분석을 처리합니다.
    
- **ND/ET: ET 계산:** 전체 전자 메일 집합에 대한 전자 메일 스레드 분석을 실행합니다.
    
- **ND/ET: 피벗 및** 유사성: 피벗 및 파일 유사성 처리를 수행합니다.
    
- **ND/ET: 메타데이터 업데이트:** 데이터베이스의 파일에 대해 수집된 새 데이터를 마무리합니다.
    
- **테마: 테마 계산**: 테마 분석을 실행합니다. (선택한 경우만 표시)
    
- **작업 상태**: 이 줄은 작업 완료 후 표시됩니다. 작업이 실행되는 동안 실행 기간이 표시됩니다.
    
> [!NOTE]
> 중복에 가까운 항목 및 전자 메일 스레드(ND 및 ED)의 분석 결과는 처리될 문서 수에 적용됩니다. 정확한 중복 파일은 포함하지 않습니다. 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>중복에 가까운 전자 메일 및 전자 메일 스레드 상태 보기

대상 **인구** 결과에는 대상 인구의 문서, 전자 메일, 첨부 파일 및 오류 수가 표시됩니다. 
  
문서 **결과에는** 피벗 수, 거의 중복된 고유 파일 및 정확한 중복 파일이 표시됩니다. 
  
전자 **메일 결과에는** 포괄, 포함- 제외, 고유한 포괄 복사본 및 나머지 전자 메일 메시지의 수가 표시됩니다. 전자 메일 결과의 유형은 서로 다릅니다. 
  
- **포함:** 포괄 전자 메일은 전자 메일 스레드에서 종료 노드로, 해당 스레드의 이전 기록을 모두 포함 따라서 검토는 스레드에서 이전 메시지를 읽을 필요 없이 포괄 전자 메일에 안전하게 집중할 수 있습니다. 
    
- **포괄** 제외: 포괄 메시지의 부모와 연결된 하나 이상의 다른 첨부 파일이 있는 경우 포괄 전자 메일은 포함-제외로 지정됩니다. 이 컨텍스트에서 Parent 용어는 전자 메일 스레드 또는 해당 특정 포괄 전자 메일에 포함된 대화의 상위에 있는 메시지에 사용됩니다. 검토자는 포괄 전자 메일 부모의 콘텐츠를 검토할 필요가 없는 경우 포괄 경로 부모와 연결된 첨부 파일을 검토하는 것이 유용할 수 있습니다. 
    
- **포괄** 복사본: 포괄 또는 포괄을 제외한 것으로 표시된 다른 메시지의 복사본인 경우 포괄 전자 메일이 포괄 복사본으로 지정됩니다. 즉, 이 메시지는 다른 포괄 메시지와 동일한 제목과 본문을 포함하며, 따라서 동일한 노드에 함께 상주합니다. 포괄 복사 메시지는 동일한 콘텐츠를 포함하기 때문에 일반적으로 검토 프로세스에서 건너뜁니다. 
    
- **나머지 :** 이는 고유한 콘텐츠가 포함되지 않은 전자 메일을 나타내며, 따라서 이전 세 가지 범주에 속하지 않습니다. 이러한 전자 메일 메시지는 검토할 필요가 없습니다. 메시지에 이후 포괄 전자 메일에 없는 첨부 파일이 포함된 경우 첨부 파일을 검토해야 할 수 있습니다. 이는 스레드 내에 포괄 minus 전자 메일이 존재하여 나타냅니다.
    
첨부 **파일 결과에는** 고유한 항목 및 중복 항목 유형에 따라 첨부 파일 수가 표시됩니다. 
  
![전자 메일 스레드 및 중복 근처](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>참고 항목

[고급 eDiscovery (클래식)](office-365-advanced-ediscovery.md)
  
[문서 유사성 이해](understand-document-similarity-in-advanced-ediscovery.md)
  
[설정 분석 옵션](set-analyze-options-in-advanced-ediscovery.md)
  
[텍스트 무시 설정](set-ignore-text-in-advanced-ediscovery.md)
  
[고급 설정 분석 설정](view-analyze-results-in-advanced-ediscovery.md)

