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
ms.openlocfilehash: 18bc5d8d0f80f7cee024f4d6358361509879bd11
ms.sourcegitcommit: 86f75cf77a7a446a79226ca530bd7b5eb39189cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/18/2020
ms.locfileid: "49717022"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="ba0da-103">Microsoft SharePoint Syntex 채택: 시작</span><span class="sxs-lookup"><span data-stu-id="ba0da-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="ba0da-104">SharePoint Syntex에서 사용할 수 있는 지능형 콘텐츠 서비스는 다음 세 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="ba0da-105">**콘텐츠 이해:** 코드 없는 AI 모델을 만들어 콘텐츠에서 정보를 분류하고 추출하여 지식 검색 및 재사용을 위한 메타데이터를 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="ba0da-106">콘텐츠 이해에 [대해 자세히 알아보겠습니다.](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ba0da-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="ba0da-107">**콘텐츠 처리:** Power Automate를 사용하여 콘텐츠의 캡처, 수집 및 분류를 자동화하고 콘텐츠 중심 프로세스를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-107">**Content processing:** Automate capture, ingestion and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="ba0da-108">콘텐츠 처리에 [대해 자세히 알아보겠습니다.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ba0da-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="ba0da-109">**콘텐츠 준수:** Microsoft Information Protection과의 통합으로 보안 및 거버넌스를 개선하기 위해 콘텐츠를 제어하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="ba0da-110">새로운 AI 서비스 및 기능을 사용하여 SharePoint Syntex를 사용하여 콘텐츠 이해 및 분류 앱을 콘텐츠 관리 흐름에 직접 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex:</span></span>

|<span data-ttu-id="ba0da-111">수동 입력</span><span class="sxs-lookup"><span data-stu-id="ba0da-111">Manual entry</span></span>| <span data-ttu-id="ba0da-112">양식 처리</span><span class="sxs-lookup"><span data-stu-id="ba0da-112">Form processing</span></span> | <span data-ttu-id="ba0da-113">문서 이해</span><span class="sxs-lookup"><span data-stu-id="ba0da-113">Document understanding</span></span> |
|:-------|:--------|:--------|
| <span data-ttu-id="ba0da-114">데이터 입력 및 콘텐츠에 대한 많은 작업</span><span class="sxs-lookup"><span data-stu-id="ba0da-114">Data entry and labor-intensive on any content</span></span> | <span data-ttu-id="ba0da-115">디지털 콘텐츠 처리 - 사진, 스캔, 영수증, 명명, OCR 및 텍스트가 & 비디오</span><span class="sxs-lookup"><span data-stu-id="ba0da-115">Process digital content - photos, scans, receipts, business cards, videos with OCR & text</span></span> |  <span data-ttu-id="ba0da-116">계약, 이력서 및 기타 구조적 문서에서 콘텐츠 형식 및 메타데이터 캡처</span><span class="sxs-lookup"><span data-stu-id="ba0da-116">Capture content types and  metadata from contracts, resumes, and other structured documents</span></span> |
| <span data-ttu-id="ba0da-117">대화형</span><span class="sxs-lookup"><span data-stu-id="ba0da-117">Interactive</span></span>   | <span data-ttu-id="ba0da-118">미리 구축되고 자동화된</span><span class="sxs-lookup"><span data-stu-id="ba0da-118">Pre-built, automated</span></span>   | <span data-ttu-id="ba0da-119">사용자 지정, 보조</span><span class="sxs-lookup"><span data-stu-id="ba0da-119">Custom, assisted</span></span>  |
| <span data-ttu-id="ba0da-120">작업 수행자</span><span class="sxs-lookup"><span data-stu-id="ba0da-120">People doing the work</span></span> | <span data-ttu-id="ba0da-121">주제 전문가(중소기업)가 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-121">Taught by your subject matter experts (SMEs).</span></span> <span data-ttu-id="ba0da-122">계약, 이력서, 기타 구조적 문서에서 콘텐츠 형식 및 메타데이터를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-122">Capture content types and  metadata from contracts, resumes, other structured documents.</span></span> | <span data-ttu-id="ba0da-123">중소기업의 참여가 적습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-123">SMEs are less involved.</span></span> <span data-ttu-id="ba0da-124">구매 주문, 응용 프로그램, 기타 반구조적 문서 및 구조적 문서에서</span><span class="sxs-lookup"><span data-stu-id="ba0da-124">from purchase orders, applications, other semi structured and structured documents</span></span> |

<span data-ttu-id="ba0da-125">다음 표에서는 SharePoint Syntex를 사용할 때 얻을 수 있는 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-125">The following table explains what you get when you use SharePoint Syntex:</span></span>

| <span data-ttu-id="ba0da-126">양식 처리</span><span class="sxs-lookup"><span data-stu-id="ba0da-126">Form processing</span></span> | <span data-ttu-id="ba0da-127">문서 이해</span><span class="sxs-lookup"><span data-stu-id="ba0da-127">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="ba0da-128">APAC, 오스트레일리아, 캐나다, EU, JP, LATAM, 영국, 미국에서 사용 가능</span><span class="sxs-lookup"><span data-stu-id="ba0da-128">Available in APAC, Australia, Canada, EU, JP, LATAM, UK, US</span></span> | <span data-ttu-id="ba0da-129">모든 지역에서 사용 가능</span><span class="sxs-lookup"><span data-stu-id="ba0da-129">Available in all regions</span></span> |
| <span data-ttu-id="ba0da-130">AI 작성기 크레딧 사용 - 1M 크레딧 = 2000페이지 소비는 약 2,000 송장=2단위입니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-130">Uses AI Builder credits - 1M credits = 2000 pages; Consumption is about 2000 invoices=2 units.</span></span> <span data-ttu-id="ba0da-131">전원 자동화가 필요합니다. 추가해야 하는 경우 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-131">Power Automate is required - if you need more you can add it.</span></span> <span data-ttu-id="ba0da-132">구매한 300개 이상의 라이선스에 할당된 1M 크레딧</span><span class="sxs-lookup"><span data-stu-id="ba0da-132">1M credits allocated for 300+ licenses purchased.</span></span> <span data-ttu-id="ba0da-133">크레딧을 별도로 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-133">You can also purchase credits separately.</span></span> | <span data-ttu-id="ba0da-134">모델은 모든 라틴어 알파벳 언어로 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-134">Models work on all latin alphabet languages.</span></span> <span data-ttu-id="ba0da-135">영어 외에 독일어, 스웨덴어, 프랑스어, 스페인어, 이탈리아어 및 포르투갈어</span><span class="sxs-lookup"><span data-stu-id="ba0da-135">In addition to English: German, Swedish, French, Spanish, Italian, and Portuguese.</span></span> |
| <span data-ttu-id="ba0da-136">기본 일반 데이터 서비스 환경에 대해 프로비전</span><span class="sxs-lookup"><span data-stu-id="ba0da-136">Provisioned against the default common data service environment</span></span>| <span data-ttu-id="ba0da-137">용량 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-137">Does not have capacity restrictions.</span></span> |

<span data-ttu-id="ba0da-138">콘텐츠를 이해하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-138">There are two different ways of understanding your content.</span></span> <span data-ttu-id="ba0da-139">사용하는 모델 유형은 파일 형식 및 사용 사례를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-139">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="ba0da-140">양식 처리</span><span class="sxs-lookup"><span data-stu-id="ba0da-140">Form processing</span></span> | <span data-ttu-id="ba0da-141">문서 이해</span><span class="sxs-lookup"><span data-stu-id="ba0da-141">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="ba0da-142">문서 라이브러리에서 만든 문서</span><span class="sxs-lookup"><span data-stu-id="ba0da-142">Created from document library</span></span> | <span data-ttu-id="ba0da-143">SharePoint Syntex의 일부인 콘텐츠 센터에서 생성</span><span class="sxs-lookup"><span data-stu-id="ba0da-143">Created in the content center, part of SharePoint Syntex</span></span> |
| <span data-ttu-id="ba0da-144">AI 작성기에서 만든 모델</span><span class="sxs-lookup"><span data-stu-id="ba0da-144">Model created in AI builder</span></span> | <span data-ttu-id="ba0da-145">기본 인터페이스에서 만든 모델</span><span class="sxs-lookup"><span data-stu-id="ba0da-145">Model created in native interface</span></span> |
| <span data-ttu-id="ba0da-146">반구조적 파일 형식에 사용</span><span class="sxs-lookup"><span data-stu-id="ba0da-146">Used for semi-structured file formats</span></span> | <span data-ttu-id="ba0da-147">구조화되지 않은 파일 형식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-147">Used for unstructured file formats</span></span> |
| <span data-ttu-id="ba0da-148">Settable 분류자</span><span class="sxs-lookup"><span data-stu-id="ba0da-148">Settable classifier</span></span> | <span data-ttu-id="ba0da-149">선택적 추출기를 통해 학습 가능한 분류자</span><span class="sxs-lookup"><span data-stu-id="ba0da-149">Trainable classifier with optional extractors</span></span> |
| <span data-ttu-id="ba0da-150">단일 라이브러리로 제한</span><span class="sxs-lookup"><span data-stu-id="ba0da-150">Restricted to a single library</span></span> | <span data-ttu-id="ba0da-151">여러 라이브러리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-151">Can be applied to multiple libraries</span></span> |
| <span data-ttu-id="ba0da-152">PDF, JPG, PNG 형식 교육 총 50MB/500 pp</span><span class="sxs-lookup"><span data-stu-id="ba0da-152">Train on PDF, JPG, PNG format, total 50 MB/500 pp</span></span> | <span data-ttu-id="ba0da-153">부정적인 예제를 포함하여 5-10 PDF, Office 또는 전자 메일 파일 교육</span><span class="sxs-lookup"><span data-stu-id="ba0da-153">Train on 5-10 PDF, Office, or email files, including negative examples</span></span> |

<span data-ttu-id="ba0da-154">SharePoint Syntex는 다음과 같은 Microsoft 365 규정 준수 기능과 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-154">SharePoint Syntex integrates with Microsoft 365 compliance features like:</span></span>

- <span data-ttu-id="ba0da-155">문서 보존 기간 또는 외부 이벤트를 기준으로 레코드 정책을 정의하는 보존 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-155">Retention labels that define records policy based on document age or external events.</span></span>
- <span data-ttu-id="ba0da-156">DLP, 암호화, 공유 및 조건부 액세스 정책을 설정하는 민감도 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-156">Sensitivity labels that set DLP, encryption, sharing, and conditional access policies.</span></span>

<span data-ttu-id="ba0da-157">사용자는 레이블을 적용하거나 SharePoint Syntex AI 모델에 의해 자동으로 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-157">Users can apply labels, or they can be applied automatically by SharePoint Syntex AI models.</span></span> <span data-ttu-id="ba0da-158">분석 및 파일 계획은 레이블 사용 및 정책의 확장된 관리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-158">Analytics and file plans provide scaled management of label usage and policies.</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="ba0da-159">최적화할 파일럿 비즈니스 시나리오 확인</span><span class="sxs-lookup"><span data-stu-id="ba0da-159">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="ba0da-160">조직에서 SharePoint Syntex 사용을 준비하려면 먼저 유용한 시나리오를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-160">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="ba0da-161">그 이유는 필요한 모델과 모델이 적용되는 위치를 기준으로 조직을 구성하는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-161">The why helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="ba0da-162">다음은 문서 이해가 조직에 도움이 될 수 있는 몇 가지 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-162">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="ba0da-163">콘텐츠 처리: 계약서, 작업 설명 및 기타 양식과 같은 문서를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-163">Content processing: Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="ba0da-164">양식을 작성하고 모델을 교육하여 필드를 이해하고 매핑한 다음 양식을 실행하여 데이터를 자동으로 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-164">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="ba0da-165">자세한 내용은 양식 처리 [개요를 참조하십시오.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ba0da-165">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="ba0da-166">송장 분석: 송장에서 관련 세부 정보를 끌어오고 정책 준수 또는 적절하게 처리되고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ba0da-166">Invoice analysis: Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="ba0da-167">SharePoint Syntex가 조직에 도움이 될 수 있는 방법을 생각해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-167">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="ba0da-168">비즈니스 프로세스 자동화</span><span class="sxs-lookup"><span data-stu-id="ba0da-168">Automate business processes</span></span>
- <span data-ttu-id="ba0da-169">검색 정확도 향상</span><span class="sxs-lookup"><span data-stu-id="ba0da-169">Improve search accuracy</span></span>
- <span data-ttu-id="ba0da-170">규정 준수 위험 관리</span><span class="sxs-lookup"><span data-stu-id="ba0da-170">Manage compliance risk</span></span>

### <a name="form-processing-scenario-example"></a><span data-ttu-id="ba0da-171">양식 처리 시나리오 예제</span><span class="sxs-lookup"><span data-stu-id="ba0da-171">Form processing scenario example</span></span>

<span data-ttu-id="ba0da-172">예를 들어 SharePoint Syntex 및 Power Automate 기능을 사용하여 송장을 추적하고 모니터링하는 프로세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-172">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="ba0da-173">송장 문서를 저장할 라이브러리를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-173">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="ba0da-174">문서의 필드를 인식할 수 있는 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-174">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="ba0da-175">추적할 필드를 목록으로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-175">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="ba0da-176">흐름을 설정하여 다음을 통해 특정 이벤트를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-176">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="ba0da-177">새 송장이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-177">A new invoice is added.</span></span>
    - <span data-ttu-id="ba0da-178">송장 기한이 지난 경우</span><span class="sxs-lookup"><span data-stu-id="ba0da-178">An invoice is past its due date.</span></span>
    - <span data-ttu-id="ba0da-179">송장은 자동 승인 금액보다 큰 금액에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-179">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![SharePoint Syntex 및 Power Automate를 통해 송장 추적 및 모니터링](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="ba0da-181">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-181">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="ba0da-182">수동으로 수행하지 않고 송장에서 데이터를 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-182">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="ba0da-183">워크플로를 사용하여 송장에 대해 작업하고 문제를 알리면 잠재적인 오류를 줄이고 규정 준수를 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-183">Reduce potential errors and ensure better compliance by using workflows to act on the invoices and notify you of any issues.</span></span>

### <a name="document-understanding-scenario-example"></a><span data-ttu-id="ba0da-184">문서 이해 시나리오 예제</span><span class="sxs-lookup"><span data-stu-id="ba0da-184">Document understanding scenario example</span></span>

<span data-ttu-id="ba0da-185">또 다른 예로, 회사가 다른 회사 또는 개인과 계약한 계약을 식별하는 프로세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-185">As another example, you can set up a process to identify contracts that your company has with other companies or individuals.</span></span> <span data-ttu-id="ba0da-186">이러한 계약에서 클라이언트 이름, 수수료, 날짜 또는 기타 중요한 정보와 같은 주요 정보를 추출하고 라이브러리에 이를 필드로 빠르게 볼 수 있도록 추가하는 모델을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-186">You can set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add that to the library as fields you can quickly view.</span></span> <span data-ttu-id="ba0da-187">또한 문서 라이브러리에 보존 레이블을 적용하여 비즈니스 규정을 적절하게 준수하기 위해 특정 기간 전에 계약을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-187">And you can apply a retention label on the document library to ensure that contracts cannot be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="ba0da-188">콘텐츠 센터에서 시작하여 계약에 대한 새 문서 이해 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-188">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="ba0da-189">예제 문서를 양성 및 부정 예제로 업로드한 다음 교육을 실행하여 계약 문서를 식별하고 결과를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-189">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="ba0da-190">추출기에서 클라이언트 이름, 수수료 및 날짜와 같은 계약의 필드를 식별하는 교육을 한 다음 추출기 테스트를 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-190">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="ba0da-191">모델이 완료되면 계약을 업로드할 수 있는 라이브러리에 모델을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-191">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="ba0da-192">조직에서 계약에 필요한 기간 동안 계약이 라이브러리에 보존될 수 있도록 날짜 필드에 보존 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-192">Apply a retention label to the date field, so that contracts are retained in the library for the length of time your organization requires for contracts.</span></span>

![SharePoint Syntex 및 보존 레이블과의 계약 추적 및 모니터링](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="ba0da-194">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-194">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="ba0da-195">수동으로 수행하지 않고 계약에서 데이터를 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-195">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="ba0da-196">보존 레이블을 사용하여 계약이 적절하게 유지되도록 하여 규정 준수를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-196">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="tips-for-identifying-scenarios"></a><span data-ttu-id="ba0da-197">시나리오를 식별하기 위한 팁</span><span class="sxs-lookup"><span data-stu-id="ba0da-197">Tips for identifying scenarios</span></span>

<span data-ttu-id="ba0da-198">고려할 비즈니스 시나리오를 고려할 때 다음 질문을 스스로에게 물어보세요.</span><span class="sxs-lookup"><span data-stu-id="ba0da-198">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="ba0da-199">실제 문제를 해결하나요?</span><span class="sxs-lookup"><span data-stu-id="ba0da-199">Does it solve a real problem?</span></span>
- <span data-ttu-id="ba0da-200">광범위하게 사용되거나 광범위하게 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="ba0da-200">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="ba0da-201">이 정보를 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ba0da-201">Is it obtainable?</span></span>
- <span data-ttu-id="ba0da-202">성공을 측정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ba0da-202">Can you measure success?</span></span>

<span data-ttu-id="ba0da-203">영향 및 구현 용이성을 기반으로 시나리오의 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-203">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="ba0da-204">초기 포커스 영역을 쉽게 구현할 수 있는 시나리오에 더 많은 영향을 미치게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-204">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="ba0da-205">구현하기 어려운 영향이 낮은 시나리오의 우선 순위를 낮게 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-205">De-prioritize lower impact scenarios that are hard to implement.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="ba0da-206">역할 및 & 식별</span><span class="sxs-lookup"><span data-stu-id="ba0da-206">Identify roles & responsibilities</span></span>

<span data-ttu-id="ba0da-207">조직에서 모델을 빌드하고 관리할 사용자 결정</span><span class="sxs-lookup"><span data-stu-id="ba0da-207">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="ba0da-208">다음과 같은 역할이 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-208">The following roles might be involved:</span></span>

| <span data-ttu-id="ba0da-209">SharePoint/지식 관리자</span><span class="sxs-lookup"><span data-stu-id="ba0da-209">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="ba0da-210">Power Platform 관리자</span><span class="sxs-lookup"><span data-stu-id="ba0da-210">Power Platform admin</span></span> | <span data-ttu-id="ba0da-211">지식 관리자</span><span class="sxs-lookup"><span data-stu-id="ba0da-211">Knowledge manager</span></span> | <span data-ttu-id="ba0da-212">모델 소유자</span><span class="sxs-lookup"><span data-stu-id="ba0da-212">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="ba0da-213">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="ba0da-213">AAD role</span></span>| <span data-ttu-id="ba0da-214">역할 추가</span><span class="sxs-lookup"><span data-stu-id="ba0da-214">ADD role</span></span> | <span data-ttu-id="ba0da-215">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="ba0da-215">AAD role</span></span> | <span data-ttu-id="ba0da-216">챔피언</span><span class="sxs-lookup"><span data-stu-id="ba0da-216">Champions</span></span> |
| <span data-ttu-id="ba0da-217">양식 처리 구성</span><span class="sxs-lookup"><span data-stu-id="ba0da-217">Configure form processing</span></span> | <span data-ttu-id="ba0da-218">양식 처리를 위한 일반 데이터 서비스 환경 구성</span><span class="sxs-lookup"><span data-stu-id="ba0da-218">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="ba0da-219">사용 사례 수집</span><span class="sxs-lookup"><span data-stu-id="ba0da-219">Gather use cases</span></span> | <span data-ttu-id="ba0da-220">비즈니스 사용 사례 수집</span><span class="sxs-lookup"><span data-stu-id="ba0da-220">Gather business use cases</span></span> |
| <span data-ttu-id="ba0da-221">콘텐츠 센터 및 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="ba0da-221">Manage content centers and permissions</span></span>| <span data-ttu-id="ba0da-222">AIB 크레딧 구입 및 할당</span><span class="sxs-lookup"><span data-stu-id="ba0da-222">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="ba0da-223">모범 사례 설정 및 모델 분석 검토</span><span class="sxs-lookup"><span data-stu-id="ba0da-223">Establish best practices and review model analytics</span></span> | <span data-ttu-id="ba0da-224">모델 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="ba0da-224">Create and apply models</span></span> |

<span data-ttu-id="ba0da-225">지식 관리자, 비즈니스 프로세스 소유자 및 콘텐츠 모델 소유자는 조직에서 샘플 모델 및 챔피언 채택을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-225">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="ba0da-226">관련이 있을 수 있는 다른 사람: 규정 준수 관리자, 세분화 관리자.</span><span class="sxs-lookup"><span data-stu-id="ba0da-226">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="ba0da-227">어디에서 모델을 빌드하고 적용할 것인가요?</span><span class="sxs-lookup"><span data-stu-id="ba0da-227">Where will they build and apply the models?</span></span> <span data-ttu-id="ba0da-228">개선할 수 있는 기존 프로세스 또는 리포지토리가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="ba0da-228">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="ba0da-229">양식 처리: 양식 처리 작업을 받을 사이트를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-229">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="ba0da-230">문서 이해: 서로 다른 비즈니스 영역에 대해 여러 콘텐츠 센터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-230">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="ba0da-231">전략적 위치</span><span class="sxs-lookup"><span data-stu-id="ba0da-231">Strategic positioning</span></span>

<span data-ttu-id="ba0da-232">관련자와 협의하여 SharePoint Syntex 사용 전략에 맞춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-232">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="ba0da-233">이 위치 관리에 도움이 되는 다음 리소스를 조사하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-233">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="ba0da-234">비즈니스 결과:</span><span class="sxs-lookup"><span data-stu-id="ba0da-234">Business outcomes:</span></span>
  - <span data-ttu-id="ba0da-235">잠재적 회계 결과</span><span class="sxs-lookup"><span data-stu-id="ba0da-235">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="ba0da-236">잠재적인 민첩성 결과</span><span class="sxs-lookup"><span data-stu-id="ba0da-236">Potential agility outcomes</span></span>
  - <span data-ttu-id="ba0da-237">비즈니스 결과 서식 파일</span><span class="sxs-lookup"><span data-stu-id="ba0da-237">Business outcome template</span></span>
- <span data-ttu-id="ba0da-238">이해 관계자/Exec 스폰서 구입/조정</span><span class="sxs-lookup"><span data-stu-id="ba0da-238">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="ba0da-239">비즈니스 사례 데크</span><span class="sxs-lookup"><span data-stu-id="ba0da-239">Business case decks</span></span>
  - <span data-ttu-id="ba0da-240">재무 모델</span><span class="sxs-lookup"><span data-stu-id="ba0da-240">Financial models</span></span>
  - <span data-ttu-id="ba0da-241">회사 준비 - 문화</span><span class="sxs-lookup"><span data-stu-id="ba0da-241">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="ba0da-242">관련자 파악</span><span class="sxs-lookup"><span data-stu-id="ba0da-242">Identify stakeholders</span></span>

<span data-ttu-id="ba0da-243">프로젝트 관련자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-243">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="ba0da-244">역할</span><span class="sxs-lookup"><span data-stu-id="ba0da-244">Role</span></span> |<span data-ttu-id="ba0da-245">책임</span><span class="sxs-lookup"><span data-stu-id="ba0da-245">Responsibilities</span></span> |<span data-ttu-id="ba0da-246">부서</span><span class="sxs-lookup"><span data-stu-id="ba0da-246">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="ba0da-247">Executive sponsor(s)</span><span class="sxs-lookup"><span data-stu-id="ba0da-247">Executive sponsor(s)</span></span>   | <span data-ttu-id="ba0da-248">회사에 대한 높은 수준의 비전과 가치 전달</span><span class="sxs-lookup"><span data-stu-id="ba0da-248">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="ba0da-249">임원진</span><span class="sxs-lookup"><span data-stu-id="ba0da-249">Executive leadership</span></span>   |
| <span data-ttu-id="ba0da-250">프로젝트 주도자</span><span class="sxs-lookup"><span data-stu-id="ba0da-250">Project lead(s)</span></span> | <span data-ttu-id="ba0da-251">전체 시작 실행 및 출시 프로세스에 대한 오버시</span><span class="sxs-lookup"><span data-stu-id="ba0da-251">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="ba0da-252">프로젝트 관리</span><span class="sxs-lookup"><span data-stu-id="ba0da-252">Project management</span></span> |
| <span data-ttu-id="ba0da-253">지식 관리자</span><span class="sxs-lookup"><span data-stu-id="ba0da-253">Knowledge administrators</span></span>| <span data-ttu-id="ba0da-254">콘텐츠 센터 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="ba0da-254">Create and manage the content centers</span></span> | <span data-ttu-id="ba0da-255">IT 또는 기타 부서</span><span class="sxs-lookup"><span data-stu-id="ba0da-255">IT or other department</span></span>|
| <span data-ttu-id="ba0da-256">콘텐츠 관리자 및 모델 소유자</span><span class="sxs-lookup"><span data-stu-id="ba0da-256">Content managers and model owners</span></span>| <span data-ttu-id="ba0da-257">사용 사례 수집 및 모델 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="ba0da-257">Gather use cases and create and apply models</span></span> | <span data-ttu-id="ba0da-258">모든 부서</span><span class="sxs-lookup"><span data-stu-id="ba0da-258">Any department</span></span>|
| <span data-ttu-id="ba0da-259">챔피언</span><span class="sxs-lookup"><span data-stu-id="ba0da-259">Champions</span></span> | <span data-ttu-id="ba0da-260">이의 처리를 전도하고 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-260">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="ba0da-261">모든 부서(직원)</span><span class="sxs-lookup"><span data-stu-id="ba0da-261">Any department (staff)</span></span> |
| <span data-ttu-id="ba0da-262">테넌트 관리자</span><span class="sxs-lookup"><span data-stu-id="ba0da-262">Tenant administrator</span></span> | <span data-ttu-id="ba0da-263">테넌트 수준 설정 구성</span><span class="sxs-lookup"><span data-stu-id="ba0da-263">Configure tenant-level settings</span></span> | <span data-ttu-id="ba0da-264">IT 부서</span><span class="sxs-lookup"><span data-stu-id="ba0da-264">IT department</span></span>|
| <span data-ttu-id="ba0da-265">Power Platform 관리자</span><span class="sxs-lookup"><span data-stu-id="ba0da-265">Power Platform administrator</span></span>| <span data-ttu-id="ba0da-266">일반 데이터 서비스 환경 구성</span><span class="sxs-lookup"><span data-stu-id="ba0da-266">Configure common data services environment</span></span> | <span data-ttu-id="ba0da-267">IT 부서</span><span class="sxs-lookup"><span data-stu-id="ba0da-267">IT department</span></span>|

> [!Note]
> <span data-ttu-id="ba0da-268">이러한 각 역할을 롤아웃 전체에서 이행하는 것이 까다로우면 식별된 솔루션을 시작하는 데 이러한 역할이 모두 필요하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-268">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="ba0da-269">준비 검사 목록</span><span class="sxs-lookup"><span data-stu-id="ba0da-269">Readiness checklist</span></span>

<span data-ttu-id="ba0da-270">SharePoint Syntex 구현을 준비하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-270">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![콘텐츠 이해를 위한 준비](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="ba0da-272">종료 상태 계획</span><span class="sxs-lookup"><span data-stu-id="ba0da-272">Plan the end state</span></span>
    - <span data-ttu-id="ba0da-273">문서 이해 모델은 끝이 아니라 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-273">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="ba0da-274">추출된 메타데이터의 값을 다음을 사용하여 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-274">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="ba0da-275">검색</span><span class="sxs-lookup"><span data-stu-id="ba0da-275">Search</span></span>
      - <span data-ttu-id="ba0da-276">필터링 및 보기 서식</span><span class="sxs-lookup"><span data-stu-id="ba0da-276">Filtering and view formatting</span></span>
      - <span data-ttu-id="ba0da-277">규정 준수</span><span class="sxs-lookup"><span data-stu-id="ba0da-277">Compliance</span></span>
      - <span data-ttu-id="ba0da-278">자동화</span><span class="sxs-lookup"><span data-stu-id="ba0da-278">Automation</span></span>
2. <span data-ttu-id="ba0da-279">식별</span><span class="sxs-lookup"><span data-stu-id="ba0da-279">Identify</span></span>
    - <span data-ttu-id="ba0da-280">기존 정보 아키텍처 및 콘텐츠 관리 기능 사용을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-280">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="ba0da-281">기존 콘텐츠 형식이 모델에 좋은 후보인가요?</span><span class="sxs-lookup"><span data-stu-id="ba0da-281">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="ba0da-282">메타데이터를 통해 개선할 기존 프로세스는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="ba0da-282">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="ba0da-283">Design</span><span class="sxs-lookup"><span data-stu-id="ba0da-283">Design</span></span>
    - <span data-ttu-id="ba0da-284">정보 아키텍처, 관리되는 메타데이터 및 콘텐츠 형식에 대한 접근 방식 디자인</span><span class="sxs-lookup"><span data-stu-id="ba0da-284">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="ba0da-285">정의, 만들기, 관리 프로세스를 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-285">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="ba0da-286">조직 참여</span><span class="sxs-lookup"><span data-stu-id="ba0da-286">Engage your organization</span></span>

1. <span data-ttu-id="ba0da-287">지분 소유자를 식별하고, 시나리오를 확인하고, 프로젝트 계획을 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-287">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="ba0da-288">설정을 구성하고 라이선스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-288">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="ba0da-289">인식과 교육 시작 - 챔피언을 모집합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-289">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="ba0da-290">단계로 롤아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-290">Roll out in stages.</span></span>  
1. <span data-ttu-id="ba0da-291">피드백을 수집하고 이르게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-291">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="ba0da-292">사용량이 증가함에 따라 필요한 경우 모든 AI 작성기 크레딧에 대한 계획이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0da-292">As usage grows plan for any AI Builder credits as needed.</span></span>
