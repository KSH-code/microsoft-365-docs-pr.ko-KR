---
title: 관리 솔루션을 사용하여 Microsoft 365 관리
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Syntex, Microsoft 365 및 SharePoint 솔루션을 사용하여 계약을 Microsoft Teams 방법을 Power Automate.
ms.openlocfilehash: 18866425cb331b01525dd488a6688608a3d1e559
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636221"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="e650a-103">관리 솔루션을 사용하여 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="e650a-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="e650a-104">이 문서에서는 조직의 Syntex 및 구성 요소를 사용하여 조직에 SharePoint 관리 솔루션을 만드는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e650a-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="e650a-105">또한 고유한 비즈니스 요구에 맞는 솔루션을 계획하고 만드는 데 도움이 되는 프레임워크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="e650a-106">이 솔루션이 비즈니스 요구에 전체적으로 적합하지 않은 경우에도 사용자 지정 계약 관리 솔루션을 만들기 위한 계획에서 솔루션의 일부를 채택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-106">Even if this solution doesn't suit your business needs as a whole, parts of it can be adopted in your planning to create a custom contract management solution.</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="e650a-107">비즈니스 문제 식별</span><span class="sxs-lookup"><span data-stu-id="e650a-107">Identify the business problem</span></span>

<span data-ttu-id="e650a-108">계약 관리 시스템을 계획하는 첫 번째 단계는 해결하려는 문제를 이해하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-108">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="e650a-109">이 솔루션의 경우 다음 네 가지 주요 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-109">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="e650a-110">**계약을 식별합니다.**</span><span class="sxs-lookup"><span data-stu-id="e650a-110">**Identify contracts**.</span></span> <span data-ttu-id="e650a-111">조직은 송장, 계약서, 작업 설명 등의 많은 문서에서 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-111">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="e650a-112">일부는 전자 메일을 통해 전송된 디지털 자산이고, 일부는 기존 메일을 통해 전송된 용지 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-112">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="e650a-113">다른 모든 문서에서 모든 고객 계약을 식별한 다음 이와 같이 분류하는 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-113">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="e650a-114">**계약 승인 내역을 추적합니다.**</span><span class="sxs-lookup"><span data-stu-id="e650a-114">**Track the history of contract approvals**.</span></span> <span data-ttu-id="e650a-115">조직은 계약이 승인 또는 거부 찾은지 여부와 지급이 처리된지 여부를 안정적으로 찾을 수 있는 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-115">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="e650a-116">**계약 승인을 관리하는 사이트입니다.**</span><span class="sxs-lookup"><span data-stu-id="e650a-116">**Site to manage contract approvals**.</span></span> <span data-ttu-id="e650a-117">조직에서는 필요한 모든 관련자가 계약을 쉽게 검토할 수 있는 공동 작업 사이트를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-117">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="e650a-118">관련자는 필요한 경우 전체 계약을 검토할 수 있지만 주로 각 계약에서 몇 가지 주요 필드(예: 고객 이름, PO 번호 및 총 비용)를 보는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-118">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="e650a-119">이해 관계자는 들어오는 계약을 쉽게 승인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-119">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="e650a-120">**검토된 계약을 라우팅합니다.**</span><span class="sxs-lookup"><span data-stu-id="e650a-120">**Route reviewed contracts**.</span></span> <span data-ttu-id="e650a-121">승인됨 및 거부된 계약은 특정 워크플로를 통해 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-121">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="e650a-122">승인된 계약은 결제 처리를 위해 타사 응용 프로그램으로 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-122">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="e650a-123">거부된 계약은 추가 검토를 위해 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-123">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="e650a-124">솔루션 개요</span><span class="sxs-lookup"><span data-stu-id="e650a-124">Overview of the solution</span></span>

  ![Syntex, SharePoint 목록, SharePoint 및 Teams 사용하는 솔루션 Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="e650a-126">이 계약 관리 솔루션 지침에는 다음과 같은 네 가지 구성 요소가 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e650a-126">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="e650a-127">**Microsoft SharePoint Syntex:** 모델을 만들어 계약 파일을 식별하고 분류한 다음 계약 파일에서 적절한 데이터를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-127">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="e650a-128">**Microsoft SharePoint 목록:** 최신 SharePoint 사용할 수 있는 서식을 사용하여 비즈니스에 친숙한 형식으로 계약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-128">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="e650a-129">**Microsoft Teams**: Teams 채널 및 관련 탭의 기능을 사용하여 관련자가 계약을 검토하고 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-129">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="e650a-130">**Power Automate:** 흐름을 사용하여 승인 프로세스를 통해 계약을 안내한 다음 타사 응용 프로그램에 지급을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-130">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="e650a-131">작동 방식</span><span class="sxs-lookup"><span data-stu-id="e650a-131">How it all works</span></span>

  ![문서를 업로드하고, 데이터를 추출하고, 이해 관계자에게 알리고, 계약을 승인하거나 거부하는 워크플로를 보여주는 솔루션 다이어그램입니다.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="e650a-133">문서가 문서 라이브러리에 SharePoint 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-133">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="e650a-134">문서 SharePoint 라이브러리에 Syntex 문서 이해 모델이 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-134">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="e650a-135">각 파일을 검사하여 검색할 수 있는 "계약" 콘텐츠 형식과 일치하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-135">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="e650a-136">일치하는 파일을 찾으면 해당 파일을 "계약"으로 분류하고 문서의 콘텐츠 형식을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-136">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="e650a-137">또한 이 모델은 클라이언트, 계약자 및 수수료 금액과 같이 이해 관계자가 관심을 가지는 각 계약 파일에서 특정 데이터를 *끌어오기도 합니다.*</span><span class="sxs-lookup"><span data-stu-id="e650a-137">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="e650a-138">다음 페이지는 모델이 식별하기 위해 교육된 계약의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-138">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![계약의 예입니다.](../media/content-understanding/contract.png)

3. <span data-ttu-id="e650a-140">Microsoft Teams 모든 이해 관계자는 문서 라이브러리의 모든 계약이 승인 또는 거부를 위해 표시되는 보안 Teams 채널의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-140">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="e650a-141">이 Teams 사용하여 새 계약을 검토해야 하는 경우 모든 이해 관계자에게 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-141">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>
 
4. <span data-ttu-id="e650a-142">이 Power Automate 사용하여 계약은 Teams 채널의 승인 프로세스를 통해 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-142">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="e650a-143">구성원이 계약을 승인하면 계약 상태가 승인으로 변경되고, 모든 구성원이 Teams 게시를 통해 알림을 하게 되고, 계약이 지급될 준비가 됐는지 표시하는 품목이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-143">When a member approves a contract, the contract status is changed to approve, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="e650a-144">이 프로세스를 확장하여 결제를 위해 타사 금융 응용 프로그램에 직접 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-144">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5.  <span data-ttu-id="e650a-145">구성원이 계약을 거부하면 상태가 거부로 변경되고 모든 구성원은 해당 게시물을 통해 Teams 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-145">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="e650a-146">이 솔루션의 최종 결과는 조직에 대한 자동화된 비즈니스 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-146">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="e650a-147">직원은 문서의 승인 워크플로를 시작하고 Teams 사용자 지정 타일 보기를 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-147">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     ![계약 탭](../media/content-understanding/tile-view.png)

## <a name="create-the-solution"></a><span data-ttu-id="e650a-149">솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="e650a-149">Create the solution</span></span>

<span data-ttu-id="e650a-150">다음 섹션에서는 계약 관리 솔루션을 구성하는 방법에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-150">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="e650a-151">이 단계는 다음 세 단계로 나뉘어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e650a-151">It's divided into three steps:</span></span>

- [<span data-ttu-id="e650a-152">1단계. Syntex를 SharePoint 사용하여 계약 파일을 식별하고 데이터 추출</span><span class="sxs-lookup"><span data-stu-id="e650a-152">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="e650a-153">2단계. 이 Microsoft Teams 사용하여 계약 관리 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="e650a-153">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="e650a-154">3단계. 이 Power Automate 사용하여 계약 처리 흐름 만들기</span><span class="sxs-lookup"><span data-stu-id="e650a-154">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
