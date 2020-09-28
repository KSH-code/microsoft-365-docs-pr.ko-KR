---
title: 양식 처리 개요
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint Syntex의 양식 처리에 대해 자세히 알아보기
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295179"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="1a1b7-103">양식 처리 개요 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1a1b7-103">Form Processing overview (Preview)</span></span>

<span data-ttu-id="1a1b7-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="1a1b7-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="1a1b7-106">Project Cortex에서는 Microsoft PowerApps [AI 작성기](https://docs.microsoft.com/ai-builder/overview) 양식 처리를 사용 하 여 SharePoint 문서 라이브러리 내에서 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="1a1b7-107">AI Builder 양식 처리 기능을 사용 하 여 기계 학습 기술을 사용 하는 AI 모델을 만들어 양식 및 송장과 같은 구조화 되거나 반구조적 문서에서 키-값 쌍 및 테이블 데이터를 식별 하 고 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="1a1b7-108">AI Builder 양식 처리 기능을 사용 하 여 ML (기계 학습) 기술을 활용 하는 AI 모델을 만들어 양식 및 송장 같은 구조화 된 문서 또는 반구조적 문서의 키-값 쌍 및 테이블 데이터를 식별 하 고 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-108">Use AI Builder form processing to create AI models that utilize machine learning (ML) technology to identify and extract key-value pairs and table data from structured or semi-structured documents, such as form and invoices.</span></span>

<span data-ttu-id="1a1b7-109">조직은 종종 메일, 팩스, 전자 메일 등의 다양 한 원본에서 송장을 많이 받습니다. 이러한 문서를 처리 하 고이를 데이터베이스에 수동으로 입력 하면 상당한 시간이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-109">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="1a1b7-110">AI를 사용 하 여 문서에서 텍스트, 키/값 쌍 및 표를 추출 하면 양식 처리가이 프로세스를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

<span data-ttu-id="1a1b7-111">예를 들어 문서 라이브러리에 업로드 되는 모든 구매 주문 문서를 식별 하는 양식 처리 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-111">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="1a1b7-112">각 구매 주문에서 *PO 번호*, *날짜*또는 *총 비용*같은 중요 한 특정 데이터를 추출 하 여 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-112">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="1a1b7-113">샘플 파일을 사용 하 여 모델을 학습 하 고 양식에서 추출할 정보를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-113">You can also use sample files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="1a1b7-114">모델을 학습 하면 문서의 레이아웃을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="1a1b7-115">시작 하려면 양식 문서가 5 개 이상 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-115">You need a minimum of five form documents to get started.</span></span> <span data-ttu-id="1a1b7-116">AI 건물에서는 주요 키-값 쌍에 대 한 샘플 파일을 분석 한 다음 검색 되지 않았을 수 있는 항목을 수동으로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-116">AI building analyzes your sample files for key-value pairs, and then manually identifies the ones that may not have been detected.</span></span>  <span data-ttu-id="1a1b7-117">AI 작성기에서는 샘플 파일의 모델 정확성을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="1a1b7-118">모델을 훈련 하 고 게시 한 후에는 SharePoint 문서 라이브러리에 파일을 업로드 한 후에 실행 되는 [전원 자동화 흐름](https://docs.microsoft.com/power-automate/getting-started) 을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-118">After you train and publish your model, use it to create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that runs after a file is uploaded to the SharePoint document library.</span></span> <span data-ttu-id="1a1b7-119">그런 다음 모델에서 식별 된 데이터를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-119">It then extracts data that has been identified in the model.</span></span> <span data-ttu-id="1a1b7-120">추출 된 데이터는 모델의 문서 라이브러리 보기에 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="1a1b7-121">샘플 파일을 사용 하 여 모델을 학습 하 고 양식에서 추출할 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-121">You use sample files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="1a1b7-122">모델을 학습 하면 문서의 레이아웃을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-122">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="1a1b7-123">시작 하려면 양식 문서가 5 개 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-123">You only need five form documents to get started.</span></span> <span data-ttu-id="1a1b7-124">AI Builder는 키-값 쌍에 대 한 예제 파일을 분석 하 고 검색 되지 않았을 수 있는 항목을 수동으로 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-124">AI Builder will analyze your sample files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="1a1b7-125">AI 작성기에서는 샘플 파일의 모델 정확성을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-125">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="1a1b7-126">모델을 학습 하 고 게시 한 후에는 [전원 자동화 흐름](https://docs.microsoft.com/power-automate/getting-started)을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-126">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="1a1b7-127">파일을 SharePoint 문서 라이브러리에 업로드 하 고 모델에서 식별 된 데이터를 추출할 때 흐름이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-127">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="1a1b7-128">추출 된 데이터는 모델의 문서 라이브러리 보기에 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-128">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="1a1b7-129">사용자가 SharePoint 문서 라이브러리에서 양식 처리 [모델을 만들](create-a-form-processing-model.md) 수 있도록 하려면 Office 365 관리자가 해당 [양식을 처리](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-129">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a1b7-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a1b7-130">See Also</span></span>
  
[<span data-ttu-id="1a1b7-131">파워 자동화 설명서</span><span class="sxs-lookup"><span data-stu-id="1a1b7-131">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="1a1b7-132">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="1a1b7-132">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="1a1b7-133">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="1a1b7-133">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="1a1b7-134">교육: AI Builder를 사용 하 여 비즈니스 성과 개선</span><span class="sxs-lookup"><span data-stu-id="1a1b7-134">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
