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
ms.openlocfilehash: b9811963210f253bbfe90af02dd6d38926776a62
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033953"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="061fb-104">Office 365에서 자동화 된 조사 및 응답 (AIR) 사용 시작</span><span class="sxs-lookup"><span data-stu-id="061fb-104">Get started using Automated investigation and response (AIR) in Office 365</span></span>

<span data-ttu-id="061fb-105">[Office 365 Advanced Threat Protection](office-365-atp.md) (OFFICE 365 ATP) 계획 2에는 보안 작업 팀의 시간과 노력을 줄일 수 있는 강력한 자동 조사 및 응답 (AIR) 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-105">[Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) Plan 2 includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="061fb-106">알림이 트리거되면 해당 경고를 검토 하 고 우선 순위를 지정 하 고 응답 하는 보안 운영 팀이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="061fb-107">들어오는 알림의 볼륨을 유지 하는 것은 매우 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="061fb-108">이 중 일부를 자동화 하면 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-108">Automating some of this can help.</span></span> <span data-ttu-id="061fb-109">AIR을 사용 하는 경우 보안 운영 팀은 트리거된 경고에 대 한 시야 없이 우선 순위가 더 높은 작업에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of alerts that are triggered.</span></span>

<span data-ttu-id="061fb-110">이 문서에서는 [전체 공기 흐름](#the-overall-flow-of-air) , 공기를 [얻는 방법](#how-to-get-air)및 air 기능을 구성 또는 사용 하는 [데 필요한 사용](#required-permissions-to-use-air-capabilities) 에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-110">This article describes the [overall flow](#the-overall-flow-of-air) of AIR, [how to get AIR](#how-to-get-air), and the [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="061fb-111">전체 공기 흐름</span><span class="sxs-lookup"><span data-stu-id="061fb-111">The overall flow of AIR</span></span>

<span data-ttu-id="061fb-112">높은 수준에서 경고가 트리거되고 보안 playbook가 시작 되 고 자동화 된 조사로 인해 발견 및 추천이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-112">At a high level, an alert is triggered, and a security playbook starts and automated investigation, which results in findings and recommendations.</span></span> <span data-ttu-id="061fb-113">다음은 AIR의 전체 흐름을 단계별로 설명한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-113">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="061fb-114">자동화 된 조사가 다음 중 한 가지 방법으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-114">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="061fb-115">인시던트를 만드는 Office 이벤트에 의해 [경고가](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-115">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by an Office event, which creates an incident.</span></span> <span data-ttu-id="061fb-116">인시던트 유형에 따라 [보안 playbook](automated-investigation-response-office.md#security-playbooks) 자동 조사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-116">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) starts an automated investigation.</span></span> 

     <span data-ttu-id="061fb-117">--- 또는 ---</span><span class="sxs-lookup"><span data-stu-id="061fb-117">--- or ---</span></span>
   
   - <span data-ttu-id="061fb-118">보안 분석가가 [Threat Explorer](threat-explorer.md)를 사용 하는 동안 [자동화 된 조사를 시작](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 합니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-118">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="061fb-119">자동화 된 조사가 실행 되는 동안에는 해당 전자 메일에 대 한 추가 데이터와 해당 전자 메일에 관련 된 엔터티가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-119">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="061fb-120">이러한 엔터티는 파일, Url 및 받는 사람을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-120">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="061fb-121">새 경고 및 관련 경고가 트리거되면 조사의 범위가 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-121">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="061fb-122">자동화 된 조사 도중 및 후에 [세부 정보 및 결과](air-view-investigation-results.md) 를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-122">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="061fb-123">결과에는 발견 된 모든 위협을 응답 하 고 수정 하기 위해 취할 수 있는 [권장 작업이](air-remediation-actions.md) 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-123">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="061fb-124">또한 모든 조사 활동을 추적 하는 [playbook 로그](air-view-investigation-results.md#playbook-log) 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-124">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

    <span data-ttu-id="061fb-125">조직에서 사용자 지정 보고 솔루션 또는 타사 솔루션을 사용 하는 경우에는 [Office 365 관리 활동 API를 사용](air-custom-reporting.md) 하 여 자동화 된 조사 및 위협에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-125">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>

4. <span data-ttu-id="061fb-126">보안 운영 팀은 [조사 결과 및 권장 사항을](air-view-investigation-results.md)검토 하 고 [재구성 작업을 승인 하거나 거부](air-review-approve-pending-completed-actions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-126">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

    <span data-ttu-id="061fb-127">보류 중인 재구성 작업이 승인 되거나 거부 됨에 따라 자동 조사가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-127">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="061fb-128">Office 365 ATP에서는 재구성 작업이 자동으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-128">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="061fb-129">수정 작업은 조직의 보안 팀이 승인한 경우에만 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-129">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

<span data-ttu-id="061fb-130">자동화 된 조사 프로세스 중 및 이후에 보안 팀은 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-130">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="061fb-131">조사와 관련 된 경고에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="061fb-131">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="061fb-132">조사 결과 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="061fb-132">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="061fb-133">조사 결과로 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="061fb-133">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="061fb-134">자세한 내용은 [AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="061fb-134">For more details, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="061fb-135">공기를 얻는 방법</span><span class="sxs-lookup"><span data-stu-id="061fb-135">How to get AIR</span></span>

<span data-ttu-id="061fb-136">Office 365의 AIR 기능은 [office 365 Advanced Threat Protection 계획 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-136">Office 365 AIR capabilities are included in [Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span></span> <span data-ttu-id="061fb-137">그러나 AIR이 예상 대로 작동 하려면 [Office 365 ATP 정책을 구성 해야](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 합니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-137">However, your [Office 365 ATP policies should be configured](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) in order for AIR to work as expected.</span></span> <span data-ttu-id="061fb-138">또한 조직의 [경고 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)검토 하 고 잠재적으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-138">In addition, make sure to review and potentially configure your organization's [alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span> 

<span data-ttu-id="061fb-139">Microsoft 365에서는 Exchange 관리자 권한 남용, 맬웨어 활동, 잠재적 외부 및 내부 위협, 정보 관리 위험을 식별 하는 데 도움이 되는 다양 한 기본 제공 경고 정책을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-139">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="061fb-140">몇 가지 [기본 경고 정책이](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 자동 조사를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-140">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="061fb-141">이러한 경계 및 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-141">These include the following:</span></span>

- <span data-ttu-id="061fb-142">잠재적으로 악의적인 URL 클릭이 검색 됨</span><span class="sxs-lookup"><span data-stu-id="061fb-142">A potentially malicious URL click is detected</span></span>

- <span data-ttu-id="061fb-143">사용자가 전자 메일 메시지를 피싱으로 보고</span><span class="sxs-lookup"><span data-stu-id="061fb-143">An email message is reported by a user as phish</span></span>

- <span data-ttu-id="061fb-144">배달이 완료 된 후 맬웨어를 포함 하는 전자 메일 메시지가 제거 됨</span><span class="sxs-lookup"><span data-stu-id="061fb-144">Email messages containing malware are removed after delivery</span></span>

- <span data-ttu-id="061fb-145">배달 후 피싱 Url이 포함 된 전자 메일 메시지가 제거 됨</span><span class="sxs-lookup"><span data-stu-id="061fb-145">Email messages containing phish URLs are removed after delivery</span></span>

- <span data-ttu-id="061fb-146">의심 스러운 전자 메일 전송 패턴이 검색 됨</span><span class="sxs-lookup"><span data-stu-id="061fb-146">Suspicious email sending patterns are detected</span></span>

- <span data-ttu-id="061fb-147">사용자가 전자 메일을 보낼 수 없도록 제한 됨</span><span class="sxs-lookup"><span data-stu-id="061fb-147">A user is restricted from sending email</span></span>

<span data-ttu-id="061fb-148">[알림 및 AIR에 대해 자세히 알아보세요](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span><span class="sxs-lookup"><span data-stu-id="061fb-148">[Learn more about alerts and AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="061fb-149">AIR 기능을 사용 하는 데 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="061fb-149">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="061fb-150">사용 권한은 다음 표에 설명 된 것과 같은 특정 역할을 통해 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-150">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="061fb-151">작업</span><span class="sxs-lookup"><span data-stu-id="061fb-151">Task</span></span> |<span data-ttu-id="061fb-152">필요한 역할</span><span class="sxs-lookup"><span data-stu-id="061fb-152">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="061fb-153">AIR 기능을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="061fb-153">To set up AIR features</span></span> |<span data-ttu-id="061fb-154">다음 역할 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-154">One of the following roles:</span></span> <br/><span data-ttu-id="061fb-155">-전역 관리자</span><span class="sxs-lookup"><span data-stu-id="061fb-155">- Global Administrator</span></span><br/><span data-ttu-id="061fb-156">-보안 관리자</span><span class="sxs-lookup"><span data-stu-id="061fb-156">- Security Administrator</span></span> <br/><span data-ttu-id="061fb-157">이러한 역할은 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에서 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-157">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="061fb-158">권장 작업을 승인 하거나 거부 하려면</span><span class="sxs-lookup"><span data-stu-id="061fb-158">To approve or reject recommended actions</span></span>|<span data-ttu-id="061fb-159">[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center))에서 할당 된 다음 역할 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-159">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="061fb-160">-전역 관리자</span><span class="sxs-lookup"><span data-stu-id="061fb-160">- Global Administrator</span></span> <br/><span data-ttu-id="061fb-161">-보안 관리자</span><span class="sxs-lookup"><span data-stu-id="061fb-161">- Security Administrator</span></span><br/><span data-ttu-id="061fb-162">-보안 독자</span><span class="sxs-lookup"><span data-stu-id="061fb-162">- Security Reader</span></span> <br/><span data-ttu-id="061fb-163">--- 및 ---</span><span class="sxs-lookup"><span data-stu-id="061fb-163">--- and ---</span></span><br/><span data-ttu-id="061fb-164">-검색 및 제거 (이 역할은 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에만 할당 됨)</span><span class="sxs-lookup"><span data-stu-id="061fb-164">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="061fb-165">여기에 새 역할 그룹을 만들고 새 역할 그룹에 검색 및 제거 역할을 추가 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061fb-165">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

## <a name="next-steps"></a><span data-ttu-id="061fb-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="061fb-166">Next steps</span></span>

- [<span data-ttu-id="061fb-167">자세한 내용은 자동화 된 조사의 세부 정보 및 결과를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="061fb-167">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="061fb-168">보류 중인 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="061fb-168">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="061fb-169">관련 문서</span><span class="sxs-lookup"><span data-stu-id="061fb-169">Related articles</span></span>

- [<span data-ttu-id="061fb-170">Microsoft Defender Advanced Threat Protection의 자동화 된 조사 및 재구성</span><span class="sxs-lookup"><span data-stu-id="061fb-170">Automated investigation and remediation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="061fb-171">Microsoft Threat Protection의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="061fb-171">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
