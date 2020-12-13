---
title: Advanced eDiscovery의 프로세스 모듈 결과 보기
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 작업 상태 및 프로세스 요약을 포함하여 Advanced eDiscovery에서 프로세스 모듈이 실행된 결과를 찾는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 73699d77e305055f6c2dc444fff00fb714b458cd
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663267"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a>Advanced eDiscovery(클래식)에서 프로세스 모듈 결과 보기

준비  \> **프로세스가** 시작된 후 진행률 및 결과를 볼 수 있습니다. 
  
> [!NOTE]
> Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다. 
  
## <a name="process-task-status"></a>프로세스 작업 상태

프로세스 **결과** 준비에서 페이지에는 다음 예제와 같이 현재 상태(프로세스가 현재 실행 중인 경우) 또는 마지막 프로세스 상태 작업 상태가 \>  \> 표시됩니다.
  
![프로세스 모듈 작업 상태](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
표시된 작업은 선택한 프로세스 옵션에 따라 다를 수 있습니다. 
  
- **인벤토리**: Advanced eDiscovery는 프로세스에 대해 선택된 모든 파일을 통해 되버르며 기본 데이터 수집을 수행합니다.
    
- **서명 계산:** MD5 디지털 서명을 계산합니다.
    
- **복합 추출:** 복합 파일(예: PST, ZIP, MSG)에서 내부 또는 포함된 파일을 재발적으로 추출합니다. 추출된 파일은 사례의 사례 폴더에 저장됩니다.
    
- **데이터베이스 동기화:** 내부 데이터베이스 프로세스
    
- **파일 복사본:** 프로세스 파일을 복사합니다. 이 작업은 고급 파일 복사 옵션을 선택한 경우에도 항상 표시됩니다.
    
- **텍스트 추출:** 기본 파일이 있는 경우 Advanced eDiscovery는 DTSearch를 사용하여 이러한 파일에서 텍스트를 추출합니다. 이러한 파일의 추출된 텍스트는 사례 폴더에 텍스트 파일로 저장됩니다.
    
- **메타데이터 업데이트:** 로드된 메타데이터를 처리합니다. 
    
- **마무리:** 로드된 사례 파일의 데이터를 마무리하는 내부 처리(예: 오류 및 성공 파일 식별) 
    
작업 상태: 작업 완료 후 표시됩니다. 작업이 실행되는 동안 실행 기간이 표시됩니다.
  
> [!NOTE]
> 완료된 작업에는 처리를 완료한 파일의 합계나 오류가 있는 파일에 대한 합계도 포함됩니다. 
  
> [!TIP]
> "취소"는 프로세스 실행을 중지한 다음 이전 데이터 수집 또는 저장된 처리된 데이터로 롤백하는 롤백 옵션을 제공합니다. 롤백하면 처리된 모든 데이터가 지워지게 됩니다. 처리된 데이터가 손실되지 않는 경우(예: 이러한 파일을 다시 로드하려는 경우) 이 창에서 "취소" 옵션을 선택하여 롤백하지 않을 것을 선택합니다. 
  
## <a name="process-summary"></a>프로세스 요약

프로세스 결과 프로세스 준비 요약에서는 로드된 파일 결과의 분석 결과가 성공적인 파일 처리 및 오류 결과에 \> \> 따라 \> 표시됩니다.
  
창에는 다음과 같이 가져온 파일 통계가 그래픽으로 표시됩니다.
  
- **프로세스 요약 d:** 이 경우 모든 파일이 누적됩니다.
    
- **마지막 프로세스 요약**: 마지막 세션 또는 작업에서 로드된 파일입니다. 
    
- **패밀리 마지막:** 사례의 가족 정보입니다(있는 경우).
    
- **시드** 파일을 추가한 경우 파일에 대해 정의된 문제당 시드 파일 수가 나열됩니다. 
    
    시드 파일의 **표시가** 실패한 경우 이 또한 참조됩니다. 
    
- 미리 **태그가 지정한** 파일을 추가한 경우 파일에 대해 정의된 문제당 미리 태그가 지정된 파일의 수가 나열됩니다. 
    
    미리 태그가 지정한 파일의 **표시가 실패한** 경우 이 또한 표시됩니다. 
    
![프로세스 모듈 요약](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>프로세스 요약 누적 차트 및 마지막 차트

왼쪽 막대에는 원본 + 추출된 파일이 포함되어 있습니다. 이 파일은 모두 찾은 파일입니다. 
  
처리된 오른쪽 막대에는 다음이 포함됩니다.
  
- 로드 오류가 있는 파일
    
- 다음을 포함할 수 있는 파일을 성공적으로 로드했습니다. 
    
  - **기존**: 전에 로드되어 다시 로드된 파일(중복 항목 포함)
    
  - **텍스트**: 텍스트가 있는 고유한 파일입니다.
    
  - **텍스트가 아닌** 파일 : 빈 텍스트 파일, 빈 네이티브 텍스트 파일, 네이티브 비 텍스트 파일 
    
  - **중복** s: 텍스트가 있는 파일이 중복됩니다.
    
## <a name="last-process-errors"></a>마지막 프로세스 오류

프로세스 결과 준비 마지막 프로세스 오류에서 마지막 세션 또는 수행된 작업의 오류에 대한 세부 정보가 \> \> \> 표시됩니다.
  
![프로세스 모듈 오류](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>참고 항목

[고급 eDiscovery (클래식)](office-365-advanced-ediscovery.md)
  
[프로세스 모듈 실행 및 데이터 로드](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

