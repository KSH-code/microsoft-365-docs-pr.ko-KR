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
description: 관리자는 EOP(Exchange Online Protection)의 보호 응용 프로그램 순서와 보호 정책의 우선 순위 값이 적용되는 정책을 결정하는 방법을 알 수 있습니다.
ms.openlocfilehash: a18234344e1100f3b6a03c10e970c8195e53e7df
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760569"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="fc68a-104">전자 메일 보호의 순서 및 우선 순위</span><span class="sxs-lookup"><span data-stu-id="fc68a-104">Order and precedence of email protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fc68a-105">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 인바운드 전자 메일은 여러 형태의 보호로 플래그가 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="fc68a-106">예를 들어 모든 Microsoft 365 고객이 사용할 수 있는 EOP의 기본 제공 피싱 방지 정책과 Office 365 고객용 Microsoft Defender에서 사용할 수 있는 보다 강력한 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-106">For example, the built-in anti-phishing policies in EOP that are available to all Microsoft 365 customers, and the more robust anti-phishing policies that are available to Microsoft Defender for Office 365 customers.</span></span> <span data-ttu-id="fc68a-107">또한 메시지는 맬웨어, 스팸, 피싱 등에 대한 여러 검색 검색을 통과합니다. 이 모든 활동이 제공될 경우 어떤 정책이 적용되는지 혼동될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="fc68a-108">일반적으로 메시지에 적용되는 정책은 **CAT(범주)** 속성의 **X-Forefront-Antispam-Report** 헤더에서 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="fc68a-109">자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc68a-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="fc68a-110">메시지에 적용되는 정책을 결정하는 주요 요인에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="fc68a-111">**전자 메일 보호** 유형의 우선 순위: 이 순서는 구성할 수 없습니다. 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="fc68a-112">우선 순위</span><span class="sxs-lookup"><span data-stu-id="fc68a-112">Priority</span></span>|<span data-ttu-id="fc68a-113">전자 메일 보호</span><span class="sxs-lookup"><span data-stu-id="fc68a-113">Email protection</span></span>|<span data-ttu-id="fc68a-114">범주</span><span class="sxs-lookup"><span data-stu-id="fc68a-114">Category</span></span>|<span data-ttu-id="fc68a-115">관리 위치</span><span class="sxs-lookup"><span data-stu-id="fc68a-115">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="fc68a-116">1 </span><span class="sxs-lookup"><span data-stu-id="fc68a-116">1</span></span>|<span data-ttu-id="fc68a-117">맬웨어</span><span class="sxs-lookup"><span data-stu-id="fc68a-117">Malware</span></span>|<span data-ttu-id="fc68a-118">CAT:MALW</span><span class="sxs-lookup"><span data-stu-id="fc68a-118">CAT:MALW</span></span>|[<span data-ttu-id="fc68a-119">EOP에서 맬웨어 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="fc68a-119">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="fc68a-120">2 </span><span class="sxs-lookup"><span data-stu-id="fc68a-120">2</span></span>|<span data-ttu-id="fc68a-121">피싱</span><span class="sxs-lookup"><span data-stu-id="fc68a-121">Phishing</span></span>|<span data-ttu-id="fc68a-122">CAT:PHSH</span><span class="sxs-lookup"><span data-stu-id="fc68a-122">CAT:PHSH</span></span>|[<span data-ttu-id="fc68a-123">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="fc68a-123">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="fc68a-124">3 </span><span class="sxs-lookup"><span data-stu-id="fc68a-124">3</span></span>|<span data-ttu-id="fc68a-125">높은 정확도 스팸</span><span class="sxs-lookup"><span data-stu-id="fc68a-125">High confidence spam</span></span>|<span data-ttu-id="fc68a-126">CAT:HSPM</span><span class="sxs-lookup"><span data-stu-id="fc68a-126">CAT:HSPM</span></span>|[<span data-ttu-id="fc68a-127">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="fc68a-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="fc68a-128">4 </span><span class="sxs-lookup"><span data-stu-id="fc68a-128">4</span></span>|<span data-ttu-id="fc68a-129">스푸핑</span><span class="sxs-lookup"><span data-stu-id="fc68a-129">Spoofing</span></span>|<span data-ttu-id="fc68a-130">CAT:스푸핑</span><span class="sxs-lookup"><span data-stu-id="fc68a-130">CAT:SPOOF</span></span>|[<span data-ttu-id="fc68a-131">EOP에서 스푸핑 인텔리전스 구성</span><span class="sxs-lookup"><span data-stu-id="fc68a-131">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="fc68a-132">5<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fc68a-132">5<sup>\*</sup></span></span>|<span data-ttu-id="fc68a-133">사용자 가장(보호된 사용자)</span><span class="sxs-lookup"><span data-stu-id="fc68a-133">User impersonation (protected users)</span></span>|<span data-ttu-id="fc68a-134">UIMP</span><span class="sxs-lookup"><span data-stu-id="fc68a-134">UIMP</span></span>|[<span data-ttu-id="fc68a-135">Office 365용 Microsoft Defender에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="fc68a-135">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="fc68a-136">6<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fc68a-136">6<sup>\*</sup></span></span>|<span data-ttu-id="fc68a-137">도메인 가장(보호된 도메인)</span><span class="sxs-lookup"><span data-stu-id="fc68a-137">Domain impersonation (protected domains)</span></span>|<span data-ttu-id="fc68a-138">DIMP</span><span class="sxs-lookup"><span data-stu-id="fc68a-138">DIMP</span></span>|[<span data-ttu-id="fc68a-139">Office 365용 Microsoft Defender에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="fc68a-139">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="fc68a-140">7 </span><span class="sxs-lookup"><span data-stu-id="fc68a-140">7</span></span>|<span data-ttu-id="fc68a-141">스팸</span><span class="sxs-lookup"><span data-stu-id="fc68a-141">Spam</span></span>|<span data-ttu-id="fc68a-142">CAT:SPM</span><span class="sxs-lookup"><span data-stu-id="fc68a-142">CAT:SPM</span></span>|[<span data-ttu-id="fc68a-143">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="fc68a-143">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="fc68a-144">8 </span><span class="sxs-lookup"><span data-stu-id="fc68a-144">8</span></span>|<span data-ttu-id="fc68a-145">대량</span><span class="sxs-lookup"><span data-stu-id="fc68a-145">Bulk</span></span>|<span data-ttu-id="fc68a-146">CAT:BULK</span><span class="sxs-lookup"><span data-stu-id="fc68a-146">CAT:BULK</span></span>|[<span data-ttu-id="fc68a-147">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="fc68a-147">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |

  <span data-ttu-id="fc68a-148"><sup>\*</sup> 이러한 기능은 Microsoft Defender for Office 365의 피싱 방지 정책에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-148"><sup>\*</sup> These features are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="fc68a-149">**정책 우선** 순위: 각 보호 유형(스팸 방지, 맬웨어 방지, 피싱 방지 등)에 대해 모든 사용자에게 적용되는 기본 정책이 있지만 특정 사용자에게 적용되는 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="fc68a-150">각 사용자 지정 정책에는 정책이 적용되는 순서를 결정하는 우선 순위 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="fc68a-151">기본 정책은 항상 마지막에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="fc68a-152">사용자가 같은 유형의 여러 정책에 정의되어 있는 경우 우선 순위가 가장 높은 정책만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="fc68a-153">해당 유형의 나머지 정책은 사용자에 대해 평가되지 않습니다(기본 정책 포함).</span><span class="sxs-lookup"><span data-stu-id="fc68a-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="fc68a-154">예를 들어 동일한 사용자에게 적용되는 Microsoft Defender for Office 365의 다음과 같은 피싱 방지 정책과 사용자 가장 및 스푸핑으로 식별된 메시지를 고려합니다. </span><span class="sxs-lookup"><span data-stu-id="fc68a-154">For example, consider the following anti-phishing policies in Microsoft Defender for Office 365 **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="fc68a-155">정책 이름</span><span class="sxs-lookup"><span data-stu-id="fc68a-155">Policy name</span></span>|<span data-ttu-id="fc68a-156">우선 순위</span><span class="sxs-lookup"><span data-stu-id="fc68a-156">Priority</span></span>|<span data-ttu-id="fc68a-157">사용자 가장</span><span class="sxs-lookup"><span data-stu-id="fc68a-157">User impersonation</span></span>|<span data-ttu-id="fc68a-158">스푸핑 방지</span><span class="sxs-lookup"><span data-stu-id="fc68a-158">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="fc68a-159">정책 A</span><span class="sxs-lookup"><span data-stu-id="fc68a-159">Policy A</span></span>|<span data-ttu-id="fc68a-160">1 </span><span class="sxs-lookup"><span data-stu-id="fc68a-160">1</span></span>|<span data-ttu-id="fc68a-161">켜짐</span><span class="sxs-lookup"><span data-stu-id="fc68a-161">On</span></span>|<span data-ttu-id="fc68a-162">해제</span><span class="sxs-lookup"><span data-stu-id="fc68a-162">Off</span></span>|
  |<span data-ttu-id="fc68a-163">정책 B</span><span class="sxs-lookup"><span data-stu-id="fc68a-163">Policy B</span></span>|<span data-ttu-id="fc68a-164">2 </span><span class="sxs-lookup"><span data-stu-id="fc68a-164">2</span></span>|<span data-ttu-id="fc68a-165">해제</span><span class="sxs-lookup"><span data-stu-id="fc68a-165">Off</span></span>|<span data-ttu-id="fc68a-166">켜짐</span><span class="sxs-lookup"><span data-stu-id="fc68a-166">On</span></span>|
  |

1. <span data-ttu-id="fc68a-167">스푸핑의 우선 순위가 사용자 가장(5)보다 높기 때문에 메시지가 스푸핑으로 표시 및 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (5).</span></span>
2. <span data-ttu-id="fc68a-168">정책 A는 정책 B보다 우선 순위가 높기 때문에 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="fc68a-169">정책 A의 설정에 따라 정책에서 스푸핑 방지가 해제되어 있기 때문에 메시지에 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="fc68a-170">정책 처리가 중지되고 정책 B가 사용자에게 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="fc68a-171">동일한 사용자가 같은 유형의 여러 사용자 지정 정책에 의도적으로 또는 의도하지 않은 것으로 포함될 수 있기 때문에 사용자 지정 정책에 대해 다음 디자인 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="fc68a-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="fc68a-172">적은 수의 사용자에게 적용되는 정책에 더 높은 우선 순위를 할당하고 많은 수의 사용자에게 적용되는 정책에 낮은 우선 순위를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="fc68a-173">기본 정책은 항상 마지막에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="fc68a-174">우선 순위가 낮은 정책보다 더 엄격하거나 더 전문화된 설정을 하도록 우선 순위가 높은 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fc68a-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="fc68a-175">더 적은 사용자 지정 정책을 사용하는 것이 좋습니다(보다 엄격하거나 더 전문화된 설정이 필요한 사용자에 대한 사용자 지정 정책만 사용).</span><span class="sxs-lookup"><span data-stu-id="fc68a-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
