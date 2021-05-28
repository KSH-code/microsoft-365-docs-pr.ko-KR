---
title: 'Microsoft SharePoint 도입: 시작'
description: 비즈니스 문제를 해결하는 데 SharePoint 조직에서 Syntex를 사용 및 구현하는 방법을 학습합니다.
ms.author: samanro
author: samanro
manager: pamgreen
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
ms.openlocfilehash: 9a73f14662deb0fc68ac6c2a8552d988efc1d351
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696469"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="c77cc-103">Microsoft SharePoint 도입: 시작</span><span class="sxs-lookup"><span data-stu-id="c77cc-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="c77cc-104">Syntex에서 사용할 수 있는 지능형 콘텐츠 SharePoint 다음 세 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="c77cc-105">**콘텐츠 이해:** 코드 없는 AI 모델을 만들어 콘텐츠에서 정보를 분류하고 추출하여 지식 검색 및 재사용을 위한 메타데이터를 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-105">**Content understanding:** Create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="c77cc-106">콘텐츠 [이해에 대해 자세히 알아보겠습니다.](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c77cc-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="c77cc-107">**콘텐츠 처리:** 콘텐츠 캡처, 수집 및 분류를 자동화하고 콘텐츠를 사용하여 콘텐츠 중심 프로세스를 Power Automate.</span><span class="sxs-lookup"><span data-stu-id="c77cc-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="c77cc-108">콘텐츠 처리에 [대해 자세히 알아보겠습니다.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c77cc-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="c77cc-109">**콘텐츠 준수:** Microsoft Information Protection에 통합된 보안 및 거버넌스를 개선하기 위해 콘텐츠를 제어하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="c77cc-110">새로운 AI 서비스 및 기능을 사용하여 콘텐츠 이해 및 분류 앱을 Syntex를 사용하여 콘텐츠 관리 흐름에 직접 SharePoint 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="c77cc-111">콘텐츠를 이해하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="c77cc-112">사용하는 모델 형식은 파일 형식 및 사용 사례를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="c77cc-113">양식 처리</span><span class="sxs-lookup"><span data-stu-id="c77cc-113">Form processing</span></span> | <span data-ttu-id="c77cc-114">문서 이해</span><span class="sxs-lookup"><span data-stu-id="c77cc-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="c77cc-115">문서 라이브러리에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-115">Created from document library.</span></span> | <span data-ttu-id="c77cc-116">Syntex의 일부인 콘텐츠 센터에서 SharePoint 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="c77cc-117">AI 작성기에서 만든 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-117">Model created in AI builder.</span></span> | <span data-ttu-id="c77cc-118">네이티브 인터페이스에서 만든 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-118">Model created in native interface.</span></span> |
| <span data-ttu-id="c77cc-119">반구조적 파일 형식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="c77cc-120">구조화되지 않은 파일 형식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="c77cc-121">Settable 분류자입니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-121">Settable classifier.</span></span> | <span data-ttu-id="c77cc-122">선택적 추출기를 사용할 수 있는 학습 가능한 분류자입니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="c77cc-123">단일 라이브러리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-123">Restricted to a single library.</span></span> | <span data-ttu-id="c77cc-124">여러 라이브러리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="c77cc-125">PDF, JPG, PNG 형식 교육 총 50MB/500 pp.</span><span class="sxs-lookup"><span data-stu-id="c77cc-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="c77cc-126">5~10개의 PDF, Office 또는 전자 메일 파일(부정 예제 포함)에 대해 학습 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="c77cc-127">기능을 보다 완전한 비교는 문서 이해 모델과 양식 처리 모델 간의 [차이를 참조하세요.](difference-between-document-understanding-and-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="c77cc-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="c77cc-128">최적화할 파일럿 비즈니스 시나리오 확인</span><span class="sxs-lookup"><span data-stu-id="c77cc-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="c77cc-129">조직에서 SharePoint Syntex 사용을 준비하려면 먼저 유용한 시나리오를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="c77cc-130">"이유"는 필요한 모델과 모델이 적용되는 위치를 기준으로 조직을 구성하는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="c77cc-131">다음은 문서 이해가 조직에 도움이 될 수 있는 몇 가지 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="c77cc-132">**콘텐츠 처리:** 계약서, 작업 설명 및 기타 양식과 같은 문서를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="c77cc-133">양식을 조정하고 필드를 이해하고 매핑하기 위해 모델을 교육한 다음 양식을 실행하여 데이터를 자동으로 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="c77cc-134">자세한 내용은 양식 처리 [개요를 참조하세요.](form-processing-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c77cc-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="c77cc-135">**송장 분석:** 송장에서 관련 세부 정보를 끌어오고 정책이 준수되고 있는지 또는 적절하게 처리되고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c77cc-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="c77cc-136">Syntex가 조직에 SharePoint 수 있는 방법을 생각해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="c77cc-137">비즈니스 프로세스 자동화</span><span class="sxs-lookup"><span data-stu-id="c77cc-137">Automate business processes</span></span>
- <span data-ttu-id="c77cc-138">검색 정확도 향상</span><span class="sxs-lookup"><span data-stu-id="c77cc-138">Improve search accuracy</span></span>
- <span data-ttu-id="c77cc-139">규정 준수 위험 관리</span><span class="sxs-lookup"><span data-stu-id="c77cc-139">Manage compliance risk</span></span>

<span data-ttu-id="c77cc-140">고려할 비즈니스 시나리오를 고려할 때 다음과 같은 질문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="c77cc-141">실제 문제를 해결하나요?</span><span class="sxs-lookup"><span data-stu-id="c77cc-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="c77cc-142">광범위하게 사용되거나 광범위한 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="c77cc-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="c77cc-143">얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c77cc-143">Is it obtainable?</span></span>
- <span data-ttu-id="c77cc-144">성공을 측정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c77cc-144">Can you measure success?</span></span>

<span data-ttu-id="c77cc-145">영향 및 구현 용이성을 기반으로 시나리오 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="c77cc-146">초기 포커스 영역을 쉽게 구현할 수 있는 더 큰 영향 시나리오로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="c77cc-147">구현하기 어려운 낮은 영향 시나리오의 우선 순위를 낮게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="c77cc-148">예제 시나리오 및 사용 [사례를](adoption-scenarios.md) 사용하여 조직에서 Syntex를 사용하는 SharePoint 아이디어를 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-148">Use the [example scenarios and use cases](adoption-scenarios.md) to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="c77cc-149">역할 및 & 식별</span><span class="sxs-lookup"><span data-stu-id="c77cc-149">Identify roles & responsibilities</span></span>

<span data-ttu-id="c77cc-150">조직에서 모델을 빌드하고 관리할 사용자 결정</span><span class="sxs-lookup"><span data-stu-id="c77cc-150">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="c77cc-151">다음과 같은 역할이 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-151">The following roles might be involved:</span></span>

| <span data-ttu-id="c77cc-152">SharePoint/지식 관리자</span><span class="sxs-lookup"><span data-stu-id="c77cc-152">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="c77cc-153">Power Platform 관리자</span><span class="sxs-lookup"><span data-stu-id="c77cc-153">Power Platform admin</span></span> | <span data-ttu-id="c77cc-154">지식 관리자</span><span class="sxs-lookup"><span data-stu-id="c77cc-154">Knowledge manager</span></span> | <span data-ttu-id="c77cc-155">모델 소유자</span><span class="sxs-lookup"><span data-stu-id="c77cc-155">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="c77cc-156">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="c77cc-156">AAD role</span></span>| <span data-ttu-id="c77cc-157">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="c77cc-157">AAD role</span></span> | <span data-ttu-id="c77cc-158">AAD 역할</span><span class="sxs-lookup"><span data-stu-id="c77cc-158">AAD role</span></span> | <span data-ttu-id="c77cc-159">챔피언</span><span class="sxs-lookup"><span data-stu-id="c77cc-159">Champions</span></span> |
| <span data-ttu-id="c77cc-160">양식 처리 구성</span><span class="sxs-lookup"><span data-stu-id="c77cc-160">Configure form processing</span></span> | <span data-ttu-id="c77cc-161">양식 처리를 위한 일반 데이터 서비스 환경 구성</span><span class="sxs-lookup"><span data-stu-id="c77cc-161">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="c77cc-162">사용 사례 수집</span><span class="sxs-lookup"><span data-stu-id="c77cc-162">Gather use cases</span></span> | <span data-ttu-id="c77cc-163">비즈니스 사용 사례 수집</span><span class="sxs-lookup"><span data-stu-id="c77cc-163">Gather business use cases</span></span> |
| <span data-ttu-id="c77cc-164">콘텐츠 센터 및 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="c77cc-164">Manage content centers and permissions</span></span>| <span data-ttu-id="c77cc-165">AIB 크레딧 구매 및 할당</span><span class="sxs-lookup"><span data-stu-id="c77cc-165">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="c77cc-166">모범 사례 설정 및 모델 분석 검토</span><span class="sxs-lookup"><span data-stu-id="c77cc-166">Establish best practices and review model analytics</span></span> | <span data-ttu-id="c77cc-167">모델 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="c77cc-167">Create and apply models</span></span> |

<span data-ttu-id="c77cc-168">기술 관리자, 비즈니스 프로세스 소유자 및 콘텐츠 모델 소유자는 조직에서 샘플 모델과 챔피언 채택을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-168">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="c77cc-169">관련이 있을 수 있는 기타: 규정 준수 관리자, 세분화 관리자.</span><span class="sxs-lookup"><span data-stu-id="c77cc-169">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="c77cc-170">어디에서 모델을 빌드하고 적용할 것인가?</span><span class="sxs-lookup"><span data-stu-id="c77cc-170">Where will they build and apply the models?</span></span> <span data-ttu-id="c77cc-171">개선할 수 있는 기존 프로세스 또는 리포지토리가 있나요?</span><span class="sxs-lookup"><span data-stu-id="c77cc-171">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="c77cc-172">양식 처리: 양식 처리 작업을 받을 사이트를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-172">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="c77cc-173">문서 이해: 서로 다른 비즈니스 영역에 대해 여러 콘텐츠 센터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-173">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="c77cc-174">전략적 위치</span><span class="sxs-lookup"><span data-stu-id="c77cc-174">Strategic positioning</span></span>

<span data-ttu-id="c77cc-175">이해 관계자와 협의하여 이해 관계자가 Syntex를 사용하는 전략에 SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-175">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="c77cc-176">이 위치 관리에 도움이 되는 다음 리소스를 조사하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-176">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="c77cc-177">비즈니스 결과:</span><span class="sxs-lookup"><span data-stu-id="c77cc-177">Business outcomes:</span></span>
  - <span data-ttu-id="c77cc-178">잠재적 회계 결과</span><span class="sxs-lookup"><span data-stu-id="c77cc-178">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="c77cc-179">잠재적인 민첩성 결과</span><span class="sxs-lookup"><span data-stu-id="c77cc-179">Potential agility outcomes</span></span>
  - <span data-ttu-id="c77cc-180">비즈니스 결과 서식 파일</span><span class="sxs-lookup"><span data-stu-id="c77cc-180">Business outcome template</span></span>
- <span data-ttu-id="c77cc-181">이해 관계자/Exec 스폰서 구입/조정</span><span class="sxs-lookup"><span data-stu-id="c77cc-181">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="c77cc-182">비즈니스 사례 데크</span><span class="sxs-lookup"><span data-stu-id="c77cc-182">Business case decks</span></span>
  - <span data-ttu-id="c77cc-183">재무 모델</span><span class="sxs-lookup"><span data-stu-id="c77cc-183">Financial models</span></span>
  - <span data-ttu-id="c77cc-184">회사 준비 - 문화</span><span class="sxs-lookup"><span data-stu-id="c77cc-184">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="c77cc-185">관련자 파악</span><span class="sxs-lookup"><span data-stu-id="c77cc-185">Identify stakeholders</span></span>

<span data-ttu-id="c77cc-186">프로젝트에 대한 관련자를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-186">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="c77cc-187">역할</span><span class="sxs-lookup"><span data-stu-id="c77cc-187">Role</span></span> |<span data-ttu-id="c77cc-188">책무</span><span class="sxs-lookup"><span data-stu-id="c77cc-188">Responsibilities</span></span> |<span data-ttu-id="c77cc-189">부서</span><span class="sxs-lookup"><span data-stu-id="c77cc-189">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="c77cc-190">Executive sponsor(s)</span><span class="sxs-lookup"><span data-stu-id="c77cc-190">Executive sponsor(s)</span></span>   | <span data-ttu-id="c77cc-191">회사에 높은 수준의 비전과 가치 전달</span><span class="sxs-lookup"><span data-stu-id="c77cc-191">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="c77cc-192">경영진 대표</span><span class="sxs-lookup"><span data-stu-id="c77cc-192">Executive leadership</span></span>   |
| <span data-ttu-id="c77cc-193">Project 선행</span><span class="sxs-lookup"><span data-stu-id="c77cc-193">Project lead(s)</span></span> | <span data-ttu-id="c77cc-194">전체 실행 및 배포 과정 감독</span><span class="sxs-lookup"><span data-stu-id="c77cc-194">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="c77cc-195">프로젝트 관리</span><span class="sxs-lookup"><span data-stu-id="c77cc-195">Project management</span></span> |
| <span data-ttu-id="c77cc-196">지식 관리자</span><span class="sxs-lookup"><span data-stu-id="c77cc-196">Knowledge administrators</span></span>| <span data-ttu-id="c77cc-197">콘텐츠 센터 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="c77cc-197">Create and manage the content centers</span></span> | <span data-ttu-id="c77cc-198">IT 또는 기타 부서</span><span class="sxs-lookup"><span data-stu-id="c77cc-198">IT or other department</span></span>|
| <span data-ttu-id="c77cc-199">콘텐츠 관리자 및 모델 소유자</span><span class="sxs-lookup"><span data-stu-id="c77cc-199">Content managers and model owners</span></span>| <span data-ttu-id="c77cc-200">사용 사례 수집 및 모델 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="c77cc-200">Gather use cases and create and apply models</span></span> | <span data-ttu-id="c77cc-201">모든 부서</span><span class="sxs-lookup"><span data-stu-id="c77cc-201">Any department</span></span>|
| <span data-ttu-id="c77cc-202">챔피언</span><span class="sxs-lookup"><span data-stu-id="c77cc-202">Champions</span></span> | <span data-ttu-id="c77cc-203">이의 처리 독려 및 관리</span><span class="sxs-lookup"><span data-stu-id="c77cc-203">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="c77cc-204">모든 부서(직원)</span><span class="sxs-lookup"><span data-stu-id="c77cc-204">Any department (staff)</span></span> |
| <span data-ttu-id="c77cc-205">테넌트 관리자</span><span class="sxs-lookup"><span data-stu-id="c77cc-205">Tenant administrator</span></span> | <span data-ttu-id="c77cc-206">테넌트 수준 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c77cc-206">Configure tenant-level settings</span></span> | <span data-ttu-id="c77cc-207">IT 부서</span><span class="sxs-lookup"><span data-stu-id="c77cc-207">IT department</span></span>|
| <span data-ttu-id="c77cc-208">파워 플랫폼 관리자</span><span class="sxs-lookup"><span data-stu-id="c77cc-208">Power Platform administrator</span></span>| <span data-ttu-id="c77cc-209">일반 데이터 서비스 환경 구성</span><span class="sxs-lookup"><span data-stu-id="c77cc-209">Configure common data services environment</span></span> | <span data-ttu-id="c77cc-210">IT 부서</span><span class="sxs-lookup"><span data-stu-id="c77cc-210">IT department</span></span>|

> [!Note]
> <span data-ttu-id="c77cc-211">이러한 각 역할을 롤아웃 전체에서 이행하는 것이 까다로우면 식별된 솔루션을 시작하는 데 이러한 역할이 모두 필요하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-211">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="c77cc-212">준비 검사 목록</span><span class="sxs-lookup"><span data-stu-id="c77cc-212">Readiness checklist</span></span>

<span data-ttu-id="c77cc-213">Syntex를 구현하기 SharePoint 준비하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-213">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![콘텐츠 이해를 위한 준비](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="c77cc-215">종료 상태 계획</span><span class="sxs-lookup"><span data-stu-id="c77cc-215">Plan the end state</span></span>
    - <span data-ttu-id="c77cc-216">문서 이해 모델은 끝이 아니라 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-216">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="c77cc-217">다음을 사용하여 추출된 메타데이터의 값을 사용 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-217">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="c77cc-218">검색</span><span class="sxs-lookup"><span data-stu-id="c77cc-218">Search</span></span>
      - <span data-ttu-id="c77cc-219">필터링 및 보기 서식</span><span class="sxs-lookup"><span data-stu-id="c77cc-219">Filtering and view formatting</span></span>
      - <span data-ttu-id="c77cc-220">규정 준수</span><span class="sxs-lookup"><span data-stu-id="c77cc-220">Compliance</span></span>
      - <span data-ttu-id="c77cc-221">자동화</span><span class="sxs-lookup"><span data-stu-id="c77cc-221">Automation</span></span>
2. <span data-ttu-id="c77cc-222">식별</span><span class="sxs-lookup"><span data-stu-id="c77cc-222">Identify</span></span>
    - <span data-ttu-id="c77cc-223">기존 정보 아키텍처 및 콘텐츠 관리 기능 사용을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-223">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="c77cc-224">기존 콘텐츠 형식이 모델에 대해 좋은 후보인가요?</span><span class="sxs-lookup"><span data-stu-id="c77cc-224">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="c77cc-225">메타데이터를 통해 개선할 기존 프로세스는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="c77cc-225">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="c77cc-226">디자인</span><span class="sxs-lookup"><span data-stu-id="c77cc-226">Design</span></span>
    - <span data-ttu-id="c77cc-227">정보 아키텍처, 관리되는 메타데이터 및 콘텐츠 형식에 대한 접근 방식 디자인</span><span class="sxs-lookup"><span data-stu-id="c77cc-227">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="c77cc-228">정의, 만들기, 관리 프로세스를 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-228">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="c77cc-229">조직 참여</span><span class="sxs-lookup"><span data-stu-id="c77cc-229">Engage your organization</span></span>

1. <span data-ttu-id="c77cc-230">지주를 식별하고 시나리오를 확인하고 프로젝트 계획을 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-230">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="c77cc-231">설정을 구성하고 라이선스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-231">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="c77cc-232">인식과 교육 시작 - 챔피언을 모집합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-232">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="c77cc-233">단계적 롤아웃</span><span class="sxs-lookup"><span data-stu-id="c77cc-233">Roll out in stages.</span></span>  
1. <span data-ttu-id="c77cc-234">피드백을 수집하고 이행합니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-234">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="c77cc-235">사용량이 증가함에 따라 필요한 경우 AI 작성기 크레딧에 대한 계획이 커지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c77cc-235">As usage grows plan for any AI Builder credits as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="c77cc-236">기타 참고 항목</span><span class="sxs-lookup"><span data-stu-id="c77cc-236">See also</span></span>

[<span data-ttu-id="c77cc-237">Syntex의 시나리오 및 SharePoint 사례</span><span class="sxs-lookup"><span data-stu-id="c77cc-237">Scenarios and use cases in SharePoint Syntex</span></span>](adoption-scenarios.md)