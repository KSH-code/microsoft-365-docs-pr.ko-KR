---
title: 'Microsoft SharePoint Syntex 채택: 시작'
description: 비즈니스 문제를 해결하는 데 도움을 줄 수 있도록 조직에서 SharePoint Syntex를 사용 및 구현하는 방법을 배워야 합니다.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 441f28e36ced25b2e5af3f71235995c8b021f779
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771874"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="447b6-103">Microsoft SharePoint Syntex 채택: 시작</span><span class="sxs-lookup"><span data-stu-id="447b6-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="447b6-104">SharePoint Syntex에서 사용할 수 있는 지능형 콘텐츠 서비스는 다음 세 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="447b6-105">**콘텐츠 이해:** 코드 없는 AI 모델을 만들어 콘텐츠에서 정보를 분류하고 추출하여 지식 검색 및 재사용을 위한 메타데이터를 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="447b6-106">콘텐츠 이해에 [대해 자세히 알아보겠습니다.](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="447b6-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="447b6-107">**콘텐츠 처리:** Power Automate를 사용하여 콘텐츠의 캡처, 수집 및 분류를 자동화하고 콘텐츠 중심 프로세스를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-107">**Content processing:** Automate capture, ingestion and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="447b6-108">콘텐츠 처리에 [대해 자세히 알아보겠습니다.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="447b6-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="447b6-109">**콘텐츠 준수:** Microsoft Information Protection과의 통합으로 보안 및 거버넌스를 개선하기 위해 콘텐츠를 제어하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="447b6-110">새로운 AI 서비스 및 기능을 사용하여 SharePoint Syntex를 사용하여 콘텐츠 이해 및 분류 앱을 콘텐츠 관리 흐름에 직접 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="447b6-111">콘텐츠를 이해하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="447b6-112">사용하는 모델 유형은 파일 형식 및 사용 사례를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="447b6-113">양식 처리</span><span class="sxs-lookup"><span data-stu-id="447b6-113">Form processing</span></span> | <span data-ttu-id="447b6-114">문서 이해</span><span class="sxs-lookup"><span data-stu-id="447b6-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="447b6-115">문서 라이브러리에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-115">Created from document library.</span></span> | <span data-ttu-id="447b6-116">SharePoint Syntex의 일부인 콘텐츠 센터에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="447b6-117">AI 작성기에서 만든 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-117">Model created in AI builder.</span></span> | <span data-ttu-id="447b6-118">기본 인터페이스에서 만든 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-118">Model created in native interface.</span></span> |
| <span data-ttu-id="447b6-119">반구조적 파일 형식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="447b6-120">구조화되지 않은 파일 형식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="447b6-121">Settable 분류자입니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-121">Settable classifier.</span></span> | <span data-ttu-id="447b6-122">선택적 추출기를 통해 학습 가능한 분류자입니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="447b6-123">단일 라이브러리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-123">Restricted to a single library.</span></span> | <span data-ttu-id="447b6-124">여러 라이브러리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="447b6-125">PDF, JPG, PNG 형식 교육 총 50MB/500 pp</span><span class="sxs-lookup"><span data-stu-id="447b6-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="447b6-126">부정적인 예제를 포함하여 5-10 PDF, Office 또는 전자 메일 파일에 대해 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="447b6-127">다음 표에서는 SharePoint Syntex의 가용성 및 라이선싱에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-127">The following table explains availability and licensing for SharePoint Syntex:</span></span>

| <span data-ttu-id="447b6-128">양식 처리</span><span class="sxs-lookup"><span data-stu-id="447b6-128">Form processing</span></span> | <span data-ttu-id="447b6-129">문서 이해</span><span class="sxs-lookup"><span data-stu-id="447b6-129">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="447b6-130">양식 처리는 Power Platform에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-130">Form processing relies on Power Platform.</span></span> <br><span data-ttu-id="447b6-131">Power Platform 및 AI Builder의 전역 가용성에 대한 자세한 내용은 [Power Platform 가용성을 참조하세요.](https://dynamics.microsoft.com/geographic-availability/)</span><span class="sxs-lookup"><span data-stu-id="447b6-131">For information about global availability for Power Platform and AI Builder, see [Power Platform availability](https://dynamics.microsoft.com/geographic-availability/).</span></span> | <span data-ttu-id="447b6-132">모든 지역에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-132">Available in all regions.</span></span> |
| <span data-ttu-id="447b6-133">AI 작성기 크레딧을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-133">Uses AI Builder credits.</span></span><br><span data-ttu-id="447b6-134">크레딧은 1M으로 일괄 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-134">Credits can be purchased in batches of 1M.</span></span><br><span data-ttu-id="447b6-135">300개 이상의 SharePoint Syntex 라이선스를 구매하면 1M 크레딧이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-135">1M credits are included when 300+ SharePoint Syntex licenses are purchased.</span></span><br><span data-ttu-id="447b6-136">1M 크레딧은 2,000개 파일 페이지를 처리하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-136">1M credits will allow processing of 2000 file pages.</span></span> | <span data-ttu-id="447b6-137">모델은 모든 라틴어 알파벳 언어로 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-137">Models work on all latin alphabet languages.</span></span> <span data-ttu-id="447b6-138">영어 외에 독일어, 스웨덴어, 프랑스어, 스페인어, 이탈리아어 및 포르투갈어</span><span class="sxs-lookup"><span data-stu-id="447b6-138">In addition to English: German, Swedish, French, Spanish, Italian, and Portuguese.</span></span> |
| <span data-ttu-id="447b6-139">기본 일반 데이터 서비스 환경에 대해 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-139">Provisioned against the default common data service environment.</span></span> | <span data-ttu-id="447b6-140">용량 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-140">Does not have capacity restrictions.</span></span> |

<span data-ttu-id="447b6-141">AI 작성기 크레딧 및 단위에 대한 자세한 내용은 [AI Builder 라이선스를 참조하세요.](https://docs.microsoft.com/ai-builder/administer-licensing)</span><span class="sxs-lookup"><span data-stu-id="447b6-141">For more information about AI Builder credits and units, see [AI Builder licensing](https://docs.microsoft.com/ai-builder/administer-licensing).</span></span>

<span data-ttu-id="447b6-142">SharePoint Syntex는 다음과 같은 Microsoft 365 규정 준수 기능과 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-142">SharePoint Syntex integrates with Microsoft 365 compliance features like:</span></span>

- <span data-ttu-id="447b6-143">문서 보존 기간 또는 외부 이벤트를 기준으로 레코드 정책을 정의하는 보존 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-143">Retention labels that define records policy based on document age or external events.</span></span>
- <span data-ttu-id="447b6-144">DLP, 암호화, 공유 및 조건부 액세스 정책을 설정하는 민감도 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-144">Sensitivity labels that set DLP, encryption, sharing, and conditional access policies.</span></span>

<span data-ttu-id="447b6-145">사용자는 레이블을 적용하거나 SharePoint Syntex AI 모델에 의해 자동으로 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-145">Users can apply labels, or they can be applied automatically by SharePoint Syntex AI models.</span></span> <span data-ttu-id="447b6-146">분석 및 파일 계획은 레이블 사용 및 정책의 확장된 관리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-146">Analytics and file plans provide scaled management of label usage and policies.</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="447b6-147">최적화할 파일럿 비즈니스 시나리오 확인</span><span class="sxs-lookup"><span data-stu-id="447b6-147">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="447b6-148">조직에서 SharePoint Syntex 사용을 준비하려면 먼저 유용한 시나리오를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-148">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="447b6-149">그 이유는 필요한 모델과 모델이 적용되는 위치를 기준으로 조직을 구성하는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-149">The why helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="447b6-150">다음은 문서 이해가 조직에 도움이 될 수 있는 몇 가지 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-150">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="447b6-151">콘텐츠 처리: 계약서, 작업 설명 및 기타 양식과 같은 문서를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-151">Content processing: Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="447b6-152">양식을 작성하고 모델을 교육하여 필드를 이해하고 매핑한 다음 양식을 실행하여 데이터를 자동으로 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-152">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="447b6-153">자세한 내용은 양식 처리 [개요를 참조하십시오.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="447b6-153">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="447b6-154">송장 분석: 송장에서 관련 세부 정보를 끌어오고 정책 준수 또는 적절하게 처리되고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="447b6-154">Invoice analysis: Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="447b6-155">SharePoint Syntex가 조직에 도움이 될 수 있는 방법을 생각해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-155">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="447b6-156">비즈니스 프로세스 자동화</span><span class="sxs-lookup"><span data-stu-id="447b6-156">Automate business processes</span></span>
- <span data-ttu-id="447b6-157">검색 정확도 향상</span><span class="sxs-lookup"><span data-stu-id="447b6-157">Improve search accuracy</span></span>
- <span data-ttu-id="447b6-158">규정 준수 위험 관리</span><span class="sxs-lookup"><span data-stu-id="447b6-158">Manage compliance risk</span></span>

### <a name="form-processing-scenario-example"></a><span data-ttu-id="447b6-159">양식 처리 시나리오 예제</span><span class="sxs-lookup"><span data-stu-id="447b6-159">Form processing scenario example</span></span>

<span data-ttu-id="447b6-160">예를 들어 SharePoint Syntex 및 Power Automate 기능을 사용하여 송장을 추적하고 모니터링하는 프로세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-160">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="447b6-161">송장 문서를 저장할 라이브러리를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-161">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="447b6-162">문서의 필드를 인식할 수 있는 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-162">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="447b6-163">추적할 필드를 목록으로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-163">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="447b6-164">흐름을 설정하여 다음을 통해 특정 이벤트를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-164">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="447b6-165">새 송장이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-165">A new invoice is added.</span></span>
    - <span data-ttu-id="447b6-166">송장 기한이 지난 경우</span><span class="sxs-lookup"><span data-stu-id="447b6-166">An invoice is past its due date.</span></span>
    - <span data-ttu-id="447b6-167">송장은 자동 승인 금액보다 큰 금액에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-167">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![SharePoint Syntex 및 Power Automate를 통해 송장 추적 및 모니터링](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="447b6-169">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-169">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="447b6-170">수동으로 수행하지 않고 송장에서 데이터를 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-170">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="447b6-171">워크플로를 사용하여 송장에 대해 작업하고 문제를 알리면 잠재적인 오류를 줄이고 규정 준수를 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-171">Reduce potential errors and ensure better compliance by using workflows to act on the invoices and notify you of any issues.</span></span>

### <a name="document-understanding-scenario-example"></a><span data-ttu-id="447b6-172">문서 이해 시나리오 예제</span><span class="sxs-lookup"><span data-stu-id="447b6-172">Document understanding scenario example</span></span>

<span data-ttu-id="447b6-173">또 다른 예로, 회사가 다른 회사 또는 개인과 계약한 계약을 식별하는 프로세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-173">As another example, you can set up a process to identify contracts that your company has with other companies or individuals.</span></span> <span data-ttu-id="447b6-174">이러한 계약에서 클라이언트 이름, 수수료, 날짜 또는 기타 중요한 정보와 같은 주요 정보를 추출하고 라이브러리에 이를 필드로 빠르게 볼 수 있도록 추가하는 모델을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-174">You can set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add that to the library as fields you can quickly view.</span></span> <span data-ttu-id="447b6-175">또한 문서 라이브러리에 보존 레이블을 적용하여 비즈니스 규정을 적절하게 준수하기 위해 특정 기간 전에 계약을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-175">And you can apply a retention label on the document library to ensure that contracts cannot be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="447b6-176">콘텐츠 센터에서 시작하여 계약에 대한 새 문서 이해 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-176">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="447b6-177">예제 문서를 양성 및 부정 예제로 업로드한 다음 교육을 실행하여 계약 문서를 식별하고 결과를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-177">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="447b6-178">추출기에서 클라이언트 이름, 수수료 및 날짜와 같은 계약의 필드를 식별하는 교육을 한 다음 추출기 테스트를 합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-178">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="447b6-179">모델이 완료되면 계약을 업로드할 수 있는 라이브러리에 모델을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-179">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="447b6-180">조직에서 계약에 필요한 기간 동안 계약이 라이브러리에 보존될 수 있도록 날짜 필드에 보존 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-180">Apply a retention label to the date field, so that contracts are retained in the library for the length of time your organization requires for contracts.</span></span>

![SharePoint Syntex 및 보존 레이블과의 계약 추적 및 모니터링](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="447b6-182">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-182">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="447b6-183">수동으로 수행하지 않고 계약에서 데이터를 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-183">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="447b6-184">보존 레이블을 사용하여 계약이 적절하게 유지되도록 하여 규정 준수를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-184">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="tips-for-identifying-scenarios"></a><span data-ttu-id="447b6-185">시나리오를 식별하기 위한 팁</span><span class="sxs-lookup"><span data-stu-id="447b6-185">Tips for identifying scenarios</span></span>

<span data-ttu-id="447b6-186">고려할 비즈니스 시나리오를 고려할 때 다음 질문을 스스로에게 물어보세요.</span><span class="sxs-lookup"><span data-stu-id="447b6-186">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="447b6-187">실제 문제를 해결하나요?</span><span class="sxs-lookup"><span data-stu-id="447b6-187">Does it solve a real problem?</span></span>
- <span data-ttu-id="447b6-188">광범위하게 사용되거나 광범위하게 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="447b6-188">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="447b6-189">이 정보를 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="447b6-189">Is it obtainable?</span></span>
- <span data-ttu-id="447b6-190">성공을 측정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="447b6-190">Can you measure success?</span></span>

<span data-ttu-id="447b6-191">영향 및 구현 용이성을 기반으로 시나리오의 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-191">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="447b6-192">초기 포커스 영역을 쉽게 구현할 수 있는 시나리오에 더 많은 영향을 미치게 합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-192">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="447b6-193">구현하기 어려운 영향이 낮은 시나리오의 우선 순위를 낮게 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-193">De-prioritize lower impact scenarios that are hard to implement.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="447b6-194">역할 및 & 식별</span><span class="sxs-lookup"><span data-stu-id="447b6-194">Identify roles & responsibilities</span></span>

<span data-ttu-id="447b6-195">조직에서 모델을 빌드하고 관리할 사용자 결정</span><span class="sxs-lookup"><span data-stu-id="447b6-195">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="447b6-196">다음과 같은 역할이 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-196">The following roles might be involved:</span></span>

| <span data-ttu-id="447b6-197">SharePoint/지식 관리자</span><span class="sxs-lookup"><span data-stu-id="447b6-197">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="447b6-198">Power Platform 관리자</span><span class="sxs-lookup"><span data-stu-id="447b6-198">Power Platform admin</span></span> | <span data-ttu-id="447b6-199">지식 관리자</span><span class="sxs-lookup"><span data-stu-id="447b6-199">Knowledge manager</span></span> | <span data-ttu-id="447b6-200">모델 소유자</span><span class="sxs-lookup"><span data-stu-id="447b6-200">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="447b6-201">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="447b6-201">AAD role</span></span>| <span data-ttu-id="447b6-202">역할 추가</span><span class="sxs-lookup"><span data-stu-id="447b6-202">ADD role</span></span> | <span data-ttu-id="447b6-203">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="447b6-203">AAD role</span></span> | <span data-ttu-id="447b6-204">챔피언</span><span class="sxs-lookup"><span data-stu-id="447b6-204">Champions</span></span> |
| <span data-ttu-id="447b6-205">양식 처리 구성</span><span class="sxs-lookup"><span data-stu-id="447b6-205">Configure form processing</span></span> | <span data-ttu-id="447b6-206">양식 처리를 위한 일반 데이터 서비스 환경 구성</span><span class="sxs-lookup"><span data-stu-id="447b6-206">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="447b6-207">사용 사례 수집</span><span class="sxs-lookup"><span data-stu-id="447b6-207">Gather use cases</span></span> | <span data-ttu-id="447b6-208">비즈니스 사용 사례 수집</span><span class="sxs-lookup"><span data-stu-id="447b6-208">Gather business use cases</span></span> |
| <span data-ttu-id="447b6-209">콘텐츠 센터 및 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="447b6-209">Manage content centers and permissions</span></span>| <span data-ttu-id="447b6-210">AIB 크레딧 구입 및 할당</span><span class="sxs-lookup"><span data-stu-id="447b6-210">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="447b6-211">모범 사례 설정 및 모델 분석 검토</span><span class="sxs-lookup"><span data-stu-id="447b6-211">Establish best practices and review model analytics</span></span> | <span data-ttu-id="447b6-212">모델 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="447b6-212">Create and apply models</span></span> |

<span data-ttu-id="447b6-213">지식 관리자, 비즈니스 프로세스 소유자 및 콘텐츠 모델 소유자는 조직에서 샘플 모델 및 챔피언 채택을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-213">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="447b6-214">관련이 있을 수 있는 다른 사람: 규정 준수 관리자, 세분화 관리자.</span><span class="sxs-lookup"><span data-stu-id="447b6-214">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="447b6-215">어디에서 모델을 빌드하고 적용할 것인가요?</span><span class="sxs-lookup"><span data-stu-id="447b6-215">Where will they build and apply the models?</span></span> <span data-ttu-id="447b6-216">개선할 수 있는 기존 프로세스 또는 리포지토리가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="447b6-216">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="447b6-217">양식 처리: 양식 처리 작업을 받을 사이트를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-217">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="447b6-218">문서 이해: 서로 다른 비즈니스 영역에 대해 여러 콘텐츠 센터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-218">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="447b6-219">전략적 위치</span><span class="sxs-lookup"><span data-stu-id="447b6-219">Strategic positioning</span></span>

<span data-ttu-id="447b6-220">관련자와 협의하여 SharePoint Syntex 사용 전략에 맞춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-220">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="447b6-221">이 위치 관리에 도움이 되는 다음 리소스를 조사하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-221">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="447b6-222">비즈니스 결과:</span><span class="sxs-lookup"><span data-stu-id="447b6-222">Business outcomes:</span></span>
  - <span data-ttu-id="447b6-223">잠재적 회계 결과</span><span class="sxs-lookup"><span data-stu-id="447b6-223">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="447b6-224">잠재적인 민첩성 결과</span><span class="sxs-lookup"><span data-stu-id="447b6-224">Potential agility outcomes</span></span>
  - <span data-ttu-id="447b6-225">비즈니스 결과 서식 파일</span><span class="sxs-lookup"><span data-stu-id="447b6-225">Business outcome template</span></span>
- <span data-ttu-id="447b6-226">이해 관계자/Exec 스폰서 구입/조정</span><span class="sxs-lookup"><span data-stu-id="447b6-226">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="447b6-227">비즈니스 사례 데크</span><span class="sxs-lookup"><span data-stu-id="447b6-227">Business case decks</span></span>
  - <span data-ttu-id="447b6-228">재무 모델</span><span class="sxs-lookup"><span data-stu-id="447b6-228">Financial models</span></span>
  - <span data-ttu-id="447b6-229">회사 준비 - 문화</span><span class="sxs-lookup"><span data-stu-id="447b6-229">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="447b6-230">관련자 파악</span><span class="sxs-lookup"><span data-stu-id="447b6-230">Identify stakeholders</span></span>

<span data-ttu-id="447b6-231">프로젝트 관련자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-231">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="447b6-232">역할</span><span class="sxs-lookup"><span data-stu-id="447b6-232">Role</span></span> |<span data-ttu-id="447b6-233">책임</span><span class="sxs-lookup"><span data-stu-id="447b6-233">Responsibilities</span></span> |<span data-ttu-id="447b6-234">부서</span><span class="sxs-lookup"><span data-stu-id="447b6-234">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="447b6-235">Executive sponsor(s)</span><span class="sxs-lookup"><span data-stu-id="447b6-235">Executive sponsor(s)</span></span>   | <span data-ttu-id="447b6-236">회사에 대한 높은 수준의 비전과 가치 전달</span><span class="sxs-lookup"><span data-stu-id="447b6-236">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="447b6-237">임원진</span><span class="sxs-lookup"><span data-stu-id="447b6-237">Executive leadership</span></span>   |
| <span data-ttu-id="447b6-238">프로젝트 주도자</span><span class="sxs-lookup"><span data-stu-id="447b6-238">Project lead(s)</span></span> | <span data-ttu-id="447b6-239">전체 시작 실행 및 출시 프로세스에 대한 오버시</span><span class="sxs-lookup"><span data-stu-id="447b6-239">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="447b6-240">프로젝트 관리</span><span class="sxs-lookup"><span data-stu-id="447b6-240">Project management</span></span> |
| <span data-ttu-id="447b6-241">지식 관리자</span><span class="sxs-lookup"><span data-stu-id="447b6-241">Knowledge administrators</span></span>| <span data-ttu-id="447b6-242">콘텐츠 센터 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="447b6-242">Create and manage the content centers</span></span> | <span data-ttu-id="447b6-243">IT 또는 기타 부서</span><span class="sxs-lookup"><span data-stu-id="447b6-243">IT or other department</span></span>|
| <span data-ttu-id="447b6-244">콘텐츠 관리자 및 모델 소유자</span><span class="sxs-lookup"><span data-stu-id="447b6-244">Content managers and model owners</span></span>| <span data-ttu-id="447b6-245">사용 사례 수집 및 모델 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="447b6-245">Gather use cases and create and apply models</span></span> | <span data-ttu-id="447b6-246">모든 부서</span><span class="sxs-lookup"><span data-stu-id="447b6-246">Any department</span></span>|
| <span data-ttu-id="447b6-247">챔피언</span><span class="sxs-lookup"><span data-stu-id="447b6-247">Champions</span></span> | <span data-ttu-id="447b6-248">이의 처리를 전도하고 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-248">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="447b6-249">모든 부서(직원)</span><span class="sxs-lookup"><span data-stu-id="447b6-249">Any department (staff)</span></span> |
| <span data-ttu-id="447b6-250">테넌트 관리자</span><span class="sxs-lookup"><span data-stu-id="447b6-250">Tenant administrator</span></span> | <span data-ttu-id="447b6-251">테넌트 수준 설정 구성</span><span class="sxs-lookup"><span data-stu-id="447b6-251">Configure tenant-level settings</span></span> | <span data-ttu-id="447b6-252">IT 부서</span><span class="sxs-lookup"><span data-stu-id="447b6-252">IT department</span></span>|
| <span data-ttu-id="447b6-253">Power Platform 관리자</span><span class="sxs-lookup"><span data-stu-id="447b6-253">Power Platform administrator</span></span>| <span data-ttu-id="447b6-254">일반 데이터 서비스 환경 구성</span><span class="sxs-lookup"><span data-stu-id="447b6-254">Configure common data services environment</span></span> | <span data-ttu-id="447b6-255">IT 부서</span><span class="sxs-lookup"><span data-stu-id="447b6-255">IT department</span></span>|

> [!Note]
> <span data-ttu-id="447b6-256">이러한 각 역할을 롤아웃 전체에서 이행하는 것이 까다로우면 식별된 솔루션을 시작하는 데 이러한 역할이 모두 필요하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-256">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="447b6-257">준비 검사 목록</span><span class="sxs-lookup"><span data-stu-id="447b6-257">Readiness checklist</span></span>

<span data-ttu-id="447b6-258">SharePoint Syntex 구현을 준비하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-258">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![콘텐츠 이해를 위한 준비](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="447b6-260">종료 상태 계획</span><span class="sxs-lookup"><span data-stu-id="447b6-260">Plan the end state</span></span>
    - <span data-ttu-id="447b6-261">문서 이해 모델은 끝이 아니라 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-261">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="447b6-262">추출된 메타데이터의 값을 다음을 사용하여 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-262">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="447b6-263">검색</span><span class="sxs-lookup"><span data-stu-id="447b6-263">Search</span></span>
      - <span data-ttu-id="447b6-264">필터링 및 보기 서식</span><span class="sxs-lookup"><span data-stu-id="447b6-264">Filtering and view formatting</span></span>
      - <span data-ttu-id="447b6-265">규정 준수</span><span class="sxs-lookup"><span data-stu-id="447b6-265">Compliance</span></span>
      - <span data-ttu-id="447b6-266">자동화</span><span class="sxs-lookup"><span data-stu-id="447b6-266">Automation</span></span>
2. <span data-ttu-id="447b6-267">식별</span><span class="sxs-lookup"><span data-stu-id="447b6-267">Identify</span></span>
    - <span data-ttu-id="447b6-268">기존 정보 아키텍처 및 콘텐츠 관리 기능 사용을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-268">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="447b6-269">기존 콘텐츠 형식이 모델에 좋은 후보인가요?</span><span class="sxs-lookup"><span data-stu-id="447b6-269">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="447b6-270">메타데이터를 통해 개선할 기존 프로세스는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="447b6-270">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="447b6-271">Design</span><span class="sxs-lookup"><span data-stu-id="447b6-271">Design</span></span>
    - <span data-ttu-id="447b6-272">정보 아키텍처, 관리되는 메타데이터 및 콘텐츠 형식에 대한 접근 방식 디자인</span><span class="sxs-lookup"><span data-stu-id="447b6-272">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="447b6-273">정의, 만들기, 관리 프로세스를 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-273">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="447b6-274">조직 참여</span><span class="sxs-lookup"><span data-stu-id="447b6-274">Engage your organization</span></span>

1. <span data-ttu-id="447b6-275">지분 소유자를 식별하고, 시나리오를 확인하고, 프로젝트 계획을 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-275">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="447b6-276">설정을 구성하고 라이선스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-276">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="447b6-277">인식과 교육 시작 - 챔피언을 모집합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-277">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="447b6-278">단계로 롤아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-278">Roll out in stages.</span></span>  
1. <span data-ttu-id="447b6-279">피드백을 수집하고 이르게 합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-279">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="447b6-280">사용량이 증가함에 따라 필요한 경우 모든 AI 작성기 크레딧에 대한 계획이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="447b6-280">As usage grows plan for any AI Builder credits as needed.</span></span>
