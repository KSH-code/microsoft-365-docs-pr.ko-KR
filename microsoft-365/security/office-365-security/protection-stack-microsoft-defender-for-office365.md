---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: Microsoft Defender for Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01ad901f7f746d9b5d2c50632c1344701120c20f
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538690"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9225f-103">Office 365용 Microsoft Defender의 단계별 위협 방지</span><span class="sxs-lookup"><span data-stu-id="9225f-103">Step-by-step threat protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9225f-104">Microsoft Defender for Office 365 보호 또는 필터링 스택은 이 문서에서와 같은 4단계로 세분화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-104">The Microsoft Defender for Office 365 protection or filtering stack can be broken out into 4 phases, as in this article.</span></span> <span data-ttu-id="9225f-105">일반적으로 받는 메일은 배달 전에 이러한 모든 단계를 통과하지만 전자 메일이 받는 실제 경로는 조직의 전자 메일 구성에 대한 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-105">Generally speaking, incoming mail passes through all of these phases before delivery, but the actual path email takes is subject to an organization's Defender for Office 365 configuration.</span></span>

> [!TIP]
> <span data-ttu-id="9225f-106">보호를 위한 Defender의 모든 4단계의 통합 그래픽에 대해 이 문서가 끝날 Office 365 계속 주시하세요! </span><span class="sxs-lookup"><span data-stu-id="9225f-106">Stay tuned till the end of this article for a *unified* graphic of all 4 phases of Defender for Office 365 protection!</span></span>

## <a name="phase-1---edge-protection"></a><span data-ttu-id="9225f-107">1단계 - 에지 보호</span><span class="sxs-lookup"><span data-stu-id="9225f-107">Phase 1 - Edge Protection</span></span>

<span data-ttu-id="9225f-108">안타깝게도 한  번 중요한 Edge 블록은 이제 악의적인 악의적인 악의를 극복할 수 있는 비교적 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-108">Unfortunately, Edge blocks that were once *critical* are now relatively simple for bad actors to overcome.</span></span> <span data-ttu-id="9225f-109">시간이 지날 때 더 적은 트래픽이 여기에서 차단되지만 스택의 중요한 부분으로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-109">Over time, less traffic is blocked here, but it remains an important part of the stack.</span></span>  

<span data-ttu-id="9225f-110">Edge 블록은 자동으로 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-110">Edge blocks are designed to be automatic.</span></span> <span data-ttu-id="9225f-111">가짓 긍정의 경우 보낸 사람에 대해 알림을 보내고 문제를 해결하는 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-111">In the case of false positive, senders will be notified and told how to address their issue.</span></span> <span data-ttu-id="9225f-112">신뢰도가 제한된 신뢰할 수 있는 파트너의 커넥터는 새 끝점을 온보드할 때 결과성을 보장하거나 임시 재지정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-112">Connectors from trusted partners with limited reputation can ensure deliverability, or temporary overrides can be put in place, when onboarding new endpoints.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="Defender for Office 365 1단계는 Edge 보호입니다.":::

1. <span data-ttu-id="9225f-114">**네트워크 제한은** 특정 인프라 Office 365 전송할 수 있는 메시지 수를 제한하여 DOS(서비스 거부) 공격으로부터 고객 및 인프라를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-114">**Network throttling** protects Office 365 infrastructure and customers from Denial of Service (DOS) attacks by limiting the number of messages that can be submitted by a specific set of infrastructure.</span></span>

2. <span data-ttu-id="9225f-115">**IP 신뢰도 및** 스로틀은 알려진 잘못된 연결 IP 주소에서 전송되는 메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-115">**IP reputation and throttling** will block messages being sent from known bad connecting IP addresses.</span></span> <span data-ttu-id="9225f-116">특정 IP가 짧은 시간 동안 많은 메시지를 보내는 경우 이러한 메시지는 스로틀됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-116">If a specific IP sends many messages in a short period of time they will be throttled.</span></span>

3. <span data-ttu-id="9225f-117">**도메인 신뢰도는** 알려진 잘못된 도메인에서 전송되는 모든 메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-117">**Domain reputation** will block any messages being sent from a known bad domain.</span></span>

4. <span data-ttu-id="9225f-118">**디렉터리 기반 에지 필터링** 차단은 SMTP를 통해 조직의 디렉터리 정보를 수집하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-118">**Directory-based edge filtering** blocks attempts to harvest an organization's directory information through SMTP.</span></span>

5. <span data-ttu-id="9225f-119">**후방산 탐지는** 잘못된 NDRs(배달 못 한 보고서)를 통해 조직이 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-119">**Backscatter detection** prevents an organization from being attacked through invalid non-delivery reports (NDRs).</span></span>

6. <span data-ttu-id="9225f-120">**커넥터에 대한** 향상된 필터링은 트래픽이 다른 장치에 도달하기 전에 다른 장치를 통과하는 경우에도 인증 Office 365.</span><span class="sxs-lookup"><span data-stu-id="9225f-120">**Enhanced filtering for connectors** preserves authentication information even when traffic passes through another device before it reaches Office 365.</span></span> <span data-ttu-id="9225f-121">이 기능을 사용하면 복잡한 또는 하이브리드 라우팅 시나리오에서라도 지루한 클러스터링, 스푸핑 방지 및 피싱 방지 기계 학습 모델을 비롯한 필터링 스택 정확도가 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-121">This improves filtering stack accuracy, including heuristic clustering, anti-spoofing, and anti-phishing machine learning models, even when in complex or hybrid routing scenarios.</span></span>

## <a name="phase-2---sender-intelligence"></a><span data-ttu-id="9225f-122">2단계 - 보낸 사람 인텔리전스</span><span class="sxs-lookup"><span data-stu-id="9225f-122">Phase 2 - Sender Intelligence</span></span>

<span data-ttu-id="9225f-123">보낸 사람 인텔리전스 기능은 스팸, 대량, 가장 및 허가되지 않은 스푸핑 메시지를 탐지하는 데 중요하며 피싱 검색에도 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-123">Features in sender intelligence are critical for catching spam, bulk, impersonation, and unauthorized spoof messages, and also factor into phish detection.</span></span> <span data-ttu-id="9225f-124">이러한 기능은 대부분 개별적으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-124">Most of these features are individually configurable.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="MDO의 필터링 2단계는 보낸 사람 인텔리전스입니다.":::

1. <span data-ttu-id="9225f-126">**계정 손상 감지** 트리거 및 경고는 계정이 손상과 일관된 변호 동작이 있는 경우 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-126">**Account compromise detection** triggers and alerts are raised when an account has anomalous behavior, consistent with compromise.</span></span> <span data-ttu-id="9225f-127">경우에 따라 사용자 계정이 차단된 후 조직의 보안 운영 팀에서 문제를 해결할 때까지 추가 전자 메일 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-127">In some cases, the user account is blocked and prevented from sending any further email messages until the issue is resolved by an organization's security operations team.</span></span>

2. <span data-ttu-id="9225f-128">**전자 메일 인증에는** 보낸 사람이 인증된 메일러를 인증할 수 있도록 클라우드에 고객이 구성한 방법과 방법이 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-128">**Email Authentication** involves both customer configured methods and methods set up in the Cloud, aimed at ensuring that senders are authorized, authentic mailers.</span></span> <span data-ttu-id="9225f-129">이러한 메서드는 스푸핑을 저항합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-129">These methods resist spoofing.</span></span>
    - <span data-ttu-id="9225f-130">**SPF는** 조직을 대신하여 메일을 보낼 수 있는 IP 주소 및 서버를 나열하는 DNS TXT 레코드를 기반으로 메일을 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-130">**SPF** can reject mails based on DNS TXT records that list IP addresses and servers allowed to send mail on the organization's behalf.</span></span>
    - <span data-ttu-id="9225f-131">**DKIM은** 보낸 사람 인증을 하는 암호화된 서명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-131">**DKIM** provides an encrypted signature that authenticates the sender.</span></span>
    - <span data-ttu-id="9225f-132">**DMARC를** 사용하면 관리자가 SPF 및 DKIM을 도메인에 필요한 것으로 표시하고 이러한 두 기술의 결과 간에 정렬을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-132">**DMARC** lets admins mark SPF and DKIM as required in their domain and enforces alignment between the results of these two technologies.</span></span>
    - <span data-ttu-id="9225f-133">**ARC는** 고객이 구성되지 않지만 인증 체인을 기록하는 동안 메일링 목록에서 전달 작업을 위해 DMARC를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-133">**ARC** is not customer configured, but builds on DMARC to work with forwarding in mailing lists, while recording an authentication chain.</span></span>

3. <span data-ttu-id="9225f-134">**스푸핑** 인텔리전스를 사용하면 조직 또는 알려진 외부 도메인을 모방하는 악의적인 보낸 사람으로부터 '스푸핑'(즉, 다른 계정을 대신하여 메일을 보내거나 메일링 목록에 전달)을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-134">**Spoof intelligence** is capable of filtering those allowed to 'spoof' (that is, those sending mail on behalf of another account, or forwarding for a mailing list) from malicious senders who imitate organizational or known external domains.</span></span> <span data-ttu-id="9225f-135">스팸 및 피싱 메시지를 배달하기 위해 스푸핑한 보낸 사람과 합법적인 '대신' 메일을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-135">It separates legitimate 'on behalf of' mail from senders who spoof to deliver spam and phishing messages.</span></span>

    <span data-ttu-id="9225f-136">**조직 내 스푸핑** 인텔리전스가 조직 내의 도메인에서 스푸핑 시도를 감지하고 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-136">**Intra-org spoof intelligence** detects and blocks spoof attempts from a domain within the organization.</span></span>

4. <span data-ttu-id="9225f-137">**도메인 간 스푸핑 인텔리전스가** 조직 외부의 도메인에서 스푸핑 시도를 감지하고 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-137">**Cross-domain spoof intelligence** detects and blocks spoof attempts from a domain outside of the organization.</span></span>

5. <span data-ttu-id="9225f-138">**대량 필터링을** 통해 관리자는 메시지를 대량 보낸 사람이 보낸 것인지 여부를 나타내는 BCL(대량 신뢰 수준)을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-138">**Bulk filtering** lets admins configure a bulk confidence level (BCL) indicating whether the message was sent from a bulk sender.</span></span> <span data-ttu-id="9225f-139">관리자는 스팸 방지 정책에서 대량 슬라이더를 사용하여 스팸으로 취급할 대량 메일 수준을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-139">Administrators can use the Bulk Slider in the Antispam policy to decide what level of bulk mail to treat as spam.</span></span>

6. <span data-ttu-id="9225f-140">**사서함 인텔리전스는** 표준 사용자 전자 메일 동작에서 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-140">**Mailbox intelligence** learns from standard user email behaviors.</span></span> <span data-ttu-id="9225f-141">사용자의 통신 그래프를 활용하여 보낸 사람이 사용자가 일반적으로 통신하는 사람으로만 나타나지만 실제로 악의적인 경우를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-141">It leverages a user's communication graph to detect when a sender only appears to be someone the user usually communicates with, but is actually malicious.</span></span> <span data-ttu-id="9225f-142">이 메서드는 가장을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-142">This method detects impersonation.</span></span>

7. <span data-ttu-id="9225f-143">**사서함 인텔리전스 가장은** 각 사용자의 개별 보낸 사람 맵에 따라 향상된 가장 결과를 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-143">**Mailbox intelligence impersonation** enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="9225f-144">이 기능을 사용하도록 설정하면 가장을 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-144">When enabled, this feature helps to identify impersonation.</span></span>

8. <span data-ttu-id="9225f-145">**사용자 가장을** 통해 관리자는 가장될 가능성이 높은 대상 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-145">**User impersonation** allows an admin to create a list of high value targets likely to be impersonated.</span></span> <span data-ttu-id="9225f-146">보낸 사람이 보호되는 고가치 계정과 같은 이름과 주소만 있는 것으로 나타나는 메일이 도착하면 메일이 표시되거나 태그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-146">If a mail arrives where the sender only appears to have the same name and address as the protected high value account, the mail is marked or tagged.</span></span> <span data-ttu-id="9225f-147">(예: *trα cye@contoso.com* 의 *경우 tracye@contoso.com).*</span><span class="sxs-lookup"><span data-stu-id="9225f-147">(For example, *trαcye@contoso.com* for *tracye@contoso.com*).</span></span>

9. <span data-ttu-id="9225f-148">**도메인 가장은** 받는 사람의 도메인과 유사하고 내부 도메인처럼 보이게 하려는 도메인을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-148">**Domain impersonation** detects domains that are similar to the recipient's domain and that attempt to look like an internal domain.</span></span> <span data-ttu-id="9225f-149">예를 들어 이 가장은 tracye@liw *re.com 가장을* *tracye@litware.com.*</span><span class="sxs-lookup"><span data-stu-id="9225f-149">For example, this impersonation *tracye@liwαre.com* for *tracye@litware.com*.</span></span>

## <a name="phase-3---content-filtering"></a><span data-ttu-id="9225f-150">3단계 - 콘텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="9225f-150">Phase 3 - Content Filtering</span></span>

<span data-ttu-id="9225f-151">이 단계에서 필터링 스택은 하이퍼링크 및 첨부 파일을 포함하여 메일의 특정 내용을 처리하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-151">In this phase the filtering stack begins to handle the specific contents of the mail, including its hyperlinks and attachments.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="MDO의 필터링 3단계는 콘텐츠 필터링입니다.":::

1. <span data-ttu-id="9225f-153">**전송 규칙(메일** 흐름 규칙 또는 Exchange 전송 규칙)을 사용하면 메시지에 대해 동등하게 광범위한 조건이 충족될 때 관리자가 광범위한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-153">**Transport rules** (also known as mail flow rules or Exchange transport rules) allow an admin to take a wide range of actions when an equally wide range of conditions are met for a message.</span></span> <span data-ttu-id="9225f-154">조직을 통과하는 모든 메시지는 사용 가능한 메일 흐름 규칙/전송 규칙에 대해 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-154">All messages that flow through your organization are evaluated against the enabled mail flow rules / transport rules.</span></span>

2. <span data-ttu-id="9225f-155">**Microsoft Defender 바이러스 백신** 및 두 *개의* 타사 바이러스 백신 엔진을 사용하여 첨부 파일에서 알려진 모든 맬웨어를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-155">**Microsoft Defender Antivirus** and two *third-party Antivirus engines* are used to detect all known malware in attachments.</span></span>

3. <span data-ttu-id="9225f-156">AV(바이러스 백신) 엔진은 모든 첨부 파일을 true로 입력하는  데도 사용 하여 유형 차단은 관리자가 지정하는 유형의 모든 첨부 파일을 차단할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-156">The anti-virus (AV) engines are also used to true-type all attachments, so that **Type blocking** can block all attachments of types the admin specifies.</span></span>

4. <span data-ttu-id="9225f-157">Microsoft Defender for Office 365 악의적인 첨부 파일을 감지할 때마다 파일의 해시와 활성 콘텐츠의 해시가 EOP(Exchange Online Protection) 신뢰도에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-157">Whenever Microsoft Defender for Office 365 detects a malicious attachment, the file's hash, and a hash of its active content, are added to Exchange Online Protection (EOP) reputation.</span></span> <span data-ttu-id="9225f-158">**첨부 파일 신뢰도 차단은** MSAV 클라우드 통화를 통해 모든 Office 365 및 끝점에서 해당 파일을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-158">**Attachment reputation blocking** will block that file across all Office 365, and on endpoints, through MSAV cloud calls.</span></span>

5. <span data-ttu-id="9225f-159">**추론 클러스터링은** 배달 추론에 따라 파일이 의심스러운지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-159">**Heuristic clustering** can determine that a file is suspicious based on delivery heuristics.</span></span> <span data-ttu-id="9225f-160">의심스러운 첨부 파일이 발견된 경우 전체 캠페인이 일시 중지된 후 파일이 샌드박스에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-160">When a suspicious attachment is found, the entire campaign pauses, and the file is sandboxed.</span></span> <span data-ttu-id="9225f-161">파일이 악성으로 발견된 경우 전체 캠페인이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-161">If the file is found to be malicious, the entire campaign is blocked.</span></span>

6. <span data-ttu-id="9225f-162">**기계 학습 모델은** 피싱 시도를 감지하기 위해 메시지의 헤더, 본문 콘텐츠 및 URL에 대해 행동합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-162">**Machine learning models** act on the header, body content, and URLs of a message to detect phishing attempts.</span></span>

7. <span data-ttu-id="9225f-163">Microsoft는 URL 신뢰도 차단의 타사 피드의 URL 신뢰도뿐만 아니라 URL 샌드박스에서 신뢰도 확인을 사용하여 알려진 악성 URL이 있는 메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-163">Microsoft uses a determination of reputation from URL sandboxing as well as URL reputation from third party feeds in **URL reputation blocking**, to block any message with a known malicious URL.</span></span>

8. <span data-ttu-id="9225f-164">**콘텐츠 추론은** 기계 학습 모델을 사용하여 메시지 본문 내의 구조 및 단어 빈도에 따라 의심스러운 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-164">**Content heuristics** can detect suspicious messages based on structure and word frequency within the body of the message, using machine learning models.</span></span>

9. <span data-ttu-id="9225f-165">**안전한 첨부 파일** 샌드박스는 동적 분석을 사용하여 전에 볼 수 없는 위협을 감지하여 Office 365 고객을 위해 Defender의 모든 첨부 파일을 샌드박스합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-165">**Safe Attachments** sandboxes every attachment for Defender for Office 365 customers, using dynamic analysis to detect never-before seen threats.</span></span>

10. <span data-ttu-id="9225f-166">**연결된 콘텐츠** 검색에서는 전자 메일의 파일에 대한 모든 URL을 첨부 파일로 취급하고 배달 시 파일을 비동기적으로 샌드박스로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-166">**Linked content detonation** treats every URL linking to a file in an email as an attachment, asynchronously sandboxing the file at the time of delivery.</span></span>

11. <span data-ttu-id="9225f-167">**URL 검색은** 업스트림 피싱 방지 기술에서 메시지 또는 URL이 의심스러운 것으로 발견될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-167">**URL Detonation** happens when upstream anti-phishing technology finds a message or URL to be suspicious.</span></span> <span data-ttu-id="9225f-168">URL 디버그 샌드박스는 배달 시 메시지의 URL을 샌드박스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-168">URL detonation sandboxes the URLs in the message at the time of delivery.</span></span>

## <a name="phase-4---post-delivery-protection"></a><span data-ttu-id="9225f-169">4단계 - 배달 후 보호</span><span class="sxs-lookup"><span data-stu-id="9225f-169">Phase 4 - Post-Delivery Protection</span></span>

<span data-ttu-id="9225f-170">마지막 단계는 메일 또는 파일 배달 후, 다양한 사서함 및 파일에 있는 메일과 클라이언트에 나타나는 링크에 대해 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9225f-170">The last stage takes place after mail or file delivery, acting on mail that is in various mailboxes and files and links that appear in clients like Microsoft Teams.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="Defender for Office 365 4단계는 배달 후 보호입니다.":::

1. <span data-ttu-id="9225f-172">**안전한 링크는** MDO의 클릭 시간 보호 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-172">**Safe Links** is MDO's time-of-click protection.</span></span> <span data-ttu-id="9225f-173">모든 메시지의 모든 URL은 Microsoft 안전 링크 서버를 지점으로 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-173">Every URL in every message is wrapped to point to Microsoft Safe Links servers.</span></span> <span data-ttu-id="9225f-174">URL을 클릭하면 사용자가 대상 사이트로 리디렉션되기 전에 최신 신뢰도에 대해 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-174">When a URL is clicked it is checked against the latest reputation, before the user is redirected to the target site.</span></span> <span data-ttu-id="9225f-175">URL은 비동기적으로 샌드박스가 적용되어 신뢰도를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-175">The URL is asynchronously sandboxed to update its reputation.</span></span>

2. <span data-ttu-id="9225f-176">**피싱 Zero-Hour ZAP(자동 제거)는** 이미 배달된 악성 피싱 메시지를 Exchange Online 중화합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-176">**Phish Zero-Hour Auto-purge (ZAP)** retroactively detects and neutralizes malicious phishing messages that have already been delivered to Exchange Online mailboxes.</span></span>

3. <span data-ttu-id="9225f-177">**맬웨어 ZAP는** 이미 사서함에 배달된 악성 맬웨어 메시지를 소급적으로 감지하고 Exchange Online 중화합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-177">**Malware ZAP** retroactively detects and neutralizes malicious malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

4. <span data-ttu-id="9225f-178">**스팸 ZAP는** 이미 해당 사서함으로 배달된 악성 스팸 메시지를 Exchange Online 중화합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-178">**Spam ZAP** retroactively detects and neutralizes malicious spam messages that have already been delivered to Exchange Online mailboxes.</span></span>

5. <span data-ttu-id="9225f-179">**캠페인 보기를** 통해 관리자는 자동화 없이 모든 팀보다 더 빠르고 완벽하게 공격의 큰 그림을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-179">**Campaign Views** let administrators see the big picture of an attack, faster and more completely, than any team could without automation.</span></span> <span data-ttu-id="9225f-180">Microsoft는 전체 서비스에서 방대한 양의 피싱 방지, 스팸 방지 및 맬웨어 방지 데이터를 활용하여 캠페인을 식별하고, 관리자는 다운로드 가능한 캠페인 쓰기에서 사용할 수 있는 대상, 영향 및 흐름을 포함하여 시작부터 끝까지 조사할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-180">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns, and then allows admins to investigate them from start to end, including targets, impacts, and flows, that are also available in a downloadable campaign write-up.</span></span>

6. <span data-ttu-id="9225f-181">**보고서 메시지** 추가 기능을 사용하면 추가 분석을 위해 가음성(양호한 전자 메일, 잘못 표시된 양호한 전자 *메일)* 또는 거짓 부정(양호한 것으로 표시된 잘못된 전자 메일)을 Microsoft에 쉽게 보고할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="9225f-181">**The Report Message add-ins** enable people to easily report false positives (good email, mistakenly marked as *bad*) or false negatives (bad email marked as *good*) to Microsoft for further analysis.</span></span>

7. <span data-ttu-id="9225f-182">**Office** 클라이언트에 대한 안전한 링크는 기본적으로 Word, Office 및 클라이언트와 같은 Office 안전한 링크 PowerPoint 제공합니다Excel.</span><span class="sxs-lookup"><span data-stu-id="9225f-182">**Safe Links for Office clients** offers the same Safe Links time-of-click protection, natively, inside of Office clients like Word, PowerPoint, and Excel.</span></span>

8. <span data-ttu-id="9225f-183">**OneDrive,** SharePoint 및 Teams 보호는 기본적으로 OneDrive, SharePoint 및 파일 내부에서 악성 파일에 대해 동일한 안전 첨부 파일 보호를 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9225f-183">**Protection for OneDrive, SharePoint, and Teams** offers the same Safe Attachments protection against malicious files, natively, inside of OneDrive, SharePoint, and Microsoft Teams.</span></span>

9. <span data-ttu-id="9225f-184">배달 후 파일을 지점하는 URL을 선택하면  링크된 콘텐츠 검색에서 파일의 샌드박스가 완료되어 URL이 안전한 것으로 확인될 때까지 경고 페이지를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-184">When a URL that points to a file is selected post delivery, **linked content detonation** displays a warning page until the sandboxing of the file is complete, and the URL is found to be safe.</span></span>


## <a name="the-filtering-stack-diagram"></a><span data-ttu-id="9225f-185">필터링 스택 다이어그램</span><span class="sxs-lookup"><span data-stu-id="9225f-185">The filtering stack diagram</span></span>

<span data-ttu-id="9225f-186">최종 다이어그램(다이어그램을 구성하는 모든 부분과)은 제품이 커지고 개발함에 따라 변경될 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="9225f-186">The final diagram (as with all parts of the diagram composing it) *is subject to change as the product grows and develops*.</span></span> <span data-ttu-id="9225f-187">업데이트 후 요청해야  하는 경우 이 페이지를 책갈피로 설정하고 아래쪽에 있는 피드백 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-187">Bookmark this page and use the **feedback** option you'll find at the bottom if you need to ask after updates.</span></span> <span data-ttu-id="9225f-188">레코드의 경우 모든 단계가 순서대로 스택입니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-188">For your records, this is the the stack with all the phases in order:</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="MDO의 모든 필터링 단계는 1에서 4까지 순서대로 진행됩니다.":::

## <a name="more-information"></a><span data-ttu-id="9225f-190">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="9225f-190">More information</span></span>

<span data-ttu-id="9225f-191">현재 _에 대해 Microsoft Defender를 설정해야 Office 365 \*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9225f-191">Do you need to set up Microsoft Defender for Office 365 \***right now** _?</span></span> <span data-ttu-id="9225f-192">이 스택(_now\*)을 사용하여 [](protect-against-threats.md) 이 단계별 단계를 통해 조직 보호를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-192">Use this stack, _now\*, with [this step-by-step](protect-against-threats.md) to start protecting your organization.</span></span>

<span data-ttu-id="9225f-193">MSFTTracyP 및 이 콘텐츠에 대한 *Giulian Garruba에게* 작성 팀의 특별 감사입니다.</span><span class="sxs-lookup"><span data-stu-id="9225f-193">*Special thanks from MSFTTracyP and the docs writing team to Giulian Garruba for this content*.</span></span>
