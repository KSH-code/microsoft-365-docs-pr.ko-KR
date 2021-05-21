---
title: 사용자에 대한 타사 피싱 시뮬레이션 및 필터되지 않은 메시지의 SecOps 사서함 배달 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 관리자는 EOP(Exchange Online Protection)의 고급 배달 정책을 사용하여 지원되는 특정 시나리오(타사 피싱 시뮬레이션 및 SecOps(보안 작업) 사서함으로 배달된 메시지)에서 필터링하지 말아야 하는 메시지를 식별하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bebc094b56a20a43f92d1acf8d374110de43d71
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594124"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="a79ff-103">사용자에 대한 타사 피싱 시뮬레이션 및 필터되지 않은 메시지의 SecOps 사서함 배달 구성</span><span class="sxs-lookup"><span data-stu-id="a79ff-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="a79ff-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="a79ff-104">**Applies to**</span></span>
- [<span data-ttu-id="a79ff-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a79ff-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a79ff-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="a79ff-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a79ff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a79ff-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="a79ff-108">이 문서에서 설명하는 기능은 미리 보기에 있으며, 모든 사람이 사용할 수 있으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="a79ff-109">기본적으로 조직의 [](secure-by-default.md)보안을 유지하기 위해 EOP(Exchange Online Protection)는 맬웨어 또는 높은 신뢰도 피싱 결과를 발생하게 하는 메시지에 대해 수신 허용 목록 또는 필터링 우회를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that result in malware or high confidence phishing verdicts.</span></span> <span data-ttu-id="a79ff-110">그러나 필터되지 않은 메시지를 배달해야 하는 특정 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-110">But there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="a79ff-111">예제:</span><span class="sxs-lookup"><span data-stu-id="a79ff-111">For example:</span></span>

- <span data-ttu-id="a79ff-112">**타사 피싱 시뮬레이션:** 시뮬레이션된 공격은 실제 공격이 조직에 영향을 미치기 전에 취약한 사용자를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="a79ff-113">**SecOps(보안 작업)** 사서함: 보안 팀에서 필터되지 않은 메시지를 수집 및 분석하는 데 사용하는 전용 사서함(좋음과 불량 모두)입니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="a79ff-114">의 _고급_ 배달 정책을 Microsoft 365 이러한 특정 시나리오에서 이러한 메시지가 필터링되지 않도록 방지할 수  <sup>\*</sup> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered<sup>\*</sup>.</span></span> <span data-ttu-id="a79ff-115">고급 배달 정책은 이러한 시나리오의 메시지가 필터링되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-115">The advanced delivery policy ensures that messages in these scenarios are not filtered:</span></span>

- <span data-ttu-id="a79ff-116">EOP 및 Microsoft Defender for Office 365 메시지에 대해 아무 작업도 수행하지 않습니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a79ff-116">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="a79ff-117">스팸 및 피싱에 [대한 ZAP(제로](zero-hour-auto-purge.md) 아워 제거)는 이러한 메시지에 대해 아무 작업도 수행하지 않습니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a79ff-117">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing takes no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="a79ff-118">[이러한 시나리오에서는](alerts.md) 기본 시스템 알림이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-118">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="a79ff-119">[Defender for Defender의](office-365-air.md) AIR Office 365 메시지는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-119">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="a79ff-120">타사 피싱 시뮬레이션을 위한 구체적인 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-120">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="a79ff-121">[관리자 제출은](admin-submission.md) 메시지가 피싱 시뮬레이션 캠페인의 일부이자 실제 위협이 아니라는 자동 응답을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-121">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="a79ff-122">경고와 AIR이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-122">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="a79ff-123">[Defender for Office 365](safe-links.md) 안전한 링크는 이러한 메시지에서 특별히 식별된 URL을 차단하거나 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-123">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="a79ff-124">[Defender for Office 365](safe-attachments.md) 메시지의 첨부 파일은 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-124">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="a79ff-125"><sup>\*</sup> 맬웨어 필터링 또는 맬웨어에 대한 ZAP를 무시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-125"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="a79ff-126">고급 배달 정책으로 식별된 메시지는 보안 위협이 아니기 때문에 메시지는 시스템 오버라이드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-126">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="a79ff-127">관리자는 다음 환경의 이러한 시스템 오버라이드를 필터링하고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-127">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="a79ff-128">계획 2용 Defender의 위협 탐색기 Office 365 검색</span><span class="sxs-lookup"><span data-stu-id="a79ff-128">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="a79ff-129">위협 [탐색기/실시간](mdo-email-entity-page.md) 검색의 전자 메일 엔터티 페이지</span><span class="sxs-lookup"><span data-stu-id="a79ff-129">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="a79ff-130">[위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="a79ff-130">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="a79ff-131">끝점용 Microsoft Defender의 고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="a79ff-131">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="a79ff-132">캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="a79ff-132">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a79ff-133">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="a79ff-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a79ff-134"><https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a79ff-135">고급 배달 페이지로 직접 **이동하기 위해** 를 를 니다. <https://protection.office.com/advanceddelivery></span><span class="sxs-lookup"><span data-stu-id="a79ff-135">To go directly to the **Advanced delivery** page, open <https://protection.office.com/advanceddelivery>.</span></span>

- <span data-ttu-id="a79ff-136">이 문서의 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a79ff-137">고급 배달 정책에서 구성된 설정을 만들거나 수정하거나 제거하려면 보안 &  준수 센터에서 보안  관리자 역할 그룹의 구성원이자 에서 조직 **관리** 역할 그룹의 구성원 Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="a79ff-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Security & Compliance Center** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="a79ff-138">고급 배달 정책에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a79ff-139">자세한 내용은 Security [& Compliance Center의](permissions-in-the-security-and-compliance-center.md) 사용 권한 및 에서 사용 [권한을 Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="a79ff-139">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="a79ff-140">보안 및 & 센터를 사용하여 고급 배달 정책에서 타사 피싱 시뮬레이션 구성</span><span class="sxs-lookup"><span data-stu-id="a79ff-140">Use the Security & Compliance Center to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="a79ff-141">보안 및 & 센터에서 **위협** 관리 정책 \> **고급** \> **배달으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a79ff-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="a79ff-142">고급 배달 **페이지에서** 피싱  시뮬레이션 탭을 선택한 다음 편집 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a79ff-142">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="a79ff-143">열 수 있는 타사 **피싱** 시뮬레이션 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-143">On the **Third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="a79ff-144">**보내는 도메인:** 전자 메일 주소 도메인이 하나 이상 필요합니다(예: contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a79ff-144">**Sending domain**: At least one email address domain is required (for example, contoso.com).</span></span> <span data-ttu-id="a79ff-145">항목을 10개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-145">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="a79ff-146">**IP 보내기:** 유효한 IPv4 주소가 하나 이상 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-146">**Sending IP**: At least one valid IPv4 address is required.</span></span> <span data-ttu-id="a79ff-147">항목을 10개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-147">You can add up to 10 entries.</span></span> <span data-ttu-id="a79ff-148">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-148">Valid values are:</span></span>
     - <span data-ttu-id="a79ff-149">단일 IP: 예: 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="a79ff-149">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="a79ff-150">IP 범위: 예: 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="a79ff-150">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="a79ff-151">CIDR IP: 예: 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="a79ff-151">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="a79ff-152">**허용할** 시뮬레이션 URL: 선택적으로 차단되거나 검색되지 않는 피싱 시뮬레이션 캠페인의 일부인 특정 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-152">**Simulation URLs to allow**: Optionally, enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated.</span></span> <span data-ttu-id="a79ff-153">항목을 10개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-153">You can add up to 10 entries.</span></span>

4. <span data-ttu-id="a79ff-154">완료되면 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a79ff-154">When you're finished, click **Save.**</span></span>

<span data-ttu-id="a79ff-155">구성한 타사 피싱 시뮬레이션 항목이 피싱 시뮬레이션 **탭에** 표시됩니다. 변경하려면 탭에서 **편집을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-155">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="a79ff-156">보안 및 & 센터를 사용하여 고급 배달 정책에서 SecOps 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="a79ff-156">Use the Security & Compliance Center to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="a79ff-157">보안 및 & 센터에서 **위협** 관리 정책 고급 \>  \> **배달으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a79ff-157">In the Security & Compliance Center, go to **Threat Management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="a79ff-158">고급 배달 **페이지에서** **SecOps** 사서함 탭을 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a79ff-158">On the **Advanced delivery** page, select the **SecOps mailbox** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="a79ff-159">**SecOps** 사서함 플라이아웃이 열리면 SecOps 사서함으로 지정하려는 기존 Exchange Online 사서함의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-159">On the **SecOps mailbox** flyout that opens, enter the email addresses of existing Exchange Online mailboxes that you want to designate as SecOps mailboxes.</span></span> <span data-ttu-id="a79ff-160">메일 그룹은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-160">Distribution groups are not allowed.</span></span>

4. <span data-ttu-id="a79ff-161">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-161">When you're finished, click **Save**.</span></span>

<span data-ttu-id="a79ff-162">구성한 SecOps 사서함 항목이 **SecOps** 사서함 탭에 표시됩니다. 변경하려면 탭에서 **편집을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-162">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="a79ff-163">필터링 우회가 필요한 추가 시나리오</span><span class="sxs-lookup"><span data-stu-id="a79ff-163">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="a79ff-164">고급 배달 정책이 도움이 될 수 있는 두 가지 시나리오 외에도 필터링을 무시해야 하는 다른 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-164">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="a79ff-165">**타사 필터:** 도메인의 MX 레코드가  메시지를 Office 365 경우(메시지가 먼저 다른 곳에 라우팅되는 [경우)](secure-by-default.md) 기본적으로 보안을 사용할 *수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="a79ff-165">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span>

  <span data-ttu-id="a79ff-166">타사 필터링을 통해 이미 평가된 메시지에 대해 Microsoft 필터링을 무시하기 위해 메일 흐름 규칙(전송 규칙)을 사용(메일 흐름 규칙을 사용하여 메시지에서 [SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)설정)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-166">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules), see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

- <span data-ttu-id="a79ff-167">**검토 중의** 가양성: 관리자 제출을 통해 Microsoft에서 여전히 분석하고 [](admin-submission.md) 있는 특정 메시지를 일시적으로 허용하여 Microsoft에 잘못 잘못된 것으로 잘못 표시된 알려진 좋은 메시지(가양성)를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-167">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="a79ff-168">모든 오버라이드와 함께 이러한 \*\*\*\* 허용을 일시적으로 만들어 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a79ff-168">As with all overrides, it is **_highly recommended_** that these allowances be made temporarily.</span></span>
