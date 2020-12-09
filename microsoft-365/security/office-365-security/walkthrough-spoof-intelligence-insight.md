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
ms.openlocfilehash: 9139a2b4c3c7ed8262f3d75b445defb869371d07
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602116"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f1a1b-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="f1a1b-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f1a1b-105">Office 365용 Defender가 있는 Microsoft 365 조직에서는 스푸핑 인텔리전스 인사이트를 사용하여 사용자가 적법하게 사용자에게 확인되지 않은 전자 메일을 보내는 외부 보낸 사람(SPF, DKIM 또는 DMARC 검사를 통과하지 않는 도메인의 메시지)을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="f1a1b-106">알려진 외부 보낸 사람이 알려진 위치에서 스푸핑된 메시지를 보낼 수 있도록 허용하면 가음성(나쁜 것으로 표시된 좋은 전자 메일)을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-106">By allowing known external senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="f1a1b-107">허용된 스푸핑된 보낸 사람 모니터링을 통해 안전하지 않은 메시지가 조직에 도착하지 않도록 추가 보안 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="f1a1b-108">보고서 및 인사이트에 대한 자세한 내용은 보안 및 규정 준수 센터의 보고서 [및 & 참조하세요.](reports-and-insights-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="f1a1b-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="f1a1b-109">이 walkthrough is one of several for the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="f1a1b-110">보고서 및 인사이트를 진행하는 데 대한 자세한 내용은 관련 항목 섹션의 walkthroughs in the [walkthroughs in](#related-topics) the Related topics(보고서 및 인사이트)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f1a1b-111">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f1a1b-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f1a1b-112"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f1a1b-113">보안 대시보드 페이지로 직접 **이동하기 위해** 다음을 <https://protection.office.com/searchandinvestigation/dashboard> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="f1a1b-114">보안 및 준수 센터에서 두 개 이상의 대시보드에서 스푸핑 인텔리전스 정보를 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="f1a1b-115">보고 있는 대시보드에 관계없이 인사이트는 동일한 세부 정보를 제공하며 동일한 작업을 빠르게 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="f1a1b-116">이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-116">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f1a1b-117">**조직 관리**</span><span class="sxs-lookup"><span data-stu-id="f1a1b-117">**Organization Management**</span></span>
  - <span data-ttu-id="f1a1b-118">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="f1a1b-118">**Security Administrator**</span></span>
  - <span data-ttu-id="f1a1b-119">**보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="f1a1b-119">**Security Reader**</span></span>
  - <span data-ttu-id="f1a1b-120">**전역 읽기 권한자**</span><span class="sxs-lookup"><span data-stu-id="f1a1b-120">**Global Reader**</span></span>

  <span data-ttu-id="f1a1b-121">**참고:** Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 _and_ & 준수 센터의 필요한 사용 권한과 Microsoft 365의 다른 기능에 대한 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-121">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f1a1b-122">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-122">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="f1a1b-123">Office 365용 Microsoft Defender에서 피싱 방지 정책에서 스푸핑 인텔리전스를 사용하도록 설정하고 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-123">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f1a1b-124">스푸핑 인텔리전스가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-124">Spoof intelligence is enabled by default.</span></span> <span data-ttu-id="f1a1b-125">자세한 내용은 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-125">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="f1a1b-126">스푸핑 인텔리전스를 사용하여 사용자에게 확인되지 않은 메시지를 보내는 보낸 사람 모니터링 및 관리는 [Microsoft 365에서](learn-about-spoof-intelligence.md)스푸핑 인텔리전스 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-126">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="f1a1b-127">보안 및 준수 센터에서 스푸핑 인텔리전스 & 열기</span><span class="sxs-lookup"><span data-stu-id="f1a1b-127">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="f1a1b-128">보안 및 & 센터에서 위협 관리 **대시보드로** \> **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f1a1b-128">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="f1a1b-129">**Insights** 행에서 다음 항목 중 하나를 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-129">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="f1a1b-130">**지난 7일** 동안의 스푸핑된 도메인일 수 있습니다. 이 인사이트는 스푸핑 인텔리전스가 사용하도록 설정되어 있습니다(기본적으로 사용).</span><span class="sxs-lookup"><span data-stu-id="f1a1b-130">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="f1a1b-131">**스푸핑** 방지 사용: 이 인사이트는 스푸핑 인텔리전스가 사용하지 않도록 설정되어 있으며, 정보를 클릭하면 스푸핑 인텔리전스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-131">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="f1a1b-132">대시보드의 인사이트에는 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-132">The insight on the dashboard shows you information like this:</span></span>

   ![스푸핑 인텔리전스 정보의 스크린샷](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="f1a1b-134">이 인사이트에는 두 가지 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-134">This insight has two modes:</span></span>

   - <span data-ttu-id="f1a1b-135">**인사이트 모드:** 스푸핑 인텔리전스를 사용하도록 설정하면 지난 7일 동안의 스푸핑 인텔리전스 기능에 영향을 미치게 된 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-135">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="f1a1b-136">**모드의 경우:** 스푸핑 인텔리전스를 사용하지 않도록 설정하면 *would* 지난 7일 동안의 스푸핑 인텔리전스 기능에 의해 영향을 하게 될 메시지 수가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-136">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="f1a1b-137">어느 경우든 인사이트에 표시되는 스푸핑된 도메인은 의심스러운 **Suspicious domains** 도메인과 의심하지 않는 도메인의 두 범주로 **구분됩니다.**</span><span class="sxs-lookup"><span data-stu-id="f1a1b-137">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="f1a1b-138">**의심스러운 도메인은 다음과** 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-138">**Suspicious domains** include:</span></span>

     - <span data-ttu-id="f1a1b-139">높은 신뢰도 스푸핑: 기록 전송 패턴 및 도메인의 신뢰도 점수를 기반으로 도메인은 스푸핑하고 이러한 도메인의 메시지는 악의적일 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-139">High-confidence spoof: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

     - <span data-ttu-id="f1a1b-140">보통 신뢰도 스푸핑: 기록 전송 패턴 및 도메인의 신뢰도 점수에 따라 도메인이 스푸핑 중일 수 있으며 이러한 도메인에서 보낸 메시지는 합법적이라고 확신합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-140">Moderate confidence spoof: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="f1a1b-141">가음성은 높은 신뢰도 스푸핑보다 이 범주에서 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-141">False positives are more likely in this category than high-confidence spoof.</span></span>

   <span data-ttu-id="f1a1b-142">**의심스러운** 도메인: 도메인에서 명시적 전자 메일 인증에 [실패하여 SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)및 [DMARC가 확인되지 않았습니다.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="f1a1b-142">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="f1a1b-143">그러나 도메인은 암시적 전자 메일 인증 확인(복합 인증)을[통과했습니다.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="f1a1b-143">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="f1a1b-144">따라서 메시지에 대한 스푸핑 방지 작업이 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-144">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a><span data-ttu-id="f1a1b-145">스푸핑 인텔리전스 정보에서 의심스러운 도메인에 대한 자세한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="f1a1b-145">View detailed information about suspicious domains from the Spoof intelligence insight</span></span>

1. <span data-ttu-id="f1a1b-146">스푸핑 인텔리전스 통찰력에서 **의심스러운** 도메인 **Non-suspicious domains** 또는 의심스러운 도메인을 클릭하여 스푸핑 **인텔리전스** 정보 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-146">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="f1a1b-147">**스푸핑 인텔리전스 정보 페이지에는** 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-147">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="f1a1b-148">**스푸핑된 도메인**: 전자 메일 클라이언트의 시작 상자에 **From** 표시되는 스푸핑된 사용자의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-148">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="f1a1b-149">이 주소를 주소라고도 `5322.From` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-149">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="f1a1b-150">**인프라:** 보내는 _인프라라고도 합니다._</span><span class="sxs-lookup"><span data-stu-id="f1a1b-150">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="f1a1b-151">원본 전자 메일 서버의 IP 주소의 역방향 DNS PTR 레코드에 있는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-151">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="f1a1b-152">원본 IP 주소에 PTR 레코드가 없는 경우 보내는 인프라는 \<source IP\> /24(예: 192.168.100.100/24)로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-152">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="f1a1b-153">**메시지 수:** 지난 7일 이내에 지정된 스푸핑된 도메인을 포함하는 보내는 인프라에서 조직으로 보내는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-153">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="f1a1b-154">**마지막 확인** 날짜: 스푸핑된 도메인이 포함된 보내는 인프라에서 메시지를 받은 마지막 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-154">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="f1a1b-155">**스푸핑 유형**: 이 값은 **External입니다.**</span><span class="sxs-lookup"><span data-stu-id="f1a1b-155">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="f1a1b-156">**스푸핑이 허용되는 경우:** 여기에 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-156">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="f1a1b-157">**예:** 스푸핑된 사용자의 도메인과 보내는 인프라의 조합에서 보낸 메시지는 허용될 수 있으며 스푸핑된 전자 메일로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-157">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="f1a1b-158">**아니요:** 스푸핑된 사용자의 도메인과 보내는 인프라의 조합에서 보낸 메시지가 스푸핑된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-158">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="f1a1b-159">이 작업은 기본 피싱 방지 정책 또는 사용자 지정 피싱 방지 정책에 의해 제어됩니다(기본값은 정크 메일 폴더로 메시지 **이동).**</span><span class="sxs-lookup"><span data-stu-id="f1a1b-159">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

     <span data-ttu-id="f1a1b-160">자세한 내용은 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-160">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

2. <span data-ttu-id="f1a1b-161">플라이아웃에서 도메인/보내는 인프라 쌍에 대한 세부 정보를 확인하려면 목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-161">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="f1a1b-162">이 정보에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-162">The information includes:</span></span>
   - <span data-ttu-id="f1a1b-163">이 경우 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-163">Why we caught this.</span></span>
   - <span data-ttu-id="f1a1b-164">해야 할 일.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-164">What you need to do.</span></span>
   - <span data-ttu-id="f1a1b-165">도메인 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-165">A domain summary.</span></span>
   - <span data-ttu-id="f1a1b-166">보낸 사람에 대한 WhoIs 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-166">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="f1a1b-167">동일한 보낸 사람으로부터 테넌트에 비슷한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-167">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="f1a1b-168">여기에서 보낸 사람 스푸핑 허용 목록에서 도메인/보내는 **Allowed to spoof** 인프라 쌍을 추가하거나 제거하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-168">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="f1a1b-169">토글을 그에 따라 설정하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-169">Simply set the toggle accordingly.</span></span>

   ![스푸핑 인텔리전스 정보 세부 정보 창의 도메인 스크린샷](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a><span data-ttu-id="f1a1b-171">스푸핑 허용 목록에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="f1a1b-171">Adding a domain to the Allowed to spoof list</span></span>

<span data-ttu-id="f1a1b-172">스푸핑 인텔리전스 정보에서 허용된 목록에 도메인을 추가하면 스푸핑된 도메인과 *and* 보내는 인프라의 조합만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-172">Adding a domain to the Allowed to spoof list from the spoof intelligence insight only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="f1a1b-173">모든 원본에서 스푸핑된 도메인의 전자 메일을 허용하지 않으며 도메인에 대한 보내는 인프라의 전자 메일을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-173">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="f1a1b-174">예를 들어 다음 도메인을 스푸핑 허용 목록에 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-174">For example, you allow the following domain to the Allowed to spoof list:</span></span>

- <span data-ttu-id="f1a1b-175">**도메인**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="f1a1b-175">**Domain**: gmail.com</span></span>
- <span data-ttu-id="f1a1b-176">**인프라**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="f1a1b-176">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="f1a1b-177">해당 도메인/보내는 인프라 쌍의 전자 메일만 스푸핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-177">Only email from that domain/sending infrastructure pair will be allowed to spoof.</span></span> <span data-ttu-id="f1a1b-178">스푸핑을 시도하는 gmail.com 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-178">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="f1a1b-179">스푸핑 인텔리전스를 통해 tms.mx.com 도메인의 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a1b-179">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f1a1b-180">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f1a1b-180">Related topics</span></span>

[<span data-ttu-id="f1a1b-181">Microsoft 365의 스푸핑 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="f1a1b-181">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
