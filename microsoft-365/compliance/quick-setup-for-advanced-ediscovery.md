---
title: 고급 eDiscovery 빠른 설정
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: 보안 &amp; 준수 센터에서 Advanced eDiscovery에 액세스하는 방법을 알아보고 Advanced eDiscovery를 사용하기 위한 일반적인 워크플로를 검토합니다.
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936261"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a>고급 eDiscovery 빠른 설정(클래식)

> [!IMPORTANT]
> 최신 버전의 Advanced eDiscovery에 계속 투자함에 따라, Advanced eDiscovery(*Advanced eDiscovery(클래식)* 또는 *Advanced eDiscovery v1.0*이라고도 함)를 발표합니다. Advanced eDiscovery v1.0을 계속 사용하고 있는 경우 [Advanced eDiscovery v2.0](overview-ediscovery-20.md)(*Advanced eDiscovery solution in Microsoft 365*라고도 함)으로 전환하세요. Advanced eDiscovery 2.0에는 Advanced eDiscovery v1.0에 있는 유사한 기능이 포함되어 있습니다. 또한 보유자 관리, 통신 관리, 검토 집합 등의 새로운 기능도 제공합니다. Advanced eDiscovery v1.0의 사용 중지에 대한 자세한 내용은 [레거시 eDiscovery 도구의 사용 중지](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)를 참조하세요. 

이 설정 섹션에는 Advanced eDiscovery를 시작하는 방법에 대한 Microsoft 365 보안 &amp; 준수 센터 eDiscovery 관리자를 표시합니다. 사용자에게 두 기능에 대한 작업 지식이 있다고 가정합니다.
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a>Advanced eDiscovery에서 사례에 액세스

You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md). 
  
Advanced eDiscovery에서 사례로 이동하려면 
  
1. [보안 &amp; 준수 센터로 이동](go-to-the-securitycompliance-center.md) 
    
2. 보안 및 준수 센터에서 **검색 &amp; 조사** \> **eDiscovery**를 클릭하여 조직의 사례 목록을 표시합니다. 
    
3. **eDiscovery** 페이지에서 Advanced eDiscovery의 이동하려는 사례 옆에 있는 **열기**를 클릭합니다.
    
4. 사례에 대한 **홈** 페이지에서 **Advanced eDiscovery로 전환**을 클릭합니다.
    
    The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery. 
    
## <a name="workflow"></a>워크플로

다음 다이어그램에서는 보안 및 인증 센터와 Advanced eDiscovery에서 사례를 관리 및 사용하기 위한 일반적인 워크플로를 보여 줍니다.
  
![다이어그램은 사용자 &amp; 사례 설정, 사례 데이터 식별, 내보내기 및 처리를 포함하는 4가지 설정 단계와 분석 및 로컬 시스템으로 내보내기 단계를 포함하는 Advanced eDiscovery 워크플로를 표시합니다.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.
  
## <a name="analyze"></a>분석

[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results. 
  
## <a name="relevance-setup-and-relevance"></a>관련성 설정 및 관련성

[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions. 
  
## <a name="export"></a>내보내기

[사례 데이터 내보내기](export-case-data-in-advanced-ediscovery.md) 외부 검토를 위해 Advanced eDiscovery 콘텐츠 및 결과를 내보낼 수 있습니다. 
  
## <a name="report"></a>보고서

[보고서 실행](run-reports-in-advanced-ediscovery.md) Advanced eDiscovery 처리와 관련해서 선택한 보고서를 생성할 수 있습니다. 
  
## <a name="see-also"></a>참고 항목

[고급 eDiscovery (클래식)](office-365-advanced-ediscovery.md)
  
[사용자 및 사례 설정](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[데이터 준비](prepare-data-for-advanced-ediscovery.md)

