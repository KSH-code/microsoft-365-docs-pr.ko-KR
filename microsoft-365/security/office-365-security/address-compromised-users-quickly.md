---
title: 자동화된 조사 및 응답을 통해 손상된 사용자 계정 해결
keywords: AIR, autoIR, ATP, 자동화된, 조사, 대응, 수정, 위협, 고급, 위협, 보호, 손상
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Office 365 계획 2용 Microsoft Defender의 자동화된 조사 및 응답 기능을 통해 손상된 사용자 계정을 검색하고 처리하는 프로세스를 빠르게 진행하는 방법에 대해 자세히 알아보는 방법을 설명하는 정보를 제공합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1dda8c9b4aec30fd35efa153aaf032eee23b5e8a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288744"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="72a80-104">자동화된 조사 및 응답을 통해 손상된 사용자 계정 해결</span><span class="sxs-lookup"><span data-stu-id="72a80-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="72a80-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="72a80-105">**Applies to**</span></span>
- [<span data-ttu-id="72a80-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="72a80-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="72a80-107">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="72a80-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="72a80-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72a80-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


<span data-ttu-id="72a80-109">[Office 365 계획 2용 Microsoft Defender에는](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 강력한 자동화된 조사 및 대응(AIR) 기능이 포함되어 있습니다. [](office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="72a80-109">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="72a80-110">이러한 기능을 통해 보안 운영 팀이 위협을 처리하고 많은 시간과 노력을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="72a80-111">Microsoft는 보안 기능을 지속적으로 개선하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="72a80-112">최근에는 손상된 사용자 보안 플레이북(현재 미리 보기에서)을 포함하도록 AIR 기능이 개선되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="72a80-113">손상된 사용자 보안 플레이북에 대한 자세한 내용은 이 문서를 읽어 하세요.</span><span class="sxs-lookup"><span data-stu-id="72a80-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="72a80-114">추가 세부 정보는 블로그 게시물 속도를 통해 사용자 손상을 감지하고 대응하고 [Microsoft Defender for Office 365를](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) 통해 위반 범위를 제한하세요.</span><span class="sxs-lookup"><span data-stu-id="72a80-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![손상된 사용자에 대한 자동화된 조사](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="72a80-116">손상된 사용자 보안 플레이북을 사용하면 조직의 보안 팀에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="72a80-117">손상된 사용자 계정 검색 속도를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="72a80-118">계정이 손상된 경우 위반 범위를 제한합니다. 및</span><span class="sxs-lookup"><span data-stu-id="72a80-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="72a80-119">손상된 사용자에게 보다 효과적으로 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="72a80-120">손상된 사용자 경고</span><span class="sxs-lookup"><span data-stu-id="72a80-120">Compromised user alerts</span></span>

<span data-ttu-id="72a80-121">사용자 계정이 손상되면 이상하거나 이상한 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="72a80-122">예를 들어 피싱 및 스팸 메시지는 신뢰할 수 있는 사용자 계정에서 내부적으로 전송될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="72a80-123">Office 365용 Defender는 Office 365 내의 전자 메일 패턴 및 공동 작업 활동에서 이러한 변호를 감지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="72a80-124">이 경우 경고가 트리거되면 위협 완화 프로세스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="72a80-125">예를 들어 다음은 의심스러운 전자 메일을 보내기 때문에 트리거된 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![의심스러운 전자 메일 보내기 때문에 트리거된 경고](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="72a80-127">다음은 사용자에 대한 전송 제한에 도달할 때 트리거된 경고의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![전송 제한에 도달하여 트리거된 경고](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="72a80-129">손상된 사용자 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="72a80-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="72a80-130">사용자 계정이 손상되면 경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="72a80-131">경우에 따라 해당 사용자 계정은 조직의 보안 운영 팀에서 문제를 해결할 때까지 추가 전자 메일 메시지를 보내지 못하도록 차단 및 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="72a80-132">그 외의 경우에는 자동화된 조사가 시작되어 보안 팀에서 권장 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="72a80-133">제한된 사용자 보기 및 조사</span><span class="sxs-lookup"><span data-stu-id="72a80-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="72a80-134">자동화된 조사에 대한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="72a80-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="72a80-135">다음 작업을 수행하려면 적절한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="72a80-136">[AIR 기능을 사용하려면 필요한 사용 권한을 참조합니다.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="72a80-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="72a80-137">제한된 사용자 보기 및 조사</span><span class="sxs-lookup"><span data-stu-id="72a80-137">View and investigate restricted users</span></span>

<span data-ttu-id="72a80-138">제한된 사용자 목록으로 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="72a80-139">예를 들어 보안 및 준수 & 위협 관리 검토  제한된 사용자로 \>  \> **이동하면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="72a80-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="72a80-140">다음 절차에서는 트리거될  수 있는 다양한 종류의 경고를 볼 수 있는 좋은 방법으로 경고 대시보드를 사용하는 탐색에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="72a80-141"><https://protection.office.com>으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="72a80-142">탐색 창에서 알림 **대시보드를** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="72a80-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="72a80-143">기타 경고 **위젯에서** 제한된 **사용자를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="72a80-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![기타 경고 위젯](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="72a80-145">그러면 제한된 사용자 목록이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-145">This opens the list of restricted users.</span></span>

   ![Office 365의 제한된 사용자](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="72a80-147">목록에서 사용자 계정을 선택하여 세부 정보를 보고 제한된 사용자를 공개하는 등의 작업을 [실행합니다.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="72a80-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="72a80-148">자동화된 조사에 대한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="72a80-148">View details about automated investigations</span></span>

<span data-ttu-id="72a80-149">자동화된 조사가 시작된 경우 보안 및 준수 센터에서 해당 세부 정보 및 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="72a80-150">위협 관리 **조사로 이동한** 다음 조사를 선택하여 세부 \> 정보를 본다.</span><span class="sxs-lookup"><span data-stu-id="72a80-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="72a80-151">자세한 내용은 조사 세부 정보 [보기를 참조합니다.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="72a80-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="72a80-152">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-152">Keep the following points in mind</span></span>

- <span data-ttu-id="72a80-153">**경고를 계속 확인**</span><span class="sxs-lookup"><span data-stu-id="72a80-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="72a80-154">아시다시피 손상이 더 오래 노출되지는 않습니다. 조직, 고객 및 파트너에게 광범위한 영향과 비용의 가능성이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="72a80-155">위협을 완화하는 데 특히 사용자의 계정이 손상된 경우 조기 감지 및 시기적시 대응이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="72a80-156">자동화는 보안 운영 팀을 지원하지만 **대체하지는 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="72a80-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="72a80-157">자동화된 조사 및 대응 기능은 초기에 손상된 사용자를 감지할 수 있지만 보안 운영 팀이 몇 가지 조사 및 수정을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="72a80-158">이에 대한 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="72a80-158">Need some help with this?</span></span> <span data-ttu-id="72a80-159">작업 [검토 및 승인을 참조합니다.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="72a80-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="72a80-160">의심스러운 로그인 경고를 유일한 지표로 **사용하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="72a80-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="72a80-161">사용자 계정이 손상되면 의심스러운 로그인 경고를 트리거하거나 트리거하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="72a80-162">경우에 따라 경고를 트리거하는 계정이 손상된 후 발생하는 일련의 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="72a80-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="72a80-163">경고에 대해 더 알고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="72a80-163">Want to know more about alerts?</span></span> <span data-ttu-id="72a80-164">경고 [정책을 참조합니다.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="72a80-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="72a80-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="72a80-165">Next steps</span></span>

- [<span data-ttu-id="72a80-166">AIR 기능을 사용하는 데 필요한 사용 권한 검토</span><span class="sxs-lookup"><span data-stu-id="72a80-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="72a80-167">Office 365에서 악성 전자 메일 찾기 및 조사</span><span class="sxs-lookup"><span data-stu-id="72a80-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="72a80-168">끝점용 Microsoft Defender의 AIR에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="72a80-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="72a80-169">Microsoft 365 로드맵을 방문하여 곧 출시될 예정인 제품 보기</span><span class="sxs-lookup"><span data-stu-id="72a80-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
