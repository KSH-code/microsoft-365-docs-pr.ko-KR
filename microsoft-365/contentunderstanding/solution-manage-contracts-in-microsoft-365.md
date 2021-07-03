---
title: Microsoft 365 솔루션을 사용하여 계약 관리
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts m365solution-overview
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Microsoft 365, 목록, SharePoint 및 SharePoint Syntex 솔루션으로 계약을 Microsoft Teams 방법을 Power Automate.
ms.openlocfilehash: bc2570b08add2fa93637b9f64931c5903795a079
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287320"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="5ae11-103">Microsoft 365 솔루션을 사용하여 계약 관리</span><span class="sxs-lookup"><span data-stu-id="5ae11-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="5ae11-104">이 문서에서는 조직의 구성 요소 및 구성 요소를 사용하여 조직에 SharePoint Syntex 관리 솔루션을 만드는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ae11-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="5ae11-105">또한 고유한 비즈니스 요구에 맞는 솔루션을 계획하고 만드는 데 도움이 되는 프레임워크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="5ae11-106">이 솔루션이 계약 관리에 대해 설명하는 경우에도 작업 또는 송장의 설명과 같은 다른 문서 관리 솔루션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-106">Even though this solution talks about contract management, you can adapt it to create other document management solutions, such as for statements of work or invoices.</span></span>

<span data-ttu-id="5ae11-107">*이 콘텐츠 집합은 Microsoft의 최신 Microsoft 365 솔루션 전략 팀과 함께 Thomas Molbach가 개발한 새로운 솔루션에 대해 문서화합니다.*</span><span class="sxs-lookup"><span data-stu-id="5ae11-107">*This content set documents a Microsoft 365 solution developed by Thomas Molbach with the Modern Work Solution Strategy Team at Microsoft.*</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="5ae11-108">비즈니스 문제 식별</span><span class="sxs-lookup"><span data-stu-id="5ae11-108">Identify the business problem</span></span>

<span data-ttu-id="5ae11-109">계약 관리 시스템을 계획하는 첫 번째 단계는 해결하려는 문제를 이해하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-109">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="5ae11-110">이 솔루션의 경우 다음 네 가지 주요 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-110">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="5ae11-111">**계약을 식별합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae11-111">**Identify contracts**.</span></span> <span data-ttu-id="5ae11-112">조직은 송장, 계약서, 작업 설명 등의 많은 문서에서 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-112">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="5ae11-113">일부는 전자 메일을 통해 전송된 디지털 자산이고, 일부는 기존 메일을 통해 전송된 용지 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-113">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="5ae11-114">다른 모든 문서에서 모든 고객 계약을 식별한 다음 이와 같이 분류하는 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-114">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="5ae11-115">**계약 승인 내역을 추적합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae11-115">**Track the history of contract approvals**.</span></span> <span data-ttu-id="5ae11-116">조직은 계약이 승인 또는 거부 찾은지 여부와 지급이 처리된지 여부를 안정적으로 찾을 수 있는 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-116">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="5ae11-117">**계약 승인을 관리하는 사이트입니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae11-117">**Site to manage contract approvals**.</span></span> <span data-ttu-id="5ae11-118">조직에서는 필요한 모든 관련자가 계약을 쉽게 검토할 수 있는 공동 작업 사이트를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-118">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="5ae11-119">관련자는 필요한 경우 전체 계약을 검토할 수 있지만 주로 각 계약에서 몇 가지 주요 필드(예: 고객 이름, PO 번호 및 총 비용)를 보는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-119">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="5ae11-120">이해 관계자는 들어오는 계약을 쉽게 승인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-120">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="5ae11-121">**검토된 계약을 라우팅합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae11-121">**Route reviewed contracts**.</span></span> <span data-ttu-id="5ae11-122">승인됨 및 거부된 계약은 특정 워크플로를 통해 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-122">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="5ae11-123">승인된 계약은 결제 처리를 위해 타사 응용 프로그램으로 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-123">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="5ae11-124">거부된 계약은 추가 검토를 위해 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-124">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="5ae11-125">솔루션 개요</span><span class="sxs-lookup"><span data-stu-id="5ae11-125">Overview of the solution</span></span>

  ![목록, SharePoint Syntex, SharePoint 및 Teams 사용하는 솔루션 Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="5ae11-127">이 계약 관리 솔루션 지침에는 다음과 같은 네 가지 구성 요소가 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ae11-127">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="5ae11-128">**Microsoft SharePoint Syntex**: 모델을 만들어 계약 파일을 식별하고 분류한 다음 계약 파일에서 적절한 데이터를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-128">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="5ae11-129">**Microsoft SharePoint 목록:** 최신 SharePoint 사용할 수 있는 서식을 사용하여 비즈니스에 친숙한 형식으로 계약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-129">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="5ae11-130">**Microsoft Teams**: Teams 채널 및 관련 탭의 기능을 사용하여 관련자가 계약을 검토하고 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-130">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="5ae11-131">**Power Automate:** 흐름을 사용하여 승인 프로세스를 통해 계약을 안내한 다음 타사 응용 프로그램에 지급을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-131">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="5ae11-132">작동 방식</span><span class="sxs-lookup"><span data-stu-id="5ae11-132">How it all works</span></span>

  ![문서를 업로드하고, 데이터를 추출하고, 이해 관계자에게 알리고, 계약을 승인하거나 거부하는 워크플로를 보여주는 솔루션 다이어그램입니다.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="5ae11-134">문서가 문서 라이브러리에 SharePoint 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-134">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="5ae11-135">문서 SharePoint Syntex 이해 모델이 문서 라이브러리에 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-135">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="5ae11-136">각 파일을 검사하여 검색할 수 있는 "계약" 콘텐츠 형식과 일치하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-136">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="5ae11-137">일치하는 파일을 찾으면 해당 파일을 "계약"으로 분류하고 문서의 콘텐츠 형식을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-137">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="5ae11-138">또한 이 모델은 클라이언트, 계약자 및 수수료 금액과 같이 이해 관계자가 관심을 가지는 각 계약 파일에서 특정 데이터를 *끌어오기도 합니다.*</span><span class="sxs-lookup"><span data-stu-id="5ae11-138">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="5ae11-139">다음 페이지는 모델이 식별하기 위해 교육된 계약의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-139">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![계약의 예입니다.](../media/content-understanding/contract.png)

3. <span data-ttu-id="5ae11-141">Microsoft Teams 모든 이해 관계자는 문서 라이브러리의 모든 계약이 승인 또는 거부를 위해 표시되는 보안 Teams 채널의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-141">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="5ae11-142">이 Teams 사용하여 새 계약을 검토해야 하는 경우 모든 이해 관계자에게 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-142">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>

4. <span data-ttu-id="5ae11-143">이 Power Automate 사용하여 계약은 Teams 채널의 승인 프로세스를 통해 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-143">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="5ae11-144">구성원이 계약을 승인하면 계약 상태가 승인됨으로 변경되고, 모든 구성원은 Teams 게시를 통해 알림을 하게 되고, 계약이 지급 준비가 됨을 보여 줄 품목이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-144">When a member approves a contract, the contract status is changed to approved, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="5ae11-145">이 프로세스를 확장하여 결제를 위해 타사 금융 응용 프로그램에 직접 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-145">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5. <span data-ttu-id="5ae11-146">구성원이 계약을 거부하면 상태가 거부로 변경되고 모든 구성원은 해당 게시물을 통해 Teams 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-146">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="5ae11-147">이 솔루션의 최종 결과는 조직에 대한 자동화된 비즈니스 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-147">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="5ae11-148">직원은 문서의 승인 워크플로를 시작하고 Teams 사용자 지정 타일 보기를 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-148">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     ![계약 탭](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a><span data-ttu-id="5ae11-150">라이선스 요구사항</span><span class="sxs-lookup"><span data-stu-id="5ae11-150">Licensing requirements</span></span>

<span data-ttu-id="5ae11-151">이 솔루션은 Microsoft 365 Enterprise(E1, E3, E5, F3) 또는 비즈니스(기본, 표준 또는 Premium) 라이선스의 일부로 사용할 수 있는 다음 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-151">This solution relies on the following functionality, all available as part of a Microsoft 365 Enterprise (E1, E3, E5, F3) or Business (Basic, Standard, or Premium) license:</span></span>

- <span data-ttu-id="5ae11-152">Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="5ae11-152">Microsoft SharePoint Syntex</span></span>
- <span data-ttu-id="5ae11-153">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5ae11-153">Microsoft Teams</span></span>
- <span data-ttu-id="5ae11-154">Power Automate</span><span class="sxs-lookup"><span data-stu-id="5ae11-154">Power Automate</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="5ae11-155">솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="5ae11-155">Create the solution</span></span>

<span data-ttu-id="5ae11-156">다음 섹션에서는 계약 관리 솔루션을 구성하는 방법에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-156">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="5ae11-157">이 단계는 다음 세 단계로 나뉘어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae11-157">It's divided into three steps:</span></span>

- [<span data-ttu-id="5ae11-158">1단계. 사용자 SharePoint Syntex 사용하여 계약 파일을 식별하고 데이터 추출</span><span class="sxs-lookup"><span data-stu-id="5ae11-158">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="5ae11-159">2단계. 이 Microsoft Teams 사용하여 계약 관리 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="5ae11-159">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="5ae11-160">3단계. 이 Power Automate 사용하여 계약 처리 흐름 만들기</span><span class="sxs-lookup"><span data-stu-id="5ae11-160">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
