---
title: 양식 처리 개요
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
description: Microsoft SharePoint Syntex에서 양식 처리 모델 알아보기
ms.openlocfilehash: e3cf8298a2db9383e5b88dde737efc84e75c7f19
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222260"
---
# <a name="form-processing-overview"></a><span data-ttu-id="87bc4-103">양식 처리 개요</span><span class="sxs-lookup"><span data-stu-id="87bc4-103">Form processing overview</span></span>

 ![AI 작성기](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="87bc4-105">Microsoft SharePoint Syntex는 Microsoft PowerApps [AI 작성기](/ai-builder/overview) 양식 처리를 사용하여 SharePoint 문서 라이브러리내에 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="87bc4-106">AI 작성기 양식 처리를 사용하여 기계 학습 기술을 사용하여 양식과 송장과 같은 구조 혹은 반구조화 된 문서에서 키-값 쌍과 테이블 데이터를 식별하고 추출하는 AI 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="87bc4-107">조직은 종종 메일, 팩스, 전자 메일 등과 같은 다양한 출처로부터 다량의 송장을 받습니다. 이러한 문서를 수동으로 데이터베이스에 입력해 처리하기 위해서는 많은 시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="87bc4-108">AI를 사용하여 문서에서 텍스트, 키/값 쌍 및 표를 추출하는 양식 처리 프로세스를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="87bc4-109">양식 처리 시나리오 예제에 대한 자세한 내용은 [SharePoint Syntex 채택: 시작 가이드](./adoption-getstarted.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87bc4-109">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="87bc4-110">예를 들어 문서 라이브러리에 업로드 되는 모든 구매 주문 문서를 식별하는 양식 처리 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="87bc4-111">각 구매 주문서에서 *PO 번호*, *날짜* 또는 *전체 비용* 과 같이 사용자에게 중요 한 특정 데이터를 추출하여 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![문서 라이브러리 보기](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="87bc4-113">예제 파일을 사용하여 모델을 훈련시키고 양식에서 추출할 정보를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="87bc4-114">문서의 레이아웃은 모델 교육을 통해 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="87bc4-115">5개의 양식 문서가 있으면 시작 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-115">You only need five form documents to get started.</span></span> <span data-ttu-id="87bc4-116">AI 작성기는 예제 파일에서 키-값 쌍을 분석하고 사용자는 감지되지 않은 정보를 수동으로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="87bc4-117">AI 작성기는 예제 파일에서 모델의 정확도를 테스트 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="87bc4-118">모델을 훈련하고 게시하면 모델은 [파워 자동화 흐름](/power-automate/getting-started)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-118">After you train and publish your model, your model creates a [Power Automate Flow](/power-automate/getting-started).</span></span> <span data-ttu-id="87bc4-119">파일이 SharePoint 문서 라이브러리에 업로드 되면 흐름이 실행되고 모델에서 식별된 데이터를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="87bc4-120">추출 된 데이터가 모델의 문서 라이브러리 보기에서 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="87bc4-121">Office 365 관리자는 SharePoint 문서 라이브러리 [양식 처리 사용을 설정](./set-up-content-understanding.md)을 하여 사용자가 [양식 처리 모델 만들기](create-a-form-processing-model.md)를 할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-121">An Office 365 admin needs to [enable Form processing](./set-up-content-understanding.md) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="87bc4-122">설치 중 또는 관리 설정에서 설정 후에 사이트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-122">You can select the sites during setup, or after setup in your management settings.</span></span>

### <a name="file-limitations"></a><span data-ttu-id="87bc4-123">파일 제한 사항</span><span class="sxs-lookup"><span data-stu-id="87bc4-123">File limitations</span></span>

<span data-ttu-id="87bc4-124">폼 처리 모델을 사용할 때 [파일 사용에 대한 요구 사항과 제한 사항](/ai-builder/form-processing-model-requirements)을 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-124">When using form processing models, make sure to note the [requirements and limitations for file usage](/ai-builder/form-processing-model-requirements).</span></span>

### <a name="multi-geo-environments"></a><span data-ttu-id="87bc4-125">Multi-Geo 환경</span><span class="sxs-lookup"><span data-stu-id="87bc4-125">Multi-Geo environments</span></span>

<span data-ttu-id="87bc4-126">[Microsoft 365 Multi-Geo 환경](../enterprise/microsoft-365-multi-geo.md)에서 SharePoint Syntex를 설정할 때는 중앙 위치에서 양식 처리를 사용하도록만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87bc4-126">When setting up SharePoint Syntex in a [Microsoft 365 Multi-Geo environment](../enterprise/microsoft-365-multi-geo.md), you can only configure it to use form processing in the central location.</span></span> <span data-ttu-id="87bc4-127">위성 위치에서 양식 처리를 사용하려는 경우 Microsoft 지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="87bc4-127">If you want to use form processing in a satellite location, contact Microsoft support.</span></span>






## <a name="see-also"></a><span data-ttu-id="87bc4-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87bc4-128">See Also</span></span>
  
[<span data-ttu-id="87bc4-129">파워 자동화 문서</span><span class="sxs-lookup"><span data-stu-id="87bc4-129">Power Automate documentation</span></span>](/power-automate/)

[<span data-ttu-id="87bc4-130">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="87bc4-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="87bc4-131">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="87bc4-131">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="87bc4-132">교육: AI 작성기를 사용하여 비즈니스 성과 개선</span><span class="sxs-lookup"><span data-stu-id="87bc4-132">Training: Improve business performance with AI Builder</span></span>](/learn/paths/improve-business-performance-ai-builder/?source=learn)