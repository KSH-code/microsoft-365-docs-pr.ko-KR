---
title: 추출자를 만들 때 용어 저장소 분류 활용
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Microsoft SharePoint Syntexdml 문서 이해 모델에서 추출자를 만들 때 용어 저장소 분류를 활용 하세요.
ms.openlocfilehash: a8078e6ff2d2ecd0f98c22b602a54675f7d62816
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701098"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="4d834-103">추출자를 만들 때 용어 저장소 분류 활용</span><span class="sxs-lookup"><span data-stu-id="4d834-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="4d834-104">Microsoft SharePoint 구문 문서 이해 모델에서 추출자를 만들 때 [관리되는 메타데이터 서비스](https://docs.microsoft.com/sharepoint/managed-metadata#terms) 용어 저장소 분류를 사용하여 추출 하고자 하는 데이터의 기본 용어를 표시 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="4d834-105">예를 들어, 모델은 문서 라이브러리에 업로드 되는 모든 **계약서** 를 식별하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="4d834-106">또한 모델은 각 계약서에서 **계약 서비스** 값을 추출하고 라이브러리 보기의 열에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="4d834-107">계약서의 다양한 계약 서비스에는 회사가 더 이상 사용하지 않고 이름이 변경 된 여러가지 이전 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="4d834-108">예를 들어 *디자인*, *그래픽* 또는 *지형* 계약 서비스에 대한 모든 참조는 이제 *창의성* 이라고 불립니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="4d834-109">모델이 계약 문서에서 오래 된 용어를 추출할 때 사용자는 라이브러리 보기에서 현재 용어인 창의성을 보기 원합니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="4d834-110">아래 예제에서 모델 교육을 하는 동안 예시 문서에 *디자인* 의 오래된 용어가 포함되어 있는 것이 보입니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![용어 저장소](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="4d834-112">추출기에서 관리되는 메타데이터 열 사용</span><span class="sxs-lookup"><span data-stu-id="4d834-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="4d834-113">용어 집합은 SharePoint 관리 센터에서 MMS(관리되는 메타데이터 서비스) 용어 저장소에 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="4d834-114">아래 예제에서는 *계약서 서비스* [용어 집합](https://docs.microsoft.com/sharepoint/managed-metadata#term-set)은 *창의성* 을 포함하여 몇 가지의 용어를 포함하도록 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="4d834-115">세부 내역에는 용어에 세 가지의 동의어(*디자인*, *그래픽* 및 *지형*)가 있다고 보여주며 이 동의어는 *창의성* 이라고 해석되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![용어 집합](../media/content-understanding/term-store.png)</br>

> [!NOTE]
>  <span data-ttu-id="4d834-117">용어 집합은 컨텐츠 센터의 MMS 필드에서 전역으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-117">Term sets are configured as global in the MMS field of the content center.</span></span>

<span data-ttu-id="4d834-118">용어 집합에서 동의어를 사용하는데는 몇 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-118">There could be a number of reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="4d834-119">예를 들어, 이름을 지을 때 예전에 사용된 용어, 이름이 바뀐 용어 혹은 조직 부서간에 다르게 사용되는 용어가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-119">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="4d834-120">모델에서 추출자를 만들 때 사용 가능한 관리되는 메타 데이터 필드를 선택하도록 하려면 [관리되는 메타 데이터 사이트 칼럼으로 추가](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-120">To make the managed metadata field available for you to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="4d834-121">사이트 열을 추가한 후 모델에 대한 추출자를 만들 때 선택 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-121">After you add the site column, it will be available for you to select when you create the extractor for your model.</span></span>

   ![계약 서비스](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="4d834-123">문서 라이브러리에 모델을 적용 한 후 문서가 라이브러리에 업로드 되면 추출자가 동의어 값(*디자인*, *그래픽*, 및 *지형*)을 찾으면 *창의성 서비스* 칼럼이 기본 용어(*창의성*)로 보여집니다.</span><span class="sxs-lookup"><span data-stu-id="4d834-123">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![계약 서비스 열](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="4d834-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d834-125">See Also</span></span>
[<span data-ttu-id="4d834-126">관리되는 메타데이터 소개</span><span class="sxs-lookup"><span data-stu-id="4d834-126">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[<span data-ttu-id="4d834-127">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="4d834-127">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="4d834-128">관리되는 메타데이터 열 만들기</span><span class="sxs-lookup"><span data-stu-id="4d834-128">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





