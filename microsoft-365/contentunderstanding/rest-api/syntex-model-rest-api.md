---
title: SharePoint Syntex 문서 이해 모델 REST API
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: SharePoint Syntex 문서 이해 모델 REST API의 개요입니다.
ms.openlocfilehash: 279c624bb818e5d8d33b476f997290269ff634cb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904314"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="25aac-103">SharePoint Syntex 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="25aac-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="25aac-104">SharePoint REST 인터페이스를 사용하여 문서 이해 모델을 만들고, 모델을 하나 이상의 라이브러리에 적용하거나 제거하고, 모델에 대한 정보를 가져오거나 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="25aac-105">SharePoint Online(및 SharePoint 2016 이상 온-프레미스) REST 서비스는 OData $batch 쿼리 옵션을 사용하여 여러 요청을 서비스에 대한 단일 호출로 결합하도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="25aac-106">코드 샘플에 대한 자세한 내용 및 링크를 보려면 [REST API를 사용하여 일괄 처리 요청](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25aac-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25aac-107">필수 조건</span><span class="sxs-lookup"><span data-stu-id="25aac-107">Prerequisites</span></span>

<span data-ttu-id="25aac-108">시작하기 전에 다음 사항을 잘 알고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="25aac-109">SharePoint REST 서비스에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="25aac-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service.md) 
- [<span data-ttu-id="25aac-110">SharePoint REST 끝점을 사용하여 기본 작업 완료</span><span class="sxs-lookup"><span data-stu-id="25aac-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints.md)

## <a name="rest-commands"></a><span data-ttu-id="25aac-111">REST 명령</span><span class="sxs-lookup"><span data-stu-id="25aac-111">REST commands</span></span>

<span data-ttu-id="25aac-112">다음 REST 명령을 Syntex 문서 이해 모델 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="25aac-113">[모델 만들기](rest-createmodel-method.md) - 모델 및 관련 콘텐츠 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="25aac-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – SharePoint Syntex 문서 이해 모델에 대한 정보를 가져오거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="25aac-115">[GetByTitle](rest-getbytitle-method.md) – 모델 제목을 사용하여 SharePoint Syntex 문서 이해 모델에 대한 정보를 가져오거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="25aac-116">[모델 적용](rest-applymodel-method.md) – 학습된 문서 이해 모델을 하나 이상의 라이브러리에 적용하거나 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="25aac-117">[모델 및 라이브러리 정보 가져오기](rest-getmodelandlibraryinfo.md) – 모델 및 모델이 적용된 라이브러리에 대한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="25aac-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – SharePoint Syntex 문서 이해 모델에 대해 사용 가능한 모델 설정(관련 보존 레이블 및 모델 설명)을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="25aac-119">[BatchDelete](rest-batchdelete-method.md) – 하나 이상의 라이브러리에서 적용된 문서 이해 모델을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="25aac-120">[분류 요청 만들기](rest-createclassificationrequest.md) – 적용된 모델을 사용하여 지정된 파일 또는 파일을 분류하는 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="25aac-121">시나리오</span><span class="sxs-lookup"><span data-stu-id="25aac-121">Scenarios</span></span>

<span data-ttu-id="25aac-122">메서드 이름으로는 직관적이지 않은 다음 시나리오 예제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="25aac-123">자세한 내용은 각 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25aac-123">For more information, see each article.</span></span>

<span data-ttu-id="25aac-124">모델 만들기 메서드는 모델 개체 및 관련 콘텐츠 형식만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="25aac-125">라이브러리에 적용하려면 먼저 콘텐츠 센터에서 모델을 학습시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="25aac-126">모델 적용 메서드는 문서를 분류하고 선택적으로 추가 정보를 추출하도록 대상 라이브러리에서 모델을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="25aac-127">또한 이 API는 모델을 여러 라이브러리에 적용하는 일괄 처리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="25aac-128">모델 제거 메서드는 이전에 적용된 하나 이상의 라이브러리에서 모델을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="25aac-129">모델을 삭제하려면 먼저 모델이 적용된 모든 라이브러리에서 제거되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aac-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="25aac-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25aac-130">See also</span></span>

[<span data-ttu-id="25aac-131">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="25aac-131">Document understanding overview</span></span>](../document-understanding-overview.md)

