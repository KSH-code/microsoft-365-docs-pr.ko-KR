---
title: 'Microsoft SharePoint Syntex 채택: 시작'
description: 비즈니스 문제를 해결하는 데 도움이 될 수 있도록 조직에서 SharePoint Syntex를 사용 및 구현하는 방법을 학습합니다.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597061"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="ce5fe-103">Microsoft SharePoint Syntex 채택: 시작</span><span class="sxs-lookup"><span data-stu-id="ce5fe-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="ce5fe-104">SharePoint Syntex에서 사용할 수 있는 지능형 콘텐츠 서비스는 다음 세 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="ce5fe-105">**콘텐츠 이해:** 코드 없는 AI 모델을 만들어 콘텐츠에서 정보를 분류하고 추출하여 지식 검색 및 재사용을 위한 메타데이터를 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="ce5fe-106">콘텐츠 [이해에 대해 자세히 알아보겠습니다.](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ce5fe-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="ce5fe-107">**콘텐츠 처리:** 콘텐츠 캡처, 수집 및 분류를 자동화하고 Power Automate를 사용하여 콘텐츠 중심 프로세스를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="ce5fe-108">콘텐츠 처리에 [대해 자세히 알아보겠습니다.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ce5fe-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="ce5fe-109">**콘텐츠 준수:** Microsoft Information Protection에 통합된 보안 및 거버넌스를 개선하기 위해 콘텐츠를 제어하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="ce5fe-110">새로운 AI 서비스 및 기능을 사용하여 콘텐츠 이해 및 분류 앱을 SharePoint Syntex를 사용하여 콘텐츠 관리 흐름에 직접 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="ce5fe-111">콘텐츠를 이해하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="ce5fe-112">사용하는 모델 형식은 파일 형식 및 사용 사례를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="ce5fe-113">양식 처리</span><span class="sxs-lookup"><span data-stu-id="ce5fe-113">Form processing</span></span> | <span data-ttu-id="ce5fe-114">문서 이해</span><span class="sxs-lookup"><span data-stu-id="ce5fe-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="ce5fe-115">문서 라이브러리에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-115">Created from document library.</span></span> | <span data-ttu-id="ce5fe-116">SharePoint Syntex의 일부인 콘텐츠 센터에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="ce5fe-117">AI 작성기에서 만든 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-117">Model created in AI builder.</span></span> | <span data-ttu-id="ce5fe-118">네이티브 인터페이스에서 만든 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-118">Model created in native interface.</span></span> |
| <span data-ttu-id="ce5fe-119">반구조적 파일 형식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="ce5fe-120">구조화되지 않은 파일 형식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="ce5fe-121">Settable 분류자입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-121">Settable classifier.</span></span> | <span data-ttu-id="ce5fe-122">선택적 추출기를 사용할 수 있는 학습 가능한 분류자입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="ce5fe-123">단일 라이브러리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-123">Restricted to a single library.</span></span> | <span data-ttu-id="ce5fe-124">여러 라이브러리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="ce5fe-125">PDF, JPG, PNG 형식 교육 총 50MB/500 pp.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="ce5fe-126">부정적인 예제를 포함하여 5-10 PDF, Office 또는 전자 메일 파일에 대해 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="ce5fe-127">기능을 보다 완전한 비교는 문서 이해 모델과 양식 처리 모델 간의 [차이를 참조하세요.](difference-between-document-understanding-and-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="ce5fe-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="ce5fe-128">최적화할 파일럿 비즈니스 시나리오 확인</span><span class="sxs-lookup"><span data-stu-id="ce5fe-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="ce5fe-129">조직에서 SharePoint Syntex 사용을 준비하려면 먼저 유용한 시나리오를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="ce5fe-130">"이유"는 필요한 모델과 모델이 적용되는 위치를 기준으로 조직을 구성하는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="ce5fe-131">다음은 문서 이해가 조직에 도움이 될 수 있는 몇 가지 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="ce5fe-132">**콘텐츠 처리:** 계약서, 작업 설명 및 기타 양식과 같은 문서를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="ce5fe-133">양식을 조정하고 필드를 이해하고 매핑하기 위해 모델을 교육한 다음 양식을 실행하여 데이터를 자동으로 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="ce5fe-134">자세한 내용은 양식 처리 [개요를 참조하세요.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ce5fe-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="ce5fe-135">**송장 분석:** 송장에서 관련 세부 정보를 끌어오고 정책이 준수되고 있는지 또는 적절하게 처리되고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ce5fe-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="ce5fe-136">SharePoint Syntex가 조직에 도움이 될 수 있는 방법에 대해 생각해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="ce5fe-137">비즈니스 프로세스 자동화</span><span class="sxs-lookup"><span data-stu-id="ce5fe-137">Automate business processes</span></span>
- <span data-ttu-id="ce5fe-138">검색 정확도 향상</span><span class="sxs-lookup"><span data-stu-id="ce5fe-138">Improve search accuracy</span></span>
- <span data-ttu-id="ce5fe-139">규정 준수 위험 관리</span><span class="sxs-lookup"><span data-stu-id="ce5fe-139">Manage compliance risk</span></span>

<span data-ttu-id="ce5fe-140">고려할 비즈니스 시나리오를 고려할 때 다음과 같은 질문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="ce5fe-141">실제 문제를 해결하나요?</span><span class="sxs-lookup"><span data-stu-id="ce5fe-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="ce5fe-142">광범위하게 사용되거나 광범위한 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="ce5fe-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="ce5fe-143">얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ce5fe-143">Is it obtainable?</span></span>
- <span data-ttu-id="ce5fe-144">성공을 측정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ce5fe-144">Can you measure success?</span></span>

<span data-ttu-id="ce5fe-145">영향 및 구현 용이성을 기반으로 시나리오 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="ce5fe-146">초기 포커스 영역을 쉽게 구현할 수 있는 더 큰 영향 시나리오로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="ce5fe-147">구현하기 어려운 낮은 영향 시나리오의 우선 순위를 낮게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="ce5fe-148">다음 예제 시나리오를 사용하여 조직에서 SharePoint Syntex를 사용하는 방법에 대한 아이디어를 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-148">Use the following example scenarios to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

### <a name="scenario-track-data-from-invoices-with-form-processing"></a><span data-ttu-id="ce5fe-149">시나리오: 양식 처리를 사용하여 송장에서 데이터 추적</span><span class="sxs-lookup"><span data-stu-id="ce5fe-149">Scenario: Track data from invoices with form processing</span></span>

<span data-ttu-id="ce5fe-150">예를 들어 SharePoint Syntex 및 Power Automate 기능을 사용하여 송장을 추적하고 모니터링하는 프로세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-150">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="ce5fe-151">송장 문서를 저장할 라이브러리를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-151">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="ce5fe-152">문서의 필드를 인식하는 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-152">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="ce5fe-153">추적할 필드를 목록으로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-153">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="ce5fe-154">흐름을 설정하여 다음을 통해 특정 이벤트를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-154">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="ce5fe-155">새 송장이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-155">A new invoice is added.</span></span>
    - <span data-ttu-id="ce5fe-156">송장 기한이 지난 경우</span><span class="sxs-lookup"><span data-stu-id="ce5fe-156">An invoice is past its due date.</span></span>
    - <span data-ttu-id="ce5fe-157">송장은 자동 승인 금액보다 큰 금액에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-157">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![SharePoint Syntex 및 Power Automate를 통해 송장 추적 및 모니터링](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="ce5fe-159">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-159">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="ce5fe-160">송장에서 데이터를 수동으로 추출하는 대신 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-160">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="ce5fe-161">워크플로를 사용하여 송장을 확인하고 문제를 알려 잠재적인 오류를 줄이고 규정 준수를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-161">Reduce potential errors and ensure better compliance by using workflows to check invoices and notify you of any issues.</span></span>

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a><span data-ttu-id="ce5fe-162">시나리오: 문서 이해를 통해 계약에서 정보 추적</span><span class="sxs-lookup"><span data-stu-id="ce5fe-162">Scenario: Track information from contracts with document understanding</span></span>

<span data-ttu-id="ce5fe-163">또 다른 예로, 회사의 다른 회사 또는 개인과의 계약을 식별하는 프로세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-163">As another example, you can set up a process to identify contracts your company has with other companies or individuals.</span></span> <span data-ttu-id="ce5fe-164">클라이언트 이름, 수수료, 날짜 또는 기타 중요한 정보와 같은 주요 정보를 해당 계약에서 추출하고 정보를 빠르게 볼 수 있는 필드로 라이브러리에 추가하는 모델을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-164">Set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add the information to the library as fields you can quickly view.</span></span> <span data-ttu-id="ce5fe-165">문서 라이브러리에 보존 레이블을 적용하여 비즈니스 규정을 적절하게 준수하기 위해 특정 기간 전에 계약을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-165">Apply a retention label on the document library to ensure that contracts can't be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="ce5fe-166">콘텐츠 센터에서 시작하여 계약에 대한 새 문서 이해 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-166">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="ce5fe-167">양성 및 부정적 예제를 위해 샘플 문서를 업로드한 다음 교육을 실행하여 계약 문서를 식별하고 결과를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-167">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="ce5fe-168">추출기에서 클라이언트 이름, 수수료 및 날짜와 같은 계약 필드를 식별하는 교육을 한 다음 추출기 테스트를 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-168">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="ce5fe-169">모델이 완료되면 계약을 업로드할 수 있는 라이브러리에 모델을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-169">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="ce5fe-170">날짜 필드에 보존 레이블을 적용하여 계약이 필요한 기간 동안 라이브러리에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-170">Apply a retention label to the date field, so that contracts are retained in the library for the required length of time.</span></span>

![SharePoint Syntex 및 보존 레이블과의 계약 추적 및 모니터링](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="ce5fe-172">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-172">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="ce5fe-173">수동으로 수행하지 않고 계약에서 데이터를 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-173">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="ce5fe-174">보존 레이블을 사용하여 계약이 적절하게 보존되도록 하여 규정 준수를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-174">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a><span data-ttu-id="ce5fe-175">시나리오: SharePoint Syntex를 기반으로 하는 레코드 관리, 문서 거버넌스 및 규정 준수 프로세스로 위험을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-175">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>

<span data-ttu-id="ce5fe-176">대부분의 회사에서 위험을 줄이는 것이 일반적인 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-176">Reducing risks is a common goal for most companies.</span></span> <span data-ttu-id="ce5fe-177">다음이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-177">You might need:</span></span>

- <span data-ttu-id="ce5fe-178">테넌트 전체에서 정보 거버넌스를 제공/적용하는 더 나은 방법</span><span class="sxs-lookup"><span data-stu-id="ce5fe-178">A better way to provide/enforce information governance across your tenant.</span></span>
- <span data-ttu-id="ce5fe-179">문서, 전자 메일 및 프로젝트의 '레코드'로 간주되는 기타 통신 형식의 분류 시스템을 개선하기 위해</span><span class="sxs-lookup"><span data-stu-id="ce5fe-179">To improve the system for classification of documents, emails and other forms of communication considered ‘records’ for projects.</span></span>
- <span data-ttu-id="ce5fe-180">회사 정책을 준수하기 위해 영수증, 계약 등 감사</span><span class="sxs-lookup"><span data-stu-id="ce5fe-180">To audit receipts, contracts, and so on, to ensure compliance with company policies.</span></span>
- <span data-ttu-id="ce5fe-181">프로젝트에 규정 준수에 필요한 모든 설명서가 프로젝트에 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-181">To ensure that projects have all the documentation required for compliance.</span></span>

<span data-ttu-id="ce5fe-182">더 나은 거버넌스가 필요한 문서 및 양식을 캡처하고 적절하게 분류, 감사 및 플래그를 지정하기 위해 SharePoint Syntex 준수를 위한 일부 프로세스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-182">Set up some processes for compliance with SharePoint Syntex to capture and appropriately classify, audit, and flag documents and forms that need better governance.</span></span> <span data-ttu-id="ce5fe-183">최종 사용자가 수동으로 태그를 지정하는 대신 SharePoint Syntex를 사용하여 콘텐츠를 자동 분류하거나 규정 준수 팀에서 거버넌스 규칙 및 보관을 수동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-183">You can rely on SharePoint Syntex to auto classify content rather than relying on end users to manually tag, or the compliance team to manually apply governance rules and archiving.</span></span> <span data-ttu-id="ce5fe-184">또한 간소화된 검색 환경을 사용하도록 설정하고, 데이터 볼륨을 관리하고, 레코드 관리 및 보존 정책을 적용하고, 규정 준수를 보장하고, 모범 사례 보관 및 삭제 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-184">And you can enable a simplified search experience, manage data volumes, apply records management and retention policies, ensure compliance, and best practice archiving and purging practices.</span></span>

<span data-ttu-id="ce5fe-185">이 시나리오를 자동화하면 다음의 안전을 느낄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-185">When you automate this scenario, you can feel secure that:</span></span>

- <span data-ttu-id="ce5fe-186">규정 준수를 준수하고 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-186">Compliance is upheld and risk is reduced.</span></span>
- <span data-ttu-id="ce5fe-187">세분화 및 레코드 관리는 일관되고 정확하게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-187">Taxonomy and records management is consistently and accurately applied.</span></span>
- <span data-ttu-id="ce5fe-188">콘텐츠 볼륨이 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-188">Content volumes are controlled.</span></span>
- <span data-ttu-id="ce5fe-189">직원은 올바른 컨텍스트에서 올바른 정보를 쉽게 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-189">Employees can easily discover the right information in the right context.</span></span>

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a><span data-ttu-id="ce5fe-190">시나리오: 이전에는 이 문서에 없는 문서에서 정보 캡처</span><span class="sxs-lookup"><span data-stu-id="ce5fe-190">Scenario: Capture information from previously inaccessible documents</span></span>

<span data-ttu-id="ce5fe-191">대부분의 조직에는 법률 문서, 정책, 계약, HR 문서 및 거버넌스 지침이 큰 저장소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-191">Most organizations have large repositories of legal documents, policies, contracts, HR documents, and governance guidelines.</span></span> <span data-ttu-id="ce5fe-192">프로젝트, 섹터, 테마, 사람, 지리적 영역 등의 중요한 정보를 추출하기 위해 이러한 데이터 저장소를 마이인드합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-192">Mine these data stores to extract valuable information such as: projects, sectors, themes, people, geographical areas, and so on.</span></span>

<span data-ttu-id="ce5fe-193">예를 들어 HR 감독은 이력서, HR 정책 및 기타 양식을 포함하여 모든 HR 문서에 빠르게 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-193">For example, an HR director needs to quickly access all HR documents – including resumes, HR policies, and other forms.</span></span> <span data-ttu-id="ce5fe-194">또한 문서를 수동으로 제거하지 않고도 이력서 및 기타 HR 관련 문서에서 필요한 정보를 빠르게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-194">And they want to quickly identify necessary information from resumes and other HR-related documents without manually sifting through the documents.</span></span> <span data-ttu-id="ce5fe-195">수천 개의 이력서, HR 정책 및 여러 사이트에 분산될 수 있는 기타 설명서를 수동으로 살펴보지 않고도 필요한 정보를 빠르게 찾을 수 있는 솔루션을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-195">They’re looking for a solution that allows them to quickly find the information they need without having to manually look through thousands of resumes, HR policies, and other documentation that may be spread across several sites.</span></span>

<span data-ttu-id="ce5fe-196">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-196">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="ce5fe-197">디지털 콘텐츠에서 지식의 잠금을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-197">Unlock knowledge from digital content.</span></span>
- <span data-ttu-id="ce5fe-198">HR 정책, 이력서, 판매 문서, 기술 청사진, 계정 계획 및 정보 추출을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-198">Classify HR policies, resumes, sales documents, technical blueprints, account plans and extract information.</span></span>
- <span data-ttu-id="ce5fe-199">원하는 올바른 정보나 문서를 빠르게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-199">Quickly find the correct information or document that you’re looking for.</span></span>
- <span data-ttu-id="ce5fe-200">최신 정보에 즉시 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-200">Get instant access to the latest information.</span></span>
- <span data-ttu-id="ce5fe-201">검색 시간을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-201">Reduce search times.</span></span>

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a><span data-ttu-id="ce5fe-202">시나리오: 데이터 처리를 개선하여 분석에 대한 & 제공</span><span class="sxs-lookup"><span data-stu-id="ce5fe-202">Scenario: Improve data processing to provide insights & analytics</span></span>

<span data-ttu-id="ce5fe-203">예를 들어 제약 회사에서 SharePoint Syntex를 사용하여 FDA 문서에서 정보를 추출하여 리더의 질문에 답변할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-203">For example, a pharmaceutical company could use SharePoint Syntex to extract information from FDA documents to answer questions that their leaders have.</span></span> <span data-ttu-id="ce5fe-204">답변에 보다 쉽게 액세스할 수 있도록 하면 이러한 답변을 생성하는 데 필요한 시간을 줄이고 데이터의 가용성을 높이어 리더십 질문에 대한 보다 정확한 답변을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-204">Having the answers more easily accessible can reduce the time needed to produce these answers and increase the availability of data to generate more accurate answers to leadership questions.</span></span>

<span data-ttu-id="ce5fe-205">예를 들어 프로젝트 관리자는 리더십 팀의 제품 관련 질문에 대한 답변을 신속하게 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-205">For example, a project manager needs to quickly provide answers to product-related questions from my leadership team.</span></span> <span data-ttu-id="ce5fe-206">하나의 통합 대시보드에서 쿼리와 관련된 정보 및 메트릭을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-206">They need to find information and metrics related to queries in one consolidated dashboard.</span></span> <span data-ttu-id="ce5fe-207">제품 레이블, 제품 팜플릿 및 기타 자료에서 필요한 정보를 추출하고 리더십 팀에 다시 보고할 때 사용할 수 있는 통합 보고서를 생성하는 솔루션을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-207">They’re looking for a solution that extracts the information they need from product labels, product pamphlets, and other materials and generates a consolidated report that they can use when reporting back to their leadership team.</span></span>

<span data-ttu-id="ce5fe-208">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-208">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="ce5fe-209">답변을 생성하는 데 필요한 시간을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-209">Reduce time to produce answers.</span></span>
- <span data-ttu-id="ce5fe-210">데이터의 가용성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-210">Increase availability of data.</span></span>
- <span data-ttu-id="ce5fe-211">보다 정확한 답변을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-211">Provide more accurate answers.</span></span>

### <a name="scenario-automate-order-processing"></a><span data-ttu-id="ce5fe-212">시나리오: 주문 처리 자동화</span><span class="sxs-lookup"><span data-stu-id="ce5fe-212">Scenario: Automate order processing</span></span>

<span data-ttu-id="ce5fe-213">SharePoint Syntex를 사용하면 고객 주문을 수동으로 처리하는 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-213">With SharePoint Syntex, you can reduce the time of manual processing of customer orders.</span></span> <span data-ttu-id="ce5fe-214">예를 들어 OCR 처리를 사용하여 팩스, 전자 메일 또는 용지의 주문을 SharePoint에 업로드한 다음 자동화된 프로세스를 사용하여 주문을 이행할 수 있도록 해당 주문에서 메타데이터를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-214">For example, you can upload orders from fax, email, or paper into SharePoint by using OCR processing and then extract the metadata from those orders so you can fulfill them by using automated processes.</span></span>

<span data-ttu-id="ce5fe-215">예를 들어 공급망 관리자는 수동 데이터 입력으로 인한 오류를 줄이고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-215">For example, a supply chain manager wants to reduce errors caused by manual data entry.</span></span> <span data-ttu-id="ce5fe-216">비즈니스 시스템으로 들어오는 오류를 줄이기 위해 인바운드 고객 주문(용지, 팩스 또는 전자 메일)의 수동 검토 및 데이터 입력을 방지하려는 경우</span><span class="sxs-lookup"><span data-stu-id="ce5fe-216">They want to avoid manual review and data entry of inbound customer orders (paper, fax, or e-mail) to reduce errors going into their business systems.</span></span> <span data-ttu-id="ce5fe-217">AI 및 기계 학습 기술을 적용하여 들어오는 주문 정보의 유효성을 검사하고 핵심 데이터를 추출한 다음 ERP 시스템에 자동으로 푸시하여 주문 이행 및 조정을 위해 솔루션을 원합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-217">They want a solution that applies AI and machine learning techniques to validate incoming order information, extract core data and automatically push it into their ERP system, for order fulfillment and reconciliation.</span></span>

<span data-ttu-id="ce5fe-218">이 시나리오를 자동화할 때 다음을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-218">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="ce5fe-219">주문 및 배송 정확도가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-219">Order and shipment accuracy increases.</span></span>
- <span data-ttu-id="ce5fe-220">주문 또는 배송 오류와 관련된 수수료 또는 페널티가 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-220">Fees or penalties associated to order or shipment errors are reduced.</span></span>
- <span data-ttu-id="ce5fe-221">송장 송장 또는 지급이 감소하는 경우의 지연</span><span class="sxs-lookup"><span data-stu-id="ce5fe-221">Delays in invoicing or payments decrease.</span></span>
- <span data-ttu-id="ce5fe-222">직원 비용 절감</span><span class="sxs-lookup"><span data-stu-id="ce5fe-222">Personnel costs are reduced.</span></span>

### <a name="scenario-simplify-visa-renewal-process"></a><span data-ttu-id="ce5fe-223">시나리오: Visa 갱신 프로세스 간소화</span><span class="sxs-lookup"><span data-stu-id="ce5fe-223">Scenario: Simplify visa renewal process</span></span>

<span data-ttu-id="ce5fe-224">SharePoint Syntex를 사용하면 주요 계약 정보에 대한 미리 알림 및 갱신을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-224">SharePoint Syntex can help you automate reminders and renewals for key contract information.</span></span> <span data-ttu-id="ce5fe-225">예를 들어 HR 감독은 직원의 Visas를 최신으로 유지 및/또는 정시에 갱신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-225">For example, an HR director needs to ensure that employees’ visas are up to date and/or renewed on time.</span></span> <span data-ttu-id="ce5fe-226">사람들이 Visas를 업데이트하는 간단하고 직관적인 프로세스를 제공하려는 경우</span><span class="sxs-lookup"><span data-stu-id="ce5fe-226">They want to give people a simple and intuitive process for updating their Visas.</span></span> <span data-ttu-id="ce5fe-227">계약에서 갱신 날짜를 추출하고 갱신 날짜가 다가오면 직원에게 미리 알림을 자동으로 보내는 솔루션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-227">They need a solution that extracts renewal dates from contracts and automatically sends employees reminders when their renewal dates are approaching.</span></span>

<span data-ttu-id="ce5fe-228">이 시나리오를 자동화할 때 다음을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-228">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="ce5fe-229">비준수 수준이 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-229">The levels of non-compliance are reduced.</span></span>
- <span data-ttu-id="ce5fe-230">수동 미리 알림 수가 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-230">The number of manual reminders is reduced.</span></span>
- <span data-ttu-id="ce5fe-231">비준수에 대한 벌금 수가 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-231">The number of fines for non-compliance is reduced.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="ce5fe-232">역할 및 & 식별</span><span class="sxs-lookup"><span data-stu-id="ce5fe-232">Identify roles & responsibilities</span></span>

<span data-ttu-id="ce5fe-233">조직에서 모델을 빌드하고 관리할 사용자 결정</span><span class="sxs-lookup"><span data-stu-id="ce5fe-233">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="ce5fe-234">다음과 같은 역할이 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-234">The following roles might be involved:</span></span>

| <span data-ttu-id="ce5fe-235">SharePoint/지식 관리자</span><span class="sxs-lookup"><span data-stu-id="ce5fe-235">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="ce5fe-236">Power Platform 관리자</span><span class="sxs-lookup"><span data-stu-id="ce5fe-236">Power Platform admin</span></span> | <span data-ttu-id="ce5fe-237">지식 관리자</span><span class="sxs-lookup"><span data-stu-id="ce5fe-237">Knowledge manager</span></span> | <span data-ttu-id="ce5fe-238">모델 소유자</span><span class="sxs-lookup"><span data-stu-id="ce5fe-238">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="ce5fe-239">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="ce5fe-239">AAD role</span></span>| <span data-ttu-id="ce5fe-240">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="ce5fe-240">AAD role</span></span> | <span data-ttu-id="ce5fe-241">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="ce5fe-241">AAD role</span></span> | <span data-ttu-id="ce5fe-242">챔피언</span><span class="sxs-lookup"><span data-stu-id="ce5fe-242">Champions</span></span> |
| <span data-ttu-id="ce5fe-243">양식 처리 구성</span><span class="sxs-lookup"><span data-stu-id="ce5fe-243">Configure form processing</span></span> | <span data-ttu-id="ce5fe-244">양식 처리를 위한 일반 데이터 서비스 환경 구성</span><span class="sxs-lookup"><span data-stu-id="ce5fe-244">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="ce5fe-245">사용 사례 수집</span><span class="sxs-lookup"><span data-stu-id="ce5fe-245">Gather use cases</span></span> | <span data-ttu-id="ce5fe-246">비즈니스 사용 사례 수집</span><span class="sxs-lookup"><span data-stu-id="ce5fe-246">Gather business use cases</span></span> |
| <span data-ttu-id="ce5fe-247">콘텐츠 센터 및 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="ce5fe-247">Manage content centers and permissions</span></span>| <span data-ttu-id="ce5fe-248">AIB 크레딧 구매 및 할당</span><span class="sxs-lookup"><span data-stu-id="ce5fe-248">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="ce5fe-249">모범 사례 설정 및 모델 분석 검토</span><span class="sxs-lookup"><span data-stu-id="ce5fe-249">Establish best practices and review model analytics</span></span> | <span data-ttu-id="ce5fe-250">모델 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="ce5fe-250">Create and apply models</span></span> |

<span data-ttu-id="ce5fe-251">기술 관리자, 비즈니스 프로세스 소유자 및 콘텐츠 모델 소유자는 조직에서 샘플 모델과 챔피언 채택을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-251">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="ce5fe-252">관련이 있을 수 있는 기타: 규정 준수 관리자, 세분화 관리자.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-252">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="ce5fe-253">어디에서 모델을 빌드하고 적용할 것인가?</span><span class="sxs-lookup"><span data-stu-id="ce5fe-253">Where will they build and apply the models?</span></span> <span data-ttu-id="ce5fe-254">개선할 수 있는 기존 프로세스 또는 리포지토리가 있나요?</span><span class="sxs-lookup"><span data-stu-id="ce5fe-254">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="ce5fe-255">양식 처리: 양식 처리 작업을 받을 사이트를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-255">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="ce5fe-256">문서 이해: 서로 다른 비즈니스 영역에 대해 여러 콘텐츠 센터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-256">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="ce5fe-257">전략적 위치</span><span class="sxs-lookup"><span data-stu-id="ce5fe-257">Strategic positioning</span></span>

<span data-ttu-id="ce5fe-258">관련자와 협의하여 SharePoint Syntex 사용 전략에 맞춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-258">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="ce5fe-259">이 위치 관리에 도움이 되는 다음 리소스를 조사하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-259">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="ce5fe-260">비즈니스 결과:</span><span class="sxs-lookup"><span data-stu-id="ce5fe-260">Business outcomes:</span></span>
  - <span data-ttu-id="ce5fe-261">잠재적 회계 결과</span><span class="sxs-lookup"><span data-stu-id="ce5fe-261">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="ce5fe-262">잠재적인 민첩성 결과</span><span class="sxs-lookup"><span data-stu-id="ce5fe-262">Potential agility outcomes</span></span>
  - <span data-ttu-id="ce5fe-263">비즈니스 결과 서식 파일</span><span class="sxs-lookup"><span data-stu-id="ce5fe-263">Business outcome template</span></span>
- <span data-ttu-id="ce5fe-264">이해 관계자/Exec 스폰서 구입/조정</span><span class="sxs-lookup"><span data-stu-id="ce5fe-264">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="ce5fe-265">비즈니스 사례 데크</span><span class="sxs-lookup"><span data-stu-id="ce5fe-265">Business case decks</span></span>
  - <span data-ttu-id="ce5fe-266">재무 모델</span><span class="sxs-lookup"><span data-stu-id="ce5fe-266">Financial models</span></span>
  - <span data-ttu-id="ce5fe-267">회사 준비 - 문화</span><span class="sxs-lookup"><span data-stu-id="ce5fe-267">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="ce5fe-268">관련자 파악</span><span class="sxs-lookup"><span data-stu-id="ce5fe-268">Identify stakeholders</span></span>

<span data-ttu-id="ce5fe-269">프로젝트 관련자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-269">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="ce5fe-270">역할</span><span class="sxs-lookup"><span data-stu-id="ce5fe-270">Role</span></span> |<span data-ttu-id="ce5fe-271">책임</span><span class="sxs-lookup"><span data-stu-id="ce5fe-271">Responsibilities</span></span> |<span data-ttu-id="ce5fe-272">부서</span><span class="sxs-lookup"><span data-stu-id="ce5fe-272">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="ce5fe-273">Executive sponsor(s)</span><span class="sxs-lookup"><span data-stu-id="ce5fe-273">Executive sponsor(s)</span></span>   | <span data-ttu-id="ce5fe-274">회사에 높은 수준의 비전과 가치 전달</span><span class="sxs-lookup"><span data-stu-id="ce5fe-274">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="ce5fe-275">임원진 리더십</span><span class="sxs-lookup"><span data-stu-id="ce5fe-275">Executive leadership</span></span>   |
| <span data-ttu-id="ce5fe-276">프로젝트 주도자</span><span class="sxs-lookup"><span data-stu-id="ce5fe-276">Project lead(s)</span></span> | <span data-ttu-id="ce5fe-277">전체 실행 실행 및 롤아웃 프로세스에 대한 오버시</span><span class="sxs-lookup"><span data-stu-id="ce5fe-277">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="ce5fe-278">프로젝트 관리</span><span class="sxs-lookup"><span data-stu-id="ce5fe-278">Project management</span></span> |
| <span data-ttu-id="ce5fe-279">지식 관리자</span><span class="sxs-lookup"><span data-stu-id="ce5fe-279">Knowledge administrators</span></span>| <span data-ttu-id="ce5fe-280">콘텐츠 센터 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="ce5fe-280">Create and manage the content centers</span></span> | <span data-ttu-id="ce5fe-281">IT 또는 기타 부서</span><span class="sxs-lookup"><span data-stu-id="ce5fe-281">IT or other department</span></span>|
| <span data-ttu-id="ce5fe-282">콘텐츠 관리자 및 모델 소유자</span><span class="sxs-lookup"><span data-stu-id="ce5fe-282">Content managers and model owners</span></span>| <span data-ttu-id="ce5fe-283">사용 사례 수집 및 모델 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="ce5fe-283">Gather use cases and create and apply models</span></span> | <span data-ttu-id="ce5fe-284">모든 부서</span><span class="sxs-lookup"><span data-stu-id="ce5fe-284">Any department</span></span>|
| <span data-ttu-id="ce5fe-285">챔피언</span><span class="sxs-lookup"><span data-stu-id="ce5fe-285">Champions</span></span> | <span data-ttu-id="ce5fe-286">이의 처리를 전도하고 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-286">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="ce5fe-287">모든 부서(직원)</span><span class="sxs-lookup"><span data-stu-id="ce5fe-287">Any department (staff)</span></span> |
| <span data-ttu-id="ce5fe-288">테넌트 관리자</span><span class="sxs-lookup"><span data-stu-id="ce5fe-288">Tenant administrator</span></span> | <span data-ttu-id="ce5fe-289">테넌트 수준 설정 구성</span><span class="sxs-lookup"><span data-stu-id="ce5fe-289">Configure tenant-level settings</span></span> | <span data-ttu-id="ce5fe-290">IT 부서</span><span class="sxs-lookup"><span data-stu-id="ce5fe-290">IT department</span></span>|
| <span data-ttu-id="ce5fe-291">Power Platform 관리자</span><span class="sxs-lookup"><span data-stu-id="ce5fe-291">Power Platform administrator</span></span>| <span data-ttu-id="ce5fe-292">일반 데이터 서비스 환경 구성</span><span class="sxs-lookup"><span data-stu-id="ce5fe-292">Configure common data services environment</span></span> | <span data-ttu-id="ce5fe-293">IT 부서</span><span class="sxs-lookup"><span data-stu-id="ce5fe-293">IT department</span></span>|

> [!Note]
> <span data-ttu-id="ce5fe-294">이러한 각 역할을 롤아웃 전체에서 이행하는 것이 까다로우면 식별된 솔루션을 시작하는 데 이러한 역할이 모두 필요하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-294">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="ce5fe-295">준비 검사 목록</span><span class="sxs-lookup"><span data-stu-id="ce5fe-295">Readiness checklist</span></span>

<span data-ttu-id="ce5fe-296">SharePoint Syntex 구현을 준비하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-296">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![콘텐츠 이해를 위한 준비](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="ce5fe-298">종료 상태 계획</span><span class="sxs-lookup"><span data-stu-id="ce5fe-298">Plan the end state</span></span>
    - <span data-ttu-id="ce5fe-299">문서 이해 모델은 끝이 아니라 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-299">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="ce5fe-300">다음을 사용하여 추출된 메타데이터의 값을 사용 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-300">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="ce5fe-301">검색</span><span class="sxs-lookup"><span data-stu-id="ce5fe-301">Search</span></span>
      - <span data-ttu-id="ce5fe-302">필터링 및 보기 서식</span><span class="sxs-lookup"><span data-stu-id="ce5fe-302">Filtering and view formatting</span></span>
      - <span data-ttu-id="ce5fe-303">규정 준수</span><span class="sxs-lookup"><span data-stu-id="ce5fe-303">Compliance</span></span>
      - <span data-ttu-id="ce5fe-304">자동화</span><span class="sxs-lookup"><span data-stu-id="ce5fe-304">Automation</span></span>
2. <span data-ttu-id="ce5fe-305">식별</span><span class="sxs-lookup"><span data-stu-id="ce5fe-305">Identify</span></span>
    - <span data-ttu-id="ce5fe-306">기존 정보 아키텍처 및 콘텐츠 관리 기능 사용을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-306">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="ce5fe-307">기존 콘텐츠 형식이 모델에 대해 좋은 후보인가요?</span><span class="sxs-lookup"><span data-stu-id="ce5fe-307">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="ce5fe-308">메타데이터를 통해 개선할 기존 프로세스는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="ce5fe-308">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="ce5fe-309">디자인</span><span class="sxs-lookup"><span data-stu-id="ce5fe-309">Design</span></span>
    - <span data-ttu-id="ce5fe-310">정보 아키텍처, 관리되는 메타데이터 및 콘텐츠 형식에 대한 접근 방식 디자인</span><span class="sxs-lookup"><span data-stu-id="ce5fe-310">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="ce5fe-311">정의, 만들기, 관리 프로세스를 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-311">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="ce5fe-312">조직 참여</span><span class="sxs-lookup"><span data-stu-id="ce5fe-312">Engage your organization</span></span>

1. <span data-ttu-id="ce5fe-313">지주를 식별하고 시나리오를 확인하고 프로젝트 계획을 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-313">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="ce5fe-314">설정을 구성하고 라이선스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-314">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="ce5fe-315">인식과 교육 시작 - 챔피언을 모집합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-315">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="ce5fe-316">단계적 롤아웃</span><span class="sxs-lookup"><span data-stu-id="ce5fe-316">Roll out in stages.</span></span>  
1. <span data-ttu-id="ce5fe-317">피드백을 수집하고 이행합니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-317">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="ce5fe-318">사용량이 증가함에 따라 필요한 경우 AI 작성기 크레딧에 대한 계획이 커지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce5fe-318">As usage grows plan for any AI Builder credits as needed.</span></span>
