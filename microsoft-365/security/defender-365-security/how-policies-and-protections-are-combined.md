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
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)의 보호 적용 순서와 보호 정책의 우선 순위 값이 적용되는 정책을 결정하는 방법에 대해 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2a72420340993c027ec99820dcd3edddab1a304
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071391"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="fb482-104">전자 메일 보호의 순서 및 우선 순위</span><span class="sxs-lookup"><span data-stu-id="fb482-104">Order and precedence of email protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fb482-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="fb482-105">**Applies to**</span></span>
- [<span data-ttu-id="fb482-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fb482-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fb482-107">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="fb482-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fb482-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fb482-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="fb482-109">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 인바운드 전자 메일은 여러 형태의 보호로 플래그가 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="fb482-110">예를 들어 모든 Microsoft 365 고객이 사용할 수 있는 EOP의 기본 제공 피싱 방지 정책과 Office 365 고객용 Microsoft Defender에서 사용할 수 있는 보다 강력한 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-110">For example, the built-in anti-phishing policies in EOP that are available to all Microsoft 365 customers, and the more robust anti-phishing policies that are available to Microsoft Defender for Office 365 customers.</span></span> <span data-ttu-id="fb482-111">또한 메시지는 맬웨어, 스팸, 피싱 등에 대한 여러 검색 검색을 통과합니다. 이 모든 활동이 제공될 경우 어떤 정책이 적용되는지 혼동될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-111">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="fb482-112">일반적으로 메시지에 적용되는 정책은 **CAT(Category)** 속성의 **X-Forefront-Antispam-Report** 헤더에서 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-112">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="fb482-113">자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb482-113">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="fb482-114">메시지에 적용되는 정책을 결정하는 주요 요인에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-114">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="fb482-115">전자 메일 보호 유형의 **우선 순위:** 이 순서는 구성할 수 없습니다. 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-115">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="fb482-116">우선 순위</span><span class="sxs-lookup"><span data-stu-id="fb482-116">Priority</span></span>|<span data-ttu-id="fb482-117">전자 메일 보호</span><span class="sxs-lookup"><span data-stu-id="fb482-117">Email protection</span></span>|<span data-ttu-id="fb482-118">범주</span><span class="sxs-lookup"><span data-stu-id="fb482-118">Category</span></span>|<span data-ttu-id="fb482-119">관리할 위치</span><span class="sxs-lookup"><span data-stu-id="fb482-119">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="fb482-120">1</span><span class="sxs-lookup"><span data-stu-id="fb482-120">1</span></span>|<span data-ttu-id="fb482-121">맬웨어</span><span class="sxs-lookup"><span data-stu-id="fb482-121">Malware</span></span>|<span data-ttu-id="fb482-122">CAT:MALW</span><span class="sxs-lookup"><span data-stu-id="fb482-122">CAT:MALW</span></span>|[<span data-ttu-id="fb482-123">EOP에서 맬웨어 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="fb482-123">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="fb482-124">2 </span><span class="sxs-lookup"><span data-stu-id="fb482-124">2</span></span>|<span data-ttu-id="fb482-125">피싱</span><span class="sxs-lookup"><span data-stu-id="fb482-125">Phishing</span></span>|<span data-ttu-id="fb482-126">CAT:PHSH</span><span class="sxs-lookup"><span data-stu-id="fb482-126">CAT:PHSH</span></span>|[<span data-ttu-id="fb482-127">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="fb482-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="fb482-128">3 </span><span class="sxs-lookup"><span data-stu-id="fb482-128">3</span></span>|<span data-ttu-id="fb482-129">높은 정확도 스팸</span><span class="sxs-lookup"><span data-stu-id="fb482-129">High confidence spam</span></span>|<span data-ttu-id="fb482-130">CAT:HSPM</span><span class="sxs-lookup"><span data-stu-id="fb482-130">CAT:HSPM</span></span>|[<span data-ttu-id="fb482-131">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="fb482-131">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="fb482-132">4 </span><span class="sxs-lookup"><span data-stu-id="fb482-132">4</span></span>|<span data-ttu-id="fb482-133">스푸핑</span><span class="sxs-lookup"><span data-stu-id="fb482-133">Spoofing</span></span>|<span data-ttu-id="fb482-134">CAT:SPOOF</span><span class="sxs-lookup"><span data-stu-id="fb482-134">CAT:SPOOF</span></span>|[<span data-ttu-id="fb482-135">EOP에서 스푸핑 인텔리전스 구성</span><span class="sxs-lookup"><span data-stu-id="fb482-135">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="fb482-136">5<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fb482-136">5<sup>\*</sup></span></span>|<span data-ttu-id="fb482-137">사용자 가장(보호된 사용자)</span><span class="sxs-lookup"><span data-stu-id="fb482-137">User impersonation (protected users)</span></span>|<span data-ttu-id="fb482-138">UIMP</span><span class="sxs-lookup"><span data-stu-id="fb482-138">UIMP</span></span>|[<span data-ttu-id="fb482-139">Microsoft Defender for Office 365에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="fb482-139">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="fb482-140">6<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fb482-140">6<sup>\*</sup></span></span>|<span data-ttu-id="fb482-141">도메인 가장(보호된 도메인)</span><span class="sxs-lookup"><span data-stu-id="fb482-141">Domain impersonation (protected domains)</span></span>|<span data-ttu-id="fb482-142">DIMP</span><span class="sxs-lookup"><span data-stu-id="fb482-142">DIMP</span></span>|[<span data-ttu-id="fb482-143">Microsoft Defender for Office 365에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="fb482-143">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="fb482-144">7 </span><span class="sxs-lookup"><span data-stu-id="fb482-144">7</span></span>|<span data-ttu-id="fb482-145">스팸</span><span class="sxs-lookup"><span data-stu-id="fb482-145">Spam</span></span>|<span data-ttu-id="fb482-146">CAT:SPM</span><span class="sxs-lookup"><span data-stu-id="fb482-146">CAT:SPM</span></span>|[<span data-ttu-id="fb482-147">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="fb482-147">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="fb482-148">8 </span><span class="sxs-lookup"><span data-stu-id="fb482-148">8</span></span>|<span data-ttu-id="fb482-149">대량</span><span class="sxs-lookup"><span data-stu-id="fb482-149">Bulk</span></span>|<span data-ttu-id="fb482-150">CAT:BULK</span><span class="sxs-lookup"><span data-stu-id="fb482-150">CAT:BULK</span></span>|[<span data-ttu-id="fb482-151">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="fb482-151">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |

  <span data-ttu-id="fb482-152"><sup>\*</sup> 이러한 기능은 Microsoft Defender for Office 365의 피싱 방지 정책에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-152"><sup>\*</sup> These features are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="fb482-153">**정책 우선** 순위: 각 보호 유형(스팸 방지, 맬웨어 방지, 피싱 방지 등)에 대해 모든 사용자에게 적용되는 기본 정책이 있지만 특정 사용자에게 적용되는 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-153">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="fb482-154">각 사용자 지정 정책에는 정책이 적용되는 순서를 결정하는 우선 순위 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-154">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="fb482-155">기본 정책은 항상 마지막에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-155">The default policy is always applied last.</span></span>

  <span data-ttu-id="fb482-156">사용자가 동일한 유형의 여러 정책에 정의되어 있는 경우 우선 순위가 가장 높은 정책만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-156">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="fb482-157">해당 유형의 나머지 정책은 사용자에 대해 평가되지 않습니다(기본 정책 포함).</span><span class="sxs-lookup"><span data-stu-id="fb482-157">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="fb482-158">예를 들어 동일한 사용자에게 적용되는 Microsoft Defender for Office 365의 다음과 같은 피싱 방지 정책과 사용자 가장 및 스푸핑으로 식별된 메시지를 고려합니다. </span><span class="sxs-lookup"><span data-stu-id="fb482-158">For example, consider the following anti-phishing policies in Microsoft Defender for Office 365 **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="fb482-159">정책 이름</span><span class="sxs-lookup"><span data-stu-id="fb482-159">Policy name</span></span>|<span data-ttu-id="fb482-160">우선 순위</span><span class="sxs-lookup"><span data-stu-id="fb482-160">Priority</span></span>|<span data-ttu-id="fb482-161">사용자 가장</span><span class="sxs-lookup"><span data-stu-id="fb482-161">User impersonation</span></span>|<span data-ttu-id="fb482-162">스푸핑 방지</span><span class="sxs-lookup"><span data-stu-id="fb482-162">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="fb482-163">정책 A</span><span class="sxs-lookup"><span data-stu-id="fb482-163">Policy A</span></span>|<span data-ttu-id="fb482-164">1</span><span class="sxs-lookup"><span data-stu-id="fb482-164">1</span></span>|<span data-ttu-id="fb482-165">켜짐</span><span class="sxs-lookup"><span data-stu-id="fb482-165">On</span></span>|<span data-ttu-id="fb482-166">해제</span><span class="sxs-lookup"><span data-stu-id="fb482-166">Off</span></span>|
  |<span data-ttu-id="fb482-167">정책 B</span><span class="sxs-lookup"><span data-stu-id="fb482-167">Policy B</span></span>|<span data-ttu-id="fb482-168">2 </span><span class="sxs-lookup"><span data-stu-id="fb482-168">2</span></span>|<span data-ttu-id="fb482-169">해제</span><span class="sxs-lookup"><span data-stu-id="fb482-169">Off</span></span>|<span data-ttu-id="fb482-170">켜짐</span><span class="sxs-lookup"><span data-stu-id="fb482-170">On</span></span>|
  |

1. <span data-ttu-id="fb482-171">스푸핑의 우선 순위가 사용자 가장(5)보다 높기 때문에 메시지가 스푸핑으로 표시되어 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-171">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (5).</span></span>
2. <span data-ttu-id="fb482-172">정책 A는 정책 B보다 우선 순위가 높기 때문에 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-172">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="fb482-173">정책 A의 설정에 따라 정책에서 스푸핑 방지가 꺼져 있기 때문에 메시지에 대한 작업이 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-173">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="fb482-174">정책 처리가 중지되고 사용자에게 정책 B가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-174">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="fb482-175">동일한 사용자가 같은 유형의 여러 사용자 지정 정책에 의도적으로 또는 의도하지 않은 것으로 포함될 수 있기 때문에 사용자 지정 정책에 대해 다음 디자인 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="fb482-175">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="fb482-176">적은 수의 사용자에게 적용되는 정책에 더 높은 우선 순위를 할당하고 많은 수의 사용자에게 적용되는 정책에 낮은 우선 순위를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-176">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="fb482-177">기본 정책은 항상 마지막으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-177">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="fb482-178">우선 순위가 높은 정책이 우선 순위가 낮은 정책보다 더 엄격하거나 더 전문화된 설정을 하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb482-178">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="fb482-179">더 적은 수의 사용자 지정 정책을 사용하는 것이 좋습니다(더 엄격하거나 더 전문화된 설정이 필요한 사용자에 대해 사용자 지정 정책만 사용).</span><span class="sxs-lookup"><span data-stu-id="fb482-179">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
