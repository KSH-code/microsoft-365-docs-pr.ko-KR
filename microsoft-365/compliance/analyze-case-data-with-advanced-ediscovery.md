---
title: Advanced eDiscovery를 사용하여 사례 데이터 분석
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dce7a700-3b6e-435f-88ba-e4b82c0f2b26
description: 'Microsoft 365 Advanced eDiscovery에서 매개 변수를 설정하고, 옵션을 실행하고, 결과를 볼 수 있는 분석 프로세스의 개요를 얻습니다. '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 27b3c6d77ddbfc9d5c7ae7a727a403d93af70b35
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663175"
---
# <a name="analyze-case-data-with-advanced-ediscovery-classic"></a><span data-ttu-id="91390-103">Advanced eDiscovery(클래식)를 사용하여 사례 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="91390-103">Analyze case data with Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="91390-p101">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91390-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="91390-106"> \>  Advanced eDiscovery의 준비 분석 프로세스는 포함된 파일에 다음 기능을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="91390-106">The **Prepare** \> **Analyze** process in Advanced eDiscovery applies the following functionality to the included files:</span></span> 
  
- <span data-ttu-id="91390-107">로드된 파일을 고유 파일, 중복 파일 및 거의 중복된 파일 그룹으로 식별하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="91390-107">Identifies and organizes the loaded files into groups of unique files, duplicates, and near-duplicates.</span></span>
    
- <span data-ttu-id="91390-108">전자 메일의 점진적 포괄성을 기반으로 계층 구조화된 전자 메일 스레드 그룹으로 전자 메일을 식별하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="91390-108">Identifies and organizes emails into hierarchically structured groups of email threads, based on the progressive inclusiveness of the emails.</span></span>
    
- <span data-ttu-id="91390-109">Advanced eDiscovery 처리 및 파일 일괄 처리에서 테마를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91390-109">Enables the use of Themes in Advanced eDiscovery processing and file batching.</span></span>
    
 <span data-ttu-id="91390-110">분석 기능을 사용하면 다음과 같이 매개 변수를 설정하고, 옵션을 실행하고, 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91390-110">Analyze allows you to set parameters, run options, and view the results, as follows:</span></span> 
  
- <span data-ttu-id="91390-111">**설치 분석**: 파일에서 Analyze를 실행하기 전에 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91390-111">**Analyze setup**: Allows settings to be specified before running Analyze on the files.</span></span>
    
- <span data-ttu-id="91390-112">**결과 분석**: 분석 메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="91390-112">**Analyze results**: Displays metrics of the analysis.</span></span> 
    
<span data-ttu-id="91390-113">Analyze를 실행하기 전에 분석할 로드된 파일과 각 파일 형식이 전송될 분석 유형을 포함하여 파일을 선택하고 처리하는 기준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="91390-113">Before running Analyze, define the criteria for selecting and processing files, including which loaded files will be analyzed and the type of analysis to which each type of file will be submitted.</span></span> 
  
## <a name="additional-resources-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="91390-114">고급 eDiscovery(클래식) 분석에 대한 추가 리소스</span><span class="sxs-lookup"><span data-stu-id="91390-114">Additional resources for Advanced eDiscovery (classic) analysis</span></span>

[<span data-ttu-id="91390-115">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="91390-115">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="91390-116">문서 유사성 이해</span><span class="sxs-lookup"><span data-stu-id="91390-116">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="91390-117">텍스트 무시 설정</span><span class="sxs-lookup"><span data-stu-id="91390-117">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="91390-118">고급 설정 분석 설정</span><span class="sxs-lookup"><span data-stu-id="91390-118">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="91390-119">작업 분석 보기</span><span class="sxs-lookup"><span data-stu-id="91390-119">Viewing Analyze tasks</span></span>](view-analyze-results-in-advanced-ediscovery.md)

