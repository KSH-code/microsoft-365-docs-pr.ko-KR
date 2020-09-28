---
title: 추출기를 만들 때 용어 저장소 분류 활용
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint Syntex의 모델을 이해 하는 문서에서 추출기를 만들 때 용어 저장소 분류법을 활용 합니다.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296012"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="407d1-103">추출기를 만들 때 용어 저장소 분류 활용</span><span class="sxs-lookup"><span data-stu-id="407d1-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="407d1-104">문서에 SharePoint Syntex의 모델을 이해 하는 추출기를 만들 때 [관리 되는 메타 데이터 서비스](https://docs.microsoft.com/sharepoint/managed-metadata#terms) 용어 저장소 분류를 활용 하 여 추출한 데이터에 대 한 기본 용어를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="407d1-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="407d1-105">예를 들어 모델은 문서 라이브러리에 업로드 되는 모든 **계약** 문서를 식별 하 고 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="407d1-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="407d1-106">또한 모델은 각 계약에서 **계약 서비스** 값을 추출 하 고이를 라이브러리 보기의 열에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="407d1-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="407d1-107">계약의 다양 한 계약 서비스 값 중에는 회사에서 더 이상 사용 하지 않고 이름이 바뀐 이전 값이 여러 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="407d1-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="407d1-108">예를 들어 *디자인*, *그래픽*또는 *Topography* 계약 서비스 라는 용어에 대 한 모든 참조를 이제 *Creative*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="407d1-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="407d1-109">모델이 계약 문서에서 오래 된 용어 중 하나를 추출한 경우 라이브러리 보기에 현재 용어 소재를 표시 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="407d1-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="407d1-110">아래 예제에서는 모델을 교육 하는 동안 해당 샘플 문서에는 오래 된 *디자인*용어가 포함 된 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="407d1-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![용어 저장소](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="407d1-112">용어 집합 동의어</span><span class="sxs-lookup"><span data-stu-id="407d1-112">Term set synonyms</span></span> 

<span data-ttu-id="407d1-113">용어 집합은 SharePoint 관리 센터의 Managed Metadata service 용어 저장소에 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="407d1-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="407d1-114">아래 예에서 *계약 서비스* [용어 집합](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) 은 *소재*를 비롯 한 여러 용어를 포함 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="407d1-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="407d1-115">이에 대 한 세부 정보는 용어에 세 개의 동의어 (*디자인*, *그래픽*및 *Topography*)가 있음을 보여 *줍니다.*</span><span class="sxs-lookup"><span data-stu-id="407d1-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![용어 집합](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="407d1-117">여기서는이를 설명 하는 방법에 대해 잘 모르는 <합니다.</span><span class="sxs-lookup"><span data-stu-id="407d1-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="407d1-118">어떤 작업을 수행 하 여 계약 서비스 열을 추출 하 고 표시 하는 추출기를 만들 때 "표시" 열이 Creative Services에 대해 관리 되는 메타 데이터 용어 집합을 사용 하는 방법은 무엇 인가요? ></span><span class="sxs-lookup"><span data-stu-id="407d1-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="407d1-119">관리 되는 메타 데이터 필드에 대 한 문서 라이브러리 사이트 열 구성</span><span class="sxs-lookup"><span data-stu-id="407d1-119">Configure your document library site column for a managed metadata field</span></span>


   ![관리 되는 메타 데이터 만들기](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="407d1-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="407d1-121">See Also</span></span>
[<span data-ttu-id="407d1-122">관리 되는 메타 데이터 소개</span><span class="sxs-lookup"><span data-stu-id="407d1-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="407d1-123">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="407d1-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="407d1-124">관리되는 메타데이터 열 만들기</span><span class="sxs-lookup"><span data-stu-id="407d1-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





