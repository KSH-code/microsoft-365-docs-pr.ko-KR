---
title: 전자 메일 보호의 순서 및 우선 순위
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
description: 관리자는 EOP (Exchange Online Protection)의 보호에 대 한 응용 프로그램 순서와 보호 정책의 우선 순위 값이 적용 되는 정책을 결정 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 6b17a524fb9dfbf5e33604c2ec26a678befc8834
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600288"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="f8258-104">전자 메일 보호의 순서 및 우선 순위</span><span class="sxs-lookup"><span data-stu-id="f8258-104">Order and precedence of email protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f8258-105">Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (독립 실행형 Exchange Online 보호) 조직에서 인바운드 전자 메일에는 여러 가지 형식의 보호에 플래그가 지정 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="f8258-106">예를 들어 모든 Microsoft 365 고객이 사용할 수 있는 기본 제공 EOP 피싱 방지 정책과 Office 365 Advanced Threat Protection (Office 365 ATP) 고객 에게도 사용할 수 있는 더욱 견고한 ATP 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="f8258-106">For example, the built-in EOP anti-phishing policies that are available to all Microsoft 365 customers, and the more robust ATP anti-phishing policies that are also available to Office 365 Advanced Threat Protection (Office 365 ATP) customers.</span></span> <span data-ttu-id="f8258-107">또한 메시지는 맬웨어, 스팸, 피싱 등에 대해 여러 검색 검사를 통과 합니다. 이 모든 활동이 제공 되는 경우 적용 되는 정책과 같은 혼동이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="f8258-108">일반적으로 메시지에 적용 되는 정책은 **CAT (Category)** 속성의 **스팸 방지-Report** 헤더에서 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="f8258-109">자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8258-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="f8258-110">메시지에 적용 되는 정책을 결정 하는 두 가지 주요 요인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="f8258-111">**전자 메일 보호 유형의 우선 순위**:이 순서는 구성할 수 없으며 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="f8258-112">우선 순위</span><span class="sxs-lookup"><span data-stu-id="f8258-112">Priority</span></span>|<span data-ttu-id="f8258-113">전자 메일 보호</span><span class="sxs-lookup"><span data-stu-id="f8258-113">Email protection</span></span>|<span data-ttu-id="f8258-114">범주</span><span class="sxs-lookup"><span data-stu-id="f8258-114">Category</span></span>|<span data-ttu-id="f8258-115">관리할 위치</span><span class="sxs-lookup"><span data-stu-id="f8258-115">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="f8258-116">1 </span><span class="sxs-lookup"><span data-stu-id="f8258-116">1</span></span>|<span data-ttu-id="f8258-117">맬웨어</span><span class="sxs-lookup"><span data-stu-id="f8258-117">Malware</span></span>|<span data-ttu-id="f8258-118">CAT: MALW</span><span class="sxs-lookup"><span data-stu-id="f8258-118">CAT:MALW</span></span>|[<span data-ttu-id="f8258-119">EOP에서 맬웨어 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f8258-119">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="f8258-120">2</span><span class="sxs-lookup"><span data-stu-id="f8258-120">2</span></span>|<span data-ttu-id="f8258-121">피싱</span><span class="sxs-lookup"><span data-stu-id="f8258-121">Phishing</span></span>|<span data-ttu-id="f8258-122">CAT: PHSH</span><span class="sxs-lookup"><span data-stu-id="f8258-122">CAT:PHSH</span></span>|[<span data-ttu-id="f8258-123">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="f8258-123">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="f8258-124">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="f8258-124">3</span></span>|<span data-ttu-id="f8258-125">높은 정확도 스팸</span><span class="sxs-lookup"><span data-stu-id="f8258-125">High confidence spam</span></span>|<span data-ttu-id="f8258-126">CAT: HSPM</span><span class="sxs-lookup"><span data-stu-id="f8258-126">CAT:HSPM</span></span>|[<span data-ttu-id="f8258-127">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="f8258-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="f8258-128">4 </span><span class="sxs-lookup"><span data-stu-id="f8258-128">4</span></span>|<span data-ttu-id="f8258-129">스푸핑</span><span class="sxs-lookup"><span data-stu-id="f8258-129">Spoofing</span></span>|<span data-ttu-id="f8258-130">CAT: 스푸핑</span><span class="sxs-lookup"><span data-stu-id="f8258-130">CAT:SPOOF</span></span>|[<span data-ttu-id="f8258-131">EOP에서 스푸핑 인텔리전스 구성</span><span class="sxs-lookup"><span data-stu-id="f8258-131">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="f8258-132">2-5<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8258-132">5<sup>\*</sup></span></span>|<span data-ttu-id="f8258-133">사용자 가장 (보호 된 도메인)</span><span class="sxs-lookup"><span data-stu-id="f8258-133">User impersonation (protected domains)</span></span>|<span data-ttu-id="f8258-134">UIMP</span><span class="sxs-lookup"><span data-stu-id="f8258-134">UIMP</span></span>|[<span data-ttu-id="f8258-135">ATP 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f8258-135">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="f8258-136">번<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8258-136">6<sup>\*</sup></span></span>|<span data-ttu-id="f8258-137">도메인 가장 (보호 된 사용자)</span><span class="sxs-lookup"><span data-stu-id="f8258-137">Domain impersonation (protected users)</span></span>|<span data-ttu-id="f8258-138">DIMP</span><span class="sxs-lookup"><span data-stu-id="f8258-138">DIMP</span></span>|[<span data-ttu-id="f8258-139">ATP 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f8258-139">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="f8258-140">7 </span><span class="sxs-lookup"><span data-stu-id="f8258-140">7</span></span>|<span data-ttu-id="f8258-141">스팸</span><span class="sxs-lookup"><span data-stu-id="f8258-141">Spam</span></span>|<span data-ttu-id="f8258-142">CAT: SPM</span><span class="sxs-lookup"><span data-stu-id="f8258-142">CAT:SPM</span></span>|[<span data-ttu-id="f8258-143">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="f8258-143">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="f8258-144">8 </span><span class="sxs-lookup"><span data-stu-id="f8258-144">8</span></span>|<span data-ttu-id="f8258-145">대량</span><span class="sxs-lookup"><span data-stu-id="f8258-145">Bulk</span></span>|<span data-ttu-id="f8258-146">CAT: 대량</span><span class="sxs-lookup"><span data-stu-id="f8258-146">CAT:BULK</span></span>|[<span data-ttu-id="f8258-147">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="f8258-147">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |

  <span data-ttu-id="f8258-148"><sup>\*</sup> 이러한 기능은 ATP 피싱 방지 정책 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-148"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="f8258-149">**정책의 우선 순위**: 각 보호 유형 (스팸 방지, 맬웨어 방지, 피싱 방지 등)에 대해 모든 사용자에 게 적용 되는 기본 정책이 있지만 특정 사용자에 게 적용 되는 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="f8258-150">각 사용자 지정 정책에는 정책이 적용 되는 순서를 결정 하는 우선 순위 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="f8258-151">기본 정책은 항상 마지막으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="f8258-152">사용자가 같은 유형의 여러 정책에서 정의 된 경우에는 우선 순위가 가장 높은 정책만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="f8258-153">해당 유형의 나머지 정책은 사용자에 대해 평가 되지 않습니다 (기본 정책 포함).</span><span class="sxs-lookup"><span data-stu-id="f8258-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="f8258-154">예를 들어 **동일한 사용자에 게 적용 되**는 다음 ATP 피싱 방지 정책 및 사용자 가장 및 스푸핑으로 식별 되는 메시지를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-154">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="f8258-155">ATP 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="f8258-155">ATP anti-phishing policy</span></span>|<span data-ttu-id="f8258-156">우선 순위</span><span class="sxs-lookup"><span data-stu-id="f8258-156">Priority</span></span>|<span data-ttu-id="f8258-157">사용자 가장</span><span class="sxs-lookup"><span data-stu-id="f8258-157">User impersonation</span></span>|<span data-ttu-id="f8258-158">스푸핑 방지</span><span class="sxs-lookup"><span data-stu-id="f8258-158">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="f8258-159">정책 A</span><span class="sxs-lookup"><span data-stu-id="f8258-159">Policy A</span></span>|<span data-ttu-id="f8258-160">1 </span><span class="sxs-lookup"><span data-stu-id="f8258-160">1</span></span>|<span data-ttu-id="f8258-161">켜짐</span><span class="sxs-lookup"><span data-stu-id="f8258-161">On</span></span>|<span data-ttu-id="f8258-162">해제</span><span class="sxs-lookup"><span data-stu-id="f8258-162">Off</span></span>|
  |<span data-ttu-id="f8258-163">정책 B</span><span class="sxs-lookup"><span data-stu-id="f8258-163">Policy B</span></span>|<span data-ttu-id="f8258-164">2</span><span class="sxs-lookup"><span data-stu-id="f8258-164">2</span></span>|<span data-ttu-id="f8258-165">해제</span><span class="sxs-lookup"><span data-stu-id="f8258-165">Off</span></span>|<span data-ttu-id="f8258-166">켜짐</span><span class="sxs-lookup"><span data-stu-id="f8258-166">On</span></span>|
  |

1. <span data-ttu-id="f8258-167">스푸핑 우선 순위 (4)가 사용자 가장 (8) 보다 높기 때문에 메시지가 스푸핑로 표시 되 고 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="f8258-168">정책 A는 정책 B 보다 우선 순위가 높기 때문에 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="f8258-169">정책 A의 설정을 기반으로 하 여 스푸핑 방지 기능이 해제 되었기 때문에 메시지에 아무 작업도 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="f8258-170">정책 처리가 중지 되므로 정책 B는 사용자에 게 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="f8258-171">동일한 사용자가 같은 유형의 여러 사용자 지정 정책에 고의적으로 포함 될 수도 있으므로 사용자 지정 정책에 대 한 다음 디자인 지침을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="f8258-172">소수의 사용자에 게 적용 되는 정책에 더 높은 우선 순위를 할당 하 고 많은 사용자에 게 적용 되는 정책의 우선 순위를 낮춥니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="f8258-173">기본 정책은 항상 마지막에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="f8258-174">우선 순위가 낮은 정책 보다 더 엄격한 설정이 되도록 우선 순위가 높은 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8258-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="f8258-175">보다 짧은 사용자 지정 정책을 사용 하는 것이 좋습니다 (보다 엄격한 설정이 필요한 사용자에 대해서만 사용자 지정 정책 사용).</span><span class="sxs-lookup"><span data-stu-id="f8258-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
