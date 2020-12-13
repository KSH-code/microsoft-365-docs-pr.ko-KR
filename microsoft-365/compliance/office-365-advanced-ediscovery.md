---
title: Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: fd53438a-a760-45f6-9df4-861b50161ae4
description: Advanced eDiscovery를 통해 데이터를 분석하고, 문서 검토를 간소화하고, 효율적인 eDiscovery를 위한 의사 결정을 내리는 데 어떻게 도움이 될 수 있습니다.
ms.openlocfilehash: f8ada5d377e72516ea42d8c5dc5680573daec717
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662823"
---
# <a name="advanced-ediscovery-classic"></a>Advanced eDiscovery(클래식)

> [!IMPORTANT]
> **Advanced eDiscovery(클래식)는 2020년 12월 31일에 영구적으로 사용 중지됩니다.**<br/>
> 최신 버전의 Advanced eDiscovery에 계속 투자할 예정인 경우 Advanced eDiscovery(클래식)에서 사례 및 사례 데이터의 영구 사용 중지 및 제거를 발표하고 있습니다.
> Advanced eDiscovery v1.0(클래식)이라고도 하는 *Advanced eDiscovery를* 계속 사용 중이면 사용 현황을 [Advanced eDiscovery v2.0(Microsoft](overview-ediscovery-20.md) *365의 Advanced eDiscovery 솔루션)으로* 최대한 빨리 전환하세요.  모든 사례 및 사례 데이터 제거를 준비할 때 사례에서 데이터를 내보내 사례 데이터를 [보관할 수 있습니다.](https://docs.microsoft.com/microsoft-365/compliance/export-results-in-advanced-ediscovery?view=o365-worldwide)
> Advanced eDiscovery v2.0에는 Advanced eDiscovery v1.0에 있는 유사한 기능이 포함되어 있지만, 관리, 커뮤니케이션 관리 및 검토 집합과 같은 다양한 새로운 기능도 제공합니다. Advanced eDiscovery v1.0의 이전 사용 중지 단계에 대한 자세한 내용은 레거시 [eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)도구의 사용 중지를 참조합니다.

Advanced eDiscovery를 사용하면 데이터를 더 잘 이해하고 eDiscovery 비용을 줄일 수 있습니다. Advanced eDiscovery를 사용하면 구조화되지 않은 데이터를 분석하고, 보다 효율적인 문서 검토를 수행하고, eDiscovery의 데이터를 줄이기 위한 의사 결정을 내릴 수 있습니다. Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft 365 그룹 및 Microsoft Teams에 저장된 데이터로 작업할 수 있습니다. 보안 및 준수 센터에서 eDiscovery 검색을 수행하여 그룹, 개별 사서함 및 사이트의 콘텐츠를 검색한 다음 Advanced eDiscovery를 사용하여 검색 결과를 분석할 수 있습니다. Advanced eDiscovery에서 분석을 위해 검색 결과를 준비할 때 광학 문자 인식을 사용하면 이미지에서 텍스트를 추출할 수 있습니다. 이 기능을 사용하면 Advanced eDiscovery의 강력한 텍스트 분석 기능을 이미지 파일에 적용할 수 있습니다.
  
Advanced eDiscovery는 중복 항목 검색 및 전자 메일 스레드 분석과 같은 기능을 사용하여 중복 정보를 식별하여 문서 검토 프로세스를 간소화하고 속도를 향상합니다. 관련성 기능은 관련 문서를 식별하기 위해 예측 코딩 기술을 적용합니다. Advanced eDiscovery는 예제 문서에 대한 태그 지정 결정에서 학습하고 통계 및 자체 학습 기술을 적용하여 데이터 집합에 있는 각 문서의 관련성을 계산합니다. 이를 통해 주요 문서에 집중하고, 사례 전략, 데이터 선고 및 검토 우선 순위를 정할 때 신속한 정보를 제공한 결정을 내릴 수 있습니다.
  
 **고급 eDiscovery를 왜 사용하나요?** Advanced eDiscovery는 Office 365의 기존 eDiscovery 기능 집합을 기반합니다. 예를 들어 보안 준수 센터의 검색 기능을 사용하여 조직의 모든 콘텐츠 원본에 대한 초기 검색을 수행하여 특정 법률 사례와 관련이 있을 수 있는 데이터를 식별하고 수집할 수 &amp; 있습니다. 그런 다음 Advanced eDiscovery의 텍스트 분석, 기계 학습 및 관련성/예측 코딩 기능을 적용하여 해당 데이터에 대한 분석을 수행할 수 있습니다. 이렇게 하여 조직에서 수천 개의 전자 메일 메시지, 문서 및 기타 종류의 데이터를 빠르게 처리하여 특정 항목과 관련성이 가장 높은 항목을 찾는 데 도움이 될 수 있습니다. 
 
> [!NOTE]
> Advanced eDiscovery를 사용하려면 Office 365 E3에 고급 준수 추가 기능 또는 조직의 E5 구독이 필요합니다. 해당 요금제가 없는 경우 Advanced eDiscovery를 사용하려는 경우 [Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)평가판을 등록할 수 있습니다. 대소문자 그러면 축소된 데이터 집합을 추가 검토를 위해 Office 365에서 내보낼 수 있습니다. 
  
## <a name="get-started"></a>시작

Advanced eDiscovery를 시작하는 가장 빠른 방법은 보안 & 준수 센터에서 사례를 만들고 검색 결과를 준비한 다음 Advanced eDiscovery에서 해당 결과를 로드한 다음 Express 분석을 실행하여 해당 사례 데이터를 분석한 다음 외부 검토를 위해 결과를 내보내는 것입니다.
  
- [Advanced](quick-setup-for-advanced-ediscovery.md) eDiscovery 워크플로에 대한 간략한 개요 보기 
    
- [보안](set-up-users-and-cases-in-advanced-ediscovery.md) 및 준수 센터를 사용하여 사례를 만들고, eDiscovery 권한을 할당하고, 사례 구성원을 추가하여 Advanced eDiscovery에 대한 사용자 및 사례를 & 수 있습니다. 
    
- [](prepare-data-for-advanced-ediscovery.md) Advanced eDiscovery에서 사례에 검색 데이터 준비 및 로드 
    
- [Office 365가](import-non-office-365-data-into-advanced-ediscovery.md) 아닌 데이터를 고급 eDiscovery에서 분석하기 위해 사례에 로드 
    
- [Express 분석을 사용하여](use-express-analysis-in-advanced-ediscovery.md) 사례의 데이터를 빠르게 분석한 다음 결과를 쉽게 내보낼 수 있습니다. 
    
## <a name="analyze-data"></a>데이터 분석

Advanced eDiscovery에서 검색 데이터가 사례에 로드된 후 분석 모듈을 사용하여 분석을 시작할 수 있습니다. 분석 프로세스의 첫 번째 부분은 파일을 고유한 파일, 중복 파일 및 거의 중복된 파일 그룹으로 구성하는 것으로 구성됩니다(문서 유사성으로도 알 수 있습니다). 그런 다음 데이터를 계층적으로 구조화된 전자 메일 스레드 및 테마 그룹으로 다시 구성하고, 선택적으로 무시 텍스트 필터를 설정하여 분석에서 특정 텍스트를 제외합니다. 그런 다음 분석을 실행하고 결과를 시청합니다.
  
- [Advanced](understand-document-similarity-in-advanced-ediscovery.md) eDiscovery에서 데이터 분석 준비를 위한 문서 유사성에 대해 자세히 알아보기 
    
- [중복에](set-analyze-options-in-advanced-ediscovery.md) 가까운 테마, 테마 및 전자 메일 스레딩에 대한 옵션을 설정한 다음 분석 모듈을 실행합니다. 
    
- [텍스트 및 텍스트](set-ignore-text-in-advanced-ediscovery.md) 문자열이 분석되지 못하게 제외하기 위해 텍스트 무시 필터를 설정하십시오. 이러한 필터는 또한 타당성 분석을 실행할 때 텍스트도 무시합니다. 
    
- [분석 프로세스의](view-analyze-results-in-advanced-ediscovery.md) 결과 보기 
    
- [분석 프로세스에](set-analyze-advanced-settings-in-advanced-ediscovery.md) 대한 고급 설정 구성 
    
## <a name="set-up-relevance-training"></a>관련성 교육 설정

Advanced eDiscovery의 예측 코딩(관련성)을 사용하면 소수의 문서 집합에 대해 의사 결정을 내릴 수 있도록 하여 원하는 정보를 시스템에 교육할 수 있습니다.
  
- [관련성](manage-relevance-setup-in-advanced-ediscovery.md) 학습 설정, 사례와 관련된 파일에 태그 지정 및 사례 문제 정의에 대해 자세히 
    
- [사례 문제를 정의하고](define-issues-and-assign-users.md) 파일을 교육할 사용자에게 각 문제를 할당합니다. 
    
- [가져온 파일을](set-up-loads-to-add-imported-files.md) 현재 또는 새 로드에 추가하고, 해당 파일은 관계성 교육에 추가합니다. 부하는 사례에 추가된 후 해당 파일에 대한 새로운 배치를 사용하여 관계성 학습에 사용되는 일괄 처리입니다. 
    
- [관련성 교육에](define-highlighted-keywords-and-advanced-options.md) 추가할 수 있는 강조 표시된 키워드를 정의합니다. 이렇게 하면 사례와 관련된 파일을 보다 잘 식별할 수 있습니다. 
    
## <a name="run-the-relevance-module"></a>연결 모듈 실행

교육을 설정하고 나면 해당 모듈을 실행하고 교육 설정의 효율성을 평가할 수 있습니다. 이렇게 하면 관련성 순위가 지정되어 추가 교육을 수행할지 또는 사례와 관련된 파일 태그 지정을 시작할 준비가 되어 있는 경우를 결정하는 데 도움이 됩니다.
  
- [파일 예제](use-relevance-in-advanced-ediscovery.md) 집합을 기반으로 평가, 태그 지정, 추적 및 재조정의 관련성 프로세스 및 이 과정에 대해 자세히 알아보기 
    
- [사례에](assessment-in-relevance-in-advanced-ediscovery.md) 익숙한 전문가가 사례 파일 집합을 검토하고 관련성 교육의 효율성을 결정하는 평가에 대해 학습합니다. 
    
- [사례 파일을 평가하여](tagging-and-assessment-in-advanced-ediscovery.md) 교육 설정의 효율성(*풍부한 정보)을 계산한 다음 사례와 관련이 있는 파일이나 관련이 없는 파일에 태그를 지정합니다. 이렇게 하면 현재 교육만으로도 충분한지 또는 교육 설정을 조정해야 하는지 결정하는 데 도움이 됩니다. 
    
- [평가가](tagging-and-relevance-training-in-advanced-ediscovery.md) 완료된 후 관련성 교육을 수행한 다음 파일에 사례에 대해 정의한 문제와 관련이 없는 것으로 다시 한 번 태그를 지정합니다. 
    
- [타당성](track-relevance-analysis-in-advanced-ediscovery.md) 분석 프로세스를 추적하여 평가 목표(*안정적인 교육 상태라고도 알려지음) 또는 추가 교육이 필요한지 여부를 파악합니다. 또한 각 사례 문제의 해당 결과를 볼 수 있습니다. 
    
- [검토를 위해](decision-based-on-the-results-in-advanced-ediscovery.md) 내보낼 수 있는 결과 사례 파일 집합의 크기를 결정하기 위한 타당성 분석에 따라 의사 결정 
    
- [유효성 분석의](test-relevance-analysis-in-advanced-ediscovery.md) 품질을 테스트하여 유효성 검사 프로세스 중에 결정한 선형 결정의 유효성을 검사합니다. 
    
## <a name="export-results"></a>결과 내보내기

Advanced eDiscovery에서 사례 데이터를 분석하는 마지막 단계는 외부 검토를 위해 분석 결과를 내보내는 것입니다.
  
- [사례 데이터 내보내기에 대해 자세히](export-case-data-in-advanced-ediscovery.md)
    
- [사례 데이터 내보내기](export-results-in-advanced-ediscovery.md)
    
- [일괄 처리 기록 보기 및 이전 결과 내보내기](view-batch-history-and-export-past-results.md)
    
- [보고서 필드 내보내기](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a>기타 Advanced eDiscovery 도구

Advanced eDiscovery는 사례 데이터 분석, 문제 분석 및 데이터 내보내기 외의 추가 도구 및 기능을 제공합니다.
  
- [Advanced eDiscovery 보고서 실행](run-reports-in-advanced-ediscovery.md)
    
- [사례 및 테넌트 설정 정의](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [고급 eDiscovery 유틸리티](use-advanced-ediscovery-utilities.md)
