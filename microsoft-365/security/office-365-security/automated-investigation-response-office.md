---
title: Microsoft Defender에서 자동화된 조사 및 대응이 작동하는 Office 365
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 자동화된 인시던트 대응, 조사, 수정, 위협 방지
ms.date: 01/29/2021
description: Microsoft Defender에서 자동화된 조사 및 응답 기능이 어떻게 Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a8d33804e8c1405093843709e06250beb7f10512
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269639"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e2ff2-104">Microsoft Defender에서 자동화된 조사 및 대응이 작동하는 Office 365</span><span class="sxs-lookup"><span data-stu-id="e2ff2-104">How automated investigation and response works in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e2ff2-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="e2ff2-105">**Applies to**</span></span>
- [<span data-ttu-id="e2ff2-106">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="e2ff2-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e2ff2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2ff2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e2ff2-108">보안 경고가 트리거되면 보안 운영 팀이 해당 경고를 보고 조직을 보호하기 위한 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-108">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="e2ff2-109">경우에 따라 보안 운영 팀이 트리거되는 경고의 양에 당황할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-109">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="e2ff2-110">Microsoft Defender for Office 365 자동화된 조사 및 대응(AIR) 기능이 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-110">Automated investigation and response (AIR) capabilities in Microsoft Defender for Office 365 can help.</span></span>

<span data-ttu-id="e2ff2-111">AIR을 사용하면 보안 운영 팀이 보다 효율적이고 효율적으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-111">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="e2ff2-112">AIR 기능에는 현재 존재하는 잘 알려진 위협에 대응하는 자동화된 조사 프로세스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-112">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="e2ff2-113">적절한 수정 작업은 승인을 대기하여 보안 운영 팀이 감지된 위협에 대응할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-113">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span>

<span data-ttu-id="e2ff2-114">이 문서에서는 AIR이 여러 예제를 통해 작동하는 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-114">This article describes how AIR works through several examples.</span></span> <span data-ttu-id="e2ff2-115">AIR 사용을 시작할 준비가 되면 위협 자동 조사 및 [대응을 참조합니다.](office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="e2ff2-115">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

- [<span data-ttu-id="e2ff2-116">예제 1: 사용자가 보고한 피싱 메시지가 조사 플레이북을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-116">Example 1: A user-reported phish message launches an investigation playbook</span></span>](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [<span data-ttu-id="e2ff2-117">예제 2: 보안 관리자가 위협 탐색기에서 조사를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-117">Example 2: A security administrator triggers an investigation from Threat Explorer</span></span>](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [<span data-ttu-id="e2ff2-118">예제 3: 보안 운영 팀이 OFFICE 365 관리 활동 API를 사용하여 AIR을 SIEM과 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-118">Example 3: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="e2ff2-119">예: 사용자가 보고한 피싱 메시지가 조사 플레이북을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-119">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="e2ff2-120">조직의 사용자가 피싱 시도로 생각할 수 있는 전자 메일을 받는 경우를 가정해 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-120">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="e2ff2-121">이러한 메시지를 보고하도록 학습된 사용자는 보고서 [](enable-the-report-message-add-in.md) 메시지 추가 기능 [](enable-the-report-phish-add-in.md) 또는 피싱 보고 추가 기능을 사용하여 분석을 위해 Microsoft로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-121">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="e2ff2-122">제출은 시스템에 보내지며 제출 보기(이전의  사용자 보고 보기)의 탐색기에서 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="e2ff2-122">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="e2ff2-123">또한 사용자가 보고한 메시지는 이제 조사 플레이북을 자동으로 시작하는 시스템 기반 정보 경고를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-123">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="e2ff2-124">루트 조사 단계에서는 전자 메일의 다양한 측면이 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-124">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="e2ff2-125">이러한 측면은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-125">These aspects include:</span></span>

- <span data-ttu-id="e2ff2-126">위협 유형에 대한 결정</span><span class="sxs-lookup"><span data-stu-id="e2ff2-126">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="e2ff2-127">Who 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-127">Who sent it;</span></span>
- <span data-ttu-id="e2ff2-128">전자 메일이 전송된 위치(인프라 전송);</span><span class="sxs-lookup"><span data-stu-id="e2ff2-128">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="e2ff2-129">전자 메일의 다른 인스턴스가 배달 또는 차단된 경우</span><span class="sxs-lookup"><span data-stu-id="e2ff2-129">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="e2ff2-130">분석가의 평가</span><span class="sxs-lookup"><span data-stu-id="e2ff2-130">An assessment from our analysts;</span></span>
- <span data-ttu-id="e2ff2-131">전자 메일이 알려진 캠페인과 연결되는지 여부</span><span class="sxs-lookup"><span data-stu-id="e2ff2-131">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="e2ff2-132">등.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-132">and more.</span></span>

<span data-ttu-id="e2ff2-133">루트 조사가 완료되면 재생북은 원래 전자 메일 및 연결된 엔터티에 대해 수행할 권장 작업 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-133">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>

<span data-ttu-id="e2ff2-134">다음으로 몇 가지 위협 조사 및 헌팅 단계가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-134">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="e2ff2-135">유사한 전자 메일 메시지는 전자 메일 클러스터 검색을 통해 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-135">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="e2ff2-136">신호는 끝점용 Microsoft Defender와 같은 다른 [플랫폼과 공유됩니다.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="e2ff2-136">The signal is shared with other platforms, such as [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="e2ff2-137">사용자가 의심스러운 전자 메일 메시지의 악의적인 링크를 클릭하는지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-137">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="e2ff2-138">EOP(Exchange Online Protection) 및 (microsoft[](exchange-online-protection-overview.md)[Defender for](defender-for-office-365.md)Office 365)에 대해 확인을 수행하여 사용자가 보고한 다른 유사한 메시지가 없는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-138">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and ([Microsoft Defender for Office 365](defender-for-office-365.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="e2ff2-139">사용자가 손상된 경우 확인이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-139">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="e2ff2-140">이 검사는 모든 관련 사용자 활동 [Office 365,](/cloud-app-security)Microsoft Cloud App Security [](/azure/active-directory)및 Azure Active Directory 신호를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-140">This check leverages signals across Office 365, [Microsoft Cloud App Security](/cloud-app-security), and [Azure Active Directory](/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="e2ff2-141">헌팅 단계에서는 다양한 헌팅 단계에 위험과 위협이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-141">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>

<span data-ttu-id="e2ff2-142">수정은 플레이북의 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-142">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="e2ff2-143">이 단계에서는 조사 및 헌팅 단계에 따라 수정 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-143">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span>

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="e2ff2-144">예: 보안 관리자가 위협 탐색기에서 조사를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-144">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="e2ff2-145">경고에 의해 트리거되는 자동화된 조사 외에도 조직의 보안 운영 팀은 위협 탐색기 의 보기에서 자동화된 조사를 트리거할 [수 있습니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="e2ff2-145">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>  <span data-ttu-id="e2ff2-146">또한 이 조사는 Microsoft Defender 인시던트 및 외부 SIEM 도구에서 이 조사가 트리거된 것으로 볼 수 있도록 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-146">This investigation also creates an alert, so that Microsoft Defender Incidents and external SIEM tools can see that this investigation was triggered.</span></span>

<span data-ttu-id="e2ff2-147">예를 들어 탐색기에서 맬웨어 **보기를 사용하고 있는** 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-147">For example, suppose that you are using the **Malware** view in Explorer.</span></span> <span data-ttu-id="e2ff2-148">차트 아래의 탭을 사용하여 전자 메일 **탭을** 선택합니다. 목록에서 항목을 하나 이상 선택하면 **+ 작업** 단추가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-148">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span>

![선택한 메시지가 있는 탐색기](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="e2ff2-150">작업 **메뉴를** 사용하여 조사 **트리거를 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e2ff2-150">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![선택한 메시지에 대한 작업 메뉴](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="e2ff2-152">경고에 의해 트리거되는 플레이북과 마찬가지로 탐색기에서 보기에서 트리거되는 자동 조사에는 루트 조사, 위협을 식별 및 상관 관계화하는 단계, 이러한 위협을 완화하기 위한 권장 조치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-152">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="e2ff2-153">예: 보안 운영 팀이 OFFICE 365 관리 활동 API를 사용하여 AIR과 SIEM을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-153">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="e2ff2-154">Microsoft Defender for Office 365 보안 운영 [&](air-view-investigation-results.md) 팀이 위협을 모니터링하고 해결하기 위해 사용할 수 있는 세부 정보 보고서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-154">AIR capabilities in Microsoft Defender for Office 365 include [reports & details](air-view-investigation-results.md) that security operations teams can use to monitor and address threats.</span></span> <span data-ttu-id="e2ff2-155">그러나 AIR 기능을 다른 솔루션과 통합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-155">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="e2ff2-156">예를 들어 SIEM(보안 정보 및 이벤트 관리) 시스템, 사례 관리 시스템 또는 사용자 지정 보고 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-156">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="e2ff2-157">이러한 종류의 통합은 관리 활동 API 에서 Office 365 [수 있습니다.](/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="e2ff2-157">These kinds of integrations can be done by using the [Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="e2ff2-158">예를 들어 최근에 조직은 보안 운영 팀이 AIR에서 이미 처리한 사용자가 보고한 피싱 알림을 볼 수 있는 방법을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-158">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="e2ff2-159">해당 솔루션은 관련 경고를 조직의 SIEM 서버 및 해당 사례 관리 시스템에 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-159">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="e2ff2-160">이 솔루션은 보안 운영 팀이 실제 위협에 시간 및 노력을 집중할 수 있도록 가짓 긍정 수를 크게 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-160">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="e2ff2-161">이 사용자 지정 솔루션에 대한 자세한 [내용은 Tech Community 블로그: Microsoft Defender for Office 365 O365 관리 API를 사용하여 SOC의](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)효율성 개선을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2ff2-161">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Microsoft Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2ff2-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e2ff2-162">Next steps</span></span>

- [<span data-ttu-id="e2ff2-163">AIR 사용 시작</span><span class="sxs-lookup"><span data-stu-id="e2ff2-163">Get started using AIR</span></span>](office-365-air.md)
- [<span data-ttu-id="e2ff2-164">보류 중 또는 완료된 수정 작업 보기</span><span class="sxs-lookup"><span data-stu-id="e2ff2-164">View pending or completed remediation actions</span></span>](air-review-approve-pending-completed-actions.md)