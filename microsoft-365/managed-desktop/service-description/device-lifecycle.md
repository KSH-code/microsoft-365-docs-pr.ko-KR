---
title: Microsoft Managed Desktop 수명 주기
description: 이 문서에서는 디바이스 사양에 사용되는 장치 사양을 Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a8b8abc58b82d08d004d204396cfd8e381c6303a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245315"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="0ecd0-104">Microsoft Managed Desktop 수명 주기</span><span class="sxs-lookup"><span data-stu-id="0ecd0-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="0ecd0-105">Microsoft Managed Desktop 항상 최상의 성능, 안정성, 디자인 및 보안 기능을 제공하는 장치(예: Windows Hello와 같은 기능 지원)를 사용하게 하여 사용자에게 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-105">Microsoft Managed Desktop benefits users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="0ecd0-106">이를 위해 Microsoft Managed Desktop 업데이트된 장치의 짧은 카탈로그를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated approved devices.</span></span> <span data-ttu-id="0ecd0-107">비즈니스 디바이스 쇼핑 사이트에서 승인된 Microsoft Managed Desktop [필터링하여 Windows 10 Pro 수](https://www.microsoft.com/windowsforbusiness/view-all-devices) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-107">You can view approved devices by filtering for Microsoft Managed Desktop on the [Shop Windows 10 Pro business devices](https://www.microsoft.com/windowsforbusiness/view-all-devices) site.</span></span>
 
<span data-ttu-id="0ecd0-108">이 문서에서는 디바이스가 승인된 카탈로그에서 추가 및 제거될 때의 장치 수명 주기에 대해 자세히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-108">This article details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="0ecd0-109">이 항목에서는 "장치"와 "제품"을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-109">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="0ecd0-110">"장치"는 하나의 개별적인 특정 컴퓨터를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-110">By "device," we mean one individual, specific computer.</span></span> <span data-ttu-id="0ecd0-111">예를 들어 "일련 번호 1234", "청구서 노트북", "공유 VM XYZ"는 특정 장치를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-111">For example, "Serial number 1234", "Bill's laptop", "Shared VM XYZ" refer to specific devices.</span></span> <span data-ttu-id="0ecd0-112">그러나 "제품"은 디바이스의 컬렉션 또는 패밀리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-112">A "product", however, refers to a collection or family of devices.</span></span> <span data-ttu-id="0ecd0-113">예를 들어 "Fabrikam Laptop", "Adatum ZX450 Laptop" 등이 있습니다. 이는 제품이 승인된 목록 또는 카탈로그에 추가되는 것이고 장치가 해당 목록에 등록되는 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-113">For example, "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. This is important because products are added to our approved list, or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="0ecd0-114">제품 수명 주기</span><span class="sxs-lookup"><span data-stu-id="0ecd0-114">Product lifecycle</span></span>

 <span data-ttu-id="0ecd0-115">일반적으로 제품은 이러한 수명 주기 단계를 통해 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-115">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="0ecd0-116">제품 릴리스 및 평가</span><span class="sxs-lookup"><span data-stu-id="0ecd0-116">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="0ecd0-117">제품 기본 가용성 기간</span><span class="sxs-lookup"><span data-stu-id="0ecd0-117">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="0ecd0-118">제품 유예 기간</span><span class="sxs-lookup"><span data-stu-id="0ecd0-118">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="0ecd0-119">제품 사용 중지</span><span class="sxs-lookup"><span data-stu-id="0ecd0-119">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="0ecd0-120">이 그림은 전체 시퀀스를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="0ecd0-120">This illustration shows the entire sequence:</span></span>

![수명 주기 타임라인: 제품 일반 공급으로 시작하여 "기본 가용성"은 2년 동안 지속됩니다.](../../media/non-dark1-edits.PNG)

<span data-ttu-id="0ecd0-126">제품은 최대 24개월 동안 카탈로그에 남아 <em></em> 있지만 장치는 개별 등록 날짜에 따라 3년 동안 관리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-126">Products remain on the catalog for up to 24 months, but <em>devices</em> remain under management for three years based on their individual enrollment dates.</span></span> <span data-ttu-id="0ecd0-127">효과적으로 각 제품에는 세 개의 중요한 날짜가 있지만 각 장치에는 하나의 날짜만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-127">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="0ecd0-128">제품의 경우 이러한 세 날짜 모두 승인 <em></em>날짜에 따라 계산됩니다. 따라서 승인 시 이러한 날짜를 게시하여 제품의 전체 수명 주기에 대해 항상 적절하게 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-128">For products, all three of these dates are calculated based on the <em>approval date</em>, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="0ecd0-129">다음 표에서는 다음과 같은 예시적 제품의 날짜를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="0ecd0-129">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="0ecd0-130">제품</span><span class="sxs-lookup"><span data-stu-id="0ecd0-130">Product</span></span>  |<span data-ttu-id="0ecd0-131">승인된 날짜</span><span class="sxs-lookup"><span data-stu-id="0ecd0-131">Approved date</span></span>  |<span data-ttu-id="0ecd0-132">기본 가용성 종료</span><span class="sxs-lookup"><span data-stu-id="0ecd0-132">End of primary availability</span></span>  |<span data-ttu-id="0ecd0-133">자격 종료</span><span class="sxs-lookup"><span data-stu-id="0ecd0-133">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="0ecd0-134">Fabrikam 노트북</span><span class="sxs-lookup"><span data-stu-id="0ecd0-134">Fabrikam Laptop</span></span>    | <span data-ttu-id="0ecd0-135">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="0ecd0-135">1/1/2017</span></span> | <span data-ttu-id="0ecd0-136">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="0ecd0-136">6/1/2019</span></span> | <span data-ttu-id="0ecd0-137">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="0ecd0-137">6/1/2022</span></span> |
|<span data-ttu-id="0ecd0-138">Adatum 노트북</span><span class="sxs-lookup"><span data-stu-id="0ecd0-138">Adatum Laptop</span></span>   | <span data-ttu-id="0ecd0-139">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="0ecd0-139">1/1/2018</span></span> | <span data-ttu-id="0ecd0-140">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="0ecd0-140">6/1/2020</span></span> | <span data-ttu-id="0ecd0-141">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="0ecd0-141">6/1/2023</span></span>  |

<span data-ttu-id="0ecd0-142">다음 표에는 예시의학적 장치 날짜가 *표시됩니다.*</span><span class="sxs-lookup"><span data-stu-id="0ecd0-142">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="0ecd0-143">장치 ID</span><span class="sxs-lookup"><span data-stu-id="0ecd0-143">Device ID</span></span>  |<span data-ttu-id="0ecd0-144">등록 날짜</span><span class="sxs-lookup"><span data-stu-id="0ecd0-144">Enrollment date</span></span>  |<span data-ttu-id="0ecd0-145">사용 중지 날짜</span><span class="sxs-lookup"><span data-stu-id="0ecd0-145">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0ecd0-146">노트북 #123412</span><span class="sxs-lookup"><span data-stu-id="0ecd0-146">Laptop #123412</span></span>     |  <span data-ttu-id="0ecd0-147">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="0ecd0-147">2/3/2018</span></span>       |  <span data-ttu-id="0ecd0-148">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="0ecd0-148">2/3/2021</span></span>       |
|<span data-ttu-id="0ecd0-149">데스크톱 #321513</span><span class="sxs-lookup"><span data-stu-id="0ecd0-149">Desktop #321513</span></span>     | <span data-ttu-id="0ecd0-150">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="0ecd0-150">6/2/2018</span></span>        |  <span data-ttu-id="0ecd0-151">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="0ecd0-151">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="0ecd0-152">제품 릴리스 및 평가</span><span class="sxs-lookup"><span data-stu-id="0ecd0-152">Product release and evaluation</span></span>

<span data-ttu-id="0ecd0-153">제조업체가 제품을 공개적으로 릴리스하면 제품 수명 주기가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-153">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![릴리스 및 평가 기간을 보여주는 수명 주기 타임라인](../../media/non-dark3-edits.PNG)

<span data-ttu-id="0ecd0-155">이 단계에서는 Microsoft Managed Desktop 엔지니어링 팀이 제품의 평가 및 인증을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-155">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="0ecd0-156">이 팀은 특히 Windows 안정성 및 성능, 하드웨어 기준 준수, 시장 정서, 인벤토리 및 채널 준비를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-156">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="0ecd0-157">이 프로세스는 일반적으로 약 6주가 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-157">This process typically takes approximately six weeks.</span></span>
  
<span data-ttu-id="0ecd0-158">Microsoft Managed Desktop 처음 6개월 이내에 인증을 위한 장치만 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-158">Microsoft Managed Desktop will only evaluate devices for certification within their first six months of availability.</span></span> <span data-ttu-id="0ecd0-159">이 정책은 항상 최신 하드웨어 세대에 노력을 집중하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-159">This policy ensures that we're always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="0ecd0-160">이 단계가 끝나면 Microsoft Managed Desktop 목록에 제품을 추가하여 [](device-list.md)고객 등록을 위해 제품을 효과적으로 출시합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-160">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="0ecd0-161">장치가 인증된 날짜와 관계없이 승인된  날짜는 제품의 일반 공급 날짜로 다시 날짜가 정해진 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-161">Regardless of the date when a device is certified, its **approved date** is back-dated to the product's own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="0ecd0-162">제품 기본 가용성 기간</span><span class="sxs-lookup"><span data-stu-id="0ecd0-162">Product primary availability period</span></span>

<span data-ttu-id="0ecd0-163">이 기간은 제품 가용성의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-163">This period is the core of product availability:</span></span>

![기본 가용성을 보여주는 수명 주기 타임라인](../../media/non-dark4-edits.PNG)

<span data-ttu-id="0ecd0-165">이 기간 동안 등록된 모든 디바이스는 파란색 타임라인에 표시된 Microsoft Managed Desktop 3년의 전체 지원을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-165">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="0ecd0-166">이 기간은 종료 날짜가 일반 공급 날짜로부터 24개월로 설정될 때까지 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-166">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="0ecd0-167">이 기간을 효과적으로 "개방형 등록"으로 생각할 수 있으므로 Microsoft Managed Desktop 해당 기간 내에 사용할 조달 모델 및 선택한 제품을 대상으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-167">You can think of this period as effectively "open enrollment", so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="0ecd0-168">작은 예로, 기본 가용성의 마지막 달에 있는 제품을 사용하여 2년의 롤아웃 기간에 대한 정착을 피해야 합니다. 이러한 장치는 대부분 3년 동안의 Microsoft Managed Desktop 관리(자세한 내용은 유예 기간 참조)를 받지 못합니다. [](#product-grace-period)</span><span class="sxs-lookup"><span data-stu-id="0ecd0-168">As a small example, you should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="0ecd0-169">제품 유예 기간</span><span class="sxs-lookup"><span data-stu-id="0ecd0-169">Product grace period</span></span>

<span data-ttu-id="0ecd0-170">제품 유예 기간은 기본 가용성 이후 3년의 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-170">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="0ecd0-171">이 단계를 통해 지원되는 제품 패밀리의 장치를 등록할 수 있지만 최신 하드웨어 및 장치 성능과 관련하여 Microsoft Managed Desktop 약속을 지키고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-171">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="0ecd0-172">이 단계는 조달 결정을 내렸다가 구매 정보를 알고 있는 고객에게 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-172">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="0ecd0-173">Microsoft Managed Desktop 등록하기 전에 최근에 승인된 장치를 구입한 경우 등록할 수 있지만 3년 동안의 관리는 받지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-173">If you've recently bought approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won't receive a full three years of management.</span></span> <span data-ttu-id="0ecd0-174">대신 등록한 날짜와 관계없이 사용 중지 날짜에 규정을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-174">Instead, they'll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="0ecd0-175">숨은 Microsoft Managed Desktop 기본 가용성의 마지막 날에 등록된 장치처럼 이러한 장치를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-175">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="0ecd0-176">이 그림에서는 등록이 1년의 차이에도 불구하고 파란색 및 녹색 장치가 같은 날에 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-176">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![유예 기간을 표시하는 수명 주기 타임라인](../../media/non-dark2-edits.PNG)

<span data-ttu-id="0ecd0-178">이전 표의 Fabrikam 노트북 예제에서는 이러한 상황을 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-178">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="0ecd0-179">제품</span><span class="sxs-lookup"><span data-stu-id="0ecd0-179">Product</span></span>  |<span data-ttu-id="0ecd0-180">승인된 날짜</span><span class="sxs-lookup"><span data-stu-id="0ecd0-180">Approved date</span></span>  |<span data-ttu-id="0ecd0-181">기본 가용성 종료</span><span class="sxs-lookup"><span data-stu-id="0ecd0-181">End of primary availability</span></span>  |<span data-ttu-id="0ecd0-182">자격 종료</span><span class="sxs-lookup"><span data-stu-id="0ecd0-182">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="0ecd0-183">Fabrikam 노트북</span><span class="sxs-lookup"><span data-stu-id="0ecd0-183">Fabrikam Laptop</span></span>    | <span data-ttu-id="0ecd0-184">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="0ecd0-184">6/1/2017</span></span> | <span data-ttu-id="0ecd0-185">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="0ecd0-185">6/1/2019</span></span> | <span data-ttu-id="0ecd0-186">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="0ecd0-186">6/1/2022</span></span> |

<span data-ttu-id="0ecd0-187">고객은 2022년 6월 1일까지 Fabrikam 랩톱을 등록할 수 있습니다. 그러나 Fabrikam 노트북은 모두 2019년 6월 1일에 등록한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-187">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="0ecd0-188">2021년 6월 1일에 Fabrikam 노트북을 등록하는 경우 1년의 관리만 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-188">If you enroll a Fabrikam Laptop on 6/1/2021, you'll only get one year of management.</span></span> <span data-ttu-id="0ecd0-189">이 정책을 사용하면 새 장치를 조달하지 않고도 이전에 지원했던 제품에서 부분 수명 주기를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-189">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="0ecd0-190">마지막으로, 이 단계에서 장치는 장치 목록에서 제거되고 보관된 장치 [목록으로 이동됩니다.](archived-device-list.md) [](device-list.md)</span><span class="sxs-lookup"><span data-stu-id="0ecd0-190">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="0ecd0-191">제품 사용 중지</span><span class="sxs-lookup"><span data-stu-id="0ecd0-191">Product retirement</span></span>

<span data-ttu-id="0ecd0-192">제품 사용 중지는 수명 주기의 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-192">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="0ecd0-193">이 단계에서는 해당 제품 유형의 새 장치를 등록할 수 Microsoft Managed Desktop 정의에 따라 모든 기존 장치가 이제 허용된 3년 기간을 밖으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-193">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="0ecd0-194">이 시간 동안 Microsoft Managed Desktop 디바이스를 공개 목록에서 완전히 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-194">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="0ecd0-195">또한 이 단계에서는 아직 교체를 조달하지 않은 경우, Microsoft Managed Desktop 장치가 규정을 준수하지 않는 디바이스에서 램프다운을 시작하면 서비스 수가 밝아지기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-195">It's also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices that are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="0ecd0-196">규정을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-196">Devices that are out of compliance</span></span>

<span data-ttu-id="0ecd0-197">장치 관리에 허용된 창이 경과하면 장치가 Microsoft Managed Desktop 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-197">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="0ecd0-198">이러한 상황은 장치가 3년의 관리에 도달하거나 해당 제품 유형이 장치 카탈로그에서 제거될 때 가장 먼저 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-198">This situation occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="0ecd0-199">항상 조달 주기를 대상으로 하여 현재 장치가 규정을 준수하지 않을 수 있도록 새 장치를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-199">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="0ecd0-200">Microsoft Managed Desktop 팀에서는 조달 주기가 길고 장기 실행 예산에 대한 계획된 것을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-200">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="0ecd0-201">장치 인구의 상태를 항상 인식할 수 있도록 관리의 [](https://aka.ms/mmdportal) 모든 장치, 해당 연령 및 규정 준수를 나타내는 상태를 나열하는 웹 사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-201">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its age, and a status indicating its compliance.</span></span> <span data-ttu-id="0ecd0-202">이 웹 사이트는 장치 사용에 대한 최신 정보를 항상 확보할 수 있으며 모든 조달 계획 주기에서 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd0-202">The website helps you always have the latest information regarding device age and can use the report in any procurement planning cycle.</span></span> 







