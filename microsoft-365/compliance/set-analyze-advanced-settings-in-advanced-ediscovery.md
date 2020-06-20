---
title: 고급 eDiscovery에서 분석 고급 설정에 대 한 설정
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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: '고급 eDiscovery의 분석 프로세스에 대 한 중복 항목, 전자 메일 스레드 및 테마를 포함 하 여 고급 설정을 구성 하는 방법을 알아봅니다. '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b596ffa4061909ccb5c149553ac8fac169b7fd77
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819238"
---
# <a name="set-analyze-advanced-settings-in-advanced-ediscovery"></a><span data-ttu-id="61084-103">고급 eDiscovery에서 분석 고급 설정에 대 한 설정</span><span class="sxs-lookup"><span data-stu-id="61084-103">Set Analyze advanced settings in Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="61084-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="61084-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="61084-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="61084-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="61084-106">Advanced eDiscovery는 모듈 설정 분석을 위한 기본 고급 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61084-106">Advanced eDiscovery provides default advanced parameters for Analyze module settings.</span></span> <span data-ttu-id="61084-107">다음 절차에서는 지정할 수 있는 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="61084-107">The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="61084-108">\*\* \> \> 설치 분석 준비\*\* 탭에서 **고급 설정** (페이지 맨 아래)을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61084-108">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page).</span></span> <span data-ttu-id="61084-109">다음 패널이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61084-109">The following panel is displayed.</span></span> 
    
    ![고급 설정 설정 분석](../media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="61084-111">**거의 중복 항목 및 전자 메일 스레드 매개 변수**에서 필요에 따라 다음에 대 한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61084-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="61084-112">**최소 단어 수**: 아래의 파일은 거의 중복 된 분석을 위해 제출 되지 않는 단어의 최소 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="61084-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="61084-113">**최대 단어 수**: 위 단어의 최대 수, 즉 파일을 거의 중복 된 분석용으로 전송 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61084-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="61084-114">**전자 메일 유사**: 두 개의 전자 메일을 유사한 것으로 간주 하는 최소 resemblance 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="61084-114">**Email similarity**: Minimal level of resemblance for two emails to be considered similar.</span></span> <span data-ttu-id="61084-115">값은 항상 문서 유사성 보다 크거나 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61084-115">Value is always equal to, or larger than document similarity.</span></span> <span data-ttu-id="61084-116">기본값은 90%입니다.</span><span class="sxs-lookup"><span data-stu-id="61084-116">Default is 90%.</span></span>
    
3. <span data-ttu-id="61084-117">분석 중에 테마를 처리 하는 데 숫자를 포함 하려면 **테마 매개 변수**에서 **숫자를 테마 분석에 포함** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61084-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="61084-118">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61084-118">Click **Save**.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="61084-119">관련 항목</span><span class="sxs-lookup"><span data-stu-id="61084-119">Related topics</span></span>

[<span data-ttu-id="61084-120">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="61084-120">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="61084-121">문서 유사성 이해</span><span class="sxs-lookup"><span data-stu-id="61084-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="61084-122">분석 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="61084-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="61084-123">무시 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="61084-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="61084-124">분석 결과 보기</span><span class="sxs-lookup"><span data-stu-id="61084-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

