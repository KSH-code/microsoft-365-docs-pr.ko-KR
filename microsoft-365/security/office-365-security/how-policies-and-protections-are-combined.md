---
title: Office 365의 전자 메일 보호 순서 및 우선 순위
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 보호의 응용 프로그램 순서와 보호 정책의 우선 순위 값이 적용 되는 정책을 결정 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: 6a95c59a5cd629b704753c6c05c9b8069d9240b1
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537416"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a><span data-ttu-id="96c9a-104">Office 365의 전자 메일 보호 순서 및 우선 순위</span><span class="sxs-lookup"><span data-stu-id="96c9a-104">Order and precedence of email protection in Office 365</span></span>

<span data-ttu-id="96c9a-105">Office 365에서 인바운드 전자 메일은로 평가 되며, 따라서 여러 형태의 보호 (맬웨어, 스팸, 피싱 등)에 의해 플래그가 지정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-105">In Office 365, inbound email is evaluated by, and therefore might be flagged by, multiple forms of protection (malware, spam, phishing, etc).</span></span> <span data-ttu-id="96c9a-106">이러한 모든 활동의 경우 적용 된 정책과 순서를 확인 하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-106">Given all of this activity, it can be hard to determine which policy was applied and in what order.</span></span>

<span data-ttu-id="96c9a-107">일반적으로 메시지에 적용 되는 정책은 **CAT (Category)** 속성의 **스팸 방지-Report** 헤더에서 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-107">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="96c9a-108">자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96c9a-108">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="96c9a-109">메시지에 적용 되는 정책을 결정 하는 두 가지 주요 요인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-109">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="96c9a-110">**전자 메일 보호 유형의 우선 순위**:이 순서는 구성할 수 없으며 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-110">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="96c9a-111">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="96c9a-111">**Priority**</span></span>|<span data-ttu-id="96c9a-112">**전자 메일 보호**</span><span class="sxs-lookup"><span data-stu-id="96c9a-112">**Email protection**</span></span>|<span data-ttu-id="96c9a-113">**범주**</span><span class="sxs-lookup"><span data-stu-id="96c9a-113">**Category**</span></span>|<span data-ttu-id="96c9a-114">**관리할 위치**</span><span class="sxs-lookup"><span data-stu-id="96c9a-114">**Where to manage**</span></span>|
  |<span data-ttu-id="96c9a-115">1 </span><span class="sxs-lookup"><span data-stu-id="96c9a-115">1</span></span>|<span data-ttu-id="96c9a-116">맬웨어</span><span class="sxs-lookup"><span data-stu-id="96c9a-116">Malware</span></span>|<span data-ttu-id="96c9a-117">CAT: MALW</span><span class="sxs-lookup"><span data-stu-id="96c9a-117">CAT:MALW</span></span>|[<span data-ttu-id="96c9a-118">Office 365에서 맬웨어 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="96c9a-118">Configure anti-malware policies in Office 365</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="96c9a-119">2 </span><span class="sxs-lookup"><span data-stu-id="96c9a-119">2</span></span>|<span data-ttu-id="96c9a-120">피싱</span><span class="sxs-lookup"><span data-stu-id="96c9a-120">Phishing</span></span>|<span data-ttu-id="96c9a-121">CAT: PHSH</span><span class="sxs-lookup"><span data-stu-id="96c9a-121">CAT:PHSH</span></span>|[<span data-ttu-id="96c9a-122">Office 365에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="96c9a-122">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="96c9a-123">3 </span><span class="sxs-lookup"><span data-stu-id="96c9a-123">3</span></span>|<span data-ttu-id="96c9a-124">높은 정확도 스팸</span><span class="sxs-lookup"><span data-stu-id="96c9a-124">High confidence spam</span></span>|<span data-ttu-id="96c9a-125">CAT: HSPM</span><span class="sxs-lookup"><span data-stu-id="96c9a-125">CAT:HSPM</span></span>|[<span data-ttu-id="96c9a-126">Office 365에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="96c9a-126">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="96c9a-127">4 </span><span class="sxs-lookup"><span data-stu-id="96c9a-127">4</span></span>|<span data-ttu-id="96c9a-128">스푸핑</span><span class="sxs-lookup"><span data-stu-id="96c9a-128">Spoofing</span></span>|<span data-ttu-id="96c9a-129">CAT: 스푸핑</span><span class="sxs-lookup"><span data-stu-id="96c9a-129">CAT:SPOOF</span></span>|[<span data-ttu-id="96c9a-130">Office 365에서 스푸핑 인텔리전스 구성</span><span class="sxs-lookup"><span data-stu-id="96c9a-130">Configure spoof intelligence in Office 365</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="96c9a-131">5 </span><span class="sxs-lookup"><span data-stu-id="96c9a-131">5</span></span>|<span data-ttu-id="96c9a-132">스팸</span><span class="sxs-lookup"><span data-stu-id="96c9a-132">Spam</span></span>|<span data-ttu-id="96c9a-133">CAT: SPM</span><span class="sxs-lookup"><span data-stu-id="96c9a-133">CAT:SPM</span></span>|[<span data-ttu-id="96c9a-134">Office 365에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="96c9a-134">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="96c9a-135">6 </span><span class="sxs-lookup"><span data-stu-id="96c9a-135">6</span></span>|<span data-ttu-id="96c9a-136">대량</span><span class="sxs-lookup"><span data-stu-id="96c9a-136">Bulk</span></span>|<span data-ttu-id="96c9a-137">CAT: 대량</span><span class="sxs-lookup"><span data-stu-id="96c9a-137">CAT:BULK</span></span>|[<span data-ttu-id="96c9a-138">Office 365에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="96c9a-138">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="96c9a-139">연중<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96c9a-139">7<sup>\*</sup></span></span>|<span data-ttu-id="96c9a-140">도메인 가장 (보호 된 사용자)</span><span class="sxs-lookup"><span data-stu-id="96c9a-140">Domain impersonation (protected users)</span></span>|<span data-ttu-id="96c9a-141">DIMP</span><span class="sxs-lookup"><span data-stu-id="96c9a-141">DIMP</span></span>|[<span data-ttu-id="96c9a-142">Office 365에서 ATP 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="96c9a-142">Configure ATP anti-phishing policies in Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="96c9a-143">8<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96c9a-143">8<sup>\*</sup></span></span>|<span data-ttu-id="96c9a-144">사용자 가장 (보호 된 도메인)</span><span class="sxs-lookup"><span data-stu-id="96c9a-144">User impersonation (protected domains)</span></span>|<span data-ttu-id="96c9a-145">UIMP</span><span class="sxs-lookup"><span data-stu-id="96c9a-145">UIMP</span></span>|[<span data-ttu-id="96c9a-146">Office 365에서 ATP 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="96c9a-146">Configure ATP anti-phishing policies in Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |

  <span data-ttu-id="96c9a-147"><sup>\*</sup>이러한 기능은 ATP 피싱 방지 정책 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-147"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="96c9a-148">**정책의 우선 순위**: 각 보호 유형 (스팸 방지, 맬웨어 방지, 피싱 방지 등)에 대해 모든 사용자에 게 적용 되는 기본 정책이 있지만 특정 사용자에 게 적용 되는 사용자 지정 정책을 종종 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-148">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can often create custom policies that apply to specific users.</span></span> <span data-ttu-id="96c9a-149">각 사용자 지정 정책에는 정책이 적용 되는 순서를 결정 하는 우선 순위 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-149">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="96c9a-150">기본 정책은 항상 마지막으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-150">The default policy is always applied last.</span></span>

  <span data-ttu-id="96c9a-151">사용자가 같은 유형의 여러 정책에서 정의 된 경우에는 우선 순위가 가장 높은 정책만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-151">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="96c9a-152">해당 유형의 나머지 정책은 사용자에 대해 평가 되지 않습니다 (기본 정책 포함).</span><span class="sxs-lookup"><span data-stu-id="96c9a-152">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="96c9a-153">예를 들어 **동일한 사용자에 게 적용 되**는 다음 ATP 피싱 방지 정책 및 사용자 가장 및 스푸핑으로 식별 되는 메시지를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-153">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="96c9a-154">**ATP 피싱 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="96c9a-154">**ATP anti-phishing policy**</span></span>|<span data-ttu-id="96c9a-155">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="96c9a-155">**Priority**</span></span>|<span data-ttu-id="96c9a-156">**사용자 가장**</span><span class="sxs-lookup"><span data-stu-id="96c9a-156">**User impersonation**</span></span>|<span data-ttu-id="96c9a-157">**스푸핑 방지**</span><span class="sxs-lookup"><span data-stu-id="96c9a-157">**Anti-spoofing**</span></span>|
  |<span data-ttu-id="96c9a-158">정책 A</span><span class="sxs-lookup"><span data-stu-id="96c9a-158">Policy A</span></span>|<span data-ttu-id="96c9a-159">1 </span><span class="sxs-lookup"><span data-stu-id="96c9a-159">1</span></span>|<span data-ttu-id="96c9a-160">켜짐</span><span class="sxs-lookup"><span data-stu-id="96c9a-160">On</span></span>|<span data-ttu-id="96c9a-161">해제</span><span class="sxs-lookup"><span data-stu-id="96c9a-161">Off</span></span>|
  |<span data-ttu-id="96c9a-162">정책 B</span><span class="sxs-lookup"><span data-stu-id="96c9a-162">Policy B</span></span>|<span data-ttu-id="96c9a-163">2 </span><span class="sxs-lookup"><span data-stu-id="96c9a-163">2</span></span>|<span data-ttu-id="96c9a-164">해제</span><span class="sxs-lookup"><span data-stu-id="96c9a-164">Off</span></span>|<span data-ttu-id="96c9a-165">켜짐</span><span class="sxs-lookup"><span data-stu-id="96c9a-165">On</span></span>|
  |

1. <span data-ttu-id="96c9a-166">스푸핑 우선 순위 (4)가 사용자 가장 (8) 보다 높기 때문에 메시지가 스푸핑로 표시 되 고 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-166">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="96c9a-167">정책 A는 정책 B 보다 우선 순위가 높기 때문에 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-167">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="96c9a-168">정책 A의 설정을 기반으로 하 여 스푸핑 방지 기능이 해제 되었기 때문에 메시지에 아무 작업도 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-168">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="96c9a-169">정책 처리가 중지 되므로 정책 B는 사용자에 게 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-169">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="96c9a-170">동일한 사용자가 같은 유형의 여러 사용자 지정 정책에 고의적으로 포함 될 수도 있으므로 사용자 지정 정책에 대 한 다음 디자인 지침을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-170">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="96c9a-171">소수의 사용자에 게 적용 되는 정책에 더 높은 우선 순위를 할당 하 고 많은 사용자에 게 적용 되는 정책의 우선 순위를 낮춥니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-171">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="96c9a-172">기본 정책은 항상 마지막에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-172">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="96c9a-173">우선 순위가 낮은 정책 보다 더 엄격한 설정이 되도록 우선 순위가 높은 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c9a-173">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="96c9a-174">보다 짧은 사용자 지정 정책을 사용 하는 것이 좋습니다 (보다 엄격한 설정이 필요한 사용자에 대해서만 사용자 지정 정책 사용).</span><span class="sxs-lookup"><span data-stu-id="96c9a-174">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
