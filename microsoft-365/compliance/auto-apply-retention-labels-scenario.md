---
title: 보존 레이블로 SharePoint에 저장된 문서의 수명 주기 관리
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 메타데이터를 사용하여 내용을 분류하고 레이블을 자동으로 적용하며 이벤트 기반 보존을 사용하여 보존 기간을 시작하여 SharePoint 에서 문서의 라이프사이클을 관리하는 방법입니다.
ms.openlocfilehash: 250bf182c26616a3a2f9253471469d2cecbd8d2b
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560671"
---
# <a name="use-retention-labels-to-manage-the-lifecycle-of-documents-stored-in-sharepoint"></a><span data-ttu-id="0e348-103">보존 레이블로 SharePoint에 저장된 문서의 수명 주기 관리</span><span class="sxs-lookup"><span data-stu-id="0e348-103">Use retention labels to manage the lifecycle of documents stored in SharePoint</span></span>

><span data-ttu-id="0e348-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="0e348-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0e348-105">이 문서에서는 자동으로 적용된 보존 레이블과 이벤트 기반 보존을 사용하여 SharePoint에 저장된 문서의 라이프사이클을 관리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-105">This article describes how you can manage the lifecycle of documents that are stored in SharePoint by using automatically applied retention labels and event-based retention.</span></span>

<span data-ttu-id="0e348-106">자동 적용 기능은 문서 분류에 SharePoint 메타데이터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-106">The auto-apply functionality uses SharePoint metadata for document classification.</span></span> <span data-ttu-id="0e348-107">이 문서의 예는 제품 관련 문서에 대한 것이지만 다른 시나리오에서도 동일한 개념을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-107">The example in this article is for product-related documents, but the same concepts can be used for other scenarios.</span></span> <span data-ttu-id="0e348-108">예를 들어, 석유 및 가스 산업에서 석유 플랫폼, 웰 로그 또는 생산 라이센스와 같은 물리적 자산에 대한 문서의 라이프사이클을 관리하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-108">For example, in the oil and gas industry, you could use it to manage the lifecycle of documents about physical assets such as oil platforms, well logs, or production licenses.</span></span> <span data-ttu-id="0e348-109">금융 서비스 산업에서는 은행 계좌, 담보 대출 또는 보험 계약 문서를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-109">In the financial services industry, you could manage bank account, mortgage, or insurance contract documents.</span></span> <span data-ttu-id="0e348-110">공공 부문에서는 건축 허가서나 세금 양식을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-110">In the public sector, you could manage construction permits or tax forms.</span></span>

<span data-ttu-id="0e348-111">이 기사에서는 정보 아키텍처와 보존 라벨의 정의를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-111">In this article, we'll look at the information architecture and definition of the retention labels.</span></span> <span data-ttu-id="0e348-112">그럼 라벨을 자동 적용하여 서류를 분류하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-112">Then we'll classify documents by auto-applying the labels.</span></span> <span data-ttu-id="0e348-113">마지막으로 보존 기간을 시작하는 이벤트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-113">And finally we'll generate the events that initiate the retention period.</span></span>

## <a name="information-architecture"></a><span data-ttu-id="0e348-114">정보 아키텍처</span><span class="sxs-lookup"><span data-stu-id="0e348-114">Information architecture</span></span>

<span data-ttu-id="0e348-115">당사의 시나리오는 SharePoint를 사용하여 회사가 개발하는 제품에 대한 모든 문서를 저장하는 제조 회사입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-115">Our scenario is a manufacturing company that uses SharePoint to store all the documents about the products that the company develops.</span></span> <span data-ttu-id="0e348-116">이러한 문서에는 제품 사양, 공급자와의 계약 및 사용자 매뉴얼이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-116">These documents include product specifications, agreements with suppliers, and user manuals.</span></span> <span data-ttu-id="0e348-117">이러한 문서가 엔터프라이즈 콘텐츠 관리 정책을 통해 SharePoint에 저장되면 문서 메타데이터가 정의되어 이를 분류하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-117">When these documents are stored in SharePoint through Enterprise Content Management policies, document metadata is defined, which is used to classify them.</span></span> <span data-ttu-id="0e348-118">각 문서에는 다음과 같은 메타 데이터 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-118">Each document has the following metadata properties:</span></span>

- <span data-ttu-id="0e348-119">**Doc 유형**(제품 사양, 계약서 또는 사용자 설명서 등)</span><span class="sxs-lookup"><span data-stu-id="0e348-119">**Doc Type** (such as product specification, agreement, or user manual)</span></span>

- <span data-ttu-id="0e348-120">**제품 이름**</span><span class="sxs-lookup"><span data-stu-id="0e348-120">**Product Name**</span></span>

- <span data-ttu-id="0e348-121">**상태** (초안 또는 최종)</span><span class="sxs-lookup"><span data-stu-id="0e348-121">**Status** (draft or final)</span></span>

<span data-ttu-id="0e348-122">이 메타데이터는 모든 문서에 대해 *생산 문서*라는 기본 콘텐츠 유형을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-122">This metadata forms a base content type called *Production Document* for all the documents.</span></span>

![제품 설명서 메타 데이터 표](../media/SPRetention1.png)

> [!NOTE]
> <span data-ttu-id="0e348-124">**문서 유형** 및 **상태** 속성은 시나리오의 뒷부분에 나오는 보존 정책에서 보존 레이블을 분류하고 자동 적용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-124">The **Doc Type** and **Status** properties are used by retention policies later in this scenario to classify and auto-apply retention labels.</span></span>

<span data-ttu-id="0e348-125">여러 유형의 문서를 나타내는 여러 콘텐츠 유형이 있을 수 있지만 제품 설명서에 초점을 맞추겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-125">We might have several content types that represent different types of documents, but let's focus on the product documentation.</span></span>

<span data-ttu-id="0e348-126">이 시나리오에서는 관리되는 메타 데이터 서비스 및 용어 저장소를 사용하여 *문서 유형*에 대한 용어 집합과 *제품 이름*에 대한 용어 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-126">In this scenario, we use the Managed Metadata service and the Term Store to create a term set for *Doc Type* and another one for *Product Name*.</span></span> <span data-ttu-id="0e348-127">각 용어 집합에 대해 각 값에 대한 용어를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-127">For each term set, we create a term for each value.</span></span> <span data-ttu-id="0e348-128">SharePoint 조직의 경우 Term Store에서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-128">It would look like something like this in Term Store for your SharePoint organization:</span></span>

![용어 저장소의 제품 설명서에 대한 샘플 용어 집합](../media/SPRetention2.png)

<span data-ttu-id="0e348-130">*콘텐츠 유형*은(는) [ 콘텐츠 유형 허브](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b)를 사용하여 생성하고 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-130">*Content Type* can be created and published by using the [Content Type Hub](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b).</span></span> <span data-ttu-id="0e348-131">[PnP 프로비저닝 프레임워크](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-framework) 또는 [ 사이트 설계 JSON 스키마](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type)와 같은 사이트 프로비저닝 도구를 사용하여 컨텐츠 유형을 생성하고 게시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-131">You can also create and publish a content type by using site provisioning tools, such as the [PnP provisioning framework](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-framework) or [site design JSON schema](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type).</span></span>

<span data-ttu-id="0e348-132">각 제품에는 올바른 콘텐츠 유형을 사용하는 하나의 문서 라이브러리가 포함된 전용 SharePoint 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-132">Each product has a dedicated SharePoint site that contains one document library that has the right content types enabled.</span></span> <span data-ttu-id="0e348-133">모든 문서는 이 문서 라이브러리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-133">All documents are stored in this document library.</span></span>

![제품 설명서에 대한 문서 라이브러리](../media/SPRetention3.png)

> [!NOTE]
> <span data-ttu-id="0e348-135">이 시나리오의 제조 회사는 제품당 SharePoint 사이트를 보유하는 대신 제품당 마이크로소프트 팀을 사용하여 지속적인 채팅을 통해 팀원 간의 협업을 지원하고 문서 관리를 위해 팀 내 **파일** 탭을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-135">Instead of having a SharePoint site per product, the manufacturing company in this scenario could use a Microsoft Team per product to support collaboration among members of the team, such as through persistent chat, and use the **Files** tab in Teams for document management.</span></span> <span data-ttu-id="0e348-136">이 기사에서는 문서에만 초점을 맞추므로 사이트만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-136">In this article we only focus on documents, so, we'll only use a site.</span></span>

<span data-ttu-id="0e348-137">다음은 스피닝 위젯 제품의 문서 라이브러리 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-137">Here's a view of the document library for the Spinning Widget product:</span></span>

![스피닝 위젯 문서 라이브러리](../media/SPRetention4.png)

<span data-ttu-id="0e348-139">이제 문서 관리를 위한 기본 정보 아키텍처가 마련되었으므로 메타데이터를 사용하는 문서에 대한 보존 및 폐기 전략과 이러한 문서를 분류하는 방법에 대해 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-139">Now that we have the basic information architecture in place for document management, let's look at the retention and disposal strategy for the documents that use the metadata and how we classify those documents.</span></span>

## <a name="retention-and-disposition"></a><span data-ttu-id="0e348-140">보존 및 폐기</span><span class="sxs-lookup"><span data-stu-id="0e348-140">Retention and disposition</span></span>

<span data-ttu-id="0e348-141">제조 회사의 규정 준수 및 데이터 거버넌스 정책은 데이터 보존 및 폐기 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-141">The manufacturing company's compliance and data governance policies dictate how data is preserved and disposed of.</span></span> <span data-ttu-id="0e348-142">제품 관련 서류는 제품 제조 기간과 일정한 추가 기간 동안 보관해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-142">Product-related documents must be kept for as long as the product is manufactured and for a certain additional period.</span></span> <span data-ttu-id="0e348-143">추가 기간은 제품 사양, 계약서 및 사용자 설명서에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-143">The additional period differs for product specifications, agreements, and user manuals.</span></span> <span data-ttu-id="0e348-144">다음 표는 보존 및 폐기 요구 사항을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-144">The following table indicates the retention and disposition requirements:</span></span>

| <span data-ttu-id="0e348-145">**문서 유형**</span><span class="sxs-lookup"><span data-stu-id="0e348-145">**Document type**</span></span>          | <span data-ttu-id="0e348-146">**보존**</span><span class="sxs-lookup"><span data-stu-id="0e348-146">**Retention**</span></span>                          | <span data-ttu-id="0e348-147">**폐기**</span><span class="sxs-lookup"><span data-stu-id="0e348-147">**Disposition**</span></span>                              |
| -------------------------- | -------------------------------------- | -------------------------------------------- |
| <span data-ttu-id="0e348-148">제품 사양</span><span class="sxs-lookup"><span data-stu-id="0e348-148">Product specifications</span></span>      | <span data-ttu-id="0e348-149">생산 중단 후 5년</span><span class="sxs-lookup"><span data-stu-id="0e348-149">5 years after production stops</span></span>  | <span data-ttu-id="0e348-150">삭제</span><span class="sxs-lookup"><span data-stu-id="0e348-150">Delete</span></span>                                       |
| <span data-ttu-id="0e348-151">제품 계약서</span><span class="sxs-lookup"><span data-stu-id="0e348-151">Product agreements</span></span>          | <span data-ttu-id="0e348-152">생산이 중단된 후 10년</span><span class="sxs-lookup"><span data-stu-id="0e348-152">10 years after production stops</span></span> | <span data-ttu-id="0e348-153">검토</span><span class="sxs-lookup"><span data-stu-id="0e348-153">Review</span></span>                                       |
| <span data-ttu-id="0e348-154">사용자 설명서</span><span class="sxs-lookup"><span data-stu-id="0e348-154">User manuals</span></span>                | <span data-ttu-id="0e348-155">생산 중단 후 5년</span><span class="sxs-lookup"><span data-stu-id="0e348-155">5 years after production stops</span></span>  | <span data-ttu-id="0e348-156">삭제</span><span class="sxs-lookup"><span data-stu-id="0e348-156">Delete</span></span>                                       |
| <span data-ttu-id="0e348-157">다른 모든 유형의 문서</span><span class="sxs-lookup"><span data-stu-id="0e348-157">All other types of documents</span></span> | <span data-ttu-id="0e348-158">능동적으로 유지하지 않음</span><span class="sxs-lookup"><span data-stu-id="0e348-158">Don't actively retain</span></span>  | <span data-ttu-id="0e348-159">문서가 3년보다 오래된 경우 삭제</span><span class="sxs-lookup"><span data-stu-id="0e348-159">Delete when document is older than 3 years</span></span> <br /><br /> <span data-ttu-id="0e348-160">지난 3년 동안 수정하지 않은 문서는 3년이 지난 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-160">A document is considered older than 3 years if it hasn't been modified within the last 3 years.</span></span> |
|||

<span data-ttu-id="0e348-161">Microsoft 365 규중 준수 센터를 사용하여 다음 [보존 레이블](retention.md#retention-labels)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-161">We use the Microsoft 365 compliance center to create the following [retention labels](retention.md#retention-labels):</span></span>

  - <span data-ttu-id="0e348-162">제품 사양</span><span class="sxs-lookup"><span data-stu-id="0e348-162">Product Specification</span></span>

  - <span data-ttu-id="0e348-163">제품 계약</span><span class="sxs-lookup"><span data-stu-id="0e348-163">Product Agreement</span></span>

  - <span data-ttu-id="0e348-164">사용자 매뉴얼</span><span class="sxs-lookup"><span data-stu-id="0e348-164">User Manual</span></span>

<span data-ttu-id="0e348-165">이 문서에서는 제품 사양 보존 레이블을 작성하고 자동 적용하는 방법만을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-165">In this article, we only show how to create and auto-apply the Product Specification retention label.</span></span> <span data-ttu-id="0e348-166">전체 시나리오를 구현하기 위해 다른 두 문서 유형에 대한 보존 레이블을 만들고 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-166">To implement the complete scenario, you would also create and auto-apply retention labels for the other two document types.</span></span>

### <a name="settings-for-the-product-specification-retention-label"></a><span data-ttu-id="0e348-167">제품 사양 보존 레이블 설정</span><span class="sxs-lookup"><span data-stu-id="0e348-167">Settings for the Product Specification retention label</span></span>

<span data-ttu-id="0e348-168">제품 사양 보존 레이블에 대한 [파일 계획](file-plan-manager.md)은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-168">Here's the [file plan](file-plan-manager.md) for the Product Specification retention label:</span></span>

- <span data-ttu-id="0e348-169">**이름:** 제품 사양</span><span class="sxs-lookup"><span data-stu-id="0e348-169">**Name:** Product Specification</span></span>

- <span data-ttu-id="0e348-170">**관리자에 대한 설명:** 운영 중지 후 5년간 유지, 자동 삭제, 이벤트 기반 보존, 이벤트 유형은 *제품 중단*입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-170">**Description for admins:** Retain for 5 years after production stops, auto delete, event-based retention, event type is *Product Cessation*.</span></span>

- <span data-ttu-id="0e348-171">**사용자에 대한 설명:** 생산 중지 후 5년간 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-171">**Description for users:** Retain for 5 years after production stops.</span></span>

- <span data-ttu-id="0e348-172">**보존 작업:** 유지 및 삭제</span><span class="sxs-lookup"><span data-stu-id="0e348-172">**Retention action:** Retain and delete.</span></span>

- <span data-ttu-id="0e348-173">**보존 기간:** 5년 (1,825일)</span><span class="sxs-lookup"><span data-stu-id="0e348-173">**Retention duration:** 5 years (1,825 days).</span></span>

- <span data-ttu-id="0e348-174">**레코드 레이블**: 콘텐츠를 [*레코드*](records.md)(으)로 분류하도록 보존 레이블을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-174">**Record label**: Configure the retention label to classify content as a [*record*](records.md).</span></span> <span data-ttu-id="0e348-175">(*레코드*로 분류된 문서는 사용자가 수정하거나 삭제할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="0e348-175">(Documents that are classified as a *record* can't be modified or deleted by users.)</span></span>

- <span data-ttu-id="0e348-176">**파일 계획 설명자:**(시나리오를 단순화하기 위해 파일 설명자가 제공되지 않습니다)</span><span class="sxs-lookup"><span data-stu-id="0e348-176">**File plan descriptors:** (for simplifying the scenario, no file descriptors are provided)</span></span>

<span data-ttu-id="0e348-177">다음 스크린샷은 Microsoft 365 규정 준수 센터에서 제품 사양 보존 레이블을 생성할 때의 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-177">The following screenshot shows the settings when you create the Product Specification retention label in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0e348-178">보존 레이블을 생성할 때 *제품 중지* 이벤트 유형을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-178">You can create the *Product Cessation* event type when you create the retention label.</span></span> <span data-ttu-id="0e348-179">다음 절의 절차를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-179">See the procedure in the following section.</span></span>

![제품 사양 레이블에 대한 보존 설정입니다.](../media/SPRetention5.png)

> [!NOTE]
> <span data-ttu-id="0e348-181">문서 삭제를 5년 동안 기다리지 않으려면 테스트 환경에서 이 시나리오를 다시 생성하는 경우 보존 기간을 ***1일***일로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-181">To avoid a 5-year wait for document deletion, set the retention duration to ***1 day*** if you're recreating this scenario in a test environment.</span></span>

### <a name="create-an-event-type-when-you-create-a-retention-label"></a><span data-ttu-id="0e348-182">보존 레이블을 생성할 때 이벤트 유형을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-182">Create an event type when you create a retention label</span></span>

1. <span data-ttu-id="0e348-183">드롭다운 목록의 **콘텐츠를 보존 또는 삭제**에서 **이벤트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-183">From the **Retain or delete content based on** drop-down list, select **an event**.</span></span>

2. <span data-ttu-id="0e348-184">**을(를) 선택합니다. 이벤트 유형**.</span><span class="sxs-lookup"><span data-stu-id="0e348-184">Select **Choose an event type**.</span></span>
    
    ![제품 사양 레이블 대화 상자에 대한 새 이벤트 유형을 생성합니다.](../media/SPRetention6.png)

3. <span data-ttu-id="0e348-186">**이벤트 유형**을(를) 선택한 다음 **이벤트 유형 선택**에서 **새로운 이벤트 유형 생성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-186">Select **Choose an event type**, and then select **Create new event types** on the **Choose an event type** page.</span></span>

4. <span data-ttu-id="0e348-187">***제품 중단***이라는 이벤트 유형을 만들고 설명을 입력한 후 **완료**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-187">Create an event type named ***Product Cessation***, enter a description, and select **Finish**.</span></span>

5. <span data-ttu-id="0e348-188">**이벤트 유형 선택** 페이지로 돌아간 후 사용자가 만든 **제품 중단** 이벤트 유형을 선택한 다음 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-188">Back on the **Choose an event type** page, select the **Product Cessation** event type that you created, and then select **Add**.</span></span>

   <span data-ttu-id="0e348-189">제품 사양 보존 레이블의 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-189">Here's what the settings look like for the Product Specification retention label.</span></span> 

   ![새 제품 사양 레이블 설정](../media/SPRetention7.png)

6. <span data-ttu-id="0e348-191">**이 레이블 생성**을 선택</span><span class="sxs-lookup"><span data-stu-id="0e348-191">Select **Create this label**.</span></span> 
> [!TIP]
> <span data-ttu-id="0e348-192">자세한 단계는 [을(를) 참조하십시오.유지 기간이 이벤트](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event)를 기준으로 하는 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-192">For more detailed steps, see [Create a label whose retention period is based on an event](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event).</span></span>

<span data-ttu-id="0e348-193">이제 제품 사양 컨텐츠에 보존 라벨을 자동으로 적용하는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-193">Now let's look at auto-applying the retention label to product-specification content.</span></span>

## <a name="auto-apply-retention-labels-to-classify-content"></a><span data-ttu-id="0e348-194">보존 레이블을 자동으로 적용하여 내용을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-194">Auto-apply retention labels to classify content</span></span>

<span data-ttu-id="0e348-195">여기에서는 키워드 쿼리 언어(KQL)를 사용하여 [자동 적용](apply-retention-labels-automatically.md) 보존 레이블을 생성하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-195">We're going to use Keyword Query Language (KQL) to [auto-apply](apply-retention-labels-automatically.md) the retention labels that we created.</span></span> <span data-ttu-id="0e348-196">KQL은 검색 쿼리를 작성하는 데 사용되는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-196">KQL is the language that's used to build search queries.</span></span> <span data-ttu-id="0e348-197">KQL에서는 키워드 또는 관리되는 속성을 사용하여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-197">In KQL, you can search by using keywords or managed properties.</span></span> <span data-ttu-id="0e348-198">자세한 내용은 [KQL(키워드 쿼리 언어) 구문 참조](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-198">For more information, see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="0e348-199">기본적으로 Microsoft 365에 "***최종*** **상태** 및 **문서 유형**이 ***제품 사양***인 모든 문서에 *제품 사양* 보존 레이블을 적용"하라고 주문하고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-199">Basically, we want to tell Microsoft 365 to "apply the *Product Specification* retention label to all documents that have a **Status** of ***Final*** and a **Doc Type** of ***Product Specification***."</span></span> <span data-ttu-id="0e348-200">**상태** 및 **문서 유형**은 [정보 아키텍처](#information-architecture) 섹션에서 제품 문서 콘텐츠 유형에 대해 이전에 정의했던 사이트 열입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-200">Recall that **Status** and **Doc Type** are the site columns that we defined for the Product Documentation content type in the [Information architecture](#information-architecture) section.</span></span> <span data-ttu-id="0e348-201">이를 위해서는 검색 스키마를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-201">To do this, we need to configure the search schema.</span></span>

<span data-ttu-id="0e348-202">SharePoint는 콘텐츠를 인덱싱할 때 각 사이트 열에 대해 크롤링된 속성을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-202">When SharePoint indexes content, it automatically generates crawled properties for each site column.</span></span> <span data-ttu-id="0e348-203">이 시나리오에서 우리는 **문서 종류** 및 **상태** 속성에 관심이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-203">For this scenario, we're interested in the **Doc Type** and **Status** properties.</span></span> <span data-ttu-id="0e348-204">탐색된 속성을 만들기 위해 검색하기 위해 올바른 내용 유형이며 사이트 열이 채워진 문서가 라이브러리에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-204">We need documents in the library that are the right content type and have the site columns filled in for search to create the crawled properties.</span></span>

<span data-ttu-id="0e348-205">SharePoint 관리 센터에서 검색 구성을 열고 **검색 스키마 관리**를 선택하여 탐색된 속성을 보고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-205">In the SharePoint admin center, open the Search configuration, and select **Manage Search Schema** to view and configure the crawled properties.</span></span>

![검색 스키마에서 속성을 탐색했습니다.](../media/SPRetention8.png)

<span data-ttu-id="0e348-207">**크롤링된 속성** 상자에 ***상태***를 입력하고 녹색 화살표를 선택하면 다음과 같은 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-207">If we type ***status*** in the **Crawled properties** box and select the green arrow, we should see a result like this:</span></span>

![ows_Status 속성이 탐색되었습니다.](../media/SPRetention9.png)

<span data-ttu-id="0e348-209">우리가 관심을 가지고 있는 속성은 **ows\_\_상태** 속성(이중 밑줄에 주목)입니다..</span><span class="sxs-lookup"><span data-stu-id="0e348-209">The **ows\_\_Status** property (notice the double underscore) is the one that interests us.</span></span> <span data-ttu-id="0e348-210">생산 문서 컨텐츠 유형의 **상태** 속성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-210">It maps to the **Status** property of the Production Document content type.</span></span>

<span data-ttu-id="0e348-211">이제 ***ows\_문서***를 입력하고 녹색 화살표를 선택하면 다음과 같은 것이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-211">Now, if we type ***ows\_doc*** and select the green arrow, we should see something like this:</span></span>

![ows_Doc_Type 속성이 탐색되었습니다.](../media/SPRetention10.png)

<span data-ttu-id="0e348-213">**ows\_문서\_x0020\_유형** 속성은 우리가 관심을 갖는 두 번째 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-213">The **ows\_Doc\_x0020\_Type** property is the second property that interests us.</span></span> <span data-ttu-id="0e348-214">생산 문서 컨텐츠 유형의 **문서 유형** 속성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-214">It maps to the **Doc Type** property of the Production Document content type.</span></span>

> [!TIP]
> <span data-ttu-id="0e348-215">이 시나리오에 대해 탐색된 속성의 이름을 확인하려면 프로덕션 문서가 들어 있는 문서 라이브러리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-215">To identify the name of a crawled property for this scenario, go to the document library that contains the production documents.</span></span> <span data-ttu-id="0e348-216">그런 다음 라이브러리 설정으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-216">Then go to the library settings.</span></span> <span data-ttu-id="0e348-217">**열**에서 열 이름 (예: **상태** 또는 **문서 유형**)을 선택하여 사이트 열 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-217">For **Columns**, select the name of the column (for example, **Status** or **Doc Type**) to open the site column page.</span></span> <span data-ttu-id="0e348-218">해당 페이지의 URL에서 *필드* 매개 변수에 필드 이름이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-218">The *Field* parameter in the URL for that page contains the name of the field.</span></span> <span data-ttu-id="0e348-219">"ows_" 접두사가 붙는 필드 이름은 크롤링된 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-219">This field name, prefixed with "ows_", is the name of the crawled property.</span></span> <span data-ttu-id="0e348-220">예를 들어 URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status`은 *ows\_\_상태* 크롤링된 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-220">For example, the URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status` corresponds to the *ows\_\_Status* crawled property.</span></span>

<span data-ttu-id="0e348-221">찾고 있는 탐색된 속성이 SharePoint 관리 센터의 검색 스키마 관리 섹션에 나타나지 않으면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-221">If the crawled properties you're looking for don't appear in the Manage Search Schema section in SharePoint admin center:</span></span>

- <span data-ttu-id="0e348-222">아마도 문서가 색인화되지 않았을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-222">Maybe the documents haven't been indexed.</span></span> <span data-ttu-id="0e348-223">**문서 라이브러리 설정** > **고급 설정**으로 이동하여 라이브러리를 강제로 다시 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-223">You can force a reindex of the library by going to **Document library settings** > **Advanced Settings**.</span></span>

- <span data-ttu-id="0e348-224">문서 라이브러리가 최신 사이트에 있는 경우 SharePoint 관리자도 사이트 모음 관리자인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-224">If the document library is in a modern site, make sure that the SharePoint admin is also a site collection admin.</span></span>

<span data-ttu-id="0e348-225">크롤링된 속성과 관리 속성에 대한 자세한 내용은 [SharePoint Server에서 자동으로 작성된 관리 속성](https://docs.microsoft.com/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e348-225">For more information about crawled and managed properties, see [Automatically created managed properties in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint).</span></span>

### <a name="map-crawled-properties-to-pre-defined-managed-properties"></a><span data-ttu-id="0e348-226">탐색된 속성을 미리 정의된 관리 속성에 매핑</span><span class="sxs-lookup"><span data-stu-id="0e348-226">Map crawled properties to pre-defined managed properties</span></span>

<span data-ttu-id="0e348-227">KQL은 검색 쿼리에서 크롤링된 속성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-227">KQL can't use crawled properties in search queries.</span></span> <span data-ttu-id="0e348-228">관리 속성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-228">It has to use a managed property.</span></span> <span data-ttu-id="0e348-229">일반적인 검색 시나리오에서는 관리 속성을 생성하여 필요한 탐색 속성에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-229">In a typical search scenario, we create a managed property and map it to the crawled property that we need.</span></span> <span data-ttu-id="0e348-230">그러나 보존 레이블 자동 적용의 경우 KQL에서 미리 정의된 관리 속성만 지정할 수 있으며 사용자 지정 관리 속성은 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-230">However, for auto-applying retention labels, you can only specify pre-defined managed properties in KQL, not custom managed properties.</span></span> <span data-ttu-id="0e348-231">시스템에 사용할 수 있는 *RefableString00* 문자열에서 *RefableString199*에 대한 미리 정의된 관리 속성 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-231">There's a set of predefined managed properties in the system for string *RefinableString00* to *RefinableString199* that you can use.</span></span> <span data-ttu-id="0e348-232">전체 목록은 [기본 미사용 관리 속성](https://docs.microsoft.com/sharepoint/manage-search-schema#default-unused-managed-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e348-232">For a complete list, see [Default unused managed properties](https://docs.microsoft.com/sharepoint/manage-search-schema#default-unused-managed-properties).</span></span> <span data-ttu-id="0e348-233">이러한 기본 관리 속성은 일반적으로 검색 구체화를 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-233">These default managed properties are typically used for defining search refiners.</span></span>

<span data-ttu-id="0e348-234">KQL 쿼리를 올바른 보존 레이블을 제품 문서 내용에 자동으로 적용하기 위해 크롤링된 속성 \**ows\_문서\_x0020\_유형*과 *ows\_\_상태*\* 를 두 개의 정의 가능한 관리 속성에 맵핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-234">For the KQL query to automatically apply the correct retention label to product document content, we map the crawled properties **ows\_Doc\_x0020\_Type* and *ows\_\_Status** to two refinable managed properties.</span></span> <span data-ttu-id="0e348-235">이 시나리오의 테스트 환경에서는 **RefinableString00** 및 **RefinableString01**은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-235">In our test environment for this scenario, **RefinableString00** and **RefinableString01** aren't being used.</span></span> <span data-ttu-id="0e348-236">SharePoint 관리 센터의 **검색 스키마 관리**에서 \*\* 관리 속성\*\*을(를) 확인하여 이 문제를 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-236">We determined this by looking at **Managed Properties** in **Manage Search Schema** in the SharePoint admin center.</span></span>

![검색 스키마의 관리 속성](../media/SPRetention12.png)

<span data-ttu-id="0e348-238">이전 스크린 샷의 **매핑된 크롤링 속성** 열이 비어있는 것을 주목하세요.</span><span class="sxs-lookup"><span data-stu-id="0e348-238">Notice that the **Mapped Crawled Properties** column in the previous screenshot is empty.</span></span>

<span data-ttu-id="0e348-239">**ows\_문서\_x0020\_유형** 크롤링된 속성에 매핑하려면 이 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-239">To map the **ows\_Doc\_x0020\_Type** crawled property, follow these steps:</span></span>

1. <span data-ttu-id="0e348-240">**관리 속성** 필터 상자에 ***RefinableString00***을 입력하고 녹색 화살표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-240">In the **Managed property** filter box, type ***RefinableString00*** and select the green arrow.</span></span>

2. <span data-ttu-id="0e348-241">결과 목록에서 **RefinableString00** 링크를 선택한 다음 아래로 스크롤하여 **크롤링된 속성에 매핑** 섹션으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-241">In the results list, select the **RefinableString00** link, and then scroll down to the **Mappings to crawled properties** section.</span></span>  

3. <span data-ttu-id="0e348-242">**매핑 추가**를 선택하고 **크롤링된 속성 선택** 창의 **크롤링된 속성 이름 검색** 상자에 ***ows\_문서\_x0020\_유형***을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-242">Select **Add a Mapping**, and then type ***ows\_Doc\_x0020\_Type*** in the **Search for a crawled property name** box in the **Crawled property selection** window.</span></span> <span data-ttu-id="0e348-243">**찾기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-243">Select **Find**.</span></span>  

4. <span data-ttu-id="0e348-244">결과 목록에서 **ows\_문서\_x0020\_유형**을 선택한 다음 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-244">In the results list, select **ows\_Doc\_x0020\_Type** and then select **OK**.</span></span>

   <span data-ttu-id="0e348-245">**맵핑된 크롤링 속성** 섹션에 다음 스크린샷과 유사한 내용이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-245">In the **Mapped Crawled Properties** section, you should see something similar to this screenshot:</span></span>

   ![매핑된 탐색 속성 섹션에서 매핑 추가를 선택합니다.](../media/SPRetention13.png)

5. <span data-ttu-id="0e348-247">페이지 하단으로 스크롤하고 **OK**를 선택하여 매핑을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-247">Scroll to the bottom of the page and select **OK** to save the mapping.</span></span>

<span data-ttu-id="0e348-248">**RefableString01** 및 **ows\_\_상태**를 매핑하려면 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-248">Repeat these steps to map **RefinableString01** and **ows\_\_Status**.</span></span>

<span data-ttu-id="0e348-249">이제 두 개의 관리되는 속성이 두 탐색된 속성에 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-249">Now you should have two managed properties mapped to the two crawled properties:</span></span>

![관리되는 속성이 탐색 속성에 매핑되어 표시됩니다.](../media/SPRetention14.png)

<span data-ttu-id="0e348-251">엔터프라이즈 검색을 실행하여 설정이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-251">Let's verify that our setup is correct by running an enterprise search.</span></span> <span data-ttu-id="0e348-252">브라우저에서 *https://\<your_tenant>.sharepoint.com/search*.(으)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-252">In a browser, go to *https://\<your_tenant>.sharepoint.com/search*.</span></span> <span data-ttu-id="0e348-253">검색 상자에 ***RefableString00:"Product Specification"*** 을 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-253">In the search box, type ***RefinableString00:"Product Specification"*** and press enter.</span></span> <span data-ttu-id="0e348-254">이 검색에서는**문서 유형** 중 ***제품 사양***이 있는 모든 문서를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-254">This search should return all documents that have a **Product Specification** of ***Doc Type***.</span></span>

<span data-ttu-id="0e348-255">이제 검색 상자에 **RefableString00: "Product Specification" 및 RefableString01을 입력합니다.Final**를 누르고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-255">Now in the search box, type **RefinableString00:"Product Specification" AND RefinableString01:Final** and press enter.</span></span> <span data-ttu-id="0e348-256">이 경우 ***제품 사양***을 포함하는 모든 문서를 **문서 유형**으로 또한 \***최종\*\*\*\*\*상태**가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-256">This should return all documents that have **Product Specification** of ***Doc Type*** and a **Status** of ***Final***.</span></span>

### <a name="create-auto-apply-label-policies"></a><span data-ttu-id="0e348-257">레이블 자동 적용 정책을 만들기</span><span class="sxs-lookup"><span data-stu-id="0e348-257">Create auto-apply label policies</span></span>

<span data-ttu-id="0e348-258">이제 KQL 쿼리가 작동 중임을 확인했으므로 KQL 쿼리를 사용하여 적절한 문서에 제품 사양 보존 레이블을 자동으로 적용하는 레이블 정책을 만들겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-258">Now that we've verified that the KQL query is working, let's create a label policy that uses a KQL query to auto-apply the Product Specification retention label to the appropriate documents.</span></span>

1. <span data-ttu-id="0e348-259">[준수 센터](https://compliance.microsoft.com/homepage)에서 **기록 관리** > **레이블 정책**으로 이동하여  > **레이블 자동 적용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-259">In the [compliance center](https://compliance.microsoft.com/homepage), go to **Records management** > **Label policies** > **Auto-apply a label**.</span></span>

   ![레이블 페이지에서 "라벨 자동 적용"을 선택합니다.](../media/SPRetention16.png)

2. <span data-ttu-id="0e348-261">마법사를 **자동으로 적용할 레이블을 선택**합니다 페이지에서 **자동 적용할 레이블을 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-261">On the **Choose a label to auto-apply** wizard page, select **Choose a label to auto-apply**.</span></span>

3. <span data-ttu-id="0e348-262">레이블 목록에서 **제품 규격**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-262">From the list of labels, select **Product Specification**.</span></span> <span data-ttu-id="0e348-263">그런 다음 **추가** 및 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-263">Then select **Add** and **Next**.</span></span>

4. <span data-ttu-id="0e348-264">**특정 단어나 구를 포함하는 콘텐츠에 레이블 적용**을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-264">Select **Apply label to content that contains specific words or phrases, or properties**, and then select **Next**.</span></span>

   ![특정 단어나 구 또는 속성을 포함하는 콘텐츠에 레이블 적용을 선택합니다.](../media/SPRetention17.png)

   <span data-ttu-id="0e348-266">다음 단계에서는 이전 섹션에서 테스트한 것과 동일한 KQL 검색 쿼리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-266">In the next step, you'll provide the same KQL search query that we tested in the previous section.</span></span> <span data-ttu-id="0e348-267">이 쿼리는 상태가 *Final*인 모든 제품 사양 문서를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-267">This query returns all Product Specification documents that have a status of *Final*.</span></span> <span data-ttu-id="0e348-268">레이블 정책에서 동일한 쿼리를 사용하면 제품 사양 보존 레이블이 일치하는 모든 문서에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-268">When we use this same query in the label policy, the Product Specification retention label will be automatically applied to all documents that match it.</span></span>

5. <span data-ttu-id="0e348-269">**키워드 쿼리 편집기** 상자에서 ***RefinableString00:"Product Specification" AND RefinableString01:Final***을 입력하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-269">In the **Keyword query editor** box, type ***RefinableString00:"Product Specification" AND RefinableString01:Final***, and then select **Next**.</span></span>

   ![키워드 쿼리 편집기 상자에서 쿼리를 지정합니다.](../media/SPRetention19.png)

6. <span data-ttu-id="0e348-271">이름(예: ***제품 사양 레이블 자동 적용***)과 레이블 정책에 대한 설명(선택 사항)을 입력한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-271">Type a name (for example, ***Auto apply Product Specification label***) and an optional description for the label policy, and then select **Next**.</span></span>

7. <span data-ttu-id="0e348-272">**위치 선택** 마법사 페이지에서 정책을 적용하려는 콘텐츠 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-272">On the **Choose locations** wizard page, you select the content locations that you want to apply the policy to.</span></span> <span data-ttu-id="0e348-273">이 시나리오에서는 모든 프로덕션 문서가 SharePoint 문서 라이브러리에 저장되기 때문에 정책을 SharePoint 위치에만 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-273">For this scenario, we apply the policy only to SharePoint locations, because all the production documents are stored in SharePoint document libraries.</span></span> <span data-ttu-id="0e348-274">**특정 위치**를 선택한 다음 **Exchange e-메일**, **OneDrive 계정** 및 **Microsoft 365 그룹**의 상태를 꺼짐으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-274">Select **Let me choose specific locations** and then toggle the status for **Exchange email**, **OneDrive accounts**, and **Microsoft 365 Groups** to off.</span></span> <span data-ttu-id="0e348-275">SharePoint 사이트의 상태가 켜짐으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-275">Make sure that the status for SharePoint sites is set to on.</span></span> 

    ![특정 사이트를 선택하여 레이블을 자동 적용할 수 있습니다.](../media/SPRetentionSPlocations.png)

   > [!TIP]
   > <span data-ttu-id="0e348-277">정책을 모든 SharePoint 사이트에 적용하는 대신 **사이트 선택**을 선택하여 특정 SharePoint 사이트의 URL을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-277">Instead of applying the policy to all SharePoint sites, you can select **Choose sites** and add the URLs for specific SharePoint sites.</span></span>

8. <span data-ttu-id="0e348-278">**다음**을 선택하여 **설정 검토** 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-278">Select **Next** to display the **Review your settings** page.</span></span>

    ![레이블을 자동으로 적용하도록 설정합니다.](../media/SPRetention18.png)

9. <span data-ttu-id="0e348-280">레이블 정책을 생성하려면 **자동 적용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-280">Select **Auto-apply** to create the label policy.</span></span>

   >[!NOTE]
   ><span data-ttu-id="0e348-281">KQL 검색 질의와 일치하는 모든 문서에 제품 사양 레이블을 자동으로 적용하는 데 최대 7일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-281">It takes up to 7 days to automatically apply the Product Specification label to all documents that match the KQL search query.</span></span>

### <a name="verify-that-the-retention-label-was-automatically-applied"></a><span data-ttu-id="0e348-282">보존 라벨이 자동으로 적용되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-282">Verify that the retention label was automatically applied</span></span>

<span data-ttu-id="0e348-283">7일 후 규정 준수 센터의 [ 활동 탐색기](data-classification-activity-explorer.md)를 사용하여 생성한 레이블 정책이 보존 레이블을 제품 문서에 자동으로 적용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-283">After 7 days, use the [activity explorer](data-classification-activity-explorer.md) in the compliance center to verify that the label policy that we created  automatically applied the retention labels to the product documents.</span></span>

<span data-ttu-id="0e348-284">문서 라이브러리에 있는 문서의 속성도 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-284">Also look at the properties of the documents in the Document Library.</span></span> <span data-ttu-id="0e348-285">정보 패널에서 보존 레이블이 선택된 문서에 적용되어 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-285">In the information panel, you can see that the retention label is applied to a selected document.</span></span>

![문서 라이브러리에서 문서 속성을 확인하여 레이블이 적용되었는지 확인합니다.](../media/SPRetention21.png)

<span data-ttu-id="0e348-287">보존 레이블이 문서에 자동으로 적용되었기 때문에 보존 레이블이 문서를 *레코드*로 선언하도록 구성되었기 때문에 해당 문서는 삭제되지 않도록 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-287">Because the retention labels were auto-applied to documents, those documents are protected from deletion because the retention label was configured to declare the documents as *records*.</span></span> <span data-ttu-id="0e348-288">이러한 보호의 예로서 다음 문서 중 하나를 삭제하려고 할 때 다음 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-288">As an example of this protection, we get the following error message when we try to delete one of these documents:</span></span>

![레이블이 문서가 레코드임을 선언하기 때문에 문서를 삭제할 수 없다는 오류 메시지가 표시됩니다.](../media/SPRetention22.png)

## <a name="generate-the-event-that-triggers-the-retention-period"></a><span data-ttu-id="0e348-290">보존 기간을 트리거하는 이벤트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-290">Generate the event that triggers the retention period</span></span>

<span data-ttu-id="0e348-291">이제 보존 라벨이 적용되었으므로 특정 제품의 생산 중단을 나타내는 이벤트에 초점을 맞추겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-291">Now that the retention labels are applied, let's focus on the event that will indicate the end of production for a particular product.</span></span> <span data-ttu-id="0e348-292">이 이벤트는 보존 레이블에 정의된 보존 기간의 시작을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-292">This event triggers the beginning of the retention period that's defined in the retention labels.</span></span> <span data-ttu-id="0e348-293">예를 들어 제품 사양 문서의 경우 "생산 종료" 이벤트가 트리거될 때 5년 보존 기간이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-293">For example, for product specification documents, the 5-year retention period begins when the "end of production" event is triggered.</span></span>

<span data-ttu-id="0e348-294">**관리 기록** > **이벤트**로 이동하여 Microsoft 365 규정 준수 센터에서 수동으로 이벤트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-294">You can manually create the event in the Microsoft 365 compliance center by going to **Records Managements** > **Events**.</span></span> <span data-ttu-id="0e348-295">이벤트 유형을 선택하고 올바른 자산 ID를 설정한 다음 이벤트 날짜를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-295">You would choose the event type, set the correct asset IDs, and enter a date for the event.</span></span> <span data-ttu-id="0e348-296">자세한 내용은 [이벤트가 발생할 때 보존 시작하기](event-driven-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e348-296">For more information, see [Start retention when an event occurs](event-driven-retention.md).</span></span>

<span data-ttu-id="0e348-297">그러나 이 시나리오에서는 외부 프로덕션 시스템에서 이벤트를 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-297">But for this scenario, we'll automatically generate the event from an external production system.</span></span> <span data-ttu-id="0e348-298">시스템은 제품이 생산 중인지 여부를 나타내는 단순한 SharePoint 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-298">The system is a simple SharePoint list that indicates whether a product is in production.</span></span> <span data-ttu-id="0e348-299">목록과 연결된 [전원 자동화](https://docs.microsoft.com/flow/getting-started) 흐름이 이벤트를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-299">A [Power Automate](https://docs.microsoft.com/flow/getting-started) flow that's associated with the list will trigger the event.</span></span> <span data-ttu-id="0e348-300">실제 시나리오에서는 다양한 시스템을 사용하여 HR 또는 CRM 시스템과 같은 이벤트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-300">In a real-world scenario, you could use various systems to generate the event, such as an HR or CRM system.</span></span> <span data-ttu-id="0e348-301">Power Automation에는 Microsoft Exchange, SharePoint, Teams 및 Dynamics 365와 같은 Microsoft 365 워크로드에 대한 많은 사용 가능한 상호 작용 및 구성 요소와 Twitter, Box, Salesforce 및 Workday와 같은 타사 앱이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-301">Power Automate contains many ready-to-use interactions and building block for Microsoft 365 workloads, such as Microsoft Exchange, SharePoint, Teams, and Dynamics 365, plus third-party apps such as Twitter, Box, Salesforce, and Workdays.</span></span> <span data-ttu-id="0e348-302">이 기능을 통해 다양한 시스템과 손쉽게 Power Automation을 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-302">This feature makes it easy to integrate Power Automate with various systems.</span></span> <span data-ttu-id="0e348-303">자세한 내용은 [이벤트 기반 보존의 자동화](automate-event-driven-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e348-303">For more information, see [Automate event-driven retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="0e348-304">다음 스크린샷은 이벤트를 트리거하는 데 사용되는 SharePoint 목록을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-304">The following screenshot shows the SharePoint list that will be used the trigger the event:</span></span>

![보존 이벤트를 트리거할 목록입니다.](../media/SPRetention23.png)

<span data-ttu-id="0e348-306">**생산** 열의 ***예***에 표시된 것처럼 현재 프로덕션 중인 제품이 두 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-306">There are two products currently in production, as indicated by the ***Yes*** in the **In Production** column.</span></span> <span data-ttu-id="0e348-307">이 열의 값을 제품에 대해 ***아니요***로 설정하면 목록과 관련된 흐름에서 자동으로 이벤트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-307">When the value in this column is set to ***No*** for a product, the flow associated with the list will automatically generate the event.</span></span> <span data-ttu-id="0e348-308">이벤트는 해당 제품 문서에 자동으로 적용된 보존 레이블의 보존 기간 시작을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-308">The event triggers the start of the retention period for the retention label that was auto-applied to the corresponding product documents.</span></span>

<span data-ttu-id="0e348-309">이 시나리오에서는 다음 흐름을 사용하여 이벤트를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-309">For this scenario, we use the following flow to trigger the event:</span></span>

![이벤트를 트리거하는 흐름의 구성](../media/SPRetention24.png)

<span data-ttu-id="0e348-311">이 흐름을 만들려면 SharePoint 커넥터에서 시작하여 **항목을 만들거나 수정할 때** 트리거를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-311">To create this flow, start from a SharePoint connector and select the **When an item is created or modified** trigger.</span></span> <span data-ttu-id="0e348-312">사이트 주소 및 목록 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-312">Specify the site address and list name.</span></span> <span data-ttu-id="0e348-313">그런 다음 **생산 중**에서 목록 열 값이 ***아니오***(또는 조건 카드의 *허위*)로 설정된 시점을 기준으로 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-313">Then add a condition based on when the **In Production** list column value is set to ***No*** (or equal to *false* on the condition card).</span></span> <span data-ttu-id="0e348-314">그런 다음 기본 제공 HTTP 서식 파일을 기반으로 하는 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-314">Then add an action based on the built-in HTTP template.</span></span> <span data-ttu-id="0e348-315">다음 섹션의 값을 사용하여 HTTP 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-315">Use the values in the following section to configure the HTTP action.</span></span> <span data-ttu-id="0e348-316">다음 섹션에서 **URI** 및 **Body** 속성의 값을 복사하여 템플릿에 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-316">You can copy the values for the **URI** and **Body** properties from the following section and paste them into the template.</span></span>

- <span data-ttu-id="0e348-317">**메서드**: POST</span><span class="sxs-lookup"><span data-stu-id="0e348-317">**Method**: POST</span></span>
- <span data-ttu-id="0e348-318">**URI**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="0e348-318">**URI**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="0e348-319">**헤더**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="0e348-319">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="0e348-320">**Body**:</span><span class="sxs-lookup"><span data-stu-id="0e348-320">**Body**:</span></span>
    
    ```HTML
    <?xml version='1.0' encoding='utf-8' standalone='yes'>
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices' xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata' xmlns='https://www.w3.org/2005/Atom'>
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent'>
    <updated>9/9/2017 10:50:00 PM</updated>
    <content type='application/xml'>
    <m:properties>
    <d:Name>Cessation Production @{triggerBody()?['Product_x0020_Name']?['Value']}</d:Name>
    <d:EventType>Product Cessation&lt;</d:EventType>
    <d:SharePointAssetIdQuery>ProductName:&quot;@{triggerBody()?['Product_x0020_Name']?['Value']}<d:SharePointAssetIdQuery>
    <d:EventDateTime>@{formatDateTime(utcNow(),'yyyy-MM-dd')}</d:EventDateTime>
    </m:properties>
    </content&gt>
    </entry>
    ```

<span data-ttu-id="0e348-321">이 목록에서는 이 시나리오에 대해 구성해야 하는 작업의 **Body** 속성에 있는 매개 변수를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-321">This list describes the parameters in the **Body** property of the action that must be configured for this scenario:</span></span>

- <span data-ttu-id="0e348-322">**이름**: 이 매개 변수는 Microsoft 365 규정 준수 센터에서 생성할 이벤트의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-322">**Name**: This parameter specifies the name of the event that will be created in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0e348-323">이 시나리오의 경우 이름은 "처리 운영 *xxx*"입니다. 여기서 *xxx*은(는) 이전에 생성한 **ProductName** 관리 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-323">For this scenario, the name is "Cessation Production *xxx*", where *xxx* is the value of the **ProductName** managed property that we created earlier.</span></span>
- <span data-ttu-id="0e348-324">**EventType**: 이 매개 변수의 값은 생성된 이벤트가 적용되는 이벤트 유형에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-324">**EventType**: The value for this parameter corresponds to the event type that the created event will apply to.</span></span> <span data-ttu-id="0e348-325">이 이벤트 유형은 보존 레이블을 생성할 때 정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-325">This event type was defined when you created the retention label.</span></span> <span data-ttu-id="0e348-326">이 시나리오의 경우 이벤트 유형은 "제품 중단"입니다."</span><span class="sxs-lookup"><span data-stu-id="0e348-326">For this scenario, the event type is "Product Cessation."</span></span>
- <span data-ttu-id="0e348-327">**SharePointAssetIdQuery**입니다. 이 매개 변수는 이벤트에 대한 자산 ID를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-327">**SharePointAssetIdQuery**: This parameter defines the asset ID for the event.</span></span> <span data-ttu-id="0e348-328">이벤트 기반 보존에는 문서의 고유 식별자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-328">Event-based retention needs a unique identifier for the document.</span></span> <span data-ttu-id="0e348-329">자산 ID를 사용하여 특정 이벤트가 적용되는 문서를 식별하거나 이 시나리오에서처럼 메타데이터 열 **제품 이름**을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-329">We can use asset IDs to identify the documents that a particular event applies to or, as in this scenario, the metadata column **Product Name**.</span></span> <span data-ttu-id="0e348-330">이렇게 하려면 KQL 쿼리에 사용할 수 있는 새 **ProductName** 관리 속성을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-330">To do  this, we need to create a new **ProductName** managed property that can be used in the KQL query.</span></span> <span data-ttu-id="0e348-331">대체적으로 새 관리 속성을 생성하는 대신 **RefableString00**를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-331">(Alternatively, we could use **RefinableString00** instead of creating a new managed property).</span></span> <span data-ttu-id="0e348-332">또한 이 새로운 관리 속성을 **ows_Product_x0020_Name** 크롤링된 속성에 맵핑해야합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-332">We also need to map this new managed property to the **ows_Product_x0020_Name** crawled property.</span></span> <span data-ttu-id="0e348-333">다음은 이 관리 속성의 스크린샷입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-333">Here's a screenshot of this managed property.</span></span>

    ![보존 관리 속성](../media/SPRetention25.png)

- <span data-ttu-id="0e348-335">**EventDateTime**: 이 매개 변수는 이벤트가 발생한 날짜를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-335">**EventDateTime**: This parameter defines the date that the event occurs.</span></span> <span data-ttu-id="0e348-336">현재 날짜 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-336">Use the current date format:</span></span><br/><br/><span data-ttu-id="0e348-337">*날짜 시간(utcNow()), 'yyyy-MM-dd'* 을(를) 포맷합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-337">*formatDateTime(utcNow(),'yyyy-MM-dd'*)</span></span>

### <a name="putting-it-all-together"></a><span data-ttu-id="0e348-338">모두 종합해 보면요.</span><span class="sxs-lookup"><span data-stu-id="0e348-338">Putting it all together</span></span>

<span data-ttu-id="0e348-339">이제 보존 라벨이 생성되고 자동으로 적용되며 흐름이 구성 및 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-339">Now the retention label is created and auto-applied, and the flow is configured and created.</span></span> <span data-ttu-id="0e348-340">제품 목록의 회전 위젯 제품에 대한 \*\*실행에서 \*\* 열의 값이 ***예***에서 ***아니오***(으)로 변경되면 흐름이 트리거되어 이벤트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-340">When the value in the **In Production** column for the Spinning Widget product in the Products list is changed from ***Yes*** to ***No***, the flow is triggered to create the event.</span></span> <span data-ttu-id="0e348-341">보안 및 준수 센터에서 이 이벤트를 보려면 **레코드 관리** > **이벤트**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-341">To see this event in the compliance center, go to **Records management** > **Events**.</span></span>

![흐름에 의해 트리거된 이벤트는 규정 준수 센터의 이벤트 페이지에 표시됩니다.](../media/SPRetention28.png)

<span data-ttu-id="0e348-343">이벤트를 선택하여 플라이아웃 페이지에서 세부 정보를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-343">Select the event to view the details on the flyout page.</span></span> <span data-ttu-id="0e348-344">이벤트가 생성되더라도 이벤트 상태는 처리된 SharePoint 사이트나 문서가 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-344">Notice that even though the event is created, the event status shows that no SharePoint sites or documents have been processed.</span></span>

![이벤트 세부 정보](../media/SPRetention29.png)

<span data-ttu-id="0e348-346">그러나 지연 후 이벤트 상태는 SharePoint 사이트와 SharePoint 문서가 처리되었음을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-346">But after a delay, the event status shows that a SharePoint site and a SharePoint document have been processed.</span></span>  

![이벤트 세부 정보는 문서가 처리되었음을 나타냅니다.](../media/SPRetention31.png)
 
<span data-ttu-id="0e348-348">*처리 생산 회전 위젯* 이벤트의 이벤트 날짜를 기준으로 회전 위젯 제품 문서에 적용된 레이블의 보존 기간이 시작되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-348">This shows that the retention period for the label applied to the Spinning Widget product document has been initiated, based on the event date of the *Cessation Production Spinning Widget* event.</span></span> <span data-ttu-id="0e348-349">1일 보존 기간을 구성하여 테스트 환경에서 시나리오를 구현했다고 가정하면 이벤트 생성 며칠 후 제품 문서의 문서 라이브러리로 이동하여 문서가 삭제되었는지(SharePoint의 삭제 작업이 실행된 후) 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-349">Assuming that you implemented the scenario in your test environment by configuring a one-day retention period, you can go to the document library for your product documents a few days after the event was created and verify that the document was deleted (after the deletion job in SharePoint has run).</span></span>

### <a name="more-about-asset-ids"></a><span data-ttu-id="0e348-350">자산 ID에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="0e348-350">More about asset IDs</span></span>

<span data-ttu-id="0e348-351">[시작 문서가 이벤트 발생 시 보존 시작](event-driven-retention.md) 문서에 설명된 것처럼 이벤트 유형, 보존 레이블, 이벤트 및 자산 ID 간의 관계를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-351">As the [Start retention when an event occurs](event-driven-retention.md) article explains, it's important to understand the relationship between event types, retention labels, events, and asset IDs.</span></span> <span data-ttu-id="0e348-352">자산 ID는 SharePoint 및 OneDrive의 문서 속성일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-352">The asset ID is simply a document property in SharePoint and OneDrive.</span></span> <span data-ttu-id="0e348-353">이벤트에 의해 트리거되는 보존 기간을 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-353">It helps you identify the documents whose retention period will be triggered by the event.</span></span> <span data-ttu-id="0e348-354">기본적으로 SharePoint에는 이벤트 기반 보존에 사용할 수 있는 **자산 ID** 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-354">By default, SharePoint has an **Asset Id** property that you can use for event-driven retention:</span></span>

![자산 ID 속성은 문서 속성 세부 정보 페이지에 표시됩니다.](../media/SPRetention26.png)

<span data-ttu-id="0e348-356">다음 스크린샷에서 볼 수 있듯이 자산 ID 관리 속성을 **ComplianceAssetId**라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-356">As the following screenshot shows, the asset ID managed property is called **ComplianceAssetId**.</span></span>

![ComplianceAssetId 관리 속성입니다.](../media/SPRetention27.png)

<span data-ttu-id="0e348-358">이 시나리오에서와 같이 기본 **Asset Id** 속성을 사용하는 대신 다른 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-358">Instead of using the default **Asset Id** property as we do in this scenario, you can use any other property.</span></span> <span data-ttu-id="0e348-359">그러나 이벤트에 대한 자산 ID 또는 키워드를 지정하지 않으면 해당 이벤트 유형의 레이블이 있는 모든 콘텐츠는 이벤트에 의해 보존 기간이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-359">But it's important to understand that if you don't specify an asset ID or keywords for an event, all the content that has a label of that event type will get its retention period triggered by the event.</span></span>

### <a name="using-advanced-search-in-sharepoint"></a><span data-ttu-id="0e348-360">SharePoint에서 고급 검색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-360">Using advanced search in SharePoint</span></span>

<span data-ttu-id="0e348-361">이전 스크린샷에서 탐색된 속성에 매핑된 **ComplianceTag**라는 보존 레이블과 관련된 또 다른 관리 속성이 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-361">In the previous screenshot, you can see that there's another managed property related to retention labels called **ComplianceTag** that's mapped to a crawled property.</span></span> <span data-ttu-id="0e348-362">**ComplianceAssetId** 관리 속성도 탐색된 속성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-362">The **ComplianceAssetId** managed property is also mapped to a crawled property.</span></span> <span data-ttu-id="0e348-363">즉, 고급 검색에서 이러한 관리 속성을 사용하여 보존 레이블로 태그가 지정된 모든 문서를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-363">This means that you can use these managed properties in advanced search to retrieve all documents that have been tagged with a retention label.</span></span>

## <a name="credits"></a><span data-ttu-id="0e348-364">크레딧</span><span class="sxs-lookup"><span data-stu-id="0e348-364">Credits</span></span>

<span data-ttu-id="0e348-365">이 시나리오의 작성자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0e348-365">This scenario was authored by:</span></span> 

<span data-ttu-id="0e348-366">Frederic Lapierre</span><span class="sxs-lookup"><span data-stu-id="0e348-366">Frederic Lapierre</span></span><br/><span data-ttu-id="0e348-367">Principal Consultant, Microsoft Services</span><span class="sxs-lookup"><span data-stu-id="0e348-367">Principal Consultant, Microsoft Services</span></span>
