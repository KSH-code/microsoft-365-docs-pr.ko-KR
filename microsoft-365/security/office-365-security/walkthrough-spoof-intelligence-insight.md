---
title: 연습-스푸핑 인텔리전스 통찰력
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
description: 스푸핑 인텔리전스 통찰력은 Office 365 Advanced Threat Protection에서 작동 하는 방법을 참조 하세요.
ms.openlocfilehash: 4ad3de8812e09b73018c02232e3e66e4bec9d041
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630932"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a><span data-ttu-id="93533-103">Microsoft 365의 연습-ATP 스푸핑 인텔리전스 정보</span><span class="sxs-lookup"><span data-stu-id="93533-103">Walkthrough - ATP Spoof intelligence insight in Microsoft 365</span></span>

<span data-ttu-id="93533-104">Microsoft 365 조직에서 ATP (Advanced Threat Protection)를 사용 하는 경우 스푸핑 인텔리전스 정보를 활용 하 여 인증 되지 않은 전자 메일을 합법적으로 전송 하는 보낸 사람을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-104">In Microsoft 365 organizations with Advanced Threat Protection (ATP), you can use the spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email.</span></span> <span data-ttu-id="93533-105">그들에 게 스푸핑된 메시지를 보낼 수 있도록 허용 하면 가양성이 사용자에 게 노출 되는 위험을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93533-105">By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span> <span data-ttu-id="93533-106">또한 스푸핑 인텔리전스 통찰력을 사용 하 여 허용 되는 도메인 쌍을 모니터링 하 고 관리 하 여 추가 보안 계층을 제공 하 고 안전 하지 않은 메시지가 조직에 도착 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-106">You can also use the spoof intelligence insight to monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="93533-107">[보안 & 준수 센터에서 보고서 및 통찰력](reports-and-insights-in-security-and-compliance.md)을 처음 사용할 경우 대시보드를 통해 파악 및 권장 작업으로 쉽게 이동할 수 있는 방법을 확인 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-107">If you're new to [reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>

<span data-ttu-id="93533-108">이 연습은 보안 & 준수 센터에 대 한 몇 가지 방법 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="93533-108">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="93533-109">보고서 및 insights를 탐색 하는 방법에 대 한 자세한 내용은 관련 항목 섹션의 연습을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="93533-109">To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="93533-110">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="93533-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="93533-111"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="93533-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="93533-112">**보안 대시보드** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/searchandinvestigation/dashboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-112">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="93533-113">보안 & 준수 센터에서 둘 이상의 대시보드에서 스푸핑 인텔리전스 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-113">You can view the spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="93533-114">현재 보고 있는 대시보드에 상관 없이, 통찰력은 동일한 세부 정보를 제공 하며 동일한 작업을 빠르게 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-114">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="93533-115">이 절차를 수행하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-115">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="93533-116">스푸핑 인텔리전스 통찰력을 사용 하려면 **조직 관리**, **보안 관리자**또는 **보안 독자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-116">To use the spoof intelligence insight, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="93533-117">보안 & 준수 센터의 역할 그룹에 대 한 자세한 내용은 [보안 & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93533-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="93533-118">ATP 피싱 방지 정책에서 스푸핑 인텔리전스를 사용 하도록 설정 하 고 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-118">You enable and disable spoof intelligence in ATP anti-phishing policies.</span></span> <span data-ttu-id="93533-119">자세한 내용은 [Microsoft 365에서 ATP 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93533-119">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="93533-120">Exchange Online 사서함이 있는 Microsoft 365 조직 및 독립 실행형 EOP (Exchange Online Protection)에서 Exchange Online 사서함이 없는 경우 스푸핑 인텔리전스를 사용 하 여 인증 되지 않은 메시지를 보내는 보낸 사람을 모니터링 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-120">In Microsoft 365 organizations with Exchange Online mailboxes, and in standalone Exchange Online Protection (EOP) without Exchange Online mailboxes, you can use spoof intelligence to monitor and manage senders you are sending you unauthenticated messages.</span></span> <span data-ttu-id="93533-121">자세한 내용은 [Microsoft 365에서 스푸핑 인텔리전스를 구성](learn-about-spoof-intelligence.md)합니다 .를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="93533-121">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="93533-122">보안 & 준수 센터에서 스푸핑 인텔리전스 통찰력을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="93533-122">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="93533-123">보안 & 준수 센터에서 **위협 관리** \> **대시보드로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="93533-123">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="93533-124">**Insights** 행에서 다음 항목 중 하나를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-124">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="93533-125">**스푸핑 인텔리전스를 사용 하도록 설정**된 경우: 위장 된 도메인 이라는 것은 **최근 30 일의 인증에 실패 한**것입니다.</span><span class="sxs-lookup"><span data-stu-id="93533-125">**Spoof intelligence is enabled**: The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="93533-126">이 옵션이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="93533-126">This is the default.</span></span>

   - <span data-ttu-id="93533-127">**스푸핑 지능 사용 안 함**: 명명 된 **스푸핑 보호 사용**을 선택 하 고이를 클릭 하면 스푸핑 인텔리전스를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-127">**Spoof intelligence is disabled**: The insight in named **Enable Spoof Protection**, and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="93533-128">대시보드에 대 한 통찰력은 다음과 같은 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93533-128">The insight on the dashboard shows you information like this:</span></span>

   ![스푸핑 인텔리전스 통찰력 스크린샷](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="93533-130">이 통찰력에는 두 가지 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-130">This insight has two modes:</span></span>

   - <span data-ttu-id="93533-131">**통찰력 모드**입니다.</span><span class="sxs-lookup"><span data-stu-id="93533-131">**Insight mode**.</span></span> <span data-ttu-id="93533-132">스푸핑 정책이 사용 하도록 설정 된 경우에는 지난 30 일 동안 스푸핑 인텔리전스 기능으로 영향을 받은 메일의 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-132">If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="93533-133">**If 모드**</span><span class="sxs-lookup"><span data-stu-id="93533-133">**What if mode**.</span></span> <span data-ttu-id="93533-134">스푸핑 정책이 사용 하도록 설정 되어 있지 않은 경우에는 지난 30 일 동안 스푸핑 인텔리전스 기능으로 *영향을 받은 메일의* 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-134">If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="93533-135">어느 방법을 사용 하 든, 파악에 표시 되는 스푸핑된 도메인은 **의심 스러운 도메인 쌍** 및 **의심 되지 않는 도메인 쌍**으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93533-135">Either way, the spoofed domains displayed in the insight are separated into two categories: **suspicious domain pairs** and **non-suspicious domain pairs**.</span></span> <span data-ttu-id="93533-136">이러한 범주는 검토할 세 가지 다른 버킷으로 세분화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93533-136">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="93533-137">**도메인 쌍** 은 보낸 사람 주소와 보내는 인프라의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="93533-137">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="93533-138">보낸 사람 주소는 전자 메일 클라이언트에 표시 되는 보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="93533-138">The From address is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="93533-139">이 주소는 전자 메일의 작성자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-139">This address identifies the author of the email.</span></span> <span data-ttu-id="93533-140">즉, 메시지 작성을 담당하는 개인 또는 시스템의 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="93533-140">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="93533-141">이 주소는 `5322.From` 주소 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-141">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="93533-142">보내는 인프라 또는 보낸 사람은 보내는 IP 주소의 역방향 DNS 조회 (PTR 레코드)에 대 한 조직 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="93533-142">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="93533-143">보내는 IP 주소에 PTR 레코드가 없으면 보낸 사람은 255.255.255.0 서브넷 마스크가 CIDR 표기법 (/24) 인 보내는 IP로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93533-143">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="93533-144">예를 들어 IP 주소가 192.168.100.100 이면 보낸 사람의 전체 IP 주소는 192.168.100.100/24가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93533-144">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="93533-145">**의심 스러운 도메인 쌍** 은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-145">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="93533-146">**신뢰도가 높은 스푸핑**: Microsoft 365는 해당 도메인의 전송 패턴 및 신뢰도 점수를 기반으로 이러한 도메인이 의심 스 럽 거는 강력한 신호를 수신 했습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-146">**High-confidence spoof**: Microsoft 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="93533-147">Microsoft 365는 도메인이 스푸핑 대상이 고 이러한 도메인에서 전송 된 메시지가 합법적 일 가능성이 낮은 지를 확실 하 게 확신 합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-147">Microsoft 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span>

   - <span data-ttu-id="93533-148">**보통 신뢰 스푸핑**: Microsoft 365는 이러한 도메인이 의심 됨을 알리는 일반 신호 및 도메인의 전송 패턴 및 신뢰도 점수를 수신 했습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-148">**Moderate confidence spoof**: Microsoft 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="93533-149">Office 365에서는 도메인이 스푸핑 되 고 이러한 도메인에서 전송 된 메시지가 합법적 인지 확실 하 게 확신 합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-149">Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="93533-150">이 버킷에는 신뢰도가 높은 위장 버킷 보다 더 많은 FPs가 포함 될 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-150">This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span>

   - <span data-ttu-id="93533-151">**의심 스러운 도메인 쌍** (자동 **복구 스푸핑**포함): 자동 복구 스푸핑이 명시적 인증 검사 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [dkim](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md))에 실패 했지만 암시적 전자 메일 인증 검사 ([복합 인증](email-validation-and-authentication.md#composite-authentication))를 통과 한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="93533-151">**Non-suspicious domain pairs** (includes **rescued spoof**): Rescued spoof are domains that have failed the explicit authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)) but passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="93533-152">따라서 Microsoft 365는 사용자를 대신 하 여 메일을 자동 복구 하며, 메시지에 대해 스푸핑 방지 작업을 수행 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-152">As a result, Microsoft 365 rescued the mail on your behalf and no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="93533-153">스푸핑 인텔리전스 통찰력에서 의심 스러운 도메인 쌍에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="93533-153">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="93533-154">스푸핑 인텔리전스 이해에서 도메인 쌍 (높음, 중간 또는 자동 복구)을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-154">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="93533-155">승인 되지 않은 메일을 조직으로 보내는 보낸 사람 목록을 보여 주는 **스푸핑 인텔리전스 이해** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93533-155">The **Spoof Intelligence insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization.</span></span> <span data-ttu-id="93533-156">이 페이지의 정보는 스푸핑된 메시지에 대 한 권한이 부여 되었는지 또는 추가 작업을 수행 해야 하는지 여부를 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93533-156">The information on this page helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span> <span data-ttu-id="93533-157">메시지 수, 스푸핑이 마지막으로 검색 된 날짜 등을 기준으로 정보를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-157">You can sort the information by message count, the date the spoof was last detected, and more.</span></span> <span data-ttu-id="93533-158">(예를 들어 **메시지 수** 또는 **마지막으로 본**것과 같은 열 머리글을 클릭 합니다.)</span><span class="sxs-lookup"><span data-stu-id="93533-158">(Click column headings, such as **Message count** or **Last seen**, for example.)</span></span>

2. <span data-ttu-id="93533-159">테이블에서 항목을 선택 하 여 도메인 쌍에 대 한 다양 한 정보가 포함 된 세부 정보 창 (이 예에서는 사용자가 수행 해야 하는 작업, 보낸 사람에 대 한 WhoIs 데이터 및 같은 보낸 사람에 대 한 테 넌 트에 표시 되는 유사한 전자 메일)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-159">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender.</span></span> <span data-ttu-id="93533-160">여기에서 **Allowedtospoof** 수신 허용-보낸 사람 목록에서 도메인 쌍을 추가 하거나 제거 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-160">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![스푸핑 인텔리전스 통찰력 세부 정보 창에 있는 도메인 스크린샷](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="93533-162">AllowedToSpoof 수신 허용-보낸 사람 목록에서 도메인 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="93533-162">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="93533-163">스푸핑 인텔리전스 이해의 세부 정보 창에서 도메인 쌍을 검토 하는 동시에 AllowedToSpoof 수신 허용-보낸 사람 목록에서 도메인을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="93533-163">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight.</span></span> <span data-ttu-id="93533-164">이에 따라 토글을 설정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93533-164">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="93533-165">이렇게 하면 스푸핑된 도메인 및 보내는 인프라의 고유한 도메인 쌍 조합이 수정 되며, 격리 된 전체 스푸핑된 도메인 또는 보내는 인프라에 대 한 검사는 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-165">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation.</span></span>

<span data-ttu-id="93533-166">예를 들어 다음 도메인 쌍을 ' AllowedToSpoof ' 보낸 사람 목록: *스푸핑된 도메인* "gmail.com"에 추가 하 고 인프라 " *Tms"를* *보내는* 경우 해당 도메인 쌍의 메일만 스푸핑 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93533-166">For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and *Sending Infrastructure* "tms *.mx.com",* then only mail from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="93533-167">다른 보낸 사람이 "gmail.com"로 위장 하려고 하 고 "tms.mx.com" 스푸핑이 시도 하는 다른 도메인은 스푸핑 인텔리전스로 계속 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93533-167">Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="93533-168">관련 항목</span><span class="sxs-lookup"><span data-stu-id="93533-168">Related topics</span></span>

[<span data-ttu-id="93533-169">Microsoft 365의 스푸핑 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="93533-169">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)

[<span data-ttu-id="93533-170">연습 - 대시보드에서 통찰력에 이르기까지</span><span class="sxs-lookup"><span data-stu-id="93533-170">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)

[<span data-ttu-id="93533-171">연습 - 자세한 보고서에서 통찰력에 이르기까지</span><span class="sxs-lookup"><span data-stu-id="93533-171">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)

[<span data-ttu-id="93533-172">연습 - 통찰력에서 자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="93533-172">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)