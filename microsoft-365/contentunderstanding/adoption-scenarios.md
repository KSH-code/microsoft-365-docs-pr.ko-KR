---
title: Microsoft SharePoint 시나리오 및 사용 사례
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: laurieellis
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: 조직에서 Syntex를 사용하는 SharePoint 시나리오를 찾아보겠습니다.
ms.openlocfilehash: b28239a304c8fab209436c12e6cdbffe160b7981
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697068"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a><span data-ttu-id="f6079-103">Microsoft SharePoint 시나리오 및 사용 사례</span><span class="sxs-lookup"><span data-stu-id="f6079-103">Scenarios and use cases for Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="f6079-104">다음 예제 시나리오를 사용하여 조직에서 Syntex를 사용하는 방법에 대한 SharePoint 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-104">Use the following example scenarios to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

- [<span data-ttu-id="f6079-105">시나리오: 양식 처리를 사용하여 송장에서 데이터 추적</span><span class="sxs-lookup"><span data-stu-id="f6079-105">Scenario: Track data from invoices with form processing</span></span>](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [<span data-ttu-id="f6079-106">시나리오: 문서 이해를 통해 계약에서 정보 추적</span><span class="sxs-lookup"><span data-stu-id="f6079-106">Scenario: Track information from contracts with document understanding</span></span>](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [<span data-ttu-id="f6079-107">시나리오: 레코드 관리, 문서 거버넌스 및 Syntex를 기반으로 하는 규정 준수 프로세스로 SharePoint 방지</span><span class="sxs-lookup"><span data-stu-id="f6079-107">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [<span data-ttu-id="f6079-108">시나리오: 이전에는 이 문서에 없는 문서에서 정보 캡처</span><span class="sxs-lookup"><span data-stu-id="f6079-108">Scenario: Capture information from previously inaccessible documents</span></span>](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [<span data-ttu-id="f6079-109">시나리오: 데이터 처리를 개선하여 인사이트 및 분석 제공</span><span class="sxs-lookup"><span data-stu-id="f6079-109">Scenario: Improve data processing to provide insights and analytics</span></span>](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [<span data-ttu-id="f6079-110">시나리오: 주문 처리 자동화</span><span class="sxs-lookup"><span data-stu-id="f6079-110">Scenario: Automate order processing</span></span>](adoption-scenarios.md#scenario-automate-order-processing)
- [<span data-ttu-id="f6079-111">시나리오: Visa 갱신 프로세스 간소화</span><span class="sxs-lookup"><span data-stu-id="f6079-111">Scenario: Simplify visa renewal process</span></span>](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a><span data-ttu-id="f6079-112">시나리오: 양식 처리를 사용하여 송장에서 데이터 추적</span><span class="sxs-lookup"><span data-stu-id="f6079-112">Scenario: Track data from invoices with form processing</span></span>

<span data-ttu-id="f6079-113">예를 들어 송장 추적 및 모니터링을 위해 SharePoint 및 Power Automate 프로세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-113">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="f6079-114">송장 문서를 저장할 라이브러리를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-114">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="f6079-115">문서의 필드를 인식하는 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-115">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="f6079-116">추적할 필드를 목록으로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-116">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="f6079-117">흐름을 설정하여 다음을 통해 특정 이벤트를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-117">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="f6079-118">새 송장이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-118">A new invoice is added.</span></span>
    - <span data-ttu-id="f6079-119">송장 기한이 지난 경우</span><span class="sxs-lookup"><span data-stu-id="f6079-119">An invoice is past its due date.</span></span>
    - <span data-ttu-id="f6079-120">송장은 자동 승인 금액보다 큰 금액에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-120">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![Syntex 및 SharePoint 송장을 추적하고 Power Automate](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="f6079-122">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-122">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="f6079-123">송장에서 데이터를 수동으로 추출하는 대신 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-123">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="f6079-124">워크플로를 사용하여 송장을 확인하고 문제를 알려 잠재적인 오류를 줄이고 규정 준수를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-124">Reduce potential errors and ensure better compliance by using workflows to check invoices and notify you of any issues.</span></span>

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a><span data-ttu-id="f6079-125">시나리오: 문서 이해를 통해 계약에서 정보 추적</span><span class="sxs-lookup"><span data-stu-id="f6079-125">Scenario: Track information from contracts with document understanding</span></span>

<span data-ttu-id="f6079-126">또 다른 예로, 회사의 다른 회사 또는 개인과의 계약을 식별하는 프로세스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-126">As another example, you can set up a process to identify contracts your company has with other companies or individuals.</span></span> <span data-ttu-id="f6079-127">클라이언트 이름, 수수료, 날짜 또는 기타 중요한 정보와 같은 주요 정보를 해당 계약에서 추출하고 정보를 빠르게 볼 수 있는 필드로 라이브러리에 추가하는 모델을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="f6079-127">Set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add the information to the library as fields you can quickly view.</span></span> <span data-ttu-id="f6079-128">문서 라이브러리에 보존 레이블을 적용하여 비즈니스 규정을 적절하게 준수하기 위해 특정 기간 전에 계약을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-128">Apply a retention label on the document library to ensure that contracts can't be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="f6079-129">콘텐츠 센터에서 시작하여 계약에 대한 새 문서 이해 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-129">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="f6079-130">업로드 예제 문서를 확인한 다음 교육을 실행하여 계약 문서를 식별하고 결과를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-130">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="f6079-131">추출기에서 클라이언트 이름, 수수료 및 날짜와 같은 계약 필드를 식별하는 교육을 한 다음 추출기 테스트를 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-131">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="f6079-132">모델이 완료되면 계약을 업로드할 수 있는 라이브러리에 모델을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-132">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="f6079-133">날짜 필드에 보존 레이블을 적용하여 계약이 필요한 기간 동안 라이브러리에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-133">Apply a retention label to the date field, so that contracts are retained in the library for the required length of time.</span></span>

![Syntex 및 SharePoint 레이블과의 계약 추적 및 모니터링](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="f6079-135">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-135">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="f6079-136">수동으로 수행하지 않고 계약에서 데이터를 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-136">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="f6079-137">보존 레이블을 사용하여 계약이 적절하게 보존되도록 하여 규정 준수를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-137">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a><span data-ttu-id="f6079-138">시나리오: 레코드 관리, 문서 거버넌스 및 Syntex를 기반으로 하는 규정 준수 프로세스로 SharePoint 방지</span><span class="sxs-lookup"><span data-stu-id="f6079-138">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>

<span data-ttu-id="f6079-139">대부분의 회사에서 위험을 줄이는 것이 일반적인 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-139">Reducing risks is a common goal for most companies.</span></span> <span data-ttu-id="f6079-140">다음이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-140">You might need:</span></span>

- <span data-ttu-id="f6079-141">테넌트 전체에서 정보 거버넌스를 제공/적용하는 더 나은 방법</span><span class="sxs-lookup"><span data-stu-id="f6079-141">A better way to provide/enforce information governance across your tenant.</span></span>
- <span data-ttu-id="f6079-142">문서, 전자 메일 및 프로젝트의 '레코드'로 간주되는 기타 통신 형식의 분류 시스템을 개선하기 위해</span><span class="sxs-lookup"><span data-stu-id="f6079-142">To improve the system for classification of documents, emails and other forms of communication considered ‘records’ for projects.</span></span>
- <span data-ttu-id="f6079-143">회사 정책을 준수하기 위해 영수증, 계약 등 감사</span><span class="sxs-lookup"><span data-stu-id="f6079-143">To audit receipts, contracts, and so on, to ensure compliance with company policies.</span></span>
- <span data-ttu-id="f6079-144">프로젝트에 규정 준수에 필요한 모든 설명서가 프로젝트에 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-144">To ensure that projects have all the documentation required for compliance.</span></span>

<span data-ttu-id="f6079-145">더 나은 거버넌스가 필요한 문서 및 양식을 SharePoint 적절히 분류하고, 감사하고, 플래그를 지정하기 위해 Syntex를 준수하기 위한 일부 프로세스를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="f6079-145">Set up some processes for compliance with SharePoint Syntex to capture and appropriately classify, audit, and flag documents and forms that need better governance.</span></span> <span data-ttu-id="f6079-146">최종 사용자가 수동으로 태그를 SharePoint 대신 Syntex를 사용하여 콘텐츠를 자동 분류하거나 규정 준수 팀에서 거버넌스 규칙 및 보관을 수동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-146">You can rely on SharePoint Syntex to auto classify content rather than relying on end users to manually tag, or the compliance team to manually apply governance rules and archiving.</span></span> <span data-ttu-id="f6079-147">또한 간소화된 검색 환경을 사용하도록 설정하고, 데이터 볼륨을 관리하고, 레코드 관리 및 보존 정책을 적용하고, 규정 준수를 보장하고, 모범 사례 보관 및 삭제 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-147">And you can enable a simplified search experience, manage data volumes, apply records management and retention policies, ensure compliance, and best practice archiving and purging practices.</span></span>

<span data-ttu-id="f6079-148">이 시나리오를 자동화하면 다음의 안전을 느낄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-148">When you automate this scenario, you can feel secure that:</span></span>

- <span data-ttu-id="f6079-149">규정 준수를 준수하고 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-149">Compliance is upheld and risk is reduced.</span></span>
- <span data-ttu-id="f6079-150">세분화 및 레코드 관리는 일관되고 정확하게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-150">Taxonomy and records management is consistently and accurately applied.</span></span>
- <span data-ttu-id="f6079-151">콘텐츠 볼륨이 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-151">Content volumes are controlled.</span></span>
- <span data-ttu-id="f6079-152">직원은 올바른 컨텍스트에서 올바른 정보를 쉽게 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-152">Employees can easily discover the right information in the right context.</span></span>

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a><span data-ttu-id="f6079-153">시나리오: 이전에는 이 문서에 없는 문서에서 정보 캡처</span><span class="sxs-lookup"><span data-stu-id="f6079-153">Scenario: Capture information from previously inaccessible documents</span></span>

<span data-ttu-id="f6079-154">대부분의 조직에는 법률 문서, 정책, 계약, HR 문서 및 거버넌스 지침이 큰 저장소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-154">Most organizations have large repositories of legal documents, policies, contracts, HR documents, and governance guidelines.</span></span> <span data-ttu-id="f6079-155">프로젝트, 섹터, 테마, 사람, 지리적 영역 등의 중요한 정보를 추출하기 위해 이러한 데이터 저장소를 마이인드합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-155">Mine these data stores to extract valuable information such as: projects, sectors, themes, people, geographical areas, and so on.</span></span>

<span data-ttu-id="f6079-156">예를 들어 HR 감독은 이력서, HR 정책 및 기타 양식을 포함하여 모든 HR 문서에 빠르게 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-156">For example, an HR director needs to quickly access all HR documents – including resumes, HR policies, and other forms.</span></span> <span data-ttu-id="f6079-157">또한 문서를 수동으로 제거하지 않고도 이력서 및 기타 HR 관련 문서에서 필요한 정보를 빠르게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-157">And they want to quickly identify necessary information from resumes and other HR-related documents without manually sifting through the documents.</span></span> <span data-ttu-id="f6079-158">수천 개의 이력서, HR 정책 및 여러 사이트에 분산될 수 있는 기타 설명서를 수동으로 살펴보지 않고도 필요한 정보를 빠르게 찾을 수 있는 솔루션을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-158">They’re looking for a solution that allows them to quickly find the information they need without having to manually look through thousands of resumes, HR policies, and other documentation that may be spread across several sites.</span></span>

<span data-ttu-id="f6079-159">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-159">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="f6079-160">디지털 콘텐츠에서 지식의 잠금을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-160">Unlock knowledge from digital content.</span></span>
- <span data-ttu-id="f6079-161">HR 정책, 이력서, 판매 문서, 기술 청사진, 계정 계획 및 정보 추출을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-161">Classify HR policies, resumes, sales documents, technical blueprints, account plans and extract information.</span></span>
- <span data-ttu-id="f6079-162">원하는 올바른 정보나 문서를 빠르게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-162">Quickly find the correct information or document that you’re looking for.</span></span>
- <span data-ttu-id="f6079-163">최신 정보에 즉시 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-163">Get instant access to the latest information.</span></span>
- <span data-ttu-id="f6079-164">검색 시간을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-164">Reduce search times.</span></span>

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a><span data-ttu-id="f6079-165">시나리오: 데이터 처리를 개선하여 인사이트 및 분석 제공</span><span class="sxs-lookup"><span data-stu-id="f6079-165">Scenario: Improve data processing to provide insights and analytics</span></span>

<span data-ttu-id="f6079-166">예를 들어 제약 회사에서는 Syntex를 사용하여 FDA SharePoint 정보를 추출하여 리더의 질문에 답변할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-166">For example, a pharmaceutical company could use SharePoint Syntex to extract information from FDA documents to answer questions that their leaders have.</span></span> <span data-ttu-id="f6079-167">답변에 보다 쉽게 액세스할 수 있도록 하면 이러한 답변을 생성하는 데 필요한 시간을 줄이고 데이터의 가용성을 높이어 리더십 질문에 대한 보다 정확한 답변을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-167">Having the answers more easily accessible can reduce the time needed to produce these answers and increase the availability of data to generate more accurate answers to leadership questions.</span></span>

<span data-ttu-id="f6079-168">예를 들어 프로젝트 관리자는 리더십 팀의 제품 관련 질문에 대한 답변을 신속하게 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-168">For example, a project manager needs to quickly provide answers to product-related questions from my leadership team.</span></span> <span data-ttu-id="f6079-169">하나의 통합 대시보드에서 쿼리와 관련된 정보 및 메트릭을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-169">They need to find information and metrics related to queries in one consolidated dashboard.</span></span> <span data-ttu-id="f6079-170">제품 레이블, 제품 팜플릿 및 기타 자료에서 필요한 정보를 추출하고 리더십 팀에 다시 보고할 때 사용할 수 있는 통합 보고서를 생성하는 솔루션을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-170">They’re looking for a solution that extracts the information they need from product labels, product pamphlets, and other materials and generates a consolidated report that they can use when reporting back to their leadership team.</span></span>

<span data-ttu-id="f6079-171">이 시나리오를 자동화할 때 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-171">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="f6079-172">답변을 생성하는 데 필요한 시간을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-172">Reduce time to produce answers.</span></span>
- <span data-ttu-id="f6079-173">데이터의 가용성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-173">Increase availability of data.</span></span>
- <span data-ttu-id="f6079-174">보다 정확한 답변을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-174">Provide more accurate answers.</span></span>

## <a name="scenario-automate-order-processing"></a><span data-ttu-id="f6079-175">시나리오: 주문 처리 자동화</span><span class="sxs-lookup"><span data-stu-id="f6079-175">Scenario: Automate order processing</span></span>

<span data-ttu-id="f6079-176">Syntex를 SharePoint 사용하면 고객 주문을 수동으로 처리하는 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-176">With SharePoint Syntex, you can reduce the time of manual processing of customer orders.</span></span> <span data-ttu-id="f6079-177">예를 들어 OCR 처리를 사용하여 팩스, 전자 메일 또는 용지의 주문을 SharePoint 자동화된 프로세스를 사용하여 주문을 이행할 수 있도록 해당 주문에서 메타데이터를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-177">For example, you can upload orders from fax, email, or paper into SharePoint by using OCR processing and then extract the metadata from those orders so you can fulfill them by using automated processes.</span></span>

<span data-ttu-id="f6079-178">예를 들어 공급망 관리자는 수동 데이터 입력으로 인한 오류를 줄이고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-178">For example, a supply chain manager wants to reduce errors caused by manual data entry.</span></span> <span data-ttu-id="f6079-179">비즈니스 시스템으로 들어오는 오류를 줄이기 위해 인바운드 고객 주문(용지, 팩스 또는 전자 메일)의 수동 검토 및 데이터 입력을 방지하려는 경우</span><span class="sxs-lookup"><span data-stu-id="f6079-179">They want to avoid manual review and data entry of inbound customer orders (paper, fax, or e-mail) to reduce errors going into their business systems.</span></span> <span data-ttu-id="f6079-180">AI 및 기계 학습 기술을 적용하여 들어오는 주문 정보의 유효성을 검사하고 핵심 데이터를 추출한 다음 ERP 시스템에 자동으로 푸시하여 주문 이행 및 조정을 위해 솔루션을 원합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-180">They want a solution that applies AI and machine learning techniques to validate incoming order information, extract core data and automatically push it into their ERP system, for order fulfillment and reconciliation.</span></span>

<span data-ttu-id="f6079-181">이 시나리오를 자동화할 때 다음을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-181">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="f6079-182">주문 및 배송 정확도가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-182">Order and shipment accuracy increases.</span></span>
- <span data-ttu-id="f6079-183">주문 또는 배송 오류와 관련된 수수료 또는 페널티가 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-183">Fees or penalties associated to order or shipment errors are reduced.</span></span>
- <span data-ttu-id="f6079-184">송장 송장 또는 지급이 감소하는 경우의 지연</span><span class="sxs-lookup"><span data-stu-id="f6079-184">Delays in invoicing or payments decrease.</span></span>
- <span data-ttu-id="f6079-185">직원 비용 절감</span><span class="sxs-lookup"><span data-stu-id="f6079-185">Personnel costs are reduced.</span></span>

## <a name="scenario-simplify-visa-renewal-process"></a><span data-ttu-id="f6079-186">시나리오: Visa 갱신 프로세스 간소화</span><span class="sxs-lookup"><span data-stu-id="f6079-186">Scenario: Simplify visa renewal process</span></span>

<span data-ttu-id="f6079-187">SharePoint Syntex를 사용하면 주요 계약 정보에 대한 미리 알림 및 갱신을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-187">SharePoint Syntex can help you automate reminders and renewals for key contract information.</span></span> <span data-ttu-id="f6079-188">예를 들어 HR 감독은 직원의 Visas를 최신으로 유지 및/또는 정시에 갱신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-188">For example, an HR director needs to ensure that employees’ visas are up to date and/or renewed on time.</span></span> <span data-ttu-id="f6079-189">사람들이 Visas를 업데이트하는 간단하고 직관적인 프로세스를 제공하려는 경우</span><span class="sxs-lookup"><span data-stu-id="f6079-189">They want to give people a simple and intuitive process for updating their Visas.</span></span> <span data-ttu-id="f6079-190">계약에서 갱신 날짜를 추출하고 갱신 날짜가 다가오면 직원에게 미리 알림을 자동으로 보내는 솔루션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-190">They need a solution that extracts renewal dates from contracts and automatically sends employees reminders when their renewal dates are approaching.</span></span>

<span data-ttu-id="f6079-191">이 시나리오를 자동화할 때 다음을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-191">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="f6079-192">비준수 수준이 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-192">The levels of non-compliance are reduced.</span></span>
- <span data-ttu-id="f6079-193">수동 미리 알림 수가 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-193">The number of manual reminders is reduced.</span></span>
- <span data-ttu-id="f6079-194">비준수에 대한 벌금 수가 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="f6079-194">The number of fines for non-compliance is reduced.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6079-195">기타 참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6079-195">See also</span></span>

[<span data-ttu-id="f6079-196">Microsoft SharePoint 도입: 시작</span><span class="sxs-lookup"><span data-stu-id="f6079-196">Microsoft SharePoint Syntex adoption: Get started</span></span>](adoption-getstarted.md)