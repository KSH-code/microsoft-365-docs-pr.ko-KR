---
title: 'Microsoft SharePoint Syntex 채택: 시작'
description: 비즈니스 문제를 해결 하는 데 도움이 되도록 조직에서 SharePoint Syntex를 사용 하 고 구현 하는 방법을 알아봅니다.
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
ms.openlocfilehash: db54ff053dcb1c9c1c608608ab1a37da8090cdb3
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087514"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="07ceb-103">Microsoft SharePoint Syntex 채택: 시작</span><span class="sxs-lookup"><span data-stu-id="07ceb-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="07ceb-104">SharePoint Syntex에서 사용할 수 있는 지능형 콘텐츠 서비스는 다음과 같은 세 가지 부분으로 생각 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="07ceb-105">**콘텐츠 이해:** 콘텐츠의 정보를 분류 및 추출 하 여 기술 자료 검색 및 다시 사용을 위한 메타 데이터를 자동으로 적용 하는 코드 없는 AI 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="07ceb-106">자세한 내용은 [콘텐츠 이해](document-understanding-overview.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="07ceb-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="07ceb-107">**콘텐츠 처리:** 파워 자동화를 사용 하 여 콘텐츠 캡처, 수집 및 분류를 자동화 하 고 콘텐츠 중심 프로세스를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-107">**Content processing:** Automate capture, ingestion and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="07ceb-108">[콘텐츠 처리](form-processing-overview.md)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="07ceb-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="07ceb-109">**콘텐츠 준수:** 콘텐츠를 제어 및 관리 하 여 Microsoft 정보 보호와의 통합을 통해 보안 및 관리 효율성을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="07ceb-110">새 인공 지능 서비스와 기능을 사용 하 여 SharePoint Syntex을 사용 하 여 콘텐츠 관리 흐름에 직접 콘텐츠와 분류 앱을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex:</span></span>

|<span data-ttu-id="07ceb-111">수동 입력</span><span class="sxs-lookup"><span data-stu-id="07ceb-111">Manual entry</span></span>| <span data-ttu-id="07ceb-112">양식 처리</span><span class="sxs-lookup"><span data-stu-id="07ceb-112">Form processing</span></span> | <span data-ttu-id="07ceb-113">문서 이해</span><span class="sxs-lookup"><span data-stu-id="07ceb-113">Document understanding</span></span> |
|:-------|:--------|:--------|
| <span data-ttu-id="07ceb-114">모든 콘텐츠에 대 한 데이터 입력 및 노동 집약적</span><span class="sxs-lookup"><span data-stu-id="07ceb-114">Data entry and labor-intensive on any content</span></span> | <span data-ttu-id="07ceb-115">디지털 콘텐츠 처리-사진, 스캔, 영수증, 명함, 비디오에서 OCR & 텍스트</span><span class="sxs-lookup"><span data-stu-id="07ceb-115">Process digital content - photos, scans, receipts, business cards, videos with OCR & text</span></span> |  <span data-ttu-id="07ceb-116">계약, 이력서 및 기타 구조화 된 문서에서 콘텐츠 형식 및 메타 데이터 캡처</span><span class="sxs-lookup"><span data-stu-id="07ceb-116">Capture content types and  metadata from contracts, resumes, and other structured documents</span></span> |
| <span data-ttu-id="07ceb-117">들은</span><span class="sxs-lookup"><span data-stu-id="07ceb-117">Interactive</span></span>   | <span data-ttu-id="07ceb-118">미리 작성 된 자동화 된</span><span class="sxs-lookup"><span data-stu-id="07ceb-118">Pre-built, automated</span></span>   | <span data-ttu-id="07ceb-119">사용자 지정, 보조</span><span class="sxs-lookup"><span data-stu-id="07ceb-119">Custom, assisted</span></span>   | <span data-ttu-id="07ceb-120">사용자 지정, 준수</span><span class="sxs-lookup"><span data-stu-id="07ceb-120">Custom, compliant</span></span> |
| <span data-ttu-id="07ceb-121">작업을 수행 하는 사용자</span><span class="sxs-lookup"><span data-stu-id="07ceb-121">People doing the work</span></span> | <span data-ttu-id="07ceb-122">주제별 전문가 (SMEs)의 배울 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-122">Taught by your subject matter experts (SMEs).</span></span> <span data-ttu-id="07ceb-123">계약, 다시 시작, 기타 구조화 되지 않은 문서에서 콘텐츠 형식 및 메타 데이터를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-123">Capture content types and  metadata from contracts, resumes, other unstructured documents.</span></span> | <span data-ttu-id="07ceb-124">SMEs은 덜 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-124">SMEs are less involved.</span></span> <span data-ttu-id="07ceb-125">구매 주문, 응용 프로그램, 기타 반구조적 및 구조화 된 문서</span><span class="sxs-lookup"><span data-stu-id="07ceb-125">from purchase orders, applications, other semi structured and structured documents</span></span> |

<span data-ttu-id="07ceb-126">다음 표에서는 SharePoint Syntex을 사용할 때 얻을 수 있는 결과에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-126">The following table explains what you get when you use SharePoint Syntex:</span></span>

| <span data-ttu-id="07ceb-127">양식 처리</span><span class="sxs-lookup"><span data-stu-id="07ceb-127">Form processing</span></span> | <span data-ttu-id="07ceb-128">문서 이해</span><span class="sxs-lookup"><span data-stu-id="07ceb-128">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="07ceb-129">APAC, 오스트레일리아, 캐나다, EU, JP, 라틴 아메리카, 영국, US에서 사용 가능</span><span class="sxs-lookup"><span data-stu-id="07ceb-129">Available in APAC, Australia, Canada, EU, JP, LATAM, UK, US</span></span> | <span data-ttu-id="07ceb-130">모든 지역에서 사용 가능</span><span class="sxs-lookup"><span data-stu-id="07ceb-130">Available in all regions</span></span> |
| <span data-ttu-id="07ceb-131">AI Builder 제작진-1M 제작진 = 2000 페이지를 사용 합니다. 소비량은 약 2000 송장 = 2 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-131">Uses AI Builder credits - 1M credits = 2000 pages; Consumption is about 2000 invoices=2 units.</span></span> <span data-ttu-id="07ceb-132">전원 자동화가 필요 하며 더 필요한 경우 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-132">Power Automate is required - if you need more you can add it.</span></span> <span data-ttu-id="07ceb-133">1M에 게 할당 된 라이선스 300 개</span><span class="sxs-lookup"><span data-stu-id="07ceb-133">1M credits allocated for 300+ licenses purchased.</span></span> <span data-ttu-id="07ceb-134">또한 제작진을 별도로 구입할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-134">You can also purchase credits separately.</span></span> | <span data-ttu-id="07ceb-135">모델은 모든 라틴어 알파벳 언어에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-135">Models work on all latin alphabet languages.</span></span> <span data-ttu-id="07ceb-136">영어 (독일어, 스웨덴어, 프랑스어, 스페인어, 이탈리아어, 포르투갈어)가 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-136">In addition to English: German, Swedish, French, Spanish, Italian, and Portuguese.</span></span> |
| <span data-ttu-id="07ceb-137">기본 일반 데이터 서비스 환경에 대해 프로 비전 됨</span><span class="sxs-lookup"><span data-stu-id="07ceb-137">Provisioned against the default common data service environment</span></span>| <span data-ttu-id="07ceb-138">용량 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-138">Does not have capacity restrictions.</span></span> |

<span data-ttu-id="07ceb-139">콘텐츠를 이해 하는 방법은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-139">There are two different ways of understanding your content.</span></span> <span data-ttu-id="07ceb-140">사용 하는 모델 유형은 파일 형식과 사용 사례를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-140">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="07ceb-141">양식 처리</span><span class="sxs-lookup"><span data-stu-id="07ceb-141">Form processing</span></span> | <span data-ttu-id="07ceb-142">문서 이해</span><span class="sxs-lookup"><span data-stu-id="07ceb-142">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="07ceb-143">문서 라이브러리에서 만들어짐</span><span class="sxs-lookup"><span data-stu-id="07ceb-143">Created from document library</span></span> | <span data-ttu-id="07ceb-144">콘텐츠 센터에서 만들어지고 SharePoint Syntex의 일부</span><span class="sxs-lookup"><span data-stu-id="07ceb-144">Created in the content center, part of SharePoint Syntex</span></span> |
| <span data-ttu-id="07ceb-145">AI builder에서 생성 되는 모델</span><span class="sxs-lookup"><span data-stu-id="07ceb-145">Model created in AI builder</span></span> | <span data-ttu-id="07ceb-146">네이티브 인터페이스에서 만든 모델</span><span class="sxs-lookup"><span data-stu-id="07ceb-146">Model created in native interface</span></span> |
| <span data-ttu-id="07ceb-147">반구조적 파일 형식에 사용 됨</span><span class="sxs-lookup"><span data-stu-id="07ceb-147">Used for semi-structured file formats</span></span> | <span data-ttu-id="07ceb-148">구조화 되지 않은 파일 형식에 사용 됨</span><span class="sxs-lookup"><span data-stu-id="07ceb-148">Used for unstructured file formats</span></span> |
| <span data-ttu-id="07ceb-149">설정 가능한 분류자</span><span class="sxs-lookup"><span data-stu-id="07ceb-149">Settable classifier</span></span> | <span data-ttu-id="07ceb-150">선택적 추출기가 포함 된 Trainable 분류자</span><span class="sxs-lookup"><span data-stu-id="07ceb-150">Trainable classifier with optional extractors</span></span> |
| <span data-ttu-id="07ceb-151">단일 라이브러리로 제한</span><span class="sxs-lookup"><span data-stu-id="07ceb-151">Restricted to a single library</span></span> | <span data-ttu-id="07ceb-152">여러 라이브러리에 적용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="07ceb-152">Can be applied to multiple libraries</span></span> |
| <span data-ttu-id="07ceb-153">PDF, JPG, PNG 형식, 총 50 MB/500 페이지를 교육 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-153">Train on PDF, JPG, PNG format, total 50 MB/500 pp</span></span> | <span data-ttu-id="07ceb-154">부정적 예를 포함 하 여 5-10 PDF, Office 또는 전자 메일 파일에 대해 교육 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-154">Train on 5-10 PDF, Office, or email files, including negative examples</span></span> |

<span data-ttu-id="07ceb-155">SharePoint Syntex는 다음과 같은 Microsoft 365 규정 준수 기능을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-155">SharePoint Syntex integrates with Microsoft 365 compliance features like:</span></span>

- <span data-ttu-id="07ceb-156">문서 보존 기간 또는 외부 이벤트를 기반으로 하는 레코드 정책을 정의 하는 보존 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-156">Retention labels that define records policy based on document age or external events.</span></span>
- <span data-ttu-id="07ceb-157">민감도 레이블-DLP, 암호화, 공유 및 조건부 액세스 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-157">Sensitivity labels that set DLP, encryption, sharing, and conditional access policies.</span></span>

<span data-ttu-id="07ceb-158">사용자는 레이블을 적용 하거나 SharePoint Syntex AI 모델에서 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-158">Users can apply labels, or they can be applied automatically by SharePoint Syntex AI models.</span></span> <span data-ttu-id="07ceb-159">분석 및 파일 계획은 레이블 사용 및 정책에 대 한 확장 된 관리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-159">Analytics and file plans provide scaled management of label usage and policies.</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="07ceb-160">최적화할 파일럿 비즈니스 시나리오 식별</span><span class="sxs-lookup"><span data-stu-id="07ceb-160">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="07ceb-161">조직에서 SharePoint Syntex 사용을 준비 하려면 먼저 it가 도움이 되는 시나리오를 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-161">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="07ceb-162">필요한 모델을 결정 하는 이유와 모델이 적용 되는 위치를 기반으로 하 여 조직 구조를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-162">The why helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="07ceb-163">다음은 문서를 이해 하는 것이 조직에 도움이 될 수 있는 몇 가지 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-163">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="07ceb-164">콘텐츠 처리: 프로세스 계약, 작업 문서 및 기타 양식 등의 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-164">Content processing: Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="07ceb-165">양식을 흡입구로 만들고 필드를 이해 하 고 매핑한 다음 양식을 실행 하 여 데이터를 자동으로 수집 하는 모델을 학습 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-165">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="07ceb-166">자세한 내용은 [양식 처리 개요](form-processing-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07ceb-166">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="07ceb-167">송장 분석: 청구서에서 관련 세부 정보를 추출 하 여 정책에 대 한 준수 여부 또는 적절 하 게 처리 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-167">Invoice analysis: Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="07ceb-168">SharePoint Syntex가 조직에 도움을 주는 방식에 대해 생각해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="07ceb-168">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="07ceb-169">비즈니스 프로세스 자동화</span><span class="sxs-lookup"><span data-stu-id="07ceb-169">Automate business processes</span></span>
- <span data-ttu-id="07ceb-170">검색 정확도 향상</span><span class="sxs-lookup"><span data-stu-id="07ceb-170">Improve search accuracy</span></span>
- <span data-ttu-id="07ceb-171">규정 준수 위험 관리</span><span class="sxs-lookup"><span data-stu-id="07ceb-171">Manage compliance risk</span></span>

### <a name="form-processing-scenario-example"></a><span data-ttu-id="07ceb-172">양식 처리 시나리오 예</span><span class="sxs-lookup"><span data-stu-id="07ceb-172">Form processing scenario example</span></span>

<span data-ttu-id="07ceb-173">예를 들어 SharePoint Syntex 및 Power 자동화 기능을 사용 하 여 송장을 추적 하 고 모니터링 하는 프로세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-173">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="07ceb-174">송장 문서를 저장할 라이브러리를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-174">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="07ceb-175">모델을 학습 하 여 문서의 필드를 인식 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-175">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="07ceb-176">목록으로 추적 하려는 필드의 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-176">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="07ceb-177">다음과 같은 특정 이벤트를 알리도록 흐름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-177">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="07ceb-178">새 송장이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-178">A new invoice is added.</span></span>
    - <span data-ttu-id="07ceb-179">송장 기한이 만료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-179">An invoice is past its due date.</span></span>
    - <span data-ttu-id="07ceb-180">송장에서 자동 승인 금액 보다 큰 경우</span><span class="sxs-lookup"><span data-stu-id="07ceb-180">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![SharePoint Syntex 및 Power 자동화를 사용 하 여 송장을 추적 및 모니터링](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="07ceb-182">이 시나리오를 자동화 하는 경우 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-182">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="07ceb-183">수동으로 작업을 수행 하는 대신 송장에서 데이터를 자동으로 추출 하 여 시간과 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-183">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="07ceb-184">잠재적 오류를 줄이고 송장을 사용 하 여 송장에 대 한 작업을 수행 하 고 문제를 사용자에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-184">Reduce potential errors and ensure better compliance by using workflows to act on the invoices and notify you of any issues.</span></span>

### <a name="document-understanding-scenario-example"></a><span data-ttu-id="07ceb-185">시나리오 이해 문서 예</span><span class="sxs-lookup"><span data-stu-id="07ceb-185">Document understanding scenario example</span></span>

<span data-ttu-id="07ceb-186">또 다른 예로 회사의 다른 회사나 개인이 가진 계약을 식별 하는 프로세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-186">As another example, you can set up a process to identify contracts that your company has with other companies or individuals.</span></span> <span data-ttu-id="07ceb-187">이러한 계약에서 클라이언트 이름, 수수료, 날짜 또는 기타 중요 한 정보와 같은 주요 정보를 추출 하는 모델을 설정 하 고 라이브러리에 빠르게 확인할 수 있는 필드로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-187">You can set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add that to the library as fields you can quickly view.</span></span> <span data-ttu-id="07ceb-188">그리고 문서 라이브러리에 보존 레이블을 적용 하 여 비즈니스 규정을 준수 하기 위해 특정 기간 이전에 계약을 삭제할 수 없도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-188">And you can apply a retention label on the document library to ensure that contracts cannot be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="07ceb-189">콘텐츠 센터에서 시작 하 고 계약에 대 한 새 문서 이해 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-189">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="07ceb-190">긍정적인 및 부정적 예제에 대 한 샘플 문서를 업로드 한 다음 교육을 실행 하 여 계약 문서를 식별 하 고 결과를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-190">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="07ceb-191">추출기를 교육 하 여 클라이언트 이름, 비용, 날짜 등 계약의 필드를 식별 한 다음 추출기를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-191">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="07ceb-192">모델이 완료 되 면 계약을 업로드할 수 있는 라이브러리에 모델을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-192">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="07ceb-193">조직에서 계약에 대해 요구 하는 기간 동안 계약이 라이브러리에 보존 되도록 날짜 필드에 보존 레이블을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-193">Apply a retention label to the date field, so that contracts are retained in the library for the length of time your organization requires for contracts.</span></span>

![SharePoint Syntex 및 보존 레이블로 계약 추적 및 모니터링](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="07ceb-195">이 시나리오를 자동화 하는 경우 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-195">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="07ceb-196">수동으로 작업을 수행 하는 대신 계약에서 데이터를 자동으로 추출 하 여 시간과 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-196">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="07ceb-197">보존 레이블을 사용 하 여 계약이 적절 하 게 보존 되도록 하 여 규정 준수를 개선 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-197">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="tips-for-identifying-scenarios"></a><span data-ttu-id="07ceb-198">시나리오 식별 팁</span><span class="sxs-lookup"><span data-stu-id="07ceb-198">Tips for identifying scenarios</span></span>

<span data-ttu-id="07ceb-199">고려해 야 하는 비즈니스 시나리오를 고려할 때는 다음 사항을 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="07ceb-199">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="07ceb-200">실제 문제가 해결 되었습니까?</span><span class="sxs-lookup"><span data-stu-id="07ceb-200">Does it solve a real problem?</span></span>
- <span data-ttu-id="07ceb-201">광범위 하 게 사용 되거나 광범위 한 영향을 줍니까?</span><span class="sxs-lookup"><span data-stu-id="07ceb-201">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="07ceb-202">해당 기능을 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="07ceb-202">Is it obtainable?</span></span>
- <span data-ttu-id="07ceb-203">성공을 측정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="07ceb-203">Can you measure success?</span></span>

<span data-ttu-id="07ceb-204">영향 및 구현 용이성에 따라 시나리오 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="07ceb-204">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="07ceb-205">초기 포커스 영역이 더 높은 영향을 받을 수 있도록 쉽게 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-205">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="07ceb-206">구현 하기 어려운 낮은 영향 시나리오의 우선 순위를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-206">De-prioritize lower impact scenarios that are hard to implement.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="07ceb-207">역할 & 책임 식별</span><span class="sxs-lookup"><span data-stu-id="07ceb-207">Identify roles & responsibilities</span></span>

<span data-ttu-id="07ceb-208">조직의 누가 모델을 빌드하고 관리할 지 결정</span><span class="sxs-lookup"><span data-stu-id="07ceb-208">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="07ceb-209">다음과 같은 역할이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-209">The following roles might be involved:</span></span>

| <span data-ttu-id="07ceb-210">SharePoint/기술 자료 관리자</span><span class="sxs-lookup"><span data-stu-id="07ceb-210">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="07ceb-211">전원 플랫폼 관리자</span><span class="sxs-lookup"><span data-stu-id="07ceb-211">Power Platform admin</span></span> | <span data-ttu-id="07ceb-212">기술 자료 관리자</span><span class="sxs-lookup"><span data-stu-id="07ceb-212">Knowledge manager</span></span> | <span data-ttu-id="07ceb-213">모델 소유자</span><span class="sxs-lookup"><span data-stu-id="07ceb-213">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="07ceb-214">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="07ceb-214">AAD role</span></span>| <span data-ttu-id="07ceb-215">역할 추가</span><span class="sxs-lookup"><span data-stu-id="07ceb-215">ADD role</span></span> | <span data-ttu-id="07ceb-216">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="07ceb-216">AAD role</span></span> | <span data-ttu-id="07ceb-217">챔피언</span><span class="sxs-lookup"><span data-stu-id="07ceb-217">Champions</span></span> |
| <span data-ttu-id="07ceb-218">양식 처리 구성</span><span class="sxs-lookup"><span data-stu-id="07ceb-218">Configure form processing</span></span> | <span data-ttu-id="07ceb-219">양식 처리를 위해 일반 데이터 서비스 환경 구성</span><span class="sxs-lookup"><span data-stu-id="07ceb-219">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="07ceb-220">사용 사례 수집</span><span class="sxs-lookup"><span data-stu-id="07ceb-220">Gather use cases</span></span> | <span data-ttu-id="07ceb-221">비즈니스 사용 사례 수집</span><span class="sxs-lookup"><span data-stu-id="07ceb-221">Gather business use cases</span></span> |
| <span data-ttu-id="07ceb-222">콘텐츠 센터 및 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="07ceb-222">Manage content centers and permissions</span></span>| <span data-ttu-id="07ceb-223">AIB 제작진 구입 및 할당</span><span class="sxs-lookup"><span data-stu-id="07ceb-223">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="07ceb-224">모범 사례 설정 및 검토 모델 분석</span><span class="sxs-lookup"><span data-stu-id="07ceb-224">Establish best practices and review model analytics</span></span> | <span data-ttu-id="07ceb-225">모델 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="07ceb-225">Create and apply models</span></span> |

<span data-ttu-id="07ceb-226">지식 관리자, 비즈니스 프로세스 소유자 및 콘텐츠 모델 소유자 조직에 샘플 모델 및 챔피언 채택을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-226">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="07ceb-227">관련 된 다른 사용자: 준수 관리자, 분류 관리자</span><span class="sxs-lookup"><span data-stu-id="07ceb-227">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="07ceb-228">모델을 빌드하고 적용할 위치</span><span class="sxs-lookup"><span data-stu-id="07ceb-228">Where will they build and apply the models?</span></span> <span data-ttu-id="07ceb-229">향상 시킬 수 있는 기존 프로세스나 리포지토리가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="07ceb-229">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="07ceb-230">양식 처리: 양식 처리 작업을 가져올 사이트를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-230">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="07ceb-231">문서 이해: 각 비즈니스 영역에 대해 콘텐츠 센터를 여러 개 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-231">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="07ceb-232">전략적 포지셔닝</span><span class="sxs-lookup"><span data-stu-id="07ceb-232">Strategic positioning</span></span>

<span data-ttu-id="07ceb-233">관련자와 협력 하 여 SharePoint Syntex 사용 전략에 부합 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-233">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="07ceb-234">이 위치 지정에 도움이 되는 다음 리소스를 조사 하 고 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-234">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="07ceb-235">비즈니스 결과:</span><span class="sxs-lookup"><span data-stu-id="07ceb-235">Business outcomes:</span></span>
  - <span data-ttu-id="07ceb-236">잠재적 회계 결과</span><span class="sxs-lookup"><span data-stu-id="07ceb-236">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="07ceb-237">잠재적인 민첩성 결과</span><span class="sxs-lookup"><span data-stu-id="07ceb-237">Potential agility outcomes</span></span>
  - <span data-ttu-id="07ceb-238">비즈니스 결과 서식 파일</span><span class="sxs-lookup"><span data-stu-id="07ceb-238">Business outcome template</span></span>
- <span data-ttu-id="07ceb-239">관련자/Exec 스폰서 구매/맞춤</span><span class="sxs-lookup"><span data-stu-id="07ceb-239">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="07ceb-240">비즈니스 사례 데크</span><span class="sxs-lookup"><span data-stu-id="07ceb-240">Business case decks</span></span>
  - <span data-ttu-id="07ceb-241">재무 모델</span><span class="sxs-lookup"><span data-stu-id="07ceb-241">Financial models</span></span>
  - <span data-ttu-id="07ceb-242">회사 준비-문화권</span><span class="sxs-lookup"><span data-stu-id="07ceb-242">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="07ceb-243">관련자 파악</span><span class="sxs-lookup"><span data-stu-id="07ceb-243">Identify stakeholders</span></span>

<span data-ttu-id="07ceb-244">프로젝트에 대 한 관련자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-244">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="07ceb-245">역할</span><span class="sxs-lookup"><span data-stu-id="07ceb-245">Role</span></span> |<span data-ttu-id="07ceb-246">업무</span><span class="sxs-lookup"><span data-stu-id="07ceb-246">Responsibilities</span></span> |<span data-ttu-id="07ceb-247">부서</span><span class="sxs-lookup"><span data-stu-id="07ceb-247">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="07ceb-248">경영 간부</span><span class="sxs-lookup"><span data-stu-id="07ceb-248">Executive sponsor(s)</span></span>   | <span data-ttu-id="07ceb-249">회사에 높은 수준의 비전 및 가치 전달</span><span class="sxs-lookup"><span data-stu-id="07ceb-249">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="07ceb-250">임원 리더십</span><span class="sxs-lookup"><span data-stu-id="07ceb-250">Executive leadership</span></span>   |
| <span data-ttu-id="07ceb-251">프로젝트 책임자</span><span class="sxs-lookup"><span data-stu-id="07ceb-251">Project lead(s)</span></span> | <span data-ttu-id="07ceb-252">전체 시작 실행 및 롤아웃 프로세스 감독</span><span class="sxs-lookup"><span data-stu-id="07ceb-252">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="07ceb-253">프로젝트 관리</span><span class="sxs-lookup"><span data-stu-id="07ceb-253">Project management</span></span> |
| <span data-ttu-id="07ceb-254">지식 관리자</span><span class="sxs-lookup"><span data-stu-id="07ceb-254">Knowledge administrators</span></span>| <span data-ttu-id="07ceb-255">콘텐츠 센터 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="07ceb-255">Create and manage the content centers</span></span> | <span data-ttu-id="07ceb-256">IT 또는 기타 부서</span><span class="sxs-lookup"><span data-stu-id="07ceb-256">IT or other department</span></span>|
| <span data-ttu-id="07ceb-257">콘텐츠 관리자 및 모델 소유자</span><span class="sxs-lookup"><span data-stu-id="07ceb-257">Content managers and model owners</span></span>| <span data-ttu-id="07ceb-258">사용 사례 수집 및 모델 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="07ceb-258">Gather use cases and create and apply models</span></span> | <span data-ttu-id="07ceb-259">모든 부서</span><span class="sxs-lookup"><span data-stu-id="07ceb-259">Any department</span></span>|
| <span data-ttu-id="07ceb-260">챔피언</span><span class="sxs-lookup"><span data-stu-id="07ceb-260">Champions</span></span> | <span data-ttu-id="07ceb-261">Objection 처리 evangelize 및 관리 지원</span><span class="sxs-lookup"><span data-stu-id="07ceb-261">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="07ceb-262">모든 부서 (직원)</span><span class="sxs-lookup"><span data-stu-id="07ceb-262">Any department (staff)</span></span> |
| <span data-ttu-id="07ceb-263">테넌트 관리자</span><span class="sxs-lookup"><span data-stu-id="07ceb-263">Tenant administrator</span></span> | <span data-ttu-id="07ceb-264">테 넌 트 수준 설정 구성</span><span class="sxs-lookup"><span data-stu-id="07ceb-264">Configure tenant-level settings</span></span> | <span data-ttu-id="07ceb-265">IT 부서</span><span class="sxs-lookup"><span data-stu-id="07ceb-265">IT department</span></span>|
| <span data-ttu-id="07ceb-266">전원 플랫폼 관리자</span><span class="sxs-lookup"><span data-stu-id="07ceb-266">Power Platform administrator</span></span>| <span data-ttu-id="07ceb-267">Common data services 환경 구성</span><span class="sxs-lookup"><span data-stu-id="07ceb-267">Configure common data services environment</span></span> | <span data-ttu-id="07ceb-268">IT 부서</span><span class="sxs-lookup"><span data-stu-id="07ceb-268">IT department</span></span>|

> [!Note]
> <span data-ttu-id="07ceb-269">롤아웃 전체에서 이러한 각 역할을 수행 하는 것이 좋지만 확인 된 솔루션을 시작 하기 위해 이러한 각 역할이 모두 필요 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-269">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="07ceb-270">준비 상태 검사 목록</span><span class="sxs-lookup"><span data-stu-id="07ceb-270">Readiness checklist</span></span>

<span data-ttu-id="07ceb-271">SharePoint Syntex 구현을 준비 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-271">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![콘텐츠 이해 준비](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="07ceb-273">최종 상태 계획</span><span class="sxs-lookup"><span data-stu-id="07ceb-273">Plan the end state</span></span>
    - <span data-ttu-id="07ceb-274">문서 이해 모델은 종료를 의미 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-274">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="07ceb-275">압축을 푼 메타 데이터의 값을 harnessing에 대 한 계획:</span><span class="sxs-lookup"><span data-stu-id="07ceb-275">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="07ceb-276">검색</span><span class="sxs-lookup"><span data-stu-id="07ceb-276">Search</span></span>
      - <span data-ttu-id="07ceb-277">서식 필터링 및 보기</span><span class="sxs-lookup"><span data-stu-id="07ceb-277">Filtering and view formatting</span></span>
      - <span data-ttu-id="07ceb-278">규정 준수</span><span class="sxs-lookup"><span data-stu-id="07ceb-278">Compliance</span></span>
      - <span data-ttu-id="07ceb-279">자동화</span><span class="sxs-lookup"><span data-stu-id="07ceb-279">Automation</span></span>
2. <span data-ttu-id="07ceb-280">신원을</span><span class="sxs-lookup"><span data-stu-id="07ceb-280">Identify</span></span>
    - <span data-ttu-id="07ceb-281">기존 정보 아키텍처 및 콘텐츠 관리 기능 사용을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-281">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="07ceb-282">기존 콘텐츠 형식이 모델에 적합 한 후보 입니까?</span><span class="sxs-lookup"><span data-stu-id="07ceb-282">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="07ceb-283">메타 데이터로 향상 된 기존 프로세스는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="07ceb-283">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="07ceb-284">Design</span><span class="sxs-lookup"><span data-stu-id="07ceb-284">Design</span></span>
    - <span data-ttu-id="07ceb-285">정보 아키텍처, 관리 되는 메타 데이터 및 콘텐츠 형식에 대 한 접근 방식 디자인</span><span class="sxs-lookup"><span data-stu-id="07ceb-285">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="07ceb-286">정의, 생성, 관리에 대 한 프로세스를 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-286">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="07ceb-287">조직에 참여</span><span class="sxs-lookup"><span data-stu-id="07ceb-287">Engage your organization</span></span>

1. <span data-ttu-id="07ceb-288">Stake 소유자 확인, 시나리오 확인 및 프로젝트 계획 개발</span><span class="sxs-lookup"><span data-stu-id="07ceb-288">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="07ceb-289">설정을 구성 하 고 라이선스를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-289">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="07ceb-290">인식 및 교육 시작-Champions.</span><span class="sxs-lookup"><span data-stu-id="07ceb-290">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="07ceb-291">단계를 롤아웃 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-291">Roll out in stages.</span></span>  
1. <span data-ttu-id="07ceb-292">의견을 수집 하 고 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-292">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="07ceb-293">사용량은 필요한 경우 모든 AI Builder 제작진을 계획 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07ceb-293">As usage grows plan for any AI Builder credits as needed.</span></span>
