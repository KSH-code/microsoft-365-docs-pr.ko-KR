---
title: Walkthrough - Spoof intelligence insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 관리자는 스푸핑 인텔리전스 정보의 작동 방식에 대해 학습할 수 있습니다. SPF, DKIM 또는 DMARC(전자 메일 인증 확인)를 통과하지 않는 도메인에서 조직에 합법적으로 전자 메일을 보내는 보낸 사람이 있는지 빠르게 확인할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f5ebd0fd42d17354eeb1e03c946ac5446c3667c
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572744"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cb7e9-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="cb7e9-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cb7e9-105">Office 365용 Defender가 있는 Microsoft 365 조직에서는 스푸핑 인텔리전스 인사이트를 사용하여 사용자가 적법하게 사용되지 않은 전자 메일을 보내는 보낸 사람(SPF, DKIM 또는 DMARC 검사를 통과하지 않는 도메인의 메시지)을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="cb7e9-106">알려진 보낸 사람이 알려진 위치에서 스푸핑된 메시지를 보낼 수 있도록 허용하면 가음성(나쁜 것으로 표시된 좋은 전자 메일)을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="cb7e9-107">허용된 스푸핑된 보낸 사람 모니터링을 통해 안전하지 않은 메시지가 조직에 도착하지 못하도록 추가 보안 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="cb7e9-108">보고서 및 인사이트에 대한 자세한 내용은 보안 및 규정 준수 센터의 보고서 [및 & 참조하세요.](reports-and-insights-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="cb7e9-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="cb7e9-109">이 Walkthrough is one of several for the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="cb7e9-110">보고서 및 인사이트를 진행하는 데 대한 자세한 내용은 관련 항목 섹션의 walkthroughs in the [walkthroughs in](#related-topics) the Related topics(보고서 및 인사이트)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cb7e9-111">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="cb7e9-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cb7e9-112"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cb7e9-113">보안 대시보드 페이지로 직접 **이동하기 위해** 다음을 <https://protection.office.com/searchandinvestigation/dashboard> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="cb7e9-114">보안 및 준수 센터에서 두 개 이상의 대시보드에서 스푸핑 인텔리전스 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="cb7e9-115">보고 있는 대시보드에 관계없이 인사이트는 동일한 세부 정보를 제공하며 동일한 작업을 빠르게 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="cb7e9-116">이 문서의 절차를 수행하려면 먼저 보안 및 준수 & 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-116">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cb7e9-117">**조직 관리**</span><span class="sxs-lookup"><span data-stu-id="cb7e9-117">**Organization Management**</span></span>
  - <span data-ttu-id="cb7e9-118">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="cb7e9-118">**Security Administrator**</span></span>
  - <span data-ttu-id="cb7e9-119">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="cb7e9-119">**Security Reader**</span></span>
  - <span data-ttu-id="cb7e9-120">**전역 읽기**</span><span class="sxs-lookup"><span data-stu-id="cb7e9-120">**Global Reader**</span></span>

  <span data-ttu-id="cb7e9-121">**참고:** Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 _and_ & 준수 센터의 필요한 사용 권한과 Microsoft 365의 다른 기능에 대한 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-121">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cb7e9-122">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-122">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="cb7e9-123">Office 365용 Microsoft Defender에서 피싱 방지 정책에서 스푸핑 인텔리전스를 사용하도록 설정하고 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-123">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="cb7e9-124">자세한 내용은 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-124">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="cb7e9-125">스푸핑 인텔리전스를 사용하여 사용자에게 확인되지 않은 메시지를 보내는 보낸 사람 모니터링 및 관리는 [Microsoft 365에서](learn-about-spoof-intelligence.md)스푸핑 인텔리전스 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-125">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="cb7e9-126">보안 및 준수 센터에서 스푸핑 인텔리전스 & 열기</span><span class="sxs-lookup"><span data-stu-id="cb7e9-126">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="cb7e9-127">보안 및 & 센터에서 위협 관리 **대시보드로** \> **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="cb7e9-127">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="cb7e9-128">**Insights** 행에서 다음 항목 중 하나를 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-128">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="cb7e9-129">**스푸핑** 인텔리전스 사용 : 이 정보의 이름은 지난 **30일** 동안 인증에 실패한 스푸핑된 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-129">**Spoof intelligence is enabled**: The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="cb7e9-130">이 옵션이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-130">This is the default.</span></span>
   - <span data-ttu-id="cb7e9-131">**스푸핑** 인텔리전스를 사용할 **Enable Spoof Protection** 수 없습니다. 스푸핑 방지 사용이라는 정보의 정보를 확인하여 이를 클릭하면 스푸핑 인텔리전스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-131">**Spoof intelligence is disabled**: The insight in named **Enable Spoof Protection**, and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="cb7e9-132">대시보드의 인사이트에는 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-132">The insight on the dashboard shows you information like this:</span></span>

   ![스푸핑 인텔리전스 정보의 스크린샷](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="cb7e9-134">이 인사이트에는 두 가지 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-134">This insight has two modes:</span></span>

   - <span data-ttu-id="cb7e9-135">**인사이트** 모드: 스푸핑 인텔리전스를 사용하도록 설정하면 지난 30일 동안의 스푸핑 인텔리전스 기능의 영향을 수신한 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-135">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="cb7e9-136">**모드의 경우:** 스푸핑 인텔리전스를 사용하지 않도록 설정하면 *would* 지난 30일 동안의 스푸핑 인텔리전스 기능에 의해 영향을 하게 될 메시지 수가 정보를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-136">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="cb7e9-137">어느 경우든 인사이트에 표시되는 스푸핑된 도메인은 의심스러운 **Suspicious domain pairs** 도메인 쌍과 의심하지 않는 도메인 쌍의 두 범주로 구분됩니다. **Non-suspicious domain pairs**</span><span class="sxs-lookup"><span data-stu-id="cb7e9-137">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="cb7e9-138">이러한 범주는 검토할 수 있는 세 가지 다른 버킷으로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-138">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="cb7e9-139">도메인 **쌍은** 보내는 주소와 보내는 인프라의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-139">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="cb7e9-140">보낸 사람 주소는 전자 메일 클라이언트의 보낸 사람 상자에 표시되는 보낸 사람 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-140">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="cb7e9-141">이 주소를 주소라고도 `5322.From` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-141">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="cb7e9-142">보내는 인프라 또는 보낸 사람이 보내는 IP 주소의 역방향 DNS PTR 레코드(PTR 레코드)의 조직 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-142">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="cb7e9-143">보내는 IP 주소에 PTR 레코드가 없는 경우 보낸 사람이 보내는 IP와 CIDR(/24)의 255.255.255.0 서브넷 마스크로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-143">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="cb7e9-144">예를 들어 IP 주소가 192.168.100.100이면 보낸 사람 전체 IP 주소는 192.168.100.100/24입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-144">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="cb7e9-145">**의심스러운** 도메인 쌍은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-145">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="cb7e9-146">**높은 신뢰도** 스푸핑: 기록 전송 패턴 및 도메인의 신뢰도 점수를 기반으로 도메인이 스푸핑 중일 수 있으며 이러한 도메인의 메시지가 악의적일 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-146">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="cb7e9-147">**보통** 신뢰도 스푸핑: 기록 전송 패턴 및 도메인의 신뢰도 점수를 기반으로 도메인이 스푸핑 중일 수 있으며 이러한 도메인에서 보낸 메시지가 합법적이라고 확신합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-147">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="cb7e9-148">가음성은 높은 신뢰도 스푸핑보다 이 범주에서 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-148">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="cb7e9-149">**의심스러운** 도메인 쌍(스푸핑 **포함):** 도메인이 명시적 전자 메일 인증 검사 [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)및 [DMARC를](use-dmarc-to-validate-email.md)확인하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-149">**Non-suspicious domain pairs** (includes **rescued spoof**): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="cb7e9-150">그러나 도메인은 암시적 전자 메일 인증 확인(복합 인증)을[통과했습니다.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="cb7e9-150">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="cb7e9-151">따라서 메시지에 대한 스푸핑 방지 작업이 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-151">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="cb7e9-152">스푸핑 인텔리전스 정보에서 의심스러운 도메인 쌍에 대한 자세한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="cb7e9-152">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="cb7e9-153">스푸핑 인텔리전스 인사이트를 클릭하고 도메인 쌍(높음, 보통 또는 고가의 도메인 쌍)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-153">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="cb7e9-154">**스푸핑 인텔리전스 정보 페이지가** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-154">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="cb7e9-155">이 페이지에는 조직에 확인되지 않은 전자 메일을 보내는 보낸 사람 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-155">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="cb7e9-156">이 정보는 스푸핑된 메시지에 권한이 부여가 되거나 추가 조치를 취해야 하는지 여부를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-156">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="cb7e9-157">메시지 수, 스푸핑이 마지막으로 검색된 날짜 등별로 정보를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-157">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="cb7e9-158">테이블에서 항목을 선택하여 도메인 쌍에 대한 다양한 정보가 포함된 세부 정보 창을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-158">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="cb7e9-159">이 정보에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-159">The information includes:</span></span>
   - <span data-ttu-id="cb7e9-160">이 경우 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-160">Why we caught this.</span></span>
   - <span data-ttu-id="cb7e9-161">해야 할 일.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-161">What you need to do.</span></span>
   - <span data-ttu-id="cb7e9-162">도메인 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-162">A domain summary.</span></span>
   - <span data-ttu-id="cb7e9-163">보낸 사람에 대한 WhoIs 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-163">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="cb7e9-164">동일한 보낸 사람으로부터 테넌트에 비슷한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-164">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="cb7e9-165">여기에서 **AllowedToSpoof** 수신 허용 - 보낸 사람 목록에서 도메인 쌍을 추가하거나 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-165">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![스푸핑 인텔리전스 정보 세부 정보 창의 도메인 스크린샷](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="cb7e9-167">AllowedToSpoof 목록에서 도메인 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="cb7e9-167">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="cb7e9-168">도메인 쌍에 대한 스푸핑 인텔리전스 정보의 세부 정보 창에서 AllowedToSpoof(수신 허용 - 보낸 사람) 목록에서 도메인을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-168">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="cb7e9-169">토글을 그에 따라 설정하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-169">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="cb7e9-170">도메인 쌍을 허용하면 스푸핑된 도메인과 보내는 인프라의 *조합만* 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-170">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="cb7e9-171">모든 원본에서 스푸핑된 도메인의 전자 메일을 허용하지 않으며 도메인에 대한 보내는 인프라의 전자 메일을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-171">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="cb7e9-172">예를 들어 다음 도메인 쌍이 조직에 스푸핑된 메시지를 보낼 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-172">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="cb7e9-173">*스푸핑된 도메인*: gmail.com"</span><span class="sxs-lookup"><span data-stu-id="cb7e9-173">*Spoofed Domain*: gmail.com"</span></span>
- <span data-ttu-id="cb7e9-174">*전송 인프라:* `tms.mx.com`</span><span class="sxs-lookup"><span data-stu-id="cb7e9-174">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="cb7e9-175">해당 도메인 쌍의 전자 메일만 스푸핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-175">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="cb7e9-176">스푸핑을 시도하는 gmail.com 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-176">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="cb7e9-177">스푸핑 인텔리전스를 통해 tms.mx.com 도메인의 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7e9-177">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cb7e9-178">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cb7e9-178">Related topics</span></span>

[<span data-ttu-id="cb7e9-179">Microsoft 365의 스푸핑 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="cb7e9-179">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
