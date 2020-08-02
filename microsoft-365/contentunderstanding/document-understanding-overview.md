---
title: 문서 이해 개요 (미리 보기)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex에서 이해 하는 문서에 대 한 개요를 가져옵니다.
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537403"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="d050d-103">문서 이해 개요 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d050d-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="d050d-104">프로젝트 Cortex 현재 미리 보기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="d050d-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="d050d-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="d050d-106">문서 이해에서는 AI 모델을 사용 하 여 파일 분류를 자동화 하 고 정보를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="d050d-107">문자 또는 계약과 같은 구조화 되지 않은 문서에서 가장 잘 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="d050d-108">문서에는 구 또는 패턴을 기반으로 식별 가능한 텍스트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="d050d-109">식별 된 텍스트는 파일 형식 (분류)과 추출할 대상 (추출기)을 모두 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="d050d-110">문서 이해 모델은 콘텐츠 센터 라는 유형의 SharePoint 사이트에서 만들어지고 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="d050d-111">SharePoint 문서 라이브러리에 적용 된 모델은 추출 된 정보를 저장할 열이 포함 된 콘텐츠 형식에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="d050d-112">만드는 콘텐츠 형식은 SharePoint 콘텐츠 형식 갤러리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="d050d-113">스키마를 사용 하기 위해 기존 콘텐츠 형식을 사용 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="d050d-114">문서에 *분류자* 와 *추출기* 를 추가 하 여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="d050d-115">분류자는 문서 라이브러리로 업로드 되는 문서를 식별 하 고 분류 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="d050d-116">예를 들어 분류자는 라이브러리에 업로드 되는 모든 *계약 갱신* 문서를 식별 하기 위해 "교육" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="d050d-117">계약 갱신 콘텐츠 형식은 사용자가 분류자를 만들 때 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="d050d-118">추출기이 문서에서 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="d050d-119">예를 들어 문서 라이브러리에서 식별 된 모든 계약 갱신 문서에 대해 각 계약 갱신 문서에 대 한 *서비스 시작 날짜* 와 *클라이언트* 도 표시 되는 열이 보기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="d050d-120">예제 파일을 사용 하 여 모델의 분류자 및 추출기을 훈련 하 고 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="d050d-121">예제 파일에서는 파일에서 데이터를 식별 하 고 추출 하려고 할 때 확인할 대상의 모델 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="d050d-122">예를 들어 회사에서 사용 하는 계약 갱신 문서의 예를 포함 하 여 계약 갱신 분류자 및 추출기을 교육 합니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="d050d-123">예제 파일을 사용 하 여 모델의 효율성을 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="d050d-124">모델을 게시 한 후 콘텐츠 센터를 사용 하 여 액세스 권한이 있는 SharePoint 문서 라이브러리에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d050d-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="d050d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d050d-125">See Also</span></span>
[<span data-ttu-id="d050d-126">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="d050d-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="d050d-127">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="d050d-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="d050d-128">[콘텐츠 센터 만들기](create-a-content-center.md) 
 [양식 처리 모델 만들기](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="d050d-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="d050d-129">[모델 적용](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="d050d-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="d050d-130">문서 이해와 양식 처리 모델의 차이점</span><span class="sxs-lookup"><span data-stu-id="d050d-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="d050d-131">양식 처리 개요</span><span class="sxs-lookup"><span data-stu-id="d050d-131">Form processing overview</span></span>](form-processing-overview.md)




