---
title: Microsoft Managed Desktop 제품 수명 주기
description: 이 문서에는 Microsoft Managed Desktop에서 사용되는 장치 사양이 나열되어 있습니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75e6c2853a0ff41efdf7d5639f675927f3b95ea4
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841202"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="d91c3-104">Microsoft Managed Desktop 제품 수명 주기</span><span class="sxs-lookup"><span data-stu-id="d91c3-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="d91c3-105">Microsoft Managed Desktop은 항상 최상의 성능, 안정성, 디자인 및 보안 기능(예: Windows Hello와 같은 기능 지원)을 제공하는 장치를 사용하게 하여 사용자에게 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-105">Microsoft Managed Desktop benefits users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="d91c3-106">이를 위해 Microsoft Managed Desktop은 지속적으로 업데이트되는 승인된 장치의 짧은 [카탈로그를 유지 관리합니다.](device-list.md)</span><span class="sxs-lookup"><span data-stu-id="d91c3-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated [approved devices](device-list.md).</span></span> 
 
<span data-ttu-id="d91c3-107">이 문서에서는 디바이스가 승인된 카탈로그에서 추가 및 제거될 때의 장치 수명 주기에 대해 자세히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-107">This article details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="d91c3-108">이 항목에서는 "장치"과 "제품"을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-108">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="d91c3-109">"장치"는 한 개인의 특정 컴퓨터를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-109">By "device," we mean one individual, specific computer.</span></span> <span data-ttu-id="d91c3-110">예를 들어 "일련 번호 1234", "청구서 노트북", "공유 VM XYZ"는 특정 장치를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-110">For example, "Serial number 1234", "Bill's laptop", "Shared VM XYZ" refer to specific devices.</span></span> <span data-ttu-id="d91c3-111">그러나 "제품"은 디바이스 컬렉션 또는 패밀리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-111">A "product", however, refers to a collection or family of devices.</span></span> <span data-ttu-id="d91c3-112">예: "Fabrikam Laptop", "Adatum ZX450 Laptop" 등 이는 제품이 승인된 목록 [](device-list.md)또는 카탈로그에 추가되고 장치가 Microsoft Managed Desktop에 등록되는 것이기 때문에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-112">For example, "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. This is important because products are added to our [approved list](device-list.md), or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="d91c3-113">제품 수명 주기</span><span class="sxs-lookup"><span data-stu-id="d91c3-113">Product lifecycle</span></span>

 <span data-ttu-id="d91c3-114">일반적으로 제품은 이러한 수명 주기 단계를 통해 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-114">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="d91c3-115">제품 릴리스 및 평가</span><span class="sxs-lookup"><span data-stu-id="d91c3-115">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="d91c3-116">제품 기본 가용성 기간</span><span class="sxs-lookup"><span data-stu-id="d91c3-116">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="d91c3-117">제품 유예 기간</span><span class="sxs-lookup"><span data-stu-id="d91c3-117">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="d91c3-118">제품 사용 중지</span><span class="sxs-lookup"><span data-stu-id="d91c3-118">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="d91c3-119">이 그림은 전체 순서를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="d91c3-119">This illustration shows the entire sequence:</span></span>

![수명 주기 타임라인: 제품 일반 공급부터 "기본 가용성"은 2년 동안 지속됩니다.](../../media/non-dark1-edits.PNG)

<span data-ttu-id="d91c3-125">제품은 최대 24개월 동안 카탈로그에 남아 <em></em> 있지만 장치는 개별 등록 날짜에 따라 3년 동안 관리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-125">Products remain on the catalog for up to 24 months, but <em>devices</em> remain under management for three years based on their individual enrollment dates.</span></span> <span data-ttu-id="d91c3-126">사실, 각 제품에는 세 개의 중요한 날짜가 있지만 각 장치에는 하나의 중요한 날짜가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-126">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="d91c3-127">제품의 경우 이러한 세 날짜 모두 승인 <em></em>날짜에 따라 계산됩니다. 따라서 항상 제품의 전체 수명 주기에 대해 적절한 계획을 세우고 계획할 수 있도록 승인 시 이러한 날짜를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-127">For products, all three of these dates are calculated based on the <em>approval date</em>, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="d91c3-128">다음 표에는 다음과 같은 예제 날짜가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-128">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="d91c3-129">제품</span><span class="sxs-lookup"><span data-stu-id="d91c3-129">Product</span></span>  |<span data-ttu-id="d91c3-130">승인된 날짜</span><span class="sxs-lookup"><span data-stu-id="d91c3-130">Approved date</span></span>  |<span data-ttu-id="d91c3-131">기본 가용성 종료</span><span class="sxs-lookup"><span data-stu-id="d91c3-131">End of primary availability</span></span>  |<span data-ttu-id="d91c3-132">자격 종료</span><span class="sxs-lookup"><span data-stu-id="d91c3-132">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="d91c3-133">Fabrikam 노트북</span><span class="sxs-lookup"><span data-stu-id="d91c3-133">Fabrikam Laptop</span></span>    | <span data-ttu-id="d91c3-134">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="d91c3-134">1/1/2017</span></span> | <span data-ttu-id="d91c3-135">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="d91c3-135">6/1/2019</span></span> | <span data-ttu-id="d91c3-136">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="d91c3-136">6/1/2022</span></span> |
|<span data-ttu-id="d91c3-137">Adatum Laptop</span><span class="sxs-lookup"><span data-stu-id="d91c3-137">Adatum Laptop</span></span>   | <span data-ttu-id="d91c3-138">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="d91c3-138">1/1/2018</span></span> | <span data-ttu-id="d91c3-139">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="d91c3-139">6/1/2020</span></span> | <span data-ttu-id="d91c3-140">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="d91c3-140">6/1/2023</span></span>  |

<span data-ttu-id="d91c3-141">다음 표에는 다음과 같은 예제 날짜가 *표시됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d91c3-141">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="d91c3-142">장치 ID</span><span class="sxs-lookup"><span data-stu-id="d91c3-142">Device ID</span></span>  |<span data-ttu-id="d91c3-143">등록 날짜</span><span class="sxs-lookup"><span data-stu-id="d91c3-143">Enrollment date</span></span>  |<span data-ttu-id="d91c3-144">사용 중지 날짜</span><span class="sxs-lookup"><span data-stu-id="d91c3-144">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d91c3-145">노트북 #123412</span><span class="sxs-lookup"><span data-stu-id="d91c3-145">Laptop #123412</span></span>     |  <span data-ttu-id="d91c3-146">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="d91c3-146">2/3/2018</span></span>       |  <span data-ttu-id="d91c3-147">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="d91c3-147">2/3/2021</span></span>       |
|<span data-ttu-id="d91c3-148">데스크톱 #321513</span><span class="sxs-lookup"><span data-stu-id="d91c3-148">Desktop #321513</span></span>     | <span data-ttu-id="d91c3-149">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="d91c3-149">6/2/2018</span></span>        |  <span data-ttu-id="d91c3-150">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="d91c3-150">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="d91c3-151">제품 릴리스 및 평가</span><span class="sxs-lookup"><span data-stu-id="d91c3-151">Product release and evaluation</span></span>

<span data-ttu-id="d91c3-152">제조업체가 제품을 공개적으로 릴리스하면 제품 수명 주기가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-152">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![릴리스 및 평가 기간을 보여주는 수명 주기 타임라인](../../media/non-dark3-edits.PNG)

<span data-ttu-id="d91c3-154">이 단계에서는 Microsoft Managed Desktop 엔지니어링 팀이 제품을 평가하고 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-154">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="d91c3-155">팀에서는 Windows의 안정성 및 성능, 하드웨어 기준 준수, 시장 정서, 인벤토리 및 채널 준비와 같은 것을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-155">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="d91c3-156">이 프로세스는 일반적으로 약 6주가 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-156">This process typically takes approximately six weeks.</span></span>
  
<span data-ttu-id="d91c3-157">Microsoft Managed Desktop은 가용성이 처음 6개월 이내에 인증을 위한 장치만 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-157">Microsoft Managed Desktop will only evaluate devices for certification within their first six months of availability.</span></span> <span data-ttu-id="d91c3-158">이 정책은 최신 하드웨어에 대한 노력에 항상 집중할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-158">This policy ensures that we're always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="d91c3-159">이 단계가 끝나면 Microsoft Managed Desktop이 승인된 목록에 제품을 추가하여 효과적으로 고객 등록을 위한 제품을 출시합니다. [](device-list.md)</span><span class="sxs-lookup"><span data-stu-id="d91c3-159">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="d91c3-160">장치가 인증된 날짜에 관계없이 승인된  날짜는 제품의 일반 공급 날짜로 다시 날짜가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-160">Regardless of the date when a device is certified, its **approved date** is back-dated to the product's own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="d91c3-161">제품 기본 가용성 기간</span><span class="sxs-lookup"><span data-stu-id="d91c3-161">Product primary availability period</span></span>

<span data-ttu-id="d91c3-162">이 기간은 제품 가용성의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-162">This period is the core of product availability:</span></span>

![기본 가용성을 보여주는 수명 주기 타임라인](../../media/non-dark4-edits.PNG)

<span data-ttu-id="d91c3-164">이 기간 동안 등록된 모든 장치는 Microsoft Managed Desktop(파란색 타임라인 표시 막대에 표시)에서 3년 동안의 전체 지원을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-164">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="d91c3-165">이 기간은 종료 날짜가 일반 가용성 날짜로부터 24개월로 설정될 때까지 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-165">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="d91c3-166">이 기간을 효과적으로 "등록 열기"로 생각할 수 있으므로 Microsoft Managed Desktop의 가치를 최대화하기 위해 이 기간 내에 사용할 조달 모델 및 선택한 제품을 대상으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-166">You can think of this period as effectively "open enrollment", so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="d91c3-167">작은 예로, 기본 가용성의 마지막 달에 있는 제품을 사용하여 2년의 롤아웃 기간에 대한 정착을 피해야 합니다. 대부분의 장치는 Microsoft Managed Desktop 관리의 3년 전체를 받지 못합니다(자세한 내용은 유예 기간 참조). [](#product-grace-period)</span><span class="sxs-lookup"><span data-stu-id="d91c3-167">As a small example, you should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="d91c3-168">제품 유예 기간</span><span class="sxs-lookup"><span data-stu-id="d91c3-168">Product grace period</span></span>

<span data-ttu-id="d91c3-169">제품 유예 기간은 기본 가용성 이후 3년의 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-169">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="d91c3-170">이 단계를 통해 지원되는 제품 패밀리의 장치를 등록할 수 있지만 최신 하드웨어 및 장치 성능과 관련하여 Microsoft Managed Desktop의 약속을 지키고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-170">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="d91c3-171">이 단계는 Microsoft Managed Desktop에 대해 알기 전에 조달 결정을 내리는 고객에게 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-171">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="d91c3-172">Microsoft Managed Desktop에 등록하기 전에 최근에 승인된 장치를 구입한 경우 등록할 수 있지만 3년 동안의 관리 기간은 받지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-172">If you've recently bought approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won't receive a full three years of management.</span></span> <span data-ttu-id="d91c3-173">대신 등록한 날짜와 관계없이 사용 중지 날짜에 규정을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-173">Instead, they'll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="d91c3-174">Microsoft Managed Desktop은 이러한 장치를 기본 가용성의 마지막 날에 등록한 것으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-174">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="d91c3-175">이 그림에서는 등록 1년의 차이에도 불구하고 파란색 및 녹색 장치가 모두 같은 날에 종료된다고 하여 이 시나리오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-175">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![유예 기간을 표시하는 수명 주기 타임라인](../../media/non-dark2-edits.PNG)

<span data-ttu-id="d91c3-177">이전 표의 Fabrikam 노트북 예제에서는 이러한 상황을 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-177">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="d91c3-178">제품</span><span class="sxs-lookup"><span data-stu-id="d91c3-178">Product</span></span>  |<span data-ttu-id="d91c3-179">승인된 날짜</span><span class="sxs-lookup"><span data-stu-id="d91c3-179">Approved date</span></span>  |<span data-ttu-id="d91c3-180">기본 가용성 종료</span><span class="sxs-lookup"><span data-stu-id="d91c3-180">End of primary availability</span></span>  |<span data-ttu-id="d91c3-181">자격 종료</span><span class="sxs-lookup"><span data-stu-id="d91c3-181">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="d91c3-182">Fabrikam 노트북</span><span class="sxs-lookup"><span data-stu-id="d91c3-182">Fabrikam Laptop</span></span>    | <span data-ttu-id="d91c3-183">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="d91c3-183">6/1/2017</span></span> | <span data-ttu-id="d91c3-184">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="d91c3-184">6/1/2019</span></span> | <span data-ttu-id="d91c3-185">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="d91c3-185">6/1/2022</span></span> |

<span data-ttu-id="d91c3-186">고객은 2022년 6월 1일까지 Fabrikam 노트북을 등록할 수 있습니다. 그러나 모두 2019년 6월 1일에 등록한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-186">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="d91c3-187">2021년 6월 1일에 Fabrikam 노트북을 등록하면 1년의 관리만 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-187">If you enroll a Fabrikam Laptop on 6/1/2021, you'll only get one year of management.</span></span> <span data-ttu-id="d91c3-188">이 정책을 사용하면 새 장치를 조달하는 대신 이전에 지원했던 제품에서 부분 수명 주기를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-188">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="d91c3-189">마지막으로, 이 단계 동안 디바이스가 [](device-list.md) 장치 목록에서 제거되고 보관된 장치 [목록으로 이동됩니다.](archived-device-list.md)</span><span class="sxs-lookup"><span data-stu-id="d91c3-189">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="d91c3-190">제품 사용 중지</span><span class="sxs-lookup"><span data-stu-id="d91c3-190">Product retirement</span></span>

<span data-ttu-id="d91c3-191">제품 사용 중지는 수명 주기의 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-191">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="d91c3-192">이 단계에서는 해당 제품 유형의 새 장치를 Microsoft Managed Desktop에 등록할 수 없습니다. 정의에 따라 모든 기존 장치는 이제 허용되는 3년 기간을 밖에 습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-192">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="d91c3-193">이 시간 동안 Microsoft Managed Desktop은 디바이스를 공개 목록에서 완전히 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-193">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="d91c3-194">또한 이 단계에서는 아직 교체를 조달하지 않은 경우 Microsoft Managed Desktop이 규정을 준수하지 않는 디바이스에서 램프 다운을 시작하면 서비스 수가 낮아진 것이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-194">It's also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices that are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="d91c3-195">규정을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-195">Devices that are out of compliance</span></span>

<span data-ttu-id="d91c3-196">Microsoft Managed Desktop 관리에 허용된 창이 경과하면 장치가 규정을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-196">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="d91c3-197">이러한 상황은 장치가 3년의 관리에 도달하거나 해당 제품 유형이 장치 카탈로그에서 제거될 때 가장 먼저 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-197">This situation occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="d91c3-198">항상 조달 주기를 대상으로 지정하여 현재 장치가 규정을 준수하지 않을 경우 새 장치를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-198">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="d91c3-199">Microsoft Managed Desktop 팀은 장기 실행 예산에 대한 조달 주기가 길고 계획된 것을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-199">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="d91c3-200">장치 인구의 상태를 항상 인식할 수 있도록 관리되는 [](https://aka.ms/mmdportal) 모든 장치, 해당 연령 및 규정 준수 상태를 나열하는 웹 사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-200">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its age, and a status indicating its compliance.</span></span> <span data-ttu-id="d91c3-201">이 웹 사이트는 장치 사용 연령에 대한 최신 정보를 항상 사용할 수 있으며 모든 조달 계획 주기에서 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d91c3-201">The website helps you always have the latest information regarding device age and can use the report in any procurement planning cycle.</span></span> 







