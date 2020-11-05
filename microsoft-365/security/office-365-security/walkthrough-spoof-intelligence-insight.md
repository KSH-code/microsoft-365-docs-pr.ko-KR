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
description: 관리자는 스푸핑 인텔리전스 통찰력의 작동 방식을 확인할 수 있습니다. 전자 메일 인증 검사 (SPF, DKIM 또는 DMARC)를 통과 하지 않는 도메인에서 조직으로 합법적으로 전자 메일을 보내는 보낸 사람을 빠르게 확인할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920481"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="65e19-104">연습-Microsoft Defender for Office 365의 스푸핑 인텔리전스 정보</span><span class="sxs-lookup"><span data-stu-id="65e19-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="65e19-105">Office 365 용 Defender가 포함 된 Microsoft 365 조 직에서 스푸핑 인텔리전스 정보를 사용 하 여 인증 되지 않은 전자 메일을 합법적으로 전송 하는 보낸 사람 (SPF, DKIM 또는 DMARC 검사를 통과 하지 않는 도메인의 메시지)을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="65e19-106">알려진 보낸 사람이 알려진 위치에서 스푸핑된 메시지를 전송 하도록 허용 하 여 가양성 (잘못 된 것으로 표시 된 전자 메일 양호)을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="65e19-107">허용 된 스푸핑된 보낸 사람을 모니터링 하면 안전 하지 않은 메시지가 조직에 도착 하지 못하도록 방지 하는 추가 보안 계층을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="65e19-108">보고서 및 insights에 대 한 자세한 내용은 [Security & 준수 센터의 reports and insights](reports-and-insights-in-security-and-compliance.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="65e19-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="65e19-109">이 연습은 보안 & 준수 센터에 대 한 몇 가지 방법 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="65e19-110">보고서 및 insights를 탐색 하는 방법에 대 한 자세한 내용은 [관련 항목](#related-topics) 섹션의 연습을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="65e19-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="65e19-111">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="65e19-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="65e19-112"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="65e19-113">**보안 대시보드** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/searchandinvestigation/dashboard> 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="65e19-114">보안 & 준수 센터에서 둘 이상의 대시보드에서 스푸핑 인텔리전스 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="65e19-115">현재 보고 있는 대시보드에 상관 없이, 통찰력은 동일한 세부 정보를 제공 하며 동일한 작업을 빠르게 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="65e19-116">이 항목의 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-116">You need to be assigned permissions before you can do the procedures in this topic.</span></span> <span data-ttu-id="65e19-117">스푸핑 인텔리전스 이해를 사용 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-117">To use the spoof intelligence insight, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="65e19-118">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="65e19-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="65e19-119">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="65e19-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>
  - <span data-ttu-id="65e19-120">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="65e19-120">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="65e19-121">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="65e19-121">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="65e19-122">Office 365 용 Microsoft Defender의 피싱 방지 정책에서 스푸핑 인텔리전스를 사용 하도록 설정 하 고 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-122">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="65e19-123">자세한 내용은 [Office 용 Microsoft Defender 365에서 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65e19-123">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="65e19-124">스푸핑 인텔리전스를 사용 하 여 인증 되지 않은 메시지를 보내는 보낸 사람을 모니터링 하 고 관리 하려면 [Microsoft 365에서 스푸핑 인텔리전스를 구성](learn-about-spoof-intelligence.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65e19-124">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="65e19-125">보안 & 준수 센터에서 스푸핑 인텔리전스 통찰력을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-125">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="65e19-126">보안 & 준수 센터에서 **위협 관리** \> **대시보드로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="65e19-126">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="65e19-127">**Insights** 행에서 다음 항목 중 하나를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-127">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="65e19-128">**스푸핑 인텔리전스를 사용 하도록 설정** 된 경우: 위장 된 도메인 이라는 것은 **최근 30 일의 인증에 실패 한** 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-128">**Spoof intelligence is enabled** : The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="65e19-129">이 옵션이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-129">This is the default.</span></span>
   - <span data-ttu-id="65e19-130">**스푸핑 지능 사용 안 함** : 명명 된 **스푸핑 보호 사용** 을 선택 하 고이를 클릭 하면 스푸핑 인텔리전스를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-130">**Spoof intelligence is disabled** : The insight in named **Enable Spoof Protection** , and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="65e19-131">대시보드에 대 한 통찰력은 다음과 같은 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-131">The insight on the dashboard shows you information like this:</span></span>

   ![스푸핑 인텔리전스 통찰력 스크린샷](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="65e19-133">이 통찰력에는 두 가지 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-133">This insight has two modes:</span></span>

   - <span data-ttu-id="65e19-134">**통찰력 모드** : 스푸핑 인텔리전스가 사용 하도록 설정 된 경우이 통찰력은 지난 30 일 동안 스푸핑 인텔리전스 기능으로 인해 영향을 받는 메시지 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-134">**Insight mode** : If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="65e19-135">**If mode** : 스푸핑 인텔리전스를 사용 하지 않도록 설정 하면 지난 30 일 동안 스푸핑 인텔리전스 기능으로 인해 *영향을 받는 메시지 수* 를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-135">**What if mode** : If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="65e19-136">어느 방법을 사용 하 든, 파악에 표시 되는 스푸핑된 도메인은 **의심 스러운 도메인 쌍** 및 **의심 되지 않는 도메인 쌍** 으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-136">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="65e19-137">이러한 범주는 검토할 세 가지 다른 버킷으로 세분화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-137">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="65e19-138">**도메인 쌍** 은 보낸 사람 주소와 보내는 인프라의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-138">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="65e19-139">보낸 사람 주소는 전자 메일 클라이언트의 시작 상자에 표시 되는 보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-139">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="65e19-140">이 주소는 `5322.From` 주소 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-140">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="65e19-141">보내는 인프라 또는 보낸 사람은 보내는 IP 주소의 역방향 DNS 조회 (PTR 레코드)에 대 한 조직 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-141">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="65e19-142">보내는 IP 주소에 PTR 레코드가 없으면 보낸 사람은 255.255.255.0 서브넷 마스크가 CIDR 표기법 (/24) 인 보내는 IP로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-142">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="65e19-143">예를 들어 IP 주소가 192.168.100.100 이면 보낸 사람의 전체 IP 주소는 192.168.100.100/24가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-143">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="65e19-144">**의심 스러운 도메인 쌍** 은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-144">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="65e19-145">**신뢰도가 높은 스푸핑** : 전송 패턴 및 도메인의 신뢰도 점수를 기반으로 하 여 도메인은 위조 되 고 이러한 도메인의 메시지가 악성이 될 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-145">**High-confidence spoof** : Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="65e19-146">**일반 신뢰도 스푸핑** : 도메인의 과거 및 신뢰도 점수를 기반으로 하 여 도메인은 스푸핑 되 고 이러한 도메인에서 전송 된 메시지가 합법적 이라는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-146">**Moderate confidence spoof** : Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="65e19-147">가양성은 높은 신뢰도 위장 보다이 범주에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-147">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="65e19-148">**의심 스러운 도메인 쌍** (자동 **복구 스푸핑** 포함): 도메인에서 명시적 전자 메일 인증 검사 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [dkim](use-dkim-to-validate-outbound-email.md)및 [DMARC](use-dmarc-to-validate-email.md))를 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-148">**Non-suspicious domain pairs** (includes **rescued spoof** ): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="65e19-149">그러나 도메인은 암시적 전자 메일 인증 검사 ([복합 인증](email-validation-and-authentication.md#composite-authentication))를 통과 했습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-149">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="65e19-150">따라서 메시지에 대해 스푸핑 방지 동작이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-150">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="65e19-151">스푸핑 인텔리전스 통찰력에서 의심 스러운 도메인 쌍에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="65e19-151">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="65e19-152">스푸핑 인텔리전스 이해에서 도메인 쌍 (높음, 중간 또는 자동 복구)을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-152">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="65e19-153">**스푸핑 인텔리전스** 정보 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-153">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="65e19-154">이 페이지에는 조직에 인증 되지 않은 전자 메일을 보내는 보낸 사람 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-154">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="65e19-155">이 정보는 스푸핑된 메시지에 대 한 권한이 부여 되었는지 또는 추가 작업을 수행 해야 하는지 여부를 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-155">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="65e19-156">메시지 수, 스푸핑이 마지막으로 검색 된 날짜 등을 기준으로 정보를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-156">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="65e19-157">테이블에서 항목을 선택 하 여 도메인 쌍에 대 한 다양 한 정보가 포함 된 세부 정보 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-157">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="65e19-158">정보에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-158">The information includes:</span></span>
   - <span data-ttu-id="65e19-159">이를 파악 한 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-159">Why we caught this.</span></span>
   - <span data-ttu-id="65e19-160">수행 해야 하는 작업</span><span class="sxs-lookup"><span data-stu-id="65e19-160">What you need to do.</span></span>
   - <span data-ttu-id="65e19-161">도메인 요약</span><span class="sxs-lookup"><span data-stu-id="65e19-161">A domain summary.</span></span>
   - <span data-ttu-id="65e19-162">보낸 사람에 대 한 데이터를 WhoIs.</span><span class="sxs-lookup"><span data-stu-id="65e19-162">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="65e19-163">동일한 보낸 사람의 테 넌 트에서 살펴본 유사한 메시지</span><span class="sxs-lookup"><span data-stu-id="65e19-163">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="65e19-164">여기에서 **Allowedtospoof** 수신 허용-보낸 사람 목록에서 도메인 쌍을 추가 하거나 제거 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-164">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![스푸핑 인텔리전스 통찰력 세부 정보 창에 있는 도메인 스크린샷](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="65e19-166">AllowedToSpoof 목록에서 도메인 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="65e19-166">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="65e19-167">도메인 쌍에 대 한 스푸핑 인텔리전스 통찰력의 세부 정보 창에서 AllowedToSpoof (수신 허용-보낸 사람) 목록에 도메인을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-167">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="65e19-168">이에 따라 토글을 설정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-168">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="65e19-169">도메인 쌍을 허용 하면 위장 *된 도메인과 보내는* 인프라를 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-169">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="65e19-170">원본에서 위장 된 도메인의 전자 메일을 허용 하지 않으며 모든 도메인에 대해 보내는 인프라에서 전자 메일을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-170">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="65e19-171">예를 들어 다음 도메인 쌍이 스푸핑된 메시지를 조직에 보낼 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-171">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="65e19-172">*스푸핑된 도메인* : gmail.com "</span><span class="sxs-lookup"><span data-stu-id="65e19-172">*Spoofed Domain* : gmail.com"</span></span>
- <span data-ttu-id="65e19-173">*보내는 인프라* `tms.mx.com` :</span><span class="sxs-lookup"><span data-stu-id="65e19-173">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="65e19-174">해당 도메인 쌍의 전자 메일만 스푸핑 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-174">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="65e19-175">Gmail.com을 스푸핑할 다른 보낸 사람은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-175">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="65e19-176">Tms.mx.com의 다른 도메인에 있는 메시지는 스푸핑 인텔리전스를 통해 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e19-176">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="65e19-177">관련 항목</span><span class="sxs-lookup"><span data-stu-id="65e19-177">Related topics</span></span>

[<span data-ttu-id="65e19-178">Microsoft 365의 스푸핑 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="65e19-178">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
