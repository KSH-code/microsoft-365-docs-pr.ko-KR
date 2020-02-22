---
title: Office 365 Advanced Threat Protection에서 자동화 된 조사 및 응답과 함께 손상 되는 사용자 계정을 해결 합니다.
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호, 손상
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/20/2020
description: Office 365 Advanced Threat Protection 계획 2의 자동화 된 조사 및 응답 기능을 사용 하 여 공격에 노출 된 사용자 계정을 검색 하 고 해결 하는 프로세스를 빠르게 진행 하는 방법을 알아봅니다.
ms.openlocfilehash: 7dfa1db02e777e3fdb546ebf948ebc297f1caad5
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228570"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="8a1c9-104">자동 조사 및 응답을 통해 손상 된 사용자 계정 처리</span><span class="sxs-lookup"><span data-stu-id="8a1c9-104">Address compromised user accounts with automated investigation and response</span></span>

<span data-ttu-id="8a1c9-105">[Office 365 Advanced Threat Protection 계획 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) 에는 강력한 [자동화 된 조사 및 응답](office-365-air.md) (AIR) 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-105">[Office 365 Advanced Threat Protection Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="8a1c9-106">이러한 기능을 통해 보안 운영 팀을 보다 많은 시간과 노력으로 위협을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="8a1c9-107">Microsoft는 계속 해 서 보안 기능을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="8a1c9-108">최근, AIR 기능은 손상 된 사용자 보안 playbook (현재 미리 보기)를 포함 하도록 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="8a1c9-109">이 문서를 읽으면 손상 된 사용자 보안 playbook에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="8a1c9-110">그리고 추가 세부 정보를 확인 하 고 [사용자 손상 및 제한 위반 범위에 응답 하 고 Office 365 ATP를 통해 침해](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) 를 처리 하는 시간을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![손상 된 사용자에 대 한 자동화 된 조사](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="8a1c9-112">손상 된 사용자 보안 playbook을 통해 조직의 보안 팀에서 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="8a1c9-113">손상 된 사용자 계정 감지 속도 향상</span><span class="sxs-lookup"><span data-stu-id="8a1c9-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="8a1c9-114">계정이 손상 되는 경우 위반 범위를 제한 합니다. 한</span><span class="sxs-lookup"><span data-stu-id="8a1c9-114">Limit the scope of a breach when an account is compromised; and</span></span> 

- <span data-ttu-id="8a1c9-115">손상 된 사용자에 게 보다 효율적이 고 효율적으로 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="8a1c9-116">손상 된 사용자 알림</span><span class="sxs-lookup"><span data-stu-id="8a1c9-116">Compromised user alerts</span></span>

<span data-ttu-id="8a1c9-117">사용자 계정이 손상 되 면 이례적인 또는 비정상 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="8a1c9-118">예를 들어 피싱 및 스팸 메시지는 신뢰할 수 있는 사용자 계정에서 내부적으로 전송 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="8a1c9-119">Office 365 Advanced Threat Protection은 전자 메일 패턴 및 Office 365 내의 공동 작업 활동에서 이러한 예외를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-119">Office 365 Advanced Threat Protection can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="8a1c9-120">이 경우 알림이 트리거되고 위협 완화 프로세스가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="8a1c9-121">예를 들어 의심 스러운 전자 메일 보내기로 인해 트리거된 경고는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![의심 스러운 전자 메일 보내기로 인해 트리거되는 알림](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="8a1c9-123">다음은 사용자에 대 한 전송 제한에 도달 했을 때 트리거되는 경고의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![전송 제한에 도달 하 여 트리거된 경고](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="8a1c9-125">손상 된 사용자 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="8a1c9-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="8a1c9-126">사용자 계정이 손상 되 면 경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="8a1c9-127">또한 조직의 보안 운영 팀에서 문제를 해결할 때까지 해당 사용자 계정이 차단 되 고 더 이상 전자 메일 메시지를 보내지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="8a1c9-128">다른 경우에는 보안 팀에서 권장 하는 작업을 수행할 수 있는 자동화 된 조사가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="8a1c9-129">제한 된 사용자 보기 및 조사</span><span class="sxs-lookup"><span data-stu-id="8a1c9-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="8a1c9-130">자동화 된 조사에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="8a1c9-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="8a1c9-131">다음 작업을 수행 하려면 적절 한 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="8a1c9-132">[AIR 기능을 사용 하려면 필수 권한을](office-365-air.md#required-permissions-to-use-air-capabilities)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-132">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="8a1c9-133">제한 된 사용자 보기 및 조사</span><span class="sxs-lookup"><span data-stu-id="8a1c9-133">View and investigate restricted users</span></span>

<span data-ttu-id="8a1c9-134">제한 된 사용자 목록으로 이동 하기 위한 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="8a1c9-135">예를 들어 Office 365 보안 & 준수 센터에서는 **위협 관리** > **검토** > **제한 된 사용자**로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-135">For example, in the Office 365 Security & Compliance Center, you can go to **Threat management** > **Review** > **Restricted Users**.</span></span> <span data-ttu-id="8a1c9-136">다음 절차에서는 **알림** 대시보드를 사용 하 여 탐색에 대해 설명 하므로 트리거된 것일 수 있는 다양 한 종류의 경고를 확인 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="8a1c9-137">[https://protection.office.com](https://protection.office.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="8a1c9-138">탐색 창에서 **경고** > **대시보드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-138">In the navigation pane, choose **Alerts** > **Dashboard**.</span></span>

3. <span data-ttu-id="8a1c9-139">**다른 경고** 위젯에 **제한 된 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span><br/>
   <span data-ttu-id="8a1c9-140">![기타 알림 위젯](/microsoft-365/media/office365atp-otheralertswidget.jpg)</span><span class="sxs-lookup"><span data-stu-id="8a1c9-140">![Other alerts widget](/microsoft-365/media/office365atp-otheralertswidget.jpg)</span></span><br/>
   <span data-ttu-id="8a1c9-141">이렇게 하면 제한 된 사용자 목록이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-141">This opens the list of restricted users.</span></span><br/><span data-ttu-id="8a1c9-142">![Office 365의 제한 된 사용자](/microsoft-365/media/office365atp-restrictedusers.jpg)</span><span class="sxs-lookup"><span data-stu-id="8a1c9-142">![Restricted users in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)</span></span> 

4. <span data-ttu-id="8a1c9-143">목록에서 사용자 계정을 선택 하 여 세부 정보를 확인 하 고 [제한 된 사용자 해제](removing-user-from-restricted-users-portal-after-spam.md)와 같은 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span> 

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="8a1c9-144">자동화 된 조사에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="8a1c9-144">View details about automated investigations</span></span>

<span data-ttu-id="8a1c9-145">자동 조사가 시작 되 면 Office 365 보안 & 준수 센터에서 해당 세부 정보와 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-145">When an automated investigation has begun, you can see its details and results in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="8a1c9-146">**위협 관리** > **조사**로 이동한 다음 조사를 선택 하 여 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-146">Go to **Threat management** > **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="8a1c9-147">자세한 내용은 [조사의 세부 정보 보기](air-view-investigation-results.md#view-details-of-an-investigation)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-147">To learn more, see [View details of an investigation](air-view-investigation-results.md#view-details-of-an-investigation).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="8a1c9-148">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-148">Keep the following points in mind</span></span>

- <span data-ttu-id="8a1c9-149">**알림 맨 위에 유지**합니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="8a1c9-150">알고 있는 것 처럼 더 긴 손상이 감지 되지 않으면 조직, 고객 및 파트너에 게 광범위 하 게 영향을 줄 수 있고 비용이 더 커집니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="8a1c9-151">위협을 완화 하려면 조기 검색 및 적시 응답이 중요 하며, 특히 사용자의 계정이 손상 되는 경우에는 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span> 

- <span data-ttu-id="8a1c9-152">**자동화는 보안 운영 팀을 지원 하지만 대체 하지는 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="8a1c9-153">자동화 된 조사 및 응답 기능은 공격에 참여 한 사용자를 일찍 검색할 수 있지만, 보안 운영 팀에서 이러한 문제를 해결 하 고 몇 가지 조사 및 관리를 수행 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="8a1c9-154">이에 대 한 도움이 필요 하세요?</span><span class="sxs-lookup"><span data-stu-id="8a1c9-154">Need some help with this?</span></span> <span data-ttu-id="8a1c9-155">[작업 검토 및 승인를](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-155">See [Review and approve actions](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).</span></span>

- <span data-ttu-id="8a1c9-156">**의심 스러운 로그인 알림을 유일한 지표로 사용 하지 마십시오**.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="8a1c9-157">사용자 계정이 손상 되 면 의심 스러운 로그인 경고가 발생 하거나 트리거되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="8a1c9-158">때로는 경고가 발생 한 계정이 손상 된 후에 발생 하는 일련의 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="8a1c9-159">경고에 대 한 자세한 정보를 보 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="8a1c9-159">Want to know more about alerts?</span></span> <span data-ttu-id="8a1c9-160">[경고 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a1c9-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8a1c9-161">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8a1c9-161">Next steps</span></span>

- [<span data-ttu-id="8a1c9-162">필요한 사용 권한을 검토 하 여 AIR 기능 사용</span><span class="sxs-lookup"><span data-stu-id="8a1c9-162">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="8a1c9-163">Office 365에서 악성 전자 메일 찾기 및 조사</span><span class="sxs-lookup"><span data-stu-id="8a1c9-163">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="8a1c9-164">Microsoft Defender ATP의 AIR에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="8a1c9-164">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="8a1c9-165">Microsoft 365 로드맵를 방문 하 여 곧 제공 되는 항목을 확인 하 고 롤아웃</span><span class="sxs-lookup"><span data-stu-id="8a1c9-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

