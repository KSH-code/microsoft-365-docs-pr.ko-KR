---
title: Microsoft Defender for Office 365에서 자동화 된 조사 및 응답을 시작 하세요.
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft Defender for Office 365의 자동화 된 조사 및 응답 기능 사용을 시작 하세요.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925607"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1d921-104">Microsoft Defender for Office 365에서 자동화 된 조사 및 응답 (AIR) 사용 시작</span><span class="sxs-lookup"><span data-stu-id="1d921-104">Get started using automated investigation and response (AIR) in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1d921-105">[Microsoft Defender For Office 365에](office-365-atp.md) 는 보안 작업 팀의 시간과 노력을 절감할 수 있는 강력한 자동화 된 조사 및 응답 (AIR) 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="1d921-106">알림이 트리거되면 해당 경고를 검토 하 고 우선 순위를 지정 하 고 응답 하는 보안 운영 팀이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="1d921-107">들어오는 알림의 볼륨을 유지 하는 것은 매우 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="1d921-108">이러한 작업 중 일부를 자동화 하는 것이 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-108">Automating some of those tasks can help.</span></span> <span data-ttu-id="1d921-109">AIR을 사용 하는 경우 보안 운영 팀은 트리거된 중요 경고의 시야 없이 우선 순위가 더 높은 작업에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of important alerts that are triggered.</span></span>

<span data-ttu-id="1d921-110">이 문서에서는 다음에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-110">This article describes:</span></span>
- <span data-ttu-id="1d921-111">[전체 공기 흐름](#the-overall-flow-of-air)</span><span class="sxs-lookup"><span data-stu-id="1d921-111">The [overall flow of AIR](#the-overall-flow-of-air);</span></span>
- <span data-ttu-id="1d921-112">[공기를 얻는 방법](#how-to-get-air) 한</span><span class="sxs-lookup"><span data-stu-id="1d921-112">[How to get AIR](#how-to-get-air); and</span></span> 
- <span data-ttu-id="1d921-113">AIR 기능을 구성 하거나 사용 하는 [데 필요한 사용 권한](#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="1d921-113">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="1d921-114">전체 공기 흐름</span><span class="sxs-lookup"><span data-stu-id="1d921-114">The overall flow of AIR</span></span>

<span data-ttu-id="1d921-115">경고가 트리거된 후 보안 playbook에서 자동화 된 조사를 시작 하 여 발견 및 권장 작업을 결과로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-115">An alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommended actions.</span></span> <span data-ttu-id="1d921-116">다음은 AIR의 전체 흐름을 단계별로 설명한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-116">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="1d921-117">자동화 된 조사가 다음 중 한 가지 방법으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-117">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="1d921-118">[경고](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 는 전자 메일 (예: 메시지, 첨부 파일 또는 URL)으로 의심 되는 항목에 의해 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-118">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by something suspicious in email (such as a message, attachment, or URL).</span></span> <span data-ttu-id="1d921-119">인시던트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-119">An incident is created.</span></span> <span data-ttu-id="1d921-120">인시던트 유형에 따라 [보안 playbook](automated-investigation-response-office.md#security-playbooks) 실행 되 고 자동 조사가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-120">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) runs, and an automated investigation begins.</span></span> 

     <span data-ttu-id="1d921-121">--- 또는 ---</span><span class="sxs-lookup"><span data-stu-id="1d921-121">--- or ---</span></span>
   
   - <span data-ttu-id="1d921-122">보안 분석가가 [Threat Explorer](threat-explorer.md)를 사용 하는 동안 [자동화 된 조사를 시작](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-122">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="1d921-123">자동화 된 조사가 실행 되는 동안에는 해당 전자 메일에 대 한 추가 데이터와 해당 전자 메일에 관련 된 엔터티가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-123">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="1d921-124">이러한 엔터티는 파일, Url 및 받는 사람을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-124">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="1d921-125">새 경고 및 관련 경고가 트리거되면 조사의 범위가 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-125">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="1d921-126">자동화 된 조사 도중 및 후에 [세부 정보 및 결과](air-view-investigation-results.md) 를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-126">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="1d921-127">결과에는 발견 된 모든 위협에 응답 하 고 문제를 수정 하기 위해 취할 수 있는 [권장 작업이](air-remediation-actions.md) 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-127">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond to and remediate any threats that were found.</span></span> <span data-ttu-id="1d921-128">또한 모든 조사 활동을 추적 하는 [playbook 로그](air-view-investigation-results.md#playbook-log) 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-128">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>


4. <span data-ttu-id="1d921-129">보안 운영 팀은 [조사 결과 및 권장 사항을](air-view-investigation-results.md)검토 하 고 [재구성 작업을 승인 하거나 거부](air-review-approve-pending-completed-actions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-129">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

5. <span data-ttu-id="1d921-130">보류 중인 재구성 작업이 승인 되거나 거부 됨에 따라 자동 조사가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-130">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d921-131">Office 365 용 Microsoft Defender에는 자동으로 수정 작업이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-131">In Microsoft Defender for Office 365, no remediation actions are taken automatically.</span></span> <span data-ttu-id="1d921-132">수정 작업은 조직의 보안 팀이 승인한 경우에만 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-132">Remediation actions are taken only upon approval by your organization's security team.</span></span> <span data-ttu-id="1d921-133">그러나 AIR 역량은 수정 작업을 식별 하 고 의사 결정을 내리는 데 필요한 세부 정보를 제공 하 여 보안 운영 팀의 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-133">However, AIR capabilities save your security operations team time by identifying remediation actions and providing the details needed to make an informed decision.</span></span>

<span data-ttu-id="1d921-134">보안 운영 팀은 각 자동화 된 조사 중 및 후에 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-134">During and after each automated investigation, your security operations team can:</span></span>

- [<span data-ttu-id="1d921-135">조사와 관련 된 경고에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1d921-135">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="1d921-136">조사 결과 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1d921-136">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="1d921-137">조사 결과로 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="1d921-137">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="1d921-138">자세한 개요는 [AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d921-138">For a more detailed overview, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="1d921-139">공기를 얻는 방법</span><span class="sxs-lookup"><span data-stu-id="1d921-139">How to get AIR</span></span>

<span data-ttu-id="1d921-140">정책 및 경고가 구성 된 경우 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)에 포함 된 AIR 기능</span><span class="sxs-lookup"><span data-stu-id="1d921-140">AIR capabilities are included in [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2), provided your policies and alerts are configured.</span></span> <span data-ttu-id="1d921-141">이에 대 한 몇 가지 도움이 필요 하면 [위협 으로부터 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 의 지침을 따라 다음 보호 설정을 설정 하거나 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-141">If you would like some help with this, follow the guidance in [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) to set up or configure the following protection settings:</span></span> 

1. <span data-ttu-id="1d921-142">[감사 로깅](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (설정 해야 함)</span><span class="sxs-lookup"><span data-stu-id="1d921-142">[Audit logging](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (should be turned on)</span></span>

2. [<span data-ttu-id="1d921-143">맬웨어 방지 정책</span><span class="sxs-lookup"><span data-stu-id="1d921-143">Antimalware policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [<span data-ttu-id="1d921-144">피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="1d921-144">Antiphishing protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. <span data-ttu-id="1d921-145">[스팸 방지 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection)</span><span class="sxs-lookup"><span data-stu-id="1d921-145">[Antispam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).</span></span>
   
5. <span data-ttu-id="1d921-146">[안전한 링크 및 안전한 첨부 파일](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="1d921-146">[Safe Links and Safe Attachments](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).</span></span>
   
6. <span data-ttu-id="1d921-147">[SharePoint, OneDrive 및 Microsoft 팀에 대 한 안전한 첨부 파일](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)</span><span class="sxs-lookup"><span data-stu-id="1d921-147">[Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).</span></span>
   
7. <span data-ttu-id="1d921-148">[전자 메일에 대해 제로 시간 자동 삭제](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop)</span><span class="sxs-lookup"><span data-stu-id="1d921-148">[Zero-hour auto purge for email](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).</span></span>

<span data-ttu-id="1d921-149">또한 [조직의 경고 정책](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), 특히 [위협 관리 범주에 있는 기본 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-149">In addition, make sure to [review your organization's alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), especially the [default policies in the Threat management category](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies).</span></span> 

## <a name="which-alert-policies-trigger-automated-investigations"></a><span data-ttu-id="1d921-150">자동 조사를 트리거하는 경고 정책은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="1d921-150">Which alert policies trigger automated investigations?</span></span>

<span data-ttu-id="1d921-151">Microsoft 365에서는 Exchange 관리자 권한 남용, 맬웨어 활동, 잠재적 외부 및 내부 위협, 정보 관리 위험을 식별 하는 데 도움이 되는 다양 한 기본 제공 경고 정책을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-151">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="1d921-152">몇 가지 [기본 경고 정책이](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 자동 조사를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-152">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="1d921-153">이러한 경계 및 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-153">These include the following:</span></span>

- <span data-ttu-id="1d921-154">잠재적으로 악의적인 URL 클릭이 검색 됨</span><span class="sxs-lookup"><span data-stu-id="1d921-154">A potentially malicious URL click is detected</span></span>
- <span data-ttu-id="1d921-155">사용자가 전자 메일 메시지를 피싱으로 보고</span><span class="sxs-lookup"><span data-stu-id="1d921-155">An email message is reported by a user as phish</span></span>
- <span data-ttu-id="1d921-156">배달이 완료 된 후 맬웨어를 포함 하는 전자 메일 메시지가 제거 됨</span><span class="sxs-lookup"><span data-stu-id="1d921-156">Email messages containing malware are removed after delivery</span></span>
- <span data-ttu-id="1d921-157">배달 후 피싱 Url이 포함 된 전자 메일 메시지가 제거 됨</span><span class="sxs-lookup"><span data-stu-id="1d921-157">Email messages containing phish URLs are removed after delivery</span></span>
- <span data-ttu-id="1d921-158">의심 스러운 전자 메일 전송 패턴이 검색 됨</span><span class="sxs-lookup"><span data-stu-id="1d921-158">Suspicious email sending patterns are detected</span></span>
- <span data-ttu-id="1d921-159">사용자가 전자 메일을 보낼 수 없도록 제한 됨</span><span class="sxs-lookup"><span data-stu-id="1d921-159">A user is restricted from sending email</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="1d921-160">AIR 기능을 사용 하는 데 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="1d921-160">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="1d921-161">사용 권한은 다음 표에 설명 된 것과 같은 특정 역할을 통해 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-161">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="1d921-162">작업</span><span class="sxs-lookup"><span data-stu-id="1d921-162">Task</span></span> |<span data-ttu-id="1d921-163">필요한 역할</span><span class="sxs-lookup"><span data-stu-id="1d921-163">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="1d921-164">AIR 기능을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1d921-164">To set up AIR features</span></span> |<span data-ttu-id="1d921-165">다음 역할 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-165">One of the following roles:</span></span> <br/><span data-ttu-id="1d921-166">-전역 관리자</span><span class="sxs-lookup"><span data-stu-id="1d921-166">- Global Administrator</span></span><br/><span data-ttu-id="1d921-167">-보안 관리자</span><span class="sxs-lookup"><span data-stu-id="1d921-167">- Security Administrator</span></span> <br/><span data-ttu-id="1d921-168">이러한 역할은 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에서 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-168">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="1d921-169">권장 작업을 승인 하거나 거부 하려면</span><span class="sxs-lookup"><span data-stu-id="1d921-169">To approve or reject recommended actions</span></span>|<span data-ttu-id="1d921-170">[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center))에서 할당 된 다음 역할 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-170">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="1d921-171">-전역 관리자</span><span class="sxs-lookup"><span data-stu-id="1d921-171">- Global Administrator</span></span> <br/><span data-ttu-id="1d921-172">-보안 관리자</span><span class="sxs-lookup"><span data-stu-id="1d921-172">- Security Administrator</span></span><br/><span data-ttu-id="1d921-173">-보안 독자</span><span class="sxs-lookup"><span data-stu-id="1d921-173">- Security Reader</span></span> <br/><span data-ttu-id="1d921-174">--- 및 ---</span><span class="sxs-lookup"><span data-stu-id="1d921-174">--- and ---</span></span><br/><span data-ttu-id="1d921-175">-검색 및 제거 (이 역할은 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에만 할당 됨)</span><span class="sxs-lookup"><span data-stu-id="1d921-175">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="1d921-176">여기에 새 역할 그룹을 만들고 새 역할 그룹에 검색 및 제거 역할을 추가 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-176">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

## <a name="required-licenses"></a><span data-ttu-id="1d921-177">필수 라이선스</span><span class="sxs-lookup"><span data-stu-id="1d921-177">Required licenses</span></span>

<span data-ttu-id="1d921-178">[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) 라이선스는 다음에 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d921-178">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="1d921-179">보안 관리자 (전역 관리자 포함)</span><span class="sxs-lookup"><span data-stu-id="1d921-179">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="1d921-180">조직의 보안 운영 팀 (보안 판독기 및 검색 및 제거 역할을 포함 하는 작업)</span><span class="sxs-lookup"><span data-stu-id="1d921-180">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="1d921-181">최종 사용자</span><span class="sxs-lookup"><span data-stu-id="1d921-181">End users</span></span>


## <a name="next-steps"></a><span data-ttu-id="1d921-182">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1d921-182">Next steps</span></span>

- [<span data-ttu-id="1d921-183">자세한 내용은 자동화 된 조사의 세부 정보 및 결과를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d921-183">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="1d921-184">보류 중인 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="1d921-184">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="1d921-185">관련 문서</span><span class="sxs-lookup"><span data-stu-id="1d921-185">Related articles</span></span>

- [<span data-ttu-id="1d921-186">끝점에 대 한 Microsoft Defender의 자동화 된 조사 및 재구성</span><span class="sxs-lookup"><span data-stu-id="1d921-186">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="1d921-187">Microsoft 365 Defender의 자동화 된 조사 및 응답</span><span class="sxs-lookup"><span data-stu-id="1d921-187">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
