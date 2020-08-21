---
title: 전자 메일 보호 순서 및 우선 순위
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)의 보호 순서와 보호 정책에서 의지 여부 값이 적용되는 정책을 결정하는 방법에 대해 학습할 수 있습니다.
ms.openlocfilehash: 9556d2262eb59224357e20027a1f0e63404081f2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827412"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="f44de-104">전자 메일 보호 순서 및 우선 순위</span><span class="sxs-lookup"><span data-stu-id="f44de-104">Order and precedence of email protection</span></span>

<span data-ttu-id="f44de-105">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 인바운드 전자 메일은 여러 형제 유형의 보호에 의해 플래그 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="f44de-106">예를 들어 모든 Microsoft 365 고객이 사용할 수 있는 기본 제공 EOP 피싱 방지 정책과 Office 365 ATP(Advanced Threat Protection) 고객에게 제공되는 더 강력한 ATP 피싱 방지 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-106">For example, the built-in EOP anti-phishing policies that are available to all Microsoft 365 customers, and the more robust ATP anti-phishing policies that are also available to Office 365 Advanced Threat Protection (Office 365 ATP) customers.</span></span> <span data-ttu-id="f44de-107">또한 메시지가 맬웨어, 스팸, 피싱 등에 대한 여러 탐지 검사를 통과합니다. 해당 활동이 모두 지정된 경우 어떤 정책이 적용되는지에 대해 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="f44de-108">일반적으로 메시지에 적용되는 정책은 **CAT(범주)** **속성의 X-Forefront-Antispam-Report** 헤더에서 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="f44de-109">자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f44de-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="f44de-110">메시지에 적용되는 정책을 결정할 때는 다음과 같은 두 가지 주요 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="f44de-111">**전자 메일 보호 유형의 우선순위:** 이 순서는 구성할 수 없습니다. 이 표는 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="f44de-112">우선 순위</span><span class="sxs-lookup"><span data-stu-id="f44de-112">Priority</span></span>|<span data-ttu-id="f44de-113">전자 메일 보호</span><span class="sxs-lookup"><span data-stu-id="f44de-113">Email protection</span></span>|<span data-ttu-id="f44de-114">범주</span><span class="sxs-lookup"><span data-stu-id="f44de-114">Category</span></span>|<span data-ttu-id="f44de-115">관리할 위치</span><span class="sxs-lookup"><span data-stu-id="f44de-115">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="f44de-116">1</span><span class="sxs-lookup"><span data-stu-id="f44de-116">1</span></span>|<span data-ttu-id="f44de-117">맬웨어</span><span class="sxs-lookup"><span data-stu-id="f44de-117">Malware</span></span>|<span data-ttu-id="f44de-118">CAT:MALW</span><span class="sxs-lookup"><span data-stu-id="f44de-118">CAT:MALW</span></span>|[<span data-ttu-id="f44de-119">EOP에서 맬웨어 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f44de-119">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="f44de-120">2</span><span class="sxs-lookup"><span data-stu-id="f44de-120">2</span></span>|<span data-ttu-id="f44de-121">피싱</span><span class="sxs-lookup"><span data-stu-id="f44de-121">Phishing</span></span>|<span data-ttu-id="f44de-122">CAT:PHSH</span><span class="sxs-lookup"><span data-stu-id="f44de-122">CAT:PHSH</span></span>|[<span data-ttu-id="f44de-123">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="f44de-123">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="f44de-124">3</span><span class="sxs-lookup"><span data-stu-id="f44de-124">3</span></span>|<span data-ttu-id="f44de-125">높은 정확도 스팸</span><span class="sxs-lookup"><span data-stu-id="f44de-125">High confidence spam</span></span>|<span data-ttu-id="f44de-126">CAT:HSPM</span><span class="sxs-lookup"><span data-stu-id="f44de-126">CAT:HSPM</span></span>|[<span data-ttu-id="f44de-127">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="f44de-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="f44de-128">4 </span><span class="sxs-lookup"><span data-stu-id="f44de-128">4</span></span>|<span data-ttu-id="f44de-129">스푸핑</span><span class="sxs-lookup"><span data-stu-id="f44de-129">Spoofing</span></span>|<span data-ttu-id="f44de-130">CAT:SPOOF</span><span class="sxs-lookup"><span data-stu-id="f44de-130">CAT:SPOOF</span></span>|[<span data-ttu-id="f44de-131">EOP에서 스푸핑 인텔리전스 구성</span><span class="sxs-lookup"><span data-stu-id="f44de-131">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="f44de-132">5 </span><span class="sxs-lookup"><span data-stu-id="f44de-132">5</span></span>|<span data-ttu-id="f44de-133">스팸</span><span class="sxs-lookup"><span data-stu-id="f44de-133">Spam</span></span>|<span data-ttu-id="f44de-134">CAT:SPM</span><span class="sxs-lookup"><span data-stu-id="f44de-134">CAT:SPM</span></span>|[<span data-ttu-id="f44de-135">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="f44de-135">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="f44de-136">6 </span><span class="sxs-lookup"><span data-stu-id="f44de-136">6</span></span>|<span data-ttu-id="f44de-137">대량</span><span class="sxs-lookup"><span data-stu-id="f44de-137">Bulk</span></span>|<span data-ttu-id="f44de-138">CAT:BULK</span><span class="sxs-lookup"><span data-stu-id="f44de-138">CAT:BULK</span></span>|[<span data-ttu-id="f44de-139">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="f44de-139">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="f44de-140">7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f44de-140">7<sup>\*</sup></span></span>|<span data-ttu-id="f44de-141">도메인 가장(보호된 사용자)</span><span class="sxs-lookup"><span data-stu-id="f44de-141">Domain impersonation (protected users)</span></span>|<span data-ttu-id="f44de-142">DIMP</span><span class="sxs-lookup"><span data-stu-id="f44de-142">DIMP</span></span>|[<span data-ttu-id="f44de-143">ATP 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f44de-143">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="f44de-144">8<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f44de-144">8<sup>\*</sup></span></span>|<span data-ttu-id="f44de-145">사용자 가장(보호된 도메인)</span><span class="sxs-lookup"><span data-stu-id="f44de-145">User impersonation (protected domains)</span></span>|<span data-ttu-id="f44de-146">UIMP</span><span class="sxs-lookup"><span data-stu-id="f44de-146">UIMP</span></span>|[<span data-ttu-id="f44de-147">ATP 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f44de-147">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |

  <span data-ttu-id="f44de-148"><sup>\*</sup> 이러한 기능은 ATP 피싱 방지 정책에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-148"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="f44de-149">**정책의 우선순위:** 각 보호 유형(스팸 방지, 맬웨어 방지, 피싱 등)에 대해, 모든 사용자에게 적용되는 기본 정책이 있지만, 특정 사용자에게 적용되는 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="f44de-150">각 사용자 지정 정책에는 정책이 적용되는 순서를 결정하는 우선 순위 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="f44de-151">기본 정책은 항상 마지막에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="f44de-152">사용자가 동일한 유형의 여러 정책에서 정의된 경우 우선 순위가 가장 높은 정책만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="f44de-153">해당 유형의 나머지 정책은 사용자에 대해 평가되지 않습니다(기본 정책 포함).</span><span class="sxs-lookup"><span data-stu-id="f44de-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="f44de-154">예를 들어 동일한 사용자에게 적용되는 다음과 같은 ATP 피싱 방지 **정책과**사용자 가장 및 스푸핑으로 식별되는 메시지를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="f44de-154">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="f44de-155">ATP 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="f44de-155">ATP anti-phishing policy</span></span>|<span data-ttu-id="f44de-156">우선 순위</span><span class="sxs-lookup"><span data-stu-id="f44de-156">Priority</span></span>|<span data-ttu-id="f44de-157">사용자 가장</span><span class="sxs-lookup"><span data-stu-id="f44de-157">User impersonation</span></span>|<span data-ttu-id="f44de-158">스푸핑 방지</span><span class="sxs-lookup"><span data-stu-id="f44de-158">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="f44de-159">정책 A</span><span class="sxs-lookup"><span data-stu-id="f44de-159">Policy A</span></span>|<span data-ttu-id="f44de-160">1</span><span class="sxs-lookup"><span data-stu-id="f44de-160">1</span></span>|<span data-ttu-id="f44de-161">켜짐</span><span class="sxs-lookup"><span data-stu-id="f44de-161">On</span></span>|<span data-ttu-id="f44de-162">해제</span><span class="sxs-lookup"><span data-stu-id="f44de-162">Off</span></span>|
  |<span data-ttu-id="f44de-163">정책 B</span><span class="sxs-lookup"><span data-stu-id="f44de-163">Policy B</span></span>|<span data-ttu-id="f44de-164">2</span><span class="sxs-lookup"><span data-stu-id="f44de-164">2</span></span>|<span data-ttu-id="f44de-165">해제</span><span class="sxs-lookup"><span data-stu-id="f44de-165">Off</span></span>|<span data-ttu-id="f44de-166">켜짐</span><span class="sxs-lookup"><span data-stu-id="f44de-166">On</span></span>|
  |

1. <span data-ttu-id="f44de-167">스푸핑의 우선 순위가 사용자 가장(8)보다 높기 때문에 메시지가 스푸핑으로 표시되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="f44de-168">정책 A는 정책 B보다 우선 순위가 높기 때문에 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="f44de-169">정책 A의 설정에 따라 정책에서 스푸핑 방지가 해제되므로 정책 A의 설정에 따라 메시지에 대해 아무 작업도 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="f44de-170">정책 처리가 중지되므로 정책 B가 사용자에게 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="f44de-171">같은 유형의 여러 사용자 지정 정책에 의도적으로 또는 의도적으로 같은 사용자가 포함될 수 있습니다. 사용자 지정 정책에 대해 다음 디자인 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f44de-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="f44de-172">소수의 사용자에게 적용할 수 높은 우선 순위를 할당하고 많은 수의 사용자에게 적용되는 정책에 낮은 우선 순위를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="f44de-173">기본 정책은 항상 마지막에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="f44de-174">우선 순위가 낮은 정책보다 우선 순위가 높은 정책을 더 전보다 또는 더 구체적으로 설정하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f44de-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="f44de-175">더 많은 사용자 지정 정책을 사용하는 것이 좋습니다(더 강격한 또는 보다 전화된 설정을 필요로 하는 사용자의 경우에만 사용자 지정 정책을 사용).</span><span class="sxs-lookup"><span data-stu-id="f44de-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
