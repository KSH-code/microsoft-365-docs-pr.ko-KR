---
title: Advanced eDiscovery에서 고급 설정 분석 설정 설정
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: Advanced eDiscovery의 분석 프로세스에 대해 중복에 가까운 전자 메일, 전자 메일 스레드 및 테마를 비롯한 고급 설정을 구성하는 방법을 확인합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac1300eb26338691722d9ccd15269ccf7f964f58
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663493"
---
# <a name="set-analyze-advanced-settings-in-advanced-ediscovery"></a><span data-ttu-id="e3c4e-103">Advanced eDiscovery에서 고급 설정 분석 설정 설정</span><span class="sxs-lookup"><span data-stu-id="e3c4e-103">Set Analyze advanced settings in Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="e3c4e-p101">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="e3c4e-106">Advanced eDiscovery는 모듈 설정 분석에 대한 기본 고급 매개 변수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-106">Advanced eDiscovery provides default advanced parameters for Analyze module settings.</span></span> <span data-ttu-id="e3c4e-107">다음 절차에서는 지정할 수 있는 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-107">The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="e3c4e-108">설치 분석 **\> \> 준비** 탭에서 페이지 아래쪽의 **고급** 설정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-108">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page).</span></span> <span data-ttu-id="e3c4e-109">다음 패널이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-109">The following panel is displayed.</span></span> 
    
    ![고급 설정 설정 분석](../media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="e3c4e-111">중복에 **가까운** 전자 메일 스레드 매개 변수에서 필요한 경우 다음에 대한 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="e3c4e-112">**최소 단어 수:** 중복에 가까운 분석을 위해 파일이 제출되지 않는 단어의 최소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="e3c4e-113">**최대 단어 수:** 중복에 가까운 분석을 위해 파일이 전송되지 않는 단어의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="e3c4e-114">**전자 메일 유사성:** 비슷한 것으로 간주되는 두 전자 메일에 대한 최소 수준의 유사성</span><span class="sxs-lookup"><span data-stu-id="e3c4e-114">**Email similarity**: Minimal level of resemblance for two emails to be considered similar.</span></span> <span data-ttu-id="e3c4e-115">값은 항상 같거나 문서 유사성보다 습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-115">Value is always equal to, or larger than document similarity.</span></span> <span data-ttu-id="e3c4e-116">기본값은 90%입니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-116">Default is 90%.</span></span>
    
3. <span data-ttu-id="e3c4e-117">테마 **매개 변수에서**  분석 중에 테마 처리에 숫자를 포함하려면 테마 분석의 숫자 포함 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="e3c4e-118">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c4e-118">Click **Save**.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="e3c4e-119">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e3c4e-119">Related topics</span></span>

[<span data-ttu-id="e3c4e-120">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="e3c4e-120">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e3c4e-121">문서 유사성 이해</span><span class="sxs-lookup"><span data-stu-id="e3c4e-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e3c4e-122">설정 분석 옵션</span><span class="sxs-lookup"><span data-stu-id="e3c4e-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e3c4e-123">텍스트 무시 설정</span><span class="sxs-lookup"><span data-stu-id="e3c4e-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e3c4e-124">분석 결과 보기</span><span class="sxs-lookup"><span data-stu-id="e3c4e-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

