---
title: 양식 처리 개요 (미리 보기)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex의 양식 처리에 대해 알아봅니다.
ms.openlocfilehash: dbea06cdf2dbb232a7ea48c78d7ea968dd18b9c0
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612729"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="66da3-103">양식 처리 개요 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="66da3-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="66da3-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="66da3-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="66da3-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="66da3-106">Project Cortex에서는 Microsoft PowerApps [AI 작성기](https://docs.microsoft.com/ai-builder/overview) 양식 처리를 사용 하 여 SharePoint 문서 라이브러리 내에서 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="66da3-107">AI Builder 양식 처리 기능을 사용 하 여 기계 학습 기술을 사용 하는 AI 모델을 만들어 양식 및 송장과 같은 구조화 되거나 반구조적 문서에서 키-값 쌍 및 테이블 데이터를 식별 하 고 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like form and invoices.</span></span>

<span data-ttu-id="66da3-108">회사는 전자 메일, 팩스, 전자 메일 또는 사용자와 같은 다양 한 원본에서 송장을 많이 수신 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="66da3-109">이러한 문서를 처리 하 고 데이터베이스에 수동으로 입력 하면 상당한 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="66da3-110">AI를 사용 하 여 문서에서 텍스트, 키/값 쌍 및 표를 추출 하면 양식 처리가이 프로세스를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="66da3-111">예를 들어 문서 라이브러리에 업로드 되는 모든 구매 주문 문서를 식별 하는 양식 처리 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="66da3-112">각 구매 주문에서 *PO 번호*, *날짜*또는 *총 비용*같은 중요 한 특정 데이터를 추출 하 고 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="66da3-113">예제 파일을 사용 하 여 모델을 학습 하 고 양식에서 추출할 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="66da3-114">모델을 학습 하면 문서의 레이아웃을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="66da3-115">시작 하려면 양식 문서가 5 개 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-115">You only need five form documents to get started.</span></span> <span data-ttu-id="66da3-116">AI 건물에서는 키-값 쌍에 대 한 예제 파일을 분석 하 고 검색 되지 않을 수도 있는 항목을 수동으로 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-116">AI building will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="66da3-117">AI 작성기에서는 샘플 파일의 모델 정확성을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="66da3-118">모델을 학습 하 고 게시 한 후에는 SharePoint 문서 라이브러리에 파일을 업로드 하 고 모델에서 식별 된 데이터를 추출할 때 실행 되는 [전원 자동화 흐름](https://docs.microsoft.com/power-automate/getting-started) 을 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that will run when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="66da3-119">추출 된 데이터는 모델의 문서 라이브러리 보기에 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="66da3-120">사용자가 SharePoint 문서 라이브러리에서 양식 처리 [모델을 만들](create-a-form-processing-model.md) 수 있도록 하려면 Office 365 관리자가 해당 [양식을 처리](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66da3-120">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="66da3-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66da3-121">See Also</span></span>
  
[<span data-ttu-id="66da3-122">파워 자동화 설명서</span><span class="sxs-lookup"><span data-stu-id="66da3-122">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="66da3-123">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="66da3-123">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="66da3-124">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="66da3-124">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="66da3-125">교육: AI Builder를 사용 하 여 비즈니스 성과 개선</span><span class="sxs-lookup"><span data-stu-id="66da3-125">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




