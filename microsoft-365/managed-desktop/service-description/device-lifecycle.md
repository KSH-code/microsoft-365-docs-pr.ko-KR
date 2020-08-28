---
title: Microsoft Managed Desktop 제품 수명 주기
description: 이 항목에는 Microsoft Managed Desktop에서 사용 되는 장치 사양이 나와 있습니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 89dbf0e67c112743a557842bb32555d3a079743b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289796"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="eeeb7-104">Microsoft Managed Desktop 제품 수명 주기</span><span class="sxs-lookup"><span data-stu-id="eeeb7-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="eeeb7-105">Microsoft Managed Desktop 이점은 사용자가 항상 최상의 성능, 안정성, 디자인 및 보안 기능을 제공 하는 장치 (예: Windows Hello와 같은 기능 지원)를 사용 하는 것을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-105">Microsoft Managed Desktop benefits users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="eeeb7-106">이 작업을 수행 하기 위해 Microsoft Managed Desktop은 [승인 된 장치](device-list.md)를 지속적으로 업데이트 하는 짧은 카탈로그를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated [approved devices](device-list.md).</span></span> 
 
<span data-ttu-id="eeeb7-107">이 항목에서는 승인 된 카탈로그에서 장치가 추가 되거나 제거 될 때의 장치 수명 주기에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-107">This topic details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="eeeb7-108">이 항목에서는 "장치"와 "제품"을 구별 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-108">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="eeeb7-109">"장치"에서는 개별 컴퓨터를 하나씩만 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-109">By "device," we mean one individual, specific computer.</span></span> <span data-ttu-id="eeeb7-110">예를 들어 "일련 번호 1234", "청구서의 랩톱", "공유 VM XYZ"는 특정 장치를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-110">For example, "Serial number 1234", "Bill's laptop", "Shared VM XYZ" refer to specific devices.</span></span> <span data-ttu-id="eeeb7-111">그러나 "제품" 이란 모음 또는 장치 패밀리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-111">A "product", however, refers to a collection or family of devices.</span></span> <span data-ttu-id="eeeb7-112">예를 들어 "Fabrikam 랩탑", "Adatum ZX450 랩탑을" 등을 들 있습니다. 제품은 [승인 된 목록](device-list.md)또는 카탈로그에 추가 되 고 장치는 Microsoft Managed Desktop에 등록 되기 때문에 중요 한 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-112">For example, "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. This is important because products are added to our [approved list](device-list.md), or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="eeeb7-113">제품 수명 주기</span><span class="sxs-lookup"><span data-stu-id="eeeb7-113">Product lifecycle</span></span>

 <span data-ttu-id="eeeb7-114">일반적으로 제품은 다음 수명 주기 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-114">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="eeeb7-115">제품 릴리스 및 평가</span><span class="sxs-lookup"><span data-stu-id="eeeb7-115">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="eeeb7-116">제품 기본 가용성 기간</span><span class="sxs-lookup"><span data-stu-id="eeeb7-116">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="eeeb7-117">제품 유예 기간</span><span class="sxs-lookup"><span data-stu-id="eeeb7-117">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="eeeb7-118">제품 폐기</span><span class="sxs-lookup"><span data-stu-id="eeeb7-118">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="eeeb7-119">다음 그림에서는 전체 시퀀스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-119">This illustration shows the entire sequence:</span></span>

![수명 주기 시간 표시 막대: 제품 일반 가용성부터 시작 하 여 "기본 가용성"은 2 년 동안 지속 됩니다.](../../media/non-dark1-edits.PNG)

<span data-ttu-id="eeeb7-125">제품은 최대 24 개월 동안 카탈로그에 유지 되지만 <em>장치</em> 는 개별 등록 날짜에 따라 3 년 동안 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-125">Products remain on the catalog for up to 24 months, but <em>devices</em> remain under management for 3 years based on their individual enrollment dates.</span></span> <span data-ttu-id="eeeb7-126">실제로 각 제품에는 세 가지 중요 한 날짜가 있지만 각 장치에는 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-126">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="eeeb7-127">제품의 경우 이러한 날짜 중 세 가지는 <em>승인 날짜</em>를 기준으로 계산 되므로 언제 든 지 승인 시에 해당 날짜를 게시 하 여 제품의 전체 수명 주기에 적절 하 게 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-127">For products, all three of these dates are calculated based on the <em>approval date</em>, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="eeeb7-128">이 표에서는 이론적인 제품의 예제 날짜를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-128">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="eeeb7-129">제품</span><span class="sxs-lookup"><span data-stu-id="eeeb7-129">Product</span></span>  |<span data-ttu-id="eeeb7-130">승인 날짜</span><span class="sxs-lookup"><span data-stu-id="eeeb7-130">Approved date</span></span>  |<span data-ttu-id="eeeb7-131">기본 가용성 종료</span><span class="sxs-lookup"><span data-stu-id="eeeb7-131">End of primary availability</span></span>  |<span data-ttu-id="eeeb7-132">자격의 끝</span><span class="sxs-lookup"><span data-stu-id="eeeb7-132">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="eeeb7-133">Fabrikam 랩톱</span><span class="sxs-lookup"><span data-stu-id="eeeb7-133">Fabrikam Laptop</span></span>    | <span data-ttu-id="eeeb7-134">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="eeeb7-134">1/1/2017</span></span> | <span data-ttu-id="eeeb7-135">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="eeeb7-135">6/1/2019</span></span> | <span data-ttu-id="eeeb7-136">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="eeeb7-136">6/1/2022</span></span> |
|<span data-ttu-id="eeeb7-137">Adatum 랩톱</span><span class="sxs-lookup"><span data-stu-id="eeeb7-137">Adatum Laptop</span></span>   | <span data-ttu-id="eeeb7-138">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="eeeb7-138">1/1/2018</span></span> | <span data-ttu-id="eeeb7-139">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="eeeb7-139">6/1/2020</span></span> | <span data-ttu-id="eeeb7-140">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="eeeb7-140">6/1/2023</span></span>  |

<span data-ttu-id="eeeb7-141">다음 표에는 이론적인 *장치*에 대 한 예제 날짜가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-141">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="eeeb7-142">장치 ID</span><span class="sxs-lookup"><span data-stu-id="eeeb7-142">Device ID</span></span>  |<span data-ttu-id="eeeb7-143">등록 날짜</span><span class="sxs-lookup"><span data-stu-id="eeeb7-143">Enrollment date</span></span>  |<span data-ttu-id="eeeb7-144">퇴직 날짜</span><span class="sxs-lookup"><span data-stu-id="eeeb7-144">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="eeeb7-145">랩탑 #123412</span><span class="sxs-lookup"><span data-stu-id="eeeb7-145">Laptop #123412</span></span>     |  <span data-ttu-id="eeeb7-146">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="eeeb7-146">2/3/2018</span></span>       |  <span data-ttu-id="eeeb7-147">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="eeeb7-147">2/3/2021</span></span>       |
|<span data-ttu-id="eeeb7-148">데스크톱 #321513</span><span class="sxs-lookup"><span data-stu-id="eeeb7-148">Desktop #321513</span></span>     | <span data-ttu-id="eeeb7-149">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="eeeb7-149">6/2/2018</span></span>        |  <span data-ttu-id="eeeb7-150">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="eeeb7-150">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="eeeb7-151">제품 릴리스 및 평가</span><span class="sxs-lookup"><span data-stu-id="eeeb7-151">Product release and evaluation</span></span>

<span data-ttu-id="eeeb7-152">제품 수명 주기는 제조업체에서 제품을 공개적으로 출시할 때 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-152">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![릴리스 및 평가 기간을 보여 주는 수명 주기 시간 표시줄](../../media/non-dark3-edits.PNG)

<span data-ttu-id="eeeb7-154">이 단계에서 Microsoft Managed Desktop 공학적 팀은 제품의 평가 및 인증을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-154">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="eeeb7-155">이 팀은 기타 다양 한 작업 중에 Windows와의 안정성 및 성능 (하드웨어 기준선, 시장 sentiment 및 재고 및 채널 준비 상태)과 같은 사항을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-155">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="eeeb7-156">이 프로세스는 보통 6 주 정도 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-156">This process typically takes approximately 6 weeks.</span></span>
  
<span data-ttu-id="eeeb7-157">Microsoft Managed Desktop은 처음 6 개월 이내에 인증 장치를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-157">Microsoft Managed Desktop will only evaluate devices for certification within their first 6 months of availability.</span></span> <span data-ttu-id="eeeb7-158">이렇게 하면 항상 최신 하드웨어 세대에 초점을 맞추어 작업을 진행 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-158">This ensures that we're always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="eeeb7-159">이 단계를 완료 하면 Microsoft Managed Desktop이 제품을 [승인 된 목록](device-list.md)에 추가 하 여 고객 enrollments 제품을 효과적으로 출시 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-159">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="eeeb7-160">장치가 인증 된 날짜에 관계 없이 해당 **승인 된 날짜** 는 제품의 일반 사용 가능 날짜에 따라 다시 날짜가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-160">Regardless of the date when a device is certified, its **approved date** is back-dated to the product's own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="eeeb7-161">제품 기본 가용성 기간</span><span class="sxs-lookup"><span data-stu-id="eeeb7-161">Product primary availability period</span></span>

<span data-ttu-id="eeeb7-162">이 기간은 제품 가용성의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-162">This period is the core of product availability:</span></span>

![기본 가용성을 보여 주는 수명 주기 시간 표시줄](../../media/non-dark4-edits.PNG)

<span data-ttu-id="eeeb7-164">이 기간 중에 등록 된 모든 장치에는 Microsoft Managed Desktop (파란색 시간 표시 막대)에서 지원 되는 3 년간의 모든 지원이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-164">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="eeeb7-165">이 기간은 일반 사용 가능 날짜 로부터 24 개월 후로 설정 될 때까지 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-165">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="eeeb7-166">이 기간을 "열기 등록"으로 간주할 수 있으므로 Microsoft Managed Desktop의 값을 최대화 하려면 조달 모델을 대상으로 하 고 선택한 제품을이 기간 내에 포함 하도록 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-166">You can think of this period as effectively "open enrollment", so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="eeeb7-167">예를 들어 고객은 기본 가용성의 마지막 달에 해당 하는 제품을 사용 하 여 2 년간의 settling을 방지 해야 하며, 이러한 장치 대부분은 Microsoft Managed 데스크톱 관리의 최대 3 년간 수신 되지 않습니다 (자세한 내용은 [유예 기간](#product-grace-period) 참조).</span><span class="sxs-lookup"><span data-stu-id="eeeb7-167">As a small example, a customer should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="eeeb7-168">제품 유예 기간</span><span class="sxs-lookup"><span data-stu-id="eeeb7-168">Product grace period</span></span>

<span data-ttu-id="eeeb7-169">제품 유예 기간은 기본 가용성을 따라 3 년 동안 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-169">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="eeeb7-170">이 단계를 통해 지원 되는 제품군의 장치를 등록할 수 있지만 아직까지 Microsoft Managed Desktop을 보유 하 고 있는 하드웨어 및 장치 성능에 대 한 준비가 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-170">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="eeeb7-171">이 단계는 Microsoft Managed Desktop에 대 한 정보를 파악 하기 전에 조달 의사 결정을 내리는 고객에 게 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-171">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="eeeb7-172">Microsoft Managed Desktop에 등록 하기 전에 최근 많은 수의 승인 된 장치를 구매한 경우에도 등록할 수는 있지만, 3 년간의 관리 작업을 받을 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-172">If you've recently bought a number of approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won't receive a full three years of management.</span></span> <span data-ttu-id="eeeb7-173">대신, 등록 시기에 관계 없이 만료 날짜가 준수 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-173">Instead, they'll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="eeeb7-174">Microsoft Managed Desktop은 내부적으로 이러한 장치를 기본 가용성의 마지막 날에 등록 한 것 처럼 취급 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-174">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="eeeb7-175">이 그림에서 이러한 시나리오는 다음과 같이 파란색 및 녹색 장치가 모두 같은 날에 종료 된다는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-175">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![유예 기간을 보여 주는 수명 주기 시간 표시줄](../../media/non-dark2-edits.PNG)

<span data-ttu-id="eeeb7-177">위 표에서 Fabrikam 랩톱 예제에는 다음과 같은 상황이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-177">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="eeeb7-178">제품</span><span class="sxs-lookup"><span data-stu-id="eeeb7-178">Product</span></span>  |<span data-ttu-id="eeeb7-179">승인 날짜</span><span class="sxs-lookup"><span data-stu-id="eeeb7-179">Approved date</span></span>  |<span data-ttu-id="eeeb7-180">기본 가용성 종료</span><span class="sxs-lookup"><span data-stu-id="eeeb7-180">End of primary availability</span></span>  |<span data-ttu-id="eeeb7-181">자격의 끝</span><span class="sxs-lookup"><span data-stu-id="eeeb7-181">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="eeeb7-182">Fabrikam 랩톱</span><span class="sxs-lookup"><span data-stu-id="eeeb7-182">Fabrikam Laptop</span></span>    | <span data-ttu-id="eeeb7-183">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="eeeb7-183">6/1/2017</span></span> | <span data-ttu-id="eeeb7-184">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="eeeb7-184">6/1/2019</span></span> | <span data-ttu-id="eeeb7-185">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="eeeb7-185">6/1/2022</span></span> |

<span data-ttu-id="eeeb7-186">고객은 6/1/2022까지 모든 방식으로 Fabrikam 랩톱을 등록할 수 있지만,이를 6/1/2019에 등록 한 것 처럼 취급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-186">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="eeeb7-187">Fabrikam 랩톱을 6/1/2021에 등록 하는 경우 1 년의 관리 작업만 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-187">If you enroll a Fabrikam Laptop on 6/1/2021 you'll only get one year of management.</span></span> <span data-ttu-id="eeeb7-188">이 정책을 사용 하면 이전에 지원 했던 제품에서 부분 생명주을 추출할 수 있으며, 이러한 기능은 새로운 장치를 조기에 조달 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-188">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="eeeb7-189">마지막으로이 단계에서는 장치가 [장치 목록](device-list.md) 에서 제거 되 고 [보관 된 장치 목록](archived-device-list.md)으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-189">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="eeeb7-190">제품 폐기</span><span class="sxs-lookup"><span data-stu-id="eeeb7-190">Product retirement</span></span>

<span data-ttu-id="eeeb7-191">제품 폐기는 주기의 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-191">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="eeeb7-192">이 단계에서는 해당 제품 유형의 새 장치를 Microsoft Managed Desktop에 등록할 수 없으며, 정의에 따라 모든 기존 장치가 허용 되는 3 년의 범위를 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-192">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="eeeb7-193">이 기간 동안 Microsoft Managed Desktop은 공용 목록에서 장치를 완전히 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-193">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="eeeb7-194">또한이 단계에서 아직 교체를 확보 하지 않은 경우에는 Microsoft Managed Desktop이 준수 하지 않는 장치에서 아래로 진입 하기 시작 하면 저하 된 서비스가 표시 되기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-194">It's also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices which are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="eeeb7-195">규정을 준수 하지 않는 장치</span><span class="sxs-lookup"><span data-stu-id="eeeb7-195">Devices that are out of compliance</span></span>

<span data-ttu-id="eeeb7-196">Microsoft Managed Desktop management에 허용 된 창이 경과 하면 장치가 준수 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-196">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="eeeb7-197">장치가 3 년 동안 관리 되거나 해당 제품 유형이 장치 카탈로그에서 제거 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-197">This occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="eeeb7-198">현재 장치에 대 한 준수를 중단 하기 전에 새 장치를 배포 하는 것과 같은 조달 주기를 항상 대상으로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-198">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="eeeb7-199">Microsoft Managed Desktop 팀은 조달 주기가 길고 장기간 실행 되는 예산을 중심으로 계획 되는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-199">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="eeeb7-200">장치 채우기의 상태를 항상 확인 하려면 관리 되는 모든 장치, 해당 보존 기간 및 준수를 나타내는 상태를 나열 하는 [웹 사이트](https://aka.ms/mmdportal) 를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-200">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its age, and a status indicating its compliance.</span></span> <span data-ttu-id="eeeb7-201">즉, 항상 장치 보존 기간에 대 한 최신 정보가 있으며, 모든 조달 계획 주기에서이 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeb7-201">This means you always have the latest information regarding device age and can use the report in any procurement planning cycle.</span></span> 







