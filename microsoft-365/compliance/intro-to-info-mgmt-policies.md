---
title: 정보 관리 정책 소개
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 정보 관리 정책을 사용하여 콘텐츠가 보존되는 기간 또는 사용자가 해당 콘텐츠에 대해 수행할 수 있는 작업과 같은 작업을 제어하고 추적하는 방법을 학습합니다.
ms.openlocfilehash: dfb1aeb3dbd3a2b17f18bbd03d5f4d3e198e4c47
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815515"
---
# <a name="introduction-to-information-management-policies"></a><span data-ttu-id="48647-103">정보 관리 정책 소개</span><span class="sxs-lookup"><span data-stu-id="48647-103">Introduction to information management policies</span></span>

<span data-ttu-id="48647-104">정보 관리 정책은 콘텐츠 형식에 대한 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="48647-104">An information management policy is a set of rules for a type of content.</span></span> <span data-ttu-id="48647-105">조직에서는 정보 관리 정책을 사용하여 콘텐츠의 보존 기간이나 사용자가 해당 콘텐츠에 대해 수행할 수 있는 작업과 같은 사항을 제어하고 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-105">Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content.</span></span> <span data-ttu-id="48647-106">정보 관리 정책은 조직이 법률 또는 정부 규정을 준수하도록 도와주거나 내부 비즈니스 프로세스를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-106">Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes.</span></span> 
  
<span data-ttu-id="48647-107">예를 들어 재무 제표의 "적절한 제어"를 입증하도록 요구하는 정부 규정을 따라야 하는 조직은 재무 제표와 관련된 모든 문서의 제작 및 승인 프로세스에서 특정 작업을 감사하는 하나 이상의 정보 관리 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-107">For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.</span></span>
  
<span data-ttu-id="48647-108">방법 정보는 정보 관리 정책 [만들기 및 적용을 참조하세요.](create-info-mgmt-policies.md)</span><span class="sxs-lookup"><span data-stu-id="48647-108">For how-to information, see [Create and apply information management policies](create-info-mgmt-policies.md).</span></span>
  
## <a name="features-of-information-management-policies"></a><span data-ttu-id="48647-109">정보 관리 정책의 기능</span><span class="sxs-lookup"><span data-stu-id="48647-109">Features of information management policies</span></span>
<span data-ttu-id="48647-110"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="48647-110"><a name="__top"> </a></span></span>

<span data-ttu-id="48647-111">조직에서 개별적으로 또는 조합하여 콘텐츠 및 프로세스를 관리하는 데 사용할 수 있는 미리 정의된 정책 기능의 기본 범주는 네 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="48647-111">There are four basic categories of predefined policy features that organizations can use individually or in combination to manage content and processes.</span></span> 
  
![콘텐츠 정책 유형](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
<span data-ttu-id="48647-113">감사 정책 기능은 조직에서 문서 및 목록 항목에 대해 수행되는 이벤트 및 작업을 로깅하여 콘텐츠 관리 시스템이 사용되는 방법을 분석하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48647-113">The Auditing policy feature helps organizations analyze how their content management systems are used by logging events and operations that are performed on documents and list items.</span></span> <span data-ttu-id="48647-114">감사 정책 기능을 구성하여 문서나 항목을 편집하거나, 보거나, 체크 인하거나, 체크 아웃하거나, 삭제하거나, 사용 권한이 변경된 경우와 같은 이벤트를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-114">You can configure the Auditing policy feature to log events such as when a document or item is edited, viewed, checked in, checked out, deleted, or has its permissions changed.</span></span> <span data-ttu-id="48647-115">모든 감사 정보는 서버의 단일 감사 로그에 저장되고 사이트 관리자는 이 로그에 대한 보고서를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-115">All of the audit information is stored in a single audit log on the server, and site administrators can run reports on it.</span></span> 
  
<span data-ttu-id="48647-116">만료 정책 기능을 사용하면 조직에서 일관되고 추적 가능한 방식으로 사이트에서 만료된 콘텐츠를 삭제하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-116">The Expiration policy feature helps organizations delete or remove out-of-date content from their sites in a consistent, trackable way.</span></span> <span data-ttu-id="48647-117">이렇게 하면 최신 콘텐츠 보존과 관련된 비용과 위험을 모두 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48647-117">This helps you manage both the cost and risk associated with retaining out-of-date content.</span></span> <span data-ttu-id="48647-118">만료 정책을 구성하여 특정 날짜 또는 문서를 만들거나 마지막으로 수정한 후 특정 기간 내에 특정 유형의 콘텐츠가 만료하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-118">You can configure an Expiration policy to specify that certain types of content expire on a particular date or within a period of time after the document was created or last modified.</span></span>
  
<span data-ttu-id="48647-119">조직에서 특정 필요에 맞는 사용자 지정 정책 기능을 만들어 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-119">Organizations can also create and deploy custom policy features to meet specific needs.</span></span> <span data-ttu-id="48647-120">예를 들어 제조 조직에서는 사용자가 비보안 프린터에서 이러한 문서의 복사본을 인쇄하지 못하게 하는 모든 초안 제품 디자인 사양 문서에 대한 정보 관리 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-120">For example, a manufacturing organization might want to define an information management policy for all draft product-design specification documents that prohibits users from printing copies of these documents on nonsecure printers.</span></span> <span data-ttu-id="48647-121">이러한 종류의 정보 관리 정책을 정의하기 위해 제품 디자인 사양 콘텐츠 형식에 대한 관련 정보 관리 정책에 추가할 수 있는 인쇄 제한 정책 기능을 만들고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-121">To define this kind of information management policy, you can create and deploy a Printing Restriction policy feature that can be added to the relevant information management policy for the product design specification content type.</span></span>
  
## <a name="locations-to-use-an-information-management-policy"></a><span data-ttu-id="48647-122">정보 관리 정책을 사용할 위치</span><span class="sxs-lookup"><span data-stu-id="48647-122">Locations to use an information management policy</span></span>
<span data-ttu-id="48647-123"><a name="__toc340213528"> </a></span><span class="sxs-lookup"><span data-stu-id="48647-123"><a name="__toc340213528"> </a></span></span>

<span data-ttu-id="48647-124">정보 관리 정책을 구현하려면 사이트의 목록, 라이브러리 또는 콘텐츠 형식에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48647-124">To implement an information management policy, you must add it to a list, library, or content type in a site.</span></span> <span data-ttu-id="48647-125">정보 관리 정책을 만들거나 추가하는 위치는 정책이 적용되는 범위나 정책의 사용 범위에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48647-125">The location where you create or add an information management policy affects how broadly the policy applies or how broadly it can be used.</span></span> <span data-ttu-id="48647-126">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-126">You can:</span></span>
  
 <span data-ttu-id="48647-127">사이트 모음 정책을 만든 다음 콘텐츠 형식, 목록 또는 라이브러리에 해당 정책을 **추가합니다.** 사이트 모음의 최상위 사이트에 있는 정책 목록에서 사이트 모음 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-127">**Create a site collection policy and then add this policy to a content type, list, or library** You can create a site collection policy in the Policies list in the top-level site of a site collection.</span></span> <span data-ttu-id="48647-128">사이트 모음 정책을 만든 후 다른 사이트 모음의 관리자가 정책 목록으로 가져올 수 있도록 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-128">After you create a site collection policy, you can export it so that administrators of other site collections can import it into their Policies list.</span></span> <span data-ttu-id="48647-129">내보낼 수 있는 사이트 모음 정책을 만들면 조직의 사이트 전체에서 정보 관리 정책을 표준화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-129">Creating an exportable site collection policy enables you to standardize the information management policies across the sites in your organization.</span></span> 
  
<span data-ttu-id="48647-130">사이트 콘텐츠 형식에 사이트 모음 정책을 추가하고 해당 사이트 콘텐츠 형식의 인스턴스를 목록 또는 라이브러리에 추가하면 해당 목록 또는 라이브러리의 소유자는 목록 또는 라이브러리에 대한 사이트 모음 정책을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-130">When you add a site collection policy to a site content type, and an instance of that site content type is added to a list or library, the owner of that list or library cannot modify the site collection policy for the list or library.</span></span> <span data-ttu-id="48647-131">사이트 콘텐츠 형식에 사이트 모음 정책을 추가하면 사이트 모음 정책이 사이트 계층 구조의 각 수준에서 적용되도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-131">Adding a site collection policy to a site content type is a good way to ensure that site collection policies are enforced at each level of your site hierarchy.</span></span>
  
![사이트 정책 페이지의 콘텐츠 형식 정책 설정 링크](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 <span data-ttu-id="48647-133">최상위 사이트의 사이트 콘텐츠 형식 갤러리에서 사이트 콘텐츠 형식에 대한 정보 관리 정책을 만든 다음 하나 이상의 목록 또는 라이브러리에 해당 콘텐츠 형식을 **추가합니다.** 사이트 콘텐츠 형식에 대해 직접 정보 관리 정책을 만든 다음 해당 사이트 콘텐츠 형식의 인스턴스를 여러 목록 또는 라이브러리에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="48647-133">**Create an information management policy for a site content type in the top-level site's Site Content Type Gallery, and then add that content type to one or more lists or libraries** You can also create an information management policy directly for a site content type and then associate an instance of that site content type with multiple lists or libraries.</span></span> <span data-ttu-id="48647-134">이러한 방식으로 정보 관리 정책을 만드는 경우 해당 콘텐츠 형식의 사이트 모음 또는 해당 콘텐츠 형식에서 상속되는 콘텐츠 형식의 모든 항목에 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-134">If you create an information management policy this way, every item in the site collection of that content type or a content type that inherits from that content type has the policy.</span></span> <span data-ttu-id="48647-135">그러나 사이트 콘텐츠 형식에 대해 직접 정보 관리 정책을 만드는 경우 이러한 방식으로 만든 정책을 내보낼 수 없는 다른 사이트 모음에서 이 정보 관리 정책을 다시 사용하기가 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-135">However, if you create an information management policy directly for a site content type, it is more difficult to reuse this information management policy in other site collections, because policies that are created this way cannot be exported.</span></span> 
  
![사이트 콘텐츠 형식 페이지의 사이트 설정 링크](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![사이트 콘텐츠 형식에 대한 설정 페이지의 정보 관리 정책 링크](../media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
<span data-ttu-id="48647-138">참고 사이트 모음에서 사용되는 정책을 제어하기 위해 사이트 모음 관리자는 콘텐츠 형식에 대해 직접 정책 기능을 설정하는 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-138">Note To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a content type.</span></span> <span data-ttu-id="48647-139">이 제한이 적용된 경우 콘텐츠 형식을 만드는 사용자는 사이트 모음 정책 목록에서 정책을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-139">When this restriction is in effect, users who create content types are limited to selecting policies from the site collection Policies list.</span></span>
  
 <span data-ttu-id="48647-140">**목록 또는 라이브러리에 대한 정보 관리 정책 만들기** 조직에서 매우 제한된 콘텐츠 집합에 특정 정보 관리 정책을 적용해야 하는 경우 개별 목록 또는 라이브러리에만 적용되는 정보 관리 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-140">**Create an information management policy for a list or library** If your organization needs to apply a specific information management policy to a very limited set of content, you can create an information management policy that applies only to an individual list or library.</span></span> <span data-ttu-id="48647-141">정보 관리 정책을 만드는 이 방법은 정책이 한 위치에만 적용될 뿐 다른 위치에 내보내거나 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-141">This method of creating an information management policy is the least flexible, because the policy applies only to one location, and it cannot be exported or reused for other locations.</span></span> <span data-ttu-id="48647-142">그러나 경우에 따라 특정 상황을 해결할 수 있는 제한된 적용성을 사용하여 고유한 정보 관리 정책을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-142">However, sometimes you may need to create unique information management policies with limited applicability to address specific situations.</span></span> 
  
![문서 라이브러리의 설정 페이지의 정보 관리 정책 링크](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
<span data-ttu-id="48647-144">메모</span><span class="sxs-lookup"><span data-stu-id="48647-144">Notes</span></span> 
  
<span data-ttu-id="48647-145">목록 또는 라이브러리가 여러 콘텐츠 형식을 지원하지 않는 경우 목록 또는 라이브러리에 대한 정보 관리 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-145">You can create an information management policy for a list or library only if that list or library does not support multiple content types.</span></span> <span data-ttu-id="48647-146">목록 또는 라이브러리에서 여러 콘텐츠 형식을 지원하는 경우 해당 목록 또는 라이브러리에 연결된 각 개별 목록 콘텐츠 형식에 대한 정보 관리 정책을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48647-146">If a list or library supports multiple content types, you need to define an information management policy for each individual list content type that is associated with that list or library.</span></span> <span data-ttu-id="48647-147">특정 목록 또는 라이브러리와 연결된 사이트 콘텐츠 형식의 인스턴스를 목록 콘텐츠 형식라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="48647-147">(Instances of a site content type that are associated with a specific list or library are known as list content types.)</span></span>
  
<span data-ttu-id="48647-148">사이트 모음에서 사용되는 정책을 제어하기 위해 사이트 모음 관리자는 목록 또는 라이브러리에 직접 정책 기능을 설정하는 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-148">To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a list or library.</span></span> <span data-ttu-id="48647-149">이 제한이 적용된 경우 목록 또는 라이브러리를 관리하는 사용자는 사이트 모음 정책 목록에서 정책을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48647-149">When this restriction is in effect, users who manage lists or libraries are limited to selecting policies from the site collection Policies list.</span></span>
  
[<span data-ttu-id="48647-150">정보 관리 정책은 콘텐츠 형식에 대한 규칙 집합입니다. 조직에서는 정보 관리 정책을 사용하여 콘텐츠가 보존되는 기간 또는 사용자가 해당 콘텐츠에 대해 수행할 수 있는 작업과 같은 작업을 제어하고 추적할 수 있습니다. 정보 관리 정책은 조직이 법률 또는 정부 규정을 준수하는 데 도움이 되거나 단순히 내부 비즈니스 프로세스를 적용할 수 있습니다. 예를 들어 재무 제표의 "적절한 제어"를 입증하도록 요구하는 정부 규정을 따라야 하는 조직은 재무 제표와 관련된 모든 문서의 제작 및 승인 프로세스에서 특정 작업을 감사하는 하나 이상의 정보 관리 정책을 만들 수 있습니다. 방법 정보는 정보 관리 정책 만들기 및 적용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48647-150">An information management policy is a set of rules for a type of content. Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content. Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes. For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.For how-to information, see Create and apply information management policies.</span></span>](intro-to-info-mgmt-policies.md#__top)
  

