---
title: 추출자를 만들 때 용어 저장소 분류 활용
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex의 문서 이해 모델에서 추출기를 만들 때 용어 저장소 분류를 사용하세요.
ms.openlocfilehash: aff2df6a96fdfee7380651f68e647019e9485658
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975742"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="79235-103">추출자를 만들 때 용어 저장소 분류 활용</span><span class="sxs-lookup"><span data-stu-id="79235-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="79235-104">SharePoint Syntex를 사용하여 문서 이해 모델에서 추출자를 생성할 때 [ 용어 저장소](https://docs.microsoft.com/sharepoint/managed-metadata)의 글로벌 용어 세트를 활용하여 추출하는 데이터에 대한 선호 용어를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79235-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of global term sets in the [term store](https://docs.microsoft.com/sharepoint/managed-metadata) to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="79235-105">예를 들어, 모델은 문서 라이브러리에 업로드 되는 모든 **계약서** 를 식별하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="79235-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="79235-106">또한 모델은 각 계약서에서 **계약 서비스** 값을 추출하고 라이브러리 보기의 열에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="79235-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="79235-107">계약서의 다양한 계약 서비스에는 회사가 더 이상 사용하지 않고 이름이 변경 된 여러가지 이전 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79235-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="79235-108">예를 들어 *디자인*, *그래픽* 또는 *지형* 계약 서비스에 대한 모든 참조는 이제 *창의성* 이라고 불립니다.</span><span class="sxs-lookup"><span data-stu-id="79235-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="79235-109">모델이 계약 문서에서 오래 된 용어를 추출할 때 사용자는 라이브러리 보기에서 현재 용어인 창의성을 보기 원합니다.</span><span class="sxs-lookup"><span data-stu-id="79235-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="79235-110">아래 예제에서 모델 교육을 하는 동안 예시 문서에 *디자인* 의 오래된 용어가 포함되어 있는 것이 보입니다.</span><span class="sxs-lookup"><span data-stu-id="79235-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![용어 저장소](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="79235-112">추출기에서 관리되는 메타데이터 열 사용</span><span class="sxs-lookup"><span data-stu-id="79235-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="79235-113">용어 집합은 SharePoint 관리 센터에서 MMS(관리되는 메타데이터 서비스) 용어 저장소에 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79235-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="79235-114">아래 예제에서 *계약 서비스* [용어 집합](https://docs.microsoft.com/sharepoint/managed-metadata#term-set)은 *창의성* 을 포함하여 여러 용어를 포함하도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79235-114">In the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include several terms, including *Creative*.</span></span>  <span data-ttu-id="79235-115">세부 내역에는 용어에 세 가지의 동의어(*디자인*, *그래픽* 및 *지형*)가 있다고 보여주며 이 동의어는 *창의성* 이라고 해석되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79235-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![용어 집합](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="79235-117">용어 집합에서 동의어를 사용하는데는 여러 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79235-117">There could be many reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="79235-118">예를 들어, 이름을 지을 때 예전에 사용된 용어, 이름이 바뀐 용어 혹은 조직 부서간에 다르게 사용되는 용어가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79235-118">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="79235-119">모델에서 추출기를 만들 때 관리되는 메타데이터 필드를 선택하도록 하려면 [관리되는 메타데이터 사이트 열로 추가](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79235-119">To make the managed metadata field available to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="79235-120">사이트 열을 추가한 후 모델에 대한 추출기를 만들 때 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79235-120">After you add the site column, you can select it when you create the extractor for your model.</span></span>

   ![계약 서비스](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="79235-122">문서 라이브러리에 모델을 적용 한 후 문서가 라이브러리에 업로드 되면 추출자가 동의어 값(*디자인*, *그래픽*, 및 *지형*)을 찾으면 *창의성 서비스* 칼럼이 기본 용어(*창의성*)로 보여집니다.</span><span class="sxs-lookup"><span data-stu-id="79235-122">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![계약 서비스 열](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="79235-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79235-124">See Also</span></span>
[<span data-ttu-id="79235-125">관리되는 메타데이터 소개</span><span class="sxs-lookup"><span data-stu-id="79235-125">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[<span data-ttu-id="79235-126">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="79235-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="79235-127">관리되는 메타데이터 열 만들기</span><span class="sxs-lookup"><span data-stu-id="79235-127">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





