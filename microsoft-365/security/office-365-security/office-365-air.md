---
title: 자동화 된 조사 및 응답 (AIR)-시작
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
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
description: Office 365 Advanced Threat Protection 계획 2의 자동화 된 조사 및 응답 기능 사용을 시작 하세요.
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: 14742df5d9dbd2f65a032250696dbc7c61210562
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336682"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="72bee-104">Office 365에서 자동화 된 조사 및 응답 (AIR) 사용 시작</span><span class="sxs-lookup"><span data-stu-id="72bee-104">Get started using Automated investigation and response (AIR) in Office 365</span></span>

<span data-ttu-id="72bee-105">[Office 365 Advanced Threat Protection](office-365-atp.md) (OFFICE 365 ATP) 계획 2에는 보안 작업 팀의 시간과 노력을 줄일 수 있는 강력한 자동 조사 및 응답 (AIR) 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-105">[Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) Plan 2 includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="72bee-106">알림이 트리거되면 해당 경고를 검토 하 고 우선 순위를 지정 하 고 응답 하는 보안 운영 팀이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="72bee-107">들어오는 알림의 볼륨을 유지 하는 것은 매우 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="72bee-108">이 중 일부를 자동화 하면 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-108">Automating some of this can help.</span></span> <span data-ttu-id="72bee-109">AIR을 사용 하는 경우 보안 운영 팀은 트리거된 경고에 대 한 시야 없이 우선 순위가 더 높은 작업에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of alerts that are triggered.</span></span>

<span data-ttu-id="72bee-110">이 문서에는 다음 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-110">This article contains information about:</span></span>

- <span data-ttu-id="72bee-111">[전체 공기 흐름](#the-overall-flow-of-air)</span><span class="sxs-lookup"><span data-stu-id="72bee-111">The [overall flow](#the-overall-flow-of-air) of AIR</span></span>
- [<span data-ttu-id="72bee-112">공기를 얻는 방법</span><span class="sxs-lookup"><span data-stu-id="72bee-112">How to get AIR</span></span>](#how-to-get-air)
- <span data-ttu-id="72bee-113">AIR 기능을 구성 하거나 사용 하는 [데 필요한 사용 권한](#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="72bee-113">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities</span></span>

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="72bee-114">전체 공기 흐름</span><span class="sxs-lookup"><span data-stu-id="72bee-114">The overall flow of AIR</span></span>

<span data-ttu-id="72bee-115">높은 수준에서 경고가 트리거되고 보안 playbook에 의해 자동화 된 조사가 시작 되어 발견 및 추천이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-115">At a high level, an alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommendations.</span></span> <span data-ttu-id="72bee-116">다음은 AIR의 전체 흐름을 단계별로 설명한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-116">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="72bee-117">자동화 된 조사가 다음 중 한 가지 방법으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-117">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="72bee-118">인시던트를 만드는 Office 이벤트에 의해 [경고가](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-118">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by an Office event, which creates an incident.</span></span> <span data-ttu-id="72bee-119">인시던트 유형에 따라 [보안 playbook](automated-investigation-response-office.md#security-playbooks) 자동 조사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-119">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) starts an automated investigation.</span></span> 

     <span data-ttu-id="72bee-120">--- 또는 ---</span><span class="sxs-lookup"><span data-stu-id="72bee-120">--- or ---</span></span>
   
   - <span data-ttu-id="72bee-121">보안 분석가가 [Threat Explorer](threat-explorer.md)를 사용 하는 동안 [자동화 된 조사를 시작](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 합니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-121">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="72bee-122">자동화 된 조사가 실행 되는 동안에는 해당 전자 메일에 대 한 추가 데이터와 해당 전자 메일에 관련 된 엔터티가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-122">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="72bee-123">이러한 엔터티는 파일, Url 및 받는 사람을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-123">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="72bee-124">새 경고 및 관련 경고가 트리거되면 조사의 범위가 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-124">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="72bee-125">자동화 된 조사 도중 및 후에 [세부 정보 및 결과](air-view-investigation-results.md) 를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-125">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="72bee-126">결과에는 발견 된 모든 위협을 응답 하 고 수정 하기 위해 취할 수 있는 [권장 작업이](air-remediation-actions.md) 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-126">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="72bee-127">또한 모든 조사 활동을 추적 하는 [playbook 로그](air-view-investigation-results.md#playbook-log) 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-127">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

    <span data-ttu-id="72bee-128">조직에서 사용자 지정 보고 솔루션 또는 타사 솔루션을 사용 하는 경우에는 [Office 365 관리 활동 API를 사용](air-custom-reporting.md) 하 여 자동화 된 조사 및 위협에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-128">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>

4. <span data-ttu-id="72bee-129">보안 운영 팀은 [조사 결과 및 권장 사항을](air-view-investigation-results.md)검토 하 고 [재구성 작업을 승인 하거나 거부](air-review-approve-pending-completed-actions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-129">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

    <span data-ttu-id="72bee-130">보류 중인 재구성 작업이 승인 되거나 거부 됨에 따라 자동 조사가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-130">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="72bee-131">Office 365 ATP에서는 재구성 작업이 자동으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-131">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="72bee-132">수정 작업은 조직의 보안 팀이 승인한 경우에만 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-132">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

<span data-ttu-id="72bee-133">자동화 된 조사 프로세스 중 및 이후에 보안 팀은 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-133">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="72bee-134">조사와 관련 된 경고에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="72bee-134">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="72bee-135">조사 결과 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="72bee-135">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="72bee-136">조사 결과로 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="72bee-136">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="72bee-137">자세한 내용은 [AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72bee-137">For more details, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="72bee-138">공기를 얻는 방법</span><span class="sxs-lookup"><span data-stu-id="72bee-138">How to get AIR</span></span>

<span data-ttu-id="72bee-139">Office 365의 AIR 기능은 [office 365 Advanced Threat Protection 계획 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-139">Office 365 AIR capabilities are included in [Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span></span> <span data-ttu-id="72bee-140">그러나 AIR이 예상 대로 작동 하려면 [Office 365 ATP 정책을 구성 해야](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 합니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-140">However, your [Office 365 ATP policies should be configured](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) in order for AIR to work as expected.</span></span> <span data-ttu-id="72bee-141">또한 조직의 [경고 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)검토 하 고 잠재적으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-141">In addition, make sure to review and potentially configure your organization's [alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span> 

<span data-ttu-id="72bee-142">Microsoft 365에서는 Exchange 관리자 권한 남용, 맬웨어 활동, 잠재적 외부 및 내부 위협, 정보 관리 위험을 식별 하는 데 도움이 되는 다양 한 기본 제공 경고 정책을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-142">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="72bee-143">몇 가지 [기본 경고 정책이](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 자동 조사를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-143">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="72bee-144">이러한 경계 및 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-144">These include the following:</span></span>

- <span data-ttu-id="72bee-145">잠재적으로 악의적인 URL 클릭이 검색 됨</span><span class="sxs-lookup"><span data-stu-id="72bee-145">A potentially malicious URL click is detected</span></span>

- <span data-ttu-id="72bee-146">사용자가 전자 메일 메시지를 피싱으로 보고</span><span class="sxs-lookup"><span data-stu-id="72bee-146">An email message is reported by a user as phish</span></span>

- <span data-ttu-id="72bee-147">배달이 완료 된 후 맬웨어를 포함 하는 전자 메일 메시지가 제거 됨</span><span class="sxs-lookup"><span data-stu-id="72bee-147">Email messages containing malware are removed after delivery</span></span>

- <span data-ttu-id="72bee-148">배달 후 피싱 Url이 포함 된 전자 메일 메시지가 제거 됨</span><span class="sxs-lookup"><span data-stu-id="72bee-148">Email messages containing phish URLs are removed after delivery</span></span>

- <span data-ttu-id="72bee-149">의심 스러운 전자 메일 전송 패턴이 검색 됨</span><span class="sxs-lookup"><span data-stu-id="72bee-149">Suspicious email sending patterns are detected</span></span>

- <span data-ttu-id="72bee-150">사용자가 전자 메일을 보낼 수 없도록 제한 됨</span><span class="sxs-lookup"><span data-stu-id="72bee-150">A user is restricted from sending email</span></span>

<span data-ttu-id="72bee-151">[알림 및 AIR에 대해 자세히 알아보세요](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span><span class="sxs-lookup"><span data-stu-id="72bee-151">[Learn more about alerts and AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="72bee-152">AIR 기능을 사용 하는 데 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="72bee-152">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="72bee-153">사용 권한은 다음 표에 설명 된 것과 같은 특정 역할을 통해 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-153">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="72bee-154">작업</span><span class="sxs-lookup"><span data-stu-id="72bee-154">Task</span></span> |<span data-ttu-id="72bee-155">필요한 역할</span><span class="sxs-lookup"><span data-stu-id="72bee-155">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="72bee-156">AIR 기능을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="72bee-156">To set up AIR features</span></span> |<span data-ttu-id="72bee-157">다음 역할 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-157">One of the following roles:</span></span> <br/><span data-ttu-id="72bee-158">-전역 관리자</span><span class="sxs-lookup"><span data-stu-id="72bee-158">- Global Administrator</span></span><br/><span data-ttu-id="72bee-159">-보안 관리자</span><span class="sxs-lookup"><span data-stu-id="72bee-159">- Security Administrator</span></span> <br/><span data-ttu-id="72bee-160">이러한 역할은 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에서 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-160">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="72bee-161">권장 작업을 승인 하거나 거부 하려면</span><span class="sxs-lookup"><span data-stu-id="72bee-161">To approve or reject recommended actions</span></span>|<span data-ttu-id="72bee-162">[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center))에서 할당 된 다음 역할 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-162">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="72bee-163">-전역 관리자</span><span class="sxs-lookup"><span data-stu-id="72bee-163">- Global Administrator</span></span> <br/><span data-ttu-id="72bee-164">-보안 관리자</span><span class="sxs-lookup"><span data-stu-id="72bee-164">- Security Administrator</span></span><br/><span data-ttu-id="72bee-165">-보안 독자</span><span class="sxs-lookup"><span data-stu-id="72bee-165">- Security Reader</span></span> <br/><span data-ttu-id="72bee-166">--- 및 ---</span><span class="sxs-lookup"><span data-stu-id="72bee-166">--- and ---</span></span><br/><span data-ttu-id="72bee-167">-검색 및 제거 (이 역할은 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에만 할당 됨)</span><span class="sxs-lookup"><span data-stu-id="72bee-167">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="72bee-168">여기에 새 역할 그룹을 만들고 새 역할 그룹에 검색 및 제거 역할을 추가 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-168">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

<span data-ttu-id="72bee-169">[Office 365 ATP 계획 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) 라이선스는 다음에 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-169">[Office 365 ATP Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="72bee-170">보안 관리자 (전역 관리자 포함)</span><span class="sxs-lookup"><span data-stu-id="72bee-170">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="72bee-171">조직의 보안 운영 팀 (보안 판독기 및 검색 및 제거 역할을 포함 하는 작업)</span><span class="sxs-lookup"><span data-stu-id="72bee-171">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="72bee-172">최종 사용자</span><span class="sxs-lookup"><span data-stu-id="72bee-172">End users</span></span>

<span data-ttu-id="72bee-173">또한 보호 기능을 적용 하려면 [Office 365 ATP 정책을](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) 정의 하 고 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72bee-173">In addition, [Office 365 ATP policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) must be defined and applied in order for protection to be in place.</span></span>

## <a name="next-steps"></a><span data-ttu-id="72bee-174">다음 단계</span><span class="sxs-lookup"><span data-stu-id="72bee-174">Next steps</span></span>

- [<span data-ttu-id="72bee-175">자세한 내용은 자동화 된 조사의 세부 정보 및 결과를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72bee-175">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="72bee-176">보류 중인 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="72bee-176">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="72bee-177">관련 문서</span><span class="sxs-lookup"><span data-stu-id="72bee-177">Related articles</span></span>

- [<span data-ttu-id="72bee-178">Microsoft Defender Advanced Threat Protection의 자동화 된 조사 및 재구성</span><span class="sxs-lookup"><span data-stu-id="72bee-178">Automated investigation and remediation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="72bee-179">Microsoft Threat Protection의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="72bee-179">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
