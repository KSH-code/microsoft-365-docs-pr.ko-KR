---
title: Advanced eDiscovery에서 프로세스 모듈 실행
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: Advanced eDiscovery를 사용하여 분석을 위해 데이터 사례 파일을 준비하는 지침에 대해 자세히 알아보십시오.
ms.openlocfilehash: 3773833d9d0af993b4ccb35bcd18276800c4081f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662813"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a>Advanced eDiscovery(클래식)에서 프로세스 모듈 실행

사례 파일은 준비 프로세스 중에 Advanced eDiscovery에  \> **로드됩니다.** 
  
> [!NOTE]
> Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다. 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>지침: Advanced eDiscovery에 대한 데이터 준비

- **품질:** 사례와 연계된 사례 파일 인구를 명확하게 식별합니다.
    
- **Loads:** Advanced eDiscovery에서 액세스할 수 있는 위치에 파일을 로드합니다.
    
- **파일 ID**: Advanced eDiscovery의 고유한 파일 식별자입니다. 파일 식별자를 가져오지 않은 경우 Advanced eDiscovery에서 ID를 자동으로 생성합니다. 이후 프로세스 로드에서 ID를 매핑하고 초기 프로세스 로드와 다른 경로를 매핑하면 Advanced eDiscovery는 새 파일 항목을 추가하는 대신 경로를 대체합니다. ID는 내보내기 프로세스에서 참조로 사용할 수 있습니다. ID 값은 "-1"으로 설정하면 안 됩니다.
    
- **MD5:** 이 서명은 파일 간을 차별화하는 데 사용됩니다(두 파일은 동일한 MD5가 없는 한 정확히 중복된 것으로 간주되지 않습니다). 기본적으로 Advanced eDiscovery는 파일의 MD5를 계산합니다. 로드된 파일이 텍스트 파일인 경우 Advanced eDiscovery에서 값을 계산하는 대신 원래 MD5 값을 로드하고 매핑하는 것이 좋습니다.
    
- **파일 형식 및 이름:**
    
  - Advanced eDiscovery는 다양한 형식의 파일을 처리하고 로드된 네이티브 파일을 표준 형식으로 추출할 수 \* 있습니다(예: . TXT, HTML 또는 . XML. 텍스트 파일 처리는 네이티브 파일보다 빠릅니다. 추출된 텍스트 파일은 사례 폴더에 저장됩니다.
    
  - 시스템 파일 또는 그래픽 이미지와 같이 추출할 수 없는 파일은 로드하지 않습니다. 이러한 파일은 처리를 지연할 수 있습니다.
    
  - 파일 이름이 크게 지정 및 경로가 올바른지 확인합니다.
    
- **파일 경로:** Advanced eDiscovery는 경로 길이가 최대 400자인 파일을 로드할 수 있습니다.
    
- **텍스트** 추출 : 기본 파일에서 텍스트를 추출할 때 일반 텍스트 외에 숨겨진 텍스트(Excel 및 .doc), 숨겨진 열(Excel), 변경 내용 추적(.doc), 스피커 메모(.ppt), 포함된 개체(예: .ppt의 Excel 개체)도 추출됩니다. 텍스트 편집기에서 볼 수 있습니다.
    
- **텍스트 무시:** 이 선택적 기능은 프로세스가 실행된 후와 분석 전에 정의됩니다. 텍스트를 무시하면 파일 분석 성능이 아날 수 있기 때문에 주의해야 합니다.
    
- **다국어 텍스트:** Advanced eDiscovery는 현재 태그, 보류자 및 문제에 대한 다국어 이름을 처리하지 않습니다.
    
- **메타데이터:** 날짜 범위, 파일 크기, 파일 형식, 보호자 및 주제와 같은 향후 참조를 위해 사례 데이터베이스에 저장할 메타데이터가 있는지 여부를 판단합니다. 인벤토리를 다시 시작하거나 다시 처리 오버헤드를 추가하지 않고도 파일이 이미 로드된 후 메타데이터를 로드할 수 있습니다. 
    
  - 파일이 원래 경로에 의해 로드된 경우 나중에 메타데이터를 가져올 때 경로 열을 매핑합니다. ID로 파일을 참조하고 다른 경로를 매핑할 수 있습니다. 이 시나리오는 파일 경로가 변경될 때 유용합니다.
    
  - 파일이 원래 파일 ID에 의해 로드된 경우 메타데이터를 로드할 때 ID 열을 매핑합니다. ID 대신 경로로 파일을 참조하면 파일이 다른 ID로 다시 로드됩니다. Advanced eDiscovery는 기존 파일의 메타데이터를 로드하는 대신 파일의 복사본을 만듭니다.
    
- **가족:** 부모(가족의 수장)가 없는 패밀리를 로드할 수 없습니다. 
    
- **파일 크기:** Advanced eDiscovery에 로드되는 파일의 크기에는 제한이 없습니다. 분석의 경우(분석, 재배포 등) 제한은 추출된 텍스트의 5,242,880자입니다. 더 큰 파일은 무시됩니다(예를 들어, 파일과의관련성 학습 프로세스에 참여하지 않는 경우 일괄 계산 후의관련성 점수가 수신되지 않습니다).
    
- **파일 수량:** 단일 사례에서 처리할 수 있는 파일 수에는 권장되는 제한이 없습니다. 성능은 시스템의 리소스에 따라 다를 수 있습니다. 
    
## <a name="filtering-files"></a>파일 필터링

사용자 정의 레이블을 파일 집합과 연결하여 프로세스 또는 기타 작업에서 제외할 수 있습니다. 각 프로세스 세션은 일괄 ID와 연결됩니다. 일괄 처리 ID는 관련성 전문가에게 표시되지는 못하지만 현재 일괄 처리에 대한 필터를 추가하고 사용자 정의 레이블을 사용하여 적절한 모든 파일에 태그를 지정하여 검색 유틸리티를 사용하여 이행할 수 있습니다. 
  
## <a name="see-also"></a>참고 항목

[고급 eDiscovery (클래식)](office-365-advanced-ediscovery.md)
  
[프로세스 모듈 실행 및 데이터 로드](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[프로세스 모듈 결과 보기](view-process-module-results-in-advanced-ediscovery.md)

